# ScaleDB Demo

A demonstration of MySQL database scaling using ReadySet (SQL caching layer) and ProxySQL (connection pooling and routing).

## Quick Start

### Using ScaleDB CLI (recommended):
```bash
# Start all services
./scaledb-cli up

# Check service status
./scaledb-cli status

# Connect to MySQL
./scaledb-cli mysql

# View logs
./scaledb-cli logs

# View ReadySet logs specifically
./scaledb-cli logs readyset

# Stop all services
./scaledb-cli down

# Get help
./scaledb-cli help
```

### Manual start with architecture-specific configs:
```bash
# For x86_64 (Intel/AMD)
docker compose -f docker-compose.yml -f docker-compose.x86_64.yml up -d

# For ARM64 (M1/M2/M3 Macs)
docker compose -f docker-compose.yml -f docker-compose.arm64.yml up -d
```

## Architecture Support

- **x86_64**: Uses official ReadySet image
- **ARM64**: Uses altmannmarcelo/readyset-mac image for Apple Silicon compatibility

## Services

- **MySQL** (port 3306): Primary database
- **ProxySQL** (port 6033): Connection pooling and query routing
- **ReadySet** (port 3307): SQL caching layer
- **Grafana** (port 4000): Monitoring dashboard
- **Prometheus**: Metrics collection
