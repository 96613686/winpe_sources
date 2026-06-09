# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreateEmbeddedPdb(char const *,_GUID const &,ulong,EMBEDDED_PDB_INFORMATION const &)

- ea: `0x1800233a0`
- end: `0x18002383b`
- name: `?CreateEmbeddedPdb@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBDAEBU_GUID@@KAEBUEMBEDDED_PDB_INFORMATION@@@Z`
- size: `1179`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this, const char *, const struct _GUID *, unsigned int, const struct EMBEDDED_PDB_INFORMATION *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x180002ac0`
- `0x180002d31`
- `0x180016274`
- `0x18001629c`
- `0x18001dd58`
- `0x18001e594`
- `0x18001ec68`
- `0x18001fde0`
- `0x180023180`
- `0x1800233a0`
- `0x180023920`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023740`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237d1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800233f4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023460`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800234a7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800233f4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023460`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800234a7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180023759`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180023759`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002379a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002379a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002369e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002369e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002372d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002372d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180023666`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180023666`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  __int64 v24; // rdx
  void **v25; // rbx
  _BYTE *v26; // rbx
  void **v27; // r8
  const WCHAR *v28; // rbx
  HANDLE FileW; // r15
  signed int LastError; // eax
  DWORD v31; // r14d
  const WCHAR *v32; // rdi
  BOOL v33; // eax
  void *v34; // rcx
  char *v35; // r12
  __int64 v36; // rax
  LPCWSTR lpPathName; // [rsp+40h] [rbp-31h] BYREF
  void *Src[2]; // [rsp+48h] [rbp-29h] BYREF
  __int128 v39; // [rsp+58h] [rbp-19h]
  __int128 v40; // [rsp+68h] [rbp-9h] BYREF
  __int128 v41; // [rsp+78h] [rbp+7h]

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
  *(_OWORD *)Src = 0;
  v39 = 0u;
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  std::string::_Construct<1,char const *>(Src, a2);
  v16 = Src;
  v17 = *((_QWORD *)&v39 + 1);
  if ( *((_QWORD *)&v39 + 1) > 0xFu )
    v16 = (void **)Src[0];
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
    v21 = Src;
    if ( v17 > 0xF )
      v21 = (void **)Src[0];
    std::string::_Construct<1,char const *>(&v40, v21);
    if ( *((_QWORD *)&v39 + 1) > 0xFu )
    {
      v22 = *((_QWORD *)&v39 + 1) + 1LL;
      if ( (unsigned __int64)(*((_QWORD *)&v39 + 1) + 1LL) < 0x1000 )
      {
        v23 = Src[0];
      }
      else
      {
        v23 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v23 - 8) > 0x1F )
          __fastfail(5u);
        v22 = *((_QWORD *)&v39 + 1) + 40LL;
      }
      operator delete(v23, v22);
    }
    *(_OWORD *)Src = v40;
    v39 = v41;
    *(_QWORD *)&v41 = 0;
    *((_QWORD *)&v41 + 1) = 15;
    LOBYTE(v40) = 0;
    std::string::~string(&v40);
    v17 = *((_QWORD *)&v39 + 1);
  }
  v24 = v39;
  if ( v17 - (unsigned __int64)v39 < 5 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 5u);
  }
  else
  {
    *(_QWORD *)&v39 = v39 + 5;
    v25 = Src;
    if ( v17 > 0xF )
      v25 = (void **)Src[0];
    v26 = (char *)v25 + v24;
    memmove_0(v26, ".cpdb", 5u);
    v26[5] = 0;
  }
  v27 = Src;
  if ( *((_QWORD *)&v39 + 1) > 0xFu )
    v27 = (void **)Src[0];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpPathName,
    L"\\%hs",
    v27);
  v28 = lpPathName;
  if ( GetFileAttributesW(lpPathName) == -1 )
  {
    FileW = CreateFileW(v28, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    if ( FileW )
    {
      v31 = *a5;
      lpPathName = (LPCWSTR)*a5;
      v32 = lpPathName;
      v33 = SetFilePointerEx(FileW, (LARGE_INTEGER)lpPathName, 0, 0);
      v34 = FileW;
      if ( v33 )
      {
        SetFilePointer(FileW, 0, 0, 0);
        if ( v31 > 0x10000 )
          v31 = 0x10000;
        v35 = (char *)*((_QWORD *)a5 + 1);
        if ( !v31 )
        {
LABEL_53:
          CloseHandle(FileW);
          goto LABEL_54;
        }
        while ( 1 )
        {
          LODWORD(lpPathName) = 0;
          if ( !WriteFile(FileW, v35, v31, (LPDWORD)&lpPathName, 0) )
            break;
          v36 = (unsigned int)lpPathName;
          v32 = (const WCHAR *)((char *)v32 - (unsigned int)lpPathName);
          lpPathName = v32;
          v35 += v36;
          v31 = (unsigned int)v32;
          if ( (unsigned int)v32 <= 0x10000 )
          {
            if ( !(_DWORD)v32 )
              goto LABEL_53;
          }
          else
          {
            v31 = 0x10000;
          }
        }
        v34 = FileW;
      }
      CloseHandle(v34);
      goto LABEL_40;
    }
    if ( GetLastError() != 80 )
    {
LABEL_40:
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      std::string::~string(Src);
      if ( _InterlockedDecrement((volatile signed __int32 *)v28 - 2) > 0 )
        return Error;
      v11 = *(void (**)(void))(**((_QWORD **)v28 - 3) + 8LL);
      goto LABEL_5;
    }
  }
LABEL_54:
  std::string::~string(Src);
  if ( _InterlockedDecrement((volatile signed __int32 *)v28 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v28 - 3) + 8LL))(*((_QWORD *)v28 - 3));
  return 0;
}

```

## disassembly

```asm
0x1800233a0  mov     [rsp-8+arg_18], rbx
0x1800233a5  push    rbp
0x1800233a6  push    rsi
0x1800233a7  push    rdi
0x1800233a8  push    r12
0x1800233aa  push    r13
0x1800233ac  push    r14
0x1800233ae  push    r15
0x1800233b0  lea     rbp, [rsp-1Fh]
0x1800233b5  sub     rsp, 90h
0x1800233bc  mov     rax, cs:__security_cookie
0x1800233c3  xor     rax, rsp
0x1800233c6  mov     [rbp+4Fh+var_38], rax
0x1800233ca  mov     r15d, r9d
0x1800233cd  mov     r12, r8
0x1800233d0  mov     r14, rdx
0x1800233d3  mov     r13, [rbp+4Fh+arg_20]
0x1800233d7  lea     rsi, [rcx+148h]
0x1800233de  mov     rdx, rsi
0x1800233e1  lea     rcx, [rbp+4Fh+lpPathName]
0x1800233e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800233ea  nop
0x1800233eb  xor     edx, edx; lpSecurityAttributes
0x1800233ed  mov     rbx, [rbp+4Fh+lpPathName]
0x1800233f1  mov     rcx, rbx; lpPathName
0x1800233f4  call    cs:__imp_CreateDirectoryW
0x1800233fb  nop     dword ptr [rax+rax+00h]
0x180023400  test    eax, eax
0x180023402  jnz     short loc_180023444
0x180023404  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023409  mov     edi, eax
0x18002340b  mov     ecx, 0B7h; unsigned int
0x180023410  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023415  cmp     edi, eax
0x180023417  jz      short loc_180023444
0x180023419  lea     rdx, [rbx-18h]
0x18002341d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023421  mov     ecx, esi
0x180023423  lock xadd [rdx+10h], ecx
0x180023428  add     ecx, esi
0x18002342a  test    ecx, ecx
0x18002342c  jg      short loc_18002343D
0x18002342e  mov     rcx, [rdx]
0x180023431  mov     rax, [rcx]
0x180023434  mov     rax, [rax+8]
0x180023438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002343d  mov     eax, edi
0x18002343f  jmp     loc_18002380A
0x180023444  mov     r8, r14
0x180023447  lea     rdx, aHs_0; "\\%hs"
0x18002344e  lea     rcx, [rbp+4Fh+lpPathName]
0x180023452  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180023457  xor     edx, edx; lpSecurityAttributes
0x180023459  mov     rbx, [rbp+4Fh+lpPathName]
0x18002345d  mov     rcx, rbx; lpPathName
0x180023460  call    cs:__imp_CreateDirectoryW
0x180023467  nop     dword ptr [rax+rax+00h]
0x18002346c  test    eax, eax
0x18002346e  jnz     short loc_180023485
0x180023470  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023475  mov     edi, eax
0x180023477  mov     ecx, 0B7h; unsigned int
0x18002347c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180023481  cmp     edi, eax
0x180023483  jnz     short loc_180023419
0x180023485  mov     [rsp+0C0h+dwFlagsAndAttributes], r15d
0x18002348a  mov     qword ptr [rsp+0C0h+dwCreationDisposition], r12
0x18002348f  mov     r9, r14
0x180023492  mov     r8, [rsi]
0x180023495  lea     rdx, [rbp+4Fh+lpPathName]
0x180023499  call    ?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)
0x18002349e  xor     edx, edx; lpSecurityAttributes
0x1800234a0  mov     rbx, [rbp+4Fh+lpPathName]
0x1800234a4  mov     rcx, rbx; lpPathName
0x1800234a7  call    cs:__imp_CreateDirectoryW
0x1800234ae  nop     dword ptr [rax+rax+00h]
0x1800234b3  xor     r12d, r12d
0x1800234b6  test    eax, eax
0x1800234b8  jnz     short loc_1800234D3
0x1800234ba  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800234bf  mov     edi, eax
0x1800234c1  mov     ecx, 0B7h; unsigned int
0x1800234c6  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800234cb  cmp     edi, eax
0x1800234cd  jnz     loc_180023419
0x1800234d3  xorps   xmm0, xmm0
0x1800234d6  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x1800234da  mov     qword ptr [rbp+4Fh+var_68], r12
0x1800234de  mov     qword ptr [rbp+4Fh+var_68+8], r12
0x1800234e2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800234e6  mov     r8, rsi
0x1800234e9  inc     r8
0x1800234ec  cmp     [r14+r8], r12b
0x1800234f0  jnz     short loc_1800234E9
0x1800234f2  mov     rdx, r14
0x1800234f5  lea     rcx, [rbp+4Fh+Src]
0x1800234f9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800234fe  nop
0x1800234ff  mov     rax, qword ptr [rbp+4Fh+var_68]
0x180023503  lea     rdi, [rbp+4Fh+Src]
0x180023507  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x18002350b  mov     r14d, 0Fh
0x180023511  cmp     r9, r14
0x180023514  cmova   rdi, [rbp+4Fh+Src]
0x180023519  test    rax, rax
0x18002351c  jz      short loc_18002354B
0x18002351e  dec     rax
0x180023521  cmp     rax, rsi
0x180023524  cmovnb  rax, rsi
0x180023528  lea     rbx, [rax+1]
0x18002352c  add     rbx, rdi
0x18002352f  mov     r8b, 2Eh ; '.'
0x180023532  mov     rdx, rbx
0x180023535  mov     rcx, rdi
0x180023538  call    __std_find_last_trivial_1
0x18002353d  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x180023541  cmp     rax, rbx
0x180023544  jz      short loc_18002354B
0x180023546  sub     rax, rdi
0x180023549  jmp     short loc_18002354E
0x18002354b  mov     rax, rsi
0x18002354e  cmp     rax, rsi
0x180023551  jz      loc_1800235EE
0x180023557  xorps   xmm0, xmm0
0x18002355a  movups  [rbp+4Fh+var_58], xmm0
0x18002355e  mov     qword ptr [rbp+4Fh+var_48], r12
0x180023562  mov     qword ptr [rbp+4Fh+var_48+8], r12
0x180023566  mov     r8, qword ptr [rbp+4Fh+var_68]
0x18002356a  cmp     r8, rax
0x18002356d  cmovnb  r8, rax
0x180023571  lea     rdx, [rbp+4Fh+Src]
0x180023575  cmp     r9, r14
0x180023578  cmova   rdx, [rbp+4Fh+Src]
0x18002357d  lea     rcx, [rbp+4Fh+var_58]
0x180023581  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180023586  mov     rdx, qword ptr [rbp+4Fh+var_68+8]
0x18002358a  cmp     rdx, r14
0x18002358d  jbe     short loc_1800235C5
0x18002358f  mov     rax, [rbp+4Fh+Src]
0x180023593  inc     rdx; unsigned __int64
0x180023596  cmp     rdx, 1000h
0x18002359d  jb      short loc_1800235BD
0x18002359f  mov     rcx, [rax-8]
0x1800235a3  sub     rax, rcx
0x1800235a6  sub     rax, 8
0x1800235aa  cmp     rax, 1Fh
0x1800235ae  ja      short loc_1800235B6
0x1800235b0  add     rdx, 27h ; '''
0x1800235b4  jmp     short loc_1800235C0
0x1800235b6  mov     ecx, 5
0x1800235bb  int     29h; Win8: RtlFailFast(ecx)
0x1800235bd  mov     rcx, rax; void *
0x1800235c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800235c5  movups  xmm0, [rbp+4Fh+var_58]
0x1800235c9  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x1800235cd  movups  xmm1, [rbp+4Fh+var_48]
0x1800235d1  movups  [rbp+4Fh+var_68], xmm1
0x1800235d5  mov     qword ptr [rbp+4Fh+var_48], r12
0x1800235d9  mov     qword ptr [rbp+4Fh+var_48+8], r14
0x1800235dd  mov     byte ptr [rbp+4Fh+var_58], r12b
0x1800235e1  lea     rcx, [rbp+4Fh+var_58]
0x1800235e5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800235ea  mov     r9, qword ptr [rbp+4Fh+var_68+8]
0x1800235ee  mov     rdx, qword ptr [rbp+4Fh+var_68]
0x1800235f2  mov     rax, r9
0x1800235f5  sub     rax, rdx
0x1800235f8  mov     ecx, 5
0x1800235fd  cmp     rax, rcx
0x180023600  jb      short loc_180023631
0x180023602  lea     rax, [rdx+5]
0x180023606  mov     qword ptr [rbp+4Fh+var_68], rax
0x18002360a  lea     rbx, [rbp+4Fh+Src]
0x18002360e  cmp     r9, r14
0x180023611  cmova   rbx, [rbp+4Fh+Src]
0x180023616  add     rbx, rdx
0x180023619  mov     r8d, ecx; Size
0x18002361c  lea     rdx, aCpdb; ".cpdb"
0x180023623  mov     rcx, rbx; void *
0x180023626  call    memmove_0
0x18002362b  mov     [rbx+5], r12b
0x18002362f  jmp     short loc_180023642
0x180023631  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx; Size
0x180023636  mov     rdx, rcx
0x180023639  lea     rcx, [rbp+4Fh+Src]; Src
0x18002363d  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180023642  lea     r8, [rbp+4Fh+Src]
0x180023646  cmp     qword ptr [rbp+4Fh+var_68+8], r14
0x18002364a  cmova   r8, [rbp+4Fh+Src]
0x18002364f  lea     rdx, aHs_0; "\\%hs"
0x180023656  lea     rcx, [rbp+4Fh+lpPathName]
0x18002365a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002365f  mov     rbx, [rbp+4Fh+lpPathName]
0x180023663  mov     rcx, rbx; lpFileName
0x180023666  call    cs:__imp_GetFileAttributesW
0x18002366d  nop     dword ptr [rax+rax+00h]
0x180023672  cmp     eax, 0FFFFFFFFh
0x180023675  jnz     loc_1800237DE
0x18002367b  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x180023680  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023688  mov     [rsp+0C0h+dwCreationDisposition], 1; dwCreationDisposition
0x180023690  xor     r9d, r9d; lpSecurityAttributes
0x180023693  xor     r8d, r8d; dwShareMode
0x180023696  mov     edx, 40000000h; dwDesiredAccess
0x18002369b  mov     rcx, rbx; lpFileName
0x18002369e  call    cs:__imp_CreateFileW
0x1800236a5  nop     dword ptr [rax+rax+00h]
0x1800236aa  mov     r15, rax
0x1800236ad  test    rax, rax
0x1800236b0  jnz     short loc_180023710
0x1800236b2  call    cs:__imp_GetLastError
0x1800236b9  nop     dword ptr [rax+rax+00h]
0x1800236be  cmp     eax, 50h ; 'P'
0x1800236c1  jz      loc_1800237DE
0x1800236c7  call    cs:__imp_GetLastError
0x1800236ce  nop     dword ptr [rax+rax+00h]
0x1800236d3  test    eax, eax
0x1800236d5  mov     edi, eax
0x1800236d7  jle     short loc_1800236E2
0x1800236d9  movzx   edi, ax
0x1800236dc  or      edi, 80070000h
0x1800236e2  lea     rcx, [rbp+4Fh+Src]
0x1800236e6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800236eb  nop
0x1800236ec  lea     rdx, [rbx-18h]
0x1800236f0  mov     ecx, esi
0x1800236f2  lock xadd [rdx+10h], ecx
0x1800236f7  add     ecx, esi
0x1800236f9  test    ecx, ecx
0x1800236fb  jg      loc_18002343D
0x180023701  mov     rcx, [rdx]
0x180023704  mov     r8, [rcx]
0x180023707  mov     rax, [r8+8]
0x18002370b  jmp     loc_180023438
0x180023710  mov     r14d, [r13+0]
0x180023714  mov     dword ptr [rbp+4Fh+lpPathName], r14d
0x180023718  xor     eax, eax
0x18002371a  mov     dword ptr [rbp+4Fh+lpPathName+4], eax
0x18002371d  xor     r9d, r9d; dwMoveMethod
0x180023720  xor     r8d, r8d; lpNewFilePointer
0x180023723  mov     rdi, [rbp+4Fh+lpPathName]
0x180023727  mov     rdx, rdi; liDistanceToMove
0x18002372a  mov     rcx, r15; hFile
0x18002372d  call    cs:__imp_SetFilePointerEx
0x180023734  nop     dword ptr [rax+rax+00h]
0x180023739  mov     rcx, r15; hFile
0x18002373c  test    eax, eax
0x18002373e  jnz     short loc_180023751
0x180023740  call    cs:__imp_CloseHandle
0x180023747  nop     dword ptr [rax+rax+00h]
0x18002374c  jmp     loc_1800236C7
0x180023751  xor     r9d, r9d; dwMoveMethod
0x180023754  xor     r8d, r8d; lpDistanceToMoveHigh
0x180023757  xor     edx, edx; lDistanceToMove
0x180023759  call    cs:__imp_SetFilePointer
0x180023760  nop     dword ptr [rax+rax+00h]
0x180023765  mov     eax, 10000h
0x18002376a  cmp     r14d, eax
0x18002376d  cmova   r14d, eax
0x180023771  mov     r12, [r13+8]
0x180023775  test    r14d, r14d
0x180023778  jz      short loc_1800237CE
0x18002377a  mov     r13d, eax
0x18002377d  mov     dword ptr [rbp+4Fh+lpPathName], 0
0x180023784  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x18002378d  lea     r9, [rbp+4Fh+lpPathName]; lpNumberOfBytesWritten
0x180023791  mov     r8d, r14d; nNumberOfBytesToWrite
0x180023794  mov     rdx, r12; lpBuffer
0x180023797  mov     rcx, r15; hFile
0x18002379a  call    cs:__imp_WriteFile
0x1800237a1  nop     dword ptr [rax+rax+00h]
0x1800237a6  test    eax, eax
0x1800237a8  jz      loc_180023832
0x1800237ae  mov     eax, dword ptr [rbp+4Fh+lpPathName]
0x1800237b1  sub     rdi, rax
0x1800237b4  mov     [rbp+4Fh+lpPathName], rdi
0x1800237b8  add     r12, rax
0x1800237bb  mov     r14d, dword ptr [rbp+4Fh+lpPathName]
0x1800237bf  cmp     r14d, r13d
0x1800237c2  jbe     short loc_1800237C9
0x1800237c4  mov     r14d, r13d
0x1800237c7  jmp     short loc_18002377D
0x1800237c9  test    r14d, r14d
0x1800237cc  jnz     short loc_18002377D
0x1800237ce  mov     rcx, r15; hObject
0x1800237d1  call    cs:__imp_CloseHandle
0x1800237d8  nop     dword ptr [rax+rax+00h]
0x1800237dd  nop
0x1800237de  lea     rcx, [rbp+4Fh+Src]
0x1800237e2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800237e7  nop
0x1800237e8  lea     rdx, [rbx-18h]
0x1800237ec  mov     eax, esi
0x1800237ee  lock xadd [rdx+10h], eax
0x1800237f3  add     eax, esi
0x1800237f5  test    eax, eax
0x1800237f7  jg      short loc_180023808
0x1800237f9  mov     rcx, [rdx]
0x1800237fc  mov     rax, [rcx]
0x1800237ff  mov     rax, [rax+8]
0x180023803  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
