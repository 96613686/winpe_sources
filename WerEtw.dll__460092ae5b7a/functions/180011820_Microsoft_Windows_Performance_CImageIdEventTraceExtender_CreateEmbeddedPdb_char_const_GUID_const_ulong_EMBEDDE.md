# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x180011820`
- end: `0x180011c6b`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, const char *, const struct _GUID *, int, DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x180001870`
- `0x180001894`
- `0x180002670`
- `0x1800027bd`
- `0x180004670`
- `0x180004694`
- `0x18000bea8`
- `0x18000c7d4`
- `0x18000cfe4`
- `0x18000e1cc`
- `0x180011630`
- `0x180011820`
- `0x180011d4c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011b06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011b06`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011874`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800118da`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001191b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180011874`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800118da`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001191b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180011b83`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180011b83`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180011ba0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180011ba0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011ad4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011ad4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011bdb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180011bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011c08`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        const char *a2,
        const struct _GUID *a3,
        int a4,
        DWORD *a5)
{
  _QWORD *v8; // rsi
  LPCWSTR v9; // rbx
  unsigned int Error; // edi
  void (*v11)(void); // rax
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r8
  void **v16; // rdi
  unsigned __int64 v17; // r9
  char *v18; // rbx
  __int64 last_trivial_1; // rax
  __int64 v20; // rax
  void **v21; // rdx
  void *v22; // rcx
  __int64 v23; // rdx
  void **v24; // rbx
  _BYTE *v25; // rbx
  void **v26; // r8
  const WCHAR *v27; // rbx
  HANDLE FileW; // r15
  signed int LastError; // eax
  DWORD v30; // r14d
  LARGE_INTEGER v31; // rdi
  BOOL v32; // eax
  void *v33; // rcx
  char *v34; // r12
  __int64 LowPart; // rax
  LARGE_INTEGER liDistanceToMove; // [rsp+40h] [rbp-41h] BYREF
  LPCWSTR lpPathName; // [rsp+48h] [rbp-39h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-31h] BYREF
  __int128 v39; // [rsp+60h] [rbp-21h]
  __int128 v40; // [rsp+70h] [rbp-11h] BYREF
  __int128 v41; // [rsp+80h] [rbp-1h]

  v8 = (_QWORD *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 328);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0)
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u))
    || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &lpPathName,
          L"\\%hs",
          a2),
        v9 = lpPathName,
        !CreateDirectoryW(lpPathName, 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u))
    || (Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
          v13,
          (unsigned int)&lpPathName,
          *v8,
          (_DWORD)a2,
          (__int64)a3,
          a4),
        v9 = lpPathName,
        !CreateDirectoryW(lpPathName, 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)v9 - 2) > 0 )
      return Error;
    v11 = *(void (**)(void))(**((_QWORD **)v9 - 3) + 8LL);
LABEL_5:
    v11();
    return Error;
  }
  *(_OWORD *)Block = 0;
  v39 = 0u;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::string::_Construct<1,char const *>(Block, a2);
  v16 = Block;
  v17 = *((_QWORD *)&v39 + 1);
  if ( *((_QWORD *)&v39 + 1) > 0xFu )
    v16 = (void **)Block[0];
  if ( !(_QWORD)v39
    || (v18 = (char *)v16 + v39,
        LOBYTE(v15) = 46,
        last_trivial_1 = _std_find_last_trivial_1(v16, (char *)v16 + v39, v15),
        v17 = *((_QWORD *)&v39 + 1),
        (char *)last_trivial_1 == v18) )
  {
    v20 = -1;
  }
  else
  {
    v20 = last_trivial_1 - (_QWORD)v16;
  }
  if ( v20 != -1 )
  {
    v40 = 0;
    v41 = 0u;
    v21 = Block;
    if ( v17 > 0xF )
      v21 = (void **)Block[0];
    std::string::_Construct<1,char const *>(&v40, v21);
    if ( *((_QWORD *)&v39 + 1) > 0xFu )
    {
      if ( (unsigned __int64)(*((_QWORD *)&v39 + 1) + 1LL) < 0x1000 )
      {
        v22 = Block[0];
      }
      else
      {
        v22 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v22 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v22);
    }
    *(_OWORD *)Block = v40;
    v39 = v41;
    *(_QWORD *)&v41 = 0;
    *((_QWORD *)&v41 + 1) = 15;
    LOBYTE(v40) = 0;
    std::string::~string(&v40);
    v17 = *((_QWORD *)&v39 + 1);
  }
  v23 = v39;
  if ( v17 - (unsigned __int64)v39 < 5 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Block, 5u);
  }
  else
  {
    *(_QWORD *)&v39 = v39 + 5;
    v24 = Block;
    if ( v17 > 0xF )
      v24 = (void **)Block[0];
    v25 = (char *)v24 + v23;
    memmove_0(v25, ".cpdb", 5u);
    v25[5] = 0;
  }
  v26 = Block;
  if ( *((_QWORD *)&v39 + 1) > 0xFu )
    v26 = (void **)Block[0];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    v26);
  v27 = lpPathName;
  if ( GetFileAttributesW(lpPathName) == -1 )
  {
    FileW = CreateFileW(v27, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    if ( FileW )
    {
      v30 = *a5;
      liDistanceToMove.QuadPart = *a5;
      v31 = liDistanceToMove;
      v32 = SetFilePointerEx(FileW, liDistanceToMove, 0, 0);
      v33 = FileW;
      if ( v32 )
      {
        SetFilePointer(FileW, 0, 0, 0);
        if ( v30 > 0x10000 )
          v30 = 0x10000;
        v34 = (char *)*((_QWORD *)a5 + 1);
        if ( !v30 )
        {
LABEL_52:
          CloseHandle(FileW);
          goto LABEL_53;
        }
        while ( 1 )
        {
          liDistanceToMove.LowPart = 0;
          if ( !WriteFile(FileW, v34, v30, (LPDWORD)&liDistanceToMove, 0) )
            break;
          LowPart = liDistanceToMove.LowPart;
          v31.QuadPart -= liDistanceToMove.LowPart;
          liDistanceToMove = v31;
          v34 += LowPart;
          v30 = v31.LowPart;
          if ( v31.LowPart <= 0x10000 )
          {
            if ( !v31.LowPart )
              goto LABEL_52;
          }
          else
          {
            v30 = 0x10000;
          }
        }
        v33 = FileW;
      }
      CloseHandle(v33);
      goto LABEL_39;
    }
    if ( GetLastError() != 80 )
    {
LABEL_39:
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      std::string::~string(Block);
      if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) > 0 )
        return Error;
      v11 = *(void (**)(void))(**((_QWORD **)v27 - 3) + 8LL);
      goto LABEL_5;
    }
  }
LABEL_53:
  std::string::~string(Block);
  if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
  return 0;
}

```

## disassembly

```asm
0x180011820  mov     [rsp-8+arg_18], rbx
0x180011825  push    rbp
0x180011826  push    rsi
0x180011827  push    rdi
0x180011828  push    r12
0x18001182a  push    r13
0x18001182c  push    r14
0x18001182e  push    r15
0x180011830  lea     rbp, [rsp-1Fh]
0x180011835  sub     rsp, 0A0h
0x18001183c  mov     rax, cs:__security_cookie
0x180011843  xor     rax, rsp
0x180011846  mov     [rbp+4Fh+var_40], rax
0x18001184a  mov     r15d, r9d
0x18001184d  mov     r12, r8
0x180011850  mov     r14, rdx
0x180011853  mov     r13, [rbp+4Fh+arg_20]
0x180011857  lea     rsi, [rcx+148h]
0x18001185e  mov     rdx, rsi
0x180011861  lea     rcx, [rbp+4Fh+lpPathName]
0x180011865  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001186a  nop
0x18001186b  xor     edx, edx; lpSecurityAttributes
0x18001186d  mov     rbx, [rbp+4Fh+lpPathName]
0x180011871  mov     rcx, rbx; lpPathName
0x180011874  call    cs:__imp_CreateDirectoryW
0x18001187a  test    eax, eax
0x18001187c  jnz     short loc_1800118BE
0x18001187e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011883  mov     edi, eax
0x180011885  mov     ecx, 0B7h; unsigned int
0x18001188a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001188f  cmp     edi, eax
0x180011891  jz      short loc_1800118BE
0x180011893  lea     rdx, [rbx-18h]
0x180011897  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001189b  mov     ecx, esi
0x18001189d  lock xadd [rdx+10h], ecx
0x1800118a2  add     ecx, esi
0x1800118a4  test    ecx, ecx
0x1800118a6  jg      short loc_1800118B7
0x1800118a8  mov     rcx, [rdx]
0x1800118ab  mov     rax, [rcx]
0x1800118ae  mov     rax, [rax+8]
0x1800118b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118b7  mov     eax, edi
0x1800118b9  jmp     loc_180011C3B
0x1800118be  mov     r8, r14
0x1800118c1  lea     rdx, aHs_0; "\\%hs"
0x1800118c8  lea     rcx, [rbp+4Fh+lpPathName]
0x1800118cc  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800118d1  xor     edx, edx; lpSecurityAttributes
0x1800118d3  mov     rbx, [rbp+4Fh+lpPathName]
0x1800118d7  mov     rcx, rbx; lpPathName
0x1800118da  call    cs:__imp_CreateDirectoryW
0x1800118e0  test    eax, eax
0x1800118e2  jnz     short loc_1800118F9
0x1800118e4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800118e9  mov     edi, eax
0x1800118eb  mov     ecx, 0B7h; unsigned int
0x1800118f0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800118f5  cmp     edi, eax
0x1800118f7  jnz     short loc_180011893
0x1800118f9  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d
0x1800118fe  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r12
0x180011903  mov     r9, r14
0x180011906  mov     r8, [rsi]
0x180011909  lea     rdx, [rbp+4Fh+lpPathName]
0x18001190d  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x180011912  xor     edx, edx; lpSecurityAttributes
0x180011914  mov     rbx, [rbp+4Fh+lpPathName]
0x180011918  mov     rcx, rbx; lpPathName
0x18001191b  call    cs:__imp_CreateDirectoryW
0x180011921  xor     r12d, r12d
0x180011924  test    eax, eax
0x180011926  jnz     short loc_180011941
0x180011928  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001192d  mov     edi, eax
0x18001192f  mov     ecx, 0B7h; unsigned int
0x180011934  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180011939  cmp     edi, eax
0x18001193b  jnz     loc_180011893
0x180011941  xorps   xmm0, xmm0
0x180011944  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x180011948  mov     qword ptr [rbp+4Fh+var_70], r12
0x18001194c  mov     qword ptr [rbp+4Fh+var_70+8], r12
0x180011950  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011954  mov     r8, rsi
0x180011957  inc     r8
0x18001195a  cmp     [r14+r8], r12b
0x18001195e  jnz     short loc_180011957
0x180011960  mov     rdx, r14
0x180011963  lea     rcx, [rbp+4Fh+Block]
0x180011967  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001196c  nop
0x18001196d  mov     rax, qword ptr [rbp+4Fh+var_70]
0x180011971  lea     rdi, [rbp+4Fh+Block]
0x180011975  mov     r9, qword ptr [rbp+4Fh+var_70+8]
0x180011979  mov     r14d, 0Fh
0x18001197f  cmp     r9, r14
0x180011982  cmova   rdi, [rbp+4Fh+Block]
0x180011987  test    rax, rax
0x18001198a  jz      short loc_1800119B9
0x18001198c  dec     rax
0x18001198f  cmp     rax, rsi
0x180011992  cmovnb  rax, rsi
0x180011996  lea     rbx, [rax+1]
0x18001199a  add     rbx, rdi
0x18001199d  mov     r8b, 2Eh ; '.'
0x1800119a0  mov     rdx, rbx
0x1800119a3  mov     rcx, rdi
0x1800119a6  call    __std_find_last_trivial_1
0x1800119ab  mov     r9, qword ptr [rbp+4Fh+var_70+8]
0x1800119af  cmp     rax, rbx
0x1800119b2  jz      short loc_1800119B9
0x1800119b4  sub     rax, rdi
0x1800119b7  jmp     short loc_1800119BC
0x1800119b9  mov     rax, rsi
0x1800119bc  cmp     rax, rsi
0x1800119bf  jz      loc_180011A5C
0x1800119c5  xorps   xmm0, xmm0
0x1800119c8  movups  [rbp+4Fh+var_60], xmm0
0x1800119cc  mov     qword ptr [rbp+4Fh+var_50], r12
0x1800119d0  mov     qword ptr [rbp+4Fh+var_50+8], r12
0x1800119d4  mov     r8, qword ptr [rbp+4Fh+var_70]
0x1800119d8  cmp     r8, rax
0x1800119db  cmovnb  r8, rax
0x1800119df  lea     rdx, [rbp+4Fh+Block]
0x1800119e3  cmp     r9, r14
0x1800119e6  cmova   rdx, [rbp+4Fh+Block]
0x1800119eb  lea     rcx, [rbp+4Fh+var_60]
0x1800119ef  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800119f4  mov     rdx, qword ptr [rbp+4Fh+var_70+8]
0x1800119f8  cmp     rdx, r14
0x1800119fb  jbe     short loc_180011A33
0x1800119fd  mov     rax, [rbp+4Fh+Block]
0x180011a01  inc     rdx
0x180011a04  cmp     rdx, 1000h
0x180011a0b  jb      short loc_180011A2B
0x180011a0d  mov     rcx, [rax-8]
0x180011a11  sub     rax, rcx
0x180011a14  sub     rax, 8
0x180011a18  cmp     rax, 1Fh
0x180011a1c  ja      short loc_180011A24
0x180011a1e  add     rdx, 27h ; '''
0x180011a22  jmp     short loc_180011A2E
0x180011a24  mov     ecx, 5
0x180011a29  int     29h; Win8: RtlFailFast(ecx)
0x180011a2b  mov     rcx, rax; Block
0x180011a2e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011a33  movups  xmm0, [rbp+4Fh+var_60]
0x180011a37  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x180011a3b  movups  xmm1, [rbp+4Fh+var_50]
0x180011a3f  movups  [rbp+4Fh+var_70], xmm1
0x180011a43  mov     qword ptr [rbp+4Fh+var_50], r12
0x180011a47  mov     qword ptr [rbp+4Fh+var_50+8], r14
0x180011a4b  mov     byte ptr [rbp+4Fh+var_60], r12b
0x180011a4f  lea     rcx, [rbp+4Fh+var_60]
0x180011a53  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180011a58  mov     r9, qword ptr [rbp+4Fh+var_70+8]
0x180011a5c  mov     rdx, qword ptr [rbp+4Fh+var_70]
0x180011a60  mov     rax, r9
0x180011a63  sub     rax, rdx
0x180011a66  mov     ecx, 5
0x180011a6b  cmp     rax, rcx
0x180011a6e  jb      short loc_180011A9F
0x180011a70  lea     rax, [rdx+5]
0x180011a74  mov     qword ptr [rbp+4Fh+var_70], rax
0x180011a78  lea     rbx, [rbp+4Fh+Block]
0x180011a7c  cmp     r9, r14
0x180011a7f  cmova   rbx, [rbp+4Fh+Block]
0x180011a84  add     rbx, rdx
0x180011a87  mov     r8d, ecx; Size
0x180011a8a  lea     rdx, aCpdb; ".cpdb"
0x180011a91  mov     rcx, rbx; void *
0x180011a94  call    memmove_0
0x180011a99  mov     [rbx+5], r12b
0x180011a9d  jmp     short loc_180011AB0
0x180011a9f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx; Size
0x180011aa4  mov     rdx, rcx
0x180011aa7  lea     rcx, [rbp+4Fh+Block]; Src
0x180011aab  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180011ab0  lea     r8, [rbp+4Fh+Block]
0x180011ab4  cmp     qword ptr [rbp+4Fh+var_70+8], r14
0x180011ab8  cmova   r8, [rbp+4Fh+Block]
0x180011abd  lea     rdx, aHs_0; "\\%hs"
0x180011ac4  lea     rcx, [rbp+4Fh+lpPathName]
0x180011ac8  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180011acd  mov     rbx, [rbp+4Fh+lpPathName]
0x180011ad1  mov     rcx, rbx; lpFileName
0x180011ad4  call    cs:__imp_GetFileAttributesW
0x180011ada  cmp     eax, 0FFFFFFFFh
0x180011add  jnz     loc_180011C0F
0x180011ae3  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x180011ae8  mov     [rsp+0D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180011af0  mov     [rsp+0D0h+dwCreationDisposition], 1; dwCreationDisposition
0x180011af8  xor     r9d, r9d; lpSecurityAttributes
0x180011afb  xor     r8d, r8d; dwShareMode
0x180011afe  mov     edx, 40000000h; dwDesiredAccess
0x180011b03  mov     rcx, rbx; lpFileName
0x180011b06  call    cs:__imp_CreateFileW
0x180011b0c  mov     r15, rax
0x180011b0f  test    rax, rax
0x180011b12  jnz     short loc_180011B66
0x180011b14  call    cs:__imp_GetLastError
0x180011b1a  cmp     eax, 50h ; 'P'
0x180011b1d  jz      loc_180011C0F
0x180011b23  call    cs:__imp_GetLastError
0x180011b29  test    eax, eax
0x180011b2b  mov     edi, eax
0x180011b2d  jle     short loc_180011B38
0x180011b2f  movzx   edi, ax
0x180011b32  or      edi, 80070000h
0x180011b38  lea     rcx, [rbp+4Fh+Block]
0x180011b3c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180011b41  nop
0x180011b42  lea     rdx, [rbx-18h]
0x180011b46  mov     ecx, esi
0x180011b48  lock xadd [rdx+10h], ecx
0x180011b4d  add     ecx, esi
0x180011b4f  test    ecx, ecx
0x180011b51  jg      loc_1800118B7
0x180011b57  mov     rcx, [rdx]
0x180011b5a  mov     r8, [rcx]
0x180011b5d  mov     rax, [r8+8]
0x180011b61  jmp     loc_1800118B2
0x180011b66  mov     r14d, [r13+0]
0x180011b6a  mov     dword ptr [rbp+4Fh+liDistanceToMove], r14d
0x180011b6e  xor     eax, eax
0x180011b70  mov     dword ptr [rbp+4Fh+liDistanceToMove+4], eax
0x180011b73  xor     r9d, r9d; dwMoveMethod
0x180011b76  xor     r8d, r8d; lpNewFilePointer
0x180011b79  mov     rdi, qword ptr [rbp+4Fh+liDistanceToMove]
0x180011b7d  mov     rdx, rdi; liDistanceToMove
0x180011b80  mov     rcx, r15; hFile
0x180011b83  call    cs:__imp_SetFilePointerEx
0x180011b89  mov     rcx, r15; hFile
0x180011b8c  test    eax, eax
0x180011b8e  jnz     short loc_180011B98
0x180011b90  call    cs:__imp_CloseHandle
0x180011b96  jmp     short loc_180011B23
0x180011b98  xor     r9d, r9d; dwMoveMethod
0x180011b9b  xor     r8d, r8d; lpDistanceToMoveHigh
0x180011b9e  xor     edx, edx; lDistanceToMove
0x180011ba0  call    cs:__imp_SetFilePointer
0x180011ba6  mov     eax, 10000h
0x180011bab  cmp     r14d, eax
0x180011bae  cmova   r14d, eax
0x180011bb2  mov     r12, [r13+8]
0x180011bb6  test    r14d, r14d
0x180011bb9  jz      short loc_180011C05
0x180011bbb  mov     r13d, eax
0x180011bbe  mov     dword ptr [rbp+4Fh+liDistanceToMove], 0
0x180011bc5  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x180011bce  lea     r9, [rbp+4Fh+liDistanceToMove]; lpNumberOfBytesWritten
0x180011bd2  mov     r8d, r14d; nNumberOfBytesToWrite
0x180011bd5  mov     rdx, r12; lpBuffer
0x180011bd8  mov     rcx, r15; hFile
0x180011bdb  call    cs:__imp_WriteFile
0x180011be1  test    eax, eax
0x180011be3  jz      short loc_180011C62
0x180011be5  mov     eax, dword ptr [rbp+4Fh+liDistanceToMove]
0x180011be8  sub     rdi, rax
0x180011beb  mov     qword ptr [rbp+4Fh+liDistanceToMove], rdi
0x180011bef  add     r12, rax
0x180011bf2  mov     r14d, dword ptr [rbp+4Fh+liDistanceToMove]
0x180011bf6  cmp     r14d, r13d
0x180011bf9  jbe     short loc_180011C00
0x180011bfb  mov     r14d, r13d
0x180011bfe  jmp     short loc_180011BBE
0x180011c00  test    r14d, r14d
0x180011c03  jnz     short loc_180011BBE
0x180011c05  mov     rcx, r15; hObject
0x180011c08  call    cs:__imp_CloseHandle
0x180011c0e  nop
0x180011c0f  lea     rcx, [rbp+4Fh+Block]
0x180011c13  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180011c18  nop
0x180011c19  lea     rdx, [rbx-18h]
0x180011c1d  mov     eax, esi
0x180011c1f  lock xadd [rdx+10h], eax
0x180011c24  add     eax, esi
0x180011c26  test    eax, eax
0x180011c28  jg      short loc_180011C39
0x180011c2a  mov     rcx, [rdx]
0x180011c2d  mov     rax, [rcx]
0x180011c30  mov     rax, [rax+8]
0x180011c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c39  xor     eax, eax
0x180011c3b  mov     rcx, [rbp+4Fh+var_40]
0x180011c3f  xor     rcx, rsp; StackCookie
0x180011c42  call    __security_check_cookie
0x180011c47  mov     rbx, [rsp+0D0h+arg_18]
0x180011c4f  add     rsp, 0A0h
0x180011c56  pop     r15
0x180011c58  pop     r14
0x180011c5a  pop     r13
0x180011c5c  pop     r12
0x180011c5e  pop     rdi
0x180011c5f  pop     rsi
  ... truncated ...
```
