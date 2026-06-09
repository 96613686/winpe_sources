# __security_check_cookie

- ea: `0x1800038f0`
- end: `0x18000390e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `67`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800017d0`
- `0x180001878`
- `0x180001990`
- `0x180001ab8`
- `0x180002000`
- `0x1800021f0`
- `0x180002610`
- `0x180002b20`
- `0x180002d90`
- `0x180002f00`
- `0x180003180`
- `0x1800033a0`
- `0x180004080`
- `0x180004d90`
- `0x18000503c`
- `0x180005828`
- `0x180005f60`
- `0x180006790`
- `0x180007144`
- `0x1800074c0`
- `0x18000813c`
- `0x18000863c`
- `0x18000878c`
- `0x18000891c`
- `0x180008afc`
- `0x18000a060`
- `0x18000a27c`
- `0x18000a514`
- `0x18000aa20`
- `0x18000ad1c`
- `0x18000afd0`
- `0x18000d8e8`
- `0x18000d9b4`
- `0x18000e0a4`
- `0x18000e840`
- `0x18000eae0`
- `0x18000ec98`
- `0x180010954`
- `0x180010cd4`
- `0x180011010`
- `0x1800116e0`
- `0x1800117d8`
- `0x180011858`
- `0x180011918`
- `0x1800125a4`
- `0x1800126f4`
- `0x1800130d0`

## callees

- `0x1800038f0`
- `0x180003920`

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
0x1800038f0  cmp     rcx, cs:__security_cookie
0x1800038f7  jnz     short ReportFailure
0x1800038f9  rol     rcx, 10h
0x1800038fd  test    cx, 0FFFFh
0x180003902  jnz     short RestoreRcx
0x180003904  retn
0x180003905  ror     rcx, 10h; StackCookie
0x180003909  jmp     __report_gsfailure
```
