# ModernDeployment::Autopilot::Core::SendTelemetryWithRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ulong)

- ea: `0x1800e12c0`
- end: `0x1800e1959`
- name: `?SendTelemetryWithRetry@Core@Autopilot@ModernDeployment@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K@Z`
- size: `1689`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e1134`

## callees

- `0x18000b8f0`
- `0x180065d98`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb94`
- `0x180077c04`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x180081f38`
- `0x180084574`
- `0x180089660`
- `0x18008af70`
- `0x1800a4890`
- `0x1800dbd94`
- `0x1800dcfdc`
- `0x1800df8c8`
- `0x1800e12c0`
- `0x1800e1bc0`
- `0x1800e1d10`
- `0x1800e1e8c`
- `0x1800e5178`
- `0x1800e5248`
- `0x1800e52b0`
- `0x1800e66f4`
- `0x1801a110c`
- `0x1801a138c`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e14f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800e14f8`

## string_xrefs

- `0x1800e151f`: `application/json; charset=utf-8`
- `0x1800e1589`: `X-Device-Token`
- `0x1800e1333`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e13c9`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e13ea`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e1461`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e14a0`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e1878`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e189e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e18d0`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`
- `0x1800e1914`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fastwindowstelemetry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
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
0x1800e12c0  mov     rax, rsp
0x1800e12c3  push    rbx
0x1800e12c4  push    rsi
0x1800e12c5  push    rdi
0x1800e12c6  push    r12
0x1800e12c8  push    r13
0x1800e12ca  push    r14
0x1800e12cc  push    r15
0x1800e12ce  sub     rsp, 150h
0x1800e12d5  movaps  xmmword ptr [rax-48h], xmm6
0x1800e12d9  mov     rax, cs:__security_cookie
0x1800e12e0  xor     rax, rsp
0x1800e12e3  mov     [rsp+188h+var_58], rax
0x1800e12eb  mov     r13d, r8d
0x1800e12ee  mov     r15, rdx
0x1800e12f1  mov     r12, rcx
0x1800e12f4  mov     [rsp+188h+var_E0], rcx
0x1800e12fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e1303  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e1308  xor     r14d, r14d
0x1800e130b  test    al, al
0x1800e130d  jz      loc_1800E1904
0x1800e1313  mov     [rsp+188h+var_10C], r14d
0x1800e1318  lea     rcx, [rsp+188h+var_10C]; unsigned int *
0x1800e131d  call    ?GetMaxRetryAttempts@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetMaxRetryAttempts(ulong &)
0x1800e1322  mov     ebx, eax
0x1800e1324  test    eax, eax
0x1800e1326  jns     short loc_1800E134B
0x1800e1328  mov     rcx, [rsp+188h]; this
0x1800e1330  mov     r9d, eax; char *
0x1800e1333  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e133a  mov     edx, 1BAh; void *
0x1800e133f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1344  mov     eax, ebx
0x1800e1346  jmp     loc_1800E192D
0x1800e134b  xorps   xmm0, xmm0
0x1800e134e  movups  [rsp+188h+var_D8], xmm0
0x1800e1356  mov     [rsp+188h+var_C8], r14
0x1800e135e  mov     [rsp+188h+var_C0], 7
0x1800e136a  mov     word ptr [rsp+188h+var_D8], r14w
0x1800e1373  lea     rcx, [rsp+188h+var_D8]
0x1800e137b  call    ModernDeployment__Autopilot__Core__AcquireMsaDeviceTicket
0x1800e1380  test    eax, eax
0x1800e1382  js      short loc_1800E1391
0x1800e1384  cmp     [rsp+188h+var_C8], r14
0x1800e138c  mov     sil, 1
0x1800e138f  jnz     short loc_1800E1394
0x1800e1391  mov     sil, r14b
0x1800e1394  mov     [rsp+188h+var_118], r14b
0x1800e1399  lea     rcx, [rsp+188h+var_118]; bool *
0x1800e139e  call    ?IsUsingMockHttpNetworkWrapperForTesting@HttpNetworkWrapperFactory@Autopilot@Windows@Microsoft@@SAJAEA_N@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::IsUsingMockHttpNetworkWrapperForTesting(bool &)
0x1800e13a3  test    sil, sil
0x1800e13a6  jnz     short loc_1800E1410
0x1800e13a8  cmp     [rsp+188h+var_118], r14b
0x1800e13ad  jnz     short loc_1800E1410
0x1800e13af  mov     rdx, r15
0x1800e13b2  mov     ecx, r13d
0x1800e13b5  call    ?Enqueue@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::Enqueue(ulong,std::string const &)
0x1800e13ba  mov     rcx, [rsp+188h]; this
0x1800e13c2  test    eax, eax
0x1800e13c4  jns     short loc_1800E13DA
0x1800e13c6  mov     r9d, eax; char *
0x1800e13c9  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e13d0  mov     edx, 1CBh; void *
0x1800e13d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e13da  mov     rcx, [rsp+188h]; this
0x1800e13e2  mov     ebx, 80070005h
0x1800e13e7  mov     r9d, ebx; char *
0x1800e13ea  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e13f1  mov     edx, 1CCh; void *
0x1800e13f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e13fb  nop
0x1800e13fc  lea     rcx, [rsp+188h+var_D8]
0x1800e1404  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e1409  mov     eax, ebx
0x1800e140b  jmp     loc_1800E192D
0x1800e1410  mov     edi, r14d
0x1800e1413  mov     ebx, r14d
0x1800e1416  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800e141e  cmp     r14d, [rsp+188h+var_10C]
0x1800e1423  ja      loc_1800E185E
0x1800e1429  test    r14d, r14d
0x1800e142c  jz      loc_1800E1511
0x1800e1432  mov     [rsp+188h+dwMilliseconds], 0
0x1800e143a  lea     ecx, [r14-1]; unsigned int
0x1800e143e  cmp     ebx, 1ADh
0x1800e1444  jnz     short loc_1800E1485
0x1800e1446  lea     r8, [rsp+188h+dwMilliseconds]; unsigned int *
0x1800e144b  call    ?GetDelayForThrottledResponse@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJKKAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForThrottledResponse(ulong,ulong,ulong &)
0x1800e1450  mov     edi, eax
0x1800e1452  test    eax, eax
0x1800e1454  jns     short loc_1800E14C6
0x1800e1456  mov     rcx, [rsp+188h]; this
0x1800e145e  mov     r9d, eax; char *
0x1800e1461  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e1468  lea     edx, [rbx+2Bh]; void *
0x1800e146b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e1470  nop
0x1800e1471  lea     rcx, [rsp+188h+var_D8]
0x1800e1479  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e147e  mov     eax, edi
0x1800e1480  jmp     loc_1800E192D
0x1800e1485  lea     rdx, [rsp+188h+dwMilliseconds]; unsigned int *
0x1800e148a  call    ?GetDelayForAttempt@FwtRetryPolicy@Core@Autopilot@ModernDeployment@@SAJKAEAK@Z; ModernDeployment::Autopilot::Core::FwtRetryPolicy::GetDelayForAttempt(ulong,ulong &)
0x1800e148f  mov     edi, eax
0x1800e1491  test    eax, eax
0x1800e1493  jns     short loc_1800E14C6
0x1800e1495  mov     rcx, [rsp+188h]; this
0x1800e149d  mov     r9d, eax; char *
0x1800e14a0  lea     r8, aOnecoreuapAdmi_160; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e14a7  mov     edx, 1DCh; void *
0x1800e14ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e14b1  nop
0x1800e14b2  lea     rcx, [rsp+188h+var_D8]
0x1800e14ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e14bf  mov     eax, edi
0x1800e14c1  jmp     loc_1800E192D
0x1800e14c6  mov     edi, [rsp+188h+dwMilliseconds]
0x1800e14ca  test    edi, edi
0x1800e14cc  jz      short loc_1800E1511
0x1800e14ce  mov     [rsp+188h+dwMilliseconds], 1
0x1800e14d6  lea     rdx, [rsp+188h+dwMilliseconds]
0x1800e14db  lea     rcx, [rsp+188h+hHandle]
0x1800e14e3  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800e14e8  mov     r8d, 1; bAlertable
0x1800e14ee  mov     edx, edi; dwMilliseconds
0x1800e14f0  mov     rcx, [rsp+188h+hHandle]; hHandle
0x1800e14f8  call    cs:__imp_WaitForSingleObjectEx
0x1800e14ff  nop     dword ptr [rax+rax+00h]
0x1800e1504  lea     rcx, [rsp+188h+hHandle]
0x1800e150c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e1511  lea     rcx, [rsp+188h+var_108]
0x1800e1519  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800e151e  nop
0x1800e151f  lea     rdx, aApplicationJso_0; "application/json; charset=utf-8"
0x1800e1526  lea     rcx, [rsp+188h+var_78]
0x1800e152e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e1533  mov     rdi, rax
0x1800e1536  lea     rdx, aContentType; "Content-Type"
0x1800e153d  lea     rcx, [rsp+188h+var_B8]
0x1800e1545  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e154a  nop
0x1800e154b  mov     rdx, rax
0x1800e154e  lea     rcx, [rsp+188h+var_108]
0x1800e1556  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800e155b  mov     rdx, rdi
0x1800e155e  mov     rcx, rax
0x1800e1561  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e1566  nop
0x1800e1567  lea     rcx, [rsp+188h+var_B8]
0x1800e156f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e1574  nop
0x1800e1575  lea     rcx, [rsp+188h+var_78]
0x1800e157d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e1582  xor     edi, edi
0x1800e1584  test    sil, sil
0x1800e1587  jz      short loc_1800E15CC
0x1800e1589  lea     rdx, aXDeviceToken; "X-Device-Token"
0x1800e1590  lea     rcx, [rsp+188h+var_78]
0x1800e1598  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e159d  nop
0x1800e159e  mov     rdx, rax
0x1800e15a1  lea     rcx, [rsp+188h+var_108]
0x1800e15a9  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x1800e15ae  lea     rdx, [rsp+188h+var_D8]
0x1800e15b6  mov     rcx, rax
0x1800e15b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800e15be  nop
0x1800e15bf  lea     rcx, [rsp+188h+var_78]
0x1800e15c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e15cc  mov     [rsp+188h+var_F8], rdi
0x1800e15d4  mov     [rsp+188h+var_F0], rdi
0x1800e15dc  mov     [rsp+188h+var_110], edi
0x1800e15e0  xorps   xmm0, xmm0
0x1800e15e3  movdqu  xmmword ptr [rsp+188h+var_B8], xmm0
0x1800e15ec  lea     rcx, [rsp+188h+var_B8]
0x1800e15f4  call    ?CreateHttpNetworkWrapper@HttpNetworkWrapperFactory@Autopilot@Windows@Microsoft@@SAJAEAV?$shared_ptr@UIHttpNetworkWrapper@Autopilot@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapperFactory::CreateHttpNetworkWrapper(std::shared_ptr<Microsoft::Windows::Autopilot::IHttpNetworkWrapper> &)
0x1800e15f9  mov     edi, eax
0x1800e15fb  test    eax, eax
0x1800e15fd  jns     short loc_1800E1625
0x1800e15ff  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800e1607  test    rcx, rcx
0x1800e160a  jz      short loc_1800E1612
0x1800e160c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e1611  nop
0x1800e1612  lea     rcx, [rsp+188h+var_F8]
0x1800e161a  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800e161f  nop
0x1800e1620  jmp     loc_1800E17F8
0x1800e1625  xorps   xmm0, xmm0
0x1800e1628  movups  [rsp+188h+var_98], xmm0
0x1800e1630  movdqu  [rsp+188h+var_88], xmm6
0x1800e1639  xor     eax, eax
0x1800e163b  mov     word ptr [rsp+188h+var_98], ax
0x1800e1643  mov     rdi, [rsp+188h+var_B8]
0x1800e164b  mov     rcx, r15
0x1800e164e  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800e1653  mov     rbx, rax
0x1800e1656  mov     rcx, r12
0x1800e1659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e165e  mov     rcx, [rdi]
0x1800e1661  mov     r10, [rcx+8]
0x1800e1665  lea     rcx, [rsp+188h+var_F8]
0x1800e166d  mov     [rsp+188h+var_130], rcx
0x1800e1672  lea     rcx, [rsp+188h+var_98]
0x1800e167a  mov     [rsp+188h+var_138], rcx
0x1800e167f  lea     rcx, [rsp+188h+var_110]
0x1800e1684  mov     [rsp+188h+var_140], rcx
0x1800e1689  mov     edx, [r15+10h]
0x1800e168d  mov     [rsp+188h+var_148], edx
0x1800e1691  mov     [rsp+188h+var_150], rbx
0x1800e1696  lea     rcx, [rsp+188h+var_108]
0x1800e169e  mov     [rsp+188h+var_158], rcx
0x1800e16a3  mov     [rsp+188h+var_160], 0
0x1800e16ac  lea     rcx, aHttp11; "HTTP/1.1"
0x1800e16b3  mov     qword ptr [rsp+188h+var_168], rcx; int
0x1800e16b8  mov     r9d, 1
0x1800e16be  mov     r8, rax
0x1800e16c1  lea     rdx, aFwtclient; "FWTClient"
0x1800e16c8  mov     rcx, rdi
0x1800e16cb  mov     rax, r10
0x1800e16ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e16d3  mov     edi, eax
0x1800e16d5  mov     rcx, r12
0x1800e16d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e16dd  mov     rbx, rax
0x1800e16e0  mov     r12d, [r15+10h]
0x1800e16e4  call    ?IsEnabled@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@SA_NE_K@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::IsEnabled(uchar,unsigned __int64)
0x1800e16e9  test    al, al
0x1800e16eb  jz      short loc_1800E1701
0x1800e16ed  call    ?get@?$static_lazy@VFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@@details@wil@@QEAAPEAVFastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@P6AXXZ@Z; wil::details::static_lazy<ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging>::get(void (*)(void))
0x1800e16f2  mov     r9, rbx; unsigned __int16 *
0x1800e16f5  mov     r8d, r12d; unsigned int
0x1800e16f8  mov     edx, [rsp+188h+var_110]; unsigned int
0x1800e16fc  call    ?UploadTelemetryResponse_@FastWindowsTelemetryTraceLogging@Core@Autopilot@ModernDeployment@@QEAAXKIPEBG@Z; ModernDeployment::Autopilot::Core::FastWindowsTelemetryTraceLogging::UploadTelemetryResponse_(ulong,uint,ushort const *)
0x1800e1701  mov     ebx, [rsp+188h+var_110]
0x1800e1705  test    edi, edi
0x1800e1707  js      short loc_1800E176A
0x1800e1709  cmp     ebx, 0C8h
0x1800e170f  jnz     short loc_1800E176A
0x1800e1711  lea     rcx, [rsp+188h+var_98]
0x1800e1719  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e171e  nop
0x1800e171f  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800e1727  test    rcx, rcx
0x1800e172a  jz      short loc_1800E1732
0x1800e172c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e1731  nop
0x1800e1732  lea     rcx, [rsp+188h+var_F8]
0x1800e173a  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800e173f  nop
0x1800e1740  lea     rdx, [rsp+188h+var_108]
0x1800e1748  lea     rcx, [rsp+188h+var_108]
0x1800e1750  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800e1755  nop
0x1800e1756  lea     rcx, [rsp+188h+var_D8]
0x1800e175e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e1763  xor     eax, eax
0x1800e1765  jmp     loc_1800E192D
0x1800e176a  test    ebx, ebx
0x1800e176c  jz      short loc_1800E17C1
0x1800e176e  mov     eax, ebx
0x1800e1770  sub     eax, 198h
0x1800e1775  jz      short loc_1800E17C1
0x1800e1777  sub     eax, 15h
0x1800e177a  jz      short loc_1800E17C1
0x1800e177c  sub     eax, 14h
0x1800e177f  jz      short loc_1800E17C1
0x1800e1781  sub     eax, 33h ; '3'
0x1800e1784  jz      short loc_1800E17C1
0x1800e1786  sub     eax, 1
0x1800e1789  jz      short loc_1800E17C1
0x1800e178b  sub     eax, 1
0x1800e178e  jz      short loc_1800E17C1
0x1800e1790  sub     eax, 1
0x1800e1793  jz      short loc_1800E17C1
0x1800e1795  cmp     eax, 1
0x1800e1798  jz      short loc_1800E17C1
0x1800e179a  cmp     ebx, 191h
0x1800e17a0  jnz     short loc_1800E181A
0x1800e17a2  lea     rcx, [rsp+188h+var_D8]
0x1800e17aa  call    ModernDeployment__Autopilot__Core__AcquireMsaDeviceTicket
0x1800e17af  test    eax, eax
0x1800e17b1  js      short loc_1800E1815
0x1800e17b3  cmp     [rsp+188h+var_C8], 0
0x1800e17bc  jz      short loc_1800E1815
0x1800e17be  mov     sil, 1
0x1800e17c1  lea     rcx, [rsp+188h+var_98]
0x1800e17c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e17ce  nop
0x1800e17cf  mov     rcx, [rsp+188h+var_B8+8]; this
0x1800e17d7  test    rcx, rcx
0x1800e17da  jz      short loc_1800E17E2
0x1800e17dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e17e1  nop
0x1800e17e2  lea     rcx, [rsp+188h+var_F8]
0x1800e17ea  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x1800e17ef  nop
0x1800e17f0  mov     r12, [rsp+188h+var_E0]
0x1800e17f8  lea     rdx, [rsp+188h+var_108]
  ... truncated ...
```
