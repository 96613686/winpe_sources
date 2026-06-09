# MapsStorageSvcOpen

- ea: `0x180010660`
- end: `0x18001068c`
- name: `MapsStorageSvcOpen`
- size: `44`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010681`
- `RPCRT4!NdrClientCall3` at `0x180010681`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall MapsStorageSvcOpen(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180013F60, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010660  sub     rsp, 48h
0x180010664  mov     [rsp+48h+var_18], r9
0x180010669  mov     r9, rcx
0x18001066c  mov     [rsp+48h+var_20], r8
0x180010671  lea     rcx, stru_180013F60; pProxyInfo
0x180010678  mov     [rsp+48h+var_28], edx
0x18001067c  xor     r8d, r8d; pReturnValue
0x18001067f  xor     edx, edx; nProcNum
0x180010681  call    cs:__imp_NdrClientCall3
0x180010687  add     rsp, 48h
0x18001068b  retn
```
