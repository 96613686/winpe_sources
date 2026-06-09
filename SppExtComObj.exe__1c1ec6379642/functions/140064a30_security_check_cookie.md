# __security_check_cookie

- ea: `0x140064a30`
- end: `0x140064a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cf78`
- `0x14000db70`
- `0x14000deb0`
- `0x14000e024`
- `0x14000eb74`
- `0x140012344`
- `0x140012510`
- `0x140012688`
- `0x140013280`
- `0x140013560`
- `0x14001383c`
- `0x140013b14`
- `0x140013de4`
- `0x1400140bc`
- `0x140014394`
- `0x14001467c`
- `0x140014958`
- `0x140014c34`
- `0x140014f0c`
- `0x140014fa8`
- `0x1400156b0`
- `0x140015bc0`
- `0x140017878`
- `0x140019810`
- `0x14001d148`
- `0x14001e28c`
- `0x14006490c`

## callees

- `0x14000aac0`
- `0x140064a30`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_14000AAC0(StackCookie);
}

```

## disassembly

```asm
0x140064a30  cmp     rcx, cs:__security_cookie
0x140064a37  jnz     short loc_140064A49
0x140064a39  rol     rcx, 10h
0x140064a3d  test    cx, 0FFFFh
0x140064a42  jnz     short loc_140064A45
0x140064a44  retn
0x140064a45  ror     rcx, 10h
0x140064a49  jmp     sub_14000AAC0
```
