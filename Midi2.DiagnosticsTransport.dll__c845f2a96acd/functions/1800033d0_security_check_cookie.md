# __security_check_cookie

- ea: `0x1800033d0`
- end: `0x1800033ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x180001784`
- `0x180001c40`
- `0x180001e30`
- `0x180002100`
- `0x180002610`
- `0x180002880`
- `0x1800029f0`
- `0x180002c70`
- `0x180002e90`
- `0x180003b24`
- `0x180004714`
- `0x1800049a8`
- `0x180005198`
- `0x1800058d0`
- `0x180006100`
- `0x180006ab4`
- `0x180006e30`
- `0x180007aac`
- `0x180007f6c`
- `0x1800080bc`
- `0x18000824c`
- `0x18000842c`
- `0x180009840`
- `0x180009a5c`
- `0x180009cf4`
- `0x18000a200`
- `0x18000a4fc`
- `0x18000a7b0`
- `0x18000cb4c`
- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f1e4`
- `0x18000f9e0`
- `0x180010b70`
- `0x180011630`
- `0x1800117e8`
- `0x1800119a0`

## callees

- `0x1800033d0`
- `0x180003400`

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
