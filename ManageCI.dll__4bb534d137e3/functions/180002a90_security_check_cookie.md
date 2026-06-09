# __security_check_cookie

- ea: `0x180002a90`
- end: `0x180002aae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `77`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012b8`
- `0x18000156c`
- `0x180001864`
- `0x180001a88`
- `0x180001b28`
- `0x180001c28`
- `0x180001da4`
- `0x180001e80`
- `0x180001fe4`
- `0x180002054`
- `0x1800031ec`
- `0x180003d6c`
- `0x1800043f8`
- `0x1800046a4`
- `0x180005968`
- `0x180005b00`
- `0x180005f24`
- `0x180006320`
- `0x180007e1c`
- `0x180008810`
- `0x180008cc0`
- `0x180009160`
- `0x180009370`
- `0x180009610`
- `0x18000a794`
- `0x18000ad4c`
- `0x18000b134`
- `0x18000b540`
- `0x18000beac`
- `0x18000c520`
- `0x18000d790`
- `0x18000d9c4`
- `0x18000e0a0`
- `0x18000eb30`
- `0x18000fb60`
- `0x180010358`
- `0x180010534`
- `0x180011d00`
- `0x180011f20`
- `0x180012110`
- `0x180012280`
- `0x1800123e0`
- `0x1800128f0`
- `0x180012e20`
- `0x180012f90`
- `0x180013660`
- `0x180015a6c`
- `0x1800168d8`
- `0x180017928`

## callees

- `0x180002a90`
- `0x180003690`

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
0x180002a90  cmp     rcx, cs:__security_cookie
0x180002a97  jnz     short ReportFailure
0x180002a99  rol     rcx, 10h
0x180002a9d  test    cx, 0FFFFh
0x180002aa2  jnz     short RestoreRcx
0x180002aa4  retn
0x180002aa5  ror     rcx, 10h; StackCookie
0x180002aa9  jmp     __report_gsfailure
```
