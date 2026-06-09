# __security_check_cookie

- ea: `0x140001330`
- end: `0x14000134e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000238c`
- `0x140002430`
- `0x140002714`

## callees

- `0x140001330`
- `0x140001910`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140001330  cmp     rcx, cs:__security_cookie
0x140001337  jnz     short loc_140001349
0x140001339  rol     rcx, 10h
0x14000133d  test    cx, 0FFFFh
0x140001342  jnz     short loc_140001345
0x140001344  retn
0x140001345  ror     rcx, 10h; StackCookie
0x140001349  jmp     __report_gsfailure
```
