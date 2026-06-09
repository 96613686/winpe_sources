# __security_check_cookie

- ea: `0x18004d240`
- end: `0x18004d25e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `473`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x180002d70`
- `0x1800036cc`
- `0x180004070`
- `0x180004710`
- `0x1800048e0`
- `0x180004cd0`
- `0x180004e40`
- `0x1800050e0`
- `0x180005360`
- `0x180005524`
- `0x180005600`
- `0x180005700`
- `0x1800057b0`
- `0x18000653c`
- `0x18000681c`
- `0x180007200`
- `0x180007300`
- `0x1800078b0`
- `0x180007bac`
- `0x180007e44`
- `0x180007f10`
- `0x180008028`
- `0x180008120`
- `0x180008840`
- `0x180008d24`
- `0x1800090e4`
- `0x18000a400`
- `0x18000ace0`
- `0x18000b6f0`
- `0x18000c15c`
- `0x18000c1fc`
- `0x18000c280`
- `0x18000c890`
- `0x18000cd70`
- `0x18000ce80`
- `0x18000cf40`
- `0x18000d134`
- `0x18000d2b4`
- `0x18000d450`
- `0x18000d740`
- `0x18000dee0`
- `0x18000e900`
- `0x18000eb70`
- `0x18000efc4`
- `0x18000f104`
- `0x18000f1f0`
- `0x18000f730`
- `0x18000f830`
- `0x18000f89c`

## callees

- `0x18004d240`
- `0x18004eff0`

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
0x18004d240  cmp     rcx, cs:__security_cookie
0x18004d247  jnz     short ReportFailure
0x18004d249  rol     rcx, 10h
0x18004d24d  test    cx, 0FFFFh
0x18004d252  jnz     short RestoreRcx
0x18004d254  retn
0x18004d255  ror     rcx, 10h; StackCookie
0x18004d259  jmp     __report_gsfailure
```
