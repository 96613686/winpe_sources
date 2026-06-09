# EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotStoreSetting(ushort const *,ushort const *)

- ea: `0x180176fa0`
- end: `0x1801772ed`
- name: `?AutoPilotStoreSetting@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBG0@Z`
- size: `845`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bc804`

## callees

- `0x18000b820`
- `0x180063620`
- `0x180067a54`
- `0x18007755c`
- `0x18007ff90`
- `0x18008019c`
- `0x1800839bc`
- `0x180084208`
- `0x1800873a4`
- `0x180087c64`
- `0x180089614`
- `0x18008c244`
- `0x18008dc5c`
- `0x18008de14`
- `0x1800fb614`
- `0x180126930`
- `0x180176fa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017712a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180177147`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18017712a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180177147`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1801771a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1801771a0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801771a9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801771a9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180177027`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180177027`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180177289`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180177289`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801771fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180177259`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801771fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180177259`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801770e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801770e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
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
    v6 = (const WCHAR *)&stru_180228C20;
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
    else if ( (wchar_t **)_std_find_trivial_8(&c_numericSettingsNames, off_1802167D0, v14) == off_1802167D0 )
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
0x180176fa0  mov     [rsp-8+arg_10], rbx
0x180176fa5  push    rbp
0x180176fa6  push    rsi
0x180176fa7  push    rdi
0x180176fa8  lea     rbp, [rsp-47h]
0x180176fad  sub     rsp, 0F0h
0x180176fb4  mov     rax, cs:__security_cookie
0x180176fbb  xor     rax, rsp
0x180176fbe  mov     [rbp+57h+var_20], rax
0x180176fc2  mov     rdi, rdx
0x180176fc5  mov     rbx, rcx
0x180176fc8  test    rcx, rcx
0x180176fcb  jnz     short loc_180176FEF
0x180176fcd  mov     rcx, [rbp+5Fh]; this
0x180176fd1  mov     ebx, 80070057h
0x180176fd6  mov     r9d, ebx; char *
0x180176fd9  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180176fe0  mov     edx, 375h; void *
0x180176fe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180176fea  jmp     loc_1801772CC
0x180176fef  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x180176ff4  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x180176ffb  lea     rdx, stru_180228C20
0x180177002  test    al, al
0x180177004  cmovz   rdx, rcx
0x180177008  lea     rcx, [rbp+57h+var_80]
0x18017700c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180177011  nop
0x180177012  mov     rdx, rbx
0x180177015  lea     rcx, [rbp+57h+var_A0]
0x180177019  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18017701e  nop
0x18017701f  mov     edx, 2Fh ; '/'; Ch
0x180177024  mov     rcx, rbx; Str
0x180177027  call    cs:__imp_wcschr
0x18017702d  mov     rsi, rax
0x180177030  test    rax, rax
0x180177033  jz      short loc_180177091
0x180177035  mov     r9, rax
0x180177038  sub     r9, rbx
0x18017703b  sar     r9, 1
0x18017703e  xor     r8d, r8d
0x180177041  lea     rdx, [rbp+57h+var_60]
0x180177045  lea     rcx, [rbp+57h+var_A0]
0x180177049  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18017704e  nop
0x18017704f  lea     r8, [rbp+57h+var_60]
0x180177053  lea     rdx, SubBlock; "\\"
0x18017705a  lea     rcx, [rbp+57h+var_40]
0x18017705e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180177063  nop
0x180177064  mov     rdx, rax
0x180177067  lea     rcx, [rbp+57h+var_80]
0x18017706b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180177070  nop
0x180177071  lea     rcx, [rbp+57h+var_40]
0x180177075  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18017707a  lea     rdx, [rsi+2]
0x18017707e  lea     rcx, [rbp+57h+var_A0]
0x180177082  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180177087  nop
0x180177088  lea     rcx, [rbp+57h+var_60]
0x18017708c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180177091  mov     [rbp+57h+hKey], 0
0x180177099  xor     edx, edx
0x18017709b  lea     rcx, [rbp+57h+hKey]
0x18017709f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801770a4  lea     rcx, [rbp+57h+var_80]
0x1801770a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801770ad  mov     rdx, rax; lpSubKey
0x1801770b0  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x1801770b9  lea     rax, [rbp+57h+hKey]
0x1801770bd  mov     [rsp+100h+phkResult], rax; phkResult
0x1801770c2  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801770cb  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x1801770d3  mov     [rsp+100h+dwOptions], 0; int
0x1801770db  xor     r9d, r9d; lpClass
0x1801770de  xor     r8d, r8d; Reserved
0x1801770e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801770e8  call    cs:__imp_RegCreateKeyExW
0x1801770ee  test    eax, eax
0x1801770f0  jz      short loc_1801770FC
0x1801770f2  mov     edx, 390h
0x1801770f7  jmp     loc_180177210
0x1801770fc  test    rdi, rdi
0x1801770ff  jz      loc_180177279
0x180177105  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppRebootFix> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::GetImpl(void)'::`2'::impl
0x18017710c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDppRebootFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDppRebootFix>::__private_IsEnabled(void)
0x180177111  mov     bl, al
0x180177113  lea     rcx, [rbp+57h+var_A0]
0x180177117  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017711c  test    bl, bl
0x18017711e  jz      short loc_180177179
0x180177120  lea     rdx, ?c_devicePreparationPageErrorPhaseSettingName@@3QBGB; "PageErrorPhase"
0x180177127  mov     rcx, rax
0x18017712a  call    cs:__imp__o__wcsicmp
0x180177130  test    eax, eax
0x180177132  jz      short loc_180177197
0x180177134  lea     rcx, [rbp+57h+var_A0]
0x180177138  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18017713d  mov     rcx, rax
0x180177140  lea     rdx, ?c_devicePreparationPageErrorCodeSettingName@@3QBGB; "PageErrorCode"
0x180177147  call    cs:__imp__o__wcsicmp
0x18017714d  test    eax, eax
0x18017714f  jz      short loc_180177197
0x180177151  mov     qword ptr [rbp+57h+Data], 0
0x180177159  lea     r8, [rbp+57h+Data]; unsigned __int64 *
0x18017715d  mov     rcx, rdi; unsigned __int16 *
0x180177160  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180177165  mov     ebx, eax
0x180177167  test    eax, eax
0x180177169  jns     loc_18017722A
0x18017716f  mov     r9d, eax
0x180177172  mov     edx, 3BBh
0x180177177  jmp     short loc_1801771C1
0x180177179  mov     r8, rax
0x18017717c  lea     rbx, off_1802167D0; "AUTOPILOT_OOBE_SETTINGS_INVALID"
0x180177183  mov     rdx, rbx
0x180177186  lea     rcx, ?c_numericSettingsNames@@3QBQEBGB; ushort const * const near * const c_numericSettingsNames
0x18017718d  call    __std_find_trivial_8
0x180177192  cmp     rax, rbx
0x180177195  jz      short loc_180177151
0x180177197  xor     edx, edx; EndPtr
0x180177199  lea     r8d, [rdx+10h]; Radix
0x18017719d  mov     rcx, rdi; String
0x1801771a0  call    cs:__imp_wcstoul
0x1801771a6  mov     dword ptr [rbp+57h+Data], eax
0x1801771a9  call    cs:__imp__o__errno
0x1801771af  cmp     dword ptr [rax], 22h ; '"'
0x1801771b2  jnz     short loc_1801771D6
0x1801771b4  mov     ebx, 80070057h
0x1801771b9  mov     edx, 3ACh; void *
0x1801771be  mov     r9d, ebx; char *
0x1801771c1  mov     rcx, [rbp+5Fh]; this
0x1801771c5  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801771cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801771d1  jmp     loc_1801772AF
0x1801771d6  lea     rcx, [rbp+57h+var_A0]
0x1801771da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801771df  mov     rdx, rax; lpValueName
0x1801771e2  mov     r9d, 4; dwType
0x1801771e8  mov     [rsp+100h+samDesired], r9d; cbData
0x1801771ed  lea     rax, [rbp+57h+Data]
0x1801771f1  mov     qword ptr [rsp+100h+dwOptions], rax; unsigned int
0x1801771f6  xor     r8d, r8d; Reserved
0x1801771f9  mov     rcx, [rbp+57h+hKey]; hKey
0x1801771fd  call    cs:__imp_RegSetValueExW
0x180177203  test    eax, eax
0x180177205  jz      loc_1801772AD
0x18017720b  mov     edx, 3B4h; void *
0x180177210  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\moderndeployment\\au"...
0x180177217  mov     r9d, eax; char *
0x18017721a  mov     rcx, [rbp+5Fh]; this
0x18017721e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180177223  mov     ebx, eax
0x180177225  jmp     loc_1801772AF
0x18017722a  mov     rax, qword ptr [rbp+57h+Data]
0x18017722e  lea     rbx, [rax+2]
0x180177232  cmp     rbx, rax
0x180177235  jb      short loc_18017726A
0x180177237  lea     rcx, [rbp+57h+var_A0]
0x18017723b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180177240  mov     rdx, rax; lpValueName
0x180177243  mov     [rsp+100h+samDesired], ebx; cbData
0x180177247  mov     qword ptr [rsp+100h+dwOptions], rdi; lpData
0x18017724c  mov     r9d, 1; dwType
0x180177252  xor     r8d, r8d; Reserved
0x180177255  mov     rcx, [rbp+57h+hKey]; hKey
0x180177259  call    cs:__imp_RegSetValueExW
0x18017725f  test    eax, eax
0x180177261  jz      short loc_1801772AD
0x180177263  mov     edx, 3C6h
0x180177268  jmp     short loc_180177210
0x18017726a  mov     ebx, 80070216h
0x18017726f  mov     edx, 3BEh
0x180177274  jmp     loc_1801771BE
0x180177279  lea     rcx, [rbp+57h+var_A0]
0x18017727d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180177282  mov     rdx, rax; lpValueName
0x180177285  mov     rcx, [rbp+57h+hKey]; hKey
0x180177289  call    cs:__imp_RegDeleteValueW
0x18017728f  mov     edx, eax
0x180177291  test    eax, eax
0x180177293  jz      short loc_1801772AD
0x180177295  sub     edx, 2
0x180177298  jz      short loc_1801772AD
0x18017729a  cmp     edx, 1
0x18017729d  jz      short loc_1801772AD
0x18017729f  test    eax, eax
0x1801772a1  jz      short loc_1801772AD
0x1801772a3  mov     edx, 3D7h
0x1801772a8  jmp     loc_180177210
0x1801772ad  xor     ebx, ebx
0x1801772af  lea     rcx, [rbp+57h+hKey]
0x1801772b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801772b8  nop
0x1801772b9  lea     rcx, [rbp+57h+var_A0]
0x1801772bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801772c2  nop
0x1801772c3  lea     rcx, [rbp+57h+var_80]
0x1801772c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801772cc  mov     eax, ebx
0x1801772ce  mov     rcx, [rbp+57h+var_20]
0x1801772d2  xor     rcx, rsp; StackCookie
0x1801772d5  call    __security_check_cookie
0x1801772da  mov     rbx, [rsp+100h+arg_10]
0x1801772e2  add     rsp, 0F0h
0x1801772e9  pop     rdi
0x1801772ea  pop     rsi
0x1801772eb  pop     rbp
0x1801772ec  retn
```
