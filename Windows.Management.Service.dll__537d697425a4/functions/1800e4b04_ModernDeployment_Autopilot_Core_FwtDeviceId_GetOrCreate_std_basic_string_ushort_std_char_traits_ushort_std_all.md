# ModernDeployment::Autopilot::Core::FwtDeviceId::GetOrCreate(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800e4b04`
- end: `0x1800e4ef2`
- name: `?GetOrCreate@FwtDeviceId@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1006`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dd23c`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006e5e4`
- `0x180077de0`
- `0x180077e54`
- `0x180080984`
- `0x180080bac`
- `0x180084d80`
- `0x18008a454`
- `0x18008af70`
- `0x18008c18c`
- `0x1800e4b04`
- `0x180138278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e4b73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e4b73`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e4c4d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800e4c4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e4e15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e4e15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e4d6c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e4d6c`

## string_xrefs

- `0x1800e4b52`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e4c6a`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e4ce3`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e4d96`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`
- `0x1800e4e3f`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceid.cpp`

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
    v5 = (const WCHAR *)&stru_18022EC60;
    v6 = (const WCHAR *)&stru_18022EC60;
    if ( !v3 )
      v6 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
    if ( (int)Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(v4, v6, L"DeviceId", &v23) >= 0
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
0x1800e4b04  mov     [rsp+arg_8], rbx
0x1800e4b09  mov     [rsp+arg_10], rsi
0x1800e4b0e  push    rdi
0x1800e4b0f  push    r14
0x1800e4b11  push    r15
0x1800e4b13  sub     rsp, 0C0h
0x1800e4b1a  mov     rax, cs:__security_cookie
0x1800e4b21  xor     rax, rsp
0x1800e4b24  mov     [rsp+0D8h+var_28], rax
0x1800e4b2c  mov     rdi, rcx
0x1800e4b2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e4b36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e4b3b  xor     r14d, r14d
0x1800e4b3e  test    al, al
0x1800e4b40  jnz     short loc_1800E4B69
0x1800e4b42  mov     rcx, [rsp+0D8h]; this
0x1800e4b4a  mov     ebx, 80004001h
0x1800e4b4f  mov     r9d, ebx; char *
0x1800e4b52  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4b59  lea     edx, [r14+16h]; void *
0x1800e4b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4b62  mov     eax, ebx
0x1800e4b64  jmp     loc_1800E4EC8
0x1800e4b69  lea     rbx, CriticalSection
0x1800e4b70  mov     rcx, rbx; lpCriticalSection
0x1800e4b73  call    cs:__imp_EnterCriticalSection
0x1800e4b7a  nop     dword ptr [rax+rax+00h]
0x1800e4b7f  mov     [rsp+0D8h+var_80], rbx
0x1800e4b84  xorps   xmm0, xmm0
0x1800e4b87  movups  [rsp+0D8h+var_78], xmm0
0x1800e4b8c  mov     [rsp+0D8h+var_68], r14
0x1800e4b91  mov     [rsp+0D8h+var_60], 7
0x1800e4b9a  mov     word ptr [rsp+0D8h+var_78], r14w
0x1800e4ba0  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e4ba5  lea     r15, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800e4bac  lea     rsi, stru_18022EC60
0x1800e4bb3  mov     rdx, rsi
0x1800e4bb6  test    al, al
0x1800e4bb8  cmovz   rdx, r15
0x1800e4bbc  lea     r9, [rsp+0D8h+var_78]
0x1800e4bc1  lea     r8, aDeviceid; "DeviceId"
0x1800e4bc8  call    ?ReadStringValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x1800e4bcd  test    eax, eax
0x1800e4bcf  js      short loc_1800E4C3A
0x1800e4bd1  mov     rbx, [rsp+0D8h+var_68]
0x1800e4bd6  test    rbx, rbx
0x1800e4bd9  jz      short loc_1800E4C3A
0x1800e4bdb  test    rbx, rbx
0x1800e4bde  jz      short loc_1800E4C10
0x1800e4be0  lea     rcx, [rsp+0D8h+var_78]
0x1800e4be5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e4bea  cmp     [rax+rbx*2-2], r14w
0x1800e4bf0  jnz     short loc_1800E4C10
0x1800e4bf2  dec     rbx
0x1800e4bf5  mov     [rsp+0D8h+var_68], rbx
0x1800e4bfa  lea     rcx, [rsp+0D8h+var_78]
0x1800e4bff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e4c04  mov     [rax+rbx*2], r14w
0x1800e4c09  mov     rbx, [rsp+0D8h+var_68]
0x1800e4c0e  jmp     short loc_1800E4BDB
0x1800e4c10  lea     rdx, [rsp+0D8h+var_78]
0x1800e4c15  mov     rcx, rdi
0x1800e4c18  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e4c1d  nop
0x1800e4c1e  lea     rcx, [rsp+0D8h+var_78]
0x1800e4c23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4c28  nop
0x1800e4c29  lea     rcx, [rsp+0D8h+var_80]
0x1800e4c2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4c33  xor     eax, eax
0x1800e4c35  jmp     loc_1800E4EC8
0x1800e4c3a  xorps   xmm0, xmm0
0x1800e4c3d  movups  xmmword ptr [rsp+0D8h+pguid.Data1], xmm0
0x1800e4c45  lea     rcx, [rsp+0D8h+pguid]; pguid
0x1800e4c4d  call    cs:__imp_CoCreateGuid
0x1800e4c54  nop     dword ptr [rax+rax+00h]
0x1800e4c59  mov     ebx, eax
0x1800e4c5b  test    eax, eax
0x1800e4c5d  jns     short loc_1800E4C98
0x1800e4c5f  mov     rcx, [rsp+0D8h]; this
0x1800e4c67  mov     r9d, eax; char *
0x1800e4c6a  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4c71  mov     edx, 31h ; '1'; void *
0x1800e4c76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4c7b  nop
0x1800e4c7c  lea     rcx, [rsp+0D8h+var_78]
0x1800e4c81  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4c86  nop
0x1800e4c87  lea     rcx, [rsp+0D8h+var_80]
0x1800e4c8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4c91  mov     eax, ebx
0x1800e4c93  jmp     loc_1800E4EC8
0x1800e4c98  xorps   xmm0, xmm0
0x1800e4c9b  movups  [rsp+0D8h+var_58], xmm0
0x1800e4ca3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e4cab  movdqu  [rsp+0D8h+var_48], xmm1
0x1800e4cb4  mov     word ptr [rsp+0D8h+var_58], r14w
0x1800e4cbd  lea     r8, [rsp+0D8h+var_58]
0x1800e4cc5  lea     rcx, [rsp+0D8h+pguid]; rguid
0x1800e4ccd  call    ?GetGuidStringFromGuid@DeviceLinkEncoding@Core@Autopilot@ModernDeployment@@SAJAEBU_GUID@@W4GuidFormat@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GetGuidStringFromGuid(_GUID const &,ModernDeployment::Autopilot::Core::DeviceLinkEncoding::GuidFormat,std::wstring &)
0x1800e4cd2  mov     ebx, eax
0x1800e4cd4  test    eax, eax
0x1800e4cd6  jns     short loc_1800E4D1F
0x1800e4cd8  mov     rcx, [rsp+0D8h]; this
0x1800e4ce0  mov     r9d, eax; char *
0x1800e4ce3  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4cea  mov     edx, 34h ; '4'; void *
0x1800e4cef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4cf4  nop
0x1800e4cf5  lea     rcx, [rsp+0D8h+var_58]
0x1800e4cfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4d02  nop
0x1800e4d03  lea     rcx, [rsp+0D8h+var_78]
0x1800e4d08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4d0d  nop
0x1800e4d0e  lea     rcx, [rsp+0D8h+var_80]
0x1800e4d13  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4d18  mov     eax, ebx
0x1800e4d1a  jmp     loc_1800E4EC8
0x1800e4d1f  mov     [rsp+0D8h+hKey], r14
0x1800e4d24  xor     edx, edx
0x1800e4d26  lea     rcx, [rsp+0D8h+hKey]
0x1800e4d2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800e4d30  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800e4d35  test    al, al
0x1800e4d37  cmovz   rsi, r15
0x1800e4d3b  mov     [rsp+0D8h+lpdwDisposition], r14; lpdwDisposition
0x1800e4d40  lea     rax, [rsp+0D8h+hKey]
0x1800e4d45  mov     [rsp+0D8h+phkResult], rax; phkResult
0x1800e4d4a  mov     [rsp+0D8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800e4d4f  mov     [rsp+0D8h+samDesired], 2001Fh; samDesired
0x1800e4d57  mov     [rsp+0D8h+dwOptions], r14d; int
0x1800e4d5c  xor     r9d, r9d; lpClass
0x1800e4d5f  xor     r8d, r8d; Reserved
0x1800e4d62  mov     rdx, rsi; lpSubKey
0x1800e4d65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e4d6c  call    cs:__imp_RegCreateKeyExW
0x1800e4d73  nop     dword ptr [rax+rax+00h]
0x1800e4d78  mov     ebx, eax
0x1800e4d7a  test    eax, eax
0x1800e4d7c  jle     short loc_1800E4D87
0x1800e4d7e  movzx   ebx, ax
0x1800e4d81  or      ebx, 80070000h
0x1800e4d87  test    ebx, ebx
0x1800e4d89  jns     short loc_1800E4DDC
0x1800e4d8b  mov     rcx, [rsp+0D8h]; this
0x1800e4d93  mov     r9d, ebx; char *
0x1800e4d96  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4d9d  mov     edx, 41h ; 'A'; void *
0x1800e4da2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4da7  lea     rcx, [rsp+0D8h+hKey]
0x1800e4dac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e4db1  nop
0x1800e4db2  lea     rcx, [rsp+0D8h+var_58]
0x1800e4dba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4dbf  nop
0x1800e4dc0  lea     rcx, [rsp+0D8h+var_78]
0x1800e4dc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4dca  nop
0x1800e4dcb  lea     rcx, [rsp+0D8h+var_80]
0x1800e4dd0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4dd5  mov     eax, ebx
0x1800e4dd7  jmp     loc_1800E4EC8
0x1800e4ddc  mov     eax, dword ptr [rsp+0D8h+var_48]
0x1800e4de3  lea     ebx, ds:2[rax*2]
0x1800e4dea  lea     rcx, [rsp+0D8h+var_58]
0x1800e4df2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e4df7  mov     [rsp+0D8h+samDesired], ebx; cbData
0x1800e4dfb  mov     qword ptr [rsp+0D8h+dwOptions], rax; int
0x1800e4e00  mov     r9d, 1; dwType
0x1800e4e06  xor     r8d, r8d; Reserved
0x1800e4e09  lea     rdx, aDeviceid; "DeviceId"
0x1800e4e10  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800e4e15  call    cs:__imp_RegSetValueExW
0x1800e4e1c  nop     dword ptr [rax+rax+00h]
0x1800e4e21  mov     ebx, eax
0x1800e4e23  test    eax, eax
0x1800e4e25  jle     short loc_1800E4E30
0x1800e4e27  movzx   ebx, ax
0x1800e4e2a  or      ebx, 80070000h
0x1800e4e30  test    ebx, ebx
0x1800e4e32  jns     short loc_1800E4E82
0x1800e4e34  mov     rcx, [rsp+0D8h]; this
0x1800e4e3c  mov     r9d, ebx; char *
0x1800e4e3f  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e4e46  mov     edx, 4Ah ; 'J'; void *
0x1800e4e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4e50  lea     rcx, [rsp+0D8h+hKey]
0x1800e4e55  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e4e5a  nop
0x1800e4e5b  lea     rcx, [rsp+0D8h+var_58]
0x1800e4e63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4e68  nop
0x1800e4e69  lea     rcx, [rsp+0D8h+var_78]
0x1800e4e6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4e73  nop
0x1800e4e74  lea     rcx, [rsp+0D8h+var_80]
0x1800e4e79  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4e7e  mov     eax, ebx
0x1800e4e80  jmp     short loc_1800E4EC8
0x1800e4e82  lea     rdx, [rsp+0D8h+var_58]
0x1800e4e8a  mov     rcx, rdi
0x1800e4e8d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e4e92  lea     rcx, [rsp+0D8h+hKey]
0x1800e4e97  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e4e9c  nop
0x1800e4e9d  lea     rcx, [rsp+0D8h+var_58]
0x1800e4ea5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4eaa  nop
0x1800e4eab  lea     rcx, [rsp+0D8h+var_78]
0x1800e4eb0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4eb5  nop
0x1800e4eb6  lea     rcx, [rsp+0D8h+var_80]
0x1800e4ebb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800e4ec0  xor     eax, eax
0x1800e4ec2  jmp     short loc_1800E4EC8
0x1800e4ec4  mov     eax, dword ptr [rsp+0D8h+hKey]
0x1800e4ec8  mov     rcx, [rsp+0D8h+var_28]
0x1800e4ed0  xor     rcx, rsp; StackCookie
0x1800e4ed3  call    __security_check_cookie
0x1800e4ed8  lea     r11, [rsp+0D8h+var_18]
0x1800e4ee0  mov     rbx, [r11+28h]
0x1800e4ee4  mov     rsi, [r11+30h]
0x1800e4ee8  mov     rsp, r11
0x1800e4eeb  pop     r15
0x1800e4eed  pop     r14
0x1800e4eef  pop     rdi
0x1800e4ef0  retn
```
