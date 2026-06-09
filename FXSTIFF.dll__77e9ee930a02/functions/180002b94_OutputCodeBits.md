# OutputCodeBits

- ea: `0x180002b94`
- end: `0x180002da4`
- name: `OutputCodeBits`
- size: `528`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001dc8`
- `0x18000214c`
- `0x180002600`

## callees

- `0x180002b94`

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
0x180002b94  mov     [rsp+arg_0], rbx
0x180002b99  mov     [rsp+arg_8], rdi
0x180002b9e  mov     rbx, r8
0x180002ba1  mov     r10d, edx
0x180002ba4  mov     r9, rcx
0x180002ba7  mov     edi, 1
0x180002bac  test    edx, edx
0x180002bae  jle     loc_180002D96
0x180002bb4  add     [rcx+628h], edx
0x180002bba  shr     edx, 3
0x180002bbd  cmp     dword ptr [rcx+624h], 0
0x180002bc4  jz      loc_180002CC8
0x180002bca  xor     r11d, r11d
0x180002bcd  test    edx, edx
0x180002bcf  jz      short loc_180002C4F
0x180002bd1  mov     ecx, [r9+630h]
0x180002bd8  mov     r8d, 0FFh
0x180002bde  add     ecx, 0FFFFFFF8h
0x180002be1  shl     r8d, cl
0x180002be4  or      r8d, [r9+62Ch]
0x180002beb  mov     [r9+62Ch], r8d
0x180002bf2  mov     [r9+630h], ecx
0x180002bf9  cmp     ecx, 10h
0x180002bfc  ja      short loc_180002C47
0x180002bfe  mov     rcx, [r9+638h]
0x180002c05  lea     rax, [rcx+1]
0x180002c09  cmp     rax, rbx
0x180002c0c  ja      loc_180002D5B
0x180002c12  shr     r8d, 18h
0x180002c16  mov     [rcx], r8b
0x180002c19  add     [r9+638h], rdi
0x180002c20  mov     rcx, [r9+638h]
0x180002c27  mov     al, [r9+62Eh]
0x180002c2e  mov     [rcx], al
0x180002c30  add     [r9+638h], rdi
0x180002c37  shl     dword ptr [r9+62Ch], 10h
0x180002c3f  add     dword ptr [r9+630h], 10h
0x180002c47  add     r11d, edi
0x180002c4a  cmp     r11d, edx
0x180002c4d  jl      short loc_180002BD1
0x180002c4f  and     r10d, 7
0x180002c53  jz      loc_180002D96
0x180002c59  mov     edx, [r9+630h]
0x180002c60  mov     eax, edi
0x180002c62  sub     edx, r10d
0x180002c65  mov     ecx, r10d
0x180002c68  shl     ax, cl
0x180002c6b  mov     ecx, edx
0x180002c6d  sub     ax, di
0x180002c70  mov     [r9+630h], edx
0x180002c77  movzx   eax, ax
0x180002c7a  shl     eax, cl
0x180002c7c  or      [r9+62Ch], eax
0x180002c83  mov     ecx, [r9+62Ch]
0x180002c8a  cmp     edx, 10h
0x180002c8d  ja      loc_180002D96
0x180002c93  mov     rdx, [r9+638h]
0x180002c9a  lea     rax, [rdx+1]
0x180002c9e  cmp     rax, rbx
0x180002ca1  ja      loc_180002D5B
0x180002ca7  shr     ecx, 18h
0x180002caa  mov     [rdx], cl
0x180002cac  add     [r9+638h], rdi
0x180002cb3  mov     rcx, [r9+638h]
0x180002cba  mov     al, [r9+62Eh]
0x180002cc1  mov     [rcx], al
0x180002cc3  jmp     loc_180002D7F
0x180002cc8  xor     r8d, r8d
0x180002ccb  test    edx, edx
0x180002ccd  jz      short loc_180002D34
0x180002ccf  mov     eax, [r9+630h]
0x180002cd6  add     eax, 0FFFFFFF8h
0x180002cd9  mov     [r9+630h], eax
0x180002ce0  cmp     eax, 10h
0x180002ce3  ja      short loc_180002D2C
0x180002ce5  mov     rcx, [r9+638h]
0x180002cec  lea     rax, [rcx+1]
0x180002cf0  cmp     rax, rbx
0x180002cf3  ja      short loc_180002D5B
0x180002cf5  mov     al, [r9+62Fh]
0x180002cfc  mov     [rcx], al
0x180002cfe  add     [r9+638h], rdi
0x180002d05  mov     rcx, [r9+638h]
0x180002d0c  mov     al, [r9+62Eh]
0x180002d13  mov     [rcx], al
0x180002d15  add     [r9+638h], rdi
0x180002d1c  shl     dword ptr [r9+62Ch], 10h
0x180002d24  add     dword ptr [r9+630h], 10h
0x180002d2c  add     r8d, edi
0x180002d2f  cmp     r8d, edx
0x180002d32  jl      short loc_180002CCF
0x180002d34  and     r10d, 7
0x180002d38  jz      short loc_180002D96
0x180002d3a  sub     [r9+630h], r10d
0x180002d41  cmp     dword ptr [r9+630h], 10h
0x180002d49  ja      short loc_180002D96
0x180002d4b  mov     rdx, [r9+638h]
0x180002d52  lea     rax, [rdx+1]
0x180002d56  cmp     rax, rbx
0x180002d59  jbe     short loc_180002D5F
0x180002d5b  xor     eax, eax
0x180002d5d  jmp     short loc_180002D98
0x180002d5f  mov     cl, [r9+62Fh]
0x180002d66  mov     [rdx], cl
0x180002d68  add     [r9+638h], rdi
0x180002d6f  mov     rdx, [r9+638h]
0x180002d76  mov     cl, [r9+62Eh]
0x180002d7d  mov     [rdx], cl
0x180002d7f  add     [r9+638h], rdi
0x180002d86  shl     dword ptr [r9+62Ch], 10h
0x180002d8e  add     dword ptr [r9+630h], 10h
0x180002d96  mov     eax, edi
0x180002d98  mov     rbx, [rsp+arg_0]
0x180002d9d  mov     rdi, [rsp+arg_8]
0x180002da2  retn
```
