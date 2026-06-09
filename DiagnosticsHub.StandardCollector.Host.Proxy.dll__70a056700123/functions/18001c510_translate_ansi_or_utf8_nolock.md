# translate_ansi_or_utf8_nolock

- ea: `0x18001c510`
- end: `0x18001c83f`
- name: `translate_ansi_or_utf8_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001c9fc`

## callees

- `0x180007718`
- `0x180007788`
- `0x18000af1c`
- `0x18001b0e8`
- `0x18001c510`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001c5da`
- `KERNEL32!ReadFile` at `0x18001c5da`
- `KERNEL32!GetLastError` at `0x18001c7d7`
- `KERNEL32!GetLastError` at `0x18001c7d7`

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
0x18001c510  mov     [rsp+arg_10], rbx
0x18001c515  push    rbp
0x18001c516  push    rsi
0x18001c517  push    rdi
0x18001c518  push    r12
0x18001c51a  push    r13
0x18001c51c  push    r14
0x18001c51e  push    r15
0x18001c520  sub     rsp, 30h
0x18001c524  movsxd  rbp, ecx
0x18001c527  lea     r11, cs:180000000h
0x18001c52e  mov     r14, rbp
0x18001c531  mov     r15, rbp
0x18001c534  sar     r15, 6
0x18001c538  and     r14d, 3Fh
0x18001c53c  mov     r12, r9
0x18001c53f  mov     rdi, rdx
0x18001c542  mov     rax, rva __pioinfo[r11+r15*8]
0x18001c54a  lea     rsi, [r14+r14*8]
0x18001c54e  mov     r10, [rax+rsi*8+28h]
0x18001c553  test    r8, r8
0x18001c556  jz      short loc_18001C564
0x18001c558  cmp     byte ptr [rdx], 0Ah
0x18001c55b  jnz     short loc_18001C564
0x18001c55d  or      byte ptr [rax+rsi*8+38h], 4
0x18001c562  jmp     short loc_18001C569
0x18001c564  and     byte ptr [rax+rsi*8+38h], 0FBh
0x18001c569  lea     r9, [rdx+r8]
0x18001c56d  mov     rax, rdi
0x18001c570  mov     rbx, rdi
0x18001c573  mov     r13d, 1
0x18001c579  cmp     rdi, r9
0x18001c57c  jnb     loc_18001C67C
0x18001c582  mov     cl, [rax]
0x18001c584  cmp     cl, 1Ah
0x18001c587  jz      loc_18001C659
0x18001c58d  lea     rdx, [rax+1]
0x18001c591  cmp     cl, 0Dh
0x18001c594  jnz     short loc_18001C5A9
0x18001c596  cmp     rdx, r9
0x18001c599  jnb     short loc_18001C5BB
0x18001c59b  cmp     byte ptr [rdx], 0Ah
0x18001c59e  jnz     short loc_18001C5A9
0x18001c5a0  add     rax, 2
0x18001c5a4  mov     byte ptr [rbx], 0Ah
0x18001c5a7  jmp     short loc_18001C5AE
0x18001c5a9  mov     [rbx], cl
0x18001c5ab  mov     rax, rdx
0x18001c5ae  inc     rbx
0x18001c5b1  cmp     rax, r9
0x18001c5b4  jb      short loc_18001C582
0x18001c5b6  jmp     loc_18001C67C
0x18001c5bb  xor     eax, eax
0x18001c5bd  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001c5c2  mov     r8d, r13d; nNumberOfBytesToRead
0x18001c5c5  mov     [rsp+68h+Buffer], al
0x18001c5c9  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18001c5ce  mov     [rsp+68h+NumberOfBytesRead], eax
0x18001c5d2  mov     rcx, r10; hFile
0x18001c5d5  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18001c5da  call    cs:__imp_ReadFile
0x18001c5e0  test    eax, eax
0x18001c5e2  jz      short loc_18001C64D
0x18001c5e4  cmp     [rsp+68h+NumberOfBytesRead], 0
0x18001c5e9  jz      short loc_18001C64D
0x18001c5eb  lea     r11, cs:180000000h
0x18001c5f2  mov     rax, rva __pioinfo[r11+r15*8]
0x18001c5fa  test    byte ptr [rax+rsi*8+38h], 48h
0x18001c5ff  jz      short loc_18001C620
0x18001c601  mov     cl, [rsp+68h+Buffer]
0x18001c605  cmp     cl, 0Ah
0x18001c608  jnz     short loc_18001C60F
0x18001c60a  mov     byte ptr [rbx], 0Ah
0x18001c60d  jmp     short loc_18001C679
0x18001c60f  mov     byte ptr [rbx], 0Dh
0x18001c612  mov     rax, rva __pioinfo[r11+r15*8]
0x18001c61a  mov     [rax+rsi*8+3Ah], cl
0x18001c61e  jmp     short loc_18001C679
0x18001c620  cmp     [rsp+68h+Buffer], 0Ah
0x18001c625  jnz     short loc_18001C62C
0x18001c627  cmp     rbx, rdi
0x18001c62a  jz      short loc_18001C60A
0x18001c62c  mov     r8d, r13d
0x18001c62f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c633  mov     ecx, ebp
0x18001c635  call    _lseeki64_nolock
0x18001c63a  cmp     [rsp+68h+Buffer], 0Ah
0x18001c63f  lea     r11, cs:180000000h
0x18001c646  jz      short loc_18001C67C
0x18001c648  mov     byte ptr [rbx], 0Dh
0x18001c64b  jmp     short loc_18001C679
0x18001c64d  mov     byte ptr [rbx], 0Dh
0x18001c650  lea     r11, cs:180000000h
0x18001c657  jmp     short loc_18001C679
0x18001c659  mov     r8, rva __pioinfo[r11+r15*8]
0x18001c661  lea     rdx, [r14+r14*8]
0x18001c665  mov     al, [r8+rdx*8+38h]
0x18001c66a  test    al, 40h
0x18001c66c  jnz     short loc_18001C677
0x18001c66e  or      al, 2
0x18001c670  mov     [r8+rdx*8+38h], al
0x18001c675  jmp     short loc_18001C67C
0x18001c677  mov     [rbx], cl
0x18001c679  add     rbx, r13
0x18001c67c  sub     ebx, edi
0x18001c67e  jnz     short loc_18001C687
0x18001c680  xor     eax, eax
0x18001c682  jmp     loc_18001C827
0x18001c687  mov     rcx, rva __pioinfo[r11+r15*8]
0x18001c68f  lea     rdx, [r14+r14*8]
0x18001c693  cmp     byte ptr [rcx+rdx*8+39h], 0
0x18001c698  jnz     short loc_18001C6A1
0x18001c69a  mov     eax, ebx
0x18001c69c  jmp     loc_18001C827
0x18001c6a1  movsxd  rcx, ebx
0x18001c6a4  add     rcx, rdi
0x18001c6a7  lea     rbx, [rcx-1]
0x18001c6ab  cmp     byte ptr [rbx], 0
0x18001c6ae  jl      short loc_18001C6B8
0x18001c6b0  mov     rbx, rcx
0x18001c6b3  jmp     loc_18001C7AC
0x18001c6b8  mov     r8d, r13d
0x18001c6bb  jmp     short loc_18001C6CE
0x18001c6bd  cmp     r8d, 4
0x18001c6c1  ja      short loc_18001C6DC
0x18001c6c3  cmp     rbx, rdi
0x18001c6c6  jb      short loc_18001C6DC
0x18001c6c8  sub     rbx, r13
0x18001c6cb  add     r8d, r13d
0x18001c6ce  movzx   eax, byte ptr [rbx]
0x18001c6d1  cmp     byte ptr [rax+r11+77AA0h], 0
0x18001c6da  jz      short loc_18001C6BD
0x18001c6dc  movzx   edx, byte ptr [rbx]
0x18001c6df  movsx   eax, byte ptr [rdx+r11+77AA0h]
0x18001c6e8  test    eax, eax
0x18001c6ea  jnz     short loc_18001C6FF
0x18001c6ec  call    _errno
0x18001c6f1  mov     dword ptr [rax], 2Ah ; '*'
0x18001c6f7  or      eax, 0FFFFFFFFh
0x18001c6fa  jmp     loc_18001C827
0x18001c6ff  inc     eax
0x18001c701  cmp     eax, r8d
0x18001c704  jnz     short loc_18001C711
0x18001c706  mov     eax, r8d
0x18001c709  add     rbx, rax
0x18001c70c  jmp     loc_18001C7AC
0x18001c711  mov     rcx, rbp
0x18001c714  mov     rax, rbp
0x18001c717  sar     rax, 6
0x18001c71b  and     ecx, 3Fh
0x18001c71e  mov     r9, rva __pioinfo[r11+rax*8]
0x18001c726  lea     rax, [rcx+rcx*8]
0x18001c72a  test    byte ptr [r9+rax*8+38h], 48h
0x18001c730  jz      short loc_18001C79C
0x18001c732  mov     rax, rbp
0x18001c735  add     rbx, r13
0x18001c738  and     eax, 3Fh
0x18001c73b  lea     rax, [rax+rax*8]
0x18001c73f  mov     [r9+rax*8+3Ah], dl
0x18001c744  cmp     r8d, 2
0x18001c748  jb      short loc_18001C76C
0x18001c74a  mov     dl, [rbx]
0x18001c74c  mov     rcx, rbp
0x18001c74f  mov     rax, rbp
0x18001c752  add     rbx, r13
0x18001c755  sar     rax, 6
0x18001c759  and     ecx, 3Fh
0x18001c75c  mov     rax, rva __pioinfo[r11+rax*8]
0x18001c764  lea     rcx, [rcx+rcx*8]
0x18001c768  mov     [rax+rcx*8+3Bh], dl
0x18001c76c  cmp     r8d, 3
0x18001c770  jnz     short loc_18001C794
0x18001c772  mov     dl, [rbx]
0x18001c774  mov     rcx, rbp
0x18001c777  mov     rax, rbp
0x18001c77a  add     rbx, r13
0x18001c77d  sar     rax, 6
0x18001c781  and     ecx, 3Fh
0x18001c784  mov     rax, rva __pioinfo[r11+rax*8]
0x18001c78c  lea     rcx, [rcx+rcx*8]
0x18001c790  mov     [rax+rcx*8+3Ch], dl
0x18001c794  mov     eax, r8d
0x18001c797  sub     rbx, rax
0x18001c79a  jmp     short loc_18001C7AC
0x18001c79c  neg     r8d
0x18001c79f  mov     ecx, ebp
0x18001c7a1  movsxd  rdx, r8d
0x18001c7a4  mov     r8d, r13d
0x18001c7a7  call    _lseeki64_nolock
0x18001c7ac  mov     eax, [rsp+68h+arg_20]
0x18001c7b3  sub     ebx, edi
0x18001c7b5  mov     [rsp+68h+var_40], eax
0x18001c7b9  mov     r9d, ebx
0x18001c7bc  mov     r8, rdi
0x18001c7bf  mov     [rsp+68h+lpOverlapped], r12
0x18001c7c4  xor     edx, edx
0x18001c7c6  mov     ecx, 0FDE9h
0x18001c7cb  call    __acrt_MultiByteToWideChar
0x18001c7d0  mov     r9d, eax
0x18001c7d3  test    eax, eax
0x18001c7d5  jnz     short loc_18001C7E9
0x18001c7d7  call    cs:__imp_GetLastError
0x18001c7dd  mov     ecx, eax
0x18001c7df  call    __acrt_errno_map_os_error
0x18001c7e4  jmp     loc_18001C6F7
0x18001c7e9  mov     rcx, rbp
0x18001c7ec  lea     rdx, cs:180000000h
0x18001c7f3  and     ecx, 3Fh
0x18001c7f6  mov     rax, rbp
0x18001c7f9  sar     rax, 6
0x18001c7fd  lea     r8, [rcx+rcx*8]
0x18001c801  mov     rdx, rva __pioinfo[rdx+rax*8]
0x18001c809  mov     eax, r9d
0x18001c80c  sub     eax, ebx
0x18001c80e  neg     eax
0x18001c810  mov     al, [rdx+r8*8+3Dh]
0x18001c815  sbb     cl, cl
0x18001c817  and     al, 0FDh
0x18001c819  and     cl, 2
0x18001c81c  or      cl, al
0x18001c81e  lea     eax, [r9+r9]
0x18001c822  mov     [rdx+r8*8+3Dh], cl
0x18001c827  mov     rbx, [rsp+68h+arg_10]
0x18001c82f  add     rsp, 30h
0x18001c833  pop     r15
0x18001c835  pop     r14
0x18001c837  pop     r13
0x18001c839  pop     r12
0x18001c83b  pop     rdi
0x18001c83c  pop     rsi
0x18001c83d  pop     rbp
0x18001c83e  retn
```
