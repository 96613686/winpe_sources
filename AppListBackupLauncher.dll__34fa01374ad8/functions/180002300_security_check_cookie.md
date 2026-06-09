# __security_check_cookie

- ea: `0x180002300`
- end: `0x18000231e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010d0`
- `0x18000117c`
- `0x180001430`
- `0x1800016d4`
- `0x1800027a0`
- `0x180003698`
- `0x180003f78`
- `0x180004224`
- `0x180004748`
- `0x1800049a8`
- `0x180005d88`
- `0x1800068a8`
- `0x180006c4c`
- `0x180007084`
- `0x1800075b4`
- `0x18000860c`
- `0x180008a84`
- `0x18000a4c4`
- `0x18000a5d0`
- `0x18000afdc`
- `0x18000ca14`
- `0x18000cc18`
- `0x18000ce20`
- `0x18000d71c`
- `0x18000dfe0`
- `0x18000f570`
- `0x18000f698`
- `0x18000fa50`
- `0x18000fc88`

## callees

- `0x180002300`
- `0x180002c50`

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
0x180002300  cmp     rcx, cs:__security_cookie
0x180002307  jnz     short ReportFailure
0x180002309  rol     rcx, 10h
0x18000230d  test    cx, 0FFFFh
0x180002312  jnz     short RestoreRcx
0x180002314  retn
0x180002315  ror     rcx, 10h; StackCookie
0x180002319  jmp     __report_gsfailure
```
