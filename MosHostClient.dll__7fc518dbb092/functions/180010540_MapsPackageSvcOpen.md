# MapsPackageSvcOpen

- ea: `0x180010540`
- end: `0x18001056c`
- name: `MapsPackageSvcOpen`
- size: `44`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010561`
- `RPCRT4!NdrClientCall3` at `0x180010561`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MapsPackageSvcOpen(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010540  sub     rsp, 48h
0x180010544  mov     [rsp+48h+var_18], r9
0x180010549  mov     r9, rcx
0x18001054c  mov     [rsp+48h+var_20], r8
0x180010551  lea     rcx, pProxyInfo; pProxyInfo
0x180010558  mov     [rsp+48h+var_28], edx
0x18001055c  xor     r8d, r8d; pReturnValue
0x18001055f  xor     edx, edx; nProcNum
0x180010561  call    cs:__imp_NdrClientCall3
0x180010567  add     rsp, 48h
0x18001056b  retn
```
