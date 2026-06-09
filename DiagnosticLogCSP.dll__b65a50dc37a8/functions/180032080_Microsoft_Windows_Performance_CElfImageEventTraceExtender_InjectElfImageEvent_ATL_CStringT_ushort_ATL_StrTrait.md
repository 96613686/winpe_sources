# Microsoft::Windows::Performance::CElfImageEventTraceExtender::InjectElfImageEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::Windows::Performance::CryptographicHasher &,_LARGE_INTEGER,ulong)

- ea: `0x180032080`
- end: `0x180032577`
- name: `?InjectElfImageEvent@CElfImageEventTraceExtender@Performance@Windows@Microsoft@@EEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCryptographicHasher@234@T_LARGE_INTEGER@@K@Z`
- size: `1271`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001b90`
- `0x180001bb4`
- `0x18000265c`
- `0x180002d19`
- `0x180002d25`
- `0x18000c07c`
- `0x18001fcec`
- `0x18001ff78`
- `0x180032080`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032258`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003245f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003253e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003255e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003245f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003253e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003255e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180032364`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180032364`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800320dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800320dd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032126`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032390`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032126`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032390`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180032270`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180032270`
- `bcrypt!BCryptHashData` at `0x1800322ac`
- `bcrypt!BCryptHashData` at `0x1800322d3`
- `bcrypt!BCryptHashData` at `0x1800322fd`
- `bcrypt!BCryptHashData` at `0x180032323`
- `bcrypt!BCryptHashData` at `0x1800323fe`
- `bcrypt!BCryptHashData` at `0x1800322ac`
- `bcrypt!BCryptHashData` at `0x1800322d3`
- `bcrypt!BCryptHashData` at `0x1800322fd`
- `bcrypt!BCryptHashData` at `0x180032323`
- `bcrypt!BCryptHashData` at `0x1800323fe`
- `bcrypt!BCryptFinishHash` at `0x18003243f`
- `bcrypt!BCryptFinishHash` at `0x18003243f`

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
    || memcmp_0(&Buffer, &qword_18003FA10, 4u)
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
0x180032080  push    rbp
0x180032082  push    rbx
0x180032083  push    rsi
0x180032084  push    rdi
0x180032085  push    r12
0x180032087  push    r13
0x180032089  push    r14
0x18003208b  push    r15
0x18003208d  lea     rbp, [rsp-48h]
0x180032092  sub     rsp, 148h
0x180032099  mov     rax, cs:__security_cookie
0x1800320a0  xor     rax, rsp
0x1800320a3  mov     [rbp+80h+var_50], rax
0x1800320a7  mov     r12, rdx
0x1800320aa  mov     [rsp+180h+var_118], rcx
0x1800320af  xor     r13d, r13d
0x1800320b2  mov     rbx, r9
0x1800320b5  mov     rsi, r8
0x1800320b8  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x1800320bd  mov     [rsp+180h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800320c5  xor     r9d, r9d; lpSecurityAttributes
0x1800320c8  mov     rcx, [r12]; lpFileName
0x1800320cc  mov     edx, 80000000h; dwDesiredAccess
0x1800320d1  lea     r8d, [r13+7]; dwShareMode
0x1800320d5  mov     [rsp+180h+dwCreationDisposition], 3; dwCreationDisposition
0x1800320dd  call    cs:__imp_CreateFileW
0x1800320e4  nop     dword ptr [rax+rax+00h]
0x1800320e9  mov     r15, rax
0x1800320ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800320f0  jz      loc_18003246B
0x1800320f6  xorps   xmm0, xmm0
0x1800320f9  mov     [rsp+180h+NumberOfBytesRead], r13d
0x1800320fe  xor     eax, eax
0x180032100  mov     qword ptr [rsp+180h+dwCreationDisposition], r13; lpOverlapped
0x180032105  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003210a  mov     [rbp+80h+var_E0], eax
0x18003210d  lea     r8d, [r13+34h]; nNumberOfBytesToRead
0x180032111  mov     rcx, r15; hFile
0x180032114  lea     rdx, [rsp+180h+Buffer]; lpBuffer
0x180032119  movups  [rsp+180h+Buffer], xmm0
0x18003211e  movups  xmmword ptr [rbp+80h+pbInput], xmm0
0x180032122  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x180032126  call    cs:__imp_ReadFile
0x18003212d  nop     dword ptr [rax+rax+00h]
0x180032132  test    eax, eax
0x180032134  jz      loc_18003245C
0x18003213a  cmp     [rsp+180h+NumberOfBytesRead], 34h ; '4'
0x18003213f  jnz     loc_18003245C
0x180032145  lea     r8d, [r13+4]; Size
0x180032149  lea     rdx, qword_18003FA10; Buf2
0x180032150  lea     rcx, [rsp+180h+Buffer]; Buf1
0x180032155  call    memcmp_0
0x18003215a  test    eax, eax
0x18003215c  jnz     loc_18003245C
0x180032162  cmp     byte ptr [rsp+180h+Buffer+4], 1
0x180032167  jnz     loc_18003245C
0x18003216d  cmp     byte ptr [rsp+180h+Buffer+5], 1
0x180032172  jnz     loc_18003245C
0x180032178  cmp     byte ptr [rsp+180h+Buffer+6], 1
0x18003217d  jnz     loc_18003245C
0x180032183  lea     eax, [r13+20h]
0x180032187  cmp     ax, word ptr [rbp+80h+var_F0+0Ah]
0x18003218b  jnz     loc_18003245C
0x180032191  mov     rax, [r12]
0x180032195  xorps   xmm0, xmm0
0x180032198  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x18003219c  mov     ecx, edx
0x18003219e  shl     ecx, 5
0x1800321a1  add     ecx, [rax-10h]
0x1800321a4  movdqu  [rsp+180h+var_138], xmm0
0x1800321aa  mov     [rsp+180h+var_128], r13
0x1800321af  lea     eax, ds:5Eh[rcx*2]
0x1800321b6  mov     r14d, eax
0x1800321b9  test    eax, eax
0x1800321bb  jz      short loc_18003222E
0x1800321bd  cmp     r14, 1000h
0x1800321c4  jb      short loc_1800321F3
0x1800321c6  lea     rcx, [rax+27h]; Size
0x1800321ca  cmp     rcx, r14
0x1800321cd  jbe     loc_180032571
0x1800321d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800321d8  mov     rcx, rax
0x1800321db  test    rax, rax
0x1800321de  jnz     short loc_1800321E5
0x1800321e0  lea     ecx, [rax+5]
0x1800321e3  int     29h; Win8: RtlFailFast(ecx)
0x1800321e5  add     rax, 27h ; '''
0x1800321e9  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800321ed  mov     [rax-8], rcx
0x1800321f1  jmp     short loc_1800321FB
0x1800321f3  mov     rcx, r14; Size
0x1800321f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800321fb  lea     rdi, [r14+rax]
0x1800321ff  mov     qword ptr [rsp+180h+var_138], rax
0x180032204  mov     r8, r14; Size
0x180032207  mov     [rsp+180h+var_128], rdi
0x18003220c  xor     edx, edx; Val
0x18003220e  mov     rcx, rax; void *
0x180032211  call    memset_0
0x180032216  lea     rcx, [rsp+180h+var_120]
0x18003221b  mov     qword ptr [rsp+180h+var_138+8], rdi
0x180032220  mov     [rsp+180h+var_120], r13
0x180032225  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18003222a  movzx   edx, word ptr [rbp+80h+var_F0+0Ch]
0x18003222e  mov     rax, [r12]
0x180032232  mov     r13, qword ptr [rsp+180h+var_138]
0x180032237  movzx   ecx, dx
0x18003223a  shl     rcx, 6
0x18003223e  movzx   edx, word ptr [rax-10h]
0x180032242  inc     dx
0x180032245  lea     rdi, [r13+1Ch]
0x180032249  movzx   edx, dx
0x18003224c  add     rcx, rdi
0x18003224f  mov     [r13+1Ah], dx
0x180032254  mov     r8, [r12]
0x180032258  call    cs:__imp__o_wcscpy_s
0x18003225f  nop     dword ptr [rax+rax+00h]
0x180032264  xor     r12d, r12d
0x180032267  xor     edx, edx; lpFileSizeHigh
0x180032269  mov     rcx, r15; hFile
0x18003226c  mov     [r13+0], r12d
0x180032270  call    cs:__imp_GetFileSize
0x180032277  nop     dword ptr [rax+rax+00h]
0x18003227c  mov     [r13+4], eax
0x180032280  cmp     eax, 0FFFFFFFFh
0x180032283  jz      loc_180032452
0x180032289  movzx   eax, word ptr [rbp+80h+var_F0+0Ch]
0x18003228d  mov     [r13+18h], ax
0x180032292  cmp     [rsi], r12b
0x180032295  jz      loc_180032336
0x18003229b  mov     rcx, [rsi+10h]; hHash
0x18003229f  lea     r8d, [r12+10h]; cbInput
0x1800322a4  xor     r9d, r9d; dwFlags
0x1800322a7  lea     rdx, [rsp+180h+Buffer]; pbInput
0x1800322ac  call    cs:__imp_BCryptHashData
0x1800322b3  nop     dword ptr [rax+rax+00h]
0x1800322b8  test    eax, eax
0x1800322ba  jns     short loc_1800322BF
0x1800322bc  mov     [rsi], r12b
0x1800322bf  cmp     [rsi], r12b
0x1800322c2  jz      short loc_180032336
0x1800322c4  mov     rcx, [rsi+10h]; hHash
0x1800322c8  lea     rdx, [rbp+80h+pbInput+2]; pbInput
0x1800322cc  xor     r9d, r9d; dwFlags
0x1800322cf  lea     r8d, [r9+2]; cbInput
0x1800322d3  call    cs:__imp_BCryptHashData
0x1800322da  nop     dword ptr [rax+rax+00h]
0x1800322df  test    eax, eax
0x1800322e1  jns     short loc_1800322E6
0x1800322e3  mov     [rsi], r12b
0x1800322e6  cmp     [rsi], r12b
0x1800322e9  jz      short loc_180032336
0x1800322eb  mov     rcx, [rsi+10h]; hHash
0x1800322ef  lea     rdx, [rbp+80h+pbInput+4]; pbInput
0x1800322f3  xor     r9d, r9d; dwFlags
0x1800322f6  lea     r14d, [r9+4]
0x1800322fa  mov     r8d, r14d; cbInput
0x1800322fd  call    cs:__imp_BCryptHashData
0x180032304  nop     dword ptr [rax+rax+00h]
0x180032309  test    eax, eax
0x18003230b  jns     short loc_180032310
0x18003230d  mov     [rsi], r12b
0x180032310  cmp     [rsi], r12b
0x180032313  jz      short loc_180032336
0x180032315  mov     rcx, [rsi+10h]; hHash
0x180032319  lea     rdx, [rbp+80h+var_F0+4]; pbInput
0x18003231d  xor     r9d, r9d; dwFlags
0x180032320  mov     r8d, r14d; cbInput
0x180032323  call    cs:__imp_BCryptHashData
0x18003232a  nop     dword ptr [rax+rax+00h]
0x18003232f  test    eax, eax
0x180032331  jns     short loc_180032336
0x180032333  mov     [rsi], r12b
0x180032336  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x18003233a  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x18003233e  mov     r14d, dword ptr [rbp+80h+pbInput+0Ch]
0x180032342  imul    ecx, eax
0x180032345  test    ecx, ecx
0x180032347  jz      loc_18003242B
0x18003234d  xorps   xmm0, xmm0
0x180032350  xor     r9d, r9d; dwMoveMethod
0x180032353  xor     r8d, r8d; lpDistanceToMoveHigh
0x180032356  mov     edx, r14d; lDistanceToMove
0x180032359  mov     rcx, r15; hFile
0x18003235c  movups  xmmword ptr [rbp+80h+var_70], xmm0
0x180032360  movups  [rbp+80h+var_60], xmm0
0x180032364  call    cs:__imp_SetFilePointer
0x18003236b  nop     dword ptr [rax+rax+00h]
0x180032370  cmp     eax, 0FFFFFFFFh
0x180032373  jz      loc_180032491
0x180032379  lea     r9, [rsp+180h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003237e  mov     qword ptr [rsp+180h+dwCreationDisposition], r12; lpOverlapped
0x180032383  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x180032389  lea     rdx, [rbp+80h+var_70]; lpBuffer
0x18003238d  mov     rcx, r15; hFile
0x180032390  call    cs:__imp_ReadFile
0x180032397  nop     dword ptr [rax+rax+00h]
0x18003239c  test    eax, eax
0x18003239e  jz      loc_180032491
0x1800323a4  cmp     [rsp+180h+NumberOfBytesRead], 20h ; ' '
0x1800323a9  jnz     loc_180032491
0x1800323af  mov     eax, dword ptr [rbp+80h+var_70]
0x1800323b2  mov     [rdi], rax
0x1800323b5  mov     eax, dword ptr [rbp+80h+var_70+4]
0x1800323b8  mov     [rdi+10h], rax
0x1800323bc  mov     eax, dword ptr [rbp+80h+var_70+8]
0x1800323bf  mov     [rdi+18h], rax
0x1800323c3  mov     eax, dword ptr [rbp+80h+var_70+0Ch]
0x1800323c6  mov     [rdi+20h], rax
0x1800323ca  mov     eax, dword ptr [rbp+80h+var_60]
0x1800323cd  mov     [rdi+28h], rax
0x1800323d1  mov     eax, dword ptr [rbp+80h+var_60+4]
0x1800323d4  mov     [rdi+30h], rax
0x1800323d8  mov     eax, dword ptr [rbp+80h+var_60+8]
0x1800323db  mov     [rdi+8], rax
0x1800323df  mov     eax, dword ptr [rbp+80h+var_60+0Ch]
0x1800323e2  mov     [rdi+38h], rax
0x1800323e6  add     rdi, 40h ; '@'
0x1800323ea  cmp     [rsi], r12b
0x1800323ed  jz      short loc_180032411
0x1800323ef  mov     rcx, [rsi+10h]; hHash
0x1800323f3  lea     rdx, [rbp+80h+var_70]; pbInput
0x1800323f7  xor     r9d, r9d; dwFlags
0x1800323fa  lea     r8d, [r9+20h]; cbInput
0x1800323fe  call    cs:__imp_BCryptHashData
0x180032405  nop     dword ptr [rax+rax+00h]
0x18003240a  test    eax, eax
0x18003240c  jns     short loc_180032411
0x18003240e  mov     [rsi], r12b
0x180032411  movzx   eax, word ptr [rbp+80h+var_F0+0Ah]
0x180032415  movzx   ecx, word ptr [rbp+80h+var_F0+0Ch]
0x180032419  add     r14d, eax
0x18003241c  imul    ecx, eax
0x18003241f  add     ecx, dword ptr [rbp+80h+pbInput+0Ch]
0x180032422  cmp     r14d, ecx
0x180032425  jnz     loc_18003234D
0x18003242b  cmp     [rsi], r12b
0x18003242e  jz      short loc_180032452
0x180032430  mov     r8d, [rsi+28h]; cbOutput
0x180032434  xor     r9d, r9d; dwFlags
0x180032437  mov     rdx, [rsi+20h]; pbOutput
0x18003243b  mov     rcx, [rsi+10h]; hHash
0x18003243f  call    cs:__imp_BCryptFinishHash
0x180032446  nop     dword ptr [rax+rax+00h]
0x18003244b  test    eax, eax
0x18003244d  jns     short loc_18003249B
0x18003244f  mov     [rsi], r12b
0x180032452  lea     rcx, [rsp+180h+var_138]
0x180032457  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18003245c  mov     rcx, r15; hObject
0x18003245f  call    cs:__imp_CloseHandle
0x180032466  nop     dword ptr [rax+rax+00h]
0x18003246b  mov     eax, 80004005h
0x180032470  mov     rcx, [rbp+80h+var_50]
0x180032474  xor     rcx, rsp; StackCookie
0x180032477  call    __security_check_cookie
0x18003247c  add     rsp, 148h
0x180032483  pop     r15
0x180032485  pop     r14
0x180032487  pop     r13
0x180032489  pop     r12
0x18003248b  pop     rdi
0x18003248c  pop     rsi
0x18003248d  pop     rbx
0x18003248e  pop     rbp
0x18003248f  retn
0x180032491  mov     ebx, 80004005h
0x180032496  jmp     loc_180032531
0x18003249b  cmp     [rsi], r12b
0x18003249e  jz      short loc_180032452
0x1800324a0  cmp     dword ptr [rsi+28h], 10h
0x1800324a4  mov     edi, 10h
0x1800324a9  ja      short loc_1800324AE
0x1800324ab  mov     edi, [rsi+28h]
0x1800324ae  mov     rdx, [rsi+20h]; Src
0x1800324b2  lea     rcx, [r13+8]; void *
0x1800324b6  mov     r8, rdi; Size
0x1800324b9  call    memcpy_0
0x1800324be  cmp     rdi, 10h
0x1800324c2  jnz     short loc_180032452
0x1800324c4  xor     edx, edx; Val
0x1800324c6  lea     r8d, [rdi+46h]; Size
0x1800324ca  lea     rcx, [rbp+80h+var_CE]; void *
0x1800324ce  call    memset_0
0x1800324d3  mov     rcx, qword ptr [rsp+180h+var_138]
0x1800324d8  lea     eax, [rdi-0Ch]
0x1800324db  movups  xmm0, cs:ElfImageGuid
0x1800324e2  mov     [rbp+80h+var_D0], ax
0x1800324e6  lea     rdx, [rbp+80h+var_D0]
0x1800324ea  mov     eax, dword ptr [rsp+180h+var_138+8]
0x1800324ee  xor     r9d, r9d
0x1800324f1  sub     eax, ecx
0x1800324f3  mov     [rbp+80h+var_88], rcx
0x1800324f7  mov     rcx, [rsp+180h+var_118]
0x1800324fc  xor     r8d, r8d
0x1800324ff  mov     [rbp+80h+var_80], eax
0x180032502  mov     eax, [rbp+80h+arg_20]
0x180032508  mov     [rbp+80h+var_7C], eax
0x18003250b  mov     rcx, [rcx+10h]
0x18003250f  mov     [rbp+80h+var_C0], rbx
  ... truncated ...
```
