# ValidateHiveAndRecoverFromLog

- ea: `0x18002f9c4`
- end: `0x18002fde1`
- name: `ValidateHiveAndRecoverFromLog`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18002c1fc`

## callees

- `0x180002140`
- `0x180002b28`
- `0x180002b34`
- `0x180002c48`
- `0x180003033`
- `0x18002f2f4`
- `0x18002f9c4`
- `0x180030b90`
- `0x180030bd0`
- `0x1800361a8`
- `0x180038240`
- `0x18003829c`
- `0x180038784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc04`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002fb61`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002fb61`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fbf4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fbf4`

## pseudocode

```c
__int64 __fastcall ValidateHiveAndRecoverFromLog(const void **a1, unsigned int *a2, __int64 a3, void *a4)
{
  unsigned int *v4; // r15
  const void **v5; // r14
  __int64 v7; // r10
  __int64 v8; // rdi
  unsigned int v9; // esi
  char v10; // al
  unsigned int v11; // r9d
  int v12; // edx
  int v13; // eax
  __int64 i; // rcx
  unsigned int LastError; // ebx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r13
  __int64 v19; // r14
  unsigned int v20; // eax
  DWORD LowPart; // eax
  LPVOID *v22; // r15
  DWORD v23; // ebx
  void *v24; // rax
  __int64 v25; // rdx
  int v26; // edx
  NTSTATUS v27; // eax
  unsigned int v28; // esi
  void *v29; // rax
  void *v30; // rbx
  __int64 j; // rdi
  void *v32; // rcx
  __int64 k; // rdi
  __int64 v34; // rcx
  __int64 m; // rdi
  void *v36; // rcx
  char v38; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h]
  const void **v43; // [rsp+60h] [rbp-A0h]
  unsigned int *v44; // [rsp+68h] [rbp-98h]
  void *Block[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v46; // [rsp+80h] [rbp-80h] BYREF
  DWORD nNumberOfBytesToRead[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-60h]
  __int128 v49; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v51[60]; // [rsp+E0h] [rbp-20h] BYREF
  int v52; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v53; // [rsp+120h] [rbp+20h]

  v44 = a2;
  v43 = a1;
  v4 = a2;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  v5 = a1;
  v46 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  *(_OWORD *)nNumberOfBytesToRead = 0;
  v48 = 0;
  *(_OWORD *)Block = 0;
  memset_0(v51, 0, 0x5Cu);
  v7 = 1;
  if ( *v4 < 0x1000 )
    goto LABEL_15;
  v8 = (__int64)*v5;
  v9 = *((_DWORD *)*v5 + 10);
  if ( v9 + 4096 < 0x1000 )
    goto LABEL_15;
  v10 = HvIsInPlaceBaseBlockValid(v8);
  v12 = -1;
  if ( v10 )
  {
    v41 = *(_QWORD *)(v8 + 12);
    v38 = v7;
    if ( *(_DWORD *)(v8 + 4) == *(_DWORD *)(v8 + 8) )
    {
      if ( v11 > *v4 )
        goto LABEL_15;
      goto LABEL_47;
    }
  }
  else
  {
    v9 = 0;
    v38 = 0;
    v13 = 0;
    for ( i = 0; i != 127; i += v7 )
      v13 ^= *(_DWORD *)(v8 + 4 * i);
    if ( v13 == -1 )
    {
      v13 = -2;
    }
    else if ( !v13 )
    {
      v13 = v7;
    }
    if ( v13 == *(_DWORD *)(v8 + 508) )
    {
      v16 = *(_QWORD *)(v8 + 12);
    }
    else
    {
      if ( *v4 < 0x1020 || *(_DWORD *)(v8 + 4096) != 1852400232 )
        goto LABEL_15;
      v16 = *(_QWORD *)(v8 + 4116);
    }
    v41 = v16;
  }
  LastError = ConstructLogPaths(a4, 0xFFFFFFFFLL, Block);
  v7 = 1;
  if ( LastError )
    goto LABEL_56;
  v18 = 0;
  v19 = 0;
  do
  {
    v20 = ORCreateFile((const WCHAR *)Block[v19], 1u, v17, 1u, &nNumberOfBytesToRead[2 * v18 - 4]);
    LastError = v20;
    if ( v20 == 2 )
    {
      v7 = 1;
    }
    else
    {
      if ( v20 )
        goto LABEL_55;
      hFile = *(HANDLE *)&nNumberOfBytesToRead[2 * v18 - 4];
      if ( !GetFileSizeEx(hFile, &FileSize) )
        LastError = GetLastError();
      if ( LastError )
        goto LABEL_55;
      LowPart = FileSize.LowPart;
      if ( FileSize.QuadPart > 0xFFFFFFFFLL )
      {
        LowPart = -1;
        FileSize.QuadPart = 0xFFFFFFFFLL;
      }
      v22 = (LPVOID *)&nNumberOfBytesToRead[4 * (unsigned int)v18];
      nNumberOfBytesToRead[4 * (unsigned int)v18 + 2] = LowPart;
      if ( LowPart )
      {
        v23 = LowPart;
        v24 = o__aligned_malloc_0(LowPart, 0x10u);
        *v22 = v24;
        if ( !v24 )
          goto LABEL_40;
        memset_0(v24, 0, v23);
        LastError = 0;
        if ( !ReadFile(hFile, *v22, nNumberOfBytesToRead[4 * (unsigned int)v18 + 2], &NumberOfBytesRead, 0) )
          LastError = GetLastError();
        if ( LastError )
          goto LABEL_55;
      }
      v7 = 1;
      v25 = 3 * v18;
      *((_QWORD *)&v49 + v25 + 1) = HiveRecoverReadRoutine;
      *((_QWORD *)v50 + v25) = v22;
      *((_DWORD *)&v50[-1] + 2 * v25) = ((_DWORD)v19 != 0) + 4;
      v18 = (unsigned int)(v18 + 1);
    }
    v19 = (unsigned int)(v19 + 1);
  }
  while ( (unsigned int)v19 < 2 );
  if ( (_DWORD)v18 )
  {
    if ( v38 )
    {
      v26 = *(_DWORD *)(v8 + 8);
      v8 = 0;
    }
    else
    {
      v26 = 0;
    }
    LOBYTE(v17) = v38 ^ 1;
    v27 = HvAnalyzeLogFiles((unsigned int)&v41, v26, v17, (unsigned int)&v49, v18, (__int64)v51, v8);
    if ( v27 < 0 )
      goto LABEL_43;
    v5 = v43;
    if ( v9 < v53 )
      v9 = v53;
    v4 = v44;
LABEL_47:
    v28 = v9 + 4096;
    if ( *v4 < v28 )
    {
      v29 = o__aligned_malloc_0(v28, 0x10u);
      v30 = v29;
      if ( !v29 )
      {
LABEL_40:
        LastError = 14;
LABEL_55:
        v7 = 1;
        goto LABEL_56;
      }
      memset_0(v29, 0, v28);
      memcpy_0(v30, *v5, *v4);
      if ( *v5 )
        aligned_free((void *)*v5);
      *v5 = v30;
      *v4 = v28;
    }
    if ( !v52
      || (v27 = HvApplyLogFilesToHiveImage((unsigned int)*v5, v12, (unsigned int)&v49, v11, (__int64)v51), v27 >= 0) )
    {
      LastError = 0;
      goto LABEL_55;
    }
LABEL_43:
    LastError = RtlNtStatusToDosError_0(v27);
    goto LABEL_55;
  }
LABEL_15:
  LastError = 1009;
LABEL_56:
  for ( j = 0; j != 2; j += v7 )
  {
    v32 = *(void **)&nNumberOfBytesToRead[4 * j];
    if ( v32 )
    {
      aligned_free(v32);
      v7 = 1;
    }
  }
  for ( k = 0; k != 2; k += v7 )
  {
    v34 = *(_QWORD *)&nNumberOfBytesToRead[2 * k - 4];
    if ( (unsigned __int64)(v34 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      ORCloseFile(v34);
      v7 = 1;
    }
  }
  for ( m = 0; m != 2; m += v7 )
  {
    v36 = Block[m];
    if ( v36 )
    {
      aligned_free(v36);
      v7 = 1;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18002f9c4  mov     [rsp-8+arg_10], rbx
0x18002f9c9  push    rbp
0x18002f9ca  push    rsi
0x18002f9cb  push    rdi
0x18002f9cc  push    r12
0x18002f9ce  push    r13
0x18002f9d0  push    r14
0x18002f9d2  push    r15
0x18002f9d4  lea     rbp, [rsp-50h]
0x18002f9d9  sub     rsp, 150h
0x18002f9e0  mov     rax, cs:__security_cookie
0x18002f9e7  xor     rax, rsp
0x18002f9ea  mov     [rbp+80h+var_40], rax
0x18002f9ee  xorps   xmm0, xmm0
0x18002f9f1  mov     [rsp+180h+var_118], rdx
0x18002f9f6  xorps   xmm1, xmm1
0x18002f9f9  mov     [rsp+180h+var_120], rcx
0x18002f9fe  mov     r15, rdx
0x18002fa01  mov     [rsp+180h+NumberOfBytesRead], 0
0x18002fa09  xor     edx, edx; Val
0x18002fa0b  mov     qword ptr [rsp+180h+FileSize], 0
0x18002fa14  mov     r14, rcx
0x18002fa17  mov     rbx, r9
0x18002fa1a  lea     rcx, [rbp+80h+var_A0]; void *
0x18002fa1e  movups  [rbp+80h+var_100], xmm0
0x18002fa22  lea     r8d, [rdx+5Ch]; Size
0x18002fa26  movups  [rbp+80h+var_D0], xmm1
0x18002fa2a  movups  [rbp+80h+var_C0], xmm1
0x18002fa2e  movups  [rbp+80h+var_B0], xmm1
0x18002fa32  movups  xmmword ptr [rbp+80h+nNumberOfBytesToRead], xmm0
0x18002fa36  movups  [rbp+80h+var_E0], xmm0
0x18002fa3a  movups  xmmword ptr [rsp+180h+Block], xmm0
0x18002fa3f  call    memset_0
0x18002fa44  mov     eax, 1000h
0x18002fa49  mov     r10d, 1
0x18002fa4f  cmp     [r15], eax
0x18002fa52  jb      short loc_18002FAD2
0x18002fa54  mov     rdi, [r14]
0x18002fa57  mov     esi, [rdi+28h]
0x18002fa5a  lea     r9d, [rsi+1000h]
0x18002fa61  cmp     r9d, eax
0x18002fa64  jb      short loc_18002FAD2
0x18002fa66  mov     rcx, rdi
0x18002fa69  call    HvIsInPlaceBaseBlockValid
0x18002fa6e  mov     edx, 0FFFFFFFFh
0x18002fa73  test    al, al
0x18002fa75  jz      short loc_18002FA98
0x18002fa77  mov     rax, [rdi+0Ch]
0x18002fa7b  mov     [rsp+180h+var_130], rax
0x18002fa80  mov     eax, [rdi+8]
0x18002fa83  mov     [rsp+180h+var_140], r10b
0x18002fa88  cmp     [rdi+4], eax
0x18002fa8b  jnz     short loc_18002FAFA
0x18002fa8d  cmp     r9d, [r15]
0x18002fa90  jbe     loc_18002FCD2
0x18002fa96  jmp     short loc_18002FAD2
0x18002fa98  xor     al, al
0x18002fa9a  xor     esi, esi
0x18002fa9c  mov     [rsp+180h+var_140], al
0x18002faa0  xor     eax, eax
0x18002faa2  xor     ecx, ecx
0x18002faa4  xor     eax, [rdi+rcx*4]
0x18002faa7  add     rcx, r10
0x18002faaa  cmp     rcx, 7Fh
0x18002faae  jnz     short loc_18002FAA4
0x18002fab0  cmp     eax, edx
0x18002fab2  jnz     short loc_18002FABB
0x18002fab4  mov     eax, 0FFFFFFFEh
0x18002fab9  jmp     short loc_18002FAC1
0x18002fabb  test    eax, eax
0x18002fabd  cmovz   eax, r10d
0x18002fac1  cmp     eax, [rdi+1FCh]
0x18002fac7  jz      short loc_18002FAF1
0x18002fac9  cmp     dword ptr [r15], 1020h
0x18002fad0  jnb     short loc_18002FADC
0x18002fad2  mov     ebx, 3F1h
0x18002fad7  jmp     loc_18002FD4C
0x18002fadc  cmp     dword ptr [rdi+1000h], 6E696268h
0x18002fae6  jnz     short loc_18002FAD2
0x18002fae8  mov     rax, [rdi+1014h]
0x18002faef  jmp     short loc_18002FAF5
0x18002faf1  mov     rax, [rdi+0Ch]
0x18002faf5  mov     [rsp+180h+var_130], rax
0x18002fafa  lea     r8, [rsp+180h+Block]
0x18002faff  mov     rcx, rbx; hFile
0x18002fb02  call    ConstructLogPaths
0x18002fb07  mov     ebx, eax
0x18002fb09  mov     r10d, 1
0x18002fb0f  test    eax, eax
0x18002fb11  jnz     loc_18002FD4C
0x18002fb17  xor     r13d, r13d
0x18002fb1a  xor     r14d, r14d
0x18002fb1d  mov     rcx, [rsp+r14*8+180h+Block]
0x18002fb22  lea     r12, [rbp+80h+var_100]
0x18002fb26  lea     r12, [r12+r13*8]
0x18002fb2a  mov     r15d, r13d
0x18002fb2d  mov     r9d, r10d
0x18002fb30  mov     [rsp+180h+lpOverlapped], r12
0x18002fb35  mov     edx, r10d
0x18002fb38  call    ORCreateFile
0x18002fb3d  mov     ebx, eax
0x18002fb3f  cmp     eax, 2
0x18002fb42  jz      loc_18002FC51
0x18002fb48  test    eax, eax
0x18002fb4a  jnz     loc_18002FD46
0x18002fb50  mov     rax, [r12]
0x18002fb54  lea     rdx, [rsp+180h+FileSize]; lpFileSize
0x18002fb59  mov     rcx, rax; hFile
0x18002fb5c  mov     [rsp+180h+hFile], rax
0x18002fb61  call    cs:__imp_GetFileSizeEx
0x18002fb68  nop     dword ptr [rax+rax+00h]
0x18002fb6d  test    eax, eax
0x18002fb6f  jnz     short loc_18002FB7F
0x18002fb71  call    cs:__imp_GetLastError
0x18002fb78  nop     dword ptr [rax+rax+00h]
0x18002fb7d  mov     ebx, eax
0x18002fb7f  test    ebx, ebx
0x18002fb81  jnz     loc_18002FD46
0x18002fb87  mov     rax, qword ptr [rsp+180h+FileSize]
0x18002fb8c  mov     ecx, 0FFFFFFFFh
0x18002fb91  cmp     rax, rcx
0x18002fb94  jle     short loc_18002FB9D
0x18002fb96  mov     eax, ecx
0x18002fb98  mov     qword ptr [rsp+180h+FileSize], rcx
0x18002fb9d  mov     r12, r15
0x18002fba0  lea     r15, [rbp+80h+nNumberOfBytesToRead]
0x18002fba4  shl     r12, 4
0x18002fba8  add     r15, r12
0x18002fbab  mov     [rbp+r12+80h+nNumberOfBytesToRead+8], eax
0x18002fbb0  test    eax, eax
0x18002fbb2  jz      short loc_18002FC1A
0x18002fbb4  mov     edx, 10h; Alignment
0x18002fbb9  mov     ecx, eax; Size
0x18002fbbb  mov     ebx, eax
0x18002fbbd  call    _o__aligned_malloc_0
0x18002fbc2  mov     [r15], rax
0x18002fbc5  test    rax, rax
0x18002fbc8  jz      loc_18002FC79
0x18002fbce  mov     r8d, ebx; Size
0x18002fbd1  xor     edx, edx; Val
0x18002fbd3  mov     rcx, rax; void *
0x18002fbd6  call    memset_0
0x18002fbdb  mov     r8d, [rbp+r12+80h+nNumberOfBytesToRead+8]; nNumberOfBytesToRead
0x18002fbe0  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002fbe5  mov     rdx, [r15]; lpBuffer
0x18002fbe8  xor     ebx, ebx
0x18002fbea  mov     rcx, [rsp+180h+hFile]; hFile
0x18002fbef  mov     [rsp+180h+lpOverlapped], rbx; lpOverlapped
0x18002fbf4  call    cs:__imp_ReadFile
0x18002fbfb  nop     dword ptr [rax+rax+00h]
0x18002fc00  test    eax, eax
0x18002fc02  jnz     short loc_18002FC12
0x18002fc04  call    cs:__imp_GetLastError
0x18002fc0b  nop     dword ptr [rax+rax+00h]
0x18002fc10  mov     ebx, eax
0x18002fc12  test    ebx, ebx
0x18002fc14  jnz     loc_18002FD46
0x18002fc1a  lea     rdx, ds:0[r13*2]
0x18002fc22  mov     r10d, 1
0x18002fc28  add     rdx, r13
0x18002fc2b  lea     rax, HiveRecoverReadRoutine
0x18002fc32  mov     qword ptr [rbp+rdx*8+80h+var_D0+8], rax
0x18002fc37  mov     eax, r14d
0x18002fc3a  neg     eax
0x18002fc3c  mov     qword ptr [rbp+rdx*8+80h+var_C0], r15
0x18002fc41  sbb     ecx, ecx
0x18002fc43  neg     ecx
0x18002fc45  add     ecx, 4
0x18002fc48  mov     dword ptr [rbp+rdx*8+80h+var_D0], ecx
0x18002fc4c  add     r13d, r10d
0x18002fc4f  jmp     short loc_18002FC57
0x18002fc51  mov     r10d, 1
0x18002fc57  add     r14d, r10d
0x18002fc5a  cmp     r14d, 2
0x18002fc5e  jb      loc_18002FB1D
0x18002fc64  test    r13d, r13d
0x18002fc67  jz      loc_18002FAD2
0x18002fc6d  mov     al, [rsp+180h+var_140]
0x18002fc71  test    al, al
0x18002fc73  jnz     short loc_18002FC83
0x18002fc75  xor     edx, edx
0x18002fc77  jmp     short loc_18002FC88
0x18002fc79  mov     ebx, 0Eh
0x18002fc7e  jmp     loc_18002FD46
0x18002fc83  mov     edx, [rdi+8]
0x18002fc86  xor     edi, edi
0x18002fc88  lea     rcx, [rbp+80h+var_A0]
0x18002fc8c  mov     [rsp+180h+var_150], rdi
0x18002fc91  mov     [rsp+180h+var_158], rcx
0x18002fc96  lea     r9, [rbp+80h+var_D0]
0x18002fc9a  xor     al, r10b
0x18002fc9d  mov     dword ptr [rsp+180h+lpOverlapped], r13d
0x18002fca2  lea     rcx, [rsp+180h+var_130]
0x18002fca7  mov     r8b, al
0x18002fcaa  call    HvAnalyzeLogFiles
0x18002fcaf  test    eax, eax
0x18002fcb1  jns     short loc_18002FCC1
0x18002fcb3  mov     ecx, eax; Status
0x18002fcb5  call    RtlNtStatusToDosError_0
0x18002fcba  mov     ebx, eax
0x18002fcbc  jmp     loc_18002FD46
0x18002fcc1  cmp     esi, [rbp+80h+var_60]
0x18002fcc4  mov     r14, [rsp+180h+var_120]
0x18002fcc9  cmovb   esi, [rbp+80h+var_60]
0x18002fccd  mov     r15, [rsp+180h+var_118]
0x18002fcd2  add     esi, 1000h
0x18002fcd8  cmp     [r15], esi
0x18002fcdb  jnb     short loc_18002FD21
0x18002fcdd  mov     edx, 10h; Alignment
0x18002fce2  mov     ecx, esi; Size
0x18002fce4  mov     edi, esi
0x18002fce6  call    _o__aligned_malloc_0
0x18002fceb  mov     rbx, rax
0x18002fcee  test    rax, rax
0x18002fcf1  jz      short loc_18002FC79
0x18002fcf3  mov     r8d, edi; Size
0x18002fcf6  xor     edx, edx; Val
0x18002fcf8  mov     rcx, rax; void *
0x18002fcfb  call    memset_0
0x18002fd00  mov     r8d, [r15]; Size
0x18002fd03  mov     rcx, rbx; void *
0x18002fd06  mov     rdx, [r14]; Src
0x18002fd09  call    memcpy_0
0x18002fd0e  mov     rcx, [r14]; Block
0x18002fd11  test    rcx, rcx
0x18002fd14  jz      short loc_18002FD1B
0x18002fd16  call    _aligned_free
0x18002fd1b  mov     [r14], rbx
0x18002fd1e  mov     [r15], esi
0x18002fd21  cmp     [rbp+80h+var_64], 0
0x18002fd25  jbe     short loc_18002FD44
0x18002fd27  mov     rcx, [r14]
0x18002fd2a  lea     rax, [rbp+80h+var_A0]
0x18002fd2e  lea     r8, [rbp+80h+var_D0]
0x18002fd32  mov     [rsp+180h+lpOverlapped], rax
0x18002fd37  call    HvApplyLogFilesToHiveImage
0x18002fd3c  test    eax, eax
0x18002fd3e  js      loc_18002FCB3
0x18002fd44  xor     ebx, ebx
0x18002fd46  mov     r10d, 1
0x18002fd4c  xor     edi, edi
0x18002fd4e  mov     rax, rdi
0x18002fd51  add     rax, rax
0x18002fd54  mov     rcx, qword ptr [rbp+rax*8+80h+nNumberOfBytesToRead]; Block
0x18002fd59  test    rcx, rcx
0x18002fd5c  jz      short loc_18002FD69
0x18002fd5e  call    _aligned_free
0x18002fd63  mov     r10d, 1
0x18002fd69  add     rdi, r10
0x18002fd6c  cmp     rdi, 2
0x18002fd70  jnz     short loc_18002FD4E
0x18002fd72  xor     edi, edi
0x18002fd74  mov     rcx, qword ptr [rbp+rdi*8+80h+var_100]
0x18002fd79  lea     rax, [rcx-1]
0x18002fd7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002fd81  ja      short loc_18002FD8E
0x18002fd83  call    ORCloseFile
0x18002fd88  mov     r10d, 1
0x18002fd8e  add     rdi, r10
0x18002fd91  cmp     rdi, 2
0x18002fd95  jnz     short loc_18002FD74
0x18002fd97  xor     edi, edi
0x18002fd99  mov     rcx, [rsp+rdi*8+180h+Block]; Block
0x18002fd9e  test    rcx, rcx
0x18002fda1  jz      short loc_18002FDAE
0x18002fda3  call    _aligned_free
0x18002fda8  mov     r10d, 1
0x18002fdae  add     rdi, r10
0x18002fdb1  cmp     rdi, 2
0x18002fdb5  jnz     short loc_18002FD99
0x18002fdb7  mov     eax, ebx
0x18002fdb9  mov     rcx, [rbp+80h+var_40]
0x18002fdbd  xor     rcx, rsp; StackCookie
0x18002fdc0  call    __security_check_cookie
0x18002fdc5  mov     rbx, [rsp+180h+arg_10]
0x18002fdcd  add     rsp, 150h
0x18002fdd4  pop     r15
0x18002fdd6  pop     r14
0x18002fdd8  pop     r13
0x18002fdda  pop     r12
0x18002fddc  pop     rdi
0x18002fddd  pop     rsi
0x18002fdde  pop     rbp
0x18002fddf  retn
```
