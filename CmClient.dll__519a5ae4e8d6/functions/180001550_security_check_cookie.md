# __security_check_cookie

- ea: `0x180001550`
- end: `0x18000156e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800034ec`
- `0x180003780`
- `0x180003fd0`
- `0x180004650`
- `0x180004bd4`
- `0x180004f50`
- `0x180006b70`
- `0x180007490`
- `0x180007610`
- `0x1800079d0`
- `0x180007d00`
- `0x180008730`
- `0x180008a90`
- `0x180009110`
- `0x180009a94`
- `0x18000c420`
- `0x18000d010`
- `0x18000d260`
- `0x18000d9e8`
- `0x18000ecbc`

## callees

- `0x180001550`
- `0x180001b10`

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
