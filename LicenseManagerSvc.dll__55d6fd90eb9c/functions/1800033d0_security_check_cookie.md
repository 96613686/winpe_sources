# __security_check_cookie

- ea: `0x1800033d0`
- end: `0x1800033ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ea0`
- `0x18000279c`
- `0x180002908`
- `0x18000443c`
- `0x18000498c`
- `0x180004c38`
- `0x18000542c`
- `0x180005794`
- `0x180005aac`
- `0x180007740`
- `0x180008344`
- `0x180009aa0`
- `0x18000a198`
- `0x18000b564`
- `0x18000b740`
- `0x18000bdf0`
- `0x18000c688`
- `0x18000cc78`
- `0x180017310`

## callees

- `0x1800033d0`
- `0x180003c60`

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
0x1800033d0  cmp     rcx, cs:__security_cookie
0x1800033d7  jnz     short ReportFailure
0x1800033d9  rol     rcx, 10h
0x1800033dd  test    cx, 0FFFFh
0x1800033e2  jnz     short RestoreRcx
0x1800033e4  retn
0x1800033e5  ror     rcx, 10h; StackCookie
0x1800033e9  jmp     __report_gsfailure
```
