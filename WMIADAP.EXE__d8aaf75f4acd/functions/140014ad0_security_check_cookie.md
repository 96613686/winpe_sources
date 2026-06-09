# __security_check_cookie

- ea: `0x140014ad0`
- end: `0x140014aee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001110`
- `0x1400037f0`
- `0x140004e24`
- `0x140005140`
- `0x1400055fc`
- `0x140005ad0`
- `0x140006d24`
- `0x140007c10`
- `0x14000887c`
- `0x14000ad50`
- `0x14000d7c4`
- `0x14000d94c`
- `0x14000f91c`
- `0x140012500`
- `0x140012c70`
- `0x140012f60`
- `0x140013510`
- `0x140013b40`
- `0x1400149d8`

## callees

- `0x1400015d0`
- `0x140014ad0`

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
0x140014ad0  cmp     rcx, cs:__security_cookie
0x140014ad7  jnz     short loc_140014AE9
0x140014ad9  rol     rcx, 10h
0x140014add  test    cx, 0FFFFh
0x140014ae2  jnz     short loc_140014AE5
0x140014ae4  retn
0x140014ae5  ror     rcx, 10h
0x140014ae9  jmp     __report_gsfailure
```
