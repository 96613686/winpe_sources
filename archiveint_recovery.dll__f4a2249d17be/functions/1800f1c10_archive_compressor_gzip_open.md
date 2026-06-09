# archive_compressor_gzip_open

- ea: `0x1800f1c10`
- end: `0x1800f1e3c`
- name: `archive_compressor_gzip_open`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004814`
- `0x180006c00`
- `0x1800f0450`
- `0x1800f1c10`
- `0x180117818`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800f1cc6`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800f1cc6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1c62`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f1c62`

## string_xrefs

- `0x1800f1e04`: `Internal error initializing compression library: invalid setup parameter`
- `0x1800f1e19`: `Internal error initializing compression library: invalid library version`
- `0x1800f1c71`: `Can't allocate data for compression buffer`
- `0x1800f1de6`: `Internal error initializing compression library`
- `0x1800f1e0d`: `Internal error initializing compression library`

## pseudocode

```c
__int64 __fastcall archive_compressor_gzip_open(__int64 a1)
{
  unsigned int *v1; // rbx
  size_t v3; // rsi
  int v4; // eax
  void *v5; // rax
  const char *v6; // r8
  __int64 v7; // rdx
  unsigned int v8; // ebp
  unsigned int v9; // eax
  __int64 v10; // r8
  _BYTE *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r9
  int v15; // edx
  char *v16; // rdx
  _BYTE *v17; // rcx
  char v18; // al
  int v19; // esi

  v1 = *(unsigned int **)(a1 + 72);
  if ( !*((_QWORD *)v1 + 14) )
  {
    v3 = 0x10000;
    if ( **(_DWORD **)(a1 + 8) == -1329217314 )
    {
      v4 = archive_write_get_bytes_per_block();
      if ( (unsigned __int64)v4 <= 0x10000 )
      {
        if ( v4 )
          v3 = 0x10000 - 0x10000uLL % v4;
      }
      else
      {
        v3 = v4;
      }
    }
    *((_QWORD *)v1 + 15) = v3;
    v5 = malloc(v3);
    *((_QWORD *)v1 + 14) = v5;
    if ( !v5 )
    {
      v6 = "Can't allocate data for compression buffer";
LABEL_9:
      v7 = 12;
LABEL_35:
      archive_set_error(*(_QWORD *)(a1 + 8), v7, v6);
      return 4294967266LL;
    }
  }
  v8 = 0;
  v9 = crc32(0, 0, 0);
  v11 = (_BYTE *)*((_QWORD *)v1 + 14);
  v1[32] = v9;
  v1[10] = v1[30];
  *((_QWORD *)v1 + 4) = v11;
  *v11 = 31;
  *(_BYTE *)(*((_QWORD *)v1 + 14) + 1LL) = -117;
  *(_BYTE *)(*((_QWORD *)v1 + 14) + 2LL) = 8;
  *(_BYTE *)(*((_QWORD *)v1 + 14) + 3LL) = 0;
  if ( (v1[1] & 0x80000000) != 0 )
    *(_DWORD *)(*((_QWORD *)v1 + 14) + 4LL) = 0;
  else
    *(_DWORD *)(*((_QWORD *)v1 + 14) + 4LL) = _time64(0);
  v12 = *((_QWORD *)v1 + 14);
  if ( *v1 == 9 )
    *(_BYTE *)(v12 + 8) = 2;
  else
    *(_BYTE *)(v12 + 8) = *v1 != 1 ? 0 : 4;
  *(_BYTE *)(*((_QWORD *)v1 + 14) + 9LL) = 3;
  *((_QWORD *)v1 + 4) += 10LL;
  v1[10] -= 10;
  v13 = *((_QWORD *)v1 + 1);
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v13 + v14) );
    v10 = 0x8000;
    v15 = v1[30] + ~v1[8] + v1[28];
    if ( v15 < 0x8000 )
      v10 = (unsigned int)v15;
    if ( (int)v14 >= (int)v10 )
    {
      archive_set_error(*(_QWORD *)(a1 + 8), 0xFFFFFFFFLL, "Gzip 'Original Filename' ignored because it is too long");
      v8 = -20;
    }
    else
    {
      *(_BYTE *)(*((_QWORD *)v1 + 14) + 3LL) |= 8u;
      v16 = (char *)*((_QWORD *)v1 + 1);
      v17 = (_BYTE *)(*((_QWORD *)v1 + 14) + 10LL);
      do
      {
        v18 = *v16++;
        *v17++ = v18;
      }
      while ( v18 );
      *((_QWORD *)v1 + 4) += (int)v14 + 1;
      v1[10] += -1 - v14;
    }
  }
  *(_QWORD *)(a1 + 40) = archive_compressor_gzip_write;
  v19 = deflateInit2_(v1 + 4, *v1, v10, 4294967281LL);
  if ( !v19 )
  {
    *(_QWORD *)(a1 + 72) = v1;
    return v8;
  }
  archive_set_error(*(_QWORD *)(a1 + 8), 0xFFFFFFFFLL, "Internal error initializing compression library");
  switch ( v19 )
  {
    case -6:
      v6 = "Internal error initializing compression library: invalid library version";
      goto LABEL_34;
    case -4:
      v6 = "Internal error initializing compression library";
      goto LABEL_9;
    case -2:
      v6 = "Internal error initializing compression library: invalid setup parameter";
LABEL_34:
      v7 = 0xFFFFFFFFLL;
      goto LABEL_35;
  }
  return 4294967266LL;
}

```

## disassembly

```asm
0x1800f1c10  push    rbx
0x1800f1c12  push    rbp
0x1800f1c13  push    rsi
0x1800f1c14  push    rdi
0x1800f1c15  push    r15
0x1800f1c17  sub     rsp, 40h
0x1800f1c1b  mov     rbx, [rcx+48h]
0x1800f1c1f  mov     rdi, rcx
0x1800f1c22  cmp     qword ptr [rbx+70h], 0
0x1800f1c27  jnz     short loc_1800F1C82
0x1800f1c29  mov     rcx, [rcx+8]
0x1800f1c2d  mov     esi, 10000h
0x1800f1c32  cmp     dword ptr [rcx], 0B0C5C0DEh
0x1800f1c38  jnz     short loc_1800F1C5B
0x1800f1c3a  call    archive_write_get_bytes_per_block
0x1800f1c3f  movsxd  rcx, eax
0x1800f1c42  cmp     rcx, rsi
0x1800f1c45  jbe     short loc_1800F1C4C
0x1800f1c47  mov     rsi, rcx
0x1800f1c4a  jmp     short loc_1800F1C5B
0x1800f1c4c  test    eax, eax
0x1800f1c4e  jz      short loc_1800F1C5B
0x1800f1c50  xor     edx, edx
0x1800f1c52  mov     rax, rsi
0x1800f1c55  div     rcx
0x1800f1c58  sub     rsi, rdx
0x1800f1c5b  mov     rcx, rsi; Size
0x1800f1c5e  mov     [rbx+78h], rsi
0x1800f1c62  call    cs:__imp_malloc
0x1800f1c68  mov     [rbx+70h], rax
0x1800f1c6c  test    rax, rax
0x1800f1c6f  jnz     short loc_1800F1C82
0x1800f1c71  lea     r8, aCanTAllocateDa_3; "Can't allocate data for compression buf"...
0x1800f1c78  mov     edx, 0Ch
0x1800f1c7d  jmp     loc_1800F1E23
0x1800f1c82  xor     r8d, r8d
0x1800f1c85  xor     edx, edx
0x1800f1c87  xor     ecx, ecx
0x1800f1c89  xor     ebp, ebp
0x1800f1c8b  call    crc32
0x1800f1c90  mov     rcx, [rbx+70h]
0x1800f1c94  mov     [rbx+80h], eax
0x1800f1c9a  mov     eax, [rbx+78h]
0x1800f1c9d  mov     [rbx+28h], eax
0x1800f1ca0  mov     [rbx+20h], rcx
0x1800f1ca4  mov     byte ptr [rcx], 1Fh
0x1800f1ca7  xor     ecx, ecx; Time
0x1800f1ca9  mov     rax, [rbx+70h]
0x1800f1cad  mov     byte ptr [rax+1], 8Bh
0x1800f1cb1  mov     rax, [rbx+70h]
0x1800f1cb5  mov     byte ptr [rax+2], 8
0x1800f1cb9  mov     rax, [rbx+70h]
0x1800f1cbd  mov     [rax+3], bpl
0x1800f1cc1  cmp     [rbx+4], ebp
0x1800f1cc4  jl      short loc_1800F1CFC
0x1800f1cc6  call    cs:__imp__time64
0x1800f1ccc  mov     rcx, [rbx+70h]
0x1800f1cd0  mov     rdx, rax
0x1800f1cd3  sar     rdx, 8
0x1800f1cd7  mov     [rcx+4], al
0x1800f1cda  mov     rcx, [rbx+70h]
0x1800f1cde  mov     [rcx+5], dl
0x1800f1ce1  mov     rdx, rax
0x1800f1ce4  mov     rcx, [rbx+70h]
0x1800f1ce8  sar     rdx, 10h
0x1800f1cec  sar     rax, 18h
0x1800f1cf0  mov     [rcx+6], dl
0x1800f1cf3  mov     rcx, [rbx+70h]
0x1800f1cf7  mov     [rcx+7], al
0x1800f1cfa  jmp     short loc_1800F1D03
0x1800f1cfc  mov     rax, [rbx+70h]
0x1800f1d00  mov     [rax+4], ecx
0x1800f1d03  cmp     dword ptr [rbx], 9
0x1800f1d06  mov     rcx, [rbx+70h]
0x1800f1d0a  jnz     short loc_1800F1D12
0x1800f1d0c  mov     byte ptr [rcx+8], 2
0x1800f1d10  jmp     short loc_1800F1D1F
0x1800f1d12  cmp     dword ptr [rbx], 1
0x1800f1d15  setnz   al
0x1800f1d18  dec     al
0x1800f1d1a  and     al, 4
0x1800f1d1c  mov     [rcx+8], al
0x1800f1d1f  mov     rax, [rbx+70h]
0x1800f1d23  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800f1d27  mov     byte ptr [rax+9], 3
0x1800f1d2b  add     qword ptr [rbx+20h], 0Ah
0x1800f1d30  add     dword ptr [rbx+28h], 0FFFFFFF6h
0x1800f1d34  mov     rax, [rbx+8]
0x1800f1d38  test    rax, rax
0x1800f1d3b  jz      short loc_1800F1DB8
0x1800f1d3d  mov     r9, r15
0x1800f1d40  inc     r9
0x1800f1d43  cmp     [rax+r9], bpl
0x1800f1d47  jnz     short loc_1800F1D40
0x1800f1d49  mov     eax, [rbx+20h]
0x1800f1d4c  mov     r8d, 8000h
0x1800f1d52  mov     edx, [rbx+70h]
0x1800f1d55  not     eax
0x1800f1d57  add     edx, eax
0x1800f1d59  add     edx, [rbx+78h]
0x1800f1d5c  cmp     edx, r8d
0x1800f1d5f  cmovl   r8d, edx
0x1800f1d63  cmp     r9d, r8d
0x1800f1d66  jge     short loc_1800F1DA0
0x1800f1d68  mov     rax, [rbx+70h]
0x1800f1d6c  or      byte ptr [rax+3], 8
0x1800f1d70  mov     rcx, [rbx+70h]
0x1800f1d74  mov     rdx, [rbx+8]
0x1800f1d78  add     rcx, 0Ah
0x1800f1d7c  mov     al, [rdx]
0x1800f1d7e  inc     rdx
0x1800f1d81  mov     [rcx], al
0x1800f1d83  inc     rcx
0x1800f1d86  test    al, al
0x1800f1d88  jnz     short loc_1800F1D7C
0x1800f1d8a  lea     eax, [r9+1]
0x1800f1d8e  movsxd  rcx, eax
0x1800f1d91  or      eax, 0FFFFFFFFh
0x1800f1d94  add     [rbx+20h], rcx
0x1800f1d98  sub     eax, r9d
0x1800f1d9b  add     [rbx+28h], eax
0x1800f1d9e  jmp     short loc_1800F1DB8
0x1800f1da0  mov     rcx, [rdi+8]
0x1800f1da4  lea     r8, aGzipOriginalFi; "Gzip 'Original Filename' ignored becaus"...
0x1800f1dab  mov     edx, r15d
0x1800f1dae  call    archive_set_error
0x1800f1db3  mov     ebp, 0FFFFFFECh
0x1800f1db8  lea     rax, archive_compressor_gzip_write
0x1800f1dbf  mov     r9d, 0FFFFFFF1h
0x1800f1dc5  mov     [rdi+28h], rax
0x1800f1dc9  lea     rcx, [rbx+10h]
0x1800f1dcd  mov     edx, [rbx]
0x1800f1dcf  call    deflateInit2_
0x1800f1dd4  mov     esi, eax
0x1800f1dd6  test    eax, eax
0x1800f1dd8  jnz     short loc_1800F1DE2
0x1800f1dda  mov     [rdi+48h], rbx
0x1800f1dde  mov     eax, ebp
0x1800f1de0  jmp     short loc_1800F1E31
0x1800f1de2  mov     rcx, [rdi+8]
0x1800f1de6  lea     r8, aInternalErrorI_8; "Internal error initializing compression"...
0x1800f1ded  mov     edx, r15d
0x1800f1df0  call    archive_set_error
0x1800f1df5  cmp     esi, 0FFFFFFFAh
0x1800f1df8  jz      short loc_1800F1E19
0x1800f1dfa  cmp     esi, 0FFFFFFFCh
0x1800f1dfd  jz      short loc_1800F1E0D
0x1800f1dff  cmp     esi, 0FFFFFFFEh
0x1800f1e02  jnz     short loc_1800F1E2C
0x1800f1e04  lea     r8, aInternalErrorI_10; "Internal error initializing compression"...
0x1800f1e0b  jmp     short loc_1800F1E20
0x1800f1e0d  lea     r8, aInternalErrorI_8; "Internal error initializing compression"...
0x1800f1e14  jmp     loc_1800F1C78
0x1800f1e19  lea     r8, aInternalErrorI_6; "Internal error initializing compression"...
0x1800f1e20  mov     edx, r15d
0x1800f1e23  mov     rcx, [rdi+8]
0x1800f1e27  call    archive_set_error
0x1800f1e2c  mov     eax, 0FFFFFFE2h
0x1800f1e31  add     rsp, 40h
0x1800f1e35  pop     r15
0x1800f1e37  pop     rdi
0x1800f1e38  pop     rsi
0x1800f1e39  pop     rbp
0x1800f1e3a  pop     rbx
0x1800f1e3b  retn
```
