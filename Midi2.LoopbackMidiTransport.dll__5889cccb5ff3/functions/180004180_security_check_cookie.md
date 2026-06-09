# __security_check_cookie

- ea: `0x180004180`
- end: `0x18000419e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `98`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800017d0`
- `0x1800018e8`
- `0x180001a38`
- `0x180001ae0`
- `0x180001c34`
- `0x180001db8`
- `0x180001f74`
- `0x180002164`
- `0x180002780`
- `0x180002970`
- `0x180002e90`
- `0x1800033a0`
- `0x180003610`
- `0x180003780`
- `0x180003a00`
- `0x180003c20`
- `0x1800049e4`
- `0x180005760`
- `0x180005a0c`
- `0x180006238`
- `0x180006970`
- `0x1800071a0`
- `0x180007b74`
- `0x180007ef0`
- `0x180008b6c`
- `0x18000902c`
- `0x18000917c`
- `0x18000930c`
- `0x1800094ec`
- `0x18000a900`
- `0x18000ab1c`
- `0x18000adb4`
- `0x18000b2c0`
- `0x18000c3fc`
- `0x18000c6b0`
- `0x18000ea80`
- `0x1800104a4`
- `0x180010848`
- `0x180011018`
- `0x180011620`
- `0x180011980`
- `0x180013294`
- `0x18001338c`
- `0x18001340c`
- `0x1800134cc`
- `0x180015efc`
- `0x1800172d4`

## callees

- `0x180004180`
- `0x1800041b0`

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
0x180004180  cmp     rcx, cs:__security_cookie
0x180004187  jnz     short ReportFailure
0x180004189  rol     rcx, 10h
0x18000418d  test    cx, 0FFFFh
0x180004192  jnz     short RestoreRcx
0x180004194  retn
0x180004195  ror     rcx, 10h; StackCookie
0x180004199  jmp     __report_gsfailure
```
