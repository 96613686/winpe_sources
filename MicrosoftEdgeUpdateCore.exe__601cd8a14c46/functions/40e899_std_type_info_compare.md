# ___std_type_info_compare

- ea: `0x40e899`
- end: `0x40e8d5`
- name: `___std_type_info_compare`
- size: `60`
- prototype: `int __cdecl(int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x40fba1`

## callees

- `0x40e899`

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
0x40e899  push    ebp
0x40e89a  mov     ebp, esp
0x40e89c  mov     eax, [ebp+arg_0]
0x40e89f  mov     ecx, [ebp+arg_4]
0x40e8a2  cmp     eax, ecx
0x40e8a4  jnz     short loc_40E8AA
0x40e8a6  xor     eax, eax
0x40e8a8  pop     ebp
0x40e8a9  retn
0x40e8aa  add     ecx, 5
0x40e8ad  add     eax, 5
0x40e8b0  mov     dl, [eax]
0x40e8b2  cmp     dl, [ecx]
0x40e8b4  jnz     short loc_40E8CE
0x40e8b6  test    dl, dl
0x40e8b8  jz      short loc_40E8A6
0x40e8ba  mov     dl, [eax+1]
0x40e8bd  cmp     dl, [ecx+1]
0x40e8c0  jnz     short loc_40E8CE
0x40e8c2  add     eax, 2
0x40e8c5  add     ecx, 2
0x40e8c8  test    dl, dl
0x40e8ca  jnz     short loc_40E8B0
0x40e8cc  jmp     short loc_40E8A6
0x40e8ce  sbb     eax, eax
0x40e8d0  or      eax, 1
0x40e8d3  pop     ebp
0x40e8d4  retn
```
