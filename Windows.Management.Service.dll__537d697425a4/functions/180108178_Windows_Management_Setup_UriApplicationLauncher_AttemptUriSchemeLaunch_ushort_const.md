# Windows::Management::Setup::UriApplicationLauncher::AttemptUriSchemeLaunch(ushort const *)

- ea: `0x180108178`
- end: `0x1801088c4`
- name: `?AttemptUriSchemeLaunch@UriApplicationLauncher@Setup@Management@Windows@@QEAAJPEBG@Z`
- size: `1868`
- prototype: `__int64 __fastcall(Windows::Management::Setup::UriApplicationLauncher *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180108db0`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x1800829ec`
- `0x180084574`
- `0x180086044`
- `0x18008d290`
- `0x1801031ec`
- `0x1801033d4`
- `0x180107e6c`
- `0x180108178`
- `0x180108c60`
- `0x180109190`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180108371`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180108516`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180108371`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180108516`

## string_xrefs

- `0x18010833c`: `Windows.Foundation.Uri`
- `0x180108241`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801082cb`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180108395`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x18010845d`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x18010853a`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801085f7`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801086c1`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180108747`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x1801087cd`: `onecoreuap\admin\moderndeployment\autopilot\service\initialprovisioning\uriapplicationlauncher.cpp`
- `0x180108597`: `LaunchUriAsync`
- `0x18010865f`: `WaitForCompletionOrTimeoutNoThrow`
- `0x1801083dc`: `CreateUri`
- `0x180108272`: `GetSchemeUri`
- `0x180108307`: `GetActivationFactory RuntimeClass_Windows_Foundation_Uri`
- `0x1801081a2`: `AttemptUriSchemeLaunch`
- `0x1801081e5`: `ValidateSchemeCommandLine`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
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
0x180108178  mov     [rsp+arg_10], rbx
0x18010817d  mov     [rsp+arg_18], rsi
0x180108182  push    rdi
0x180108183  sub     rsp, 140h
0x18010818a  mov     rax, cs:__security_cookie
0x180108191  xor     rax, rsp
0x180108194  mov     [rsp+148h+var_18], rax
0x18010819c  mov     rsi, rdx
0x18010819f  mov     rbx, rcx
0x1801081a2  lea     rdx, aAttempturische; "AttemptUriSchemeLaunch"
0x1801081a9  lea     rcx, [rsp+148h+hstringHeader]
0x1801081b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801081b6  nop
0x1801081b7  lea     rdi, [rbx+24h]
0x1801081bb  lea     r9, [rsp+148h+hstringHeader]
0x1801081c3  mov     r8, rdi
0x1801081c6  mov     rdx, [rbx+38h]
0x1801081ca  lea     rcx, [rsp+148h+var_98]; this
0x1801081d2  call    ??0ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@PEAUIProvisioningSessionLogger@123@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::ProvisioningSessionScopedLogger::ProvisioningSessionScopedLogger(Windows::Management::Setup::IProvisioningSessionLogger *,_GUID const &,std::wstring const &)
0x1801081d7  nop
0x1801081d8  lea     rcx, [rsp+148h+hstringHeader]
0x1801081e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801081e5  lea     rdx, aValidatescheme; "ValidateSchemeCommandLine"
0x1801081ec  lea     rcx, [rsp+148h+var_90]
0x1801081f4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801081f9  xorps   xmm0, xmm0
0x1801081fc  movups  [rsp+148h+var_D8], xmm0
0x180108201  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180108209  movdqu  [rsp+148h+var_C8], xmm1
0x180108212  xor     eax, eax
0x180108214  mov     word ptr [rsp+148h+var_D8], ax
0x180108219  lea     r8, [rsp+148h+var_D8]
0x18010821e  mov     rdx, rdi
0x180108221  mov     rcx, rsi
0x180108224  call    ?ValidateSchemeCommandLine@UriApplicationLauncher@Setup@Management@Windows@@SAJPEBGAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::UriApplicationLauncher::ValidateSchemeCommandLine(ushort const *,_GUID const &,std::wstring &)
0x180108229  mov     ebx, eax
0x18010822b  mov     [rsp+148h+var_98], eax
0x180108232  test    eax, eax
0x180108234  jns     short loc_180108272
0x180108236  mov     rcx, [rsp+148h]; this
0x18010823e  mov     r9d, eax; char *
0x180108241  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180108248  mov     edx, 0A3h; void *
0x18010824d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108252  nop
0x180108253  lea     rcx, [rsp+148h+var_D8]
0x180108258  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010825d  nop
0x18010825e  lea     rcx, [rsp+148h+var_98]; this
0x180108266  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x18010826b  mov     eax, ebx
0x18010826d  jmp     loc_18010889E
0x180108272  lea     rdx, aGetschemeuri; "GetSchemeUri"
0x180108279  lea     rcx, [rsp+148h+var_90]
0x180108281  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180108286  xorps   xmm0, xmm0
0x180108289  movups  [rsp+148h+var_F8], xmm0
0x18010828e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180108296  movdqu  [rsp+148h+var_E8], xmm1
0x18010829c  xor     eax, eax
0x18010829e  mov     word ptr [rsp+148h+var_F8], ax
0x1801082a3  lea     r8, [rsp+148h+var_F8]
0x1801082a8  mov     rdx, rdi
0x1801082ab  mov     rcx, rsi
0x1801082ae  call    ?GetSchemeUri@UriApplicationLauncher@Setup@Management@Windows@@SAJPEBGAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Management::Setup::UriApplicationLauncher::GetSchemeUri(ushort const *,_GUID const &,std::wstring &)
0x1801082b3  mov     ebx, eax
0x1801082b5  mov     [rsp+148h+var_98], eax
0x1801082bc  test    eax, eax
0x1801082be  jns     short loc_180108307
0x1801082c0  mov     rcx, [rsp+148h]; this
0x1801082c8  mov     r9d, eax; char *
0x1801082cb  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801082d2  mov     edx, 0A7h; void *
0x1801082d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801082dc  nop
0x1801082dd  lea     rcx, [rsp+148h+var_F8]
0x1801082e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801082e7  nop
0x1801082e8  lea     rcx, [rsp+148h+var_D8]
0x1801082ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801082f2  nop
0x1801082f3  lea     rcx, [rsp+148h+var_98]; this
0x1801082fb  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180108300  mov     eax, ebx
0x180108302  jmp     loc_18010889E
0x180108307  lea     rdx, aGetactivationf; "GetActivationFactory RuntimeClass_Windo"...
0x18010830e  lea     rcx, [rsp+148h+var_90]
0x180108316  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18010831b  mov     [rsp+148h+var_120], 0
0x180108324  mov     [rsp+148h+var_A0], 0
0x180108330  mov     esi, 17h
0x180108335  lea     r9d, [rsi-1]; unsigned int
0x180108339  mov     r8d, esi; unsigned int
0x18010833c  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180108343  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x18010834b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180108350  mov     rbx, [rsp+148h+var_A0]
0x180108358  lea     rcx, [rsp+148h+var_120]
0x18010835d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108362  lea     r8, [rsp+148h+var_120]
0x180108367  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18010836e  mov     rcx, rbx
0x180108371  call    cs:__imp_RoGetActivationFactory
0x180108378  nop     dword ptr [rax+rax+00h]
0x18010837d  mov     ebx, eax
0x18010837f  mov     [rsp+148h+var_98], eax
0x180108386  test    eax, eax
0x180108388  jns     short loc_1801083DC
0x18010838a  mov     rcx, [rsp+148h]; this
0x180108392  mov     r9d, eax; char *
0x180108395  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x18010839c  mov     edx, 0ABh; void *
0x1801083a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801083a6  nop
0x1801083a7  lea     rcx, [rsp+148h+var_120]
0x1801083ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801083b1  nop
0x1801083b2  lea     rcx, [rsp+148h+var_F8]
0x1801083b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801083bc  nop
0x1801083bd  lea     rcx, [rsp+148h+var_D8]
0x1801083c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801083c7  nop
0x1801083c8  lea     rcx, [rsp+148h+var_98]; this
0x1801083d0  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1801083d5  mov     eax, ebx
0x1801083d7  jmp     loc_18010889E
0x1801083dc  lea     rdx, aCreateuri; "CreateUri"
0x1801083e3  lea     rcx, [rsp+148h+var_90]
0x1801083eb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801083f0  mov     [rsp+148h+var_118], 0
0x1801083f9  mov     rdi, [rsp+148h+var_120]
0x1801083fe  mov     rax, [rdi]
0x180108401  mov     rbx, [rax+30h]
0x180108405  lea     rcx, [rsp+148h+var_118]
0x18010840a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010840f  lea     rcx, [rsp+148h+var_F8]
0x180108414  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180108419  mov     [rsp+148h+var_100], rax
0x18010841e  lea     rdx, [rsp+148h+var_100]
0x180108423  lea     rcx, [rsp+148h+hstringHeader]
0x18010842b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180108430  nop
0x180108431  lea     r8, [rsp+148h+var_118]
0x180108436  mov     rdx, [rax+18h]
0x18010843a  mov     rcx, rdi
0x18010843d  mov     rax, rbx
0x180108440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108445  mov     ebx, eax
0x180108447  mov     [rsp+148h+var_98], eax
0x18010844e  test    eax, eax
0x180108450  jns     short loc_1801084AF
0x180108452  mov     rcx, [rsp+148h]; this
0x18010845a  mov     r9d, eax; char *
0x18010845d  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180108464  mov     edx, 0AFh; void *
0x180108469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010846e  nop
0x18010846f  lea     rcx, [rsp+148h+var_118]
0x180108474  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108479  nop
0x18010847a  lea     rcx, [rsp+148h+var_120]
0x18010847f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108484  nop
0x180108485  lea     rcx, [rsp+148h+var_F8]
0x18010848a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010848f  nop
0x180108490  lea     rcx, [rsp+148h+var_D8]
0x180108495  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010849a  nop
0x18010849b  lea     rcx, [rsp+148h+var_98]; this
0x1801084a3  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x1801084a8  mov     eax, ebx
0x1801084aa  jmp     loc_18010889E
0x1801084af  lea     rdx, aGetactivationf_0; "GetActivationFactory RuntimeClass_Windo"...
0x1801084b6  lea     rcx, [rsp+148h+var_90]
0x1801084be  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801084c3  mov     [rsp+148h+var_110], 0
0x1801084cc  mov     [rsp+148h+var_A0], 0
0x1801084d8  mov     r9d, esi; unsigned int
0x1801084db  mov     r8d, 18h; unsigned int
0x1801084e1  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x1801084e8  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1801084f0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801084f5  mov     rbx, [rsp+148h+var_A0]
0x1801084fd  lea     rcx, [rsp+148h+var_110]
0x180108502  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108507  lea     r8, [rsp+148h+var_110]
0x18010850c  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x180108513  mov     rcx, rbx
0x180108516  call    cs:__imp_RoGetActivationFactory
0x18010851d  nop     dword ptr [rax+rax+00h]
0x180108522  mov     ebx, eax
0x180108524  mov     [rsp+148h+var_98], eax
0x18010852b  test    eax, eax
0x18010852d  jns     short loc_180108597
0x18010852f  mov     rcx, [rsp+148h]; this
0x180108537  mov     r9d, eax; char *
0x18010853a  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x180108541  mov     edx, 0B3h; void *
0x180108546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010854b  nop
0x18010854c  lea     rcx, [rsp+148h+var_110]
0x180108551  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108556  nop
0x180108557  lea     rcx, [rsp+148h+var_118]
0x18010855c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108561  nop
0x180108562  lea     rcx, [rsp+148h+var_120]
0x180108567  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010856c  nop
0x18010856d  lea     rcx, [rsp+148h+var_F8]
0x180108572  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108577  nop
0x180108578  lea     rcx, [rsp+148h+var_D8]
0x18010857d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108582  nop
0x180108583  lea     rcx, [rsp+148h+var_98]; this
0x18010858b  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180108590  mov     eax, ebx
0x180108592  jmp     loc_18010889E
0x180108597  lea     rdx, aLaunchuriasync; "LaunchUriAsync"
0x18010859e  lea     rcx, [rsp+148h+var_90]
0x1801085a6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801085ab  mov     [rsp+148h+var_108], 0
0x1801085b4  mov     rdi, [rsp+148h+var_110]
0x1801085b9  mov     rax, [rdi]
0x1801085bc  mov     rbx, [rax+40h]
0x1801085c0  lea     rcx, [rsp+148h+var_108]
0x1801085c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801085ca  lea     r8, [rsp+148h+var_108]
0x1801085cf  mov     rdx, [rsp+148h+var_118]
0x1801085d4  mov     rcx, rdi
0x1801085d7  mov     rax, rbx
0x1801085da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801085df  mov     ebx, eax
0x1801085e1  mov     [rsp+148h+var_98], eax
0x1801085e8  test    eax, eax
0x1801085ea  jns     short loc_18010865F
0x1801085ec  mov     rcx, [rsp+148h]; this
0x1801085f4  mov     r9d, eax; char *
0x1801085f7  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801085fe  mov     edx, 0B7h; void *
0x180108603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108608  nop
0x180108609  lea     rcx, [rsp+148h+var_108]
0x18010860e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108613  nop
0x180108614  lea     rcx, [rsp+148h+var_110]
0x180108619  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010861e  nop
0x18010861f  lea     rcx, [rsp+148h+var_118]
0x180108624  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108629  nop
0x18010862a  lea     rcx, [rsp+148h+var_120]
0x18010862f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180108634  nop
0x180108635  lea     rcx, [rsp+148h+var_F8]
0x18010863a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010863f  nop
0x180108640  lea     rcx, [rsp+148h+var_D8]
0x180108645  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010864a  nop
0x18010864b  lea     rcx, [rsp+148h+var_98]; this
0x180108653  call    ??1ProvisioningSessionScopedLogger@Setup@Management@Windows@@QEAA@XZ; Windows::Management::Setup::ProvisioningSessionScopedLogger::~ProvisioningSessionScopedLogger(void)
0x180108658  mov     eax, ebx
0x18010865a  jmp     loc_18010889E
0x18010865f  lea     rdx, aWaitforcomplet; "WaitForCompletionOrTimeoutNoThrow"
0x180108666  lea     rcx, [rsp+148h+var_90]
0x18010866e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180108673  mov     byte ptr [rsp+148h+var_128+1], 0
0x180108678  mov     byte ptr [rsp+148h+var_128], 0; int
0x18010867d  mov     rdi, [rsp+148h+var_108]
0x180108682  lea     r9, [rsp+148h+var_128+1]
0x180108687  mov     rcx, rdi
0x18010868a  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18010868f  mov     ebx, eax
0x180108691  test    eax, eax
0x180108693  js      short loc_1801086AB
0x180108695  mov     rax, [rdi]
0x180108698  lea     rdx, [rsp+148h+var_128]
0x18010869d  mov     rcx, rdi
0x1801086a0  mov     rax, [rax+40h]
0x1801086a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801086a9  mov     ebx, eax
0x1801086ab  mov     [rsp+148h+var_98], ebx
0x1801086b2  test    ebx, ebx
0x1801086b4  jns     short loc_180108729
0x1801086b6  mov     rcx, [rsp+148h]; this
0x1801086be  mov     r9d, ebx; char *
0x1801086c1  lea     r8, aOnecoreuapAdmi_105; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801086c8  mov     edx, 0BDh; void *
0x1801086cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801086d2  nop
0x1801086d3  lea     rcx, [rsp+148h+var_108]
0x1801086d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801086dd  nop
0x1801086de  lea     rcx, [rsp+148h+var_110]
0x1801086e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801086e8  nop
  ... truncated ...
```
