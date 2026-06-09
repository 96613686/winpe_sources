# CmsRpcClt_SetDebugConfigurationForLayer

- ea: `0x18000e830`
- end: `0x18000e855`
- name: `CmsRpcClt_SetDebugConfigurationForLayer`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e84a`
- `RPCRT4!NdrClientCall3` at `0x18000e84a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_SetDebugConfigurationForLayer(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x43u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000e830  sub     rsp, 38h
0x18000e834  xor     r8d, r8d; pReturnValue
0x18000e837  mov     [rsp+38h+var_18], rdx
0x18000e83c  mov     r9, rcx
0x18000e83f  lea     rcx, pProxyInfo; pProxyInfo
0x18000e846  lea     edx, [r8+43h]; nProcNum
0x18000e84a  call    cs:__imp_NdrClientCall3
0x18000e850  add     rsp, 38h
0x18000e854  retn
```
