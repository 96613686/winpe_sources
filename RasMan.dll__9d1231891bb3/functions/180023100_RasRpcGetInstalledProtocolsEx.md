# RasRpcGetInstalledProtocolsEx

- ea: `0x180023100`
- end: `0x18002312e`
- name: `RasRpcGetInstalledProtocolsEx`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023123`
- `RPCRT4!NdrClientCall3` at `0x180023123`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetInstalledProtocolsEx(__int64 a1, int a2, int a3, int a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xEu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180023100  sub     rsp, 48h
0x180023104  mov     [rsp+48h+var_18], r9d
0x180023109  mov     r9, rcx
0x18002310c  mov     [rsp+48h+var_20], r8d
0x180023111  lea     rcx, pProxyInfo; pProxyInfo
0x180023118  xor     r8d, r8d; pReturnValue
0x18002311b  mov     [rsp+48h+var_28], edx
0x18002311f  lea     edx, [r8+0Eh]; nProcNum
0x180023123  call    cs:__imp_NdrClientCall3
0x180023129  add     rsp, 48h
0x18002312d  retn
```
