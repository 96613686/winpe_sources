# sub_40CAD8

- ea: `0x40cad8`
- end: `0x40cb50`
- name: `sub_40CAD8`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40cad8`

## pseudocode

```c
int __cdecl sub_40CAD8(int a1, _DWORD *a2, unsigned int a3)
{
  _DWORD *v3; // edx
  unsigned int v4; // ebx
  int v5; // ecx
  unsigned __int8 v6; // al
  bool v7; // cc
  int v8; // eax

  v3 = a2;
  v4 = a3;
  if ( !a3 )
    return 0;
  v5 = a1 - (_DWORD)a2;
  if ( ((unsigned __int8)a2 & 3) != 0 )
    goto LABEL_3;
LABEL_7:
  while ( (((_WORD)v5 + (_WORD)v3) & 0xFFFu) <= 0xFFC )
  {
    v8 = *(_DWORD *)((char *)v3 + v5);
    if ( v8 != *v3 )
      break;
    v7 = v4 <= 4;
    v4 -= 4;
    if ( !v7 )
    {
      ++v3;
      if ( ((v8 - 16843009) & ~v8 & 0x80808080) == 0 )
        continue;
    }
    return 0;
  }
LABEL_3:
  while ( 1 )
  {
    v6 = *((_BYTE *)v3 + v5);
    if ( v6 != *(_BYTE *)v3 )
      return v6 < *(_BYTE *)v3 ? -1 : 1;
    if ( !*((_BYTE *)v3 + v5) )
      return 0;
    v3 = (_DWORD *)((char *)v3 + 1);
    v7 = v4-- <= 1;
    if ( v7 )
      return 0;
    if ( ((unsigned __int8)v3 & 3) == 0 )
      goto LABEL_7;
  }
}

```

## disassembly

```asm
0x40cad8  push    ebx
0x40cad9  push    esi
0x40cada  mov     ecx, [esp+8+arg_0]
0x40cade  mov     edx, [esp+8+arg_4]
0x40cae2  mov     ebx, [esp+8+arg_8]
0x40cae6  test    ebx, 0FFFFFFFFh
0x40caec  jz      short loc_40CB3E
0x40caee  sub     ecx, edx
0x40caf0  test    edx, 3
0x40caf6  jz      short loc_40CB0F
0x40caf8  movzx   eax, byte ptr [ecx+edx]
0x40cafc  cmp     al, [edx]
0x40cafe  jnz     short loc_40CB48
0x40cb00  test    eax, eax
0x40cb02  jz      short loc_40CB3E
0x40cb04  inc     edx
0x40cb05  sub     ebx, 1
0x40cb08  jbe     short loc_40CB3E
0x40cb0a  test    dl, 3
0x40cb0d  jnz     short loc_40CAF8
0x40cb0f  lea     eax, [ecx+edx]
0x40cb12  and     eax, 0FFFh
0x40cb17  cmp     eax, 0FFCh
0x40cb1c  ja      short loc_40CAF8
0x40cb1e  mov     eax, [ecx+edx]
0x40cb21  cmp     eax, [edx]
0x40cb23  jnz     short loc_40CAF8
0x40cb25  sub     ebx, 4
0x40cb28  jbe     short loc_40CB3E
0x40cb2a  lea     esi, [eax-1010101h]
0x40cb30  add     edx, 4
0x40cb33  not     eax
0x40cb35  and     eax, esi
0x40cb37  test    eax, 80808080h
0x40cb3c  jz      short loc_40CB0F
0x40cb3e  xor     eax, eax
0x40cb40  pop     esi
0x40cb41  pop     ebx
0x40cb42  retn
0x40cb43  jmp     short loc_40CB48
0x40cb48  sbb     eax, eax
0x40cb4a  or      eax, 1
0x40cb4d  pop     esi
0x40cb4e  pop     ebx
0x40cb4f  retn
```
