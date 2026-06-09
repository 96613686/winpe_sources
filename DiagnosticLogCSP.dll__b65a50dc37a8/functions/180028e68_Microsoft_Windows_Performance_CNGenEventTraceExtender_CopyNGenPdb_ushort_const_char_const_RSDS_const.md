# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x180028e68`
- end: `0x180029134`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `716`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002954c`

## callees

- `0x180001b90`
- `0x1800161d4`
- `0x180016274`
- `0x18001629c`
- `0x18001ec68`
- `0x180023180`
- `0x18002847c`
- `0x180028e68`
- `0x1800298b0`
- `0x18002a904`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028ead`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028f18`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028f5a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028ead`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028f18`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028f5a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180029044`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180029044`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
           *v7,
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
0x180028e68  push    rbp
0x180028e6a  push    rbx
0x180028e6b  push    rsi
0x180028e6c  push    rdi
0x180028e6d  push    r12
0x180028e6f  push    r13
0x180028e71  push    r14
0x180028e73  push    r15
0x180028e75  mov     rbp, rsp
0x180028e78  sub     rsp, 78h
0x180028e7c  mov     rax, cs:__security_cookie
0x180028e83  xor     rax, rsp
0x180028e86  mov     [rbp+var_10], rax
0x180028e8a  mov     r12, r9
0x180028e8d  mov     r14, r8
0x180028e90  mov     rdi, rdx
0x180028e93  lea     r15, [rcx+38h]
0x180028e97  mov     rdx, r15
0x180028e9a  lea     rcx, [rbp+lpPathName]
0x180028e9e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180028ea3  nop
0x180028ea4  xor     edx, edx; lpSecurityAttributes
0x180028ea6  mov     rbx, [rbp+lpPathName]
0x180028eaa  mov     rcx, rbx; lpPathName
0x180028ead  call    cs:__imp_CreateDirectoryW
0x180028eb4  nop     dword ptr [rax+rax+00h]
0x180028eb9  xor     r13d, r13d
0x180028ebc  test    eax, eax
0x180028ebe  jnz     short loc_180028EFC
0x180028ec0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028ec5  mov     esi, eax
0x180028ec7  mov     ecx, 0B7h; unsigned int
0x180028ecc  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180028ed1  cmp     esi, eax
0x180028ed3  jz      short loc_180028EFC
0x180028ed5  lea     rdx, [rbx-18h]
0x180028ed9  or      ecx, 0FFFFFFFFh
0x180028edc  lock xadd [rdx+10h], ecx
0x180028ee1  sub     ecx, 1
0x180028ee4  jg      short loc_180028EF5
0x180028ee6  mov     rcx, [rdx]
0x180028ee9  mov     rax, [rcx]
0x180028eec  mov     rax, [rax+8]
0x180028ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ef5  mov     eax, esi
0x180028ef7  jmp     loc_180029116
0x180028efc  mov     r8, r14
0x180028eff  lea     rdx, aHs_0; "\\%hs"
0x180028f06  lea     rcx, [rbp+lpPathName]
0x180028f0a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180028f0f  xor     edx, edx; lpSecurityAttributes
0x180028f11  mov     rbx, [rbp+lpPathName]
0x180028f15  mov     rcx, rbx; lpPathName
0x180028f18  call    cs:__imp_CreateDirectoryW
0x180028f1f  nop     dword ptr [rax+rax+00h]
0x180028f24  test    eax, eax
0x180028f26  jnz     short loc_180028F3D
0x180028f28  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028f2d  mov     esi, eax
0x180028f2f  mov     ecx, 0B7h; unsigned int
0x180028f34  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180028f39  cmp     esi, eax
0x180028f3b  jnz     short loc_180028ED5
0x180028f3d  mov     [rsp+78h+var_58], r12
0x180028f42  mov     r9, r14
0x180028f45  mov     r8, [r15]
0x180028f48  lea     rdx, [rbp+lpPathName]
0x180028f4c  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x180028f51  xor     edx, edx; lpSecurityAttributes
0x180028f53  mov     rbx, [rbp+lpPathName]
0x180028f57  mov     rcx, rbx; lpPathName
0x180028f5a  call    cs:__imp_CreateDirectoryW
0x180028f61  nop     dword ptr [rax+rax+00h]
0x180028f66  test    eax, eax
0x180028f68  jnz     short loc_180028F83
0x180028f6a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028f6f  mov     esi, eax
0x180028f71  mov     ecx, 0B7h; unsigned int
0x180028f76  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180028f7b  cmp     esi, eax
0x180028f7d  jnz     loc_180028ED5
0x180028f83  mov     esi, 1
0x180028f88  mov     r8d, esi
0x180028f8b  lea     rdx, StringValue; "\\"
0x180028f92  lea     rcx, [rbp+lpPathName]
0x180028f96  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028f9b  mov     rdx, r14
0x180028f9e  lea     rcx, [rbp+lpPathName]
0x180028fa2  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180028fa7  mov     rbx, [rbp+lpPathName]
0x180028fab  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x180028fb2  jz      loc_18002903B
0x180028fb8  lea     ecx, [rsi+9]
0x180028fbb  test    rdi, rdi
0x180028fbe  jz      short loc_180028FD8
0x180028fc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028fc4  inc     rax
0x180028fc7  cmp     [rdi+rax*2], r13w
0x180028fcc  jnz     short loc_180028FC4
0x180028fce  lea     r8d, ds:2[rax*2]
0x180028fd6  jmp     short loc_180028FDB
0x180028fd8  mov     r8d, ecx
0x180028fdb  lea     rdx, aNull; "NULL"
0x180028fe2  mov     rax, rdi
0x180028fe5  test    rdi, rdi
0x180028fe8  cmovz   rax, rdx
0x180028fec  mov     [rbp+var_30], rax
0x180028ff0  mov     dword ptr [rbp+var_28], r8d
0x180028ff4  mov     dword ptr [rbp+var_28+4], r13d
0x180028ff8  test    rbx, rbx
0x180028ffb  jz      short loc_180029015
0x180028ffd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029001  inc     rax
0x180029004  cmp     [rbx+rax*2], r13w
0x180029009  jnz     short loc_180029001
0x18002900b  mov     rdx, rbx
0x18002900e  lea     ecx, ds:2[rax*2]
0x180029015  mov     [rbp+var_20], rdx
0x180029019  mov     [rbp+var_18], ecx
0x18002901c  mov     [rbp+var_14], r13d
0x180029020  lea     rax, [rbp+var_40]
0x180029024  mov     [rsp+78h+var_58], rax
0x180029029  mov     r9d, 3
0x18002902f  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x180029036  call    McGenEventWrite_EventWriteTransfer
0x18002903b  xor     r8d, r8d; bFailIfExists
0x18002903e  mov     rdx, rbx; lpNewFileName
0x180029041  mov     rcx, rdi; lpExistingFileName
0x180029044  call    cs:__imp_CopyFileW
0x18002904b  nop     dword ptr [rax+rax+00h]
0x180029050  test    eax, eax
0x180029052  jnz     short loc_1800290BB
0x180029054  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x18002905b  jz      short loc_180029090
0x18002905d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180029062  mov     dword ptr [rbp+lpPathName], eax
0x180029065  lea     rax, [rbp+lpPathName]
0x180029069  mov     [rbp+var_30], rax
0x18002906d  mov     [rbp+var_28], 4
0x180029075  lea     rax, [rbp+var_40]
0x180029079  mov     [rsp+78h+var_58], rax
0x18002907e  mov     r9d, 2
0x180029084  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18002908b  call    McGenEventWrite_EventWriteTransfer
0x180029090  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180029095  mov     edi, eax
0x180029097  lea     rdx, [rbx-18h]
0x18002909b  or      ecx, 0FFFFFFFFh
0x18002909e  lock xadd [rdx+10h], ecx
0x1800290a3  sub     ecx, 1
0x1800290a6  jg      short loc_1800290B7
0x1800290a8  mov     rcx, [rdx]
0x1800290ab  mov     r8, [rcx]
0x1800290ae  mov     rax, [r8+8]
0x1800290b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290b7  mov     eax, edi
0x1800290b9  jmp     short loc_180029116
0x1800290bb  test    cs:Microsoft_Windows_XPerfCoreEnableBits, sil
0x1800290c2  jz      short loc_1800290F4
0x1800290c4  mov     dword ptr [rbp+lpPathName], r13d
0x1800290c8  lea     rax, [rbp+lpPathName]
0x1800290cc  mov     [rbp+var_30], rax
0x1800290d0  mov     [rbp+var_28], 4
0x1800290d8  lea     rax, [rbp+var_40]
0x1800290dc  mov     [rsp+78h+var_58], rax
0x1800290e1  mov     r9d, 2
0x1800290e7  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x1800290ee  call    McGenEventWrite_EventWriteTransfer
0x1800290f3  nop
0x1800290f4  lea     rdx, [rbx-18h]
0x1800290f8  or      eax, 0FFFFFFFFh
0x1800290fb  lock xadd [rdx+10h], eax
0x180029100  sub     eax, 1
0x180029103  jg      short loc_180029114
0x180029105  mov     rcx, [rdx]
0x180029108  mov     rax, [rcx]
0x18002910b  mov     rax, [rax+8]
0x18002910f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029114  xor     eax, eax
0x180029116  mov     rcx, [rbp+var_10]
0x18002911a  xor     rcx, rsp; StackCookie
0x18002911d  call    __security_check_cookie
0x180029122  add     rsp, 78h
0x180029126  pop     r15
0x180029128  pop     r14
0x18002912a  pop     r13
0x18002912c  pop     r12
0x18002912e  pop     rdi
0x18002912f  pop     rsi
0x180029130  pop     rbx
0x180029131  pop     rbp
0x180029132  retn
```
