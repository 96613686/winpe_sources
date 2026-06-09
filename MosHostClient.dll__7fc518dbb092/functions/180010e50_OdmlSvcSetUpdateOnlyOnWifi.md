# OdmlSvcSetUpdateOnlyOnWifi

- ea: `0x180010e50`
- end: `0x180010e74`
- name: `OdmlSvcSetUpdateOnlyOnWifi`
- size: `36`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010e69`
- `RPCRT4!NdrClientCall3` at `0x180010e69`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcSetUpdateOnlyOnWifi(__int64 a1, int a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0xEu, 0, a1, a2);
}

```

## disassembly

```asm
0x180010e50  sub     rsp, 38h
0x180010e54  xor     r8d, r8d; pReturnValue
0x180010e57  mov     [rsp+38h+var_18], edx
0x180010e5b  mov     r9, rcx
0x180010e5e  lea     rcx, stru_180013630; pProxyInfo
0x180010e65  lea     edx, [r8+0Eh]; nProcNum
0x180010e69  call    cs:__imp_NdrClientCall3
0x180010e6f  add     rsp, 38h
0x180010e73  retn
```
