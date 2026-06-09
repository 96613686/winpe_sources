# CMonitorManager::CreateStreamConnection(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,StreamConnectionSettings *,std::shared_ptr<CStreamConnection> &)

- ea: `0x1800b7d0c`
- end: `0x1800b8053`
- name: `?CreateStreamConnection@CMonitorManager@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUStreamConnectionSettings@@AEAV?$shared_ptr@VCStreamConnection@@@3@@Z`
- size: `839`
- prototype: `int __fastcall(CMonitorManager *this, unsigned __int16 *, unsigned __int16 *, struct StreamConnectionSettings *, __int64 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180129420`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x180019998`
- `0x1800237e0`
- `0x180032600`
- `0x1800a4af8`
- `0x1800afbc4`
- `0x1800b7d0c`
- `0x1800b805c`
- `0x1800b81e0`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800e77a0`
- `0x1800e9a40`
- `0x1800f2d40`
- `0x180128970`
- `0x180128bf0`
- `0x180129468`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800b7d67`
- `RPCRT4!RpcImpersonateClient` at `0x1800b7d67`
- `RPCRT4!RpcRevertToSelf` at `0x1800b7e2c`
- `RPCRT4!RpcRevertToSelf` at `0x1800b7e6f`
- `RPCRT4!RpcRevertToSelf` at `0x1800b7e2c`
- `RPCRT4!RpcRevertToSelf` at `0x1800b7e6f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b7db9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b7db9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800b7df8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800b7df8`

## pseudocode

```c

```
