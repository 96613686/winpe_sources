# Microsoft::Windows::Autopilot::AutoPilotStateUtils::TryReadVolatileStringValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008ca70`
- end: `0x18008ce19`
- name: `?TryReadVolatileStringValue@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z`
- size: `937`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800df648`
- `0x1800df8e4`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180077e54`
- `0x180080984`
- `0x180080bac`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x18008af70`
- `0x18008ca70`
- `0x18008d6d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008cb54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008cbec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008cb54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008cbec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cc77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cd33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cc77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008cd33`

## string_xrefs

- `0x18008cabd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008cb7e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008cc16`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008cc9e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008cd4e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008cde0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::TryReadVolatileStringValue(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  bool v7; // al
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  const WCHAR *v11; // rax
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rax
  unsigned int ValueW; // eax
  unsigned int v16; // ebx
  const WCHAR *v17; // rbx
  void *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // ebx
  int dwOptions; // [rsp+20h] [rbp-98h]
  int dwOptionsa; // [rsp+20h] [rbp-98h]
  int dwOptionsb; // [rsp+20h] [rbp-98h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-98h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-98h]
  DWORD pcbData; // [rsp+50h] [rbp-68h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v29[2]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    if ( *(_QWORD *)(a1 + 16) && *(_QWORD *)(a2 + 16) )
    {
      *(_QWORD *)(a3 + 16) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v7 = ZTPIsStateSeparationEnabled();
      v8 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings\\Volatile";
      if ( !v7 )
        v8 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings\\Volatile";
      v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 1u, 0x20019u, 0, &hKey, 0);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( (v10 & 0x80000000) == 0 )
      {
        hkey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
        v12 = RegCreateKeyExW(hKey, v11, 0, 0, 1u, 0x20019u, 0, &hkey, 0);
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        if ( (v13 & 0x80000000) == 0 )
        {
          pcbData = 0;
          v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
          ValueW = RegGetValueW(hkey, 0, v14, 2u, 0, 0, &pcbData);
          if ( ValueW - 2 <= 1 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return 0;
          }
          else if ( ValueW )
          {
            v16 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x26A,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                    (const char *)ValueW,
                    dwOptionsc);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v16;
          }
          else
          {
            v29[0] = 0;
            v29[1] = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v29[0]) = 0;
            std::wstring::resize(v29, (unsigned __int64)pcbData >> 1, 0);
            v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
            v18 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
            v19 = RegGetValueW(hkey, 0, v17, 2u, 0, v18, &pcbData);
            if ( v19 )
            {
              v20 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x26E,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                      (const char *)v19,
                      dwOptionsd);
              std::wstring::_Tidy_deallocate(v29);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return v20;
            }
            else
            {
              std::wstring::operator=(a3, v29);
              std::wstring::_Tidy_deallocate(v29);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return 0;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x260,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
            (const char *)v13,
            dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
          (const char *)v10,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
        (const char *)0x80070057LL,
        dwOptions);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)0x80004001LL,
      dwOptions);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18008ca70  push    rbx
0x18008ca72  push    rsi
0x18008ca73  push    rdi
0x18008ca74  push    r14
0x18008ca76  push    r15
0x18008ca78  sub     rsp, 90h
0x18008ca7f  mov     rax, cs:__security_cookie
0x18008ca86  xor     rax, rsp
0x18008ca89  mov     [rsp+0B8h+var_30], rax
0x18008ca91  mov     r14, r8
0x18008ca94  mov     rdi, rdx
0x18008ca97  mov     rsi, rcx
0x18008ca9a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x18008caa1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x18008caa6  xor     r15d, r15d
0x18008caa9  test    al, al
0x18008caab  jnz     short loc_18008CAD5
0x18008caad  mov     rcx, [rsp+0B8h]; this
0x18008cab5  mov     ebx, 80004001h
0x18008caba  mov     r9d, ebx; char *
0x18008cabd  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cac4  mov     edx, 245h; void *
0x18008cac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cace  mov     eax, ebx
0x18008cad0  jmp     loc_18008CDF9
0x18008cad5  cmp     [rsi+10h], r15
0x18008cad9  jz      loc_18008CDD0
0x18008cadf  cmp     [rdi+10h], r15
0x18008cae3  jz      loc_18008CDD0
0x18008cae9  mov     [r14+10h], r15
0x18008caed  mov     rcx, r14
0x18008caf0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008caf5  mov     [rax], r15w
0x18008caf9  mov     [rsp+0B8h+hKey], r15
0x18008cafe  xor     edx, edx
0x18008cb00  lea     rcx, [rsp+0B8h+hKey]
0x18008cb05  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008cb0a  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008cb0f  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Provisioning\\Auto"...
0x18008cb16  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x18008cb1d  test    al, al
0x18008cb1f  cmovz   rdx, rcx; lpSubKey
0x18008cb23  mov     [rsp+0B8h+lpdwDisposition], r15; lpdwDisposition
0x18008cb28  lea     rax, [rsp+0B8h+hKey]
0x18008cb2d  mov     [rsp+0B8h+phkResult], rax; phkResult
0x18008cb32  mov     [rsp+0B8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18008cb37  mov     [rsp+0B8h+samDesired], 20019h; samDesired
0x18008cb3f  mov     [rsp+0B8h+dwOptions], 1; int
0x18008cb47  xor     r9d, r9d; lpClass
0x18008cb4a  xor     r8d, r8d; Reserved
0x18008cb4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008cb54  call    cs:__imp_RegCreateKeyExW
0x18008cb5b  nop     dword ptr [rax+rax+00h]
0x18008cb60  mov     ebx, eax
0x18008cb62  test    eax, eax
0x18008cb64  jle     short loc_18008CB6F
0x18008cb66  movzx   ebx, ax
0x18008cb69  or      ebx, 80070000h
0x18008cb6f  test    ebx, ebx
0x18008cb71  jns     short loc_18008CBA1
0x18008cb73  mov     rcx, [rsp+0B8h]; this
0x18008cb7b  mov     r9d, ebx; char *
0x18008cb7e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cb85  mov     edx, 254h; void *
0x18008cb8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cb8f  nop
0x18008cb90  lea     rcx, [rsp+0B8h+hKey]
0x18008cb95  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cb9a  mov     eax, ebx
0x18008cb9c  jmp     loc_18008CDF9
0x18008cba1  mov     [rsp+0B8h+hkey], r15
0x18008cba6  xor     edx, edx
0x18008cba8  lea     rcx, [rsp+0B8h+hkey]
0x18008cbad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008cbb2  mov     rcx, rsi
0x18008cbb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008cbba  mov     [rsp+0B8h+lpdwDisposition], r15; lpdwDisposition
0x18008cbbf  lea     rcx, [rsp+0B8h+hkey]
0x18008cbc4  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x18008cbc9  mov     [rsp+0B8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18008cbce  mov     [rsp+0B8h+samDesired], 20019h; samDesired
0x18008cbd6  mov     [rsp+0B8h+dwOptions], 1; int
0x18008cbde  xor     r9d, r9d; lpClass
0x18008cbe1  xor     r8d, r8d; Reserved
0x18008cbe4  mov     rdx, rax; lpSubKey
0x18008cbe7  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18008cbec  call    cs:__imp_RegCreateKeyExW
0x18008cbf3  nop     dword ptr [rax+rax+00h]
0x18008cbf8  mov     ebx, eax
0x18008cbfa  test    eax, eax
0x18008cbfc  jle     short loc_18008CC07
0x18008cbfe  movzx   ebx, ax
0x18008cc01  or      ebx, 80070000h
0x18008cc07  test    ebx, ebx
0x18008cc09  jns     short loc_18008CC44
0x18008cc0b  mov     rcx, [rsp+0B8h]; this
0x18008cc13  mov     r9d, ebx; char *
0x18008cc16  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cc1d  mov     edx, 260h; void *
0x18008cc22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cc27  nop
0x18008cc28  lea     rcx, [rsp+0B8h+hkey]
0x18008cc2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cc32  nop
0x18008cc33  lea     rcx, [rsp+0B8h+hKey]
0x18008cc38  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cc3d  mov     eax, ebx
0x18008cc3f  jmp     loc_18008CDF9
0x18008cc44  mov     [rsp+0B8h+pcbData], r15d
0x18008cc49  mov     rcx, rdi
0x18008cc4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008cc51  lea     rcx, [rsp+0B8h+pcbData]
0x18008cc56  mov     [rsp+0B8h+lpSecurityAttributes], rcx; pcbData
0x18008cc5b  mov     qword ptr [rsp+0B8h+samDesired], r15; pvData
0x18008cc60  mov     qword ptr [rsp+0B8h+dwOptions], r15; unsigned int
0x18008cc65  mov     esi, 2
0x18008cc6a  mov     r9d, esi; dwFlags
0x18008cc6d  mov     r8, rax; lpValue
0x18008cc70  xor     edx, edx; lpSubKey
0x18008cc72  mov     rcx, [rsp+0B8h+hkey]; hkey
0x18008cc77  call    cs:__imp_RegGetValueW
0x18008cc7e  nop     dword ptr [rax+rax+00h]
0x18008cc83  lea     ecx, [rax-2]
0x18008cc86  cmp     ecx, 1
0x18008cc89  jbe     loc_18008CDB7
0x18008cc8f  test    eax, eax
0x18008cc91  jz      short loc_18008CCCD
0x18008cc93  mov     rcx, [rsp+0B8h]; this
0x18008cc9b  mov     r9d, eax; char *
0x18008cc9e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cca5  mov     edx, 26Ah; void *
0x18008ccaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008ccaf  mov     ebx, eax
0x18008ccb1  lea     rcx, [rsp+0B8h+hkey]
0x18008ccb6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008ccbb  nop
0x18008ccbc  lea     rcx, [rsp+0B8h+hKey]
0x18008ccc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008ccc6  mov     eax, ebx
0x18008ccc8  jmp     loc_18008CDF9
0x18008cccd  xorps   xmm0, xmm0
0x18008ccd0  movups  [rsp+0B8h+var_50], xmm0
0x18008ccd5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008ccdd  movdqu  [rsp+0B8h+var_40], xmm1
0x18008cce3  mov     word ptr [rsp+0B8h+var_50], r15w
0x18008cce9  xor     r8d, r8d
0x18008ccec  mov     edx, [rsp+0B8h+pcbData]
0x18008ccf0  shr     rdx, 1
0x18008ccf3  lea     rcx, [rsp+0B8h+var_50]
0x18008ccf8  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18008ccfd  mov     rcx, rdi
0x18008cd00  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008cd05  mov     rbx, rax
0x18008cd08  lea     rcx, [rsp+0B8h+var_50]
0x18008cd0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008cd12  lea     rcx, [rsp+0B8h+pcbData]
0x18008cd17  mov     [rsp+0B8h+lpSecurityAttributes], rcx; pcbData
0x18008cd1c  mov     qword ptr [rsp+0B8h+samDesired], rax; pvData
0x18008cd21  mov     qword ptr [rsp+0B8h+dwOptions], r15; unsigned int
0x18008cd26  mov     r9d, esi; dwFlags
0x18008cd29  mov     r8, rbx; lpValue
0x18008cd2c  xor     edx, edx; lpSubKey
0x18008cd2e  mov     rcx, [rsp+0B8h+hkey]; hkey
0x18008cd33  call    cs:__imp_RegGetValueW
0x18008cd3a  nop     dword ptr [rax+rax+00h]
0x18008cd3f  test    eax, eax
0x18008cd41  jz      short loc_18008CD85
0x18008cd43  mov     rcx, [rsp+0B8h]; this
0x18008cd4b  mov     r9d, eax; char *
0x18008cd4e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cd55  mov     edx, 26Eh; void *
0x18008cd5a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008cd5f  mov     ebx, eax
0x18008cd61  lea     rcx, [rsp+0B8h+var_50]
0x18008cd66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008cd6b  nop
0x18008cd6c  lea     rcx, [rsp+0B8h+hkey]
0x18008cd71  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cd76  nop
0x18008cd77  lea     rcx, [rsp+0B8h+hKey]
0x18008cd7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cd81  mov     eax, ebx
0x18008cd83  jmp     short loc_18008CDF9
0x18008cd85  lea     rdx, [rsp+0B8h+var_50]
0x18008cd8a  mov     rcx, r14
0x18008cd8d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008cd92  nop
0x18008cd93  lea     rcx, [rsp+0B8h+var_50]
0x18008cd98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008cd9d  nop
0x18008cd9e  lea     rcx, [rsp+0B8h+hkey]
0x18008cda3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cda8  nop
0x18008cda9  lea     rcx, [rsp+0B8h+hKey]
0x18008cdae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cdb3  xor     eax, eax
0x18008cdb5  jmp     short loc_18008CDF9
0x18008cdb7  lea     rcx, [rsp+0B8h+hkey]
0x18008cdbc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cdc1  nop
0x18008cdc2  lea     rcx, [rsp+0B8h+hKey]
0x18008cdc7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008cdcc  xor     eax, eax
0x18008cdce  jmp     short loc_18008CDF9
0x18008cdd0  mov     rcx, [rsp+0B8h]; this
0x18008cdd8  mov     ebx, 80070057h
0x18008cddd  mov     r9d, ebx; char *
0x18008cde0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008cde7  mov     edx, 247h; void *
0x18008cdec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008cdf1  mov     eax, ebx
0x18008cdf3  jmp     short loc_18008CDF9
0x18008cdf5  mov     eax, [rsp+0B8h+pcbData]
0x18008cdf9  mov     rcx, [rsp+0B8h+var_30]
0x18008ce01  xor     rcx, rsp; StackCookie
0x18008ce04  call    __security_check_cookie
0x18008ce09  add     rsp, 90h
0x18008ce10  pop     r15
0x18008ce12  pop     r14
0x18008ce14  pop     rdi
0x18008ce15  pop     rsi
0x18008ce16  pop     rbx
0x18008ce17  retn
```
