# __security_check_cookie

- ea: `0x18000e3a0`
- end: `0x18000e3be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001880`
- `0x18000a900`
- `0x18000aa00`
- `0x18000aaf0`
- `0x18000b4ec`
- `0x18000cab8`
- `0x18000d164`
- `0x18000d2dc`
- `0x18000f0d0`
- `0x18000f640`
- `0x18000fc50`
- `0x18000fcc8`
- `0x18000ffb4`
- `0x18001143c`

## callees

- `0x18000e3a0`
- `0x18000e730`

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
0x18000e3a0  cmp     rcx, cs:__security_cookie
0x18000e3a7  jnz     short loc_18000E3B9
0x18000e3a9  rol     rcx, 10h
0x18000e3ad  test    cx, 0FFFFh
0x18000e3b2  jnz     short loc_18000E3B5
0x18000e3b4  retn
0x18000e3b5  ror     rcx, 10h; StackCookie
0x18000e3b9  jmp     __report_gsfailure
```
