# EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotStoreSetting(ushort const *,ushort const *)

- ea: `0x18017b624`
- end: `0x18017b9a8`
- name: `?AutoPilotStoreSetting@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBG0@Z`
- size: `900`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800be608`

## callees

- `0x18000b8f0`
- `0x180063800`
- `0x180067e54`
- `0x180077de0`
- `0x180080984`
- `0x180080bac`
- `0x180084574`
- `0x180084d80`
- `0x180088144`
- `0x180088a70`
- `0x18008a454`
- `0x18008d290`
- `0x18008ed40`
- `0x18008ef2c`
- `0x1800fe700`
- `0x18012a598`
- `0x18017b624`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017b7ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017b7dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017b7ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017b7dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18017b83c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18017b83c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017b84b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017b84b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18017b6ab`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18017b6ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18017b93d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18017b93d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18017b8a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18017b907`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18017b8a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18017b907`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18017b772`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18017b772`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotStoreSetting(
        wchar_t *Str,
        const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  bool v5; // al
  const WCHAR *v6; // rdx
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  __int64 v9; // rax
  const WCHAR *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rdx
  char IsEnabled; // bl
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  const WCHAR *v20; // rax
  DWORD v21; // ebx
  const WCHAR *v22; // rax
  const WCHAR *v23; // rax
  int dwOptions; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-89h]
  HKEY hKey; // [rsp+50h] [rbp-59h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v30[32]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v31[32]; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v32[32]; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( Str )
  {
    v5 = ZTPIsStateSeparationEnabled();
    v6 = (const WCHAR *)&stru_18022EC60;
    if ( !v5 )
      v6 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
    std::wstring::wstring(v30, v6);
    std::wstring::wstring(v29, Str);
    v7 = wcschr(Str, 0x2Fu);
    v8 = v7;
    if ( v7 )
    {
      std::wstring::substr(v29, v31, 0, v7 - Str);
      v9 = std::operator+<unsigned short>(v32, L"\\", v31);
      std::wstring::append(v30, v9);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::assign(v29, v8 + 1);
      std::wstring::_Tidy_deallocate(v31);
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v11 )
    {
      v12 = 912;
LABEL_22:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
             (const char *)v11,
             dwOptionsa);
      goto LABEL_31;
    }
    if ( !a2 )
    {
      v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      v11 = RegDeleteValueW(hKey, v23);
      if ( v11 && v11 - 2 >= 2 )
      {
        v12 = 983;
        goto LABEL_22;
      }
      goto LABEL_30;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::GetImpl'::`2'::impl);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    if ( IsEnabled )
    {
      if ( (unsigned int)_o__wcsicmp(v14, L"PageErrorPhase") )
      {
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
        if ( (unsigned int)_o__wcsicmp(v15, L"PageErrorCode") )
          goto LABEL_13;
      }
    }
    else if ( (wchar_t **)_std_find_trivial_8(&c_numericSettingsNames, off_18021C7D0, v14) == off_18021C7D0 )
    {
LABEL_13:
      *(_QWORD *)Data = 0;
      v17 = StringCbLengthW(a2, v16, (unsigned __int64 *)Data);
      v4 = v17;
      if ( v17 < 0 )
      {
        v18 = (unsigned int)v17;
        v19 = 955;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
          (const char *)v18,
          dwOptionsa);
LABEL_31:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v30);
        return v4;
      }
      v21 = *(_DWORD *)Data + 2;
      if ( (unsigned __int64)(*(_QWORD *)Data + 2LL) >= *(_QWORD *)Data )
      {
        v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
        v11 = RegSetValueExW(hKey, v22, 0, 1u, (const BYTE *)a2, v21);
        if ( v11 )
        {
          v12 = 966;
          goto LABEL_22;
        }
        goto LABEL_30;
      }
      v4 = -2147024362;
      v19 = 958;
      goto LABEL_18;
    }
    *(_DWORD *)Data = wcstoul(a2, 0, 16);
    if ( *(_DWORD *)_o__errno() != 34 )
    {
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      v11 = RegSetValueExW(hKey, v20, 0, 4u, Data, 4u);
      if ( v11 )
      {
        v12 = 948;
        goto LABEL_22;
      }
LABEL_30:
      v4 = 0;
      goto LABEL_31;
    }
    v4 = -2147024809;
    v19 = 940;
LABEL_18:
    v18 = v4;
    goto LABEL_19;
  }
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x375,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\autopilotutils\\autopilot.cpp",
    (const char *)0x80070057LL,
    dwOptions);
  return v4;
}

```

## disassembly

```asm
0x18017b624  mov     [rsp-8+arg_10], rbx
0x18017b629  push    rbp
0x18017b62a  push    rsi
0x18017b62b  push    rdi
0x18017b62c  lea     rbp, [rsp-47h]
0x18017b631  sub     rsp, 0F0h
0x18017b638  mov     rax, cs:__security_cookie
0x18017b63f  xor     rax, rsp
0x18017b642  mov     [rbp+57h+var_20], rax
0x18017b646  mov     rdi, rdx
0x18017b649  mov     rbx, rcx
0x18017b64c  test    rcx, rcx
0x18017b64f  jnz     short loc_18017B673
0x18017b651  mov     rcx, [rbp+5Fh]; this
0x18017b655  mov     ebx, 80070057h
0x18017b65a  mov     r9d, ebx; char *
0x18017b65d  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b664  mov     edx, 375h; void *
0x18017b669  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b66e  jmp     loc_18017B986
0x18017b673  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18017b678  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x18017b67f  lea     rdx, stru_18022EC60
0x18017b686  test    al, al
0x18017b688  cmovz   rdx, rcx
0x18017b68c  lea     rcx, [rbp+57h+var_80]
0x18017b690  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18017b695  nop
0x18017b696  mov     rdx, rbx
0x18017b699  lea     rcx, [rbp+57h+var_A0]
0x18017b69d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18017b6a2  nop
0x18017b6a3  mov     edx, 2Fh ; '/'; Ch
0x18017b6a8  mov     rcx, rbx; Str
0x18017b6ab  call    cs:__imp_wcschr
0x18017b6b2  nop     dword ptr [rax+rax+00h]
0x18017b6b7  mov     rsi, rax
0x18017b6ba  test    rax, rax
0x18017b6bd  jz      short loc_18017B71B
0x18017b6bf  mov     r9, rax
0x18017b6c2  sub     r9, rbx
0x18017b6c5  sar     r9, 1
0x18017b6c8  xor     r8d, r8d
0x18017b6cb  lea     rdx, [rbp+57h+var_60]
0x18017b6cf  lea     rcx, [rbp+57h+var_A0]
0x18017b6d3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18017b6d8  nop
0x18017b6d9  lea     r8, [rbp+57h+var_60]
0x18017b6dd  lea     rdx, SubBlock; "\\"
0x18017b6e4  lea     rcx, [rbp+57h+var_40]
0x18017b6e8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18017b6ed  nop
0x18017b6ee  mov     rdx, rax
0x18017b6f1  lea     rcx, [rbp+57h+var_80]
0x18017b6f5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18017b6fa  nop
0x18017b6fb  lea     rcx, [rbp+57h+var_40]
0x18017b6ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017b704  lea     rdx, [rsi+2]
0x18017b708  lea     rcx, [rbp+57h+var_A0]
0x18017b70c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18017b711  nop
0x18017b712  lea     rcx, [rbp+57h+var_60]
0x18017b716  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017b71b  mov     [rbp+57h+hKey], 0
0x18017b723  xor     edx, edx
0x18017b725  lea     rcx, [rbp+57h+hKey]
0x18017b729  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18017b72e  lea     rcx, [rbp+57h+var_80]
0x18017b732  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b737  mov     rdx, rax; lpSubKey
0x18017b73a  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x18017b743  lea     rax, [rbp+57h+hKey]
0x18017b747  mov     [rsp+100h+phkResult], rax; phkResult
0x18017b74c  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18017b755  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x18017b75d  mov     [rsp+100h+dwOptions], 0; int
0x18017b765  xor     r9d, r9d; lpClass
0x18017b768  xor     r8d, r8d; Reserved
0x18017b76b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18017b772  call    cs:__imp_RegCreateKeyExW
0x18017b779  nop     dword ptr [rax+rax+00h]
0x18017b77e  test    eax, eax
0x18017b780  jz      short loc_18017B78C
0x18017b782  mov     edx, 390h
0x18017b787  jmp     loc_18017B8BE
0x18017b78c  test    rdi, rdi
0x18017b78f  jz      loc_18017B92D
0x18017b795  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppRebootFix> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::GetImpl(void)'::`2'::impl
0x18017b79c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::__private_IsEnabled(void)
0x18017b7a1  mov     bl, al
0x18017b7a3  lea     rcx, [rbp+57h+var_A0]
0x18017b7a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b7ac  test    bl, bl
0x18017b7ae  jz      short loc_18017B815
0x18017b7b0  lea     rdx, ?c_devicePreparationPageErrorPhaseSettingName@@3QBGB; "PageErrorPhase"
0x18017b7b7  mov     rcx, rax
0x18017b7ba  call    cs:__imp__o__wcsicmp
0x18017b7c1  nop     dword ptr [rax+rax+00h]
0x18017b7c6  test    eax, eax
0x18017b7c8  jz      short loc_18017B833
0x18017b7ca  lea     rcx, [rbp+57h+var_A0]
0x18017b7ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b7d3  mov     rcx, rax
0x18017b7d6  lea     rdx, ?c_devicePreparationPageErrorCodeSettingName@@3QBGB; "PageErrorCode"
0x18017b7dd  call    cs:__imp__o__wcsicmp
0x18017b7e4  nop     dword ptr [rax+rax+00h]
0x18017b7e9  test    eax, eax
0x18017b7eb  jz      short loc_18017B833
0x18017b7ed  mov     qword ptr [rbp+57h+Data], 0
0x18017b7f5  lea     r8, [rbp+57h+Data]; unsigned __int64 *
0x18017b7f9  mov     rcx, rdi; unsigned __int16 *
0x18017b7fc  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18017b801  mov     ebx, eax
0x18017b803  test    eax, eax
0x18017b805  jns     loc_18017B8D8
0x18017b80b  mov     r9d, eax
0x18017b80e  mov     edx, 3BBh
0x18017b813  jmp     short loc_18017B869
0x18017b815  mov     r8, rax
0x18017b818  lea     rbx, off_18021C7D0; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x18017b81f  mov     rdx, rbx
0x18017b822  lea     rcx, ?c_numericSettingsNames@@3QBQEBGB; ushort const * const near * const c_numericSettingsNames
0x18017b829  call    __std_find_trivial_8
0x18017b82e  cmp     rax, rbx
0x18017b831  jz      short loc_18017B7ED
0x18017b833  xor     edx, edx; EndPtr
0x18017b835  lea     r8d, [rdx+10h]; Radix
0x18017b839  mov     rcx, rdi; String
0x18017b83c  call    cs:__imp_wcstoul
0x18017b843  nop     dword ptr [rax+rax+00h]
0x18017b848  mov     dword ptr [rbp+57h+Data], eax
0x18017b84b  call    cs:__imp__o__errno
0x18017b852  nop     dword ptr [rax+rax+00h]
0x18017b857  cmp     dword ptr [rax], 22h ; '"'
0x18017b85a  jnz     short loc_18017B87E
0x18017b85c  mov     ebx, 80070057h
0x18017b861  mov     edx, 3ACh; void *
0x18017b866  mov     r9d, ebx; char *
0x18017b869  mov     rcx, [rbp+5Fh]; this
0x18017b86d  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017b879  jmp     loc_18017B969
0x18017b87e  lea     rcx, [rbp+57h+var_A0]
0x18017b882  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b887  mov     rdx, rax; lpValueName
0x18017b88a  mov     r9d, 4; dwType
0x18017b890  mov     [rsp+100h+samDesired], r9d; cbData
0x18017b895  lea     rax, [rbp+57h+Data]
0x18017b899  mov     qword ptr [rsp+100h+dwOptions], rax; unsigned int
0x18017b89e  xor     r8d, r8d; Reserved
0x18017b8a1  mov     rcx, [rbp+57h+hKey]; hKey
0x18017b8a5  call    cs:__imp_RegSetValueExW
0x18017b8ac  nop     dword ptr [rax+rax+00h]
0x18017b8b1  test    eax, eax
0x18017b8b3  jz      loc_18017B967
0x18017b8b9  mov     edx, 3B4h; void *
0x18017b8be  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x18017b8c5  mov     r9d, eax; char *
0x18017b8c8  mov     rcx, [rbp+5Fh]; this
0x18017b8cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18017b8d1  mov     ebx, eax
0x18017b8d3  jmp     loc_18017B969
0x18017b8d8  mov     rax, qword ptr [rbp+57h+Data]
0x18017b8dc  lea     rbx, [rax+2]
0x18017b8e0  cmp     rbx, rax
0x18017b8e3  jb      short loc_18017B91E
0x18017b8e5  lea     rcx, [rbp+57h+var_A0]
0x18017b8e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b8ee  mov     rdx, rax; lpValueName
0x18017b8f1  mov     [rsp+100h+samDesired], ebx; cbData
0x18017b8f5  mov     qword ptr [rsp+100h+dwOptions], rdi; lpData
0x18017b8fa  mov     r9d, 1; dwType
0x18017b900  xor     r8d, r8d; Reserved
0x18017b903  mov     rcx, [rbp+57h+hKey]; hKey
0x18017b907  call    cs:__imp_RegSetValueExW
0x18017b90e  nop     dword ptr [rax+rax+00h]
0x18017b913  test    eax, eax
0x18017b915  jz      short loc_18017B967
0x18017b917  mov     edx, 3C6h
0x18017b91c  jmp     short loc_18017B8BE
0x18017b91e  mov     ebx, 80070216h
0x18017b923  mov     edx, 3BEh
0x18017b928  jmp     loc_18017B866
0x18017b92d  lea     rcx, [rbp+57h+var_A0]
0x18017b931  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017b936  mov     rdx, rax; lpValueName
0x18017b939  mov     rcx, [rbp+57h+hKey]; hKey
0x18017b93d  call    cs:__imp_RegDeleteValueW
0x18017b944  nop     dword ptr [rax+rax+00h]
0x18017b949  mov     edx, eax
0x18017b94b  test    eax, eax
0x18017b94d  jz      short loc_18017B967
0x18017b94f  sub     edx, 2
0x18017b952  jz      short loc_18017B967
0x18017b954  cmp     edx, 1
0x18017b957  jz      short loc_18017B967
0x18017b959  test    eax, eax
0x18017b95b  jz      short loc_18017B967
0x18017b95d  mov     edx, 3D7h
0x18017b962  jmp     loc_18017B8BE
0x18017b967  xor     ebx, ebx
0x18017b969  lea     rcx, [rbp+57h+hKey]
0x18017b96d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18017b972  nop
0x18017b973  lea     rcx, [rbp+57h+var_A0]
0x18017b977  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017b97c  nop
0x18017b97d  lea     rcx, [rbp+57h+var_80]
0x18017b981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017b986  mov     eax, ebx
0x18017b988  mov     rcx, [rbp+57h+var_20]
0x18017b98c  xor     rcx, rsp; StackCookie
0x18017b98f  call    __security_check_cookie
0x18017b994  mov     rbx, [rsp+100h+arg_10]
0x18017b99c  add     rsp, 0F0h
0x18017b9a3  pop     rdi
0x18017b9a4  pop     rsi
0x18017b9a5  pop     rbp
0x18017b9a6  retn
```
