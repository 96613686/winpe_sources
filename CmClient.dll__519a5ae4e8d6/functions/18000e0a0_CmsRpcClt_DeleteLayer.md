# CmsRpcClt_DeleteLayer

- ea: `0x18000e0a0`
- end: `0x18000e0b8`
- name: `CmsRpcClt_DeleteLayer`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e0b1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_DeleteLayer(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x46u, 0, a1);
}

```

## disassembly

```asm
0x18000e0a0  xor     r8d, r8d
0x18000e0a3  mov     r9, rcx
0x18000e0a6  lea     rcx, pProxyInfo
0x18000e0ad  lea     edx, [r8+46h]
0x18000e0b1  jmp     cs:__imp_NdrClientCall3
```
