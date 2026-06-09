# OdmlSvcGetAutoUpdateEnabled

- ea: `0x180010c50`
- end: `0x180010c75`
- name: `OdmlSvcGetAutoUpdateEnabled`
- size: `37`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010c6a`
- `RPCRT4!NdrClientCall3` at `0x180010c6a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcGetAutoUpdateEnabled(__int64 a1, __int64 a2)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0xDu, 0, a1, a2);
}

```

## disassembly

```asm
0x180010c50  sub     rsp, 38h
0x180010c54  xor     r8d, r8d; pReturnValue
0x180010c57  mov     [rsp+38h+var_18], rdx
0x180010c5c  mov     r9, rcx
0x180010c5f  lea     rcx, stru_180013630; pProxyInfo
0x180010c66  lea     edx, [r8+0Dh]; nProcNum
0x180010c6a  call    cs:__imp_NdrClientCall3
0x180010c70  add     rsp, 38h
0x180010c74  retn
```
