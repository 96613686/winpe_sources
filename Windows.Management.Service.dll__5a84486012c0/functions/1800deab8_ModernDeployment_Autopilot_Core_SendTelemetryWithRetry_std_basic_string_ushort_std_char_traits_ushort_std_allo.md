# ModernDeployment::Autopilot::Core::SendTelemetryWithRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ulong)

- ea: `0x1800deab8`
- end: `0x1800df14b`
- name: `?SendTelemetryWithRetry@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K@Z`
- size: `1683`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800de934`

## callees

- `0x18000b820`
- `0x180065bac`
- `0x180067a54`
- `0x18006b708`
- `0x18006c694`
- `0x180077384`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x1800814a8`
- `0x1800839bc`
- `0x1800887b8`
- `0x18008a0a8`
- `0x1800a3240`
- `0x1800d961c`
- `0x1800da81c`
- `0x1800dd0d8`
- `0x1800deab8`
- `0x1800df390`
- `0x1800df4d8`
- `0x1800df644`
- `0x1800e2854`
- `0x1800e2924`
- `0x1800e298c`
- `0x1800e3d8c`
- `0x18019bd4c`
- `0x18019bfcc`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800decf0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800decf0`

## string_xrefs

- `0x1800ded11`: `application/json; charset=utf-8`
- `0x1800ded7b`: `X-Device-Token`
- `0x1800deb2b`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800debc1`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800debe2`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800dec59`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800dec98`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800df06a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800df090`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800df0c2`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800df106`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ModernDeployment::Autopilot::Core::SendTelemetryWithRetry(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // r12
  unsigned int v6; // r14d
  int MaxRetryAttempts; // eax
  unsigned int v8; // ebx
  bool v10; // si
  unsigned int v11; // edx
  int v12; // eax
  int HttpNetworkWrapper; // edi
  unsigned int v14; // ebx
  __m128i si128; // xmm6
  unsigned int v16; // ecx
  int DelayForThrottledResponse; // eax
  unsigned int v18; // edi
  int DelayForAttempt; // eax
  unsigned int v20; // edi
  DWORD v21; // edi
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  std::_Ref_count_base *v27; // rdi
  __int64 v28; // rax
  const unsigned __int16 *v29; // rbx
  unsigned int v30; // r12d
  unsigned __int64 v31; // rdx
  unsigned __int8 v32; // cl
  ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging *v33; // rcx
  int v34; // eax
  unsigned int v35; // ebx
  const char *v36; // [rsp+20h] [rbp-168h]
  bool v37; // [rsp+70h] [rbp-118h] BYREF
  DWORD dwMilliseconds; // [rsp+74h] [rbp-114h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-110h]
  unsigned int v40; // [rsp+7Ch] [rbp-10Ch] BYREF
  _BYTE v41[16]; // [rsp+80h] [rbp-108h] BYREF
  _QWORD v42[2]; // [rsp+90h] [rbp-F8h] BYREF
  HANDLE hHandle; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-E0h]
  __int128 v45; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-C8h]
  __int64 v47; // [rsp+C8h] [rbp-C0h]
  std::_Ref_count_base *v48[2]; // [rsp+D0h] [rbp-B8h] BYREF
  _OWORD v49[2]; // [rsp+F0h] [rbp-98h] BYREF
  _BYTE v50[32]; // [rsp+110h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v5 = a1;
  v44 = a1;
  v6 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    v40 = 0;
    MaxRetryAttempts = ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetMaxRetryAttempts(&v40);
    v8 = MaxRetryAttempts;
    if ( MaxRetryAttempts >= 0 )
    {
      v45 = 0;
      v46 = 0;
      v47 = 7;
      LOWORD(v45) = 0;
      if ( (int)ModernDeployment::Autopilot::Core::AcquireMsaDeviceTicket(&v45) < 0 || (v10 = 1, !v46) )
        v10 = 0;
      v37 = 0;
      Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::IsUsingMockHttpNetworkWrapperForTesting(&v37);
      if ( v10 || v37 )
      {
        HttpNetworkWrapper = 0;
        v14 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        while ( v6 <= v40 )
        {
          if ( v6 )
          {
            dwMilliseconds = 0;
            v16 = v6 - 1;
            if ( v14 == 429 )
            {
              DelayForThrottledResponse = ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForThrottledResponse(
                                            v16,
                                            v11,
                                            &dwMilliseconds);
              v18 = DelayForThrottledResponse;
              if ( DelayForThrottledResponse < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1D8,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)DelayForThrottledResponse,
                  (int)v36);
                std::wstring::_Tidy_deallocate(&v45);
                return v18;
              }
            }
            else
            {
              DelayForAttempt = ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForAttempt(
                                  v16,
                                  &dwMilliseconds);
              v20 = DelayForAttempt;
              if ( DelayForAttempt < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1DC,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
                  (const char *)(unsigned int)DelayForAttempt,
                  (int)v36);
                std::wstring::_Tidy_deallocate(&v45);
                return v20;
              }
            }
            v21 = dwMilliseconds;
            if ( dwMilliseconds )
            {
              dwMilliseconds = 1;
              ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
                &hHandle,
                &dwMilliseconds);
              WaitForSingleObjectEx(hHandle, v21, 1);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
            }
          }
          std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v41);
          v22 = std::wstring::wstring(v50, L"application/json; charset=utf-8");
          v23 = std::wstring::wstring(v48, L"Content-Type");
          v24 = std::map<std::wstring,std::wstring>::operator[](v41, v23);
          std::wstring::operator=(v24, v22);
          std::wstring::_Tidy_deallocate(v48);
          std::wstring::_Tidy_deallocate(v50);
          if ( v10 )
          {
            v25 = std::wstring::wstring(v50, L"X-Device-Token");
            v26 = std::map<std::wstring,std::wstring>::operator[](v41, v25);
            std::wstring::operator=(v26, &v45);
            std::wstring::_Tidy_deallocate(v50);
          }
          v42[0] = 0;
          v42[1] = 0;
          v39 = 0;
          *(_OWORD *)v48 = 0;
          HttpNetworkWrapper = Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::CreateHttpNetworkWrapper(v48);
          if ( HttpNetworkWrapper >= 0 )
          {
            v49[0] = 0;
            v49[1] = si128;
            LOWORD(v49[0]) = 0;
            v27 = v48[0];
            std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
            v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
            v36 = L"HTTP/1.1";
            HttpNetworkWrapper = (*(__int64 (__fastcall **)(std::_Ref_count_base *, const wchar_t *, __int64, __int64))(*(_QWORD *)v27 + 8LL))(
                                   v27,
                                   L"FWTClient",
                                   v28,
                                   1);
            v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
            v30 = *(_DWORD *)(a2 + 16);
            if ( ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(v32, v31) )
            {
              wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get();
              ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::UploadTelemetryResponse_(
                v33,
                v39,
                v30,
                v29);
            }
            v14 = v39;
            if ( HttpNetworkWrapper >= 0 && v39 == 200 )
            {
              std::wstring::_Tidy_deallocate(v49);
              if ( v48[1] )
                std::_Ref_count_base::_Decref(v48[1]);
              wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v42);
              std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                v41,
                v41);
              std::wstring::_Tidy_deallocate(&v45);
              return 0;
            }
            if ( v39
              && v39 != 408
              && v39 != 429
              && v39 != 449
              && v39 != 500
              && v39 != 501
              && v39 != 502
              && v39 - 503 >= 2 )
            {
              if ( v39 != 401 )
              {
                std::wstring::_Tidy_deallocate(v49);
                if ( v48[1] )
                  std::_Ref_count_base::_Decref(v48[1]);
                wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v42);
                std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
                  v41,
                  v41);
                break;
              }
              v10 = (int)ModernDeployment::Autopilot::Core::AcquireMsaDeviceTicket(&v45) >= 0 && v46;
            }
            std::wstring::_Tidy_deallocate(v49);
            if ( v48[1] )
              std::_Ref_count_base::_Decref(v48[1]);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v42);
            v5 = v44;
          }
          else
          {
            if ( v48[1] )
              std::_Ref_count_base::_Decref(v48[1]);
            wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(v42);
          }
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v41,
            v41);
          ++v6;
        }
        v34 = ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(a3, a2);
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x225,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
            (const char *)(unsigned int)v34,
            (int)v36);
        if ( v14 )
        {
          v35 = v14 | 0x80190000;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x229,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
            (const char *)v35,
            (int)v36);
          std::wstring::_Tidy_deallocate(&v45);
          return v35;
        }
        else if ( HttpNetworkWrapper >= 0 )
        {
          std::wstring::_Tidy_deallocate(&v45);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22C,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
            (const char *)(unsigned int)HttpNetworkWrapper,
            (int)v36);
          std::wstring::_Tidy_deallocate(&v45);
          return (unsigned int)HttpNetworkWrapper;
        }
      }
      else
      {
        v12 = ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(a3, a2);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1CB,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
            (const char *)(unsigned int)v12,
            (int)v36);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
          (const char *)0x80070005LL,
          (int)v36);
        std::wstring::_Tidy_deallocate(&v45);
        return 2147942405LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
        (const char *)(unsigned int)MaxRetryAttempts,
        (int)v36);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fastwindowstelemetry.cpp",
      (const char *)0x80004001LL,
      (int)v36);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800deab8  mov     rax, rsp
0x1800deabb  push    rbx
0x1800deabc  push    rsi
0x1800deabd  push    rdi
0x1800deabe  push    r12
0x1800deac0  push    r13
0x1800deac2  push    r14
0x1800deac4  push    r15
0x1800deac6  sub     rsp, 150h
0x1800deacd  movaps  xmmword ptr [rax-48h], xmm6
0x1800dead1  mov     rax, cs:__security_cookie
0x1800dead8  xor     rax, rsp
0x1800deadb  mov     [rsp+188h+var_58], rax
0x1800deae3  mov     r13d, r8d
0x1800deae6  mov     r15, rdx
0x1800deae9  mov     r12, rcx
0x1800deaec  mov     [rsp+188h+var_E0], rcx
0x1800deaf4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800deafb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800deb00  xor     r14d, r14d
0x1800deb03  test    al, al
0x1800deb05  jz      loc_1800DF0F6
0x1800deb0b  mov     [rsp+188h+var_10C], r14d
0x1800deb10  lea     rcx, [rsp+188h+var_10C]; unsigned int *
0x1800deb15  call    ?GetMaxRetryAttempts@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetMaxRetryAttempts(ulong &)
0x1800deb1a  mov     ebx, eax
0x1800deb1c  test    eax, eax
0x1800deb1e  jns     short loc_1800DEB43
0x1800deb20  mov     rcx, [rsp+188h]; this
0x1800deb28  mov     r9d, eax; char *
0x1800deb2b  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800deb32  mov     edx, 1BAh; void *
0x1800deb37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800deb3c  mov     eax, ebx
0x1800deb3e  jmp     loc_1800DF11F
0x1800deb43  xorps   xmm0, xmm0
0x1800deb46  movups  [rsp+188h+var_D8], xmm0
0x1800deb4e  mov     [rsp+188h+var_C8], r14
0x1800deb56  mov     [rsp+188h+var_C0], 7
0x1800deb62  mov     word ptr [rsp+188h+var_D8], r14w
0x1800deb6b  lea     rcx, [rsp+188h+var_D8]
0x1800deb73  call    ModernDeployment__Autopilot__Core__AcquireMsaDeviceTicket
0x1800deb78  test    eax, eax
0x1800deb7a  js      short loc_1800DEB89
0x1800deb7c  cmp     [rsp+188h+var_C8], r14
0x1800deb84  mov     sil, 1
0x1800deb87  jnz     short loc_1800DEB8C
0x1800deb89  mov     sil, r14b
0x1800deb8c  mov     [rsp+188h+var_118], r14b
0x1800deb91  lea     rcx, [rsp+188h+var_118]; bool *
0x1800deb96  call    ?IsUsingMockHttpNetworkWrapperForTesting@HttpNetworkWrapperFactory@Autopilot@Windows@Microsoft@@SAJAEA_N@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::IsUsingMockHttpNetworkWrapperForTesting(bool &)
0x1800deb9b  test    sil, sil
0x1800deb9e  jnz     short loc_1800DEC08
0x1800deba0  cmp     [rsp+188h+var_118], r14b
0x1800deba5  jnz     short loc_1800DEC08
0x1800deba7  mov     rdx, r15
0x1800debaa  mov     ecx, r13d
0x1800debad  call    ?Enqueue@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(ulong,std::string const &)
0x1800debb2  mov     rcx, [rsp+188h]; this
0x1800debba  test    eax, eax
0x1800debbc  jns     short loc_1800DEBD2
0x1800debbe  mov     r9d, eax; char *
0x1800debc1  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800debc8  mov     edx, 1CBh; void *
0x1800debcd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800debd2  mov     rcx, [rsp+188h]; this
0x1800debda  mov     ebx, 80070005h
0x1800debdf  mov     r9d, ebx; char *
0x1800debe2  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800debe9  mov     edx, 1CCh; void *
0x1800debee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800debf3  nop
0x1800debf4  lea     rcx, [rsp+188h+var_D8]
0x1800debfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dec01  mov     eax, ebx
0x1800dec03  jmp     loc_1800DF11F
0x1800dec08  mov     edi, r14d
0x1800dec0b  mov     ebx, r14d
0x1800dec0e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800dec16  cmp     r14d, [rsp+188h+var_10C]
0x1800dec1b  ja      loc_1800DF050
0x1800dec21  test    r14d, r14d
0x1800dec24  jz      loc_1800DED03
0x1800dec2a  mov     [rsp+188h+dwMilliseconds], 0
0x1800dec32  lea     ecx, [r14-1]; unsigned int
0x1800dec36  cmp     ebx, 1ADh
0x1800dec3c  jnz     short loc_1800DEC7D
0x1800dec3e  lea     r8, [rsp+188h+dwMilliseconds]; unsigned int *
0x1800dec43  call    ?GetDelayForThrottledResponse@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJKKAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForThrottledResponse(ulong,ulong,ulong &)
0x1800dec48  mov     edi, eax
0x1800dec4a  test    eax, eax
0x1800dec4c  jns     short loc_1800DECBE
0x1800dec4e  mov     rcx, [rsp+188h]; this
0x1800dec56  mov     r9d, eax; char *
0x1800dec59  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dec60  lea     edx, [rbx+2Bh]; void *
0x1800dec63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dec68  nop
0x1800dec69  lea     rcx, [rsp+188h+var_D8]
0x1800dec71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dec76  mov     eax, edi
0x1800dec78  jmp     loc_1800DF11F
0x1800dec7d  lea     rdx, [rsp+188h+dwMilliseconds]; unsigned int *
0x1800dec82  call    ?GetDelayForAttempt@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJKAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForAttempt(ulong,ulong &)
0x1800dec87  mov     edi, eax
0x1800dec89  test    eax, eax
0x1800dec8b  jns     short loc_1800DECBE
0x1800dec8d  mov     rcx, [rsp+188h]; this
0x1800dec95  mov     r9d, eax; char *
0x1800dec98  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800dec9f  mov     edx, 1DCh; void *
0x1800deca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800deca9  nop
0x1800decaa  lea     rcx, [rsp+188h+var_D8]
0x1800decb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800decb7  mov     eax, edi
0x1800decb9  jmp     loc_1800DF11F
0x1800decbe  mov     edi, [rsp+188h+dwMilliseconds]
0x1800decc2  test    edi, edi
0x1800decc4  jz      short loc_1800DED03
0x1800decc6  mov     [rsp+188h+dwMilliseconds], 1
0x1800decce  lea     rdx, [rsp+188h+dwMilliseconds]
0x1800decd3  lea     rcx, [rsp+188h+hHandle]
0x1800decdb  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800dece0  mov     r8d, 1; bAlertable
0x1800dece6  mov     edx, edi; dwMilliseconds
0x1800dece8  mov     rcx, [rsp+188h+hHandle]; hHandle
0x1800decf0  call    cs:__imp_WaitForSingleObjectEx
0x1800decf6  lea     rcx, [rsp+188h+hHandle]
0x1800decfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ded03  lea     rcx, [rsp+188h+var_108]
0x1800ded0b  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800ded10  nop
0x1800ded11  lea     rdx, aApplicationJso_0; "application/json; charset=utf-8"
0x1800ded18  lea     rcx, [rsp+188h+var_78]
0x1800ded20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ded25  mov     rdi, rax
0x1800ded28  lea     rdx, aContentType; "Content-Type"
0x1800ded2f  lea     rcx, [rsp+188h+var_B8]
0x1800ded37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ded3c  nop
0x1800ded3d  mov     rdx, rax
0x1800ded40  lea     rcx, [rsp+188h+var_108]
0x1800ded48  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800ded4d  mov     rdx, rdi
0x1800ded50  mov     rcx, rax
0x1800ded53  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800ded58  nop
0x1800ded59  lea     rcx, [rsp+188h+var_B8]
0x1800ded61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ded66  nop
0x1800ded67  lea     rcx, [rsp+188h+var_78]
0x1800ded6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ded74  xor     edi, edi
0x1800ded76  test    sil, sil
0x1800ded79  jz      short loc_1800DEDBE
0x1800ded7b  lea     rdx, aXDeviceToken; "X-Device-Token"
0x1800ded82  lea     rcx, [rsp+188h+var_78]
0x1800ded8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ded8f  nop
0x1800ded90  mov     rdx, rax
0x1800ded93  lea     rcx, [rsp+188h+var_108]
0x1800ded9b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800deda0  lea     rdx, [rsp+188h+var_D8]
0x1800deda8  mov     rcx, rax
0x1800dedab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dedb0  nop
0x1800dedb1  lea     rcx, [rsp+188h+var_78]
0x1800dedb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dedbe  mov     [rsp+188h+var_F8], rdi
0x1800dedc6  mov     [rsp+188h+var_F0], rdi
0x1800dedce  mov     [rsp+188h+var_110], edi
0x1800dedd2  xorps   xmm0, xmm0
0x1800dedd5  movdqu  xmmword ptr [rsp+188h+var_B8], xmm0
0x1800dedde  lea     rcx, [rsp+188h+var_B8]
0x1800dede6  call    ?CreateHttpNetworkWrapper@HttpNetworkWrapperFactory@Autopilot@Windows@Microsoft@@SAJAEAV?$shared_ptr@UIHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::CreateHttpNetworkWrapper(std::shared_ptr<Microsoft::Windows::Autopilot::IHttpNetworkWrapper> &)
0x1800dedeb  mov     edi, eax
0x1800deded  test    eax, eax
0x1800dedef  jns     short loc_1800DEE17
0x1800dedf1  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800dedf9  test    rcx, rcx
0x1800dedfc  jz      short loc_1800DEE04
0x1800dedfe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800dee03  nop
0x1800dee04  lea     rcx, [rsp+188h+var_F8]
0x1800dee0c  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800dee11  nop
0x1800dee12  jmp     loc_1800DEFEA
0x1800dee17  xorps   xmm0, xmm0
0x1800dee1a  movups  [rsp+188h+var_98], xmm0
0x1800dee22  movdqu  [rsp+188h+var_88], xmm6
0x1800dee2b  xor     eax, eax
0x1800dee2d  mov     word ptr [rsp+188h+var_98], ax
0x1800dee35  mov     rdi, [rsp+188h+var_B8]
0x1800dee3d  mov     rcx, r15
0x1800dee40  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800dee45  mov     rbx, rax
0x1800dee48  mov     rcx, r12
0x1800dee4b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dee50  mov     rcx, [rdi]
0x1800dee53  mov     r10, [rcx+8]
0x1800dee57  lea     rcx, [rsp+188h+var_F8]
0x1800dee5f  mov     [rsp+188h+var_130], rcx
0x1800dee64  lea     rcx, [rsp+188h+var_98]
0x1800dee6c  mov     [rsp+188h+var_138], rcx
0x1800dee71  lea     rcx, [rsp+188h+var_110]
0x1800dee76  mov     [rsp+188h+var_140], rcx
0x1800dee7b  mov     edx, [r15+10h]
0x1800dee7f  mov     [rsp+188h+var_148], edx
0x1800dee83  mov     [rsp+188h+var_150], rbx
0x1800dee88  lea     rcx, [rsp+188h+var_108]
0x1800dee90  mov     [rsp+188h+var_158], rcx
0x1800dee95  mov     [rsp+188h+var_160], 0
0x1800dee9e  lea     rcx, aHttp11; "HTTP/1.1"
0x1800deea5  mov     qword ptr [rsp+188h+var_168], rcx; int
0x1800deeaa  mov     r9d, 1
0x1800deeb0  mov     r8, rax
0x1800deeb3  lea     rdx, aFwtclient; "FWTClient"
0x1800deeba  mov     rcx, rdi
0x1800deebd  mov     rax, r10
0x1800deec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deec5  mov     edi, eax
0x1800deec7  mov     rcx, r12
0x1800deeca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800deecf  mov     rbx, rax
0x1800deed2  mov     r12d, [r15+10h]
0x1800deed6  call    ?IsEnabled@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@SA_NE_K@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(uchar,unsigned __int64)
0x1800deedb  test    al, al
0x1800deedd  jz      short loc_1800DEEF3
0x1800deedf  call    ?get@?$static_lazy@VFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@@details@wil@@QEAAPEAVFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@P6AXXZ@Z; wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get(void (*)(void))
0x1800deee4  mov     r9, rbx; unsigned __int16 *
0x1800deee7  mov     r8d, r12d; unsigned int
0x1800deeea  mov     edx, [rsp+188h+var_110]; unsigned int
0x1800deeee  call    ?UploadTelemetryResponse_@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@QEAAXKIPEBG@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::UploadTelemetryResponse_(ulong,uint,ushort const *)
0x1800deef3  mov     ebx, [rsp+188h+var_110]
0x1800deef7  test    edi, edi
0x1800deef9  js      short loc_1800DEF5C
0x1800deefb  cmp     ebx, 0C8h
0x1800def01  jnz     short loc_1800DEF5C
0x1800def03  lea     rcx, [rsp+188h+var_98]
0x1800def0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def10  nop
0x1800def11  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800def19  test    rcx, rcx
0x1800def1c  jz      short loc_1800DEF24
0x1800def1e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800def23  nop
0x1800def24  lea     rcx, [rsp+188h+var_F8]
0x1800def2c  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800def31  nop
0x1800def32  lea     rdx, [rsp+188h+var_108]
0x1800def3a  lea     rcx, [rsp+188h+var_108]
0x1800def42  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800def47  nop
0x1800def48  lea     rcx, [rsp+188h+var_D8]
0x1800def50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800def55  xor     eax, eax
0x1800def57  jmp     loc_1800DF11F
0x1800def5c  test    ebx, ebx
0x1800def5e  jz      short loc_1800DEFB3
0x1800def60  mov     eax, ebx
0x1800def62  sub     eax, 198h
0x1800def67  jz      short loc_1800DEFB3
0x1800def69  sub     eax, 15h
0x1800def6c  jz      short loc_1800DEFB3
0x1800def6e  sub     eax, 14h
0x1800def71  jz      short loc_1800DEFB3
0x1800def73  sub     eax, 33h ; '3'
0x1800def76  jz      short loc_1800DEFB3
0x1800def78  sub     eax, 1
0x1800def7b  jz      short loc_1800DEFB3
0x1800def7d  sub     eax, 1
0x1800def80  jz      short loc_1800DEFB3
0x1800def82  sub     eax, 1
0x1800def85  jz      short loc_1800DEFB3
0x1800def87  cmp     eax, 1
0x1800def8a  jz      short loc_1800DEFB3
0x1800def8c  cmp     ebx, 191h
0x1800def92  jnz     short loc_1800DF00C
0x1800def94  lea     rcx, [rsp+188h+var_D8]
0x1800def9c  call    ModernDeployment__Autopilot__Core__AcquireMsaDeviceTicket
0x1800defa1  test    eax, eax
0x1800defa3  js      short loc_1800DF007
0x1800defa5  cmp     [rsp+188h+var_C8], 0
0x1800defae  jz      short loc_1800DF007
0x1800defb0  mov     sil, 1
0x1800defb3  lea     rcx, [rsp+188h+var_98]
0x1800defbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800defc0  nop
0x1800defc1  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800defc9  test    rcx, rcx
0x1800defcc  jz      short loc_1800DEFD4
0x1800defce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800defd3  nop
0x1800defd4  lea     rcx, [rsp+188h+var_F8]
0x1800defdc  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800defe1  nop
0x1800defe2  mov     r12, [rsp+188h+var_E0]
0x1800defea  lea     rdx, [rsp+188h+var_108]
0x1800deff2  lea     rcx, [rsp+188h+var_108]
  ... truncated ...
```
