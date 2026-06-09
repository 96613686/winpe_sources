# __security_check_cookie

- ea: `0x180001c00`
- end: `0x180001c1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800011dc`
- `0x1800012bc`
- `0x1800013d8`
- `0x180001514`
- `0x18000160c`
- `0x180002fa8`
- `0x18000323c`
- `0x1800038c8`
- `0x180003cd4`
- `0x180004140`
- `0x180004490`
- `0x18000467c`
- `0x180004b54`
- `0x180004ed0`
- `0x18000698c`
- `0x180006f30`
- `0x180007160`
- `0x180007918`
- `0x180009f70`
- `0x18000a5f0`
- `0x180010208`
- `0x180010388`
- `0x180011b90`
- `0x1800127a8`
- `0x180013068`
- `0x180013528`
- `0x180013720`
- `0x180013980`

## callees

- `0x180001c00`
- `0x180002050`

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
0x180001c00  cmp     rcx, cs:__security_cookie
0x180001c07  jnz     short ReportFailure
0x180001c09  rol     rcx, 10h
0x180001c0d  test    cx, 0FFFFh
0x180001c12  jnz     short RestoreRcx
0x180001c14  retn
0x180001c15  ror     rcx, 10h; StackCookie
0x180001c19  jmp     __report_gsfailure
```
