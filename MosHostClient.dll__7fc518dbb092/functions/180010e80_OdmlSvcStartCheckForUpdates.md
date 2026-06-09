# OdmlSvcStartCheckForUpdates

- ea: `0x180010e80`
- end: `0x180010e98`
- name: `OdmlSvcStartCheckForUpdates`
- size: `24`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010e91`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcStartCheckForUpdates(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 2u, 0, a1);
}

```

## disassembly

```asm
0x180010e80  xor     r8d, r8d
0x180010e83  mov     r9, rcx
0x180010e86  lea     rcx, stru_180013630
0x180010e8d  lea     edx, [r8+2]
0x180010e91  jmp     cs:__imp_NdrClientCall3
```
