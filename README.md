# AddOrgAndOrdererAtRuntime

## 1. Hyperledger fabric network details

## 2. Repository Folder Structure

- Check the artifacts folder - docker-compose.yaml (2 ca-org, 3 orderer, 4 couchdb, 4 peers)

## 3. Create cryptomaterials for all network Participant

- Check create-artifacts.sh
- Move to artifacts/channel folder
- Create artifacts
```bash
./create-artifacts.sh
```
- Check genesis.block, mychannel.tx, Org1MSPanchors.tx and Org2 MSPanchors.tx
- Check crypto-config folder

## 4. Create channel artefacts (Genesis block, channel.tx file, etc.)

- Check crypto-config.yaml

```yaml
EnableNodeOUs: true
```

- Check crypto-config/ordererOrganizations/eample.com/config.yaml (NodeOUs - Node Organizational Units)

```yaml
NodeOUs:
  Enable: true
  ClientOUIdentifier:
    Certificate: cacerts/ca.example.com-cert.pem
    OrganizationalUnitIdentifier: client
  PeerOUIdentifier:
    Certificate: cacerts/ca.example.com-cert.pem
    OrganizationalUnitIdentifier: peer
  AdminOUIdentifier:
    Certificate: cacerts/ca.example.com-cert.pem
    OrganizationalUnitIdentifier: admin
  OrdererOUIdentifier:
    Certificate: cacerts/ca.example.com-cert.pem
    OrganizationalUnitIdentifier: orderer
```

## 9. Docker-Compose file Walk-through (Alll services)

Just explain

## . 10. Run all services in network

- Total 13 services
- go to artifacts folder
- Execute the following command (docker-compoase detached mode)

```bash
docker-compose up -d
```