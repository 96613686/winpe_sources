# GetBlockedUpdatesFromBlockList(ulong *,ulong *,ushort * *)

- ea: `0x18003a8a8`
- end: `0x18003acfe`
- name: `?GetBlockedUpdatesFromBlockList@@YAJPEAK0PEAPEAG@Z`
- size: `1110`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x180015198`
- `0x18001a42c`
- `0x18001bddc`
- `0x18001be20`
- `0x1800243e8`
- `0x18003a794`
- `0x18003a7d0`
- `0x18003a8a8`
- `0x18003ad04`
- `0x18003c0b8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003aac2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003aac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ab22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ab22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ab33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ab33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a965`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a977`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a989`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a965`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a977`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003a989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aaf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aaf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ab67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ac9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ab7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ab7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ab15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003ab15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a9f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003a9f4`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003a996`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003a996`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003aa32`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003acc0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003aa32`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003acc0`

## string_xrefs

- `0x18003a8e8`: `DBUPDATEBL`
- `0x18003aa8d`: `DBUPDATEBL`
- `0x18003a959`: `LastUpdated`
- `0x18003ac71`: `pBlockedUpdates %d pRebootBlockedUpdates %d pBlockListString %s\n`

## pseudocode

```c
__int64 __fastcall GetBlockedUpdatesFromBlockList(unsigned int *a1, unsigned int *a2, unsigned __int16 **a3)
{
  int v6; // eax
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rbx
  int ActivationFactory; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // r14d
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v17; // rbx
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, HSTRING *); // rbx
  unsigned __int64 v20; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v24; // eax
  __int64 *v25; // rcx
  int BlockedUpdatesFromBlockListConfig; // eax
  __int64 *v27; // rcx
  __int64 *v28; // rcx
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v33; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char v35; // [rsp+59h] [rbp-A7h]
  __int64 *v36; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER v39; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v41[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  hKey = 0;
  v6 = StringCchPrintfW(
         v41,
         0x104u,
         L"%s%s",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState\\");
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = 366;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
      (const char *)(unsigned int)v6,
      (int)L"DBUPDATEBL");
    goto LABEL_32;
  }
  v6 = wil::reg::open_unique_key_nothrow(v7, v41, &hKey, 1);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = 367;
    goto LABEL_5;
  }
  RegDeleteValueW(hKey, L"LastUpdated");
  RegDeleteValueW(hKey, L"LastRefreshByApp");
  RegDeleteValueW(hKey, L"LastForceRefresh");
  DeleteBlockListCachedFile();
  v6 = RoInitialize(1);
  v8 = v6;
  if ( v6 < 0 )
  {
    v9 = 373;
    goto LABEL_5;
  }
  v35 = 1;
  v32 = 0;
  v31 = 0;
  v38 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
    0x3Au,
    0x39u);
  v10 = v38;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v32);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v12 = (unsigned int)ActivationFactory;
    v13 = 384;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
      (const char *)v12,
      (int)L"DBUPDATEBL");
    goto LABEL_11;
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = v32;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v32 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v38 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &sourceString, 1u, 0);
    v17 = v38;
    v40 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v39, L"DBUPDATEBL", 0xBu, 0xAu);
    v8 = v16(v15, v40, v17, &v31);
    if ( v8 >= 0 )
      break;
    Sleep(0x1F4u);
    if ( (unsigned int)++v14 >= 3 )
    {
      v12 = (unsigned int)v8;
      v13 = 396;
      goto LABEL_10;
    }
  }
  string = 0;
  v18 = v31;
  v19 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v19(v18, &string);
  v20 = 2 * WindowsGetStringLen(string) + 2;
  ProcessHeap = GetProcessHeap();
  v22 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v20);
  if ( !v22 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
      (const char *)0x8007000ELL,
      (int)L"DBUPDATEBL");
LABEL_18:
    WindowsDeleteString(string);
    string = 0;
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    RoUninitialize();
    goto LABEL_32;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  StringCchCopyW(v22, v20 >> 1, StringRawBuffer);
  *a3 = v22;
  v33 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v31 + 96LL))(v31, &v33);
  v8 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
      (const char *)(unsigned int)v24,
      (int)L"DBUPDATEBL");
    v25 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
    }
    goto LABEL_18;
  }
  v36 = v33;
  if ( v33 )
    (*(void (__fastcall **)(__int64 *))(*v33 + 8))(v33);
  BlockedUpdatesFromBlockListConfig = GetBlockedUpdatesFromBlockListConfig(&v36, a1, a2);
  v8 = BlockedUpdatesFromBlockListConfig;
  if ( BlockedUpdatesFromBlockListConfig < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
      (const char *)(unsigned int)BlockedUpdatesFromBlockListConfig,
      (int)L"DBUPDATEBL");
    v27 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    }
    goto LABEL_18;
  }
  SBServicingLogMessage((wchar_t *)L"pBlockedUpdates %d pRebootBlockedUpdates %d pBlockListString %s\n", *a1, *a2, *a3);
  v28 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  RoUninitialize();
  v8 = 0;
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003a8a8  mov     [rsp-8+arg_18], rbx
0x18003a8ad  push    rbp
0x18003a8ae  push    rsi
0x18003a8af  push    rdi
0x18003a8b0  push    r12
0x18003a8b2  push    r13
0x18003a8b4  push    r14
0x18003a8b6  push    r15
0x18003a8b8  lea     rbp, [rsp-1D0h]
0x18003a8c0  sub     rsp, 2D0h
0x18003a8c7  mov     rax, cs:__security_cookie
0x18003a8ce  xor     rax, rsp
0x18003a8d1  mov     [rbp+200h+var_40], rax
0x18003a8d8  mov     r13, r8
0x18003a8db  mov     r12, rdx
0x18003a8de  mov     r15, rcx
0x18003a8e1  xor     edi, edi
0x18003a8e3  mov     [rsp+300h+hKey], rdi
0x18003a8e8  lea     rax, aDbupdatebl; "DBUPDATEBL"
0x18003a8ef  mov     qword ptr [rsp+300h+var_2E0], rax; int
0x18003a8f4  lea     r9, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003a8fb  lea     r8, aSS_0; "%s%s"
0x18003a902  mov     edx, 104h; unsigned __int64
0x18003a907  lea     rcx, [rbp+200h+var_250]; unsigned __int16 *
0x18003a90b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a910  mov     ebx, eax
0x18003a912  test    eax, eax
0x18003a914  jns     short loc_18003A91D
0x18003a916  mov     edx, 16Eh
0x18003a91b  jmp     short loc_18003A93E
0x18003a91d  mov     esi, 1
0x18003a922  mov     r9d, esi
0x18003a925  lea     r8, [rsp+300h+hKey]
0x18003a92a  lea     rdx, [rbp+200h+var_250]
0x18003a92e  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003a933  mov     ebx, eax
0x18003a935  test    eax, eax
0x18003a937  jns     short loc_18003A959
0x18003a939  mov     edx, 16Fh; void *
0x18003a93e  mov     rcx, [rbp+208h]; this
0x18003a945  mov     r9d, eax; char *
0x18003a948  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003a94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a954  jmp     loc_18003ACC8
0x18003a959  lea     rdx, aLastupdated; "LastUpdated"
0x18003a960  mov     rcx, [rsp+300h+hKey]; hKey
0x18003a965  call    cs:__imp_RegDeleteValueW
0x18003a96b  lea     rdx, aLastrefreshbya; "LastRefreshByApp"
0x18003a972  mov     rcx, [rsp+300h+hKey]; hKey
0x18003a977  call    cs:__imp_RegDeleteValueW
0x18003a97d  lea     rdx, aLastforcerefre; "LastForceRefresh"
0x18003a984  mov     rcx, [rsp+300h+hKey]; hKey
0x18003a989  call    cs:__imp_RegDeleteValueW
0x18003a98f  call    ?DeleteBlockListCachedFile@@YAXXZ; DeleteBlockListCachedFile(void)
0x18003a994  mov     ecx, esi
0x18003a996  call    cs:__imp_RoInitialize
0x18003a99c  mov     ebx, eax
0x18003a99e  test    eax, eax
0x18003a9a0  jns     short loc_18003A9A9
0x18003a9a2  mov     edx, 175h
0x18003a9a7  jmp     short loc_18003A93E
0x18003a9a9  mov     [rsp+300h+var_2A7], sil
0x18003a9ae  mov     [rsp+300h+var_2C0], rdi
0x18003a9b3  mov     [rsp+300h+var_2C8], rdi
0x18003a9b8  mov     [rbp+200h+var_280], rdi
0x18003a9bc  mov     r9d, 39h ; '9'; unsigned int
0x18003a9c2  lea     r8d, [r9+1]; unsigned int
0x18003a9c6  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003a9cd  lea     rcx, [rsp+300h+hstringHeader]; hstringHeader
0x18003a9d2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003a9d7  mov     rbx, [rbp+200h+var_280]
0x18003a9db  lea     rcx, [rsp+300h+var_2C0]
0x18003a9e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a9e5  lea     r8, [rsp+300h+var_2C0]
0x18003a9ea  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x18003a9f1  mov     rcx, rbx
0x18003a9f4  call    cs:__imp_RoGetActivationFactory
0x18003a9fa  mov     ebx, eax
0x18003a9fc  test    eax, eax
0x18003a9fe  jns     short loc_18003AA3D
0x18003aa00  mov     r9d, eax; char *
0x18003aa03  mov     edx, 180h; void *
0x18003aa08  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003aa0f  mov     rcx, [rbp+208h]; this
0x18003aa16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa1b  nop
0x18003aa1c  lea     rcx, [rsp+300h+var_2C8]
0x18003aa21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003aa26  nop
0x18003aa27  lea     rcx, [rsp+300h+var_2C0]
0x18003aa2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003aa31  nop
0x18003aa32  call    cs:__imp_RoUninitialize
0x18003aa38  jmp     loc_18003ACC8
0x18003aa3d  mov     r14d, edi
0x18003aa40  mov     rsi, [rsp+300h+var_2C0]
0x18003aa45  mov     rax, [rsi]
0x18003aa48  mov     rdi, [rax+38h]
0x18003aa4c  lea     rcx, [rsp+300h+var_2C8]
0x18003aa51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003aa56  mov     [rbp+200h+var_280], 0
0x18003aa5e  xor     r9d, r9d; unsigned int
0x18003aa61  lea     r8d, [r9+1]; unsigned int
0x18003aa65  lea     rdx, sourceString; sourceString
0x18003aa6c  lea     rcx, [rsp+300h+hstringHeader]; hstringHeader
0x18003aa71  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003aa76  nop
0x18003aa77  mov     rbx, [rbp+200h+var_280]
0x18003aa7b  mov     [rbp+200h+var_260], 0
0x18003aa83  mov     r9d, 0Ah; unsigned int
0x18003aa89  lea     r8d, [r9+1]; unsigned int
0x18003aa8d  lea     rdx, aDbupdatebl; "DBUPDATEBL"
0x18003aa94  lea     rcx, [rbp+200h+var_278]; hstringHeader
0x18003aa98  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003aa9d  nop
0x18003aa9e  lea     r9, [rsp+300h+var_2C8]
0x18003aaa3  mov     r8, rbx
0x18003aaa6  mov     rdx, [rbp+200h+var_260]
0x18003aaaa  mov     rcx, rsi
0x18003aaad  mov     rax, rdi
0x18003aab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aab5  mov     ebx, eax
0x18003aab7  xor     esi, esi
0x18003aab9  test    eax, eax
0x18003aabb  jns     short loc_18003AAE2
0x18003aabd  mov     ecx, 1F4h; dwMilliseconds
0x18003aac2  call    cs:__imp_Sleep
0x18003aac8  inc     r14d
0x18003aacb  cmp     r14d, 3
0x18003aacf  jb      loc_18003AA40
0x18003aad5  mov     r9d, ebx
0x18003aad8  mov     edx, 18Ch
0x18003aadd  jmp     loc_18003AA08
0x18003aae2  mov     [rsp+300h+string], rsi
0x18003aae7  mov     rdi, [rsp+300h+var_2C8]
0x18003aaec  mov     rax, [rdi]
0x18003aaef  mov     rbx, [rax+68h]
0x18003aaf3  xor     ecx, ecx; string
0x18003aaf5  call    cs:__imp_WindowsDeleteString
0x18003aafb  mov     [rsp+300h+string], rsi
0x18003ab00  lea     rdx, [rsp+300h+string]
0x18003ab05  mov     rcx, rdi
0x18003ab08  mov     rax, rbx
0x18003ab0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab10  mov     rcx, [rsp+300h+string]; string
0x18003ab15  call    cs:__imp_WindowsGetStringLen
0x18003ab1b  lea     ebx, ds:2[rax*2]
0x18003ab22  call    cs:__imp_GetProcessHeap
0x18003ab28  mov     rcx, rax; hHeap
0x18003ab2b  mov     r8d, ebx; dwBytes
0x18003ab2e  mov     edx, 8; dwFlags
0x18003ab33  call    cs:__imp_HeapAlloc
0x18003ab39  mov     rdi, rax
0x18003ab3c  test    rax, rax
0x18003ab3f  jnz     short loc_18003AB77
0x18003ab41  mov     rcx, [rbp+208h]; this
0x18003ab48  mov     ebx, 8007000Eh
0x18003ab4d  mov     r9d, ebx; char *
0x18003ab50  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003ab57  mov     edx, 197h; void *
0x18003ab5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab61  nop
0x18003ab62  mov     rcx, [rsp+300h+string]; string
0x18003ab67  call    cs:__imp_WindowsDeleteString
0x18003ab6d  mov     [rsp+300h+string], rsi
0x18003ab72  jmp     loc_18003AA1C
0x18003ab77  xor     edx, edx; length
0x18003ab79  mov     rcx, [rsp+300h+string]; string
0x18003ab7e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ab84  shr     rbx, 1
0x18003ab87  mov     r8, rax; unsigned __int16 *
0x18003ab8a  mov     rdx, rbx; unsigned __int64
0x18003ab8d  mov     rcx, rdi; unsigned __int16 *
0x18003ab90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ab95  mov     [r13+0], rdi
0x18003ab99  mov     [rsp+300h+var_2B8], rsi
0x18003ab9e  mov     rcx, [rsp+300h+var_2C8]
0x18003aba3  mov     rax, [rcx]
0x18003aba6  lea     rdx, [rsp+300h+var_2B8]
0x18003abab  mov     rax, [rax+60h]
0x18003abaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abb4  mov     ebx, eax
0x18003abb6  test    eax, eax
0x18003abb8  jns     short loc_18003ABF7
0x18003abba  mov     rcx, [rbp+208h]; this
0x18003abc1  mov     r9d, eax; char *
0x18003abc4  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003abcb  mov     edx, 19Dh; void *
0x18003abd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abd5  nop
0x18003abd6  mov     rcx, [rsp+300h+var_2B8]
0x18003abdb  test    rcx, rcx
0x18003abde  jz      short loc_18003ABF2
0x18003abe0  mov     [rsp+300h+var_2B8], rsi
0x18003abe5  mov     rax, [rcx]
0x18003abe8  mov     rax, [rax+10h]
0x18003abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abf1  nop
0x18003abf2  jmp     loc_18003AB62
0x18003abf7  mov     rcx, [rsp+300h+var_2B8]
0x18003abfc  mov     [rsp+300h+var_2A0], rcx
0x18003ac01  test    rcx, rcx
0x18003ac04  jz      short loc_18003AC13
0x18003ac06  mov     rax, [rcx]
0x18003ac09  mov     rax, [rax+8]
0x18003ac0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac12  nop
0x18003ac13  mov     r8, r12
0x18003ac16  mov     rdx, r15
0x18003ac19  lea     rcx, [rsp+300h+var_2A0]
0x18003ac1e  call    ?GetBlockedUpdatesFromBlockListConfig@@YAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAK1@Z; GetBlockedUpdatesFromBlockListConfig(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ulong *,ulong *)
0x18003ac23  mov     ebx, eax
0x18003ac25  test    eax, eax
0x18003ac27  jns     short loc_18003AC66
0x18003ac29  mov     rcx, [rbp+208h]; this
0x18003ac30  mov     r9d, eax; char *
0x18003ac33  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003ac3a  mov     edx, 19Fh; void *
0x18003ac3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ac44  nop
0x18003ac45  mov     rcx, [rsp+300h+var_2B8]
0x18003ac4a  test    rcx, rcx
0x18003ac4d  jz      short loc_18003AC61
0x18003ac4f  mov     [rsp+300h+var_2B8], rsi
0x18003ac54  mov     rax, [rcx]
0x18003ac57  mov     rax, [rax+10h]
0x18003ac5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac60  nop
0x18003ac61  jmp     loc_18003AB62
0x18003ac66  mov     r9, [r13+0]
0x18003ac6a  mov     r8d, [r12]
0x18003ac6e  mov     edx, [r15]
0x18003ac71  lea     rcx, aPblockedupdate; "pBlockedUpdates %d pRebootBlockedUpdate"...
0x18003ac78  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003ac7d  nop
0x18003ac7e  mov     rcx, [rsp+300h+var_2B8]
0x18003ac83  test    rcx, rcx
0x18003ac86  jz      short loc_18003AC9A
0x18003ac88  mov     [rsp+300h+var_2B8], rsi
0x18003ac8d  mov     rax, [rcx]
0x18003ac90  mov     rax, [rax+10h]
0x18003ac94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac99  nop
0x18003ac9a  mov     rcx, [rsp+300h+string]; string
0x18003ac9f  call    cs:__imp_WindowsDeleteString
0x18003aca5  mov     [rsp+300h+string], rsi
0x18003acaa  lea     rcx, [rsp+300h+var_2C8]
0x18003acaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003acb4  nop
0x18003acb5  lea     rcx, [rsp+300h+var_2C0]
0x18003acba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003acbf  nop
0x18003acc0  call    cs:__imp_RoUninitialize
0x18003acc6  mov     ebx, esi
0x18003acc8  lea     rcx, [rsp+300h+hKey]
0x18003accd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003acd2  mov     eax, ebx
0x18003acd4  mov     rcx, [rbp+200h+var_40]
0x18003acdb  xor     rcx, rsp; StackCookie
0x18003acde  call    __security_check_cookie
0x18003ace3  mov     rbx, [rsp+300h+arg_18]
0x18003aceb  add     rsp, 2D0h
0x18003acf2  pop     r15
0x18003acf4  pop     r14
0x18003acf6  pop     r13
0x18003acf8  pop     r12
0x18003acfa  pop     rdi
0x18003acfb  pop     rsi
0x18003acfc  pop     rbp
0x18003acfd  retn
```
