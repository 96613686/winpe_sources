# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x180027c84`
- end: `0x180027f37`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028340`

## callees

- `0x180001b60`
- `0x180015674`
- `0x180015710`
- `0x180015734`
- `0x18001dccc`
- `0x180022240`
- `0x1800272dc`
- `0x180027c84`
- `0x180028740`
- `0x180029710`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027cc9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027d2e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027d6a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027cc9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027d2e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027d6a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180027e4e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180027e4e`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  _QWORD *v7; // r15
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

  v7 = (_QWORD *)((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 56);
  v8 = lpPathName;
  if ( (CreateDirectoryW(lpPathName, 0)
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(183)))
    && ((ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
           &lpPathName,
           L"\\%hs",
           a3),
         v8 = lpPathName,
         CreateDirectoryW(lpPathName, 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(183)))
    && ((Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
           v11,
           (unsigned int)&lpPathName,
           *v7,
           (_DWORD)a3,
           (__int64)a4),
         v8 = lpPathName,
         CreateDirectoryW(lpPathName, 0))
     || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(183))) )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&lpPathName, (__int64)L"\\", 1);
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
      v16 = L"NULL";
      v17 = a2;
      if ( !a2 )
        v17 = L"NULL";
      p_lpPathName = (LPCWSTR *)v17;
      v27 = (unsigned int)v15;
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
        p_lpPathName = &lpPathName;
        v27 = 4;
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
0x180027c84  push    rbp
0x180027c86  push    rbx
0x180027c87  push    rsi
0x180027c88  push    rdi
0x180027c89  push    r12
0x180027c8b  push    r13
0x180027c8d  push    r14
0x180027c8f  push    r15
0x180027c91  mov     rbp, rsp
0x180027c94  sub     rsp, 78h
0x180027c98  mov     rax, cs:__security_cookie
0x180027c9f  xor     rax, rsp
0x180027ca2  mov     [rbp+var_10], rax
0x180027ca6  mov     r12, r9
0x180027ca9  mov     r14, r8
0x180027cac  mov     rdi, rdx
0x180027caf  lea     r15, [rcx+38h]
0x180027cb3  mov     rdx, r15
0x180027cb6  lea     rcx, [rbp+lpPathName]
0x180027cba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027cbf  nop
0x180027cc0  xor     edx, edx; lpSecurityAttributes
0x180027cc2  mov     rbx, [rbp+lpPathName]
0x180027cc6  mov     rcx, rbx; lpPathName
0x180027cc9  call    cs:__imp_CreateDirectoryW
0x180027ccf  xor     r13d, r13d
0x180027cd2  test    eax, eax
0x180027cd4  jnz     short loc_180027D12
0x180027cd6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027cdb  mov     esi, eax
0x180027cdd  mov     ecx, 0B7h; unsigned int
0x180027ce2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180027ce7  cmp     esi, eax
0x180027ce9  jz      short loc_180027D12
0x180027ceb  lea     rdx, [rbx-18h]
0x180027cef  or      ecx, 0FFFFFFFFh
0x180027cf2  lock xadd [rdx+10h], ecx
0x180027cf7  sub     ecx, 1
0x180027cfa  jg      short loc_180027D0B
0x180027cfc  mov     rcx, [rdx]
0x180027cff  mov     rax, [rcx]
0x180027d02  mov     rax, [rax+8]
0x180027d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d0b  mov     eax, esi
0x180027d0d  jmp     loc_180027F1A
0x180027d12  mov     r8, r14
0x180027d15  lea     rdx, aHs_0; "\\%hs"
0x180027d1c  lea     rcx, [rbp+lpPathName]
0x180027d20  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180027d25  xor     edx, edx; lpSecurityAttributes
0x180027d27  mov     rbx, [rbp+lpPathName]
0x180027d2b  mov     rcx, rbx; lpPathName
0x180027d2e  call    cs:__imp_CreateDirectoryW
0x180027d34  test    eax, eax
0x180027d36  jnz     short loc_180027D4D
0x180027d38  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027d3d  mov     esi, eax
0x180027d3f  mov     ecx, 0B7h; unsigned int
0x180027d44  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180027d49  cmp     esi, eax
0x180027d4b  jnz     short loc_180027CEB
0x180027d4d  mov     [rsp+78h+var_58], r12
0x180027d52  mov     r9, r14
0x180027d55  mov     r8, [r15]
0x180027d58  lea     rdx, [rbp+lpPathName]
0x180027d5c  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x180027d61  xor     edx, edx; lpSecurityAttributes
0x180027d63  mov     rbx, [rbp+lpPathName]
0x180027d67  mov     rcx, rbx; lpPathName
0x180027d6a  call    cs:__imp_CreateDirectoryW
0x180027d70  test    eax, eax
0x180027d72  jnz     short loc_180027D8D
0x180027d74  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027d79  mov     esi, eax
0x180027d7b  mov     ecx, 0B7h; unsigned int
0x180027d80  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180027d85  cmp     esi, eax
0x180027d87  jnz     loc_180027CEB
0x180027d8d  mov     esi, 1
0x180027d92  mov     r8d, esi
0x180027d95  lea     rdx, StringValue; "\\"
0x180027d9c  lea     rcx, [rbp+lpPathName]
0x180027da0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180027da5  mov     rdx, r14
0x180027da8  lea     rcx, [rbp+lpPathName]
0x180027dac  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180027db1  mov     rbx, [rbp+lpPathName]
0x180027db5  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x180027dbc  jz      loc_180027E45
0x180027dc2  lea     ecx, [rsi+9]
0x180027dc5  test    rdi, rdi
0x180027dc8  jz      short loc_180027DE2
0x180027dca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027dce  inc     rax
0x180027dd1  cmp     [rdi+rax*2], r13w
0x180027dd6  jnz     short loc_180027DCE
0x180027dd8  lea     r8d, ds:2[rax*2]
0x180027de0  jmp     short loc_180027DE5
0x180027de2  mov     r8d, ecx
0x180027de5  lea     rdx, aNull; "NULL"
0x180027dec  mov     rax, rdi
0x180027def  test    rdi, rdi
0x180027df2  cmovz   rax, rdx
0x180027df6  mov     [rbp+var_30], rax
0x180027dfa  mov     dword ptr [rbp+var_28], r8d
0x180027dfe  mov     dword ptr [rbp+var_28+4], r13d
0x180027e02  test    rbx, rbx
0x180027e05  jz      short loc_180027E1F
0x180027e07  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027e0b  inc     rax
0x180027e0e  cmp     [rbx+rax*2], r13w
0x180027e13  jnz     short loc_180027E0B
0x180027e15  mov     rdx, rbx
0x180027e18  lea     ecx, ds:2[rax*2]
0x180027e1f  mov     [rbp+var_20], rdx
0x180027e23  mov     [rbp+var_18], ecx
0x180027e26  mov     [rbp+var_14], r13d
0x180027e2a  lea     rax, [rbp+var_40]
0x180027e2e  mov     [rsp+78h+var_58], rax
0x180027e33  mov     r9d, 3
0x180027e39  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x180027e40  call    McGenEventWrite_EventWriteTransfer
0x180027e45  xor     r8d, r8d; bFailIfExists
0x180027e48  mov     rdx, rbx; lpNewFileName
0x180027e4b  mov     rcx, rdi; lpExistingFileName
0x180027e4e  call    cs:__imp_CopyFileW
0x180027e54  test    eax, eax
0x180027e56  jnz     short loc_180027EBF
0x180027e58  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x180027e5f  jz      short loc_180027E94
0x180027e61  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027e66  mov     dword ptr [rbp+lpPathName], eax
0x180027e69  lea     rax, [rbp+lpPathName]
0x180027e6d  mov     [rbp+var_30], rax
0x180027e71  mov     [rbp+var_28], 4
0x180027e79  lea     rax, [rbp+var_40]
0x180027e7d  mov     [rsp+78h+var_58], rax
0x180027e82  mov     r9d, 2
0x180027e88  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180027e8f  call    McGenEventWrite_EventWriteTransfer
0x180027e94  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180027e99  mov     edi, eax
0x180027e9b  lea     rdx, [rbx-18h]
0x180027e9f  or      ecx, 0FFFFFFFFh
0x180027ea2  lock xadd [rdx+10h], ecx
0x180027ea7  sub     ecx, 1
0x180027eaa  jg      short loc_180027EBB
0x180027eac  mov     rcx, [rdx]
0x180027eaf  mov     r8, [rcx]
0x180027eb2  mov     rax, [r8+8]
0x180027eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ebb  mov     eax, edi
0x180027ebd  jmp     short loc_180027F1A
0x180027ebf  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x180027ec6  jz      short loc_180027EF8
0x180027ec8  mov     dword ptr [rbp+lpPathName], r13d
0x180027ecc  lea     rax, [rbp+lpPathName]
0x180027ed0  mov     [rbp+var_30], rax
0x180027ed4  mov     [rbp+var_28], 4
0x180027edc  lea     rax, [rbp+var_40]
0x180027ee0  mov     [rsp+78h+var_58], rax
0x180027ee5  mov     r9d, 2
0x180027eeb  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180027ef2  call    McGenEventWrite_EventWriteTransfer
0x180027ef7  nop
0x180027ef8  lea     rdx, [rbx-18h]
0x180027efc  or      eax, 0FFFFFFFFh
0x180027eff  lock xadd [rdx+10h], eax
0x180027f04  sub     eax, 1
0x180027f07  jg      short loc_180027F18
0x180027f09  mov     rcx, [rdx]
0x180027f0c  mov     rax, [rcx]
0x180027f0f  mov     rax, [rax+8]
0x180027f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f18  xor     eax, eax
0x180027f1a  mov     rcx, [rbp+var_10]
0x180027f1e  xor     rcx, rsp; StackCookie
0x180027f21  call    __security_check_cookie
0x180027f26  add     rsp, 78h
0x180027f2a  pop     r15
0x180027f2c  pop     r14
0x180027f2e  pop     r13
0x180027f30  pop     r12
0x180027f32  pop     rdi
0x180027f33  pop     rsi
0x180027f34  pop     rbx
0x180027f35  pop     rbp
0x180027f36  retn
```
