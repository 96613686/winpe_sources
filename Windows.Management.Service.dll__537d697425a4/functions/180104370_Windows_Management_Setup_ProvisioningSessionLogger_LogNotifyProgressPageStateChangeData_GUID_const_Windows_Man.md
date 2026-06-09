# Windows::Management::Setup::ProvisioningSessionLogger::LogNotifyProgressPageStateChangeData(_GUID const &,Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *)

- ea: `0x180104370`
- end: `0x1801046b6`
- name: `?LogNotifyProgressPageStateChangeData@ProvisioningSessionLogger@Setup@Management@Windows@@UEAAJAEBU_GUID@@PEAUIDeploymentSessionStateChangedEventArgs@234@@Z`
- size: `838`
- prototype: `__int64 __fastcall(Windows::Management::Setup::ProvisioningSessionLogger *__hidden this, const struct _GUID *, struct Windows::Management::Setup::IDeploymentSessionStateChangedEventArgs *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x18006e608`
- `0x180077de0`
- `0x180080bac`
- `0x180086044`
- `0x18008a9c4`
- `0x18008c9a8`
- `0x18008f570`
- `0x18008f6c0`
- `0x1800feb74`
- `0x180103408`
- `0x180104370`
- `0x180104f08`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801043a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801043a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010450f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010450f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801044ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801044f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010465f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801044ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801044f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010465f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180104416`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180104416`

## string_xrefs

- `0x1801043ca`: `Windows.Data.Json.JsonObject`
- `0x1801043f5`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180104453`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801044d9`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x1801045c2`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`
- `0x180104629`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\provisioningsessionlogger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180104370  mov     [rsp-8+arg_18], rbx
0x180104375  push    rbp
0x180104376  push    rsi
0x180104377  push    rdi
0x180104378  push    r14
0x18010437a  push    r15
0x18010437c  lea     rbp, [rsp-37h]
0x180104381  sub     rsp, 0E0h
0x180104388  mov     rax, cs:__security_cookie
0x18010438f  xor     rax, rsp
0x180104392  mov     [rbp+57h+var_30], rax
0x180104396  mov     rdi, r8
0x180104399  mov     r14, rdx
0x18010439c  mov     rsi, rcx
0x18010439f  lea     rbx, [rcx+8]
0x1801043a3  mov     rcx, rbx; SRWLock
0x1801043a6  call    cs:__imp_AcquireSRWLockExclusive
0x1801043ad  nop     dword ptr [rax+rax+00h]
0x1801043b2  mov     [rbp+57h+var_C8], rbx
0x1801043b6  xor     r15d, r15d
0x1801043b9  mov     [rsp+100h+var_D8], r15
0x1801043be  mov     [rbp+57h+var_38], r15
0x1801043c2  lea     r9d, [r15+1Ch]; unsigned int
0x1801043c6  lea     r8d, [r15+1Dh]; unsigned int
0x1801043ca  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801043d1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801043d5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801043da  lea     rdx, [rsp+100h+var_D8]
0x1801043df  mov     rcx, [rbp+57h+var_38]
0x1801043e3  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801043e8  mov     ebx, eax
0x1801043ea  test    eax, eax
0x1801043ec  jns     short loc_18010440B
0x1801043ee  mov     rcx, [rbp+5Fh]; this
0x1801043f2  mov     r9d, eax; char *
0x1801043f5  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801043fc  mov     edx, 122h; void *
0x180104401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104406  jmp     loc_18010467C
0x18010440b  xorps   xmm0, xmm0
0x18010440e  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180104412  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180104416  call    cs:__imp_GetSystemTime
0x18010441d  nop     dword ptr [rax+rax+00h]
0x180104422  xorps   xmm0, xmm0
0x180104425  movups  [rbp+57h+var_C0], xmm0
0x180104429  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180104431  movdqu  [rbp+57h+var_B0], xmm1
0x180104436  mov     word ptr [rbp+57h+var_C0], r15w
0x18010443b  lea     rdx, [rbp+57h+var_C0]
0x18010443f  lea     rcx, [rbp+57h+SystemTime]
0x180104443  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x180104448  mov     ebx, eax
0x18010444a  test    eax, eax
0x18010444c  jns     short loc_180104475
0x18010444e  mov     edx, 127h; void *
0x180104453  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010445a  mov     r9d, eax; char *
0x18010445d  mov     rcx, [rbp+5Fh]; this
0x180104461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104466  nop
0x180104467  lea     rcx, [rbp+57h+var_C0]
0x18010446b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104470  jmp     loc_18010467C
0x180104475  lea     rcx, [rbp+57h+var_C0]
0x180104479  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010447e  mov     r8, rax; unsigned __int16 *
0x180104481  lea     rdx, aDate; "Date"
0x180104488  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x18010448d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180104492  mov     ebx, eax
0x180104494  test    eax, eax
0x180104496  jns     short loc_18010449F
0x180104498  mov     edx, 128h
0x18010449d  jmp     short loc_180104453
0x18010449f  mov     [rsp+100h+string], r15
0x1801044a4  mov     rax, [rdi]
0x1801044a7  mov     rbx, [rax+30h]
0x1801044ab  xor     ecx, ecx; string
0x1801044ad  call    cs:__imp_WindowsDeleteString
0x1801044b4  nop     dword ptr [rax+rax+00h]
0x1801044b9  mov     [rsp+100h+string], r15; int
0x1801044be  lea     rdx, [rsp+100h+string]
0x1801044c3  mov     rcx, rdi
0x1801044c6  mov     rax, rbx
0x1801044c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801044ce  mov     ebx, eax
0x1801044d0  test    eax, eax
0x1801044d2  jns     short loc_180104508
0x1801044d4  mov     edx, 12Bh; void *
0x1801044d9  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801044e0  mov     r9d, eax; char *
0x1801044e3  mov     rcx, [rbp+5Fh]; this
0x1801044e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801044ec  nop
0x1801044ed  mov     rcx, [rsp+100h+string]; string
0x1801044f2  call    cs:__imp_WindowsDeleteString
0x1801044f9  nop     dword ptr [rax+rax+00h]
0x1801044fe  mov     [rsp+100h+string], r15
0x180104503  jmp     loc_180104467
0x180104508  xor     edx, edx; length
0x18010450a  mov     rcx, [rsp+100h+string]; string
0x18010450f  call    cs:__imp_WindowsGetStringRawBuffer
0x180104516  nop     dword ptr [rax+rax+00h]
0x18010451b  mov     r8, rax; unsigned __int16 *
0x18010451e  lea     rdx, aSessionid; "SessionId"
0x180104525  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x18010452a  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18010452f  mov     ebx, eax
0x180104531  test    eax, eax
0x180104533  jns     short loc_18010453C
0x180104535  mov     edx, 12Ch
0x18010453a  jmp     short loc_1801044D9
0x18010453c  mov     [rbp+57h+var_D0], r15d
0x180104540  mov     rax, [rdi]
0x180104543  lea     rdx, [rbp+57h+var_D0]
0x180104547  mov     rcx, rdi
0x18010454a  mov     rax, [rax+38h]
0x18010454e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104553  mov     ebx, eax
0x180104555  test    eax, eax
0x180104557  jns     short loc_180104563
0x180104559  mov     edx, 12Fh
0x18010455e  jmp     loc_1801044D9
0x180104563  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x180104567  lea     rdx, aDeploymentsess; "DeploymentSessionStateChange"
0x18010456e  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x180104573  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x180104578  mov     ebx, eax
0x18010457a  test    eax, eax
0x18010457c  jns     short loc_180104588
0x18010457e  mov     edx, 130h
0x180104583  jmp     loc_1801044D9
0x180104588  mov     r8b, 1
0x18010458b  mov     rdx, r14
0x18010458e  lea     rcx, [rbp+57h+var_90]
0x180104592  call    ?GuidToString@InitialProvisioningKnownGuids@Setup@Management@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Windows::Management::Setup::InitialProvisioningKnownGuids::GuidToString(_GUID const &,bool)
0x180104597  nop
0x180104598  lea     rcx, [rbp+57h+var_90]
0x18010459c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801045a1  mov     r8, rax; unsigned __int16 *
0x1801045a4  lea     rdx, aOrchestratorco; "OrchestratorContext"
0x1801045ab  mov     rcx, [rsp+100h+var_D8]; struct Windows::Data::Json::IJsonObject *
0x1801045b0  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801045b5  mov     ebx, eax
0x1801045b7  test    eax, eax
0x1801045b9  jns     short loc_1801045E2
0x1801045bb  mov     rcx, [rbp+5Fh]; this
0x1801045bf  mov     r9d, eax; char *
0x1801045c2  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801045c9  mov     edx, 133h; void *
0x1801045ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801045d3  nop
0x1801045d4  lea     rcx, [rbp+57h+var_90]
0x1801045d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801045dd  jmp     loc_1801044ED
0x1801045e2  lea     rcx, [rsi+28h]
0x1801045e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801045eb  mov     r9, rax
0x1801045ee  lea     r8, aProgressstatec; "ProgressStateChange"
0x1801045f5  lea     rdx, aSS; "%s_%s"
0x1801045fc  lea     rcx, [rbp+57h+var_70]
0x180104600  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x180104605  nop
0x180104606  lea     rcx, [rbp+57h+var_70]
0x18010460a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010460f  mov     rdx, rax; struct Windows::Data::Json::IJsonObject *
0x180104612  mov     rcx, [rsp+100h+var_D8]; this
0x180104617  call    ?AppendToLog@Setup@Management@Windows@@YAJPEAUIJsonObject@Json@Data@3@PEBG@Z; Windows::Management::Setup::AppendToLog(Windows::Data::Json::IJsonObject *,ushort const *)
0x18010461c  mov     ebx, eax
0x18010461e  test    eax, eax
0x180104620  jns     short loc_180104646
0x180104622  mov     rcx, [rbp+5Fh]; this
0x180104626  mov     r9d, eax; char *
0x180104629  lea     r8, aOnecoreuapAdmi_80; "onecoreuap\\admin\\moderndeployment\\au"...
0x180104630  mov     edx, 13Ah; void *
0x180104635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010463a  nop
0x18010463b  lea     rcx, [rbp+57h+var_70]
0x18010463f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104644  jmp     short loc_1801045D4
0x180104646  lea     rcx, [rbp+57h+var_70]
0x18010464a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010464f  nop
0x180104650  lea     rcx, [rbp+57h+var_90]
0x180104654  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104659  nop
0x18010465a  mov     rcx, [rsp+100h+string]; string
0x18010465f  call    cs:__imp_WindowsDeleteString
0x180104666  nop     dword ptr [rax+rax+00h]
0x18010466b  mov     [rsp+100h+string], r15
0x180104670  lea     rcx, [rbp+57h+var_C0]
0x180104674  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104679  mov     ebx, r15d
0x18010467c  lea     rcx, [rsp+100h+var_D8]
0x180104681  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180104686  nop
0x180104687  lea     rcx, [rbp+57h+var_C8]
0x18010468b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180104690  mov     eax, ebx
0x180104692  mov     rcx, [rbp+57h+var_30]
0x180104696  xor     rcx, rsp; StackCookie
0x180104699  call    __security_check_cookie
0x18010469e  mov     rbx, [rsp+100h+arg_18]
0x1801046a6  add     rsp, 0E0h
0x1801046ad  pop     r15
0x1801046af  pop     r14
0x1801046b1  pop     rdi
0x1801046b2  pop     rsi
0x1801046b3  pop     rbp
0x1801046b4  retn
```
