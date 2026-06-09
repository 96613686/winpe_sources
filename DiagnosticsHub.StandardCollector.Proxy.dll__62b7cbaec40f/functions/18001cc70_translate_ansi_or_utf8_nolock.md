# translate_ansi_or_utf8_nolock

- ea: `0x18001cc70`
- end: `0x18001cf9f`
- name: `translate_ansi_or_utf8_nolock`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001d15c`

## callees

- `0x180007e78`
- `0x180007ee8`
- `0x18000b67c`
- `0x18001b848`
- `0x18001cc70`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001cd3a`
- `KERNEL32!ReadFile` at `0x18001cd3a`
- `KERNEL32!GetLastError` at `0x18001cf37`
- `KERNEL32!GetLastError` at `0x18001cf37`

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
0x18001cc70  mov     [rsp+arg_10], rbx
0x18001cc75  push    rbp
0x18001cc76  push    rsi
0x18001cc77  push    rdi
0x18001cc78  push    r12
0x18001cc7a  push    r13
0x18001cc7c  push    r14
0x18001cc7e  push    r15
0x18001cc80  sub     rsp, 30h
0x18001cc84  movsxd  rbp, ecx
0x18001cc87  lea     r11, cs:180000000h
0x18001cc8e  mov     r14, rbp
0x18001cc91  mov     r15, rbp
0x18001cc94  sar     r15, 6
0x18001cc98  and     r14d, 3Fh
0x18001cc9c  mov     r12, r9
0x18001cc9f  mov     rdi, rdx
0x18001cca2  mov     rax, rva __pioinfo[r11+r15*8]
0x18001ccaa  lea     rsi, [r14+r14*8]
0x18001ccae  mov     r10, [rax+rsi*8+28h]
0x18001ccb3  test    r8, r8
0x18001ccb6  jz      short loc_18001CCC4
0x18001ccb8  cmp     byte ptr [rdx], 0Ah
0x18001ccbb  jnz     short loc_18001CCC4
0x18001ccbd  or      byte ptr [rax+rsi*8+38h], 4
0x18001ccc2  jmp     short loc_18001CCC9
0x18001ccc4  and     byte ptr [rax+rsi*8+38h], 0FBh
0x18001ccc9  lea     r9, [rdx+r8]
0x18001cccd  mov     rax, rdi
0x18001ccd0  mov     rbx, rdi
0x18001ccd3  mov     r13d, 1
0x18001ccd9  cmp     rdi, r9
0x18001ccdc  jnb     loc_18001CDDC
0x18001cce2  mov     cl, [rax]
0x18001cce4  cmp     cl, 1Ah
0x18001cce7  jz      loc_18001CDB9
0x18001cced  lea     rdx, [rax+1]
0x18001ccf1  cmp     cl, 0Dh
0x18001ccf4  jnz     short loc_18001CD09
0x18001ccf6  cmp     rdx, r9
0x18001ccf9  jnb     short loc_18001CD1B
0x18001ccfb  cmp     byte ptr [rdx], 0Ah
0x18001ccfe  jnz     short loc_18001CD09
0x18001cd00  add     rax, 2
0x18001cd04  mov     byte ptr [rbx], 0Ah
0x18001cd07  jmp     short loc_18001CD0E
0x18001cd09  mov     [rbx], cl
0x18001cd0b  mov     rax, rdx
0x18001cd0e  inc     rbx
0x18001cd11  cmp     rax, r9
0x18001cd14  jb      short loc_18001CCE2
0x18001cd16  jmp     loc_18001CDDC
0x18001cd1b  xor     eax, eax
0x18001cd1d  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001cd22  mov     r8d, r13d; nNumberOfBytesToRead
0x18001cd25  mov     [rsp+68h+Buffer], al
0x18001cd29  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18001cd2e  mov     [rsp+68h+NumberOfBytesRead], eax
0x18001cd32  mov     rcx, r10; hFile
0x18001cd35  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18001cd3a  call    cs:__imp_ReadFile
0x18001cd40  test    eax, eax
0x18001cd42  jz      short loc_18001CDAD
0x18001cd44  cmp     [rsp+68h+NumberOfBytesRead], 0
0x18001cd49  jz      short loc_18001CDAD
0x18001cd4b  lea     r11, cs:180000000h
0x18001cd52  mov     rax, rva __pioinfo[r11+r15*8]
0x18001cd5a  test    byte ptr [rax+rsi*8+38h], 48h
0x18001cd5f  jz      short loc_18001CD80
0x18001cd61  mov     cl, [rsp+68h+Buffer]
0x18001cd65  cmp     cl, 0Ah
0x18001cd68  jnz     short loc_18001CD6F
0x18001cd6a  mov     byte ptr [rbx], 0Ah
0x18001cd6d  jmp     short loc_18001CDD9
0x18001cd6f  mov     byte ptr [rbx], 0Dh
0x18001cd72  mov     rax, rva __pioinfo[r11+r15*8]
0x18001cd7a  mov     [rax+rsi*8+3Ah], cl
0x18001cd7e  jmp     short loc_18001CDD9
0x18001cd80  cmp     [rsp+68h+Buffer], 0Ah
0x18001cd85  jnz     short loc_18001CD8C
0x18001cd87  cmp     rbx, rdi
0x18001cd8a  jz      short loc_18001CD6A
0x18001cd8c  mov     r8d, r13d
0x18001cd8f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001cd93  mov     ecx, ebp
0x18001cd95  call    _lseeki64_nolock
0x18001cd9a  cmp     [rsp+68h+Buffer], 0Ah
0x18001cd9f  lea     r11, cs:180000000h
0x18001cda6  jz      short loc_18001CDDC
0x18001cda8  mov     byte ptr [rbx], 0Dh
0x18001cdab  jmp     short loc_18001CDD9
0x18001cdad  mov     byte ptr [rbx], 0Dh
0x18001cdb0  lea     r11, cs:180000000h
0x18001cdb7  jmp     short loc_18001CDD9
0x18001cdb9  mov     r8, rva __pioinfo[r11+r15*8]
0x18001cdc1  lea     rdx, [r14+r14*8]
0x18001cdc5  mov     al, [r8+rdx*8+38h]
0x18001cdca  test    al, 40h
0x18001cdcc  jnz     short loc_18001CDD7
0x18001cdce  or      al, 2
0x18001cdd0  mov     [r8+rdx*8+38h], al
0x18001cdd5  jmp     short loc_18001CDDC
0x18001cdd7  mov     [rbx], cl
0x18001cdd9  add     rbx, r13
0x18001cddc  sub     ebx, edi
0x18001cdde  jnz     short loc_18001CDE7
0x18001cde0  xor     eax, eax
0x18001cde2  jmp     loc_18001CF87
0x18001cde7  mov     rcx, rva __pioinfo[r11+r15*8]
0x18001cdef  lea     rdx, [r14+r14*8]
0x18001cdf3  cmp     byte ptr [rcx+rdx*8+39h], 0
0x18001cdf8  jnz     short loc_18001CE01
0x18001cdfa  mov     eax, ebx
0x18001cdfc  jmp     loc_18001CF87
0x18001ce01  movsxd  rcx, ebx
0x18001ce04  add     rcx, rdi
0x18001ce07  lea     rbx, [rcx-1]
0x18001ce0b  cmp     byte ptr [rbx], 0
0x18001ce0e  jl      short loc_18001CE18
0x18001ce10  mov     rbx, rcx
0x18001ce13  jmp     loc_18001CF0C
0x18001ce18  mov     r8d, r13d
0x18001ce1b  jmp     short loc_18001CE2E
0x18001ce1d  cmp     r8d, 4
0x18001ce21  ja      short loc_18001CE3C
0x18001ce23  cmp     rbx, rdi
0x18001ce26  jb      short loc_18001CE3C
0x18001ce28  sub     rbx, r13
0x18001ce2b  add     r8d, r13d
0x18001ce2e  movzx   eax, byte ptr [rbx]
0x18001ce31  cmp     byte ptr [rax+r11+7AFE0h], 0
0x18001ce3a  jz      short loc_18001CE1D
0x18001ce3c  movzx   edx, byte ptr [rbx]
0x18001ce3f  movsx   eax, byte ptr [rdx+r11+7AFE0h]
0x18001ce48  test    eax, eax
0x18001ce4a  jnz     short loc_18001CE5F
0x18001ce4c  call    _errno
0x18001ce51  mov     dword ptr [rax], 2Ah ; '*'
0x18001ce57  or      eax, 0FFFFFFFFh
0x18001ce5a  jmp     loc_18001CF87
0x18001ce5f  inc     eax
0x18001ce61  cmp     eax, r8d
0x18001ce64  jnz     short loc_18001CE71
0x18001ce66  mov     eax, r8d
0x18001ce69  add     rbx, rax
0x18001ce6c  jmp     loc_18001CF0C
0x18001ce71  mov     rcx, rbp
0x18001ce74  mov     rax, rbp
0x18001ce77  sar     rax, 6
0x18001ce7b  and     ecx, 3Fh
0x18001ce7e  mov     r9, rva __pioinfo[r11+rax*8]
0x18001ce86  lea     rax, [rcx+rcx*8]
0x18001ce8a  test    byte ptr [r9+rax*8+38h], 48h
0x18001ce90  jz      short loc_18001CEFC
0x18001ce92  mov     rax, rbp
0x18001ce95  add     rbx, r13
0x18001ce98  and     eax, 3Fh
0x18001ce9b  lea     rax, [rax+rax*8]
0x18001ce9f  mov     [r9+rax*8+3Ah], dl
0x18001cea4  cmp     r8d, 2
0x18001cea8  jb      short loc_18001CECC
0x18001ceaa  mov     dl, [rbx]
0x18001ceac  mov     rcx, rbp
0x18001ceaf  mov     rax, rbp
0x18001ceb2  add     rbx, r13
0x18001ceb5  sar     rax, 6
0x18001ceb9  and     ecx, 3Fh
0x18001cebc  mov     rax, rva __pioinfo[r11+rax*8]
0x18001cec4  lea     rcx, [rcx+rcx*8]
0x18001cec8  mov     [rax+rcx*8+3Bh], dl
0x18001cecc  cmp     r8d, 3
0x18001ced0  jnz     short loc_18001CEF4
0x18001ced2  mov     dl, [rbx]
0x18001ced4  mov     rcx, rbp
0x18001ced7  mov     rax, rbp
0x18001ceda  add     rbx, r13
0x18001cedd  sar     rax, 6
0x18001cee1  and     ecx, 3Fh
0x18001cee4  mov     rax, rva __pioinfo[r11+rax*8]
0x18001ceec  lea     rcx, [rcx+rcx*8]
0x18001cef0  mov     [rax+rcx*8+3Ch], dl
0x18001cef4  mov     eax, r8d
0x18001cef7  sub     rbx, rax
0x18001cefa  jmp     short loc_18001CF0C
0x18001cefc  neg     r8d
0x18001ceff  mov     ecx, ebp
0x18001cf01  movsxd  rdx, r8d
0x18001cf04  mov     r8d, r13d
0x18001cf07  call    _lseeki64_nolock
0x18001cf0c  mov     eax, [rsp+68h+arg_20]
0x18001cf13  sub     ebx, edi
0x18001cf15  mov     [rsp+68h+var_40], eax
0x18001cf19  mov     r9d, ebx
0x18001cf1c  mov     r8, rdi
0x18001cf1f  mov     [rsp+68h+lpOverlapped], r12
0x18001cf24  xor     edx, edx
0x18001cf26  mov     ecx, 0FDE9h
0x18001cf2b  call    __acrt_MultiByteToWideChar
0x18001cf30  mov     r9d, eax
0x18001cf33  test    eax, eax
0x18001cf35  jnz     short loc_18001CF49
0x18001cf37  call    cs:__imp_GetLastError
0x18001cf3d  mov     ecx, eax
0x18001cf3f  call    __acrt_errno_map_os_error
0x18001cf44  jmp     loc_18001CE57
0x18001cf49  mov     rcx, rbp
0x18001cf4c  lea     rdx, cs:180000000h
0x18001cf53  and     ecx, 3Fh
0x18001cf56  mov     rax, rbp
0x18001cf59  sar     rax, 6
0x18001cf5d  lea     r8, [rcx+rcx*8]
0x18001cf61  mov     rdx, rva __pioinfo[rdx+rax*8]
0x18001cf69  mov     eax, r9d
0x18001cf6c  sub     eax, ebx
0x18001cf6e  neg     eax
0x18001cf70  mov     al, [rdx+r8*8+3Dh]
0x18001cf75  sbb     cl, cl
0x18001cf77  and     al, 0FDh
0x18001cf79  and     cl, 2
0x18001cf7c  or      cl, al
0x18001cf7e  lea     eax, [r9+r9]
0x18001cf82  mov     [rdx+r8*8+3Dh], cl
0x18001cf87  mov     rbx, [rsp+68h+arg_10]
0x18001cf8f  add     rsp, 30h
0x18001cf93  pop     r15
0x18001cf95  pop     r14
0x18001cf97  pop     r13
0x18001cf99  pop     r12
0x18001cf9b  pop     rdi
0x18001cf9c  pop     rsi
0x18001cf9d  pop     rbp
0x18001cf9e  retn
```
