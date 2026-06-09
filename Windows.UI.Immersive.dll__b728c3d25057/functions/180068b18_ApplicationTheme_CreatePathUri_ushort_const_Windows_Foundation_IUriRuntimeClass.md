# ApplicationTheme::CreatePathUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180068b18`
- end: `0x180068da0`
- name: `?CreatePathUri@ApplicationTheme@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(ApplicationTheme *__hidden this, const unsigned __int16 *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004b370`
- `0x18006a0e0`

## callees

- `0x180012c24`
- `0x180013244`
- `0x180048f34`
- `0x180062a04`
- `0x180068aec`
- `0x180068b18`
- `0x18006b4e4`
- `0x18006b524`
- `0x18006b560`
- `0x18006c460`
- `0x18006c574`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180068cca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180068cca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180068c52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068d25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180068c97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180068c97`

## string_xrefs

- `0x180068cc3`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::CreatePathUri(
        ApplicationTheme *this,
        unsigned __int16 *a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  HSTRING v4; // rbx
  struct Windows::Internal::String *v5; // rdx
  int AppInstallFolderPath; // edi
  int AppDataFolderPath; // eax
  UINT32 StringLen; // eax
  unsigned int v9; // edx
  struct Windows::Internal::String *v10; // rdx
  UINT32 v11; // eax
  const unsigned __int16 *v12; // rdx
  UINT32 v13; // eax
  unsigned int v14; // edx
  UINT32 v15; // eax
  HRESULT v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64 *); // rbx
  __int64 v20; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string1; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string2; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+48h] [rbp-28h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-20h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h] BYREF
  HSTRING newString; // [rsp+68h] [rbp-8h] BYREF
  HSTRING v30; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING v31; // [rsp+A8h] [rbp+38h] BYREF

  v31 = 0;
  v4 = 0;
  v24 = 0;
  v28 = 0;
  string2 = 0;
  string = 0;
  v27 = 0;
  string1 = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  v30 = 0;
  if ( this )
  {
    AppInstallFolderPath = Windows::Internal::String::_InitializeHelper(&v31, (const unsigned __int16 *)this);
    if ( AppInstallFolderPath >= 0 )
    {
      AppDataFolderPath = ApplicationThemeHelper::GetAppDataFolderPath(&v24, v5);
      v4 = v24;
      AppInstallFolderPath = AppDataFolderPath;
    }
  }
  else
  {
    AppInstallFolderPath = -2147467261;
  }
  StringLen = WindowsGetStringLen(v4);
  if ( Windows::Internal::String::Substring(
         (Windows::Internal::String *)&v31,
         v9,
         StringLen,
         (struct Windows::Internal::String *)&v28) < 0
    || (unsigned int)Windows::Internal::String::CompareOrdinal(
                       (Windows::Internal::String *)&v24,
                       (const struct Windows::Internal::String *)&v28) )
  {
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    AppInstallFolderPath = ApplicationThemeHelper::GetAppInstallFolderPath(&string, v10);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v13 = WindowsGetStringLen(string);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v14,
                             v13,
                             (struct Windows::Internal::String *)&v27);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                         (Windows::Internal::String *)&string,
                         (const struct Windows::Internal::String *)&v27) )
    {
      AppInstallFolderPath = -2147024809;
      goto LABEL_23;
    }
    v15 = WindowsGetStringLen(string);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v15 + 1,
                             (struct Windows::Internal::String *)&string2);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v12 = L"ms-appx:///";
  }
  else
  {
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v11 = WindowsGetStringLen(v4);
    AppInstallFolderPath = Windows::Internal::String::Substring(
                             (Windows::Internal::String *)&v31,
                             v11 + 1,
                             (struct Windows::Internal::String *)&string2);
    if ( AppInstallFolderPath < 0 )
      goto LABEL_23;
    v12 = L"ms-appdata:///Local/";
  }
  if ( v12 )
    Windows::Internal::String::_InitializeHelper(&string1, v12);
  newString = 0;
  v16 = WindowsConcatString(string1, string2, &newString);
  Windows::Internal::String::FreeAndAssignOnSuccess(v16, newString, &v26);
  WindowsDeleteString(v30);
  v30 = 0;
  AppInstallFolderPath = WindowsCreateString(L"Windows.Foundation.Uri", 0x16u, &v30);
  if ( AppInstallFolderPath >= 0 )
  {
    AppInstallFolderPath = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                             (__int64)v30,
                             (__int64)&v25);
    if ( AppInstallFolderPath >= 0 )
    {
      v17 = v25;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v25 + 48LL);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v20);
      AppInstallFolderPath = v18(v17, v26, &v20);
      if ( AppInstallFolderPath >= 0 )
      {
        *(_QWORD *)a2 = v20;
        v20 = 0;
      }
    }
  }
LABEL_23:
  WindowsDeleteString(v30);
  v30 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v25);
  Windows::Internal::String::~String((Windows::Internal::String *)&v26);
  Windows::Internal::String::~String((Windows::Internal::String *)&string1);
  Windows::Internal::String::~String((Windows::Internal::String *)&v27);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  Windows::Internal::String::~String((Windows::Internal::String *)&string2);
  Windows::Internal::String::~String((Windows::Internal::String *)&v28);
  Windows::Internal::String::~String((Windows::Internal::String *)&v24);
  Windows::Internal::String::~String((Windows::Internal::String *)&v31);
  return (unsigned int)AppInstallFolderPath;
}

```

## disassembly

```asm
0x180068b18  mov     [rsp-18h+arg_0], rbx
0x180068b1d  mov     [rsp-18h+arg_8], rsi
0x180068b22  push    rbp
0x180068b23  push    rdi
0x180068b24  push    r14
0x180068b26  mov     rbp, rsp
0x180068b29  sub     rsp, 70h
0x180068b2d  xor     r14d, r14d
0x180068b30  mov     rsi, rdx
0x180068b33  mov     [rbp+arg_18], r14
0x180068b37  mov     ebx, r14d
0x180068b3a  mov     [rbp+var_30], rbx
0x180068b3e  mov     [rbp+var_10], r14
0x180068b42  mov     [rbp+string2], r14
0x180068b46  mov     [rbp+string], r14
0x180068b4a  mov     [rbp+var_18], r14
0x180068b4e  mov     [rbp+string1], r14
0x180068b52  mov     [rbp+var_20], r14
0x180068b56  mov     [rbp+var_28], r14
0x180068b5a  mov     [rbp+var_50], r14
0x180068b5e  mov     [rbp+arg_10], r14
0x180068b62  test    rcx, rcx
0x180068b65  jz      short loc_180068B8A
0x180068b67  mov     rdx, rcx; unsigned __int16 *
0x180068b6a  lea     rcx, [rbp+arg_18]; this
0x180068b6e  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180068b73  mov     edi, eax
0x180068b75  test    eax, eax
0x180068b77  js      short loc_180068B8F
0x180068b79  lea     rcx, [rbp+var_30]; this
0x180068b7d  call    ?GetAppDataFolderPath@ApplicationThemeHelper@@YAJPEAVString@Internal@Windows@@@Z; ApplicationThemeHelper::GetAppDataFolderPath(Windows::Internal::String *)
0x180068b82  mov     rbx, [rbp+var_30]
0x180068b86  mov     edi, eax
0x180068b88  jmp     short loc_180068B8F
0x180068b8a  mov     edi, 80004003h
0x180068b8f  mov     rcx, rbx; string
0x180068b92  call    cs:__imp_WindowsGetStringLen
0x180068b98  mov     r8d, eax; unsigned int
0x180068b9b  lea     r9, [rbp+var_10]; struct Windows::Internal::String *
0x180068b9f  lea     rcx, [rbp+arg_18]; this
0x180068ba3  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x180068ba8  test    eax, eax
0x180068baa  js      short loc_180068BF4
0x180068bac  lea     rdx, [rbp+var_10]; struct Windows::Internal::String *
0x180068bb0  lea     rcx, [rbp+var_30]; this
0x180068bb4  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180068bb9  test    eax, eax
0x180068bbb  jnz     short loc_180068BF4
0x180068bbd  test    edi, edi
0x180068bbf  js      loc_180068D21
0x180068bc5  mov     rcx, rbx; string
0x180068bc8  call    cs:__imp_WindowsGetStringLen
0x180068bce  lea     r8, [rbp+string2]; struct Windows::Internal::String *
0x180068bd2  lea     rcx, [rbp+arg_18]; this
0x180068bd6  lea     edx, [rax+1]; unsigned int
0x180068bd9  call    ?Substring@String@Internal@Windows@@QEBAJIPEAV123@@Z; Windows::Internal::String::Substring(uint,Windows::Internal::String *)
0x180068bde  mov     edi, eax
0x180068be0  test    eax, eax
0x180068be2  js      loc_180068D21
0x180068be8  mov     rdx, cs:off_1800F7EB8; "ms-appdata:///Local/"
0x180068bef  jmp     loc_180068C79
0x180068bf4  test    edi, edi
0x180068bf6  js      loc_180068D21
0x180068bfc  lea     rcx, [rbp+string]; this
0x180068c00  call    ?GetAppInstallFolderPath@ApplicationThemeHelper@@YAJPEAVString@Internal@Windows@@@Z; ApplicationThemeHelper::GetAppInstallFolderPath(Windows::Internal::String *)
0x180068c05  mov     edi, eax
0x180068c07  test    eax, eax
0x180068c09  js      loc_180068D21
0x180068c0f  mov     rcx, [rbp+string]; string
0x180068c13  call    cs:__imp_WindowsGetStringLen
0x180068c19  mov     r8d, eax; unsigned int
0x180068c1c  lea     r9, [rbp+var_18]; struct Windows::Internal::String *
0x180068c20  lea     rcx, [rbp+arg_18]; this
0x180068c24  call    ?Substring@String@Internal@Windows@@QEBAJIIPEAV123@@Z; Windows::Internal::String::Substring(uint,uint,Windows::Internal::String *)
0x180068c29  mov     edi, eax
0x180068c2b  test    eax, eax
0x180068c2d  js      loc_180068D21
0x180068c33  lea     rdx, [rbp+var_18]; struct Windows::Internal::String *
0x180068c37  lea     rcx, [rbp+string]; this
0x180068c3b  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x180068c40  test    eax, eax
0x180068c42  jz      short loc_180068C4E
0x180068c44  mov     edi, 80070057h
0x180068c49  jmp     loc_180068D21
0x180068c4e  mov     rcx, [rbp+string]; string
0x180068c52  call    cs:__imp_WindowsGetStringLen
0x180068c58  lea     r8, [rbp+string2]; struct Windows::Internal::String *
0x180068c5c  lea     rcx, [rbp+arg_18]; this
0x180068c60  lea     edx, [rax+1]; unsigned int
0x180068c63  call    ?Substring@String@Internal@Windows@@QEBAJIPEAV123@@Z; Windows::Internal::String::Substring(uint,Windows::Internal::String *)
0x180068c68  mov     edi, eax
0x180068c6a  test    eax, eax
0x180068c6c  js      loc_180068D21
0x180068c72  mov     rdx, cs:off_1800F7EB0; unsigned __int16 *
0x180068c79  test    rdx, rdx
0x180068c7c  jz      short loc_180068C87
0x180068c7e  lea     rcx, [rbp+string1]; this
0x180068c82  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180068c87  mov     rdx, [rbp+string2]; string2
0x180068c8b  lea     r8, [rbp+newString]; newString
0x180068c8f  mov     rcx, [rbp+string1]; string1
0x180068c93  mov     [rbp+newString], r14
0x180068c97  call    cs:__imp_WindowsConcatString
0x180068c9d  mov     rdx, [rbp+newString]; HSTRING
0x180068ca1  lea     r8, [rbp+var_20]; HSTRING *
0x180068ca5  mov     ecx, eax; int
0x180068ca7  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x180068cac  mov     rcx, [rbp+arg_10]; string
0x180068cb0  call    cs:__imp_WindowsDeleteString
0x180068cb6  lea     r8, [rbp+arg_10]; string
0x180068cba  mov     [rbp+arg_10], r14
0x180068cbe  mov     edx, 16h; length
0x180068cc3  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180068cca  call    cs:__imp_WindowsCreateString
0x180068cd0  mov     edi, eax
0x180068cd2  test    eax, eax
0x180068cd4  js      short loc_180068D21
0x180068cd6  mov     rcx, [rbp+arg_10]
0x180068cda  lea     rdx, [rbp+var_28]
0x180068cde  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180068ce3  mov     edi, eax
0x180068ce5  test    eax, eax
0x180068ce7  js      short loc_180068D21
0x180068ce9  mov     rdi, [rbp+var_28]
0x180068ced  lea     rcx, [rbp+var_50]
0x180068cf1  mov     rax, [rdi]
0x180068cf4  mov     rbx, [rax+30h]
0x180068cf8  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180068cfd  mov     rdx, [rbp+var_20]
0x180068d01  lea     r8, [rbp+var_50]
0x180068d05  mov     rcx, rdi
0x180068d08  mov     rax, rbx
0x180068d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d10  mov     edi, eax
0x180068d12  test    eax, eax
0x180068d14  js      short loc_180068D21
0x180068d16  mov     rax, [rbp+var_50]
0x180068d1a  mov     [rsi], rax
0x180068d1d  mov     [rbp+var_50], r14
0x180068d21  mov     rcx, [rbp+arg_10]; string
0x180068d25  call    cs:__imp_WindowsDeleteString
0x180068d2b  lea     rcx, [rbp+var_50]
0x180068d2f  mov     [rbp+arg_10], r14
0x180068d33  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180068d38  lea     rcx, [rbp+var_28]
0x180068d3c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180068d41  lea     rcx, [rbp+var_20]; this
0x180068d45  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d4a  lea     rcx, [rbp+string1]; this
0x180068d4e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d53  lea     rcx, [rbp+var_18]; this
0x180068d57  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d5c  lea     rcx, [rbp+string]; this
0x180068d60  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d65  lea     rcx, [rbp+string2]; this
0x180068d69  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d6e  lea     rcx, [rbp+var_10]; this
0x180068d72  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d77  lea     rcx, [rbp+var_30]; this
0x180068d7b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d80  lea     rcx, [rbp+arg_18]; this
0x180068d84  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180068d89  lea     r11, [rsp+70h+var_s0]
0x180068d8e  mov     eax, edi
0x180068d90  mov     rbx, [r11+20h]
0x180068d94  mov     rsi, [r11+28h]
0x180068d98  mov     rsp, r11
0x180068d9b  pop     r14
0x180068d9d  pop     rdi
0x180068d9e  pop     rbp
0x180068d9f  retn
```
