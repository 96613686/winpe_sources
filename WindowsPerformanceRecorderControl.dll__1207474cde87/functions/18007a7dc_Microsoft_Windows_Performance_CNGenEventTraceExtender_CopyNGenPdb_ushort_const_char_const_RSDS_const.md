# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x18007a7dc`
- end: `0x18007a96d`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007acb0`

## callees

- `0x18000829c`
- `0x180008330`
- `0x1800102d8`
- `0x1800128f8`
- `0x180021810`
- `0x18004b39c`
- `0x1800600a0`
- `0x18007a728`
- `0x18007a7dc`
- `0x18007aefc`
- `0x18007bcac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a818`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a856`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a895`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a818`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a856`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18007a895`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18007a906`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18007a906`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  _QWORD *v7; // r14
  unsigned int v8; // ebx
  int v9; // ecx
  __int64 v10; // rcx
  unsigned int Error; // eax
  __int64 v12; // rcx
  LPCWSTR lpPathName; // [rsp+60h] [rbp+8h] BYREF

  v7 = (_QWORD *)((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 56);
  if ( CreateDirectoryW(lpPathName, 0)
    || (v8 = ATL::AtlHresultFromLastError(), v8 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &lpPathName,
      L"\\%hs",
      a3);
    if ( CreateDirectoryW(lpPathName, 0)
      || (v8 = ATL::AtlHresultFromLastError(), v8 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        v9,
        (unsigned int)&lpPathName,
        *v7,
        (_DWORD)a3,
        (__int64)a4);
      if ( CreateDirectoryW(lpPathName, 0)
        || (v8 = ATL::AtlHresultFromLastError(), v8 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpPathName, L"\\");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
          &lpPathName,
          a3);
        if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            Microsoft_Windows_XPerfCore_ETWProvider_Context,
            TraceMerge_NGEN_CopyingPDB_Start,
            a2,
            lpPathName);
        if ( CopyFileW(a2, lpPathName, 0) )
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
            McTemplateU0q_EventWriteTransfer(v10, TraceMerge_NGEN_CopyingPDB_Stop, 0);
          v8 = 0;
        }
        else
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          {
            Error = ATL::AtlHresultFromLastError();
            McTemplateU0q_EventWriteTransfer(v12, TraceMerge_NGEN_CopyingPDB_Stop, Error);
          }
          v8 = ATL::AtlHresultFromLastError();
        }
      }
    }
  }
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpPathName);
  return v8;
}

```

## disassembly

```asm
0x18007a7dc  mov     rax, rsp
0x18007a7df  push    rsi
0x18007a7e0  push    rdi
0x18007a7e1  push    r14
0x18007a7e3  sub     rsp, 40h
0x18007a7e7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18007a7ef  mov     [rax+10h], rbx
0x18007a7f3  mov     [rax+18h], rbp
0x18007a7f7  mov     rbp, r9
0x18007a7fa  mov     rdi, r8
0x18007a7fd  mov     rsi, rdx
0x18007a800  lea     r14, [rcx+38h]
0x18007a804  mov     rdx, r14; void *
0x18007a807  lea     rcx, [rax+8]; void *
0x18007a80b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18007a810  nop
0x18007a811  xor     edx, edx; lpSecurityAttributes
0x18007a813  mov     rcx, [rsp+58h+lpPathName]; lpPathName
0x18007a818  call    cs:__imp_CreateDirectoryW
0x18007a81e  test    eax, eax
0x18007a820  jnz     short loc_18007A83B
0x18007a822  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007a827  mov     ebx, eax
0x18007a829  mov     ecx, 0B7h; unsigned int
0x18007a82e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007a833  cmp     ebx, eax
0x18007a835  jnz     loc_18007A94E
0x18007a83b  mov     r8, rdi
0x18007a83e  lea     rdx, aHs_0; "\\%hs"
0x18007a845  lea     rcx, [rsp+58h+lpPathName]
0x18007a84a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18007a84f  xor     edx, edx; lpSecurityAttributes
0x18007a851  mov     rcx, [rsp+58h+lpPathName]; lpPathName
0x18007a856  call    cs:__imp_CreateDirectoryW
0x18007a85c  test    eax, eax
0x18007a85e  jnz     short loc_18007A879
0x18007a860  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007a865  mov     ebx, eax
0x18007a867  mov     ecx, 0B7h; unsigned int
0x18007a86c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007a871  cmp     ebx, eax
0x18007a873  jnz     loc_18007A94E
0x18007a879  mov     [rsp+58h+var_38], rbp
0x18007a87e  mov     r9, rdi
0x18007a881  mov     r8, [r14]
0x18007a884  lea     rdx, [rsp+58h+lpPathName]
0x18007a889  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18007a88e  xor     edx, edx; lpSecurityAttributes
0x18007a890  mov     rcx, [rsp+58h+lpPathName]; lpPathName
0x18007a895  call    cs:__imp_CreateDirectoryW
0x18007a89b  test    eax, eax
0x18007a89d  jnz     short loc_18007A8B8
0x18007a89f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007a8a4  mov     ebx, eax
0x18007a8a6  mov     ecx, 0B7h; unsigned int
0x18007a8ab  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007a8b0  cmp     ebx, eax
0x18007a8b2  jnz     loc_18007A94E
0x18007a8b8  lea     rdx, SubBlock; "\\"
0x18007a8bf  lea     rcx, [rsp+58h+lpPathName]
0x18007a8c4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18007a8c9  mov     rdx, rdi
0x18007a8cc  lea     rcx, [rsp+58h+lpPathName]
0x18007a8d1  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18007a8d6  mov     bl, 1
0x18007a8d8  test    cs:Microsoft_Windows_XPerfCoreEnableBits, bl
0x18007a8de  jz      short loc_18007A8FB
0x18007a8e0  mov     r9, [rsp+58h+lpPathName]
0x18007a8e5  mov     r8, rsi
0x18007a8e8  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x18007a8ef  lea     rcx, Microsoft_Windows_XPerfCore_ETWProvider_Context
0x18007a8f6  call    McTemplateU0zz_EventWriteTransfer
0x18007a8fb  xor     r8d, r8d; bFailIfExists
0x18007a8fe  mov     rdx, [rsp+58h+lpPathName]; lpNewFileName
0x18007a903  mov     rcx, rsi; lpExistingFileName
0x18007a906  call    cs:__imp_CopyFileW
0x18007a90c  test    eax, eax
0x18007a90e  jnz     short loc_18007A935
0x18007a910  test    cs:Microsoft_Windows_XPerfCoreEnableBits, bl
0x18007a916  jz      short loc_18007A92C
0x18007a918  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007a91d  mov     r8d, eax
0x18007a920  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18007a927  call    McTemplateU0q_EventWriteTransfer
0x18007a92c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007a931  mov     ebx, eax
0x18007a933  jmp     short loc_18007A94E
0x18007a935  test    cs:Microsoft_Windows_XPerfCoreEnableBits, bl
0x18007a93b  jz      short loc_18007A94C
0x18007a93d  xor     r8d, r8d
0x18007a940  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x18007a947  call    McTemplateU0q_EventWriteTransfer
0x18007a94c  xor     ebx, ebx
0x18007a94e  lea     rcx, [rsp+58h+lpPathName]; this
0x18007a953  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007a958  mov     eax, ebx
0x18007a95a  mov     rbx, [rsp+58h+arg_8]
0x18007a95f  mov     rbp, [rsp+58h+arg_10]
0x18007a964  add     rsp, 40h
0x18007a968  pop     r14
0x18007a96a  pop     rdi
0x18007a96b  pop     rsi
0x18007a96c  retn
```
