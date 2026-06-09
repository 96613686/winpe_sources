# Windows::Management::Setup::UriApplicationLauncher::AttemptUriSchemeLaunch(ushort const *)

- ea: `0x180104e30`
- end: `0x180105570`
- name: `?AttemptUriSchemeLaunch@UriApplicationLauncher@Setup@Management@Windows@@QEAAJPEBG@Z`
- size: `1856`
- prototype: `__int64 __fastcall(Windows::Management::Setup::UriApplicationLauncher *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180105a44`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x180081f1c`
- `0x1800839bc`
- `0x1800853a0`
- `0x18008c244`
- `0x18010006c`
- `0x18010024c`
- `0x180104b2c`
- `0x180104e30`
- `0x1801058fc`
- `0x180105e20`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180105029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801051c8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180105029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801051c8`

## string_xrefs

- `0x180104ff4`: `Windows.Foundation.Uri`
- `0x180104ef9`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180104f83`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180105047`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x18010510f`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801051e6`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801052a3`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x18010536d`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801053f3`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180105479`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180104e5a`: `AttemptUriSchemeLaunch`
- `0x18010530b`: `WaitForCompletionOrTimeoutNoThrow`
- `0x180105243`: `LaunchUriAsync`
- `0x180104fbf`: `GetActivationFactory RuntimeClass_Windows_Foundation_Uri`
- `0x18010508e`: `CreateUri`
- `0x180104e9d`: `ValidateSchemeCommandLine`
- `0x180104f2a`: `GetSchemeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Windows::Management::Setup::UriApplicationLauncher::AttemptUriSchemeLaunch(
        Windows::Management::Setup::UriApplicationLauncher *this,
        const unsigned __int16 *a2)
{
  char *v4; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  int SchemeUri; // eax
  unsigned int v9; // ebx
  __int64 v10; // rbx
  int ActivationFactory; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rbx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // ebx
  int v29; // [rsp+20h] [rbp-128h] BYREF
  __int64 v30; // [rsp+28h] [rbp-120h] BYREF
  __int64 v31; // [rsp+30h] [rbp-118h] BYREF
  __int64 v32; // [rsp+38h] [rbp-110h] BYREF
  __int64 v33; // [rsp+40h] [rbp-108h] BYREF
  __int64 v34; // [rsp+48h] [rbp-100h] BYREF
  _OWORD v35[2]; // [rsp+50h] [rbp-F8h] BYREF
  _OWORD v36[2]; // [rsp+70h] [rbp-D8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-A0h]
  int v39; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v40[120]; // [rsp+B8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  std::wstring::wstring(&hstringHeader, L"AttemptUriSchemeLaunch");
  v4 = (char *)this + 36;
  Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
  std::wstring::_Tidy_deallocate(&hstringHeader);
  std::wstring::assign(v40, L"ValidateSchemeCommandLine");
  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  v5 = Windows::Management::Setup::UriApplicationLauncher::ValidateSchemeCommandLine(a2, (char *)this + 36, v36);
  v6 = v5;
  v39 = v5;
  if ( v5 >= 0 )
  {
    std::wstring::assign(v40, L"GetSchemeUri");
    v35[0] = 0;
    v35[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v35[0]) = 0;
    SchemeUri = Windows::Management::Setup::UriApplicationLauncher::GetSchemeUri(a2, v4, v35);
    v9 = SchemeUri;
    v39 = SchemeUri;
    if ( SchemeUri >= 0 )
    {
      std::wstring::assign(v40, L"GetActivationFactory RuntimeClass_Windows_Foundation_Uri");
      v30 = 0;
      v38 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Uri",
        0x17u,
        0x16u);
      v10 = v38;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      ActivationFactory = RoGetActivationFactory(v10, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v30);
      v12 = ActivationFactory;
      v39 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        std::wstring::assign(v40, L"CreateUri");
        v31 = 0;
        v13 = v30;
        v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
        v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
        v16 = v14(v13, *(_QWORD *)(v15 + 24), &v31);
        v17 = v16;
        v39 = v16;
        if ( v16 >= 0 )
        {
          std::wstring::assign(v40, L"GetActivationFactory RuntimeClass_Windows_System_Launcher");
          v32 = 0;
          v38 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.System.Launcher",
            0x18u,
            0x17u);
          v18 = v38;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          v19 = RoGetActivationFactory(v18, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v32);
          v20 = v19;
          v39 = v19;
          if ( v19 >= 0 )
          {
            std::wstring::assign(v40, L"LaunchUriAsync");
            v33 = 0;
            v21 = v32;
            v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v32 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            v23 = v22(v21, v31, &v33);
            v24 = v23;
            v39 = v23;
            if ( v23 >= 0 )
            {
              std::wstring::assign(v40, L"WaitForCompletionOrTimeoutNoThrow");
              LOWORD(v29) = 0;
              v25 = v33;
              v28 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(
                      v33,
                      v26,
                      v27,
                      (char *)&v29 + 1);
              if ( v28 >= 0 )
                v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 64LL))(v25, &v29);
              v39 = v28;
              if ( v28 >= 0 )
              {
                if ( (_BYTE)v29 )
                {
                  if ( BYTE1(v29) )
                  {
                    v39 = -2147023436;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xBF,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapp"
                                    "licationlauncher.cpp",
                      (const char *)0x800705B4LL,
                      v29);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                    std::wstring::_Tidy_deallocate(v35);
                    std::wstring::_Tidy_deallocate(v36);
                    Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
                    return 2147943860LL;
                  }
                  else
                  {
                    std::wstring::assign(v40, &sourceString);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                    std::wstring::_Tidy_deallocate(v35);
                    std::wstring::_Tidy_deallocate(v36);
                    Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
                    return 0;
                  }
                }
                else
                {
                  v39 = -2130464759;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xBE,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriappli"
                                  "cationlauncher.cpp",
                    (const char *)0x8103B009LL,
                    v29);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                  std::wstring::_Tidy_deallocate(v35);
                  std::wstring::_Tidy_deallocate(v36);
                  Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
                  return 2164502537LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBD,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplica"
                                "tionlauncher.cpp",
                  (const char *)(unsigned int)v28,
                  v29);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
                std::wstring::_Tidy_deallocate(v35);
                std::wstring::_Tidy_deallocate(v36);
                Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
                return (unsigned int)v28;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB7,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
                (const char *)(unsigned int)v23,
                v29);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
              std::wstring::_Tidy_deallocate(v35);
              std::wstring::_Tidy_deallocate(v36);
              Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
              return v24;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB3,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
              (const char *)(unsigned int)v19,
              v29);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            std::wstring::_Tidy_deallocate(v35);
            std::wstring::_Tidy_deallocate(v36);
            Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
            return v20;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAF,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
            (const char *)(unsigned int)v16,
            v29);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          std::wstring::_Tidy_deallocate(v35);
          std::wstring::_Tidy_deallocate(v36);
          Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
          return v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v36);
        Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
        (const char *)(unsigned int)SchemeUri,
        v29);
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v36);
      Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\initialprovisioning\\uriapplicationlauncher.cpp",
      (const char *)(unsigned int)v5,
      v29);
    std::wstring::_Tidy_deallocate(v36);
    Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger((Windows::Management::Setup::ProvisioningSessionScopedLogger *)&v39);
    return v6;
  }
}

```

## disassembly

```asm
0x180104e30  mov     [rsp+arg_10], rbx
0x180104e35  mov     [rsp+arg_18], rsi
0x180104e3a  push    rdi
0x180104e3b  sub     rsp, 140h
0x180104e42  mov     rax, cs:__security_cookie
0x180104e49  xor     rax, rsp
0x180104e4c  mov     [rsp+148h+var_18], rax
0x180104e54  mov     rsi, rdx
0x180104e57  mov     rbx, rcx
0x180104e5a  lea     rdx, aAttempturische; "AttemptUriSchemeLaunch"
0x180104e61  lea     rcx, [rsp+148h+hstringHeader]
0x180104e69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180104e6e  nop
0x180104e6f  lea     rdi, [rbx+24h]
0x180104e73  lea     r9, [rsp+148h+hstringHeader]
0x180104e7b  mov     r8, rdi
0x180104e7e  mov     rdx, [rbx+38h]
0x180104e82  lea     rcx, [rsp+148h+var_98]; this
0x180104e8a  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x180104e8f  nop
0x180104e90  lea     rcx, [rsp+148h+hstringHeader]
0x180104e98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104e9d  lea     rdx, aValidatescheme; "ValidateSchemeCommandLine"
0x180104ea4  lea     rcx, [rsp+148h+var_90]
0x180104eac  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180104eb1  xorps   xmm0, xmm0
0x180104eb4  movups  [rsp+148h+var_D8], xmm0
0x180104eb9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180104ec1  movdqu  [rsp+148h+var_C8], xmm1
0x180104eca  xor     eax, eax
0x180104ecc  mov     word ptr [rsp+148h+var_D8], ax
0x180104ed1  lea     r8, [rsp+148h+var_D8]
0x180104ed6  mov     rdx, rdi
0x180104ed9  mov     rcx, rsi
0x180104edc  call    ?ValidateSchemeCommandLine@UriApplicationLauncher@Setup@Management@Windows@@SAJPEBGAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::UriApplicationLauncher::ValidateSchemeCommandLine(ushort const *,_GUID const &,std::wstring &)
0x180104ee1  mov     ebx, eax
0x180104ee3  mov     [rsp+148h+var_98], eax
0x180104eea  test    eax, eax
0x180104eec  jns     short loc_180104F2A
0x180104eee  mov     rcx, [rsp+148h]; this
0x180104ef6  mov     r9d, eax; char *
0x180104ef9  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180104f00  mov     edx, 0A3h; void *
0x180104f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104f0a  nop
0x180104f0b  lea     rcx, [rsp+148h+var_D8]
0x180104f10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104f15  nop
0x180104f16  lea     rcx, [rsp+148h+var_98]; this
0x180104f1e  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180104f23  mov     eax, ebx
0x180104f25  jmp     loc_18010554A
0x180104f2a  lea     rdx, aGetschemeuri; "GetSchemeUri"
0x180104f31  lea     rcx, [rsp+148h+var_90]
0x180104f39  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180104f3e  xorps   xmm0, xmm0
0x180104f41  movups  [rsp+148h+var_F8], xmm0
0x180104f46  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180104f4e  movdqu  [rsp+148h+var_E8], xmm1
0x180104f54  xor     eax, eax
0x180104f56  mov     word ptr [rsp+148h+var_F8], ax
0x180104f5b  lea     r8, [rsp+148h+var_F8]
0x180104f60  mov     rdx, rdi
0x180104f63  mov     rcx, rsi
0x180104f66  call    ?GetSchemeUri@UriApplicationLauncher@Setup@Management@Windows@@SAJPEBGAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::UriApplicationLauncher::GetSchemeUri(ushort const *,_GUID const &,std::wstring &)
0x180104f6b  mov     ebx, eax
0x180104f6d  mov     [rsp+148h+var_98], eax
0x180104f74  test    eax, eax
0x180104f76  jns     short loc_180104FBF
0x180104f78  mov     rcx, [rsp+148h]; this
0x180104f80  mov     r9d, eax; char *
0x180104f83  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180104f8a  mov     edx, 0A7h; void *
0x180104f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180104f94  nop
0x180104f95  lea     rcx, [rsp+148h+var_F8]
0x180104f9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104f9f  nop
0x180104fa0  lea     rcx, [rsp+148h+var_D8]
0x180104fa5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180104faa  nop
0x180104fab  lea     rcx, [rsp+148h+var_98]; this
0x180104fb3  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180104fb8  mov     eax, ebx
0x180104fba  jmp     loc_18010554A
0x180104fbf  lea     rdx, aGetactivationf; "GetActivationFactory RuntimeClass_Windo"...
0x180104fc6  lea     rcx, [rsp+148h+var_90]
0x180104fce  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180104fd3  mov     [rsp+148h+var_120], 0
0x180104fdc  mov     [rsp+148h+var_A0], 0
0x180104fe8  mov     esi, 17h
0x180104fed  lea     r9d, [rsi-1]; unsigned int
0x180104ff1  mov     r8d, esi; unsigned int
0x180104ff4  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180104ffb  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180105003  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180105008  mov     rbx, [rsp+148h+var_A0]
0x180105010  lea     rcx, [rsp+148h+var_120]
0x180105015  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010501a  lea     r8, [rsp+148h+var_120]
0x18010501f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180105026  mov     rcx, rbx
0x180105029  call    cs:__imp_RoGetActivationFactory
0x18010502f  mov     ebx, eax
0x180105031  mov     [rsp+148h+var_98], eax
0x180105038  test    eax, eax
0x18010503a  jns     short loc_18010508E
0x18010503c  mov     rcx, [rsp+148h]; this
0x180105044  mov     r9d, eax; char *
0x180105047  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010504e  mov     edx, 0ABh; void *
0x180105053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105058  nop
0x180105059  lea     rcx, [rsp+148h+var_120]
0x18010505e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105063  nop
0x180105064  lea     rcx, [rsp+148h+var_F8]
0x180105069  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010506e  nop
0x18010506f  lea     rcx, [rsp+148h+var_D8]
0x180105074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105079  nop
0x18010507a  lea     rcx, [rsp+148h+var_98]; this
0x180105082  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180105087  mov     eax, ebx
0x180105089  jmp     loc_18010554A
0x18010508e  lea     rdx, aCreateuri; "CreateUri"
0x180105095  lea     rcx, [rsp+148h+var_90]
0x18010509d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801050a2  mov     [rsp+148h+var_118], 0
0x1801050ab  mov     rdi, [rsp+148h+var_120]
0x1801050b0  mov     rax, [rdi]
0x1801050b3  mov     rbx, [rax+30h]
0x1801050b7  lea     rcx, [rsp+148h+var_118]
0x1801050bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801050c1  lea     rcx, [rsp+148h+var_F8]
0x1801050c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801050cb  mov     [rsp+148h+var_100], rax
0x1801050d0  lea     rdx, [rsp+148h+var_100]
0x1801050d5  lea     rcx, [rsp+148h+hstringHeader]
0x1801050dd  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801050e2  nop
0x1801050e3  lea     r8, [rsp+148h+var_118]
0x1801050e8  mov     rdx, [rax+18h]
0x1801050ec  mov     rcx, rdi
0x1801050ef  mov     rax, rbx
0x1801050f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801050f7  mov     ebx, eax
0x1801050f9  mov     [rsp+148h+var_98], eax
0x180105100  test    eax, eax
0x180105102  jns     short loc_180105161
0x180105104  mov     rcx, [rsp+148h]; this
0x18010510c  mov     r9d, eax; char *
0x18010510f  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180105116  mov     edx, 0AFh; void *
0x18010511b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105120  nop
0x180105121  lea     rcx, [rsp+148h+var_118]
0x180105126  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010512b  nop
0x18010512c  lea     rcx, [rsp+148h+var_120]
0x180105131  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105136  nop
0x180105137  lea     rcx, [rsp+148h+var_F8]
0x18010513c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105141  nop
0x180105142  lea     rcx, [rsp+148h+var_D8]
0x180105147  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010514c  nop
0x18010514d  lea     rcx, [rsp+148h+var_98]; this
0x180105155  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x18010515a  mov     eax, ebx
0x18010515c  jmp     loc_18010554A
0x180105161  lea     rdx, aGetactivationf_0; "GetActivationFactory RuntimeClass_Windo"...
0x180105168  lea     rcx, [rsp+148h+var_90]
0x180105170  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180105175  mov     [rsp+148h+var_110], 0
0x18010517e  mov     [rsp+148h+var_A0], 0
0x18010518a  mov     r9d, esi; unsigned int
0x18010518d  mov     r8d, 18h; unsigned int
0x180105193  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18010519a  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1801051a2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801051a7  mov     rbx, [rsp+148h+var_A0]
0x1801051af  lea     rcx, [rsp+148h+var_110]
0x1801051b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801051b9  lea     r8, [rsp+148h+var_110]
0x1801051be  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x1801051c5  mov     rcx, rbx
0x1801051c8  call    cs:__imp_RoGetActivationFactory
0x1801051ce  mov     ebx, eax
0x1801051d0  mov     [rsp+148h+var_98], eax
0x1801051d7  test    eax, eax
0x1801051d9  jns     short loc_180105243
0x1801051db  mov     rcx, [rsp+148h]; this
0x1801051e3  mov     r9d, eax; char *
0x1801051e6  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801051ed  mov     edx, 0B3h; void *
0x1801051f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801051f7  nop
0x1801051f8  lea     rcx, [rsp+148h+var_110]
0x1801051fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105202  nop
0x180105203  lea     rcx, [rsp+148h+var_118]
0x180105208  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010520d  nop
0x18010520e  lea     rcx, [rsp+148h+var_120]
0x180105213  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105218  nop
0x180105219  lea     rcx, [rsp+148h+var_F8]
0x18010521e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180105223  nop
0x180105224  lea     rcx, [rsp+148h+var_D8]
0x180105229  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010522e  nop
0x18010522f  lea     rcx, [rsp+148h+var_98]; this
0x180105237  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x18010523c  mov     eax, ebx
0x18010523e  jmp     loc_18010554A
0x180105243  lea     rdx, aLaunchuriasync; "LaunchUriAsync"
0x18010524a  lea     rcx, [rsp+148h+var_90]
0x180105252  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180105257  mov     [rsp+148h+var_108], 0
0x180105260  mov     rdi, [rsp+148h+var_110]
0x180105265  mov     rax, [rdi]
0x180105268  mov     rbx, [rax+40h]
0x18010526c  lea     rcx, [rsp+148h+var_108]
0x180105271  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105276  lea     r8, [rsp+148h+var_108]
0x18010527b  mov     rdx, [rsp+148h+var_118]
0x180105280  mov     rcx, rdi
0x180105283  mov     rax, rbx
0x180105286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010528b  mov     ebx, eax
0x18010528d  mov     [rsp+148h+var_98], eax
0x180105294  test    eax, eax
0x180105296  jns     short loc_18010530B
0x180105298  mov     rcx, [rsp+148h]; this
0x1801052a0  mov     r9d, eax; char *
0x1801052a3  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801052aa  mov     edx, 0B7h; void *
0x1801052af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801052b4  nop
0x1801052b5  lea     rcx, [rsp+148h+var_108]
0x1801052ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052bf  nop
0x1801052c0  lea     rcx, [rsp+148h+var_110]
0x1801052c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052ca  nop
0x1801052cb  lea     rcx, [rsp+148h+var_118]
0x1801052d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052d5  nop
0x1801052d6  lea     rcx, [rsp+148h+var_120]
0x1801052db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801052e0  nop
0x1801052e1  lea     rcx, [rsp+148h+var_F8]
0x1801052e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801052eb  nop
0x1801052ec  lea     rcx, [rsp+148h+var_D8]
0x1801052f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801052f6  nop
0x1801052f7  lea     rcx, [rsp+148h+var_98]; this
0x1801052ff  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180105304  mov     eax, ebx
0x180105306  jmp     loc_18010554A
0x18010530b  lea     rdx, aWaitforcomplet; "WaitForCompletionOrTimeoutNoThrow"
0x180105312  lea     rcx, [rsp+148h+var_90]
0x18010531a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18010531f  mov     byte ptr [rsp+148h+var_128+1], 0
0x180105324  mov     byte ptr [rsp+148h+var_128], 0; int
0x180105329  mov     rdi, [rsp+148h+var_108]
0x18010532e  lea     r9, [rsp+148h+var_128+1]
0x180105333  mov     rcx, rdi
0x180105336  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18010533b  mov     ebx, eax
0x18010533d  test    eax, eax
0x18010533f  js      short loc_180105357
0x180105341  mov     rax, [rdi]
0x180105344  lea     rdx, [rsp+148h+var_128]
0x180105349  mov     rcx, rdi
0x18010534c  mov     rax, [rax+40h]
0x180105350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105355  mov     ebx, eax
0x180105357  mov     [rsp+148h+var_98], ebx
0x18010535e  test    ebx, ebx
0x180105360  jns     short loc_1801053D5
0x180105362  mov     rcx, [rsp+148h]; this
0x18010536a  mov     r9d, ebx; char *
0x18010536d  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180105374  mov     edx, 0BDh; void *
0x180105379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010537e  nop
0x18010537f  lea     rcx, [rsp+148h+var_108]
0x180105384  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105389  nop
0x18010538a  lea     rcx, [rsp+148h+var_110]
0x18010538f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180105394  nop
0x180105395  lea     rcx, [rsp+148h+var_118]
0x18010539a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
