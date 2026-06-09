# UWAInstallWork::_DoDirectDownload(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800ef480`
- end: `0x1800ef8e5`
- name: `?_DoDirectDownload@UWAInstallWork@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@1@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ef8ec`

## callees

- `0x180009ea0`
- `0x180012368`
- `0x1800123f8`
- `0x1800127c8`
- `0x18001c414`
- `0x18001c964`
- `0x1800228c4`
- `0x18002865c`
- `0x180034874`
- `0x1800726a0`
- `0x18007f214`
- `0x180084010`
- `0x1800ef480`
- `0x1800fd0cc`
- `0x1800fe30c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ef580`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800ef580`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef6dc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef6dc`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800ef55c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800ef55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef4f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef64d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef4f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef64d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef806`

## string_xrefs

- `0x1800ef52e`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef67b`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef6c3`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef73f`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef79b`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef846`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef521`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef66e`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef6b6`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef732`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef78e`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef839`: `UWAInstallWork::_DoDirectDownload`
- `0x1800ef721`: `Deleting temporary file %s from download. File name: %s`
- `0x1800ef77e`: `Failed to get temp file path for direct download.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall UWAInstallWork::_DoDirectDownload(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v4; // rbx
  bool v8; // r12
  _WORD *v9; // rcx
  _WORD *v10; // rcx
  __int64 v11; // r14
  _QWORD *v12; // r12
  PCWSTR v13; // rax
  int FileWithProgress; // r12d
  const unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // rax
  const wchar_t *v17; // rbx
  const unsigned __int16 *v18; // rax
  unsigned int Error; // ebx
  const unsigned __int16 *v21; // rax
  unsigned __int16 *StringRawBuffer; // [rsp+38h] [rbp-4B0h]
  unsigned __int16 *v23; // [rsp+38h] [rbp-4B0h]
  __int64 v24; // [rsp+50h] [rbp-498h] BYREF
  _BYTE v25[16]; // [rsp+58h] [rbp-490h] BYREF
  __int64 v26; // [rsp+68h] [rbp-480h]
  _QWORD *v27; // [rsp+70h] [rbp-478h]
  WCHAR TempFileName[264]; // [rsp+80h] [rbp-468h] BYREF
  WCHAR PathName[264]; // [rsp+290h] [rbp-258h] BYREF

  v4 = a4;
  v26 = a1;
  v27 = a2;
  v8 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v9 = (_WORD *)a3;
  else
    v9 = *(_WORD **)a3;
  *v9 = 0;
  a4[2] = 0;
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_WORD *)*a4;
  *v10 = 0;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
  v11 = -1;
  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0x12F9u,
    "UWAInstallWork::_DoDirectDownload",
    -1,
    L"[Start] _DoDirectDownload, Starting direct download for single TLU.",
    (const char *)(a1 + 304),
    StringRawBuffer);
  CallerContext::ImpersonateUser((_QWORD *)(a1 + 152), (__int64)v25);
  if ( (unsigned int)GetTempPath2W(260, PathName) )
    v8 = GetTempFileNameW(PathName, L"tlu", 0, TempFileName) != 0;
  TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v25);
  if ( v8 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScanEnhancement>::GetImpl'::`2'::impl) )
    {
      wil::AcquireSRWLockExclusive(&v24, a1 + 1048);
      std::wstring::operator=(a1 + 952, a2);
      *(_BYTE *)(a1 + 984) = 0;
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v24);
    }
    if ( a2[3] <= 7u )
      v12 = a2;
    else
      v12 = (_QWORD *)*a2;
    v13 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
    FileWithProgress = Http_GetFileWithProgress(v13, v12, TempFileName, a1 + 1272);
    if ( *(_DWORD *)(a1 + 1272) && FileWithProgress == -2147467260 )
    {
      v15 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x131Eu,
        "UWAInstallWork::_DoDirectDownload",
        -1,
        L"Direct download was aborted by user.",
        (const char *)(a1 + 304),
        v15);
    }
    else if ( FileWithProgress >= 0 )
    {
      if ( v4[3] > 7u )
        v4 = (_QWORD *)*v4;
      v21 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x1323u,
        "UWAInstallWork::_DoDirectDownload",
        -1,
        L"Direct download succeeded. Filename: %s. packageName: %s",
        (const char *)(a1 + 304),
        v21,
        TempFileName,
        v4);
      do
        ++v11;
      while ( TempFileName[v11] );
      std::wstring::_Assign<unsigned short>(a3, TempFileName);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScanEnhancement>::GetImpl'::`2'::impl) )
      {
        wil::AcquireSRWLockExclusive(v25, a1 + 1048);
        std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<UpdateMetadata>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<UpdateMetadata>>>,0>>::find(
          a1 + 856,
          &v24,
          a1 + 952);
        if ( v24 != *(_QWORD *)(a1 + 864) )
          *(_QWORD *)(a1 + 944) += *(_QWORD *)(v24 + 48);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v25);
      }
      goto LABEL_21;
    }
    v16 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
    LogSimpleMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x1333u,
      "UWAInstallWork::_DoDirectDownload",
      FileWithProgress,
      L"Direct download failed with error",
      (const char *)(a1 + 304),
      v16);
    v17 = L"succeeded";
    if ( !DeleteFileW(TempFileName) )
      v17 = L"failed";
    v18 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x1335u,
      "UWAInstallWork::_DoDirectDownload",
      -1,
      L"Deleting temporary file %s from download. File name: %s",
      (const char *)(a1 + 304),
      v18,
      v17,
      TempFileName);
LABEL_21:
    std::wstring::_Tidy_deallocate(a2);
    return (unsigned int)FileWithProgress;
  }
  Error = ResultFromKnownLastError();
  v23 = (unsigned __int16 *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
  LogSimpleMessage(
    1u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0x133Du,
    "UWAInstallWork::_DoDirectDownload",
    Error,
    L"Failed to get temp file path for direct download.",
    (const char *)(a1 + 304),
    v23);
  std::wstring::_Tidy_deallocate(a2);
  return Error;
}

```

## disassembly

```asm
0x1800ef480  push    rbx
0x1800ef482  push    rsi
0x1800ef483  push    rdi
0x1800ef484  push    r12
0x1800ef486  push    r13
0x1800ef488  push    r14
0x1800ef48a  push    r15
0x1800ef48c  sub     rsp, 4B0h
0x1800ef493  mov     rax, cs:__security_cookie
0x1800ef49a  xor     rax, rsp
0x1800ef49d  mov     [rsp+4E8h+var_48], rax
0x1800ef4a5  mov     rbx, r9
0x1800ef4a8  mov     r15, r8
0x1800ef4ab  mov     rsi, rdx
0x1800ef4ae  mov     rdi, rcx
0x1800ef4b1  mov     [rsp+4E8h+var_480], rcx
0x1800ef4b6  mov     [rsp+4E8h+var_478], rdx
0x1800ef4bb  xor     r12d, r12d
0x1800ef4be  mov     [r8+10h], r12
0x1800ef4c2  cmp     qword ptr [r8+18h], 7
0x1800ef4c7  jbe     short loc_1800EF4CE
0x1800ef4c9  mov     rcx, [r8]
0x1800ef4cc  jmp     short loc_1800EF4D1
0x1800ef4ce  mov     rcx, r15
0x1800ef4d1  mov     [rcx], r12w
0x1800ef4d5  mov     [r9+10h], r12
0x1800ef4d9  cmp     qword ptr [r9+18h], 7
0x1800ef4de  jbe     short loc_1800EF4E5
0x1800ef4e0  mov     rcx, [r9]
0x1800ef4e3  jmp     short loc_1800EF4E8
0x1800ef4e5  mov     rcx, rbx
0x1800ef4e8  mov     [rcx], r12w
0x1800ef4ec  xor     edx, edx; length
0x1800ef4ee  mov     rcx, [rdi+1D8h]; string
0x1800ef4f5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef4fb  lea     r13, [rdi+130h]
0x1800ef502  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef507  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef50c  lea     rax, aStartDodirectd_0; "[Start] _DoDirectDownload, Starting dir"...
0x1800ef513  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef518  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ef51c  mov     [rsp+4E8h+var_4C8], r14d; int
0x1800ef521  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef528  mov     r8d, 12F9h; unsigned int
0x1800ef52e  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef535  lea     ecx, [r14+4]; unsigned int
0x1800ef539  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef53e  lea     rcx, [rdi+98h]
0x1800ef545  lea     rdx, [rsp+4E8h+var_490]
0x1800ef54a  call    ?ImpersonateUser@CallerContext@@QEAA?AVImpersonateContext@TokenHelpers@@XZ; CallerContext::ImpersonateUser(void)
0x1800ef54f  lea     rdx, [rsp+4E8h+PathName]
0x1800ef557  mov     ecx, 104h
0x1800ef55c  call    cs:__imp_GetTempPath2W
0x1800ef562  test    eax, eax
0x1800ef564  jz      short loc_1800EF58C
0x1800ef566  lea     r9, [rsp+4E8h+TempFileName]; lpTempFileName
0x1800ef56e  xor     r8d, r8d; uUnique
0x1800ef571  lea     rdx, PrefixString; "tlu"
0x1800ef578  lea     rcx, [rsp+4E8h+PathName]; lpPathName
0x1800ef580  call    cs:__imp_GetTempFileNameW
0x1800ef586  test    eax, eax
0x1800ef588  setnz   r12b
0x1800ef58c  lea     rcx, [rsp+4E8h+var_490]; this
0x1800ef591  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x1800ef596  test    r12b, r12b
0x1800ef599  jz      loc_1800EF75E
0x1800ef59f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement> `wil::Feature<__WilFeatureTraits_Feature_BackupScanEnhancement>::GetImpl(void)'::`2'::impl
0x1800ef5a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement>::__private_IsEnabled(void)
0x1800ef5ab  xor     r12d, r12d
0x1800ef5ae  test    al, al
0x1800ef5b0  jz      short loc_1800EF5E4
0x1800ef5b2  lea     rdx, [rdi+418h]
0x1800ef5b9  lea     rcx, [rsp+4E8h+var_498]
0x1800ef5be  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800ef5c3  nop
0x1800ef5c4  lea     rcx, [rdi+3B8h]
0x1800ef5cb  mov     rdx, rsi
0x1800ef5ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ef5d3  mov     [rdi+3D8h], r12b
0x1800ef5da  lea     rcx, [rsp+4E8h+var_498]; this
0x1800ef5df  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800ef5e4  cmp     qword ptr [rsi+18h], 7
0x1800ef5e9  jbe     short loc_1800EF5F0
0x1800ef5eb  mov     r12, [rsi]
0x1800ef5ee  jmp     short loc_1800EF5F3
0x1800ef5f0  mov     r12, rsi
0x1800ef5f3  xor     edx, edx; length
0x1800ef5f5  mov     rcx, [rdi+1D8h]; string
0x1800ef5fc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef602  lea     r9, [rdi+4F8h]
0x1800ef609  mov     [rsp+4E8h+var_4B8], rbx
0x1800ef60e  mov     [rsp+4E8h+var_4C0], rdi
0x1800ef613  lea     r8, [rsp+4E8h+TempFileName]
0x1800ef61b  mov     rdx, r12
0x1800ef61e  mov     rcx, rax
0x1800ef621  call    ?Http_GetFileWithProgress@@YAJPEBG00PEAHP6AXPEAXI_K3@Z2AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Http_GetFileWithProgress(ushort const *,ushort const *,ushort const *,int *,void (*)(void *,uint,unsigned __int64,unsigned __int64),void *,std::wstring &)
0x1800ef626  mov     r12d, eax
0x1800ef629  xor     eax, eax
0x1800ef62b  cmp     [rdi+4F8h], eax
0x1800ef631  jz      loc_1800EF7EA
0x1800ef637  cmp     r12d, 80004004h
0x1800ef63e  jnz     loc_1800EF7EA
0x1800ef644  xor     edx, edx; length
0x1800ef646  mov     rcx, [rdi+1D8h]; string
0x1800ef64d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef653  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef658  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef65d  lea     rax, aDirectDownload; "Direct download was aborted by user."
0x1800ef664  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef669  mov     [rsp+4E8h+var_4C8], r14d; int
0x1800ef66e  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef675  mov     r8d, 131Eh; unsigned int
0x1800ef67b  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef682  mov     ecx, 3; unsigned int
0x1800ef687  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef68c  xor     edx, edx; length
0x1800ef68e  mov     rcx, [rdi+1D8h]; string
0x1800ef695  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef69b  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef6a0  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef6a5  lea     rax, aDirectDownload_0; "Direct download failed with error"
0x1800ef6ac  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef6b1  mov     [rsp+4E8h+var_4C8], r12d; int
0x1800ef6b6  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef6bd  mov     r8d, 1333h; unsigned int
0x1800ef6c3  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef6ca  mov     ecx, 1; unsigned int
0x1800ef6cf  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef6d4  lea     rcx, [rsp+4E8h+TempFileName]; lpFileName
0x1800ef6dc  call    cs:__imp_DeleteFileW
0x1800ef6e2  lea     rcx, aFailed; "failed"
0x1800ef6e9  lea     rbx, aSucceeded_0; "succeeded"
0x1800ef6f0  test    eax, eax
0x1800ef6f2  cmovz   rbx, rcx
0x1800ef6f6  xor     edx, edx; length
0x1800ef6f8  mov     rcx, [rdi+1D8h]; string
0x1800ef6ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef705  lea     rcx, [rsp+4E8h+TempFileName]
0x1800ef70d  mov     [rsp+4E8h+var_4A0], rcx
0x1800ef712  mov     [rsp+4E8h+var_4A8], rbx
0x1800ef717  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef71c  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef721  lea     rax, aDeletingTempor_0; "Deleting temporary file %s from downloa"...
0x1800ef728  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef72d  mov     [rsp+4E8h+var_4C8], r14d; int
0x1800ef732  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef739  mov     r8d, 1335h; unsigned int
0x1800ef73f  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef746  mov     ecx, 3; unsigned int
0x1800ef74b  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800ef750  nop
0x1800ef751  mov     rcx, rsi
0x1800ef754  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ef759  mov     eax, r12d
0x1800ef75c  jmp     short loc_1800EF7C7
0x1800ef75e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ef763  mov     ebx, eax
0x1800ef765  xor     edx, edx; length
0x1800ef767  mov     rcx, [rdi+1D8h]; string
0x1800ef76e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef774  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef779  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef77e  lea     rax, aFailedToGetTem; "Failed to get temp file path for direct"...
0x1800ef785  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef78a  mov     [rsp+4E8h+var_4C8], ebx; int
0x1800ef78e  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef795  mov     r8d, 133Dh; unsigned int
0x1800ef79b  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef7a2  mov     ecx, 1; unsigned int
0x1800ef7a7  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef7ac  nop
0x1800ef7ad  mov     rcx, rsi
0x1800ef7b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ef7b5  mov     eax, ebx
0x1800ef7b7  jmp     short loc_1800EF7C7
0x1800ef7b9  mov     rcx, [rsp+4E8h+var_478]
0x1800ef7be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ef7c3  mov     eax, dword ptr [rsp+4E8h+var_498]
0x1800ef7c7  mov     rcx, [rsp+4E8h+var_48]
0x1800ef7cf  xor     rcx, rsp; StackCookie
0x1800ef7d2  call    __security_check_cookie
0x1800ef7d7  add     rsp, 4B0h
0x1800ef7de  pop     r15
0x1800ef7e0  pop     r14
0x1800ef7e2  pop     r13
0x1800ef7e4  pop     r12
0x1800ef7e6  pop     rdi
0x1800ef7e7  pop     rsi
0x1800ef7e8  pop     rbx
0x1800ef7e9  retn
0x1800ef7ea  test    r12d, r12d
0x1800ef7ed  js      loc_1800EF68C
0x1800ef7f3  cmp     qword ptr [rbx+18h], 7
0x1800ef7f8  jbe     short loc_1800EF7FD
0x1800ef7fa  mov     rbx, [rbx]
0x1800ef7fd  xor     edx, edx; length
0x1800ef7ff  mov     rcx, [rdi+1D8h]; string
0x1800ef806  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef80c  mov     [rsp+4E8h+var_4A0], rbx
0x1800ef811  lea     r8, [rsp+4E8h+TempFileName]
0x1800ef819  mov     [rsp+4E8h+var_4A8], r8
0x1800ef81e  mov     [rsp+4E8h+var_4B0], rax; unsigned __int16 *
0x1800ef823  mov     [rsp+4E8h+var_4B8], r13; char *
0x1800ef828  lea     rax, aDirectDownload_2; "Direct download succeeded. Filename: %s"...
0x1800ef82f  mov     [rsp+4E8h+var_4C0], rax; unsigned __int16 *
0x1800ef834  mov     [rsp+4E8h+var_4C8], r14d; int
0x1800ef839  lea     r9, aUwainstallwork_36; "UWAInstallWork::_DoDirectDownload"
0x1800ef840  mov     r8d, 1323h; unsigned int
0x1800ef846  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef84d  mov     ecx, 3; unsigned int
0x1800ef852  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800ef857  lea     rax, [rsp+4E8h+TempFileName]
0x1800ef85f  xor     ebx, ebx
0x1800ef861  inc     r14
0x1800ef864  cmp     [rax+r14*2], bx
0x1800ef869  jnz     short loc_1800EF861
0x1800ef86b  mov     r8, r14
0x1800ef86e  lea     rdx, [rsp+4E8h+TempFileName]
0x1800ef876  mov     rcx, r15
0x1800ef879  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ef87e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement> `wil::Feature<__WilFeatureTraits_Feature_BackupScanEnhancement>::GetImpl(void)'::`2'::impl
0x1800ef885  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScanEnhancement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScanEnhancement>::__private_IsEnabled(void)
0x1800ef88a  test    al, al
0x1800ef88c  jz      loc_1800EF751
0x1800ef892  lea     rdx, [rdi+418h]
0x1800ef899  lea     rcx, [rsp+4E8h+var_490]
0x1800ef89e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800ef8a3  lea     r8, [rdi+3B8h]
0x1800ef8aa  lea     rcx, [rdi+358h]
0x1800ef8b1  lea     rdx, [rsp+4E8h+var_498]
0x1800ef8b6  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UUpdateMetadata@@U?$default_delete@UUpdateMetadata@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UUpdateMetadata@@U?$default_delete@UUpdateMetadata@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UUpdateMetadata@@U?$default_delete@UUpdateMetadata@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<UpdateMetadata>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<UpdateMetadata>>>,0>>::find(std::wstring const &)
0x1800ef8bb  mov     rax, [rsp+4E8h+var_498]
0x1800ef8c0  cmp     rax, [rdi+360h]
0x1800ef8c7  jz      short loc_1800EF8D4
0x1800ef8c9  mov     rcx, [rax+30h]
0x1800ef8cd  add     [rdi+3B0h], rcx
0x1800ef8d4  lea     rcx, [rsp+4E8h+var_490]; this
0x1800ef8d9  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800ef8de  jmp     loc_1800EF751
```
