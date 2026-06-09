# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180030b70`
- end: `0x18003100c`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `1180`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b60`
- `0x180001b84`
- `0x18000262c`
- `0x180002ce9`
- `0x180002cf5`
- `0x18000bb3c`
- `0x18001ecf8`
- `0x18001ef84`
- `0x180030b70`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180030d3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180030d3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030f07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030ff9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180030e24`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180030e24`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030bcd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030bcd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030c10`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030e4a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030c10`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030e4a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180030d4e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180030d4e`
- `bcrypt!BCryptHashData` at `0x180030d84`
- `bcrypt!BCryptHashData` at `0x180030da5`
- `bcrypt!BCryptHashData` at `0x180030dc9`
- `bcrypt!BCryptHashData` at `0x180030de9`
- `bcrypt!BCryptHashData` at `0x180030eb2`
- `bcrypt!BCryptHashData` at `0x180030d84`
- `bcrypt!BCryptHashData` at `0x180030da5`
- `bcrypt!BCryptHashData` at `0x180030dc9`
- `bcrypt!BCryptHashData` at `0x180030de9`
- `bcrypt!BCryptHashData` at `0x180030eb2`
- `bcrypt!BCryptFinishHash` at `0x180030eed`
- `bcrypt!BCryptFinishHash` at `0x180030eed`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HANDLE FileW; // r15
  unsigned __int16 v9; // dx
  int v10; // ecx
  __int64 v11; // rax
  size_t v12; // r14
  void *v13; // rax
  void *v14; // rcx
  _QWORD *v15; // rax
  char *v16; // rdi
  __int64 v17; // r13
  unsigned __int64 v18; // rcx
  _QWORD *v19; // rdi
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  DWORD FileSize; // eax
  LONG v23; // r14d
  int v25; // ebx
  size_t v26; // rdi
  __int64 v27; // rcx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+48h] [rbp-B8h] BYREF
  char *v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 Buffer; // [rsp+70h] [rbp-90h] BYREF
  UCHAR pbInput[16]; // [rsp+80h] [rbp-80h] BYREF
  UCHAR v35[16]; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+A0h] [rbp-60h]
  __int16 v37; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[2]; // [rsp+B2h] [rbp-4Eh] BYREF
  int v39; // [rsp+B4h] [rbp-4Ch]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+104h] [rbp+4h]
  UCHAR v45[16]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v46; // [rsp+120h] [rbp+20h]

  v32 = a1;
  FileW = CreateFileW(*a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 2147500037LL;
  NumberOfBytesRead = 0;
  v36 = 0;
  Buffer = 0;
  *(_OWORD *)pbInput = 0;
  *(_OWORD *)v35 = 0;
  if ( !ReadFile(FileW, &Buffer, 0x34u, &NumberOfBytesRead, 0)
    || NumberOfBytesRead != 52
    || memcmp_0(&Buffer, &qword_18003DA30, 4u)
    || WORD2(Buffer) != 257
    || BYTE6(Buffer) != 1
    || *(_WORD *)&v35[10] != 32 )
  {
LABEL_41:
    CloseHandle(FileW);
    return 2147500037LL;
  }
  v9 = *(_WORD *)&v35[12];
  v10 = *((_DWORD *)*a2 - 4) + 32 * *(unsigned __int16 *)&v35[12];
  v29 = 0;
  v30 = 0;
  v11 = (unsigned int)(2 * v10 + 94);
  v12 = (unsigned int)v11;
  if ( 2 * v10 != -94 )
  {
    if ( (unsigned int)v11 < 0x1000uLL )
    {
      v15 = operator new((unsigned int)v11);
    }
    else
    {
      if ( v11 + 39 <= (unsigned __int64)(unsigned int)v11 )
        __scrt_throw_std_bad_array_new_length();
      v13 = operator new(v11 + 39);
      v14 = v13;
      if ( !v13 )
        __fastfail(5u);
      v15 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v15 - 1) = v14;
    }
    v16 = (char *)v15 + v12;
    *(_QWORD *)&v29 = v15;
    v30 = (char *)v15 + v12;
    memset_0(v15, 0, v12);
    *((_QWORD *)&v29 + 1) = v16;
    v31 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v31);
    v9 = *(_WORD *)&v35[12];
  }
  v17 = v29;
  v18 = (unsigned __int64)v9 << 6;
  v19 = (_QWORD *)(v29 + 28);
  v20 = (unsigned __int16)(*(*a2 - 8) + 1);
  v21 = v29 + 28 + v18;
  *(_WORD *)(v29 + 26) = v20;
  _o_wcscpy_s(v21, v20, *a2);
  *(_DWORD *)v17 = 0;
  FileSize = GetFileSize(FileW, 0);
  *(_DWORD *)(v17 + 4) = FileSize;
  if ( FileSize == -1 )
    goto LABEL_40;
  *(_WORD *)(v17 + 24) = *(_WORD *)&v35[12];
  if ( *(_BYTE *)a3 )
  {
    if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), (PUCHAR)&Buffer, 0x10u, 0) < 0 )
      *(_BYTE *)a3 = 0;
    if ( *(_BYTE *)a3 )
    {
      if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &pbInput[2], 2u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      if ( *(_BYTE *)a3 )
      {
        if ( BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &pbInput[4], 4u, 0) < 0 )
          *(_BYTE *)a3 = 0;
        if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), &v35[4], 4u, 0) < 0 )
          *(_BYTE *)a3 = 0;
      }
    }
  }
  v23 = *(_DWORD *)&pbInput[12];
  if ( *(unsigned __int16 *)&v35[10] * *(unsigned __int16 *)&v35[12] )
  {
    while ( 1 )
    {
      *(_OWORD *)v45 = 0;
      v46 = 0;
      if ( SetFilePointer(FileW, v23, 0, 0) == -1
        || !ReadFile(FileW, v45, 0x20u, &NumberOfBytesRead, 0)
        || NumberOfBytesRead != 32 )
      {
        break;
      }
      *v19 = *(unsigned int *)v45;
      v19[2] = *(unsigned int *)&v45[4];
      v19[3] = *(unsigned int *)&v45[8];
      v19[4] = *(unsigned int *)&v45[12];
      v19[5] = (unsigned int)v46;
      v19[6] = DWORD1(v46);
      v19[1] = DWORD2(v46);
      v19[7] = HIDWORD(v46);
      v19 += 8;
      if ( *(_BYTE *)a3 && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a3 + 16), v45, 0x20u, 0) < 0 )
        *(_BYTE *)a3 = 0;
      v23 += *(unsigned __int16 *)&v35[10];
      if ( v23 == *(_DWORD *)&pbInput[12] + *(unsigned __int16 *)&v35[10] * *(unsigned __int16 *)&v35[12] )
        goto LABEL_37;
    }
    v25 = -2147467259;
    goto LABEL_49;
  }
LABEL_37:
  if ( !*(_BYTE *)a3 )
  {
LABEL_40:
    std::vector<char>::~vector<char>(&v29);
    goto LABEL_41;
  }
  if ( BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a3 + 16), *(PUCHAR *)(a3 + 32), *(_DWORD *)(a3 + 40), 0) < 0 )
  {
    *(_BYTE *)a3 = 0;
    goto LABEL_40;
  }
  if ( !*(_BYTE *)a3 )
    goto LABEL_40;
  v26 = 16;
  if ( *(_DWORD *)(a3 + 40) <= 0x10u )
    v26 = *(unsigned int *)(a3 + 40);
  memcpy_0((void *)(v17 + 8), *(const void **)(a3 + 32), v26);
  if ( v26 != 16 )
    goto LABEL_40;
  memset_0(v38, 0, 0x56u);
  v37 = 4;
  v42 = v29;
  v43 = DWORD2(v29) - v29;
  v44 = a5;
  v27 = *(_QWORD *)(v32 + 16);
  v40 = a4;
  v41 = ElfImageGuid;
  v39 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, _QWORD))(*(_QWORD *)v27 + 192LL))(v27, &v37, 0, 0);
  if ( v25 < 0 )
  {
LABEL_49:
    std::vector<char>::~vector<char>(&v29);
    CloseHandle(FileW);
    return (unsigned int)v25;
  }
  std::vector<char>::~vector<char>(&v29);
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x180030b70  push    rbp
0x180030b72  push    rbx
0x180030b73  push    rsi
0x180030b74  push    rdi
0x180030b75  push    r12
0x180030b77  push    r13
0x180030b79  push    r14
0x180030b7b  push    r15
0x180030b7d  lea     rbp, [rsp-48h]
0x180030b82  sub     rsp, 148h
0x180030b89  mov     rax, cs:__security_cookie
0x180030b90  xor     rax, rsp
0x180030b93  mov     [rbp+80h+var_50], rax
0x180030b97  mov     r12, rdx
0x180030b9a  mov     [rsp+180h+var_118], rcx
0x180030b9f  xor     r13d, r13d
0x180030ba2  mov     rbx, r9
0x180030ba5  mov     rsi, r8
0x180030ba8  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x180030bad  mov     [rsp+180h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180030bb5  xor     r9d, r9d; lpSecurityAttributes
0x180030bb8  mov     rcx, [r12]; lpFileName
0x180030bbc  mov     edx, 80000000h; dwDesiredAccess
0x180030bc1  lea     r8d, [r13+7]; dwShareMode
0x180030bc5  mov     [rsp+180h+dwCreationDisposition], 3; dwCreationDisposition
0x180030bcd  call    cs:__imp_CreateFileW
0x180030bd3  mov     r15, rax
0x180030bd6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030bda  jz      loc_180030F0D
0x180030be0  xorps   xmm0, xmm0
0x180030be3  mov     [rsp+180h+NumberOfBytesRead], r13d
0x180030be8  xor     eax, eax
0x180030bea  mov     qword ptr [rsp+180h+dwCreationDisposition], r13; lpOverlapped
0x180030bef  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030bf4  mov     [rbp+80h+var_E0], eax
0x180030bf7  lea     r8d, [r13+34h]; nNumberOfBytesToRead
0x180030bfb  mov     rcx, r15; hFile
0x180030bfe  lea     rdx, [rsp+180h+Buffer]; lpBuffer
0x180030c03  movups  [rsp+180h+Buffer], xmm0
0x180030c08  movups  xmmword ptr [rbp+80h+pbInput], xmm0
0x180030c0c  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x180030c10  call    cs:__imp_ReadFile
0x180030c16  test    eax, eax
0x180030c18  jz      loc_180030F04
0x180030c1e  cmp     [rsp+180h+NumberOfBytesRead], 34h ; '4'
0x180030c23  jnz     loc_180030F04
0x180030c29  lea     r8d, [r13+4]; Size
0x180030c2d  lea     rdx, qword_18003DA30; Buf2
0x180030c34  lea     rcx, [rsp+180h+Buffer]; Buf1
0x180030c39  call    memcmp_0
0x180030c3e  test    eax, eax
0x180030c40  jnz     loc_180030F04
0x180030c46  cmp     byte ptr [rsp+180h+Buffer+4], 1
0x180030c4b  jnz     loc_180030F04
0x180030c51  cmp     byte ptr [rsp+180h+Buffer+5], 1
0x180030c56  jnz     loc_180030F04
0x180030c5c  cmp     byte ptr [rsp+180h+Buffer+6], 1
0x180030c61  jnz     loc_180030F04
0x180030c67  lea     eax, [r13+20h]
0x180030c6b  cmp     ax, word ptr [rbp+80h+var_F0+0Ah]
0x180030c6f  jnz     loc_180030F04
0x180030c75  mov     rax, [r12]
0x180030c79  xorps   xmm0, xmm0
0x180030c7c  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x180030c80  mov     ecx, edx
0x180030c82  shl     ecx, 5
0x180030c85  add     ecx, [rax-10h]
0x180030c88  movdqu  [rsp+180h+var_138], xmm0
0x180030c8e  mov     [rsp+180h+var_128], r13
0x180030c93  lea     eax, ds:5Eh[rcx*2]
0x180030c9a  mov     r14d, eax
0x180030c9d  test    eax, eax
0x180030c9f  jz      short loc_180030D12
0x180030ca1  cmp     r14, 1000h
0x180030ca8  jb      short loc_180030CD7
0x180030caa  lea     rcx, [rax+27h]; Size
0x180030cae  cmp     rcx, r14
0x180030cb1  jbe     loc_180031006
0x180030cb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030cbc  mov     rcx, rax
0x180030cbf  test    rax, rax
0x180030cc2  jnz     short loc_180030CC9
0x180030cc4  lea     ecx, [rax+5]
0x180030cc7  int     29h; Win8: RtlFailFast(ecx)
0x180030cc9  add     rax, 27h ; '''
0x180030ccd  and     rax, 0FFFFFFFFFFFFFFE0h
0x180030cd1  mov     [rax-8], rcx
0x180030cd5  jmp     short loc_180030CDF
0x180030cd7  mov     rcx, r14; Size
0x180030cda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030cdf  lea     rdi, [r14+rax]
0x180030ce3  mov     qword ptr [rsp+180h+var_138], rax
0x180030ce8  mov     r8, r14; Size
0x180030ceb  mov     [rsp+180h+var_128], rdi
0x180030cf0  xor     edx, edx; Val
0x180030cf2  mov     rcx, rax; void *
0x180030cf5  call    memset_0
0x180030cfa  lea     rcx, [rsp+180h+var_120]
0x180030cff  mov     qword ptr [rsp+180h+var_138+8], rdi
0x180030d04  mov     [rsp+180h+var_120], r13
0x180030d09  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180030d0e  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x180030d12  mov     rax, [r12]
0x180030d16  mov     r13, qword ptr [rsp+180h+var_138]
0x180030d1b  movzx   ecx, dx
0x180030d1e  shl     rcx, 6
0x180030d22  movzx   edx, word ptr [rax-10h]
0x180030d26  inc     dx
0x180030d29  lea     rdi, [r13+1Ch]
0x180030d2d  movzx   edx, dx
0x180030d30  add     rcx, rdi
0x180030d33  mov     [r13+1Ah], dx
0x180030d38  mov     r8, [r12]
0x180030d3c  call    cs:__imp__o_wcscpy_s
0x180030d42  xor     r12d, r12d
0x180030d45  xor     edx, edx; lpFileSizeHigh
0x180030d47  mov     rcx, r15; hFile
0x180030d4a  mov     [r13+0], r12d
0x180030d4e  call    cs:__imp_GetFileSize
0x180030d54  mov     [r13+4], eax
0x180030d58  cmp     eax, 0FFFFFFFFh
0x180030d5b  jz      loc_180030EFA
0x180030d61  movzx   eax, word ptr [rbp+80h+var_F0+0Ch]
0x180030d65  mov     [r13+18h], ax
0x180030d6a  cmp     [rsi], r12b
0x180030d6d  jz      loc_180030DF6
0x180030d73  mov     rcx, [rsi+10h]; hHash
0x180030d77  lea     r8d, [r12+10h]; cbInput
0x180030d7c  xor     r9d, r9d; dwFlags
0x180030d7f  lea     rdx, [rsp+180h+Buffer]; pbInput
0x180030d84  call    cs:__imp_BCryptHashData
0x180030d8a  test    eax, eax
0x180030d8c  jns     short loc_180030D91
0x180030d8e  mov     [rsi], r12b
0x180030d91  cmp     [rsi], r12b
0x180030d94  jz      short loc_180030DF6
0x180030d96  mov     rcx, [rsi+10h]; hHash
0x180030d9a  lea     rdx, [rbp+80h+pbInput+2]; pbInput
0x180030d9e  xor     r9d, r9d; dwFlags
0x180030da1  lea     r8d, [r9+2]; cbInput
0x180030da5  call    cs:__imp_BCryptHashData
0x180030dab  test    eax, eax
0x180030dad  jns     short loc_180030DB2
0x180030daf  mov     [rsi], r12b
0x180030db2  cmp     [rsi], r12b
0x180030db5  jz      short loc_180030DF6
0x180030db7  mov     rcx, [rsi+10h]; hHash
0x180030dbb  lea     rdx, [rbp+80h+pbInput+4]; pbInput
0x180030dbf  xor     r9d, r9d; dwFlags
0x180030dc2  lea     r14d, [r9+4]
0x180030dc6  mov     r8d, r14d; cbInput
0x180030dc9  call    cs:__imp_BCryptHashData
0x180030dcf  test    eax, eax
0x180030dd1  jns     short loc_180030DD6
0x180030dd3  mov     [rsi], r12b
0x180030dd6  cmp     [rsi], r12b
0x180030dd9  jz      short loc_180030DF6
0x180030ddb  mov     rcx, [rsi+10h]; hHash
0x180030ddf  lea     rdx, [rbp+80h+var_F0+4]; pbInput
0x180030de3  xor     r9d, r9d; dwFlags
0x180030de6  mov     r8d, r14d; cbInput
0x180030de9  call    cs:__imp_BCryptHashData
0x180030def  test    eax, eax
0x180030df1  jns     short loc_180030DF6
0x180030df3  mov     [rsi], r12b
0x180030df6  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x180030dfa  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x180030dfe  mov     r14d, dword ptr [rbp+80h+pbInput+0Ch]
0x180030e02  imul    ecx, eax
0x180030e05  test    ecx, ecx
0x180030e07  jz      loc_180030ED9
0x180030e0d  xorps   xmm0, xmm0
0x180030e10  xor     r9d, r9d; dwMoveMethod
0x180030e13  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030e16  mov     edx, r14d; lDistanceToMove
0x180030e19  mov     rcx, r15; hFile
0x180030e1c  movups  xmmword ptr [rbp+80h+var_70], xmm0
0x180030e20  movups  [rbp+80h+var_60], xmm0
0x180030e24  call    cs:__imp_SetFilePointer
0x180030e2a  cmp     eax, 0FFFFFFFFh
0x180030e2d  jz      loc_180030F32
0x180030e33  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030e38  mov     qword ptr [rsp+180h+dwCreationDisposition], r12; lpOverlapped
0x180030e3d  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x180030e43  lea     rdx, [rbp+80h+var_70]; lpBuffer
0x180030e47  mov     rcx, r15; hFile
0x180030e4a  call    cs:__imp_ReadFile
0x180030e50  test    eax, eax
0x180030e52  jz      loc_180030F32
0x180030e58  cmp     [rsp+180h+NumberOfBytesRead], 20h ; ' '
0x180030e5d  jnz     loc_180030F32
0x180030e63  mov     eax, dword ptr [rbp+80h+var_70]
0x180030e66  mov     [rdi], rax
0x180030e69  mov     eax, dword ptr [rbp+80h+var_70+4]
0x180030e6c  mov     [rdi+10h], rax
0x180030e70  mov     eax, dword ptr [rbp+80h+var_70+8]
0x180030e73  mov     [rdi+18h], rax
0x180030e77  mov     eax, dword ptr [rbp+80h+var_70+0Ch]
0x180030e7a  mov     [rdi+20h], rax
0x180030e7e  mov     eax, dword ptr [rbp+80h+var_60]
0x180030e81  mov     [rdi+28h], rax
0x180030e85  mov     eax, dword ptr [rbp+80h+var_60+4]
0x180030e88  mov     [rdi+30h], rax
0x180030e8c  mov     eax, dword ptr [rbp+80h+var_60+8]
0x180030e8f  mov     [rdi+8], rax
0x180030e93  mov     eax, dword ptr [rbp+80h+var_60+0Ch]
0x180030e96  mov     [rdi+38h], rax
0x180030e9a  add     rdi, 40h ; '@'
0x180030e9e  cmp     [rsi], r12b
0x180030ea1  jz      short loc_180030EBF
0x180030ea3  mov     rcx, [rsi+10h]; hHash
0x180030ea7  lea     rdx, [rbp+80h+var_70]; pbInput
0x180030eab  xor     r9d, r9d; dwFlags
0x180030eae  lea     r8d, [r9+20h]; cbInput
0x180030eb2  call    cs:__imp_BCryptHashData
0x180030eb8  test    eax, eax
0x180030eba  jns     short loc_180030EBF
0x180030ebc  mov     [rsi], r12b
0x180030ebf  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x180030ec3  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x180030ec7  add     r14d, eax
0x180030eca  imul    ecx, eax
0x180030ecd  add     ecx, dword ptr [rbp+80h+pbInput+0Ch]
0x180030ed0  cmp     r14d, ecx
0x180030ed3  jnz     loc_180030E0D
0x180030ed9  cmp     [rsi], r12b
0x180030edc  jz      short loc_180030EFA
0x180030ede  mov     r8d, [rsi+28h]; cbOutput
0x180030ee2  xor     r9d, r9d; dwFlags
0x180030ee5  mov     rdx, [rsi+20h]; pbOutput
0x180030ee9  mov     rcx, [rsi+10h]; hHash
0x180030eed  call    cs:__imp_BCryptFinishHash
0x180030ef3  test    eax, eax
0x180030ef5  jns     short loc_180030F3C
0x180030ef7  mov     [rsi], r12b
0x180030efa  lea     rcx, [rsp+180h+var_138]
0x180030eff  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180030f04  mov     rcx, r15; hObject
0x180030f07  call    cs:__imp_CloseHandle
0x180030f0d  mov     eax, 80004005h
0x180030f12  mov     rcx, [rbp+80h+var_50]
0x180030f16  xor     rcx, rsp; StackCookie
0x180030f19  call    __security_check_cookie
0x180030f1e  add     rsp, 148h
0x180030f25  pop     r15
0x180030f27  pop     r14
0x180030f29  pop     r13
0x180030f2b  pop     r12
0x180030f2d  pop     rdi
0x180030f2e  pop     rsi
0x180030f2f  pop     rbx
0x180030f30  pop     rbp
0x180030f31  retn
0x180030f32  mov     ebx, 80004005h
0x180030f37  jmp     loc_180030FD2
0x180030f3c  cmp     [rsi], r12b
0x180030f3f  jz      short loc_180030EFA
0x180030f41  cmp     dword ptr [rsi+28h], 10h
0x180030f45  mov     edi, 10h
0x180030f4a  ja      short loc_180030F4F
0x180030f4c  mov     edi, [rsi+28h]
0x180030f4f  mov     rdx, [rsi+20h]; Src
0x180030f53  lea     rcx, [r13+8]; void *
0x180030f57  mov     r8, rdi; Size
0x180030f5a  call    memcpy_0
0x180030f5f  cmp     rdi, 10h
0x180030f63  jnz     short loc_180030EFA
0x180030f65  xor     edx, edx; Val
0x180030f67  lea     r8d, [rdi+46h]; Size
0x180030f6b  lea     rcx, [rbp+80h+var_CE]; void *
0x180030f6f  call    memset_0
0x180030f74  mov     rcx, qword ptr [rsp+180h+var_138]
0x180030f79  lea     eax, [rdi-0Ch]
0x180030f7c  movups  xmm0, cs:ElfImageGuid
0x180030f83  mov     [rbp+80h+var_D0], ax
0x180030f87  lea     rdx, [rbp+80h+var_D0]
0x180030f8b  mov     eax, dword ptr [rsp+180h+var_138+8]
0x180030f8f  xor     r9d, r9d
0x180030f92  sub     eax, ecx
0x180030f94  mov     [rbp+80h+var_88], rcx
0x180030f98  mov     rcx, [rsp+180h+var_118]
0x180030f9d  xor     r8d, r8d
0x180030fa0  mov     [rbp+80h+var_80], eax
0x180030fa3  mov     eax, [rbp+80h+arg_20]
0x180030fa9  mov     [rbp+80h+var_7C], eax
0x180030fac  mov     rcx, [rcx+10h]
0x180030fb0  mov     [rbp+80h+var_C0], rbx
0x180030fb4  movdqu  [rbp+80h+var_B8], xmm0
0x180030fb9  mov     [rbp+80h+var_CC], r12d
0x180030fbd  mov     rax, [rcx]
0x180030fc0  mov     rax, [rax+0C0h]
0x180030fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fcc  mov     ebx, eax
0x180030fce  test    eax, eax
0x180030fd0  jns     short loc_180030FEC
0x180030fd2  lea     rcx, [rsp+180h+var_138]
0x180030fd7  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180030fdc  mov     rcx, r15; hObject
0x180030fdf  call    cs:__imp_CloseHandle
0x180030fe5  mov     eax, ebx
  ... truncated ...
```
