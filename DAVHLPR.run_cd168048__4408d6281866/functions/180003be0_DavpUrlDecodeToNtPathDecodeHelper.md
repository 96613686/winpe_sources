# DavpUrlDecodeToNtPathDecodeHelper

- ea: `0x180003be0`
- end: `0x180003dfb`
- name: `DavpUrlDecodeToNtPathDecodeHelper`
- size: `539`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, __int64, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180001010`
- `0x180001e80`
- `0x1800027c0`

## callees

- `0x180003be0`

## pseudocode

```c
__int64 __fastcall DavpUrlDecodeToNtPathDecodeHelper(
        unsigned __int16 **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5)
{
  __int64 v5; // rax
  unsigned int v7; // r11d
  unsigned int *v8; // rdx
  unsigned __int16 v9; // ax
  __int64 result; // rax
  __int16 v11; // cx
  char v12; // r9
  __int16 v13; // cx
  char v14; // al
  char v15; // cl
  unsigned __int8 v16; // r9
  unsigned int v17; // r9d
  char v18; // cl
  __int64 v19; // r11
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // cx
  int v22; // ecx
  unsigned __int16 v23; // r11

  v5 = (__int64)*a1;
  v7 = **a1;
  if ( v7 != 37 )
  {
    if ( !*(_BYTE *)(a3 + 5) )
    {
      v8 = a5;
      if ( *(_BYTE *)a4 )
      {
        *(_BYTE *)a4 = 0;
        v23 = v7 + 9216;
        if ( v23 <= 0x3FFu )
        {
          *a5 = v23 + (*(unsigned __int16 *)(a4 + 2) << 10) + 0x10000;
          result = 0;
          goto LABEL_6;
        }
      }
      else
      {
        v9 = v7 + 10240;
        if ( (unsigned __int16)(v7 + 10240) >= 0x800u )
        {
          *a5 = v7;
          result = 0;
LABEL_6:
          ++*a1;
          goto LABEL_7;
        }
        if ( v9 <= 0x3FFu )
        {
          *(_WORD *)(a4 + 2) = v9;
          result = 997;
          *(_BYTE *)a4 = 1;
          goto LABEL_6;
        }
      }
      result = 582;
      goto LABEL_6;
    }
    return 582;
  }
  if ( *(_BYTE *)a4 || (__int64)((a2 - v5) & 0xFFFFFFFFFFFFFFFEuLL) < 6 )
    return 582;
  v11 = *(_WORD *)(v5 + 2);
  v12 = v11 - 48;
  if ( (unsigned __int16)(v11 - 48) >= 0xAu )
  {
    v20 = (v11 | 0x20) - 97;
    if ( v20 >= 6u )
      return 582;
    v12 = v20 + 10;
  }
  v13 = *(_WORD *)(v5 + 4);
  v14 = v13 - 48;
  if ( (unsigned __int16)(v13 - 48) >= 0xAu )
  {
    v21 = (v13 | 0x20) - 97;
    if ( v21 >= 6u )
      return 582;
    v14 = v21 + 10;
  }
  v15 = *(_BYTE *)(a3 + 5);
  v8 = a5;
  v16 = v14 | (16 * v12);
  if ( v15 )
  {
    if ( (v16 & 0xC0) == 0x80 )
    {
      v17 = (*(_DWORD *)a3 << 6) | v16 & 0x3F;
      v18 = v15 - 1;
      *(_DWORD *)a3 = v17;
      *(_BYTE *)(a3 + 5) = v18;
      if ( v18 )
      {
        result = 997;
LABEL_20:
        *a1 += 3;
        goto LABEL_7;
      }
      if ( v17 >= dword_1800076F0[*(unsigned __int8 *)(a3 + 4)] && (v17 <= 0xD7FF || v17 - 57344 <= 0x101FFF) )
      {
        *a5 = v17;
        result = 0;
        goto LABEL_20;
      }
    }
    goto LABEL_23;
  }
  if ( v16 < 0x80u )
  {
    *a5 = (char)v16;
    result = 0;
    goto LABEL_20;
  }
  v19 = *((unsigned __int8 *)qword_1800074E8 + ((unsigned __int64)v16 >> 3));
  if ( !(_BYTE)v19 )
  {
LABEL_23:
    *a1 += 3;
    result = 582;
    goto LABEL_7;
  }
  *(_BYTE *)(a3 + 4) = v19;
  v22 = (unsigned __int8)byte_1800076E1[2 * v19];
  *(_BYTE *)(a3 + 5) = v19 - 1;
  *(_DWORD *)a3 = v16 & ~v22;
  result = 997;
  *a1 += 3;
LABEL_7:
  if ( !(_DWORD)result && *v8 == 47 )
    *v8 = 92;
  return result;
}

```

## disassembly

```asm
0x180003be0  mov     rax, [rcx]
0x180003be3  mov     r10, rcx
0x180003be6  movzx   r11d, word ptr [rax]
0x180003bea  cmp     r11d, 25h ; '%'
0x180003bee  jz      short loc_180003C35
0x180003bf0  cmp     byte ptr [r8+5], 0
0x180003bf5  jnz     short loc_180003C3B
0x180003bf7  cmp     byte ptr [r9], 0
0x180003bfb  mov     rdx, [rsp+arg_20]
0x180003c00  jnz     loc_180003DC6
0x180003c06  mov     eax, 2800h
0x180003c0b  mov     ecx, 800h
0x180003c10  add     eax, r11d
0x180003c13  cmp     ax, cx
0x180003c16  jb      loc_180003D92
0x180003c1c  mov     [rdx], r11d
0x180003c1f  xor     eax, eax
0x180003c21  add     qword ptr [r10], 2
0x180003c25  test    eax, eax
0x180003c27  jnz     short locret_180003C34
0x180003c29  cmp     dword ptr [rdx], 2Fh ; '/'
0x180003c2c  jnz     short locret_180003C34
0x180003c2e  mov     dword ptr [rdx], 5Ch ; '\'
0x180003c34  retn
0x180003c35  cmp     byte ptr [r9], 0
0x180003c39  jz      short loc_180003C41
0x180003c3b  mov     eax, 246h
0x180003c40  retn
0x180003c41  sub     rdx, rax
0x180003c44  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180003c48  cmp     rdx, 6
0x180003c4c  jl      short loc_180003C3B
0x180003c4e  movzx   ecx, word ptr [rax+2]
0x180003c52  lea     r9d, [rcx-30h]
0x180003c56  cmp     r9w, 0Ah
0x180003c5b  jnb     loc_180003CF1
0x180003c61  movzx   ecx, word ptr [rax+4]
0x180003c65  lea     eax, [rcx-30h]
0x180003c68  cmp     ax, 0Ah
0x180003c6c  jnb     loc_180003D0C
0x180003c72  movzx   ecx, byte ptr [r8+5]
0x180003c77  mov     rdx, [rsp+arg_20]
0x180003c7c  shl     r9b, 4
0x180003c80  or      r9b, al
0x180003c83  test    cl, cl
0x180003c85  jz      short loc_180003CBC
0x180003c87  movzx   eax, r9b
0x180003c8b  and     al, 0C0h
0x180003c8d  cmp     al, 80h
0x180003c8f  jnz     short loc_180003CE3
0x180003c91  mov     eax, [r8]
0x180003c94  and     r9d, 3Fh
0x180003c98  shl     eax, 6
0x180003c9b  or      r9d, eax
0x180003c9e  sub     cl, 1
0x180003ca1  mov     [r8], r9d
0x180003ca4  mov     [r8+5], cl
0x180003ca8  jz      loc_180003D53
0x180003cae  mov     eax, 3E5h
0x180003cb3  add     qword ptr [r10], 6
0x180003cb7  jmp     loc_180003C25
0x180003cbc  cmp     r9b, 80h
0x180003cc0  jb      loc_180003DA6
0x180003cc6  movzx   eax, r9b
0x180003cca  lea     rcx, __ImageBase
0x180003cd1  shr     rax, 3
0x180003cd5  movzx   r11d, byte ptr [rax+rcx+74E8h]
0x180003cde  test    r11b, r11b
0x180003ce1  jnz     short loc_180003D26
0x180003ce3  add     qword ptr [r10], 6
0x180003ce7  mov     eax, 246h
0x180003cec  jmp     loc_180003C25
0x180003cf1  or      cx, 20h
0x180003cf5  sub     cx, 61h ; 'a'
0x180003cf9  cmp     cx, 6
0x180003cfd  jnb     loc_180003C3B
0x180003d03  lea     r9d, [rcx+0Ah]
0x180003d07  jmp     loc_180003C61
0x180003d0c  or      cx, 20h
0x180003d10  sub     cx, 61h ; 'a'
0x180003d14  cmp     cx, 6
0x180003d18  jnb     loc_180003C3B
0x180003d1e  lea     eax, [rcx+0Ah]
0x180003d21  jmp     loc_180003C72
0x180003d26  mov     [r8+4], r11b
0x180003d2a  movzx   ecx, ds:rva byte_1800076E1[rcx+r11*2]
0x180003d33  dec     r11b
0x180003d36  movzx   eax, r9b
0x180003d3a  not     ecx
0x180003d3c  and     ecx, eax
0x180003d3e  mov     [r8+5], r11b
0x180003d42  mov     [r8], ecx
0x180003d45  mov     eax, 3E5h
0x180003d4a  add     qword ptr [r10], 6
0x180003d4e  jmp     loc_180003C25
0x180003d53  movzx   eax, byte ptr [r8+4]
0x180003d58  lea     rcx, __ImageBase
0x180003d5f  cmp     r9d, ds:rva dword_1800076F0[rcx+rax*4]
0x180003d67  jb      loc_180003CE3
0x180003d6d  cmp     r9d, 0D7FFh
0x180003d74  jbe     short loc_180003D88
0x180003d76  lea     eax, [r9-0E000h]
0x180003d7d  cmp     eax, 101FFFh
0x180003d82  ja      loc_180003CE3
0x180003d88  mov     [rdx], r9d
0x180003d8b  xor     eax, eax
0x180003d8d  jmp     loc_180003CB3
0x180003d92  mov     ecx, 3FFh
0x180003d97  cmp     ax, cx
0x180003d9a  jbe     short loc_180003DB3
0x180003d9c  mov     eax, 246h
0x180003da1  jmp     loc_180003C21
0x180003da6  movsx   eax, r9b
0x180003daa  mov     [rdx], eax
0x180003dac  xor     eax, eax
0x180003dae  jmp     loc_180003CB3
0x180003db3  mov     [r9+2], ax
0x180003db8  mov     eax, 3E5h
0x180003dbd  mov     byte ptr [r9], 1
0x180003dc1  jmp     loc_180003C21
0x180003dc6  mov     eax, 2400h
0x180003dcb  mov     byte ptr [r9], 0
0x180003dcf  add     r11w, ax
0x180003dd3  mov     ecx, 3FFh
0x180003dd8  cmp     r11w, cx
0x180003ddc  ja      short loc_180003D9C
0x180003dde  movzx   ecx, word ptr [r9+2]
0x180003de3  shl     ecx, 0Ah
0x180003de6  add     ecx, 10000h
0x180003dec  movzx   eax, r11w
0x180003df0  add     ecx, eax
0x180003df2  mov     [rdx], ecx
0x180003df4  xor     eax, eax
0x180003df6  jmp     loc_180003C21
```
