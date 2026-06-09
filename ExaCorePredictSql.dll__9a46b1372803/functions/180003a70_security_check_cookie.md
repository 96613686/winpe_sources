# __security_check_cookie

- ea: `0x180003a70`
- end: `0x180003a91`
- name: `__security_check_cookie`
- size: `33`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002030`
- `0x180002a00`
- `0x180003310`
- `0x1800049e4`

## callees

- `0x180003a70`
- `0x180004350`

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
0x180003a70  cmp     rcx, cs:__security_cookie
0x180003a77  bnd jnz short ReportFailure
0x180003a7a  rol     rcx, 10h
0x180003a7e  test    cx, 0FFFFh
0x180003a83  bnd jnz short RestoreRcx
0x180003a86  bnd retn
0x180003a88  ror     rcx, 10h
0x180003a8c  jmp     __report_gsfailure
```
