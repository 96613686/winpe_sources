# __security_check_cookie

- ea: `0x180002470`
- end: `0x18000248e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800017d0`
- `0x180001878`
- `0x180001998`
- `0x180001abc`
- `0x180001bfc`
- `0x1800035b4`
- `0x180003848`
- `0x180004038`
- `0x180004770`
- `0x180004fa0`
- `0x180005954`
- `0x180005cd0`
- `0x18000695c`
- `0x180006e1c`
- `0x180006f6c`
- `0x1800070fc`
- `0x1800072dc`
- `0x180008700`
- `0x18000893c`
- `0x180008bf4`
- `0x180009100`
- `0x1800095d0`
- `0x180009d5c`
- `0x18000f570`
- `0x18000fbb4`
- `0x1800121c4`
- `0x180012b04`
- `0x180013730`
- `0x180013a3c`
- `0x180013ed0`

## callees

- `0x180002470`
- `0x1800024a0`

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
0x180002470  cmp     rcx, cs:__security_cookie
0x180002477  jnz     short ReportFailure
0x180002479  rol     rcx, 10h
0x18000247d  test    cx, 0FFFFh
0x180002482  jnz     short RestoreRcx
0x180002484  retn
0x180002485  ror     rcx, 10h; StackCookie
0x180002489  jmp     __report_gsfailure
```
