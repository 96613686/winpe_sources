# __security_check_cookie

- ea: `0x180012fc0`
- end: `0x180012fde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001280`
- `0x180001cb0`
- `0x180003ea0`
- `0x180003f10`
- `0x180003f80`
- `0x1800048d0`
- `0x180004fe4`
- `0x180005104`
- `0x180005238`
- `0x180005388`
- `0x1800054bc`
- `0x180005584`
- `0x18000565c`
- `0x1800056e0`
- `0x180005860`
- `0x1800066d0`
- `0x180006ac0`
- `0x180006e30`
- `0x1800073ec`
- `0x1800074a8`
- `0x180007768`
- `0x180007ba8`
- `0x180008000`
- `0x180008780`
- `0x1800089d0`
- `0x1800095a8`
- `0x180009750`
- `0x180009a50`
- `0x180009b20`
- `0x180009eec`
- `0x18000a220`
- `0x18000a590`
- `0x18000a640`
- `0x18000a760`
- `0x18000a8dc`
- `0x18000a9f0`
- `0x18000ab80`
- `0x18000af00`
- `0x18000b390`
- `0x18000b5e0`
- `0x18000b770`
- `0x18000b940`
- `0x18000be70`
- `0x18000c000`
- `0x18000c190`
- `0x18000c330`
- `0x18000c570`
- `0x18000ca70`
- `0x18000cc00`
- `0x18000cec0`

## callees

- `0x1800024f0`
- `0x180012fc0`

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
0x180012fc0  cmp     rcx, cs:__security_cookie
0x180012fc7  jnz     short ReportFailure
0x180012fc9  rol     rcx, 10h
0x180012fcd  test    cx, 0FFFFh
0x180012fd2  jnz     short RestoreRcx
0x180012fd4  retn
0x180012fd5  ror     rcx, 10h
0x180012fd9  jmp     __report_gsfailure
```
