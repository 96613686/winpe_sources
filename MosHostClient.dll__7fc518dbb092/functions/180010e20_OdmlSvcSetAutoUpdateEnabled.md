# OdmlSvcSetAutoUpdateEnabled

- ea: `0x180010e20`
- end: `0x180010e44`
- name: `OdmlSvcSetAutoUpdateEnabled`
- size: `36`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010e39`
- `RPCRT4!NdrClientCall3` at `0x180010e39`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcSetAutoUpdateEnabled(__int64 a1, int a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0xCu, 0, a1, a2);
}

```

## disassembly

```asm
0x180010e20  sub     rsp, 38h
0x180010e24  xor     r8d, r8d; pReturnValue
0x180010e27  mov     [rsp+38h+var_18], edx
0x180010e2b  mov     r9, rcx
0x180010e2e  lea     rcx, stru_180013630; pProxyInfo
0x180010e35  lea     edx, [r8+0Ch]; nProcNum
0x180010e39  call    cs:__imp_NdrClientCall3
0x180010e3f  add     rsp, 38h
0x180010e43  retn
```
