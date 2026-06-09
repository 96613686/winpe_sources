# __security_check_cookie

- ea: `0x180002380`
- end: `0x18000239e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `80`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012cc`
- `0x18000133c`
- `0x1800013cc`
- `0x180001670`
- `0x180001968`
- `0x180002c5c`
- `0x180005220`
- `0x180005fb0`
- `0x18000625c`
- `0x180006908`
- `0x180006aa0`
- `0x180006e94`
- `0x180007350`
- `0x180008aec`
- `0x1800090f0`
- `0x1800098d0`
- `0x180009e74`
- `0x18000a52c`
- `0x18000abdc`
- `0x18000ac74`
- `0x18000b140`
- `0x18000b264`
- `0x18000b7c8`
- `0x18000c230`
- `0x18000d280`
- `0x18000d3d4`
- `0x18000de9c`
- `0x18000df9c`
- `0x18000e24c`
- `0x18000e6b0`
- `0x18000e794`
- `0x18000e814`
- `0x18000ea04`
- `0x18000ed48`
- `0x18000ee28`
- `0x18001250c`
- `0x1800126c4`
- `0x180012f74`
- `0x180013210`
- `0x18001334c`
- `0x1800133d0`
- `0x1800136c8`
- `0x180014160`
- `0x180014610`
- `0x180014c5c`
- `0x180014eb4`
- `0x180015030`
- `0x180015680`
- `0x180015714`

## callees

- `0x180002380`
- `0x180003110`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180002380  cmp     rcx, cs:__security_cookie
0x180002387  jnz     short ReportFailure
0x180002389  rol     rcx, 10h
0x18000238d  test    cx, 0FFFFh
0x180002392  jnz     short RestoreRcx
0x180002394  retn
0x180002395  ror     rcx, 10h; StackCookie
0x180002399  jmp     __report_gsfailure
```
