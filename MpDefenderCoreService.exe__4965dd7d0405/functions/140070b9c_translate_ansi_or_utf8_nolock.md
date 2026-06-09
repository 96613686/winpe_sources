# translate_ansi_or_utf8_nolock

- ea: `0x140070b9c`
- end: `0x140070ecb`
- name: `translate_ansi_or_utf8_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140070fec`

## callees

- `0x14005af8c`
- `0x14005affc`
- `0x14006d748`
- `0x140070b9c`
- `0x140071934`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140070c66`
- `KERNEL32!ReadFile` at `0x140070c66`
- `KERNEL32!GetLastError` at `0x140070e63`
- `KERNEL32!GetLastError` at `0x140070e63`

## pseudocode

```c
__int64 __fastcall translate_ansi_or_utf8_nolock(int a1, unsigned __int8 *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // rbp
  __int64 v6; // r15
  __int64 v7; // r14
  __int64 v10; // rax
  void *v11; // r10
  unsigned __int8 *v12; // r9
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rbx
  unsigned __int8 v15; // cl
  unsigned __int8 *v16; // rdx
  char v17; // cl
  __int64 v18; // r8
  char v19; // al
  unsigned int v20; // ebx
  __int64 result; // rax
  unsigned __int8 *v22; // rcx
  char *v23; // rbx
  unsigned int i; // r8d
  __int64 v25; // rdx
  __int64 v26; // r9
  char v27; // dl
  char v28; // dl
  unsigned int v29; // ebx
  int v30; // r9d
  DWORD LastError; // eax
  char Buffer; // [rsp+70h] [rbp+8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  v5 = a1;
  v6 = (__int64)a1 >> 6;
  v7 = a1 & 0x3F;
  v10 = _pioinfo[v6];
  v11 = *(void **)(v10 + 72 * v7 + 40);
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v10 + 72 * v7 + 56) |= 4u;
  else
    *(_BYTE *)(v10 + 72 * v7 + 56) &= ~4u;
  v12 = &a2[a3];
  v13 = a2;
  v14 = a2;
  if ( a2 >= &a2[a3] )
    goto LABEL_29;
  while ( 1 )
  {
    v15 = *v13;
    if ( *v13 == 26 )
    {
      v18 = _pioinfo[v6];
      v19 = *(_BYTE *)(v18 + 72 * v7 + 56);
      if ( (v19 & 0x40) == 0 )
      {
        *(_BYTE *)(v18 + 72 * v7 + 56) = v19 | 2;
        goto LABEL_29;
      }
      *v14 = 26;
      goto LABEL_28;
    }
    v16 = v13 + 1;
    if ( v15 != 13 )
    {
LABEL_11:
      *v14 = v15;
      ++v13;
      goto LABEL_12;
    }
    if ( v16 >= v12 )
      break;
    if ( *v16 != 10 )
      goto LABEL_11;
    v13 += 2;
    *v14 = 10;
LABEL_12:
    ++v14;
    if ( v13 >= v12 )
      goto LABEL_29;
  }
  Buffer = 0;
  NumberOfBytesRead = 0;
  if ( ReadFile(v11, &Buffer, 1u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
  {
    if ( (*(_BYTE *)(_pioinfo[v6] + 72 * v7 + 56) & 0x48) != 0 )
    {
      v17 = Buffer;
      if ( Buffer == 10 )
      {
LABEL_18:
        *v14 = 10;
        goto LABEL_28;
      }
      *v14 = 13;
      *(_BYTE *)(_pioinfo[v6] + 72 * v7 + 58) = v17;
    }
    else
    {
      if ( Buffer == 10 && v14 == a2 )
        goto LABEL_18;
      lseeki64_nolock((unsigned int)v5, -1, 1);
      if ( Buffer == 10 )
        goto LABEL_29;
      *v14 = 13;
    }
  }
  else
  {
    *v14 = 13;
  }
LABEL_28:
  LODWORD(v14) = (_DWORD)v14 + 1;
LABEL_29:
  v20 = (_DWORD)v14 - (_DWORD)a2;
  if ( !v20 )
    return 0;
  if ( !*(_BYTE *)(_pioinfo[v6] + 72 * v7 + 57) )
    return v20;
  v22 = &a2[v20];
  v23 = (char *)(v22 - 1);
  if ( (*(v22 - 1) & 0x80u) == 0 )
  {
    LODWORD(v23) = (_DWORD)v22;
    goto LABEL_52;
  }
  for ( i = 1; !*((_BYTE *)lookuptrailbytes + (unsigned __int8)*v23) && i <= 4 && v23 >= (char *)a2; ++i )
    --v23;
  v25 = (unsigned __int8)*v23;
  if ( !*((_BYTE *)lookuptrailbytes + v25) )
  {
    *errno() = 42;
    return 0xFFFFFFFFLL;
  }
  if ( *((char *)lookuptrailbytes + v25) + 1 == i )
  {
    LODWORD(v23) = i + (_DWORD)v23;
  }
  else
  {
    v26 = _pioinfo[v5 >> 6];
    if ( (*(_BYTE *)(v26 + 72 * (v5 & 0x3F) + 56) & 0x48) != 0 )
    {
      ++v23;
      *(_BYTE *)(v26 + 72 * (v5 & 0x3F) + 58) = v25;
      if ( i >= 2 )
      {
        v27 = *v23++;
        *(_BYTE *)(_pioinfo[v5 >> 6] + 72 * (v5 & 0x3F) + 59) = v27;
      }
      if ( i == 3 )
      {
        v28 = *v23;
        LODWORD(v23) = (_DWORD)v23 + 1;
        *(_BYTE *)(_pioinfo[v5 >> 6] + 72 * (v5 & 0x3F) + 60) = v28;
      }
      LODWORD(v23) = (_DWORD)v23 - i;
    }
    else
    {
      lseeki64_nolock((unsigned int)v5, -i, 1);
    }
  }
LABEL_52:
  v29 = (_DWORD)v23 - (_DWORD)a2;
  v30 = _acrt_MultiByteToWideChar(65001, 0, a2, v29, a4, a5);
  if ( v30 )
  {
    result = (unsigned int)(2 * v30);
    *(_BYTE *)(_pioinfo[v5 >> 6] + 72 * (v5 & 0x3F) + 61) = *(_BYTE *)(_pioinfo[v5 >> 6] + 72 * (v5 & 0x3F) + 61) & 0xFD
                                                          | (v29 != v30 ? 2 : 0);
  }
  else
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x140070b9c  mov     [rsp+arg_10], rbx
0x140070ba1  push    rbp
0x140070ba2  push    rsi
0x140070ba3  push    rdi
0x140070ba4  push    r12
0x140070ba6  push    r13
0x140070ba8  push    r14
0x140070baa  push    r15
0x140070bac  sub     rsp, 30h
0x140070bb0  movsxd  rbp, ecx
0x140070bb3  lea     r11, cs:140000000h
0x140070bba  mov     r14, rbp
0x140070bbd  mov     r15, rbp
0x140070bc0  sar     r15, 6
0x140070bc4  and     r14d, 3Fh
0x140070bc8  mov     r12, r9
0x140070bcb  mov     rdi, rdx
0x140070bce  mov     rax, rva __pioinfo[r11+r15*8]
0x140070bd6  lea     rsi, [r14+r14*8]
0x140070bda  mov     r10, [rax+rsi*8+28h]
0x140070bdf  test    r8, r8
0x140070be2  jz      short loc_140070BF0
0x140070be4  cmp     byte ptr [rdx], 0Ah
0x140070be7  jnz     short loc_140070BF0
0x140070be9  or      byte ptr [rax+rsi*8+38h], 4
0x140070bee  jmp     short loc_140070BF5
0x140070bf0  and     byte ptr [rax+rsi*8+38h], 0FBh
0x140070bf5  lea     r9, [rdx+r8]
0x140070bf9  mov     rax, rdi
0x140070bfc  mov     rbx, rdi
0x140070bff  mov     r13d, 1
0x140070c05  cmp     rdi, r9
0x140070c08  jnb     loc_140070D08
0x140070c0e  mov     cl, [rax]
0x140070c10  cmp     cl, 1Ah
0x140070c13  jz      loc_140070CE5
0x140070c19  lea     rdx, [rax+1]
0x140070c1d  cmp     cl, 0Dh
0x140070c20  jnz     short loc_140070C35
0x140070c22  cmp     rdx, r9
0x140070c25  jnb     short loc_140070C47
0x140070c27  cmp     byte ptr [rdx], 0Ah
0x140070c2a  jnz     short loc_140070C35
0x140070c2c  add     rax, 2
0x140070c30  mov     byte ptr [rbx], 0Ah
0x140070c33  jmp     short loc_140070C3A
0x140070c35  mov     [rbx], cl
0x140070c37  mov     rax, rdx
0x140070c3a  inc     rbx
0x140070c3d  cmp     rax, r9
0x140070c40  jb      short loc_140070C0E
0x140070c42  jmp     loc_140070D08
0x140070c47  xor     eax, eax
0x140070c49  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140070c4e  mov     r8d, r13d; nNumberOfBytesToRead
0x140070c51  mov     [rsp+68h+Buffer], al
0x140070c55  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x140070c5a  mov     [rsp+68h+NumberOfBytesRead], eax
0x140070c5e  mov     rcx, r10; hFile
0x140070c61  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x140070c66  call    cs:__imp_ReadFile
0x140070c6c  test    eax, eax
0x140070c6e  jz      short loc_140070CD9
0x140070c70  cmp     [rsp+68h+NumberOfBytesRead], 0
0x140070c75  jz      short loc_140070CD9
0x140070c77  lea     r11, cs:140000000h
0x140070c7e  mov     rax, rva __pioinfo[r11+r15*8]
0x140070c86  test    byte ptr [rax+rsi*8+38h], 48h
0x140070c8b  jz      short loc_140070CAC
0x140070c8d  mov     cl, [rsp+68h+Buffer]
0x140070c91  cmp     cl, 0Ah
0x140070c94  jnz     short loc_140070C9B
0x140070c96  mov     byte ptr [rbx], 0Ah
0x140070c99  jmp     short loc_140070D05
0x140070c9b  mov     byte ptr [rbx], 0Dh
0x140070c9e  mov     rax, rva __pioinfo[r11+r15*8]
0x140070ca6  mov     [rax+rsi*8+3Ah], cl
0x140070caa  jmp     short loc_140070D05
0x140070cac  cmp     [rsp+68h+Buffer], 0Ah
0x140070cb1  jnz     short loc_140070CB8
0x140070cb3  cmp     rbx, rdi
0x140070cb6  jz      short loc_140070C96
0x140070cb8  mov     r8d, r13d
0x140070cbb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140070cbf  mov     ecx, ebp
0x140070cc1  call    _lseeki64_nolock
0x140070cc6  cmp     [rsp+68h+Buffer], 0Ah
0x140070ccb  lea     r11, cs:140000000h
0x140070cd2  jz      short loc_140070D08
0x140070cd4  mov     byte ptr [rbx], 0Dh
0x140070cd7  jmp     short loc_140070D05
0x140070cd9  mov     byte ptr [rbx], 0Dh
0x140070cdc  lea     r11, cs:140000000h
0x140070ce3  jmp     short loc_140070D05
0x140070ce5  mov     r8, rva __pioinfo[r11+r15*8]
0x140070ced  lea     rdx, [r14+r14*8]
0x140070cf1  mov     al, [r8+rdx*8+38h]
0x140070cf6  test    al, 40h
0x140070cf8  jnz     short loc_140070D03
0x140070cfa  or      al, 2
0x140070cfc  mov     [r8+rdx*8+38h], al
0x140070d01  jmp     short loc_140070D08
0x140070d03  mov     [rbx], cl
0x140070d05  add     rbx, r13
0x140070d08  sub     ebx, edi
0x140070d0a  jnz     short loc_140070D13
0x140070d0c  xor     eax, eax
0x140070d0e  jmp     loc_140070EB3
0x140070d13  mov     rcx, rva __pioinfo[r11+r15*8]
0x140070d1b  lea     rdx, [r14+r14*8]
0x140070d1f  cmp     byte ptr [rcx+rdx*8+39h], 0
0x140070d24  jnz     short loc_140070D2D
0x140070d26  mov     eax, ebx
0x140070d28  jmp     loc_140070EB3
0x140070d2d  movsxd  rcx, ebx
0x140070d30  add     rcx, rdi
0x140070d33  lea     rbx, [rcx-1]
0x140070d37  cmp     byte ptr [rbx], 0
0x140070d3a  jl      short loc_140070D44
0x140070d3c  mov     rbx, rcx
0x140070d3f  jmp     loc_140070E38
0x140070d44  mov     r8d, r13d
0x140070d47  jmp     short loc_140070D5A
0x140070d49  cmp     r8d, 4
0x140070d4d  ja      short loc_140070D68
0x140070d4f  cmp     rbx, rdi
0x140070d52  jb      short loc_140070D68
0x140070d54  sub     rbx, r13
0x140070d57  add     r8d, r13d
0x140070d5a  movzx   eax, byte ptr [rbx]
0x140070d5d  cmp     byte ptr [rax+r11+1D8FB0h], 0
0x140070d66  jz      short loc_140070D49
0x140070d68  movzx   edx, byte ptr [rbx]
0x140070d6b  movsx   eax, byte ptr [rdx+r11+1D8FB0h]
0x140070d74  test    eax, eax
0x140070d76  jnz     short loc_140070D8B
0x140070d78  call    _errno
0x140070d7d  mov     dword ptr [rax], 2Ah ; '*'
0x140070d83  or      eax, 0FFFFFFFFh
0x140070d86  jmp     loc_140070EB3
0x140070d8b  inc     eax
0x140070d8d  cmp     eax, r8d
0x140070d90  jnz     short loc_140070D9D
0x140070d92  mov     eax, r8d
0x140070d95  add     rbx, rax
0x140070d98  jmp     loc_140070E38
0x140070d9d  mov     rcx, rbp
0x140070da0  mov     rax, rbp
0x140070da3  sar     rax, 6
0x140070da7  and     ecx, 3Fh
0x140070daa  mov     r9, rva __pioinfo[r11+rax*8]
0x140070db2  lea     rax, [rcx+rcx*8]
0x140070db6  test    byte ptr [r9+rax*8+38h], 48h
0x140070dbc  jz      short loc_140070E28
0x140070dbe  mov     rax, rbp
0x140070dc1  add     rbx, r13
0x140070dc4  and     eax, 3Fh
0x140070dc7  lea     rax, [rax+rax*8]
0x140070dcb  mov     [r9+rax*8+3Ah], dl
0x140070dd0  cmp     r8d, 2
0x140070dd4  jb      short loc_140070DF8
0x140070dd6  mov     dl, [rbx]
0x140070dd8  mov     rcx, rbp
0x140070ddb  mov     rax, rbp
0x140070dde  add     rbx, r13
0x140070de1  sar     rax, 6
0x140070de5  and     ecx, 3Fh
0x140070de8  mov     rax, rva __pioinfo[r11+rax*8]
0x140070df0  lea     rcx, [rcx+rcx*8]
0x140070df4  mov     [rax+rcx*8+3Bh], dl
0x140070df8  cmp     r8d, 3
0x140070dfc  jnz     short loc_140070E20
0x140070dfe  mov     dl, [rbx]
0x140070e00  mov     rcx, rbp
0x140070e03  mov     rax, rbp
0x140070e06  add     rbx, r13
0x140070e09  sar     rax, 6
0x140070e0d  and     ecx, 3Fh
0x140070e10  mov     rax, rva __pioinfo[r11+rax*8]
0x140070e18  lea     rcx, [rcx+rcx*8]
0x140070e1c  mov     [rax+rcx*8+3Ch], dl
0x140070e20  mov     eax, r8d
0x140070e23  sub     rbx, rax
0x140070e26  jmp     short loc_140070E38
0x140070e28  neg     r8d
0x140070e2b  mov     ecx, ebp
0x140070e2d  movsxd  rdx, r8d
0x140070e30  mov     r8d, r13d
0x140070e33  call    _lseeki64_nolock
0x140070e38  mov     eax, [rsp+68h+arg_20]
0x140070e3f  sub     ebx, edi
0x140070e41  mov     [rsp+68h+var_40], eax
0x140070e45  mov     r9d, ebx
0x140070e48  mov     r8, rdi
0x140070e4b  mov     [rsp+68h+lpOverlapped], r12
0x140070e50  xor     edx, edx
0x140070e52  mov     ecx, 0FDE9h
0x140070e57  call    __acrt_MultiByteToWideChar
0x140070e5c  mov     r9d, eax
0x140070e5f  test    eax, eax
0x140070e61  jnz     short loc_140070E75
0x140070e63  call    cs:__imp_GetLastError
0x140070e69  mov     ecx, eax
0x140070e6b  call    __acrt_errno_map_os_error
0x140070e70  jmp     loc_140070D83
0x140070e75  mov     rcx, rbp
0x140070e78  lea     rdx, cs:140000000h
0x140070e7f  and     ecx, 3Fh
0x140070e82  mov     rax, rbp
0x140070e85  sar     rax, 6
0x140070e89  lea     r8, [rcx+rcx*8]
0x140070e8d  mov     rdx, rva __pioinfo[rdx+rax*8]
0x140070e95  mov     eax, r9d
0x140070e98  sub     eax, ebx
0x140070e9a  neg     eax
0x140070e9c  mov     al, [rdx+r8*8+3Dh]
0x140070ea1  sbb     cl, cl
0x140070ea3  and     al, 0FDh
0x140070ea5  and     cl, 2
0x140070ea8  or      cl, al
0x140070eaa  lea     eax, [r9+r9]
0x140070eae  mov     [rdx+r8*8+3Dh], cl
0x140070eb3  mov     rbx, [rsp+68h+arg_10]
0x140070ebb  add     rsp, 30h
0x140070ebf  pop     r15
0x140070ec1  pop     r14
0x140070ec3  pop     r13
0x140070ec5  pop     r12
0x140070ec7  pop     rdi
0x140070ec8  pop     rsi
0x140070ec9  pop     rbp
0x140070eca  retn
```
