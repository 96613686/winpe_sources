# __security_check_cookie

- ea: `0x1800106c0`
- end: `0x1800106de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001dc4`
- `0x180001f30`
- `0x180002628`
- `0x18000296c`
- `0x180002c80`
- `0x180002eb0`
- `0x180003460`
- `0x1800039d0`
- `0x1800048e0`
- `0x180005030`
- `0x180006800`
- `0x180007dd0`
- `0x180009940`
- `0x18000a960`
- `0x18000b8f4`
- `0x18000c380`
- `0x18000d000`
- `0x18000d630`
- `0x18000e1c0`
- `0x18000ed70`
- `0x18000eff0`
- `0x18000fd94`
- `0x180011a18`
- `0x180011f20`
- `0x180012370`
- `0x1800124d0`
- `0x18001334c`
- `0x1800135e8`
- `0x180013d08`
- `0x180013ed0`
- `0x1800144e4`
- `0x180014908`
- `0x180016158`
- `0x1800168a0`
- `0x180016ec4`
- `0x180017100`
- `0x180017d30`
- `0x1800187a0`
- `0x180018bb0`
- `0x180018e40`
- `0x1800194d0`
- `0x180019920`
- `0x180019c9c`
- `0x18001a690`
- `0x18001aa80`
- `0x18001d52c`
- `0x18001dec0`
- `0x180020664`

## callees

- `0x1800106c0`
- `0x1800106f0`

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
0x1800106c0  cmp     rcx, cs:__security_cookie
0x1800106c7  jnz     short ReportFailure
0x1800106c9  rol     rcx, 10h
0x1800106cd  test    cx, 0FFFFh
0x1800106d2  jnz     short RestoreRcx
0x1800106d4  retn
0x1800106d5  ror     rcx, 10h; StackCookie
0x1800106d9  jmp     __report_gsfailure
```
