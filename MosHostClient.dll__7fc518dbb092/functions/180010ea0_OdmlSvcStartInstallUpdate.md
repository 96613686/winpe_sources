# OdmlSvcStartInstallUpdate

- ea: `0x180010ea0`
- end: `0x180010eb8`
- name: `OdmlSvcStartInstallUpdate`
- size: `24`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010eb1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcStartInstallUpdate(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 3u, 0, a1);
}

```

## disassembly

```asm
0x180010ea0  xor     r8d, r8d
0x180010ea3  mov     r9, rcx
0x180010ea6  lea     rcx, stru_180013630
0x180010ead  lea     edx, [r8+3]
0x180010eb1  jmp     cs:__imp_NdrClientCall3
```
