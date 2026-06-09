# ModernDeployment::Autopilot::Core::FwtDeviceId::GetOrCreate(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800e2210`
- end: `0x1800e25e6`
- name: `?GetOrCreate@FwtDeviceId@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `982`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800daa7c`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006e088`
- `0x18007755c`
- `0x1800775c4`
- `0x18007ff90`
- `0x18008019c`
- `0x180084208`
- `0x180089614`
- `0x18008a0a8`
- `0x18008b240`
- `0x1800e2210`
- `0x1801343e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e227f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e227f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e2353`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e2353`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e250f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e250f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e246c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e246c`

## string_xrefs

- `0x1800e225e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e236a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e23e3`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e2490`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e2533`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtDeviceId::GetOrCreate(__int64 a1)
{
  bool v3; // al
  __int64 v4; // rcx
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rdx
  __int64 v7; // rbx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int GuidStringFromGuid; // eax
  unsigned int v11; // ebx
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  DWORD v14; // ebx
  const BYTE *v15; // rax
  LSTATUS v16; // eax
  unsigned int v17; // ebx
  int dwOptions; // [rsp+20h] [rbp-B8h]
  int dwOptionsa; // [rsp+20h] [rbp-B8h]
  int dwOptionsb; // [rsp+20h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+58h] [rbp-80h] BYREF
  __int128 v23; // [rsp+60h] [rbp-78h] BYREF
  __int64 v24; // [rsp+70h] [rbp-68h]
  __int64 v25; // [rsp+78h] [rbp-60h]
  __int128 v26; // [rsp+80h] [rbp-58h] BYREF
  __m128i si128; // [rsp+90h] [rbp-48h]
  GUID pguid; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection(&CriticalSection);
    v22 = &CriticalSection;
    v23 = 0;
    v24 = 0;
    v25 = 7;
    LOWORD(v23) = 0;
    v3 = ZTPIsStateSeparationEnabled();
    v5 = (const WCHAR *)&stru_180228C20;
    v6 = (const WCHAR *)&stru_180228C20;
    if ( !v3 )
      v6 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
    if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(
                v4,
                v6,
                L"DeviceId",
                (__int64)&v23) >= 0
      && (v7 = v24) != 0 )
    {
      while ( v7 && !*(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v23) + 2 * v7 - 2) )
      {
        v24 = v7 - 1;
        *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v23) + 2 * v24) = 0;
        v7 = v24;
      }
      std::wstring::operator=(a1, &v23);
      std::wstring::_Tidy_deallocate(&v23);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
      return 0;
    }
    else
    {
      pguid = 0;
      v8 = CoCreateGuid(&pguid);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v26 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v26) = 0;
        GuidStringFromGuid = ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(&pguid);
        v11 = GuidStringFromGuid;
        if ( GuidStringFromGuid >= 0 )
        {
          hKey = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          if ( !ZTPIsStateSeparationEnabled() )
            v5 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
          v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
          v13 = v12;
          if ( v12 > 0 )
            v13 = (unsigned __int16)v12 | 0x80070000;
          if ( (v13 & 0x80000000) == 0 )
          {
            v14 = 2 * si128.m128i_i32[0] + 2;
            v15 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v26);
            v16 = RegSetValueExW(hKey, L"DeviceId", 0, 1u, v15, v14);
            v17 = v16;
            if ( v16 > 0 )
              v17 = (unsigned __int16)v16 | 0x80070000;
            if ( (v17 & 0x80000000) == 0 )
            {
              std::wstring::operator=(a1, &v26);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::wstring::_Tidy_deallocate(&v26);
              std::wstring::_Tidy_deallocate(&v23);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4A,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid.cpp",
                (const char *)v17,
                dwOptionsb);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              std::wstring::_Tidy_deallocate(&v26);
              std::wstring::_Tidy_deallocate(&v23);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
              return v17;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x41,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid.cpp",
              (const char *)v13,
              dwOptionsa);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            std::wstring::_Tidy_deallocate(&v26);
            std::wstring::_Tidy_deallocate(&v23);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
            return v13;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid.cpp",
            (const char *)(unsigned int)GuidStringFromGuid,
            dwOptions);
          std::wstring::_Tidy_deallocate(&v26);
          std::wstring::_Tidy_deallocate(&v23);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
          return v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid.cpp",
          (const char *)(unsigned int)v8,
          dwOptions);
        std::wstring::_Tidy_deallocate(&v23);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
        return v9;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid.cpp",
      (const char *)0x80004001LL,
      dwOptions);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800e2210  mov     [rsp+arg_8], rbx
0x1800e2215  mov     [rsp+arg_10], rsi
0x1800e221a  push    rdi
0x1800e221b  push    r14
0x1800e221d  push    r15
0x1800e221f  sub     rsp, 0C0h
0x1800e2226  mov     rax, cs:__security_cookie
0x1800e222d  xor     rax, rsp
0x1800e2230  mov     [rsp+0D8h+var_28], rax
0x1800e2238  mov     rdi, rcx
0x1800e223b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e2242  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e2247  xor     r14d, r14d
0x1800e224a  test    al, al
0x1800e224c  jnz     short loc_1800E2275
0x1800e224e  mov     rcx, [rsp+0D8h]; this
0x1800e2256  mov     ebx, 80004001h
0x1800e225b  mov     r9d, ebx; char *
0x1800e225e  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2265  lea     edx, [r14+16h]; void *
0x1800e2269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e226e  mov     eax, ebx
0x1800e2270  jmp     loc_1800E25BC
0x1800e2275  lea     rbx, CriticalSection
0x1800e227c  mov     rcx, rbx; lpCriticalSection
0x1800e227f  call    cs:__imp_EnterCriticalSection
0x1800e2285  mov     [rsp+0D8h+var_80], rbx
0x1800e228a  xorps   xmm0, xmm0
0x1800e228d  movups  [rsp+0D8h+var_78], xmm0
0x1800e2292  mov     [rsp+0D8h+var_68], r14
0x1800e2297  mov     [rsp+0D8h+var_60], 7
0x1800e22a0  mov     word ptr [rsp+0D8h+var_78], r14w
0x1800e22a6  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e22ab  lea     r15, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800e22b2  lea     rsi, stru_180228C20
0x1800e22b9  mov     rdx, rsi
0x1800e22bc  test    al, al
0x1800e22be  cmovz   rdx, r15
0x1800e22c2  lea     r9, [rsp+0D8h+var_78]
0x1800e22c7  lea     r8, aDeviceid; "DeviceId"
0x1800e22ce  call    ?ReadStringValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x1800e22d3  test    eax, eax
0x1800e22d5  js      short loc_1800E2340
0x1800e22d7  mov     rbx, [rsp+0D8h+var_68]
0x1800e22dc  test    rbx, rbx
0x1800e22df  jz      short loc_1800E2340
0x1800e22e1  test    rbx, rbx
0x1800e22e4  jz      short loc_1800E2316
0x1800e22e6  lea     rcx, [rsp+0D8h+var_78]
0x1800e22eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e22f0  cmp     [rax+rbx*2-2], r14w
0x1800e22f6  jnz     short loc_1800E2316
0x1800e22f8  dec     rbx
0x1800e22fb  mov     [rsp+0D8h+var_68], rbx
0x1800e2300  lea     rcx, [rsp+0D8h+var_78]
0x1800e2305  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e230a  mov     [rax+rbx*2], r14w
0x1800e230f  mov     rbx, [rsp+0D8h+var_68]
0x1800e2314  jmp     short loc_1800E22E1
0x1800e2316  lea     rdx, [rsp+0D8h+var_78]
0x1800e231b  mov     rcx, rdi
0x1800e231e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e2323  nop
0x1800e2324  lea     rcx, [rsp+0D8h+var_78]
0x1800e2329  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e232e  nop
0x1800e232f  lea     rcx, [rsp+0D8h+var_80]
0x1800e2334  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e2339  xor     eax, eax
0x1800e233b  jmp     loc_1800E25BC
0x1800e2340  xorps   xmm0, xmm0
0x1800e2343  movups  xmmword ptr [rsp+0D8h+pguid.Data1], xmm0
0x1800e234b  lea     rcx, [rsp+0D8h+pguid]; pguid
0x1800e2353  call    cs:__imp_CoCreateGuid
0x1800e2359  mov     ebx, eax
0x1800e235b  test    eax, eax
0x1800e235d  jns     short loc_1800E2398
0x1800e235f  mov     rcx, [rsp+0D8h]; this
0x1800e2367  mov     r9d, eax; char *
0x1800e236a  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2371  mov     edx, 31h ; '1'; void *
0x1800e2376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e237b  nop
0x1800e237c  lea     rcx, [rsp+0D8h+var_78]
0x1800e2381  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2386  nop
0x1800e2387  lea     rcx, [rsp+0D8h+var_80]
0x1800e238c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e2391  mov     eax, ebx
0x1800e2393  jmp     loc_1800E25BC
0x1800e2398  xorps   xmm0, xmm0
0x1800e239b  movups  [rsp+0D8h+var_58], xmm0
0x1800e23a3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e23ab  movdqu  [rsp+0D8h+var_48], xmm1
0x1800e23b4  mov     word ptr [rsp+0D8h+var_58], r14w
0x1800e23bd  lea     r8, [rsp+0D8h+var_58]
0x1800e23c5  lea     rcx, [rsp+0D8h+pguid]; rguid
0x1800e23cd  call    ?GetGuidStringFromGuid@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_GUID@@W4GuidFormat@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(_GUID const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x1800e23d2  mov     ebx, eax
0x1800e23d4  test    eax, eax
0x1800e23d6  jns     short loc_1800E241F
0x1800e23d8  mov     rcx, [rsp+0D8h]; this
0x1800e23e0  mov     r9d, eax; char *
0x1800e23e3  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e23ea  mov     edx, 34h ; '4'; void *
0x1800e23ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e23f4  nop
0x1800e23f5  lea     rcx, [rsp+0D8h+var_58]
0x1800e23fd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2402  nop
0x1800e2403  lea     rcx, [rsp+0D8h+var_78]
0x1800e2408  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e240d  nop
0x1800e240e  lea     rcx, [rsp+0D8h+var_80]
0x1800e2413  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e2418  mov     eax, ebx
0x1800e241a  jmp     loc_1800E25BC
0x1800e241f  mov     [rsp+0D8h+hKey], r14
0x1800e2424  xor     edx, edx
0x1800e2426  lea     rcx, [rsp+0D8h+hKey]
0x1800e242b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800e2430  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e2435  test    al, al
0x1800e2437  cmovz   rsi, r15
0x1800e243b  mov     [rsp+0D8h+lpdwDisposition], r14; lpdwDisposition
0x1800e2440  lea     rax, [rsp+0D8h+hKey]
0x1800e2445  mov     [rsp+0D8h+phkResult], rax; phkResult
0x1800e244a  mov     [rsp+0D8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800e244f  mov     [rsp+0D8h+samDesired], 2001Fh; samDesired
0x1800e2457  mov     [rsp+0D8h+dwOptions], r14d; int
0x1800e245c  xor     r9d, r9d; lpClass
0x1800e245f  xor     r8d, r8d; Reserved
0x1800e2462  mov     rdx, rsi; lpSubKey
0x1800e2465  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e246c  call    cs:__imp_RegCreateKeyExW
0x1800e2472  mov     ebx, eax
0x1800e2474  test    eax, eax
0x1800e2476  jle     short loc_1800E2481
0x1800e2478  movzx   ebx, ax
0x1800e247b  or      ebx, 80070000h
0x1800e2481  test    ebx, ebx
0x1800e2483  jns     short loc_1800E24D6
0x1800e2485  mov     rcx, [rsp+0D8h]; this
0x1800e248d  mov     r9d, ebx; char *
0x1800e2490  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e2497  mov     edx, 41h ; 'A'; void *
0x1800e249c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e24a1  lea     rcx, [rsp+0D8h+hKey]
0x1800e24a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e24ab  nop
0x1800e24ac  lea     rcx, [rsp+0D8h+var_58]
0x1800e24b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e24b9  nop
0x1800e24ba  lea     rcx, [rsp+0D8h+var_78]
0x1800e24bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e24c4  nop
0x1800e24c5  lea     rcx, [rsp+0D8h+var_80]
0x1800e24ca  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e24cf  mov     eax, ebx
0x1800e24d1  jmp     loc_1800E25BC
0x1800e24d6  mov     eax, dword ptr [rsp+0D8h+var_48]
0x1800e24dd  lea     ebx, ds:2[rax*2]
0x1800e24e4  lea     rcx, [rsp+0D8h+var_58]
0x1800e24ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e24f1  mov     [rsp+0D8h+samDesired], ebx; cbData
0x1800e24f5  mov     qword ptr [rsp+0D8h+dwOptions], rax; int
0x1800e24fa  mov     r9d, 1; dwType
0x1800e2500  xor     r8d, r8d; Reserved
0x1800e2503  lea     rdx, aDeviceid; "DeviceId"
0x1800e250a  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800e250f  call    cs:__imp_RegSetValueExW
0x1800e2515  mov     ebx, eax
0x1800e2517  test    eax, eax
0x1800e2519  jle     short loc_1800E2524
0x1800e251b  movzx   ebx, ax
0x1800e251e  or      ebx, 80070000h
0x1800e2524  test    ebx, ebx
0x1800e2526  jns     short loc_1800E2576
0x1800e2528  mov     rcx, [rsp+0D8h]; this
0x1800e2530  mov     r9d, ebx; char *
0x1800e2533  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e253a  mov     edx, 4Ah ; 'J'; void *
0x1800e253f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2544  lea     rcx, [rsp+0D8h+hKey]
0x1800e2549  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e254e  nop
0x1800e254f  lea     rcx, [rsp+0D8h+var_58]
0x1800e2557  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e255c  nop
0x1800e255d  lea     rcx, [rsp+0D8h+var_78]
0x1800e2562  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2567  nop
0x1800e2568  lea     rcx, [rsp+0D8h+var_80]
0x1800e256d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e2572  mov     eax, ebx
0x1800e2574  jmp     short loc_1800E25BC
0x1800e2576  lea     rdx, [rsp+0D8h+var_58]
0x1800e257e  mov     rcx, rdi
0x1800e2581  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e2586  lea     rcx, [rsp+0D8h+hKey]
0x1800e258b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e2590  nop
0x1800e2591  lea     rcx, [rsp+0D8h+var_58]
0x1800e2599  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e259e  nop
0x1800e259f  lea     rcx, [rsp+0D8h+var_78]
0x1800e25a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e25a9  nop
0x1800e25aa  lea     rcx, [rsp+0D8h+var_80]
0x1800e25af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e25b4  xor     eax, eax
0x1800e25b6  jmp     short loc_1800E25BC
0x1800e25b8  mov     eax, dword ptr [rsp+0D8h+hKey]
0x1800e25bc  mov     rcx, [rsp+0D8h+var_28]
0x1800e25c4  xor     rcx, rsp; StackCookie
0x1800e25c7  call    __security_check_cookie
0x1800e25cc  lea     r11, [rsp+0D8h+var_18]
0x1800e25d4  mov     rbx, [r11+28h]
0x1800e25d8  mov     rsi, [r11+30h]
0x1800e25dc  mov     rsp, r11
0x1800e25df  pop     r15
0x1800e25e1  pop     r14
0x1800e25e3  pop     rdi
0x1800e25e4  retn
```
