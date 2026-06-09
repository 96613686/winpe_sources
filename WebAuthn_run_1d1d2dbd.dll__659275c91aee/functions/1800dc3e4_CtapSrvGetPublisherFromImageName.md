# _CtapSrvGetPublisherFromImageName

- ea: `0x1800dc3e4`
- end: `0x1800dc640`
- name: `_CtapSrvGetPublisherFromImageName`
- size: `604`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000d640`
- `0x18001dfb8`

## callees

- `0x18002bbf4`
- `0x1800466ec`
- `0x18005378c`
- `0x1800537a4`
- `0x1800dc3e4`
- `0x1800dc690`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc5b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc5b5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dc5f3`
- `CRYPT32!CertFreeCertificateContext` at `0x1800dc5f3`
- `CRYPT32!CertGetNameStringW` at `0x1800dc568`
- `CRYPT32!CertGetNameStringW` at `0x1800dc594`
- `CRYPT32!CertGetNameStringW` at `0x1800dc568`
- `CRYPT32!CertGetNameStringW` at `0x1800dc594`
- `RPCRT4!RpcImpersonateClient` at `0x1800dc49c`
- `RPCRT4!RpcImpersonateClient` at `0x1800dc49c`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dc4f8`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800dc4f8`
- `WINTRUST!WTGetSignatureInfo` at `0x1800dc459`
- `WINTRUST!WTGetSignatureInfo` at `0x1800dc4ed`
- `WINTRUST!WTGetSignatureInfo` at `0x1800dc459`
- `WINTRUST!WTGetSignatureInfo` at `0x1800dc4ed`

## string_xrefs

- `0x1800dc4a8`: `Impersonate`
- `0x1800dc481`: `NoImpersonateGetInfo`

## pseudocode

```c

```
