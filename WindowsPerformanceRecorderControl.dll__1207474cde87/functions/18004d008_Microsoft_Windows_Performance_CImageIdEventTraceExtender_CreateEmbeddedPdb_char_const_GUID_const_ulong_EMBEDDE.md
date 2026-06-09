# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x18004d008`
- end: `0x18004d350`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, const char *, const struct _GUID *, unsigned int, const struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027e60`

## callees

- `0x18000829c`
- `0x180008330`
- `0x1800128f8`
- `0x180021810`
- `0x18004b39c`
- `0x18004d008`
- `0x18004d358`
- `0x18004ece0`
- `0x180076bbc`
- `0x180076c3c`
- `0x180077df4`
- `0x180082920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d25f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d25f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d315`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004d242`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004d242`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d05c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d098`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d0da`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d05c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d098`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004d0da`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004d29e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004d29e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004d2f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004d2f4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004d20b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004d20b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004d2bb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004d2bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
        const void **this,
        const char *a2,
        const struct _GUID *a3,
        int a4,
        DWORD *a5)
{
  _QWORD *v8; // rsi
  unsigned int Error; // ebx
  int v10; // ecx
  __int64 v11; // r8
  __int128 *p_Src; // rdi
  char *v13; // rbx
  __int64 traits_1_0_unsigned_char; // rax
  __int128 *v15; // rdx
  __int128 *v16; // r8
  HANDLE FileW; // rsi
  signed int LastError; // eax
  DWORD LowPart; // edi
  LARGE_INTEGER v20; // rbx
  BOOL v21; // eax
  void *v22; // rcx
  char *v23; // r14
  LPCWSTR lpPathName; // [rsp+40h] [rbp-51h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-49h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+50h] [rbp-41h]
  __int64 v28; // [rsp+58h] [rbp-39h]
  __int128 Src; // [rsp+60h] [rbp-31h] BYREF
  __m128i v30; // [rsp+70h] [rbp-21h]
  __int128 v31; // [rsp+80h] [rbp-11h] BYREF
  __m128i si128; // [rsp+90h] [rbp-1h]

  v28 = -2;
  v8 = this + 41;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    this + 41);
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    a2);
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v10,
    (unsigned int)&lpPathName,
    *v8,
    (_DWORD)a2,
    (__int64)a3,
    a4);
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u) )
      goto LABEL_36;
  }
  Src = 0;
  v30 = 0u;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  std::string::_Construct<1,char const *>(&Src, a2);
  p_Src = &Src;
  if ( v30.m128i_i64[1] > 0xFuLL )
    p_Src = (__int128 *)Src;
  if ( v30.m128i_i64[0] )
  {
    v13 = (char *)p_Src + v30.m128i_i64[0];
    traits_1_0_unsigned_char = anonymous_namespace_::_Finding::_Find_last_impl__anonymous_namespace_::_Finding::_Find_traits_1_0_unsigned_char_(
                                 p_Src,
                                 (char *)p_Src + v30.m128i_i64[0]);
    if ( (char *)traits_1_0_unsigned_char != v13 && traits_1_0_unsigned_char - (_QWORD)p_Src != -1 )
    {
      v31 = 0;
      si128 = 0;
      v15 = &Src;
      if ( v30.m128i_i64[1] > 0xFuLL )
        v15 = (__int128 *)Src;
      std::string::_Construct<1,char const *>(&v31, v15);
      std::string::_Tidy_deallocate(&Src);
      Src = v31;
      v30 = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v31) = 0;
      std::string::_Tidy_deallocate(&v31);
    }
  }
  std::string::_Append<char>(&Src);
  v16 = &Src;
  if ( v30.m128i_i64[1] > 0xFuLL )
    v16 = (__int128 *)Src;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    v16);
  if ( GetFileAttributesW(lpPathName) != -1 )
    goto LABEL_35;
  FileW = CreateFileW(lpPathName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( FileW )
  {
    LowPart = *a5;
    liDistanceToMove.QuadPart = *a5;
    v20 = liDistanceToMove;
    v21 = SetFilePointerEx(FileW, liDistanceToMove, 0, 0);
    v22 = FileW;
    if ( !v21 )
    {
LABEL_26:
      CloseHandle(v22);
      goto LABEL_22;
    }
    SetFilePointer(FileW, 0, 0, 0);
    v23 = (char *)*((_QWORD *)a5 + 1);
    while ( 1 )
    {
      if ( LowPart > 0x10000 )
        LowPart = 0x10000;
      if ( !LowPart )
        break;
      NumberOfBytesWritten = 0;
      if ( !WriteFile(FileW, v23, LowPart, &NumberOfBytesWritten, 0) )
      {
        v22 = FileW;
        goto LABEL_26;
      }
      v20.QuadPart -= NumberOfBytesWritten;
      liDistanceToMove = v20;
      v23 += NumberOfBytesWritten;
      LowPart = v20.LowPart;
    }
    CloseHandle(FileW);
LABEL_35:
    std::string::_Tidy_deallocate(&Src);
    Error = 0;
    goto LABEL_36;
  }
  if ( GetLastError() == 80 )
    goto LABEL_35;
LABEL_22:
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  std::string::_Tidy_deallocate(&Src);
LABEL_36:
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpPathName);
  return Error;
}

```

## disassembly

```asm
0x18004d008  push    rbp
0x18004d00a  push    rbx
0x18004d00b  push    rsi
0x18004d00c  push    rdi
0x18004d00d  push    r12
0x18004d00f  push    r14
0x18004d011  push    r15
0x18004d013  lea     rbp, [rsp-1Fh]
0x18004d018  sub     rsp, 0B0h
0x18004d01f  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x18004d027  mov     rax, cs:__security_cookie
0x18004d02e  xor     rax, rsp
0x18004d031  mov     [rbp+4Fh+var_40], rax
0x18004d035  mov     r14d, r9d
0x18004d038  mov     r15, r8
0x18004d03b  mov     rdi, rdx
0x18004d03e  mov     r12, [rbp+4Fh+arg_20]
0x18004d042  lea     rsi, [rcx+148h]
0x18004d049  mov     rdx, rsi; void *
0x18004d04c  lea     rcx, [rbp+4Fh+lpPathName]; void *
0x18004d050  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004d055  nop
0x18004d056  xor     edx, edx; lpSecurityAttributes
0x18004d058  mov     rcx, [rbp+4Fh+lpPathName]; lpPathName
0x18004d05c  call    cs:__imp_CreateDirectoryW
0x18004d062  test    eax, eax
0x18004d064  jnz     short loc_18004D07F
0x18004d066  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004d06b  mov     ebx, eax
0x18004d06d  mov     ecx, 0B7h; unsigned int
0x18004d072  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004d077  cmp     ebx, eax
0x18004d079  jnz     loc_18004D327
0x18004d07f  mov     r8, rdi
0x18004d082  lea     rdx, aHs_0; "\\%hs"
0x18004d089  lea     rcx, [rbp+4Fh+lpPathName]
0x18004d08d  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18004d092  xor     edx, edx; lpSecurityAttributes
0x18004d094  mov     rcx, [rbp+4Fh+lpPathName]; lpPathName
0x18004d098  call    cs:__imp_CreateDirectoryW
0x18004d09e  test    eax, eax
0x18004d0a0  jnz     short loc_18004D0BB
0x18004d0a2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004d0a7  mov     ebx, eax
0x18004d0a9  mov     ecx, 0B7h; unsigned int
0x18004d0ae  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004d0b3  cmp     ebx, eax
0x18004d0b5  jnz     loc_18004D327
0x18004d0bb  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d
0x18004d0c0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r15
0x18004d0c5  mov     r9, rdi
0x18004d0c8  mov     r8, [rsi]
0x18004d0cb  lea     rdx, [rbp+4Fh+lpPathName]
0x18004d0cf  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x18004d0d4  xor     edx, edx; lpSecurityAttributes
0x18004d0d6  mov     rcx, [rbp+4Fh+lpPathName]; lpPathName
0x18004d0da  call    cs:__imp_CreateDirectoryW
0x18004d0e0  test    eax, eax
0x18004d0e2  jnz     short loc_18004D0FD
0x18004d0e4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004d0e9  mov     ebx, eax
0x18004d0eb  mov     ecx, 0B7h; unsigned int
0x18004d0f0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004d0f5  cmp     ebx, eax
0x18004d0f7  jnz     loc_18004D327
0x18004d0fd  xorps   xmm0, xmm0
0x18004d100  movups  [rbp+4Fh+Src], xmm0
0x18004d104  mov     qword ptr [rbp+4Fh+var_70], 0
0x18004d10c  mov     qword ptr [rbp+4Fh+var_70+8], 0
0x18004d114  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004d118  mov     r8, rsi
0x18004d11b  inc     r8
0x18004d11e  cmp     byte ptr [rdi+r8], 0
0x18004d123  jnz     short loc_18004D11B
0x18004d125  mov     rdx, rdi
0x18004d128  lea     rcx, [rbp+4Fh+Src]
0x18004d12c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004d131  nop
0x18004d132  mov     rax, qword ptr [rbp+4Fh+var_70]
0x18004d136  lea     rdi, [rbp+4Fh+Src]
0x18004d13a  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x18004d13f  cmova   rdi, qword ptr [rbp+4Fh+Src]
0x18004d144  test    rax, rax
0x18004d147  jz      loc_18004D1DA
0x18004d14d  dec     rax
0x18004d150  cmp     rax, rsi
0x18004d153  cmovnb  rax, rsi
0x18004d157  lea     rbx, [rdi+1]
0x18004d15b  add     rbx, rax
0x18004d15e  mov     rdx, rbx
0x18004d161  mov     rcx, rdi
0x18004d164  call    _anonymous_namespace____Finding___Find_last_impl__anonymous_namespace____Finding___Find_traits_1_0_unsigned_char_
0x18004d169  cmp     rax, rbx
0x18004d16c  jz      short loc_18004D1DA
0x18004d16e  sub     rax, rdi
0x18004d171  cmp     rax, rsi
0x18004d174  jz      short loc_18004D1DA
0x18004d176  xorps   xmm0, xmm0
0x18004d179  movups  [rbp+4Fh+var_60], xmm0
0x18004d17d  xorps   xmm1, xmm1
0x18004d180  movdqu  [rbp+4Fh+var_50], xmm1
0x18004d185  mov     r8, qword ptr [rbp+4Fh+var_70]
0x18004d189  cmp     r8, rax
0x18004d18c  cmovnb  r8, rax
0x18004d190  lea     rdx, [rbp+4Fh+Src]
0x18004d194  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x18004d199  cmova   rdx, qword ptr [rbp+4Fh+Src]
0x18004d19e  lea     rcx, [rbp+4Fh+var_60]
0x18004d1a2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004d1a7  lea     rcx, [rbp+4Fh+Src]
0x18004d1ab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004d1b0  movups  xmm0, [rbp+4Fh+var_60]
0x18004d1b4  movups  [rbp+4Fh+Src], xmm0
0x18004d1b8  movups  xmm1, [rbp+4Fh+var_50]
0x18004d1bc  movups  [rbp+4Fh+var_70], xmm1
0x18004d1c0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18004d1c8  movdqu  [rbp+4Fh+var_50], xmm0
0x18004d1cd  mov     byte ptr [rbp+4Fh+var_60], 0
0x18004d1d1  lea     rcx, [rbp+4Fh+var_60]
0x18004d1d5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004d1da  mov     r8d, 5
0x18004d1e0  lea     rcx, [rbp+4Fh+Src]; Src
0x18004d1e4  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x18004d1e9  lea     r8, [rbp+4Fh+Src]
0x18004d1ed  cmp     qword ptr [rbp+4Fh+var_70+8], 0Fh
0x18004d1f2  cmova   r8, qword ptr [rbp+4Fh+Src]
0x18004d1f7  lea     rdx, aHs_0; "\\%hs"
0x18004d1fe  lea     rcx, [rbp+4Fh+lpPathName]
0x18004d202  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18004d207  mov     rcx, [rbp+4Fh+lpPathName]; lpFileName
0x18004d20b  call    cs:__imp_GetFileAttributesW
0x18004d211  cmp     eax, 0FFFFFFFFh
0x18004d214  jnz     loc_18004D31C
0x18004d21a  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18004d223  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004d22b  mov     [rsp+0E0h+dwCreationDisposition], 1; dwCreationDisposition
0x18004d233  xor     r9d, r9d; lpSecurityAttributes
0x18004d236  xor     r8d, r8d; dwShareMode
0x18004d239  mov     edx, 40000000h; dwDesiredAccess
0x18004d23e  mov     rcx, [rbp+4Fh+lpPathName]; lpFileName
0x18004d242  call    cs:__imp_CreateFileW
0x18004d248  mov     rsi, rax
0x18004d24b  test    rax, rax
0x18004d24e  jnz     short loc_18004D282
0x18004d250  call    cs:__imp_GetLastError
0x18004d256  cmp     eax, 50h ; 'P'
0x18004d259  jz      loc_18004D31C
0x18004d25f  call    cs:__imp_GetLastError
0x18004d265  test    eax, eax
0x18004d267  mov     ebx, eax
0x18004d269  jle     short loc_18004D274
0x18004d26b  movzx   ebx, ax
0x18004d26e  or      ebx, 80070000h
0x18004d274  lea     rcx, [rbp+4Fh+Src]
0x18004d278  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004d27d  jmp     loc_18004D327
0x18004d282  mov     edi, [r12]
0x18004d286  mov     dword ptr [rbp+4Fh+liDistanceToMove], edi
0x18004d289  xor     eax, eax
0x18004d28b  mov     dword ptr [rbp+4Fh+liDistanceToMove+4], eax
0x18004d28e  xor     r9d, r9d; dwMoveMethod
0x18004d291  xor     r8d, r8d; lpNewFilePointer
0x18004d294  mov     rbx, qword ptr [rbp+4Fh+liDistanceToMove]
0x18004d298  mov     rdx, rbx; liDistanceToMove
0x18004d29b  mov     rcx, rsi; hFile
0x18004d29e  call    cs:__imp_SetFilePointerEx
0x18004d2a4  mov     rcx, rsi; hFile
0x18004d2a7  test    eax, eax
0x18004d2a9  jnz     short loc_18004D2B3
0x18004d2ab  call    cs:__imp_CloseHandle
0x18004d2b1  jmp     short loc_18004D25F
0x18004d2b3  xor     r9d, r9d; dwMoveMethod
0x18004d2b6  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004d2b9  xor     edx, edx; lDistanceToMove
0x18004d2bb  call    cs:__imp_SetFilePointer
0x18004d2c1  mov     r15d, 10000h
0x18004d2c7  mov     r14, [r12+8]
0x18004d2cc  cmp     edi, r15d
0x18004d2cf  cmova   edi, r15d
0x18004d2d3  mov     rcx, rsi; hObject
0x18004d2d6  test    edi, edi
0x18004d2d8  jz      short loc_18004D315
0x18004d2da  mov     [rbp+4Fh+NumberOfBytesWritten], 0
0x18004d2e1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18004d2ea  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004d2ee  mov     r8d, edi; nNumberOfBytesToWrite
0x18004d2f1  mov     rdx, r14; lpBuffer
0x18004d2f4  call    cs:__imp_WriteFile
0x18004d2fa  test    eax, eax
0x18004d2fc  jz      short loc_18004D310
0x18004d2fe  mov     eax, [rbp+4Fh+NumberOfBytesWritten]
0x18004d301  sub     rbx, rax
0x18004d304  mov     qword ptr [rbp+4Fh+liDistanceToMove], rbx
0x18004d308  add     r14, rax
0x18004d30b  mov     edi, dword ptr [rbp+4Fh+liDistanceToMove]
0x18004d30e  jmp     short loc_18004D2CC
0x18004d310  mov     rcx, rsi
0x18004d313  jmp     short loc_18004D2AB
0x18004d315  call    cs:__imp_CloseHandle
0x18004d31b  nop
0x18004d31c  lea     rcx, [rbp+4Fh+Src]
0x18004d320  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004d325  xor     ebx, ebx
0x18004d327  lea     rcx, [rbp+4Fh+lpPathName]; this
0x18004d32b  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18004d330  mov     eax, ebx
0x18004d332  mov     rcx, [rbp+4Fh+var_40]
0x18004d336  xor     rcx, rsp; StackCookie
0x18004d339  call    __security_check_cookie
0x18004d33e  add     rsp, 0B0h
0x18004d345  pop     r15
0x18004d347  pop     r14
0x18004d349  pop     r12
0x18004d34b  pop     rdi
0x18004d34c  pop     rsi
0x18004d34d  pop     rbx
0x18004d34e  pop     rbp
0x18004d34f  retn
```
