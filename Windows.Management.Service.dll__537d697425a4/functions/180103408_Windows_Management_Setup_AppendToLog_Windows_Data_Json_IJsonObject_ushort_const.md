# Windows::Management::Setup::AppendToLog(Windows::Data::Json::IJsonObject *,ushort const *)

- ea: `0x180103408`
- end: `0x180103a65`
- name: `?AppendToLog@Setup@Management@Windows@@YAJPEAUIJsonObject@Json@Data@3@PEBG@Z`
- size: `1629`
- prototype: `__int64 __fastcall(Windows::Management::Setup *__hidden this, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180104080`
- `0x180104370`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x180088144`
- `0x18008aecc`
- `0x18008c9a8`
- `0x18008e088`
- `0x18008e570`
- `0x18008e918`
- `0x18008eef4`
- `0x1800901c0`
- `0x1800feb74`
- `0x180103408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180103984`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180103868`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180103868`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180103642`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180103642`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010354f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801035e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801037d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010354f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801035e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801037d6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180103839`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010393d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801039c0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180103839`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010393d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801039c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180103441`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180103441`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010377b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18010377b`

## string_xrefs

- `0x180103481`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801034f2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180103599`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010361c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180103671`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801036d4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010372f`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180103790`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801038a5`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180103951`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801039d4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010349a`: `ProvisioningStatus\PageUpdate`
- `0x1801036a7`: `ProvisioningStatus\PageUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Management::Setup::AppendToLog(
        Windows::Management::Setup *this,
        struct Windows::Data::Json::IJsonObject *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int StateSeparationAwareExpandedFilePath; // eax
  const WCHAR *v9; // rax
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  int v12; // eax
  const WCHAR *v13; // rax
  HANDLE v14; // rax
  const char *v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  const WCHAR *v20; // rbx
  const WCHAR *v21; // rax
  const char *v22; // r9
  __int64 v23; // rdx
  const WCHAR *v24; // rax
  HANDLE v25; // rax
  char v26; // bl
  int v27; // eax
  unsigned int v28; // esi
  __int64 v29; // r9
  const WCHAR *v30; // r8
  DWORD v31; // ebx
  const void *v32; // rax
  const char *v33; // r9
  PCWSTR StringRawBuffer; // rax
  DWORD v35; // ebx
  const void *v36; // rax
  const char *v37; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v46[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v47[32]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v48[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v49[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v52[16]; // [rsp+110h] [rbp+10h] BYREF
  int v53; // [rsp+120h] [rbp+20h]
  _BYTE v54[16]; // [rsp+130h] [rbp+30h] BYREF
  int v55; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v50[0] = 0;
  v50[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v50[0]) = 0;
  v5 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, v50);
  v6 = v5;
  if ( v5 >= 0 )
  {
    wil::str_printf<std::wstring>(v47, L"%s\\%s.log", L"ProvisioningStatus\\PageUpdate", a2);
    v46[0] = 0;
    v46[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v46[0]) = 0;
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
    StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                             v7,
                                             v46);
    v6 = StateSeparationAwareExpandedFilePath;
    if ( StateSeparationAwareExpandedFilePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
        (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
        dwCreationDisposition);
LABEL_5:
      std::wstring::_Tidy_deallocate(v46);
      std::wstring::_Tidy_deallocate(v47);
      goto LABEL_49;
    }
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
    FileW = CreateFileW(v9, 0x12019Fu, 2u, 0, 3u, 0, 0);
    hFile = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LastError - 2 > 1 )
      {
        if ( LastError )
        {
          v12 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCD,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioni"
                                "ngsessionlogger.cpp",
                  (const char *)LastError,
                  dwCreationDispositiona);
LABEL_10:
          v6 = v12;
LABEL_11:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          goto LABEL_5;
        }
LABEL_48:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        std::wstring::_Tidy_deallocate(v46);
        std::wstring::_Tidy_deallocate(v47);
        v6 = 0;
        goto LABEL_49;
      }
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
      v14 = CreateFileW(v13, 0x12019Fu, 2u, 0, 1u, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        v14);
      FileW = hFile;
      if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v16 = 217;
        goto LABEL_14;
      }
      goto LABEL_32;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v16 = 223;
      goto LABEL_14;
    }
    if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    {
      v6 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
        (const char *)0x80070216LL,
        dwCreationDispositiona);
      goto LABEL_11;
    }
    if ( FileSize.QuadPart < 0x100000 )
    {
      v26 = 1;
LABEL_36:
      if ( SetFilePointerEx(FileW, 0, 0, 2u) )
      {
        string = 0;
        v27 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(this, &string);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x110,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
            (const char *)(unsigned int)v27,
            dwCreationDispositiona);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          std::wstring::_Tidy_deallocate(v46);
          std::wstring::_Tidy_deallocate(v47);
          v6 = v28;
          goto LABEL_49;
        }
        v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
        v30 = L"\r\n";
        if ( !v26 )
          v30 = &sourceString;
        wil::str_printf<std::wstring>(v52, L"%s%s\r\n", v30, v29);
        v31 = 2 * v53;
        v32 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
        if ( WriteFile(FileW, v32, v31, 0, 0) )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          std::wstring::wstring(v54, StringRawBuffer);
          v35 = 2 * v55;
          v36 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
          if ( WriteFile(FileW, v36, v35, 0, 0) )
          {
            std::wstring::_Tidy_deallocate(v54);
            std::wstring::_Tidy_deallocate(v52);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            goto LABEL_48;
          }
          v6 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x117,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisionin"
                               "gsessionlogger.cpp",
                 v37);
          std::wstring::_Tidy_deallocate(v54);
        }
        else
        {
          v6 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x114,
                 (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisionin"
                               "gsessionlogger.cpp",
                 v33);
        }
        std::wstring::_Tidy_deallocate(v52);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_11;
      }
      v16 = 269;
LABEL_14:
      v12 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)v16,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
              v15);
      goto LABEL_10;
    }
    dwCreationDispositionb = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
    wil::str_printf<std::wstring>(v49, L"%s\\%s_%s.log", L"ProvisioningStatus\\PageUpdate", a2);
    v17 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::NormalizeFilePath(v49);
    v6 = v17;
    if ( v17 >= 0 )
    {
      v48[0] = 0;
      v48[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v48[0]) = 0;
      v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
      v19 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
              v18,
              v48);
      v6 = v19;
      if ( v19 >= 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hFile,
          -1);
        v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
        v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
        if ( MoveFileExW(v21, v20, 9u) )
        {
          v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
          v25 = CreateFileW(v24, 0x12019Fu, 2u, 0, 1u, 0, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            v25);
          FileW = hFile;
          if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
            std::wstring::_Tidy_deallocate(v48);
            std::wstring::_Tidy_deallocate(v49);
LABEL_32:
            Buffer = 65279;
            if ( !WriteFile(FileW, &Buffer, 4u, 0, 0) )
            {
              v16 = 264;
              goto LABEL_14;
            }
            v26 = 0;
            goto LABEL_36;
          }
          v23 = 252;
        }
        else
        {
          v23 = 241;
        }
        v6 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v23,
               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisionings"
                             "essionlogger.cpp",
               v22);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
          (const char *)(unsigned int)v19,
          dwCreationDispositionb);
      }
      std::wstring::_Tidy_deallocate(v48);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
        (const char *)(unsigned int)v17,
        dwCreationDispositionb);
    }
    std::wstring::_Tidy_deallocate(v49);
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB5,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
    (const char *)(unsigned int)v5,
    dwCreationDisposition);
LABEL_49:
  std::wstring::_Tidy_deallocate(v50);
  return v6;
}

```

## disassembly

```asm
0x180103408  mov     [rsp-8+arg_10], rbx
0x18010340d  mov     [rsp-8+arg_18], rsi
0x180103412  push    rbp
0x180103413  push    rdi
0x180103414  push    r14
0x180103416  lea     rbp, [rsp-60h]
0x18010341b  sub     rsp, 160h
0x180103422  mov     rax, cs:__security_cookie
0x180103429  xor     rax, rsp
0x18010342c  mov     [rbp+70h+var_20], rax
0x180103430  mov     rsi, rdx
0x180103433  mov     r14, rcx
0x180103436  xorps   xmm0, xmm0
0x180103439  movups  xmmword ptr [rbp+70h+SystemTime.wYear], xmm0
0x18010343d  lea     rcx, [rbp+70h+SystemTime]; lpSystemTime
0x180103441  call    cs:__imp_GetSystemTime
0x180103448  nop     dword ptr [rax+rax+00h]
0x18010344d  xorps   xmm0, xmm0
0x180103450  movups  [rbp+70h+var_90], xmm0
0x180103454  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010345c  movdqu  [rbp+70h+var_80], xmm1
0x180103461  xor     eax, eax
0x180103463  mov     word ptr [rbp+70h+var_90], ax
0x180103467  lea     rdx, [rbp+70h+var_90]
0x18010346b  lea     rcx, [rbp+70h+SystemTime]
0x18010346f  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x180103474  mov     ebx, eax
0x180103476  test    eax, eax
0x180103478  jns     short loc_180103497
0x18010347a  mov     rcx, [rbp+78h]; this
0x18010347e  mov     r9d, eax; char *
0x180103481  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180103488  mov     edx, 0B5h; void *
0x18010348d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103492  jmp     loc_180103A35
0x180103497  mov     r9, rsi
0x18010349a  lea     r8, aProvisioningst_0; "ProvisioningStatus\\PageUpdate"
0x1801034a1  lea     rdx, aSSLog; "%s\\%s.log"
0x1801034a8  lea     rcx, [rbp+70h+var_F0]
0x1801034ac  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801034b1  nop
0x1801034b2  xorps   xmm0, xmm0
0x1801034b5  movups  [rsp+170h+var_110], xmm0
0x1801034ba  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801034c2  movdqu  [rsp+170h+var_100], xmm1
0x1801034c8  xor     eax, eax
0x1801034ca  mov     word ptr [rsp+170h+var_110], ax
0x1801034cf  lea     rcx, [rbp+70h+var_F0]
0x1801034d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801034d8  mov     rcx, rax
0x1801034db  lea     rdx, [rsp+170h+var_110]
0x1801034e0  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x1801034e5  mov     ebx, eax
0x1801034e7  test    eax, eax
0x1801034e9  jns     short loc_18010351D
0x1801034eb  mov     rcx, [rbp+78h]; this
0x1801034ef  mov     r9d, eax; char *
0x1801034f2  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801034f9  mov     edx, 0BCh; void *
0x1801034fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103503  nop
0x180103504  lea     rcx, [rsp+170h+var_110]
0x180103509  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010350e  nop
0x18010350f  lea     rcx, [rbp+70h+var_F0]
0x180103513  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103518  jmp     loc_180103A35
0x18010351d  lea     rcx, [rsp+170h+var_110]
0x180103522  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180103527  mov     rcx, rax; lpFileName
0x18010352a  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x180103533  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18010353b  mov     [rsp+170h+dwCreationDisposition], 3; int
0x180103543  xor     r9d, r9d; lpSecurityAttributes
0x180103546  mov     edx, 12019Fh; dwDesiredAccess
0x18010354b  lea     r8d, [r9+2]; dwShareMode
0x18010354f  call    cs:__imp_CreateFileW
0x180103556  nop     dword ptr [rax+rax+00h]
0x18010355b  mov     rdi, rax
0x18010355e  mov     [rsp+170h+hFile], rax
0x180103563  inc     rax
0x180103566  test    rax, 0FFFFFFFFFFFFFFFEh
0x18010356c  jnz     loc_180103631
0x180103572  call    cs:__imp_GetLastError
0x180103579  nop     dword ptr [rax+rax+00h]
0x18010357e  lea     ecx, [rax-2]
0x180103581  mov     ebx, 1
0x180103586  cmp     ecx, ebx
0x180103588  jbe     short loc_1801035BB
0x18010358a  test    eax, eax
0x18010358c  jz      loc_180103A14
0x180103592  mov     rcx, [rbp+78h]; this
0x180103596  mov     r9d, eax; char *
0x180103599  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801035a0  mov     edx, 0CDh; void *
0x1801035a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801035aa  mov     ebx, eax
0x1801035ac  lea     rcx, [rsp+170h+hFile]
0x1801035b1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801035b6  jmp     loc_180103504
0x1801035bb  lea     rcx, [rsp+170h+var_110]
0x1801035c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801035c5  mov     rcx, rax; lpFileName
0x1801035c8  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x1801035d1  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801035d9  mov     [rsp+170h+dwCreationDisposition], ebx; dwCreationDisposition
0x1801035dd  xor     r9d, r9d; lpSecurityAttributes
0x1801035e0  mov     edx, 12019Fh; dwDesiredAccess
0x1801035e5  lea     r8d, [r9+2]; dwShareMode
0x1801035e9  call    cs:__imp_CreateFileW
0x1801035f0  nop     dword ptr [rax+rax+00h]
0x1801035f5  mov     rdx, rax
0x1801035f8  lea     rcx, [rsp+170h+hFile]
0x1801035fd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103602  mov     rdi, [rsp+170h+hFile]
0x180103607  lea     rax, [rdi+1]
0x18010360b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180103611  jnz     loc_180103819
0x180103617  mov     edx, 0D9h; void *
0x18010361c  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180103623  mov     rcx, [rbp+78h]; this
0x180103627  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010362c  jmp     loc_1801035AA
0x180103631  mov     qword ptr [rsp+170h+FileSize], 0
0x18010363a  lea     rdx, [rsp+170h+FileSize]; lpFileSize
0x18010363f  mov     rcx, rdi; hFile
0x180103642  call    cs:__imp_GetFileSizeEx
0x180103649  nop     dword ptr [rax+rax+00h]
0x18010364e  test    eax, eax
0x180103650  jnz     short loc_180103659
0x180103652  mov     edx, 0DFh
0x180103657  jmp     short loc_18010361C
0x180103659  mov     eax, 0FFFFFFFFh
0x18010365e  cmp     qword ptr [rsp+170h+FileSize], rax
0x180103663  jl      short loc_180103687
0x180103665  mov     rcx, [rbp+78h]; this
0x180103669  mov     ebx, 80070216h
0x18010366e  mov     r9d, ebx; char *
0x180103671  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180103678  mov     edx, 0E0h; void *
0x18010367d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103682  jmp     loc_1801035AC
0x180103687  cmp     qword ptr [rsp+170h+FileSize], 100000h
0x180103690  jl      loc_180103857
0x180103696  lea     rcx, [rbp+70h+var_90]
0x18010369a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010369f  mov     qword ptr [rsp+170h+dwCreationDisposition], rax; int
0x1801036a4  mov     r9, rsi
0x1801036a7  lea     r8, aProvisioningst_0; "ProvisioningStatus\\PageUpdate"
0x1801036ae  lea     rdx, aSSSLog; "%s\\%s_%s.log"
0x1801036b5  lea     rcx, [rbp+70h+var_B0]
0x1801036b9  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801036be  lea     rcx, [rbp+70h+var_B0]
0x1801036c2  call    ?NormalizeFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::NormalizeFilePath(std::wstring &)
0x1801036c7  mov     ebx, eax
0x1801036c9  test    eax, eax
0x1801036cb  jns     short loc_1801036F3
0x1801036cd  mov     rcx, [rbp+78h]; this
0x1801036d1  mov     r9d, eax; char *
0x1801036d4  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801036db  mov     edx, 0E9h; void *
0x1801036e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801036e5  lea     rcx, [rbp+70h+var_B0]
0x1801036e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801036ee  jmp     loc_1801035AC
0x1801036f3  xorps   xmm0, xmm0
0x1801036f6  movups  [rbp+70h+var_D0], xmm0
0x1801036fa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180103702  movdqu  [rbp+70h+var_C0], xmm1
0x180103707  xor     eax, eax
0x180103709  mov     word ptr [rbp+70h+var_D0], ax
0x18010370d  lea     rcx, [rbp+70h+var_B0]
0x180103711  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180103716  mov     rcx, rax
0x180103719  lea     rdx, [rbp+70h+var_D0]
0x18010371d  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x180103722  mov     ebx, eax
0x180103724  test    eax, eax
0x180103726  jns     short loc_18010374B
0x180103728  mov     rcx, [rbp+78h]; this
0x18010372c  mov     r9d, eax; char *
0x18010372f  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180103736  mov     edx, 0EEh; void *
0x18010373b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180103740  lea     rcx, [rbp+70h+var_D0]
0x180103744  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103749  jmp     short loc_1801036E5
0x18010374b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18010374f  lea     rcx, [rsp+170h+hFile]
0x180103754  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180103759  lea     rcx, [rbp+70h+var_D0]
0x18010375d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180103762  mov     rbx, rax
0x180103765  lea     rcx, [rsp+170h+var_110]
0x18010376a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010376f  mov     rcx, rax; lpExistingFileName
0x180103772  mov     r8d, 9; dwFlags
0x180103778  mov     rdx, rbx; lpNewFileName
0x18010377b  call    cs:__imp_MoveFileExW
0x180103782  nop     dword ptr [rax+rax+00h]
0x180103787  test    eax, eax
0x180103789  jnz     short loc_1801037A4
0x18010378b  mov     edx, 0F1h; void *
0x180103790  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180103797  mov     rcx, [rbp+78h]; this
0x18010379b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801037a0  mov     ebx, eax
0x1801037a2  jmp     short loc_180103740
0x1801037a4  lea     rcx, [rsp+170h+var_110]
0x1801037a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801037ae  mov     rcx, rax; lpFileName
0x1801037b1  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x1801037ba  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801037c2  mov     [rsp+170h+dwCreationDisposition], 1; dwCreationDisposition
0x1801037ca  xor     r9d, r9d; lpSecurityAttributes
0x1801037cd  mov     edx, 12019Fh; dwDesiredAccess
0x1801037d2  lea     r8d, [r9+2]; dwShareMode
0x1801037d6  call    cs:__imp_CreateFileW
0x1801037dd  nop     dword ptr [rax+rax+00h]
0x1801037e2  mov     rdx, rax
0x1801037e5  lea     rcx, [rsp+170h+hFile]
0x1801037ea  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801037ef  mov     rdi, [rsp+170h+hFile]
0x1801037f4  lea     rax, [rdi+1]
0x1801037f8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801037fe  jnz     short loc_180103807
0x180103800  mov     edx, 0FCh
0x180103805  jmp     short loc_180103790
0x180103807  lea     rcx, [rbp+70h+var_D0]
0x18010380b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103810  lea     rcx, [rbp+70h+var_B0]
0x180103814  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180103819  mov     [rsp+170h+Buffer], 0FEFFh
0x180103821  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x18010382a  xor     r9d, r9d; lpNumberOfBytesWritten
0x18010382d  lea     r8d, [r9+4]; nNumberOfBytesToWrite
0x180103831  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x180103836  mov     rcx, rdi; hFile
0x180103839  call    cs:__imp_WriteFile
0x180103840  nop     dword ptr [rax+rax+00h]
0x180103845  test    eax, eax
0x180103847  jnz     short loc_180103853
0x180103849  mov     edx, 108h
0x18010384e  jmp     loc_18010361C
0x180103853  xor     bl, bl
0x180103855  jmp     short loc_18010385C
0x180103857  mov     ebx, 1
0x18010385c  xor     edx, edx; liDistanceToMove
0x18010385e  lea     r9d, [rdx+2]; dwMoveMethod
0x180103862  xor     r8d, r8d; lpNewFilePointer
0x180103865  mov     rcx, rdi; hFile
0x180103868  call    cs:__imp_SetFilePointerEx
0x18010386f  nop     dword ptr [rax+rax+00h]
0x180103874  test    eax, eax
0x180103876  jnz     short loc_180103882
0x180103878  mov     edx, 10Dh
0x18010387d  jmp     loc_18010361C
0x180103882  mov     [rsp+170h+string], 0
0x18010388b  lea     rdx, [rsp+170h+string]
0x180103890  mov     rcx, r14
0x180103893  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180103898  mov     esi, eax
0x18010389a  test    eax, eax
0x18010389c  jns     short loc_1801038E8
0x18010389e  mov     rcx, [rbp+78h]; this
0x1801038a2  mov     r9d, eax; char *
0x1801038a5  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801038ac  mov     edx, 110h; void *
0x1801038b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801038b6  nop
0x1801038b7  lea     rcx, [rsp+170h+string]; this
0x1801038bc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801038c1  nop
0x1801038c2  lea     rcx, [rsp+170h+hFile]
0x1801038c7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801038cc  nop
0x1801038cd  lea     rcx, [rsp+170h+var_110]
0x1801038d2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801038d7  nop
0x1801038d8  lea     rcx, [rbp+70h+var_F0]
0x1801038dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801038e1  mov     ebx, esi
0x1801038e3  jmp     loc_180103A35
0x1801038e8  lea     rcx, [rbp+70h+var_90]
0x1801038ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801038f1  mov     r9, rax
0x1801038f4  lea     rax, sourceString
0x1801038fb  lea     r8, S; "\r\n"
0x180103902  test    bl, bl
0x180103904  cmovz   r8, rax
0x180103908  lea     rdx, aSS_1; "%s%s\r\n"
0x18010390f  lea     rcx, [rbp+70h+var_60]
0x180103913  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180103918  nop
0x180103919  mov     eax, [rbp+70h+var_50]
0x18010391c  lea     ebx, [rax+rax]
0x18010391f  lea     rcx, [rbp+70h+var_60]
0x180103923  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180103928  mov     rdx, rax; lpBuffer
0x18010392b  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
  ... truncated ...
```
