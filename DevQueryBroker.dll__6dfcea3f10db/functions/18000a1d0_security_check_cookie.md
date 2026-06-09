# __security_check_cookie

- ea: `0x18000a1d0`
- end: `0x18000a1ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024ac`
- `0x180002e18`
- `0x180003f80`
- `0x180004e98`
- `0x180005134`
- `0x18000596c`
- `0x180005d10`
- `0x1800060e0`
- `0x180006b44`
- `0x180006ebc`
- `0x180007afc`
- `0x180007d7c`
- `0x180008648`
- `0x1800094c8`
- `0x180009e08`
- `0x18000a11c`

## callees

- `0x1800019f0`
- `0x18000a1d0`

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
0x18000a1d0  cmp     rcx, cs:__security_cookie
0x18000a1d7  jnz     short ReportFailure
0x18000a1d9  rol     rcx, 10h
0x18000a1dd  test    cx, 0FFFFh
0x18000a1e2  jnz     short RestoreRcx
0x18000a1e4  retn
0x18000a1e5  ror     rcx, 10h
0x18000a1e9  jmp     __report_gsfailure
```
