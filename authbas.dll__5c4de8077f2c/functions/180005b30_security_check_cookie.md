# __security_check_cookie

- ea: `0x180005b30`
- end: `0x180005b4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180002990`
- `0x180003d34`
- `0x180003fc8`
- `0x1800044a0`
- `0x18000485c`
- `0x18000568c`
- `0x180005a80`

## callees

- `0x180001790`
- `0x180005b30`

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
0x180005b30  cmp     rcx, cs:__security_cookie
0x180005b37  jnz     short ReportFailure
0x180005b39  rol     rcx, 10h
0x180005b3d  test    cx, 0FFFFh
0x180005b42  jnz     short RestoreRcx
0x180005b44  retn
0x180005b45  ror     rcx, 10h
0x180005b49  jmp     __report_gsfailure
```
