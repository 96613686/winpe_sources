# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x180022450`
- end: `0x18002289b`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, const char *, const struct _GUID *, int, DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020204`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x180002a90`
- `0x180002d01`
- `0x180015710`
- `0x180015734`
- `0x18001cdc8`
- `0x18001d5fc`
- `0x18001dccc`
- `0x18001edec`
- `0x180022240`
- `0x180022450`
- `0x18002297c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800227c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022838`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800224a4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002250a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002254b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800224a4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002250a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002254b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800227d0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800227d0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002280b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002280b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022736`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022736`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800227b3`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800227b3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022704`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022704`

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
  const WCHAR *v31; // rdi
  BOOL v32; // eax
  void *v33; // rcx
  char *v34; // r12
  __int64 v35; // rax
  LPCWSTR lpPathName; // [rsp+40h] [rbp-31h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-29h] BYREF
  __int128 v38; // [rsp+58h] [rbp-19h]
  __int128 v39; // [rsp+68h] [rbp-9h] BYREF
  __int128 v40; // [rsp+78h] [rbp+7h]

  v8 = (_QWORD *)((char *)this + 328);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 328);
  v9 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0)
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(183))
    || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &lpPathName,
          L"\\%hs",
          a2),
        v9 = lpPathName,
        !CreateDirectoryW(lpPathName, 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(183))
    || (Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
          v13,
          (unsigned int)&lpPathName,
          *v8,
          (_DWORD)a2,
          (__int64)a3,
          a4),
        v9 = lpPathName,
        !CreateDirectoryW(lpPathName, 0))
    && (Error = ATL::AtlHresultFromLastError(), Error != (unsigned int)ATL::AtlHresultFromWin32(183)) )
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)v9 - 2) > 0 )
      return Error;
    v11 = *(void (**)(void))(**((_QWORD **)v9 - 3) + 8LL);
LABEL_5:
    v11();
    return Error;
  }
  *(_OWORD *)Src = 0;
  v38 = 0u;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::string::_Construct<1,char const *>(Src, a2);
  v16 = Src;
  v17 = *((_QWORD *)&v38 + 1);
  if ( *((_QWORD *)&v38 + 1) > 0xFu )
    v16 = (void **)Src[0];
  if ( !(_QWORD)v38
    || (v18 = (char *)v16 + v38,
        LOBYTE(v15) = 46,
        last_trivial_1 = _std_find_last_trivial_1(v16, (char *)v16 + v38, v15),
        v17 = *((_QWORD *)&v38 + 1),
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
    v39 = 0;
    v40 = 0u;
    v21 = Src;
    if ( v17 > 0xF )
      v21 = (void **)Src[0];
    std::string::_Construct<1,char const *>(&v39, v21);
    if ( *((_QWORD *)&v38 + 1) > 0xFu )
    {
      if ( (unsigned __int64)(*((_QWORD *)&v38 + 1) + 1LL) < 0x1000 )
      {
        v22 = Src[0];
      }
      else
      {
        v22 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v22 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v22);
    }
    *(_OWORD *)Src = v39;
    v38 = v40;
    *(_QWORD *)&v40 = 0;
    *((_QWORD *)&v40 + 1) = 15;
    LOBYTE(v39) = 0;
    std::string::~string(&v39);
    v17 = *((_QWORD *)&v38 + 1);
  }
  v23 = v38;
  if ( v17 - (unsigned __int64)v38 < 5 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 5u);
  }
  else
  {
    *(_QWORD *)&v38 = v38 + 5;
    v24 = Src;
    if ( v17 > 0xF )
      v24 = (void **)Src[0];
    v25 = (char *)v24 + v23;
    memmove_0(v25, ".cpdb", 5u);
    v25[5] = 0;
  }
  v26 = Src;
  if ( *((_QWORD *)&v38 + 1) > 0xFu )
    v26 = (void **)Src[0];
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
      lpPathName = (LPCWSTR)*a5;
      v31 = lpPathName;
      v32 = SetFilePointerEx(FileW, (LARGE_INTEGER)lpPathName, 0, 0);
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
          LODWORD(lpPathName) = 0;
          if ( !WriteFile(FileW, v34, v30, (LPDWORD)&lpPathName, 0) )
            break;
          v35 = (unsigned int)lpPathName;
          v31 = (const WCHAR *)((char *)v31 - (unsigned int)lpPathName);
          lpPathName = v31;
          v34 += v35;
          v30 = (unsigned int)v31;
          if ( (unsigned int)v31 <= 0x10000 )
          {
            if ( !(_DWORD)v31 )
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
      std::string::~string(Src);
      if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) > 0 )
        return Error;
      v11 = *(void (**)(void))(**((_QWORD **)v27 - 3) + 8LL);
      goto LABEL_5;
    }
  }
LABEL_53:
  std::string::~string(Src);
  if ( _InterlockedDecrement((volatile signed __int32 *)v27 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
  return 0;
}

```

## disassembly

```asm
0x180022450  mov     [rsp-8+arg_18], rbx
0x180022455  push    rbp
0x180022456  push    rsi
0x180022457  push    rdi
0x180022458  push    r12
0x18002245a  push    r13
0x18002245c  push    r14
0x18002245e  push    r15
0x180022460  lea     rbp, [rsp-1Fh]
0x180022465  sub     rsp, 90h
0x18002246c  mov     rax, cs:__security_cookie
0x180022473  xor     rax, rsp
0x180022476  mov     [rbp+4Fh+var_38], rax
0x18002247a  mov     r15d, r9d
0x18002247d  mov     r12, r8
0x180022480  mov     r14, rdx
0x180022483  mov     r13, [rbp+4Fh+arg_20]
0x180022487  lea     rsi, [rcx+148h]
0x18002248e  mov     rdx, rsi
0x180022491  lea     rcx, [rbp+4Fh+lpPathName]
0x180022495  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002249a  nop
0x18002249b  xor     edx, edx; lpSecurityAttributes
0x18002249d  mov     rbx, [rbp+4Fh+lpPathName]
0x1800224a1  mov     rcx, rbx; lpPathName
0x1800224a4  call    cs:__imp_CreateDirectoryW
0x1800224aa  test    eax, eax
0x1800224ac  jnz     short loc_1800224EE
0x1800224ae  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800224b3  mov     edi, eax
0x1800224b5  mov     ecx, 0B7h; unsigned int
0x1800224ba  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800224bf  cmp     edi, eax
0x1800224c1  jz      short loc_1800224EE
0x1800224c3  lea     rdx, [rbx-18h]
0x1800224c7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800224cb  mov     ecx, esi
0x1800224cd  lock xadd [rdx+10h], ecx
0x1800224d2  add     ecx, esi
0x1800224d4  test    ecx, ecx
0x1800224d6  jg      short loc_1800224E7
0x1800224d8  mov     rcx, [rdx]
0x1800224db  mov     rax, [rcx]
0x1800224de  mov     rax, [rax+8]
0x1800224e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e7  mov     eax, edi
0x1800224e9  jmp     loc_18002286B
0x1800224ee  mov     r8, r14
0x1800224f1  lea     rdx, aHs_0; "\\%hs"
0x1800224f8  lea     rcx, [rbp+4Fh+lpPathName]
0x1800224fc  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180022501  xor     edx, edx; lpSecurityAttributes
0x180022503  mov     rbx, [rbp+4Fh+lpPathName]
0x180022507  mov     rcx, rbx; lpPathName
0x18002250a  call    cs:__imp_CreateDirectoryW
0x180022510  test    eax, eax
0x180022512  jnz     short loc_180022529
0x180022514  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180022519  mov     edi, eax
0x18002251b  mov     ecx, 0B7h; unsigned int
0x180022520  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022525  cmp     edi, eax
0x180022527  jnz     short loc_1800224C3
0x180022529  mov     [rsp+0C0h+dwFlagsAndAttributes], r15d
0x18002252e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r12
0x180022533  mov     r9, r14
0x180022536  mov     r8, [rsi]
0x180022539  lea     rdx, [rbp+4Fh+lpPathName]
0x18002253d  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x180022542  xor     edx, edx; lpSecurityAttributes
0x180022544  mov     rbx, [rbp+4Fh+lpPathName]
0x180022548  mov     rcx, rbx; lpPathName
0x18002254b  call    cs:__imp_CreateDirectoryW
0x180022551  xor     r12d, r12d
0x180022554  test    eax, eax
0x180022556  jnz     short loc_180022571
0x180022558  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002255d  mov     edi, eax
0x18002255f  mov     ecx, 0B7h; unsigned int
0x180022564  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022569  cmp     edi, eax
0x18002256b  jnz     loc_1800224C3
0x180022571  xorps   xmm0, xmm0
0x180022574  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x180022578  mov     qword ptr [rbp+4Fh+var_68], r12
0x18002257c  mov     qword ptr [rbp+4Fh+var_68+8], r12
0x180022580  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022584  mov     r8, rsi
0x180022587  inc     r8
0x18002258a  cmp     [r14+r8], r12b
0x18002258e  jnz     short loc_180022587
0x180022590  mov     rdx, r14
0x180022593  lea     rcx, [rbp+4Fh+Src]
0x180022597  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002259c  nop
0x18002259d  mov     rax, qword ptr [rbp+4Fh+var_68]
0x1800225a1  lea     rdi, [rbp+4Fh+Src]
0x1800225a5  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x1800225a9  mov     r14d, 0Fh
0x1800225af  cmp     r9, r14
0x1800225b2  cmova   rdi, [rbp+4Fh+Src]
0x1800225b7  test    rax, rax
0x1800225ba  jz      short loc_1800225E9
0x1800225bc  dec     rax
0x1800225bf  cmp     rax, rsi
0x1800225c2  cmovnb  rax, rsi
0x1800225c6  lea     rbx, [rax+1]
0x1800225ca  add     rbx, rdi
0x1800225cd  mov     r8b, 2Eh ; '.'
0x1800225d0  mov     rdx, rbx
0x1800225d3  mov     rcx, rdi
0x1800225d6  call    __std_find_last_trivial_1
0x1800225db  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x1800225df  cmp     rax, rbx
0x1800225e2  jz      short loc_1800225E9
0x1800225e4  sub     rax, rdi
0x1800225e7  jmp     short loc_1800225EC
0x1800225e9  mov     rax, rsi
0x1800225ec  cmp     rax, rsi
0x1800225ef  jz      loc_18002268C
0x1800225f5  xorps   xmm0, xmm0
0x1800225f8  movups  [rbp+4Fh+var_58], xmm0
0x1800225fc  mov     qword ptr [rbp+4Fh+var_48], r12
0x180022600  mov     qword ptr [rbp+4Fh+var_48+8], r12
0x180022604  mov     r8, qword ptr [rbp+4Fh+var_68]
0x180022608  cmp     r8, rax
0x18002260b  cmovnb  r8, rax
0x18002260f  lea     rdx, [rbp+4Fh+Src]
0x180022613  cmp     r9, r14
0x180022616  cmova   rdx, [rbp+4Fh+Src]
0x18002261b  lea     rcx, [rbp+4Fh+var_58]
0x18002261f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180022624  mov     rdx, qword ptr [rbp+4Fh+var_68+8]
0x180022628  cmp     rdx, r14
0x18002262b  jbe     short loc_180022663
0x18002262d  mov     rax, [rbp+4Fh+Src]
0x180022631  inc     rdx; unsigned __int64
0x180022634  cmp     rdx, 1000h
0x18002263b  jb      short loc_18002265B
0x18002263d  mov     rcx, [rax-8]
0x180022641  sub     rax, rcx
0x180022644  sub     rax, 8
0x180022648  cmp     rax, 1Fh
0x18002264c  ja      short loc_180022654
0x18002264e  add     rdx, 27h ; '''
0x180022652  jmp     short loc_18002265E
0x180022654  mov     ecx, 5
0x180022659  int     29h; Win8: RtlFailFast(ecx)
0x18002265b  mov     rcx, rax; void *
0x18002265e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022663  movups  xmm0, [rbp+4Fh+var_58]
0x180022667  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x18002266b  movups  xmm1, [rbp+4Fh+var_48]
0x18002266f  movups  [rbp+4Fh+var_68], xmm1
0x180022673  mov     qword ptr [rbp+4Fh+var_48], r12
0x180022677  mov     qword ptr [rbp+4Fh+var_48+8], r14
0x18002267b  mov     byte ptr [rbp+4Fh+var_58], r12b
0x18002267f  lea     rcx, [rbp+4Fh+var_58]
0x180022683  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180022688  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x18002268c  mov     rdx, qword ptr [rbp+4Fh+var_68]
0x180022690  mov     rax, r9
0x180022693  sub     rax, rdx
0x180022696  mov     ecx, 5
0x18002269b  cmp     rax, rcx
0x18002269e  jb      short loc_1800226CF
0x1800226a0  lea     rax, [rdx+5]
0x1800226a4  mov     qword ptr [rbp+4Fh+var_68], rax
0x1800226a8  lea     rbx, [rbp+4Fh+Src]
0x1800226ac  cmp     r9, r14
0x1800226af  cmova   rbx, [rbp+4Fh+Src]
0x1800226b4  add     rbx, rdx
0x1800226b7  mov     r8d, ecx; Size
0x1800226ba  lea     rdx, aCpdb; ".cpdb"
0x1800226c1  mov     rcx, rbx; void *
0x1800226c4  call    memmove_0
0x1800226c9  mov     [rbx+5], r12b
0x1800226cd  jmp     short loc_1800226E0
0x1800226cf  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; Size
0x1800226d4  mov     rdx, rcx
0x1800226d7  lea     rcx, [rbp+4Fh+Src]; Src
0x1800226db  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x1800226e0  lea     r8, [rbp+4Fh+Src]
0x1800226e4  cmp     qword ptr [rbp+4Fh+var_68+8], r14
0x1800226e8  cmova   r8, [rbp+4Fh+Src]
0x1800226ed  lea     rdx, aHs_0; "\\%hs"
0x1800226f4  lea     rcx, [rbp+4Fh+lpPathName]
0x1800226f8  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800226fd  mov     rbx, [rbp+4Fh+lpPathName]
0x180022701  mov     rcx, rbx; lpFileName
0x180022704  call    cs:__imp_GetFileAttributesW
0x18002270a  cmp     eax, 0FFFFFFFFh
0x18002270d  jnz     loc_18002283F
0x180022713  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x180022718  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180022720  mov     [rsp+0C0h+dwCreationDisposition], 1; dwCreationDisposition
0x180022728  xor     r9d, r9d; lpSecurityAttributes
0x18002272b  xor     r8d, r8d; dwShareMode
0x18002272e  mov     edx, 40000000h; dwDesiredAccess
0x180022733  mov     rcx, rbx; lpFileName
0x180022736  call    cs:__imp_CreateFileW
0x18002273c  mov     r15, rax
0x18002273f  test    rax, rax
0x180022742  jnz     short loc_180022796
0x180022744  call    cs:__imp_GetLastError
0x18002274a  cmp     eax, 50h ; 'P'
0x18002274d  jz      loc_18002283F
0x180022753  call    cs:__imp_GetLastError
0x180022759  test    eax, eax
0x18002275b  mov     edi, eax
0x18002275d  jle     short loc_180022768
0x18002275f  movzx   edi, ax
0x180022762  or      edi, 80070000h
0x180022768  lea     rcx, [rbp+4Fh+Src]
0x18002276c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180022771  nop
0x180022772  lea     rdx, [rbx-18h]
0x180022776  mov     ecx, esi
0x180022778  lock xadd [rdx+10h], ecx
0x18002277d  add     ecx, esi
0x18002277f  test    ecx, ecx
0x180022781  jg      loc_1800224E7
0x180022787  mov     rcx, [rdx]
0x18002278a  mov     r8, [rcx]
0x18002278d  mov     rax, [r8+8]
0x180022791  jmp     loc_1800224E2
0x180022796  mov     r14d, [r13+0]
0x18002279a  mov     dword ptr [rbp+4Fh+lpPathName], r14d
0x18002279e  xor     eax, eax
0x1800227a0  mov     dword ptr [rbp+4Fh+lpPathName+4], eax
0x1800227a3  xor     r9d, r9d; dwMoveMethod
0x1800227a6  xor     r8d, r8d; lpNewFilePointer
0x1800227a9  mov     rdi, [rbp+4Fh+lpPathName]
0x1800227ad  mov     rdx, rdi; liDistanceToMove
0x1800227b0  mov     rcx, r15; hFile
0x1800227b3  call    cs:__imp_SetFilePointerEx
0x1800227b9  mov     rcx, r15; hFile
0x1800227bc  test    eax, eax
0x1800227be  jnz     short loc_1800227C8
0x1800227c0  call    cs:__imp_CloseHandle
0x1800227c6  jmp     short loc_180022753
0x1800227c8  xor     r9d, r9d; dwMoveMethod
0x1800227cb  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800227ce  xor     edx, edx; lDistanceToMove
0x1800227d0  call    cs:__imp_SetFilePointer
0x1800227d6  mov     eax, 10000h
0x1800227db  cmp     r14d, eax
0x1800227de  cmova   r14d, eax
0x1800227e2  mov     r12, [r13+8]
0x1800227e6  test    r14d, r14d
0x1800227e9  jz      short loc_180022835
0x1800227eb  mov     r13d, eax
0x1800227ee  mov     dword ptr [rbp+4Fh+lpPathName], 0
0x1800227f5  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x1800227fe  lea     r9, [rbp+4Fh+lpPathName]; lpNumberOfBytesWritten
0x180022802  mov     r8d, r14d; nNumberOfBytesToWrite
0x180022805  mov     rdx, r12; lpBuffer
0x180022808  mov     rcx, r15; hFile
0x18002280b  call    cs:__imp_WriteFile
0x180022811  test    eax, eax
0x180022813  jz      short loc_180022892
0x180022815  mov     eax, dword ptr [rbp+4Fh+lpPathName]
0x180022818  sub     rdi, rax
0x18002281b  mov     [rbp+4Fh+lpPathName], rdi
0x18002281f  add     r12, rax
0x180022822  mov     r14d, dword ptr [rbp+4Fh+lpPathName]
0x180022826  cmp     r14d, r13d
0x180022829  jbe     short loc_180022830
0x18002282b  mov     r14d, r13d
0x18002282e  jmp     short loc_1800227EE
0x180022830  test    r14d, r14d
0x180022833  jnz     short loc_1800227EE
0x180022835  mov     rcx, r15; hObject
0x180022838  call    cs:__imp_CloseHandle
0x18002283e  nop
0x18002283f  lea     rcx, [rbp+4Fh+Src]
0x180022843  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180022848  nop
0x180022849  lea     rdx, [rbx-18h]
0x18002284d  mov     eax, esi
0x18002284f  lock xadd [rdx+10h], eax
0x180022854  add     eax, esi
0x180022856  test    eax, eax
0x180022858  jg      short loc_180022869
0x18002285a  mov     rcx, [rdx]
0x18002285d  mov     rax, [rcx]
0x180022860  mov     rax, [rax+8]
0x180022864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022869  xor     eax, eax
0x18002286b  mov     rcx, [rbp+4Fh+var_38]
0x18002286f  xor     rcx, rsp; StackCookie
0x180022872  call    __security_check_cookie
0x180022877  mov     rbx, [rsp+0C0h+arg_18]
0x18002287f  add     rsp, 90h
0x180022886  pop     r15
0x180022888  pop     r14
0x18002288a  pop     r13
0x18002288c  pop     r12
0x18002288e  pop     rdi
0x18002288f  pop     rsi
  ... truncated ...
```
