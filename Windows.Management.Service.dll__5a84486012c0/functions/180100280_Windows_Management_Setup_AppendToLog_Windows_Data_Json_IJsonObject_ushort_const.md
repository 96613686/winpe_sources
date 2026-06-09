# Windows::Management::Setup::AppendToLog(Windows::Data::Json::IJsonObject *,ushort const *)

- ea: `0x180100280`
- end: `0x180100891`
- name: `?AppendToLog@Setup@Management@Windows@@YAJPEAUIJsonObject@Json@Data@3@PEBG@Z`
- size: `1553`
- prototype: `__int64 __fastcall(Windows::Management::Setup *__hidden this, struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180100e70`
- `0x180101150`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x1800873a4`
- `0x18008a014`
- `0x18008b9c4`
- `0x18008cfa4`
- `0x18008d484`
- `0x18008d818`
- `0x18008dddc`
- `0x18008f068`
- `0x1800fba84`
- `0x180100280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801003de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801003de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801007bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801007bd`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801006ad`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801006ad`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18010049f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18010049f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801003c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010044f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100627`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801003c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010044f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180100627`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180100684`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010077c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801007f3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180100684`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010077c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801007f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801002b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801002b9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801005d2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801005d2`

## string_xrefs

- `0x1801002f3`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180100364`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801003ff`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010047c`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801004c8`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010052b`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180100586`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801005e1`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801006e4`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010078a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180100801`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x18010030c`: `ProvisioningStatus\PageUpdate`
- `0x1801004fe`: `ProvisioningStatus\PageUpdate`

## pseudocode

```c
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
0x180100280  mov     [rsp-8+arg_10], rbx
0x180100285  mov     [rsp-8+arg_18], rsi
0x18010028a  push    rbp
0x18010028b  push    rdi
0x18010028c  push    r14
0x18010028e  lea     rbp, [rsp-60h]
0x180100293  sub     rsp, 160h
0x18010029a  mov     rax, cs:__security_cookie
0x1801002a1  xor     rax, rsp
0x1801002a4  mov     [rbp+70h+var_20], rax
0x1801002a8  mov     rsi, rdx
0x1801002ab  mov     r14, rcx
0x1801002ae  xorps   xmm0, xmm0
0x1801002b1  movups  xmmword ptr [rbp+70h+SystemTime.wYear], xmm0
0x1801002b5  lea     rcx, [rbp+70h+SystemTime]; lpSystemTime
0x1801002b9  call    cs:__imp_GetSystemTime
0x1801002bf  xorps   xmm0, xmm0
0x1801002c2  movups  [rbp+70h+var_90], xmm0
0x1801002c6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801002ce  movdqu  [rbp+70h+var_80], xmm1
0x1801002d3  xor     eax, eax
0x1801002d5  mov     word ptr [rbp+70h+var_90], ax
0x1801002d9  lea     rdx, [rbp+70h+var_90]
0x1801002dd  lea     rcx, [rbp+70h+SystemTime]
0x1801002e1  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x1801002e6  mov     ebx, eax
0x1801002e8  test    eax, eax
0x1801002ea  jns     short loc_180100309
0x1801002ec  mov     rcx, [rbp+78h]; this
0x1801002f0  mov     r9d, eax; char *
0x1801002f3  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801002fa  mov     edx, 0B5h; void *
0x1801002ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100304  jmp     loc_180100862
0x180100309  mov     r9, rsi
0x18010030c  lea     r8, aProvisioningst_0; "ProvisioningStatus\\PageUpdate"
0x180100313  lea     rdx, aSSLog; "%s\\%s.log"
0x18010031a  lea     rcx, [rbp+70h+var_F0]
0x18010031e  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180100323  nop
0x180100324  xorps   xmm0, xmm0
0x180100327  movups  [rsp+170h+var_110], xmm0
0x18010032c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180100334  movdqu  [rsp+170h+var_100], xmm1
0x18010033a  xor     eax, eax
0x18010033c  mov     word ptr [rsp+170h+var_110], ax
0x180100341  lea     rcx, [rbp+70h+var_F0]
0x180100345  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010034a  mov     rcx, rax
0x18010034d  lea     rdx, [rsp+170h+var_110]
0x180100352  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x180100357  mov     ebx, eax
0x180100359  test    eax, eax
0x18010035b  jns     short loc_18010038F
0x18010035d  mov     rcx, [rbp+78h]; this
0x180100361  mov     r9d, eax; char *
0x180100364  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010036b  mov     edx, 0BCh; void *
0x180100370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100375  nop
0x180100376  lea     rcx, [rsp+170h+var_110]
0x18010037b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100380  nop
0x180100381  lea     rcx, [rbp+70h+var_F0]
0x180100385  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010038a  jmp     loc_180100862
0x18010038f  lea     rcx, [rsp+170h+var_110]
0x180100394  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180100399  mov     rcx, rax; lpFileName
0x18010039c  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x1801003a5  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801003ad  mov     [rsp+170h+dwCreationDisposition], 3; int
0x1801003b5  xor     r9d, r9d; lpSecurityAttributes
0x1801003b8  mov     edx, 12019Fh; dwDesiredAccess
0x1801003bd  lea     r8d, [r9+2]; dwShareMode
0x1801003c1  call    cs:__imp_CreateFileW
0x1801003c7  mov     rdi, rax
0x1801003ca  mov     [rsp+170h+hFile], rax
0x1801003cf  inc     rax
0x1801003d2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801003d8  jnz     loc_18010048E
0x1801003de  call    cs:__imp_GetLastError
0x1801003e4  lea     ecx, [rax-2]
0x1801003e7  mov     ebx, 1
0x1801003ec  cmp     ecx, ebx
0x1801003ee  jbe     short loc_180100421
0x1801003f0  test    eax, eax
0x1801003f2  jz      loc_180100841
0x1801003f8  mov     rcx, [rbp+78h]; this
0x1801003fc  mov     r9d, eax; char *
0x1801003ff  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180100406  mov     edx, 0CDh; void *
0x18010040b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180100410  mov     ebx, eax
0x180100412  lea     rcx, [rsp+170h+hFile]
0x180100417  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010041c  jmp     loc_180100376
0x180100421  lea     rcx, [rsp+170h+var_110]
0x180100426  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010042b  mov     rcx, rax; lpFileName
0x18010042e  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x180100437  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18010043f  mov     [rsp+170h+dwCreationDisposition], ebx; dwCreationDisposition
0x180100443  xor     r9d, r9d; lpSecurityAttributes
0x180100446  mov     edx, 12019Fh; dwDesiredAccess
0x18010044b  lea     r8d, [r9+2]; dwShareMode
0x18010044f  call    cs:__imp_CreateFileW
0x180100455  mov     rdx, rax
0x180100458  lea     rcx, [rsp+170h+hFile]
0x18010045d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180100462  mov     rdi, [rsp+170h+hFile]
0x180100467  lea     rax, [rdi+1]
0x18010046b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180100471  jnz     loc_180100664
0x180100477  mov     edx, 0D9h; void *
0x18010047c  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180100483  mov     rcx, [rbp+78h]; this
0x180100487  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010048c  jmp     short loc_180100410
0x18010048e  mov     qword ptr [rsp+170h+FileSize], 0
0x180100497  lea     rdx, [rsp+170h+FileSize]; lpFileSize
0x18010049c  mov     rcx, rdi; hFile
0x18010049f  call    cs:__imp_GetFileSizeEx
0x1801004a5  test    eax, eax
0x1801004a7  jnz     short loc_1801004B0
0x1801004a9  mov     edx, 0DFh
0x1801004ae  jmp     short loc_18010047C
0x1801004b0  mov     eax, 0FFFFFFFFh
0x1801004b5  cmp     qword ptr [rsp+170h+FileSize], rax
0x1801004ba  jl      short loc_1801004DE
0x1801004bc  mov     rcx, [rbp+78h]; this
0x1801004c0  mov     ebx, 80070216h
0x1801004c5  mov     r9d, ebx; char *
0x1801004c8  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801004cf  mov     edx, 0E0h; void *
0x1801004d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801004d9  jmp     loc_180100412
0x1801004de  cmp     qword ptr [rsp+170h+FileSize], 100000h
0x1801004e7  jl      loc_18010069C
0x1801004ed  lea     rcx, [rbp+70h+var_90]
0x1801004f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801004f6  mov     qword ptr [rsp+170h+dwCreationDisposition], rax; int
0x1801004fb  mov     r9, rsi
0x1801004fe  lea     r8, aProvisioningst_0; "ProvisioningStatus\\PageUpdate"
0x180100505  lea     rdx, aSSSLog; "%s\\%s_%s.log"
0x18010050c  lea     rcx, [rbp+70h+var_B0]
0x180100510  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180100515  lea     rcx, [rbp+70h+var_B0]
0x180100519  call    ?NormalizeFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::NormalizeFilePath(std::wstring &)
0x18010051e  mov     ebx, eax
0x180100520  test    eax, eax
0x180100522  jns     short loc_18010054A
0x180100524  mov     rcx, [rbp+78h]; this
0x180100528  mov     r9d, eax; char *
0x18010052b  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180100532  mov     edx, 0E9h; void *
0x180100537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010053c  lea     rcx, [rbp+70h+var_B0]
0x180100540  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100545  jmp     loc_180100412
0x18010054a  xorps   xmm0, xmm0
0x18010054d  movups  [rbp+70h+var_D0], xmm0
0x180100551  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180100559  movdqu  [rbp+70h+var_C0], xmm1
0x18010055e  xor     eax, eax
0x180100560  mov     word ptr [rbp+70h+var_D0], ax
0x180100564  lea     rcx, [rbp+70h+var_B0]
0x180100568  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010056d  mov     rcx, rax
0x180100570  lea     rdx, [rbp+70h+var_D0]
0x180100574  call    ?GetStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x180100579  mov     ebx, eax
0x18010057b  test    eax, eax
0x18010057d  jns     short loc_1801005A2
0x18010057f  mov     rcx, [rbp+78h]; this
0x180100583  mov     r9d, eax; char *
0x180100586  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010058d  mov     edx, 0EEh; void *
0x180100592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100597  lea     rcx, [rbp+70h+var_D0]
0x18010059b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801005a0  jmp     short loc_18010053C
0x1801005a2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801005a6  lea     rcx, [rsp+170h+hFile]
0x1801005ab  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801005b0  lea     rcx, [rbp+70h+var_D0]
0x1801005b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801005b9  mov     rbx, rax
0x1801005bc  lea     rcx, [rsp+170h+var_110]
0x1801005c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801005c6  mov     rcx, rax; lpExistingFileName
0x1801005c9  mov     r8d, 9; dwFlags
0x1801005cf  mov     rdx, rbx; lpNewFileName
0x1801005d2  call    cs:__imp_MoveFileExW
0x1801005d8  test    eax, eax
0x1801005da  jnz     short loc_1801005F5
0x1801005dc  mov     edx, 0F1h; void *
0x1801005e1  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801005e8  mov     rcx, [rbp+78h]; this
0x1801005ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801005f1  mov     ebx, eax
0x1801005f3  jmp     short loc_180100597
0x1801005f5  lea     rcx, [rsp+170h+var_110]
0x1801005fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801005ff  mov     rcx, rax; lpFileName
0x180100602  mov     [rsp+170h+hTemplateFile], 0; hTemplateFile
0x18010060b  mov     [rsp+170h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180100613  mov     [rsp+170h+dwCreationDisposition], 1; dwCreationDisposition
0x18010061b  xor     r9d, r9d; lpSecurityAttributes
0x18010061e  mov     edx, 12019Fh; dwDesiredAccess
0x180100623  lea     r8d, [r9+2]; dwShareMode
0x180100627  call    cs:__imp_CreateFileW
0x18010062d  mov     rdx, rax
0x180100630  lea     rcx, [rsp+170h+hFile]
0x180100635  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18010063a  mov     rdi, [rsp+170h+hFile]
0x18010063f  lea     rax, [rdi+1]
0x180100643  test    rax, 0FFFFFFFFFFFFFFFEh
0x180100649  jnz     short loc_180100652
0x18010064b  mov     edx, 0FCh
0x180100650  jmp     short loc_1801005E1
0x180100652  lea     rcx, [rbp+70h+var_D0]
0x180100656  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010065b  lea     rcx, [rbp+70h+var_B0]
0x18010065f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100664  mov     [rsp+170h+Buffer], 0FEFFh
0x18010066c  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x180100675  xor     r9d, r9d; lpNumberOfBytesWritten
0x180100678  lea     r8d, [r9+4]; nNumberOfBytesToWrite
0x18010067c  lea     rdx, [rsp+170h+Buffer]; lpBuffer
0x180100681  mov     rcx, rdi; hFile
0x180100684  call    cs:__imp_WriteFile
0x18010068a  test    eax, eax
0x18010068c  jnz     short loc_180100698
0x18010068e  mov     edx, 108h
0x180100693  jmp     loc_18010047C
0x180100698  xor     bl, bl
0x18010069a  jmp     short loc_1801006A1
0x18010069c  mov     ebx, 1
0x1801006a1  xor     edx, edx; liDistanceToMove
0x1801006a3  lea     r9d, [rdx+2]; dwMoveMethod
0x1801006a7  xor     r8d, r8d; lpNewFilePointer
0x1801006aa  mov     rcx, rdi; hFile
0x1801006ad  call    cs:__imp_SetFilePointerEx
0x1801006b3  test    eax, eax
0x1801006b5  jnz     short loc_1801006C1
0x1801006b7  mov     edx, 10Dh
0x1801006bc  jmp     loc_18010047C
0x1801006c1  mov     [rsp+170h+string], 0
0x1801006ca  lea     rdx, [rsp+170h+string]
0x1801006cf  mov     rcx, r14
0x1801006d2  call    ?ToString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToString(Windows::Data::Json::IJsonObject *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1801006d7  mov     esi, eax
0x1801006d9  test    eax, eax
0x1801006db  jns     short loc_180100727
0x1801006dd  mov     rcx, [rbp+78h]; this
0x1801006e1  mov     r9d, eax; char *
0x1801006e4  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801006eb  mov     edx, 110h; void *
0x1801006f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801006f5  nop
0x1801006f6  lea     rcx, [rsp+170h+string]; this
0x1801006fb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180100700  nop
0x180100701  lea     rcx, [rsp+170h+hFile]
0x180100706  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010070b  nop
0x18010070c  lea     rcx, [rsp+170h+var_110]
0x180100711  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100716  nop
0x180100717  lea     rcx, [rbp+70h+var_F0]
0x18010071b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180100720  mov     ebx, esi
0x180100722  jmp     loc_180100862
0x180100727  lea     rcx, [rbp+70h+var_90]
0x18010072b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180100730  mov     r9, rax
0x180100733  lea     rax, sourceString
0x18010073a  lea     r8, S; "\r\n"
0x180100741  test    bl, bl
0x180100743  cmovz   r8, rax
0x180100747  lea     rdx, aSS_1; "%s%s\r\n"
0x18010074e  lea     rcx, [rbp+70h+var_60]
0x180100752  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180100757  nop
0x180100758  mov     eax, [rbp+70h+var_50]
0x18010075b  lea     ebx, [rax+rax]
0x18010075e  lea     rcx, [rbp+70h+var_60]
0x180100762  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180100767  mov     rdx, rax; lpBuffer
0x18010076a  mov     qword ptr [rsp+170h+dwCreationDisposition], 0; lpOverlapped
0x180100773  xor     r9d, r9d; lpNumberOfBytesWritten
0x180100776  mov     r8d, ebx; nNumberOfBytesToWrite
0x180100779  mov     rcx, rdi; hFile
0x18010077c  call    cs:__imp_WriteFile
0x180100782  test    eax, eax
0x180100784  jnz     short loc_1801007B6
0x180100786  mov     rcx, [rbp+78h]; this
0x18010078a  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180100791  mov     edx, 114h; void *
  ... truncated ...
```
