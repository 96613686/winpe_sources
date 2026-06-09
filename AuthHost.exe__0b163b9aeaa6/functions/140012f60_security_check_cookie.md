# __security_check_cookie

- ea: `0x140012f60`
- end: `0x140012f7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x14000116c`
- `0x1400028e8`
- `0x140002a10`
- `0x140003b70`
- `0x1400042fc`
- `0x1400051f0`
- `0x140005dbc`
- `0x1400067a0`
- `0x140007080`
- `0x140007750`
- `0x1400079e0`
- `0x140008b30`
- `0x14000a4b0`
- `0x14000a858`
- `0x14000ad80`
- `0x14000b0d0`
- `0x14000b6f0`
- `0x14000b840`
- `0x14000c370`
- `0x14000c3dc`
- `0x14000c45c`
- `0x14000c4f8`
- `0x14000c598`
- `0x14000c668`
- `0x14000db74`
- `0x14000f6b4`
- `0x14000fe40`
- `0x1400113a0`
- `0x140011438`
- `0x140011aa4`

## callees

- `0x140001900`
- `0x140012f60`

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
0x140012f60  cmp     rcx, cs:__security_cookie
0x140012f67  jnz     short loc_140012F79
0x140012f69  rol     rcx, 10h
0x140012f6d  test    cx, 0FFFFh
0x140012f72  jnz     short loc_140012F75
0x140012f74  retn
0x140012f75  ror     rcx, 10h
0x140012f79  jmp     __report_gsfailure
```
