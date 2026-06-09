# ___std_type_info_compare

- ea: `0x408f17`
- end: `0x408f53`
- name: `___std_type_info_compare`
- size: `60`
- prototype: `int __cdecl(int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x40aac1`

## callees

- `0x408f17`

## pseudocode

```c
int __cdecl __std_type_info_compare(int a1, int a2)
{
  _BYTE *v3; // ecx
  _BYTE *i; // eax
  bool v5; // cf
  unsigned __int8 v6; // dl

  if ( a1 == a2 )
    return 0;
  v3 = (_BYTE *)(a2 + 5);
  for ( i = (_BYTE *)(a1 + 5); ; i += 2 )
  {
    v5 = *i < *v3;
    if ( *i != *v3 )
      break;
    if ( !*i )
      return 0;
    v6 = i[1];
    v5 = v6 < v3[1];
    if ( v6 != v3[1] )
      break;
    v3 += 2;
    if ( !v6 )
      return 0;
  }
  return v5 ? -1 : 1;
}

```

## disassembly

```asm
0x408f17  push    ebp
0x408f18  mov     ebp, esp
0x408f1a  mov     eax, [ebp+arg_0]
0x408f1d  mov     ecx, [ebp+arg_4]
0x408f20  cmp     eax, ecx
0x408f22  jnz     short loc_408F28
0x408f24  xor     eax, eax
0x408f26  pop     ebp
0x408f27  retn
0x408f28  add     ecx, 5
0x408f2b  add     eax, 5
0x408f2e  mov     dl, [eax]
0x408f30  cmp     dl, [ecx]
0x408f32  jnz     short loc_408F4C
0x408f34  test    dl, dl
0x408f36  jz      short loc_408F24
0x408f38  mov     dl, [eax+1]
0x408f3b  cmp     dl, [ecx+1]
0x408f3e  jnz     short loc_408F4C
0x408f40  add     eax, 2
0x408f43  add     ecx, 2
0x408f46  test    dl, dl
0x408f48  jnz     short loc_408F2E
0x408f4a  jmp     short loc_408F24
0x408f4c  sbb     eax, eax
0x408f4e  or      eax, 1
0x408f51  pop     ebp
0x408f52  retn
```
