# Windows::Management::Setup::ProvisioningSessionLogger::LogNotifyProgressPageStateChangeData(_GUID const &,Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *)

- ea: `0x180101150`
- end: `0x18010146e`
- name: `?LogNotifyProgressPageStateChangeData@ProvisioningSessionLogger@Setup@Management@Windows@@UEAAJAEBU_GUID@@PEAUIDeploymentSessionStateChangedEventArgs@234@@Z`
- size: `798`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18006e0a8`
- `0x18007755c`
- `0x18008019c`
- `0x1800853a0`
- `0x180089b58`
- `0x18008b9c4`
- `0x18008e438`
- `0x18008e584`
- `0x1800fba84`
- `0x180100280`
- `0x180101150`
- `0x180101cb4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180101186`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180101186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801012d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801012d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801012c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010141e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101281`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801012c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010141e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801011f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801011f0`

## string_xrefs

- `0x1801011a4`: `Windows.Data.Json.JsonObject`
- `0x1801011cf`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180101227`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801012a7`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180101381`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801013e8`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall Windows::Management::Setup::ProvisioningSessionLogger::LogNotifyProgressPageStateChangeData(
        RTL_SRWLOCK *this,
        const struct _GUID *a2,
        struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *a3)
{
  RTL_SRWLOCK *v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rax
  __int64 (__fastcall *v12)(struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v16; // r8
  const unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // rax
  struct Windows::Data::Json::IJsonObject *v20; // rax
  const unsigned __int16 *v21; // r8
  int v22; // eax
  HSTRING string; // [rsp+20h] [rbp-89h] BYREF
  struct Windows::Data::Json::IJsonObject *v25; // [rsp+28h] [rbp-81h] BYREF
  unsigned int v26; // [rsp+30h] [rbp-79h] BYREF
  RTL_SRWLOCK *v27; // [rsp+38h] [rbp-71h] BYREF
  _OWORD v28[2]; // [rsp+40h] [rbp-69h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v30[32]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v31[32]; // [rsp+90h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v33; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v6 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v27 = v6;
  v25 = 0;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v33, &v25);
  v8 = v7;
  if ( v7 >= 0 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v28[0] = 0;
    v28[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v28[0]) = 0;
    v9 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, v28);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = 295;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
        (const char *)(unsigned int)v9,
        (int)string);
LABEL_6:
      std::wstring::_Tidy_deallocate(v28);
      goto LABEL_25;
    }
    v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    v9 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v25, L"Date", v11);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = 296;
      goto LABEL_5;
    }
    string = 0;
    v12 = *(__int64 (__fastcall **)(struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(a3, &string);
    v8 = v13;
    if ( v13 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v25, L"SessionId", StringRawBuffer);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v26 = 0;
        v13 = (*(__int64 (__fastcall **)(struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *, unsigned int *))(*(_QWORD *)a3 + 56LL))(
                a3,
                &v26);
        v8 = v13;
        if ( v13 >= 0 )
        {
          v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v25, L"DeploymentSessionStateChange", v26);
          v8 = v13;
          if ( v13 >= 0 )
          {
            LOBYTE(v16) = 1;
            Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(v30, a2, v16);
            v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
            v18 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v25, L"OrchestratorContext", v17);
            v8 = v18;
            if ( v18 >= 0 )
            {
              v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[5]);
              wil::str_printf<std::wstring>(v31, L"%s_%s", L"ProgressStateChange", v19);
              v20 = (struct Windows::Data::Json::IJsonObject *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
              v22 = Windows::Management::Setup::AppendToLog(v25, v20, v21);
              v8 = v22;
              if ( v22 >= 0 )
              {
                std::wstring::_Tidy_deallocate(v31);
                std::wstring::_Tidy_deallocate(v30);
                WindowsDeleteString(string);
                string = 0;
                std::wstring::_Tidy_deallocate(v28);
                v8 = 0;
                goto LABEL_25;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x13A,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioning"
                              "sessionlogger.cpp",
                (const char *)(unsigned int)v22,
                (int)string);
              std::wstring::_Tidy_deallocate(v31);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x133,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioning"
                              "sessionlogger.cpp",
                (const char *)(unsigned int)v18,
                (int)string);
            }
            std::wstring::_Tidy_deallocate(v30);
            goto LABEL_12;
          }
          v14 = 304;
        }
        else
        {
          v14 = 303;
        }
      }
      else
      {
        v14 = 300;
      }
    }
    else
    {
      v14 = 299;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
      (const char *)(unsigned int)v13,
      (int)string);
LABEL_12:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x122,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\provisioningsessionlogger.cpp",
    (const char *)(unsigned int)v7,
    (int)string);
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
  return v8;
}

```

## disassembly

```asm
0x180101150  mov     [rsp-8+arg_18], rbx
0x180101155  push    rbp
0x180101156  push    rsi
0x180101157  push    rdi
0x180101158  push    r14
0x18010115a  push    r15
0x18010115c  lea     rbp, [rsp-37h]
0x180101161  sub     rsp, 0E0h
0x180101168  mov     rax, cs:__security_cookie
0x18010116f  xor     rax, rsp
0x180101172  mov     [rbp+57h+var_30], rax
0x180101176  mov     rdi, r8
0x180101179  mov     r14, rdx
0x18010117c  mov     rsi, rcx
0x18010117f  lea     rbx, [rcx+8]
0x180101183  mov     rcx, rbx; SRWLock
0x180101186  call    cs:__imp_AcquireSRWLockExclusive
0x18010118c  mov     [rbp+57h+var_C8], rbx
0x180101190  xor     r15d, r15d
0x180101193  mov     [rsp+100h+var_D8], r15
0x180101198  mov     [rbp+57h+var_38], r15
0x18010119c  lea     r9d, [r15+1Ch]; unsigned int
0x1801011a0  lea     r8d, [r15+1Dh]; unsigned int
0x1801011a4  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801011ab  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801011af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801011b4  lea     rdx, [rsp+100h+var_D8]
0x1801011b9  mov     rcx, [rbp+57h+var_38]
0x1801011bd  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801011c2  mov     ebx, eax
0x1801011c4  test    eax, eax
0x1801011c6  jns     short loc_1801011E5
0x1801011c8  mov     rcx, [rbp+5Fh]; this
0x1801011cc  mov     r9d, eax; char *
0x1801011cf  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801011d6  mov     edx, 122h; void *
0x1801011db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801011e0  jmp     loc_180101435
0x1801011e5  xorps   xmm0, xmm0
0x1801011e8  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1801011ec  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1801011f0  call    cs:__imp_GetSystemTime
0x1801011f6  xorps   xmm0, xmm0
0x1801011f9  movups  [rbp+57h+var_C0], xmm0
0x1801011fd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180101205  movdqu  [rbp+57h+var_B0], xmm1
0x18010120a  mov     word ptr [rbp+57h+var_C0], r15w
0x18010120f  lea     rdx, [rbp+57h+var_C0]
0x180101213  lea     rcx, [rbp+57h+SystemTime]
0x180101217  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x18010121c  mov     ebx, eax
0x18010121e  test    eax, eax
0x180101220  jns     short loc_180101249
0x180101222  mov     edx, 127h; void *
0x180101227  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010122e  mov     r9d, eax; char *
0x180101231  mov     rcx, [rbp+5Fh]; this
0x180101235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010123a  nop
0x18010123b  lea     rcx, [rbp+57h+var_C0]
0x18010123f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180101244  jmp     loc_180101435
0x180101249  lea     rcx, [rbp+57h+var_C0]
0x18010124d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180101252  mov     r8, rax; unsigned __int16 *
0x180101255  lea     rdx, aDate; "Date"
0x18010125c  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x180101261  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180101266  mov     ebx, eax
0x180101268  test    eax, eax
0x18010126a  jns     short loc_180101273
0x18010126c  mov     edx, 128h
0x180101271  jmp     short loc_180101227
0x180101273  mov     [rsp+100h+string], r15
0x180101278  mov     rax, [rdi]
0x18010127b  mov     rbx, [rax+30h]
0x18010127f  xor     ecx, ecx; string
0x180101281  call    cs:__imp_WindowsDeleteString
0x180101287  mov     [rsp+100h+string], r15; int
0x18010128c  lea     rdx, [rsp+100h+string]
0x180101291  mov     rcx, rdi
0x180101294  mov     rax, rbx
0x180101297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010129c  mov     ebx, eax
0x18010129e  test    eax, eax
0x1801012a0  jns     short loc_1801012D0
0x1801012a2  mov     edx, 12Bh; void *
0x1801012a7  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801012ae  mov     r9d, eax; char *
0x1801012b1  mov     rcx, [rbp+5Fh]; this
0x1801012b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801012ba  nop
0x1801012bb  mov     rcx, [rsp+100h+string]; string
0x1801012c0  call    cs:__imp_WindowsDeleteString
0x1801012c6  mov     [rsp+100h+string], r15
0x1801012cb  jmp     loc_18010123B
0x1801012d0  xor     edx, edx; length
0x1801012d2  mov     rcx, [rsp+100h+string]; string
0x1801012d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801012dd  mov     r8, rax; unsigned __int16 *
0x1801012e0  lea     rdx, aSessionid; "SessionId"
0x1801012e7  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x1801012ec  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801012f1  mov     ebx, eax
0x1801012f3  test    eax, eax
0x1801012f5  jns     short loc_1801012FE
0x1801012f7  mov     edx, 12Ch
0x1801012fc  jmp     short loc_1801012A7
0x1801012fe  mov     [rbp+57h+var_D0], r15d
0x180101302  mov     rax, [rdi]
0x180101305  lea     rdx, [rbp+57h+var_D0]
0x180101309  mov     rcx, rdi
0x18010130c  mov     rax, [rax+38h]
0x180101310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101315  mov     ebx, eax
0x180101317  test    eax, eax
0x180101319  jns     short loc_180101322
0x18010131b  mov     edx, 12Fh
0x180101320  jmp     short loc_1801012A7
0x180101322  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x180101326  lea     rdx, aDeploymentsess; "DeploymentSessionStateChange"
0x18010132d  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x180101332  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x180101337  mov     ebx, eax
0x180101339  test    eax, eax
0x18010133b  jns     short loc_180101347
0x18010133d  mov     edx, 130h
0x180101342  jmp     loc_1801012A7
0x180101347  mov     r8b, 1
0x18010134a  mov     rdx, r14
0x18010134d  lea     rcx, [rbp+57h+var_90]
0x180101351  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180101356  nop
0x180101357  lea     rcx, [rbp+57h+var_90]
0x18010135b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180101360  mov     r8, rax; unsigned __int16 *
0x180101363  lea     rdx, aOrchestratorco; "OrchestratorContext"
0x18010136a  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x18010136f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180101374  mov     ebx, eax
0x180101376  test    eax, eax
0x180101378  jns     short loc_1801013A1
0x18010137a  mov     rcx, [rbp+5Fh]; this
0x18010137e  mov     r9d, eax; char *
0x180101381  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180101388  mov     edx, 133h; void *
0x18010138d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101392  nop
0x180101393  lea     rcx, [rbp+57h+var_90]
0x180101397  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010139c  jmp     loc_1801012BB
0x1801013a1  lea     rcx, [rsi+28h]
0x1801013a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801013aa  mov     r9, rax
0x1801013ad  lea     r8, aProgressstatec; "ProgressStateChange"
0x1801013b4  lea     rdx, aSS; "%s_%s"
0x1801013bb  lea     rcx, [rbp+57h+var_70]
0x1801013bf  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801013c4  nop
0x1801013c5  lea     rcx, [rbp+57h+var_70]
0x1801013c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801013ce  mov     rdx, rax; struct Windows::Data::Json::IJsonObject *
0x1801013d1  mov     rcx, [rsp+100h+var_D8]; this
0x1801013d6  call    ?AppendToLog@Setup@Management@Windows@@YAJPEAUIJsonObject@Json@Data@3@PEBG@Z; Windows::Management::Setup::AppendToLog(Windows::Data::Json::IJsonObject *,ushort const *)
0x1801013db  mov     ebx, eax
0x1801013dd  test    eax, eax
0x1801013df  jns     short loc_180101405
0x1801013e1  mov     rcx, [rbp+5Fh]; this
0x1801013e5  mov     r9d, eax; char *
0x1801013e8  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801013ef  mov     edx, 13Ah; void *
0x1801013f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801013f9  nop
0x1801013fa  lea     rcx, [rbp+57h+var_70]
0x1801013fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180101403  jmp     short loc_180101393
0x180101405  lea     rcx, [rbp+57h+var_70]
0x180101409  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010140e  nop
0x18010140f  lea     rcx, [rbp+57h+var_90]
0x180101413  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180101418  nop
0x180101419  mov     rcx, [rsp+100h+string]; string
0x18010141e  call    cs:__imp_WindowsDeleteString
0x180101424  mov     [rsp+100h+string], r15
0x180101429  lea     rcx, [rbp+57h+var_C0]
0x18010142d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180101432  mov     ebx, r15d
0x180101435  lea     rcx, [rsp+100h+var_D8]
0x18010143a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010143f  nop
0x180101440  lea     rcx, [rbp+57h+var_C8]
0x180101444  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180101449  mov     eax, ebx
0x18010144b  mov     rcx, [rbp+57h+var_30]
0x18010144f  xor     rcx, rsp; StackCookie
0x180101452  call    __security_check_cookie
0x180101457  mov     rbx, [rsp+100h+arg_18]
0x18010145f  add     rsp, 0E0h
0x180101466  pop     r15
0x180101468  pop     r14
0x18010146a  pop     rdi
0x18010146b  pop     rsi
0x18010146c  pop     rbp
0x18010146d  retn
```
