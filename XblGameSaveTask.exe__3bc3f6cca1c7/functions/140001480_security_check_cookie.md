# __security_check_cookie

- ea: `0x140001480`
- end: `0x14000149e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002524`
- `0x1400027b8`
- `0x140002d58`
- `0x1400030fc`
- `0x140003644`
- `0x1400039c0`
- `0x14000516c`
- `0x140005640`
- `0x1400061e8`
- `0x1400063e0`

## callees

- `0x140001480`
- `0x140001a70`

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
0x140001480  cmp     rcx, cs:__security_cookie
0x140001487  jnz     short loc_140001499
0x140001489  rol     rcx, 10h
0x14000148d  test    cx, 0FFFFh
0x140001492  jnz     short loc_140001495
0x140001494  retn
0x140001495  ror     rcx, 10h; StackCookie
0x140001499  jmp     __report_gsfailure
```
