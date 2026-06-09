# CmsRpcClt_DeleteStorage

- ea: `0x18000e0c0`
- end: `0x18000e0d8`
- name: `CmsRpcClt_DeleteStorage`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e0d1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_DeleteStorage(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Eu, 0, a1);
}

```

## disassembly

```asm
0x18000e0c0  xor     r8d, r8d
0x18000e0c3  mov     r9, rcx
0x18000e0c6  lea     rcx, pProxyInfo
0x18000e0cd  lea     edx, [r8+2Eh]
0x18000e0d1  jmp     cs:__imp_NdrClientCall3
```
