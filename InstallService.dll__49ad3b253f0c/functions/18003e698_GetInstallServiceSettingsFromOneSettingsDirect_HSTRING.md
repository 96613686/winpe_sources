# GetInstallServiceSettingsFromOneSettingsDirect(HSTRING__ * *)

- ea: `0x18003e698`
- end: `0x18003e9d8`
- name: `?GetInstallServiceSettingsFromOneSettingsDirect@@YAJPEAPEAUHSTRING__@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(HSTRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003f2a4`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001bdf0`
- `0x18001c108`
- `0x18001c964`
- `0x180023a9c`
- `0x18002548c`
- `0x18003e698`
- `0x180044c3c`
- `0x18006d9e0`
- `0x18007e714`
- `0x18007f57c`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e7d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003e7d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e81d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e6d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e7aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e81d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e9a7`

## string_xrefs

- `0x18003e91c`: `InstallService`
- `0x18003e713`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003e7ed`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003e875`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003e8df`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003e959`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003e6f1`: `https://settings-win.data.microsoft.com/settings/v3.0/scc/InstallService`
- `0x18003e737`: `https://settings-win.data.microsoft.com/settings/v3.0/scc/InstallService`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall GetInstallServiceSettingsFromOneSettingsDirect(HSTRING *a1)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  const WCHAR *v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int Uri; // eax
  char *v8; // r8
  unsigned int v9; // ebx
  struct Windows::Foundation::IUriRuntimeClass *v10; // rbx
  int UriResponseWithAuthTicket; // eax
  unsigned int v12; // edx
  unsigned int v13; // edi
  unsigned int v14; // edx
  int v15; // [rsp+20h] [rbp-138h]
  HSTRING string; // [rsp+50h] [rbp-108h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v17[2]; // [rsp+58h] [rbp-100h] BYREF
  PCNZWCH sourceString[2]; // [rsp+68h] [rbp-F0h] BYREF
  UINT32 length; // [rsp+78h] [rbp-E0h]
  unsigned __int64 v20; // [rsp+80h] [rbp-D8h]
  _QWORD v21[3]; // [rsp+88h] [rbp-D0h] BYREF
  HSTRING__ v22; // [rsp+B0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  string = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
  {
    std::wstring::wstring(sourceString, L"https://settings-win.data.microsoft.com/settings/v3.0/scc/InstallService");
    Utils::GetOsVersionFull(v21);
    if ( v21[2] )
    {
      std::wstring::_Append<unsigned short>(sourceString);
      std::wstring::_Append<unsigned short>(sourceString);
    }
    WindowsDeleteString(string);
    string = 0;
    v4 = (const WCHAR *)sourceString;
    if ( v20 > 7 )
      v4 = sourceString[0];
    v5 = WindowsCreateString(v4, length, &string);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v5,
        v15);
      std::wstring::_Tidy_deallocate(v21);
      std::wstring::_Tidy_deallocate(sourceString);
      WindowsDeleteString(string);
      return v6;
    }
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(sourceString);
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    v1 = WindowsCreateString(
           L"https://settings-win.data.microsoft.com/settings/v3.0/scc/InstallService",
           0x48u,
           &string);
    v2 = v1;
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v1,
        v15);
      WindowsDeleteString(string);
      return v2;
    }
  }
  v17[0] = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v17);
  Uri = MakeUri(string, v17);
  v9 = Uri;
  if ( Uri >= 0 )
  {
    WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(0, &v22, v8);
    v10 = TraceLoggingCorrelationVector::Extend((const char *)&v22, 0);
    v17[1] = v10;
    if ( v10 )
    {
      UriResponseWithAuthTicket = FetchUriResponseWithAuthTicket(v10, v17[0], 0, 0);
      v13 = UriResponseWithAuthTicket;
      if ( UriResponseWithAuthTicket >= 0 )
      {
        TraceLoggingCorrelationVector::`scalar deleting destructor'(v10, v12);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v17);
        WindowsDeleteString(string);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)UriResponseWithAuthTicket,
          0);
        TraceLoggingCorrelationVector::`scalar deleting destructor'(v10, v14);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v17);
        WindowsDeleteString(string);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x227,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)0x8007000ELL,
        v15);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v17);
      WindowsDeleteString(string);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)Uri,
      v15);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v17);
    WindowsDeleteString(string);
    return v9;
  }
}

```

## disassembly

```asm
0x18003e698  mov     [rsp+arg_8], rbx
0x18003e69d  push    rdi
0x18003e69e  sub     rsp, 150h
0x18003e6a5  mov     rax, cs:__security_cookie
0x18003e6ac  xor     rax, rsp
0x18003e6af  mov     [rsp+158h+var_18], rax
0x18003e6b7  mov     rdi, rcx
0x18003e6ba  mov     [rsp+158h+string], 0
0x18003e6c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupScan@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScan@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan> `wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl(void)'::`2'::impl
0x18003e6ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupScan@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(void)
0x18003e6cf  test    al, al
0x18003e6d1  jnz     short loc_18003E737
0x18003e6d3  mov     rcx, [rsp+158h+string]; string
0x18003e6d8  call    cs:__imp_WindowsDeleteString
0x18003e6de  mov     [rsp+158h+string], 0
0x18003e6e7  lea     r8, [rsp+158h+string]; string
0x18003e6ec  mov     edx, 48h ; 'H'; length
0x18003e6f1  lea     rcx, sourceString; "https://settings-win.data.microsoft.com"...
0x18003e6f8  call    cs:__imp_WindowsCreateString
0x18003e6fe  mov     ebx, eax
0x18003e700  test    eax, eax
0x18003e702  jns     loc_18003E842
0x18003e708  mov     rcx, [rsp+158h]; this
0x18003e710  mov     r9d, eax; char *
0x18003e713  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003e71a  mov     edx, 21Eh; void *
0x18003e71f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e724  nop
0x18003e725  mov     rcx, [rsp+158h+string]; string
0x18003e72a  call    cs:__imp_WindowsDeleteString
0x18003e730  mov     eax, ebx
0x18003e732  jmp     loc_18003E9B6
0x18003e737  lea     rdx, sourceString; "https://settings-win.data.microsoft.com"...
0x18003e73e  lea     rcx, [rsp+158h+sourceString]
0x18003e743  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e748  nop
0x18003e749  lea     rcx, [rsp+158h+var_D0]
0x18003e751  call    ?GetOsVersionFull@Utils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Utils::GetOsVersionFull(void)
0x18003e756  nop
0x18003e757  cmp     [rsp+158h+var_C0], 0
0x18003e760  jz      short loc_18003E7A5
0x18003e762  mov     r8d, 0Fh
0x18003e768  lea     rdx, aOsversionfull; "?OsVersionFull="
0x18003e76f  lea     rcx, [rsp+158h+sourceString]; Src
0x18003e774  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e779  lea     rdx, [rsp+158h+var_D0]
0x18003e781  cmp     [rsp+158h+var_B8], 7
0x18003e78a  cmova   rdx, [rsp+158h+var_D0]
0x18003e793  mov     r8, [rsp+158h+var_C0]
0x18003e79b  lea     rcx, [rsp+158h+sourceString]; Src
0x18003e7a0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e7a5  mov     rcx, [rsp+158h+string]; string
0x18003e7aa  call    cs:__imp_WindowsDeleteString
0x18003e7b0  mov     [rsp+158h+string], 0
0x18003e7b9  lea     rcx, [rsp+158h+sourceString]
0x18003e7be  cmp     [rsp+158h+var_D8], 7
0x18003e7c7  cmova   rcx, [rsp+158h+sourceString]; sourceString
0x18003e7cd  lea     r8, [rsp+158h+string]; string
0x18003e7d2  mov     edx, [rsp+158h+length]; length
0x18003e7d6  call    cs:__imp_WindowsCreateString
0x18003e7dc  mov     ebx, eax
0x18003e7de  test    eax, eax
0x18003e7e0  jns     short loc_18003E82A
0x18003e7e2  mov     rcx, [rsp+158h]; this
0x18003e7ea  mov     r9d, eax; char *
0x18003e7ed  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003e7f4  mov     edx, 21Ah; void *
0x18003e7f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e7fe  nop
0x18003e7ff  lea     rcx, [rsp+158h+var_D0]
0x18003e807  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e80c  nop
0x18003e80d  lea     rcx, [rsp+158h+sourceString]
0x18003e812  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e817  nop
0x18003e818  mov     rcx, [rsp+158h+string]; string
0x18003e81d  call    cs:__imp_WindowsDeleteString
0x18003e823  mov     eax, ebx
0x18003e825  jmp     loc_18003E9B6
0x18003e82a  lea     rcx, [rsp+158h+var_D0]
0x18003e832  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e837  nop
0x18003e838  lea     rcx, [rsp+158h+sourceString]
0x18003e83d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e842  mov     [rsp+158h+var_100], 0
0x18003e84b  lea     rcx, [rsp+158h+var_100]
0x18003e850  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003e855  lea     rdx, [rsp+158h+var_100]; struct Windows::Foundation::IUriRuntimeClass **
0x18003e85a  mov     rcx, [rsp+158h+string]; HSTRING
0x18003e85f  call    ?MakeUri@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; MakeUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)
0x18003e864  mov     ebx, eax
0x18003e866  test    eax, eax
0x18003e868  jns     short loc_18003E8A4
0x18003e86a  mov     rcx, [rsp+158h]; this
0x18003e872  mov     r9d, eax; char *
0x18003e875  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003e87c  mov     edx, 221h; void *
0x18003e881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e886  nop
0x18003e887  lea     rcx, [rsp+158h+var_100]
0x18003e88c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003e891  nop
0x18003e892  mov     rcx, [rsp+158h+string]; string
0x18003e897  call    cs:__imp_WindowsDeleteString
0x18003e89d  mov     eax, ebx
0x18003e89f  jmp     loc_18003E9B6
0x18003e8a4  lea     rdx, [rsp+158h+var_A8]; HSTRING
0x18003e8ac  xor     ecx, ecx; this
0x18003e8ae  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x18003e8b3  xor     edx, edx; bool
0x18003e8b5  lea     rcx, [rsp+158h+var_A8]; char *
0x18003e8bd  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18003e8c2  mov     rbx, rax
0x18003e8c5  mov     [rsp+158h+var_F8], rax
0x18003e8ca  test    rax, rax
0x18003e8cd  jnz     short loc_18003E90E
0x18003e8cf  mov     rcx, [rsp+158h]; this
0x18003e8d7  mov     ebx, 8007000Eh
0x18003e8dc  mov     r9d, ebx; char *
0x18003e8df  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003e8e6  mov     edx, 227h; void *
0x18003e8eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e8f0  nop
0x18003e8f1  lea     rcx, [rsp+158h+var_100]
0x18003e8f6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003e8fb  nop
0x18003e8fc  mov     rcx, [rsp+158h+string]; string
0x18003e901  call    cs:__imp_WindowsDeleteString
0x18003e907  mov     eax, ebx
0x18003e909  jmp     loc_18003E9B6
0x18003e90e  mov     [rsp+158h+var_118], rdi
0x18003e913  mov     [rsp+158h+var_120], 0
0x18003e91c  lea     rax, ServiceName; "InstallService"
0x18003e923  mov     [rsp+158h+var_128], rax
0x18003e928  mov     [rsp+158h+var_130], 0
0x18003e92d  mov     [rsp+158h+var_138], 0; int
0x18003e935  xor     r9d, r9d
0x18003e938  xor     r8d, r8d
0x18003e93b  mov     rdx, [rsp+158h+var_100]
0x18003e940  mov     rcx, rbx
0x18003e943  call    ?FetchUriResponseWithAuthTicket@@YAJPEAVTraceLoggingCorrelationVector@@PEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@PEAUIJsonObject@Json@Data@4@W4Http_Verb@@_NPEBG6PEAPEAU5@@Z; FetchUriResponseWithAuthTicket(TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,Windows::Data::Json::IJsonObject *,Http_Verb,bool,ushort const *,ushort const *,HSTRING__ * *)
0x18003e948  mov     edi, eax
0x18003e94a  test    eax, eax
0x18003e94c  jns     short loc_18003E98E
0x18003e94e  mov     rcx, [rsp+158h]; this
0x18003e956  mov     r9d, eax; char *
0x18003e959  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003e960  mov     edx, 231h; void *
0x18003e965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e96a  nop
0x18003e96b  mov     rcx, rbx; this
0x18003e96e  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18003e973  nop
0x18003e974  lea     rcx, [rsp+158h+var_100]
0x18003e979  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003e97e  nop
0x18003e97f  mov     rcx, [rsp+158h+string]; string
0x18003e984  call    cs:__imp_WindowsDeleteString
0x18003e98a  mov     eax, edi
0x18003e98c  jmp     short loc_18003E9B6
0x18003e98e  mov     rcx, rbx; this
0x18003e991  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x18003e996  nop
0x18003e997  lea     rcx, [rsp+158h+var_100]
0x18003e99c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003e9a1  nop
0x18003e9a2  mov     rcx, [rsp+158h+string]; string
0x18003e9a7  call    cs:__imp_WindowsDeleteString
0x18003e9ad  nop
0x18003e9ae  xor     eax, eax
0x18003e9b0  jmp     short loc_18003E9B6
0x18003e9b2  mov     eax, dword ptr [rsp+158h+string]
0x18003e9b6  mov     rcx, [rsp+158h+var_18]
0x18003e9be  xor     rcx, rsp; StackCookie
0x18003e9c1  call    __security_check_cookie
0x18003e9c6  mov     rbx, [rsp+158h+arg_8]
0x18003e9ce  add     rsp, 150h
0x18003e9d5  pop     rdi
0x18003e9d6  retn
```
