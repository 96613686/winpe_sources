# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180023510`
- end: `0x1800239ac`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `1180`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001870`
- `0x1800018a0`
- `0x180002420`
- `0x1800027a5`
- `0x1800027b1`
- `0x18000be50`
- `0x18000e0d8`
- `0x18000e364`
- `0x180023510`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800236dc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800236dc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800236ee`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800236ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002356d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002356d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800235b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800237ea`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800235b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800237ea`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800237c4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800237c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800238a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002397f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023999`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800238a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002397f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023999`
- `bcrypt!BCryptFinishHash` at `0x18002388d`
- `bcrypt!BCryptFinishHash` at `0x18002388d`
- `bcrypt!BCryptHashData` at `0x180023724`
- `bcrypt!BCryptHashData` at `0x180023745`
- `bcrypt!BCryptHashData` at `0x180023769`
- `bcrypt!BCryptHashData` at `0x180023789`
- `bcrypt!BCryptHashData` at `0x180023852`
- `bcrypt!BCryptHashData` at `0x180023724`
- `bcrypt!BCryptHashData` at `0x180023745`
- `bcrypt!BCryptHashData` at `0x180023769`
- `bcrypt!BCryptHashData` at `0x180023789`
- `bcrypt!BCryptHashData` at `0x180023852`

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
    || memcmp_0(&Buffer, &unk_18002ED38, 4u)
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
0x180023510  push    rbp
0x180023512  push    rbx
0x180023513  push    rsi
0x180023514  push    rdi
0x180023515  push    r12
0x180023517  push    r13
0x180023519  push    r14
0x18002351b  push    r15
0x18002351d  lea     rbp, [rsp-48h]
0x180023522  sub     rsp, 148h
0x180023529  mov     rax, cs:__security_cookie
0x180023530  xor     rax, rsp
0x180023533  mov     [rbp+80h+var_50], rax
0x180023537  mov     r12, rdx
0x18002353a  mov     [rsp+180h+var_118], rcx
0x18002353f  xor     r13d, r13d
0x180023542  mov     rbx, r9
0x180023545  mov     rsi, r8
0x180023548  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x18002354d  mov     [rsp+180h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023555  xor     r9d, r9d; lpSecurityAttributes
0x180023558  mov     rcx, [r12]; lpFileName
0x18002355c  mov     edx, 80000000h; dwDesiredAccess
0x180023561  lea     r8d, [r13+7]; dwShareMode
0x180023565  mov     [rsp+180h+dwCreationDisposition], 3; dwCreationDisposition
0x18002356d  call    cs:__imp_CreateFileW
0x180023573  mov     r15, rax
0x180023576  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002357a  jz      loc_1800238AD
0x180023580  xorps   xmm0, xmm0
0x180023583  mov     [rsp+180h+NumberOfBytesRead], r13d
0x180023588  xor     eax, eax
0x18002358a  mov     qword ptr [rsp+180h+dwCreationDisposition], r13; lpOverlapped
0x18002358f  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180023594  mov     [rbp+80h+var_E0], eax
0x180023597  lea     r8d, [r13+34h]; nNumberOfBytesToRead
0x18002359b  mov     rcx, r15; hFile
0x18002359e  lea     rdx, [rsp+180h+Buffer]; lpBuffer
0x1800235a3  movups  [rsp+180h+Buffer], xmm0
0x1800235a8  movups  xmmword ptr [rbp+80h+pbInput], xmm0
0x1800235ac  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x1800235b0  call    cs:__imp_ReadFile
0x1800235b6  test    eax, eax
0x1800235b8  jz      loc_1800238A4
0x1800235be  cmp     [rsp+180h+NumberOfBytesRead], 34h ; '4'
0x1800235c3  jnz     loc_1800238A4
0x1800235c9  lea     r8d, [r13+4]; Size
0x1800235cd  lea     rdx, unk_18002ED38; Buf2
0x1800235d4  lea     rcx, [rsp+180h+Buffer]; Buf1
0x1800235d9  call    memcmp_0
0x1800235de  test    eax, eax
0x1800235e0  jnz     loc_1800238A4
0x1800235e6  cmp     byte ptr [rsp+180h+Buffer+4], 1
0x1800235eb  jnz     loc_1800238A4
0x1800235f1  cmp     byte ptr [rsp+180h+Buffer+5], 1
0x1800235f6  jnz     loc_1800238A4
0x1800235fc  cmp     byte ptr [rsp+180h+Buffer+6], 1
0x180023601  jnz     loc_1800238A4
0x180023607  lea     eax, [r13+20h]
0x18002360b  cmp     ax, word ptr [rbp+80h+var_F0+0Ah]
0x18002360f  jnz     loc_1800238A4
0x180023615  mov     rax, [r12]
0x180023619  xorps   xmm0, xmm0
0x18002361c  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x180023620  mov     ecx, edx
0x180023622  shl     ecx, 5
0x180023625  add     ecx, [rax-10h]
0x180023628  movdqu  [rsp+180h+var_138], xmm0
0x18002362e  mov     [rsp+180h+var_128], r13
0x180023633  lea     eax, ds:5Eh[rcx*2]
0x18002363a  mov     r14d, eax
0x18002363d  test    eax, eax
0x18002363f  jz      short loc_1800236B2
0x180023641  cmp     r14, 1000h
0x180023648  jb      short loc_180023677
0x18002364a  lea     rcx, [rax+27h]; Size
0x18002364e  cmp     rcx, r14
0x180023651  jbe     loc_1800239A6
0x180023657  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002365c  mov     rcx, rax
0x18002365f  test    rax, rax
0x180023662  jnz     short loc_180023669
0x180023664  lea     ecx, [rax+5]
0x180023667  int     29h; Win8: RtlFailFast(ecx)
0x180023669  add     rax, 27h ; '''
0x18002366d  and     rax, 0FFFFFFFFFFFFFFE0h
0x180023671  mov     [rax-8], rcx
0x180023675  jmp     short loc_18002367F
0x180023677  mov     rcx, r14; Size
0x18002367a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002367f  lea     rdi, [r14+rax]
0x180023683  mov     qword ptr [rsp+180h+var_138], rax
0x180023688  mov     r8, r14; Size
0x18002368b  mov     [rsp+180h+var_128], rdi
0x180023690  xor     edx, edx; Val
0x180023692  mov     rcx, rax; void *
0x180023695  call    memset_0
0x18002369a  lea     rcx, [rsp+180h+var_120]
0x18002369f  mov     qword ptr [rsp+180h+var_138+8], rdi
0x1800236a4  mov     [rsp+180h+var_120], r13
0x1800236a9  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x1800236ae  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x1800236b2  mov     rax, [r12]
0x1800236b6  mov     r13, qword ptr [rsp+180h+var_138]
0x1800236bb  movzx   ecx, dx
0x1800236be  shl     rcx, 6
0x1800236c2  movzx   edx, word ptr [rax-10h]
0x1800236c6  inc     dx
0x1800236c9  lea     rdi, [r13+1Ch]
0x1800236cd  movzx   edx, dx
0x1800236d0  add     rcx, rdi
0x1800236d3  mov     [r13+1Ah], dx
0x1800236d8  mov     r8, [r12]
0x1800236dc  call    cs:__imp__o_wcscpy_s
0x1800236e2  xor     r12d, r12d
0x1800236e5  xor     edx, edx; lpFileSizeHigh
0x1800236e7  mov     rcx, r15; hFile
0x1800236ea  mov     [r13+0], r12d
0x1800236ee  call    cs:__imp_GetFileSize
0x1800236f4  mov     [r13+4], eax
0x1800236f8  cmp     eax, 0FFFFFFFFh
0x1800236fb  jz      loc_18002389A
0x180023701  movzx   eax, word ptr [rbp+80h+var_F0+0Ch]
0x180023705  mov     [r13+18h], ax
0x18002370a  cmp     [rsi], r12b
0x18002370d  jz      loc_180023796
0x180023713  mov     rcx, [rsi+10h]; hHash
0x180023717  lea     r8d, [r12+10h]; cbInput
0x18002371c  xor     r9d, r9d; dwFlags
0x18002371f  lea     rdx, [rsp+180h+Buffer]; pbInput
0x180023724  call    cs:__imp_BCryptHashData
0x18002372a  test    eax, eax
0x18002372c  jns     short loc_180023731
0x18002372e  mov     [rsi], r12b
0x180023731  cmp     [rsi], r12b
0x180023734  jz      short loc_180023796
0x180023736  mov     rcx, [rsi+10h]; hHash
0x18002373a  lea     rdx, [rbp+80h+pbInput+2]; pbInput
0x18002373e  xor     r9d, r9d; dwFlags
0x180023741  lea     r8d, [r9+2]; cbInput
0x180023745  call    cs:__imp_BCryptHashData
0x18002374b  test    eax, eax
0x18002374d  jns     short loc_180023752
0x18002374f  mov     [rsi], r12b
0x180023752  cmp     [rsi], r12b
0x180023755  jz      short loc_180023796
0x180023757  mov     rcx, [rsi+10h]; hHash
0x18002375b  lea     rdx, [rbp+80h+pbInput+4]; pbInput
0x18002375f  xor     r9d, r9d; dwFlags
0x180023762  lea     r14d, [r9+4]
0x180023766  mov     r8d, r14d; cbInput
0x180023769  call    cs:__imp_BCryptHashData
0x18002376f  test    eax, eax
0x180023771  jns     short loc_180023776
0x180023773  mov     [rsi], r12b
0x180023776  cmp     [rsi], r12b
0x180023779  jz      short loc_180023796
0x18002377b  mov     rcx, [rsi+10h]; hHash
0x18002377f  lea     rdx, [rbp+80h+var_F0+4]; pbInput
0x180023783  xor     r9d, r9d; dwFlags
0x180023786  mov     r8d, r14d; cbInput
0x180023789  call    cs:__imp_BCryptHashData
0x18002378f  test    eax, eax
0x180023791  jns     short loc_180023796
0x180023793  mov     [rsi], r12b
0x180023796  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x18002379a  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x18002379e  mov     r14d, dword ptr [rbp+80h+pbInput+0Ch]
0x1800237a2  imul    ecx, eax
0x1800237a5  test    ecx, ecx
0x1800237a7  jz      loc_180023879
0x1800237ad  xorps   xmm0, xmm0
0x1800237b0  xor     r9d, r9d; dwMoveMethod
0x1800237b3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800237b6  mov     edx, r14d; lDistanceToMove
0x1800237b9  mov     rcx, r15; hFile
0x1800237bc  movups  xmmword ptr [rbp+80h+var_70], xmm0
0x1800237c0  movups  [rbp+80h+var_60], xmm0
0x1800237c4  call    cs:__imp_SetFilePointer
0x1800237ca  cmp     eax, 0FFFFFFFFh
0x1800237cd  jz      loc_1800238D2
0x1800237d3  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800237d8  mov     qword ptr [rsp+180h+dwCreationDisposition], r12; lpOverlapped
0x1800237dd  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x1800237e3  lea     rdx, [rbp+80h+var_70]; lpBuffer
0x1800237e7  mov     rcx, r15; hFile
0x1800237ea  call    cs:__imp_ReadFile
0x1800237f0  test    eax, eax
0x1800237f2  jz      loc_1800238D2
0x1800237f8  cmp     [rsp+180h+NumberOfBytesRead], 20h ; ' '
0x1800237fd  jnz     loc_1800238D2
0x180023803  mov     eax, dword ptr [rbp+80h+var_70]
0x180023806  mov     [rdi], rax
0x180023809  mov     eax, dword ptr [rbp+80h+var_70+4]
0x18002380c  mov     [rdi+10h], rax
0x180023810  mov     eax, dword ptr [rbp+80h+var_70+8]
0x180023813  mov     [rdi+18h], rax
0x180023817  mov     eax, dword ptr [rbp+80h+var_70+0Ch]
0x18002381a  mov     [rdi+20h], rax
0x18002381e  mov     eax, dword ptr [rbp+80h+var_60]
0x180023821  mov     [rdi+28h], rax
0x180023825  mov     eax, dword ptr [rbp+80h+var_60+4]
0x180023828  mov     [rdi+30h], rax
0x18002382c  mov     eax, dword ptr [rbp+80h+var_60+8]
0x18002382f  mov     [rdi+8], rax
0x180023833  mov     eax, dword ptr [rbp+80h+var_60+0Ch]
0x180023836  mov     [rdi+38h], rax
0x18002383a  add     rdi, 40h ; '@'
0x18002383e  cmp     [rsi], r12b
0x180023841  jz      short loc_18002385F
0x180023843  mov     rcx, [rsi+10h]; hHash
0x180023847  lea     rdx, [rbp+80h+var_70]; pbInput
0x18002384b  xor     r9d, r9d; dwFlags
0x18002384e  lea     r8d, [r9+20h]; cbInput
0x180023852  call    cs:__imp_BCryptHashData
0x180023858  test    eax, eax
0x18002385a  jns     short loc_18002385F
0x18002385c  mov     [rsi], r12b
0x18002385f  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x180023863  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x180023867  add     r14d, eax
0x18002386a  imul    ecx, eax
0x18002386d  add     ecx, dword ptr [rbp+80h+pbInput+0Ch]
0x180023870  cmp     r14d, ecx
0x180023873  jnz     loc_1800237AD
0x180023879  cmp     [rsi], r12b
0x18002387c  jz      short loc_18002389A
0x18002387e  mov     r8d, [rsi+28h]; cbOutput
0x180023882  xor     r9d, r9d; dwFlags
0x180023885  mov     rdx, [rsi+20h]; pbOutput
0x180023889  mov     rcx, [rsi+10h]; hHash
0x18002388d  call    cs:__imp_BCryptFinishHash
0x180023893  test    eax, eax
0x180023895  jns     short loc_1800238DC
0x180023897  mov     [rsi], r12b
0x18002389a  lea     rcx, [rsp+180h+var_138]
0x18002389f  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800238a4  mov     rcx, r15; hObject
0x1800238a7  call    cs:__imp_CloseHandle
0x1800238ad  mov     eax, 80004005h
0x1800238b2  mov     rcx, [rbp+80h+var_50]
0x1800238b6  xor     rcx, rsp; StackCookie
0x1800238b9  call    __security_check_cookie
0x1800238be  add     rsp, 148h
0x1800238c5  pop     r15
0x1800238c7  pop     r14
0x1800238c9  pop     r13
0x1800238cb  pop     r12
0x1800238cd  pop     rdi
0x1800238ce  pop     rsi
0x1800238cf  pop     rbx
0x1800238d0  pop     rbp
0x1800238d1  retn
0x1800238d2  mov     ebx, 80004005h
0x1800238d7  jmp     loc_180023972
0x1800238dc  cmp     [rsi], r12b
0x1800238df  jz      short loc_18002389A
0x1800238e1  cmp     dword ptr [rsi+28h], 10h
0x1800238e5  mov     edi, 10h
0x1800238ea  ja      short loc_1800238EF
0x1800238ec  mov     edi, [rsi+28h]
0x1800238ef  mov     rdx, [rsi+20h]; Src
0x1800238f3  lea     rcx, [r13+8]; void *
0x1800238f7  mov     r8, rdi; Size
0x1800238fa  call    memcpy_0
0x1800238ff  cmp     rdi, 10h
0x180023903  jnz     short loc_18002389A
0x180023905  xor     edx, edx; Val
0x180023907  lea     r8d, [rdi+46h]; Size
0x18002390b  lea     rcx, [rbp+80h+var_CE]; void *
0x18002390f  call    memset_0
0x180023914  mov     rcx, qword ptr [rsp+180h+var_138]
0x180023919  lea     eax, [rdi-0Ch]
0x18002391c  movups  xmm0, cs:ElfImageGuid
0x180023923  mov     [rbp+80h+var_D0], ax
0x180023927  lea     rdx, [rbp+80h+var_D0]
0x18002392b  mov     eax, dword ptr [rsp+180h+var_138+8]
0x18002392f  xor     r9d, r9d
0x180023932  sub     eax, ecx
0x180023934  mov     [rbp+80h+var_88], rcx
0x180023938  mov     rcx, [rsp+180h+var_118]
0x18002393d  xor     r8d, r8d
0x180023940  mov     [rbp+80h+var_80], eax
0x180023943  mov     eax, [rbp+80h+arg_20]
0x180023949  mov     [rbp+80h+var_7C], eax
0x18002394c  mov     rcx, [rcx+10h]
0x180023950  mov     [rbp+80h+var_C0], rbx
0x180023954  movdqu  [rbp+80h+var_B8], xmm0
0x180023959  mov     [rbp+80h+var_CC], r12d
0x18002395d  mov     rax, [rcx]
0x180023960  mov     rax, [rax+0C0h]
0x180023967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002396c  mov     ebx, eax
0x18002396e  test    eax, eax
0x180023970  jns     short loc_18002398C
0x180023972  lea     rcx, [rsp+180h+var_138]
0x180023977  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18002397c  mov     rcx, r15; hObject
0x18002397f  call    cs:__imp_CloseHandle
0x180023985  mov     eax, ebx
  ... truncated ...
```
