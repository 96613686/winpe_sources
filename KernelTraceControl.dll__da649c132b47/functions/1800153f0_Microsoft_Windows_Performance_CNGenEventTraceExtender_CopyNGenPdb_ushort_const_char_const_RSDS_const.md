# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x1800153f0`
- end: `0x1800155bb`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800150e8`

## callees

- `0x1800067f0`
- `0x180006960`
- `0x18000e858`
- `0x18000f560`
- `0x180010e6c`
- `0x180013d94`
- `0x180013e4c`
- `0x1800153f0`
- `0x1800155bc`
- `0x180015a08`
- `0x180027910`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180015436`
- `KERNEL32!CreateDirectoryW` at `0x18001547a`
- `KERNEL32!CreateDirectoryW` at `0x1800154bd`
- `KERNEL32!CreateDirectoryW` at `0x180015436`
- `KERNEL32!CreateDirectoryW` at `0x18001547a`
- `KERNEL32!CreateDirectoryW` at `0x1800154bd`
- `KERNEL32!CopyFileW` at `0x180015534`
- `KERNEL32!CopyFileW` at `0x180015534`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  const WCHAR *v8; // rbx
  unsigned int v9; // edi
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int Error; // eax
  __int64 v16; // rcx
  LPCWSTR lpPathName; // [rsp+70h] [rbp+8h] BYREF

  v8 = (const WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)this + 7) - 24LL) + 24);
  lpPathName = v8;
  if ( CreateDirectoryW(v8, 0)
    || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &lpPathName,
      L"\\%hs",
      a3);
    v8 = lpPathName;
    if ( CreateDirectoryW(lpPathName, 0)
      || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        v10,
        (unsigned int)&lpPathName,
        *((_QWORD *)this + 7),
        (_DWORD)a3,
        (__int64)a4);
      v8 = lpPathName;
      if ( CreateDirectoryW(lpPathName, 0)
        || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
      {
        v11 = -1;
        do
          ++v11;
        while ( SubBlock[v11] );
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpPathName, L"\\", (unsigned int)v11);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
          &lpPathName,
          a3);
        v8 = lpPathName;
        if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          Template_zz(v13, v12, a2, lpPathName);
        if ( CopyFileW(a2, v8, 0) )
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
            Template_q(v14, TraceMerge_NGEN_CopyingPDB_Stop, 0);
          v9 = 0;
        }
        else
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          {
            Error = ATL::AtlHresultFromLastError();
            Template_q(v16, TraceMerge_NGEN_CopyingPDB_Stop, Error);
          }
          v9 = ATL::AtlHresultFromLastError();
        }
      }
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  return v9;
}

```

## disassembly

```asm
0x1800153f0  mov     rax, rsp
0x1800153f3  push    rsi
0x1800153f4  push    rdi
0x1800153f5  push    r12
0x1800153f7  push    r14
0x1800153f9  push    r15
0x1800153fb  sub     rsp, 40h
0x1800153ff  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180015407  mov     [rax+10h], rbx
0x18001540b  mov     [rax+18h], rbp
0x18001540f  mov     r15, r9
0x180015412  mov     rsi, r8
0x180015415  mov     rbp, rdx
0x180015418  mov     r14, rcx
0x18001541b  mov     rcx, [rcx+38h]
0x18001541f  sub     rcx, 18h
0x180015423  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180015428  lea     rbx, [rax+18h]
0x18001542c  mov     [rsp+68h+lpPathName], rbx
0x180015431  xor     edx, edx; lpSecurityAttributes
0x180015433  mov     rcx, rbx; lpPathName
0x180015436  call    cs:__imp_CreateDirectoryW
0x18001543c  xor     r12d, r12d
0x18001543f  test    eax, eax
0x180015441  jnz     short loc_18001545C
0x180015443  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015448  mov     edi, eax
0x18001544a  mov     ecx, 0B7h; unsigned int
0x18001544f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180015454  cmp     edi, eax
0x180015456  jnz     loc_18001557F
0x18001545c  mov     r8, rsi
0x18001545f  lea     rdx, aHs_0; "\\%hs"
0x180015466  lea     rcx, [rsp+68h+lpPathName]
0x18001546b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180015470  xor     edx, edx; lpSecurityAttributes
0x180015472  mov     rbx, [rsp+68h+lpPathName]
0x180015477  mov     rcx, rbx; lpPathName
0x18001547a  call    cs:__imp_CreateDirectoryW
0x180015480  test    eax, eax
0x180015482  jnz     short loc_18001549D
0x180015484  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015489  mov     edi, eax
0x18001548b  mov     ecx, 0B7h; unsigned int
0x180015490  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180015495  cmp     edi, eax
0x180015497  jnz     loc_18001557F
0x18001549d  mov     [rsp+68h+var_48], r15
0x1800154a2  mov     r9, rsi
0x1800154a5  mov     r8, [r14+38h]
0x1800154a9  lea     rdx, [rsp+68h+lpPathName]
0x1800154ae  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x1800154b3  xor     edx, edx; lpSecurityAttributes
0x1800154b5  mov     rbx, [rsp+68h+lpPathName]
0x1800154ba  mov     rcx, rbx; lpPathName
0x1800154bd  call    cs:__imp_CreateDirectoryW
0x1800154c3  test    eax, eax
0x1800154c5  jnz     short loc_1800154E0
0x1800154c7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800154cc  mov     edi, eax
0x1800154ce  mov     ecx, 0B7h; unsigned int
0x1800154d3  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800154d8  cmp     edi, eax
0x1800154da  jnz     loc_18001557F
0x1800154e0  lea     rdx, SubBlock; "\\"
0x1800154e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800154eb  inc     rax
0x1800154ee  cmp     [rdx+rax*2], r12w
0x1800154f3  jnz     short loc_1800154EB
0x1800154f5  mov     r8d, eax
0x1800154f8  lea     rcx, [rsp+68h+lpPathName]
0x1800154fd  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180015502  mov     rdx, rsi
0x180015505  lea     rcx, [rsp+68h+lpPathName]
0x18001550a  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18001550f  mov     rbx, [rsp+68h+lpPathName]
0x180015514  mov     dil, 1
0x180015517  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x18001551e  jz      short loc_18001552B
0x180015520  mov     r9, rbx
0x180015523  mov     r8, rbp
0x180015526  call    Template_zz
0x18001552b  xor     r8d, r8d; bFailIfExists
0x18001552e  mov     rdx, rbx; lpNewFileName
0x180015531  mov     rcx, rbp; lpExistingFileName
0x180015534  call    cs:__imp_CopyFileW
0x18001553a  test    eax, eax
0x18001553c  jnz     short loc_180015564
0x18001553e  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x180015545  jz      short loc_18001555B
0x180015547  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001554c  mov     r8d, eax
0x18001554f  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180015556  call    Template_q
0x18001555b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015560  mov     edi, eax
0x180015562  jmp     short loc_18001557F
0x180015564  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x18001556b  jz      short loc_18001557C
0x18001556d  xor     r8d, r8d
0x180015570  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180015577  call    Template_q
0x18001557c  mov     edi, r12d
0x18001557f  lea     rdx, [rbx-18h]
0x180015583  or      ecx, 0FFFFFFFFh
0x180015586  lock xadd [rdx+10h], ecx
0x18001558b  sub     ecx, 1
0x18001558e  jg      short loc_1800155A0
0x180015590  mov     rcx, [rdx]
0x180015593  mov     r8, [rcx]
0x180015596  mov     rax, [r8+8]
0x18001559a  call    cs:__guard_dispatch_icall_fptr
0x1800155a0  mov     eax, edi
0x1800155a2  lea     r11, [rsp+68h+var_28]
0x1800155a7  mov     rbx, [r11+38h]
0x1800155ab  mov     rbp, [r11+40h]
0x1800155af  mov     rsp, r11
0x1800155b2  pop     r15
0x1800155b4  pop     r14
0x1800155b6  pop     r12
0x1800155b8  pop     rdi
0x1800155b9  pop     rsi
0x1800155ba  retn
```
