# OdmlSvcDeleteAllMaps

- ea: `0x180010bc0`
- end: `0x180010bd8`
- name: `OdmlSvcDeleteAllMaps`
- size: `24`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010bd1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall OdmlSvcDeleteAllMaps(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013630, 0xAu, 0, a1);
}

```

## disassembly

```asm
0x180010bc0  xor     r8d, r8d
0x180010bc3  mov     r9, rcx
0x180010bc6  lea     rcx, stru_180013630
0x180010bcd  lea     edx, [r8+0Ah]
0x180010bd1  jmp     cs:__imp_NdrClientCall3
```
