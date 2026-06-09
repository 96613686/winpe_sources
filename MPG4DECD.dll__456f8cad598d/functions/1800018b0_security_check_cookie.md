# __security_check_cookie

- ea: `0x1800018b0`
- end: `0x1800018ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023a0`
- `0x1800026f0`
- `0x18000330c`
- `0x180003480`
- `0x180004810`
- `0x180005630`
- `0x180005740`
- `0x180005990`
- `0x180005aa0`
- `0x18000676c`
- `0x1800078c0`
- `0x180008410`
- `0x180008808`
- `0x180008f20`
- `0x180013540`
- `0x18001d6f0`
- `0x18001d7d0`
- `0x18001d8b0`
- `0x18001d980`
- `0x18001da50`
- `0x18001db30`
- `0x18001dd20`
- `0x18001de70`
- `0x18001f230`
- `0x180020f90`

## callees

- `0x1800018b0`
- `0x180001de0`

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
0x1800018b0  cmp     rcx, cs:__security_cookie
0x1800018b7  jnz     short ReportFailure
0x1800018b9  rol     rcx, 10h
0x1800018bd  test    cx, 0FFFFh
0x1800018c2  jnz     short RestoreRcx
0x1800018c4  retn
0x1800018c5  ror     rcx, 10h; StackCookie
0x1800018c9  jmp     __report_gsfailure
```
