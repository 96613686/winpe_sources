# __security_check_cookie

- ea: `0x180001550`
- end: `0x18000156e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001de8`
- `0x180001fa0`
- `0x180002070`
- `0x180002260`
- `0x180002440`
- `0x180002928`
- `0x180002a90`
- `0x180002ba0`
- `0x180002cb0`
- `0x180002ea8`

## callees

- `0x180001550`
- `0x180001a80`

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
0x180001550  cmp     rcx, cs:__security_cookie
0x180001557  jnz     short ReportFailure
0x180001559  rol     rcx, 10h
0x18000155d  test    cx, 0FFFFh
0x180001562  jnz     short RestoreRcx
0x180001564  retn
0x180001565  ror     rcx, 10h; StackCookie
0x180001569  jmp     __report_gsfailure
```
