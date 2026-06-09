# MapsStorageSvcGetDataDirectory

- ea: `0x1800105d0`
- end: `0x1800105fa`
- name: `MapsStorageSvcGetDataDirectory`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800105ef`
- `RPCRT4!NdrClientCall3` at `0x1800105ef`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MapsStorageSvcGetDataDirectory(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013F60, 6u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x1800105d0  sub     rsp, 38h
0x1800105d4  mov     [rsp+38h+var_10], r8d
0x1800105d9  mov     r9, rcx
0x1800105dc  xor     r8d, r8d; pReturnValue
0x1800105df  mov     [rsp+38h+var_18], rdx
0x1800105e4  lea     rcx, stru_180013F60; pProxyInfo
0x1800105eb  lea     edx, [r8+6]; nProcNum
0x1800105ef  call    cs:__imp_NdrClientCall3
0x1800105f5  add     rsp, 38h
0x1800105f9  retn
```
