# OutputCodeBits

- ea: `0x180002b6c`
- end: `0x180002d7b`
- name: `OutputCodeBits`
- size: `527`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001da8`
- `0x18000212c`
- `0x1800025e0`

## callees

- `0x180002b6c`

## pseudocode

```c
__int64 __fastcall OutputCodeBits(__int64 a1, int a2, unsigned __int64 a3)
{
  char v4; // r10
  signed int v6; // edx
  signed int v7; // r11d
  unsigned int v8; // ecx
  int v9; // r8d
  _BYTE *v10; // rcx
  int v11; // r10d
  unsigned int v12; // edx
  char v13; // cl
  _BYTE *v14; // rdx
  signed int v15; // r8d
  unsigned int v16; // eax
  _BYTE *v17; // rcx
  int v18; // r10d
  _BYTE *v19; // rdx

  v4 = a2;
  if ( a2 <= 0 )
    return 1;
  *(_DWORD *)(a1 + 1576) += a2;
  v6 = (unsigned int)a2 >> 3;
  if ( !*(_DWORD *)(a1 + 1572) )
  {
    v15 = 0;
    if ( v6 )
    {
      do
      {
        v16 = *(_DWORD *)(a1 + 1584) - 8;
        *(_DWORD *)(a1 + 1584) = v16;
        if ( v16 <= 0x10 )
        {
          v17 = *(_BYTE **)(a1 + 1592);
          if ( (unsigned __int64)(v17 + 1) > a3 )
            return 0;
          *v17 = *(_BYTE *)(a1 + 1583);
          *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
          ++*(_QWORD *)(a1 + 1592);
          *(_DWORD *)(a1 + 1580) <<= 16;
          *(_DWORD *)(a1 + 1584) += 16;
        }
        ++v15;
      }
      while ( v15 < v6 );
    }
    v18 = v4 & 7;
    if ( !v18 )
      return 1;
    *(_DWORD *)(a1 + 1584) -= v18;
    if ( *(_DWORD *)(a1 + 1584) > 0x10u )
      return 1;
    v19 = *(_BYTE **)(a1 + 1592);
    if ( (unsigned __int64)(v19 + 1) <= a3 )
    {
      *v19 = *(_BYTE *)(a1 + 1583);
      *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
      goto LABEL_22;
    }
    return 0;
  }
  v7 = 0;
  if ( v6 )
  {
    do
    {
      v8 = *(_DWORD *)(a1 + 1584) - 8;
      v9 = *(_DWORD *)(a1 + 1580) | (255 << (*(_BYTE *)(a1 + 1584) - 8));
      *(_DWORD *)(a1 + 1580) = v9;
      *(_DWORD *)(a1 + 1584) = v8;
      if ( v8 <= 0x10 )
      {
        v10 = *(_BYTE **)(a1 + 1592);
        if ( (unsigned __int64)(v10 + 1) > a3 )
          return 0;
        *v10 = HIBYTE(v9);
        *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
        ++*(_QWORD *)(a1 + 1592);
        *(_DWORD *)(a1 + 1580) <<= 16;
        *(_DWORD *)(a1 + 1584) += 16;
      }
      ++v7;
    }
    while ( v7 < v6 );
  }
  v11 = v4 & 7;
  if ( !v11 )
    return 1;
  v12 = *(_DWORD *)(a1 + 1584) - v11;
  v13 = *(_BYTE *)(a1 + 1584) - v11;
  *(_DWORD *)(a1 + 1584) = v12;
  *(_DWORD *)(a1 + 1580) |= (unsigned __int16)((1 << v11) - 1) << v13;
  if ( v12 > 0x10 )
    return 1;
  v14 = *(_BYTE **)(a1 + 1592);
  if ( (unsigned __int64)(v14 + 1) > a3 )
    return 0;
  *v14 = HIBYTE(*(_DWORD *)(a1 + 1580));
  *(_BYTE *)++*(_QWORD *)(a1 + 1592) = *(_BYTE *)(a1 + 1582);
LABEL_22:
  ++*(_QWORD *)(a1 + 1592);
  *(_DWORD *)(a1 + 1580) <<= 16;
  *(_DWORD *)(a1 + 1584) += 16;
  return 1;
}

```

## disassembly

```asm
0x180002b6c  mov     [rsp+arg_0], rbx
0x180002b71  mov     [rsp+arg_8], rdi
0x180002b76  mov     rbx, r8
0x180002b79  mov     r10d, edx
0x180002b7c  mov     r9, rcx
0x180002b7f  mov     edi, 1
0x180002b84  test    edx, edx
0x180002b86  jle     loc_180002D6E
0x180002b8c  add     [rcx+628h], edx
0x180002b92  shr     edx, 3
0x180002b95  cmp     dword ptr [rcx+624h], 0
0x180002b9c  jz      loc_180002CA0
0x180002ba2  xor     r11d, r11d
0x180002ba5  test    edx, edx
0x180002ba7  jz      short loc_180002C27
0x180002ba9  mov     ecx, [r9+630h]
0x180002bb0  mov     r8d, 0FFh
0x180002bb6  add     ecx, 0FFFFFFF8h
0x180002bb9  shl     r8d, cl
0x180002bbc  or      r8d, [r9+62Ch]
0x180002bc3  mov     [r9+62Ch], r8d
0x180002bca  mov     [r9+630h], ecx
0x180002bd1  cmp     ecx, 10h
0x180002bd4  ja      short loc_180002C1F
0x180002bd6  mov     rcx, [r9+638h]
0x180002bdd  lea     rax, [rcx+1]
0x180002be1  cmp     rax, rbx
0x180002be4  ja      loc_180002D33
0x180002bea  shr     r8d, 18h
0x180002bee  mov     [rcx], r8b
0x180002bf1  add     [r9+638h], rdi
0x180002bf8  mov     rcx, [r9+638h]
0x180002bff  mov     al, [r9+62Eh]
0x180002c06  mov     [rcx], al
0x180002c08  add     [r9+638h], rdi
0x180002c0f  shl     dword ptr [r9+62Ch], 10h
0x180002c17  add     dword ptr [r9+630h], 10h
0x180002c1f  add     r11d, edi
0x180002c22  cmp     r11d, edx
0x180002c25  jl      short loc_180002BA9
0x180002c27  and     r10d, 7
0x180002c2b  jz      loc_180002D6E
0x180002c31  mov     edx, [r9+630h]
0x180002c38  mov     eax, edi
0x180002c3a  sub     edx, r10d
0x180002c3d  mov     ecx, r10d
0x180002c40  shl     ax, cl
0x180002c43  mov     ecx, edx
0x180002c45  sub     ax, di
0x180002c48  mov     [r9+630h], edx
0x180002c4f  movzx   eax, ax
0x180002c52  shl     eax, cl
0x180002c54  or      [r9+62Ch], eax
0x180002c5b  mov     ecx, [r9+62Ch]
0x180002c62  cmp     edx, 10h
0x180002c65  ja      loc_180002D6E
0x180002c6b  mov     rdx, [r9+638h]
0x180002c72  lea     rax, [rdx+1]
0x180002c76  cmp     rax, rbx
0x180002c79  ja      loc_180002D33
0x180002c7f  shr     ecx, 18h
0x180002c82  mov     [rdx], cl
0x180002c84  add     [r9+638h], rdi
0x180002c8b  mov     rcx, [r9+638h]
0x180002c92  mov     al, [r9+62Eh]
0x180002c99  mov     [rcx], al
0x180002c9b  jmp     loc_180002D57
0x180002ca0  xor     r8d, r8d
0x180002ca3  test    edx, edx
0x180002ca5  jz      short loc_180002D0C
0x180002ca7  mov     eax, [r9+630h]
0x180002cae  add     eax, 0FFFFFFF8h
0x180002cb1  mov     [r9+630h], eax
0x180002cb8  cmp     eax, 10h
0x180002cbb  ja      short loc_180002D04
0x180002cbd  mov     rcx, [r9+638h]
0x180002cc4  lea     rax, [rcx+1]
0x180002cc8  cmp     rax, rbx
0x180002ccb  ja      short loc_180002D33
0x180002ccd  mov     al, [r9+62Fh]
0x180002cd4  mov     [rcx], al
0x180002cd6  add     [r9+638h], rdi
0x180002cdd  mov     rcx, [r9+638h]
0x180002ce4  mov     al, [r9+62Eh]
0x180002ceb  mov     [rcx], al
0x180002ced  add     [r9+638h], rdi
0x180002cf4  shl     dword ptr [r9+62Ch], 10h
0x180002cfc  add     dword ptr [r9+630h], 10h
0x180002d04  add     r8d, edi
0x180002d07  cmp     r8d, edx
0x180002d0a  jl      short loc_180002CA7
0x180002d0c  and     r10d, 7
0x180002d10  jz      short loc_180002D6E
0x180002d12  sub     [r9+630h], r10d
0x180002d19  cmp     dword ptr [r9+630h], 10h
0x180002d21  ja      short loc_180002D6E
0x180002d23  mov     rdx, [r9+638h]
0x180002d2a  lea     rax, [rdx+1]
0x180002d2e  cmp     rax, rbx
0x180002d31  jbe     short loc_180002D37
0x180002d33  xor     eax, eax
0x180002d35  jmp     short loc_180002D70
0x180002d37  mov     cl, [r9+62Fh]
0x180002d3e  mov     [rdx], cl
0x180002d40  add     [r9+638h], rdi
0x180002d47  mov     rdx, [r9+638h]
0x180002d4e  mov     cl, [r9+62Eh]
0x180002d55  mov     [rdx], cl
0x180002d57  add     [r9+638h], rdi
0x180002d5e  shl     dword ptr [r9+62Ch], 10h
0x180002d66  add     dword ptr [r9+630h], 10h
0x180002d6e  mov     eax, edi
0x180002d70  mov     rbx, [rsp+arg_0]
0x180002d75  mov     rdi, [rsp+arg_8]
0x180002d7a  retn
```
