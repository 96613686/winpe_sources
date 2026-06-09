# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x180016e84`
- end: `0x180017133`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001753c`

## callees

- `0x180001870`
- `0x1800045d4`
- `0x180004670`
- `0x180004694`
- `0x18000cfe4`
- `0x180011630`
- `0x1800164e0`
- `0x180016e84`
- `0x180017938`
- `0x180018910`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016ec8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016f2d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016f69`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016ec8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016f2d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016f69`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001704d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001704d`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  _QWORD *v4; // r15
  LPCWSTR v8; // rbx
  unsigned int v9; // esi
  int v11; // ecx
  const WCHAR *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r8
  LPCWSTR v16; // rdx
  const wchar_t *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // r8
  unsigned int Error; // edi
  LPCWSTR lpPathName; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v25[16]; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR *p_lpPathName; // [rsp+48h] [rbp-30h]
  __int64 v27; // [rsp+50h] [rbp-28h]
  LPCWSTR v28; // [rsp+58h] [rbp-20h]
  int v29; // [rsp+60h] [rbp-18h]
  int v30; // [rsp+64h] [rbp-14h]

  v4 = (_QWORD *)((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 56);
  v8 = lpPathName;
  if ( (CreateDirectoryW(lpPathName, 0)
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)))
    && ((ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
           &lpPathName,
           L"\\%hs",
           a3),
         v8 = lpPathName,
         CreateDirectoryW(lpPathName, 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)))
    && ((Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
           v11,
           (unsigned int)&lpPathName,
           *v4,
           (_DWORD)a3,
           (__int64)a4),
         v8 = lpPathName,
         CreateDirectoryW(lpPathName, 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u))) )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpPathName, L"\\", 1);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
      &lpPathName,
      a3);
    v12 = lpPathName;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    {
      v13 = 10;
      if ( a2 )
      {
        v14 = -1;
        do
          ++v14;
        while ( a2[v14] );
        v15 = (unsigned int)(2 * v14 + 2);
      }
      else
      {
        v15 = 10;
      }
      v27 = (unsigned int)v15;
      v16 = L"NULL";
      v17 = a2;
      if ( !a2 )
        v17 = L"NULL";
      p_lpPathName = (LPCWSTR *)v17;
      if ( lpPathName )
      {
        v18 = -1;
        do
          ++v18;
        while ( lpPathName[v18] );
        v16 = lpPathName;
        v13 = (unsigned int)(2 * v18 + 2);
      }
      v28 = v16;
      v29 = v13;
      v30 = 0;
      McGenEventWrite_EventWriteTransfer(v13, TraceMerge_NGEN_CopyingPDB_Start, v15, 3, v25);
    }
    if ( CopyFileW(a2, v12, 0) )
    {
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        LODWORD(lpPathName) = 0;
        p_lpPathName = &lpPathName;
        v27 = 4;
        McGenEventWrite_EventWriteTransfer(v19, TraceMerge_NGEN_CopyingPDB_Stop, v20, 2, v25);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      return 0;
    }
    else
    {
      if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      {
        LODWORD(lpPathName) = ATL::AtlHresultFromLastError();
        v27 = 4;
        p_lpPathName = &lpPathName;
        McGenEventWrite_EventWriteTransfer(v21, TraceMerge_NGEN_CopyingPDB_Stop, v22, 2, v25);
      }
      Error = ATL::AtlHresultFromLastError();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
      return Error;
    }
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
    return v9;
  }
}

```

## disassembly

```asm
0x180016e84  push    rbp
0x180016e86  push    rbx
0x180016e87  push    rsi
0x180016e88  push    rdi
0x180016e89  push    r12
0x180016e8b  push    r13
0x180016e8d  push    r14
0x180016e8f  push    r15
0x180016e91  mov     rbp, rsp
0x180016e94  sub     rsp, 78h
0x180016e98  mov     rax, cs:__security_cookie
0x180016e9f  xor     rax, rsp
0x180016ea2  mov     [rbp+var_10], rax
0x180016ea6  lea     r15, [rcx+38h]
0x180016eaa  mov     rdi, rdx
0x180016ead  mov     rdx, r15
0x180016eb0  lea     rcx, [rbp+lpPathName]
0x180016eb4  mov     r12, r9
0x180016eb7  mov     r14, r8
0x180016eba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180016ebf  mov     rbx, [rbp+lpPathName]
0x180016ec3  xor     edx, edx; lpSecurityAttributes
0x180016ec5  mov     rcx, rbx; lpPathName
0x180016ec8  call    cs:__imp_CreateDirectoryW
0x180016ece  xor     r13d, r13d
0x180016ed1  test    eax, eax
0x180016ed3  jnz     short loc_180016F11
0x180016ed5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016eda  mov     ecx, 0B7h; unsigned int
0x180016edf  mov     esi, eax
0x180016ee1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180016ee6  cmp     esi, eax
0x180016ee8  jz      short loc_180016F11
0x180016eea  lea     rdx, [rbx-18h]
0x180016eee  or      ecx, 0FFFFFFFFh
0x180016ef1  lock xadd [rdx+10h], ecx
0x180016ef6  sub     ecx, 1
0x180016ef9  jg      short loc_180016F0A
0x180016efb  mov     rcx, [rdx]
0x180016efe  mov     rax, [rcx]
0x180016f01  mov     rax, [rax+8]
0x180016f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f0a  mov     eax, esi
0x180016f0c  jmp     loc_180017116
0x180016f11  mov     r8, r14
0x180016f14  lea     rdx, aHs_0; "\\%hs"
0x180016f1b  lea     rcx, [rbp+lpPathName]
0x180016f1f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180016f24  mov     rbx, [rbp+lpPathName]
0x180016f28  xor     edx, edx; lpSecurityAttributes
0x180016f2a  mov     rcx, rbx; lpPathName
0x180016f2d  call    cs:__imp_CreateDirectoryW
0x180016f33  test    eax, eax
0x180016f35  jnz     short loc_180016F4C
0x180016f37  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016f3c  mov     ecx, 0B7h; unsigned int
0x180016f41  mov     esi, eax
0x180016f43  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180016f48  cmp     esi, eax
0x180016f4a  jnz     short loc_180016EEA
0x180016f4c  mov     r8, [r15]
0x180016f4f  lea     rdx, [rbp+lpPathName]
0x180016f53  mov     r9, r14
0x180016f56  mov     [rsp+78h+var_58], r12
0x180016f5b  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x180016f60  mov     rbx, [rbp+lpPathName]
0x180016f64  xor     edx, edx; lpSecurityAttributes
0x180016f66  mov     rcx, rbx; lpPathName
0x180016f69  call    cs:__imp_CreateDirectoryW
0x180016f6f  test    eax, eax
0x180016f71  jnz     short loc_180016F8C
0x180016f73  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016f78  mov     ecx, 0B7h; unsigned int
0x180016f7d  mov     esi, eax
0x180016f7f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180016f84  cmp     esi, eax
0x180016f86  jnz     loc_180016EEA
0x180016f8c  mov     esi, 1
0x180016f91  lea     rdx, asc_18002D2B0; "\\"
0x180016f98  mov     r8d, esi
0x180016f9b  lea     rcx, [rbp+lpPathName]
0x180016f9f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180016fa4  mov     rdx, r14
0x180016fa7  lea     rcx, [rbp+lpPathName]
0x180016fab  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180016fb0  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x180016fb7  mov     rbx, [rbp+lpPathName]
0x180016fbb  jz      loc_180017044
0x180016fc1  lea     ecx, [rsi+9]
0x180016fc4  test    rdi, rdi
0x180016fc7  jz      short loc_180016FE1
0x180016fc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016fcd  inc     rax
0x180016fd0  cmp     [rdi+rax*2], r13w
0x180016fd5  jnz     short loc_180016FCD
0x180016fd7  lea     r8d, ds:2[rax*2]
0x180016fdf  jmp     short loc_180016FE4
0x180016fe1  mov     r8d, ecx
0x180016fe4  test    rdi, rdi
0x180016fe7  mov     dword ptr [rbp+var_28], r8d
0x180016feb  lea     rdx, aNull; "NULL"
0x180016ff2  mov     dword ptr [rbp+var_28+4], r13d
0x180016ff6  mov     rax, rdi
0x180016ff9  cmovz   rax, rdx
0x180016ffd  mov     [rbp+var_30], rax
0x180017001  test    rbx, rbx
0x180017004  jz      short loc_18001701E
0x180017006  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001700a  inc     rax
0x18001700d  cmp     [rbx+rax*2], r13w
0x180017012  jnz     short loc_18001700A
0x180017014  mov     rdx, rbx
0x180017017  lea     ecx, ds:2[rax*2]
0x18001701e  mov     [rbp+var_20], rdx
0x180017022  lea     rax, [rbp+var_40]
0x180017026  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x18001702d  mov     [rsp+78h+var_58], rax
0x180017032  mov     r9d, 3
0x180017038  mov     [rbp+var_18], ecx
0x18001703b  mov     [rbp+var_14], r13d
0x18001703f  call    McGenEventWrite_EventWriteTransfer
0x180017044  xor     r8d, r8d; bFailIfExists
0x180017047  mov     rdx, rbx; lpNewFileName
0x18001704a  mov     rcx, rdi; lpExistingFileName
0x18001704d  call    cs:__imp_CopyFileW
0x180017053  test    eax, eax
0x180017055  jnz     short loc_1800170BD
0x180017057  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x18001705e  jz      short loc_180017093
0x180017060  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017065  mov     dword ptr [rbp+lpPathName], eax
0x180017068  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18001706f  lea     rax, [rbp+lpPathName]
0x180017073  mov     [rbp+var_28], 4
0x18001707b  mov     [rbp+var_30], rax
0x18001707f  mov     r9d, 2
0x180017085  lea     rax, [rbp+var_40]
0x180017089  mov     [rsp+78h+var_58], rax
0x18001708e  call    McGenEventWrite_EventWriteTransfer
0x180017093  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180017098  mov     edi, eax
0x18001709a  lea     rdx, [rbx-18h]
0x18001709e  or      ecx, 0FFFFFFFFh
0x1800170a1  lock xadd [rdx+10h], ecx
0x1800170a6  sub     ecx, esi
0x1800170a8  jg      short loc_1800170B9
0x1800170aa  mov     rcx, [rdx]
0x1800170ad  mov     r8, [rcx]
0x1800170b0  mov     rax, [r8+8]
0x1800170b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b9  mov     eax, edi
0x1800170bb  jmp     short loc_180017116
0x1800170bd  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x1800170c4  jz      short loc_1800170F5
0x1800170c6  lea     rax, [rbp+lpPathName]
0x1800170ca  mov     dword ptr [rbp+lpPathName], r13d
0x1800170ce  mov     [rbp+var_30], rax
0x1800170d2  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x1800170d9  lea     rax, [rbp+var_40]
0x1800170dd  mov     [rbp+var_28], 4
0x1800170e5  mov     r9d, 2
0x1800170eb  mov     [rsp+78h+var_58], rax
0x1800170f0  call    McGenEventWrite_EventWriteTransfer
0x1800170f5  lea     rdx, [rbx-18h]
0x1800170f9  or      eax, 0FFFFFFFFh
0x1800170fc  lock xadd [rdx+10h], eax
0x180017101  sub     eax, esi
0x180017103  jg      short loc_180017114
0x180017105  mov     rcx, [rdx]
0x180017108  mov     rax, [rcx]
0x18001710b  mov     rax, [rax+8]
0x18001710f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017114  xor     eax, eax
0x180017116  mov     rcx, [rbp+var_10]
0x18001711a  xor     rcx, rsp; StackCookie
0x18001711d  call    __security_check_cookie
0x180017122  add     rsp, 78h
0x180017126  pop     r15
0x180017128  pop     r14
0x18001712a  pop     r13
0x18001712c  pop     r12
0x18001712e  pop     rdi
0x18001712f  pop     rsi
0x180017130  pop     rbx
0x180017131  pop     rbp
0x180017132  retn
```
