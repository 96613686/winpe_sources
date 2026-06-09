# Microsoft::Windows::Autopilot::AutoPilotStateUtils::TryReadVolatileStringValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18008ba8c`
- end: `0x18008be1d`
- name: `?TryReadVolatileStringValue@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z`
- size: `913`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dce60`
- `0x1800dd0f4`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x1800775c4`
- `0x18007ff90`
- `0x18008019c`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x18008a0a8`
- `0x18008ba8c`
- `0x18008c630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008bb70`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008bc02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008bb70`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008bc02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bc87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bd3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bc87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bd3d`

## string_xrefs

- `0x18008bad9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bb94`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bc26`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bca8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bd52`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008bde4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18008ba8c  push    rbx
0x18008ba8e  push    rsi
0x18008ba8f  push    rdi
0x18008ba90  push    r14
0x18008ba92  push    r15
0x18008ba94  sub     rsp, 90h
0x18008ba9b  mov     rax, cs:__security_cookie
0x18008baa2  xor     rax, rsp
0x18008baa5  mov     [rsp+0B8h+var_30], rax
0x18008baad  mov     r14, r8
0x18008bab0  mov     rdi, rdx
0x18008bab3  mov     rsi, rcx
0x18008bab6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x18008babd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x18008bac2  xor     r15d, r15d
0x18008bac5  test    al, al
0x18008bac7  jnz     short loc_18008BAF1
0x18008bac9  mov     rcx, [rsp+0B8h]; this
0x18008bad1  mov     ebx, 80004001h
0x18008bad6  mov     r9d, ebx; char *
0x18008bad9  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bae0  mov     edx, 245h; void *
0x18008bae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008baea  mov     eax, ebx
0x18008baec  jmp     loc_18008BDFD
0x18008baf1  cmp     [rsi+10h], r15
0x18008baf5  jz      loc_18008BDD4
0x18008bafb  cmp     [rdi+10h], r15
0x18008baff  jz      loc_18008BDD4
0x18008bb05  mov     [r14+10h], r15
0x18008bb09  mov     rcx, r14
0x18008bb0c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008bb11  mov     [rax], r15w
0x18008bb15  mov     [rsp+0B8h+hKey], r15
0x18008bb1a  xor     edx, edx
0x18008bb1c  lea     rcx, [rsp+0B8h+hKey]
0x18008bb21  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008bb26  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008bb2b  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Provisioning\\Auto"...
0x18008bb32  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x18008bb39  test    al, al
0x18008bb3b  cmovz   rdx, rcx; lpSubKey
0x18008bb3f  mov     [rsp+0B8h+lpdwDisposition], r15; lpdwDisposition
0x18008bb44  lea     rax, [rsp+0B8h+hKey]
0x18008bb49  mov     [rsp+0B8h+phkResult], rax; phkResult
0x18008bb4e  mov     [rsp+0B8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18008bb53  mov     [rsp+0B8h+samDesired], 20019h; samDesired
0x18008bb5b  mov     [rsp+0B8h+dwOptions], 1; int
0x18008bb63  xor     r9d, r9d; lpClass
0x18008bb66  xor     r8d, r8d; Reserved
0x18008bb69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008bb70  call    cs:__imp_RegCreateKeyExW
0x18008bb76  mov     ebx, eax
0x18008bb78  test    eax, eax
0x18008bb7a  jle     short loc_18008BB85
0x18008bb7c  movzx   ebx, ax
0x18008bb7f  or      ebx, 80070000h
0x18008bb85  test    ebx, ebx
0x18008bb87  jns     short loc_18008BBB7
0x18008bb89  mov     rcx, [rsp+0B8h]; this
0x18008bb91  mov     r9d, ebx; char *
0x18008bb94  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bb9b  mov     edx, 254h; void *
0x18008bba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bba5  nop
0x18008bba6  lea     rcx, [rsp+0B8h+hKey]
0x18008bbab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bbb0  mov     eax, ebx
0x18008bbb2  jmp     loc_18008BDFD
0x18008bbb7  mov     [rsp+0B8h+hkey], r15
0x18008bbbc  xor     edx, edx
0x18008bbbe  lea     rcx, [rsp+0B8h+hkey]
0x18008bbc3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008bbc8  mov     rcx, rsi
0x18008bbcb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008bbd0  mov     [rsp+0B8h+lpdwDisposition], r15; lpdwDisposition
0x18008bbd5  lea     rcx, [rsp+0B8h+hkey]
0x18008bbda  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x18008bbdf  mov     [rsp+0B8h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18008bbe4  mov     [rsp+0B8h+samDesired], 20019h; samDesired
0x18008bbec  mov     [rsp+0B8h+dwOptions], 1; int
0x18008bbf4  xor     r9d, r9d; lpClass
0x18008bbf7  xor     r8d, r8d; Reserved
0x18008bbfa  mov     rdx, rax; lpSubKey
0x18008bbfd  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18008bc02  call    cs:__imp_RegCreateKeyExW
0x18008bc08  mov     ebx, eax
0x18008bc0a  test    eax, eax
0x18008bc0c  jle     short loc_18008BC17
0x18008bc0e  movzx   ebx, ax
0x18008bc11  or      ebx, 80070000h
0x18008bc17  test    ebx, ebx
0x18008bc19  jns     short loc_18008BC54
0x18008bc1b  mov     rcx, [rsp+0B8h]; this
0x18008bc23  mov     r9d, ebx; char *
0x18008bc26  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bc2d  mov     edx, 260h; void *
0x18008bc32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bc37  nop
0x18008bc38  lea     rcx, [rsp+0B8h+hkey]
0x18008bc3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bc42  nop
0x18008bc43  lea     rcx, [rsp+0B8h+hKey]
0x18008bc48  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bc4d  mov     eax, ebx
0x18008bc4f  jmp     loc_18008BDFD
0x18008bc54  mov     [rsp+0B8h+pcbData], r15d
0x18008bc59  mov     rcx, rdi
0x18008bc5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008bc61  lea     rcx, [rsp+0B8h+pcbData]
0x18008bc66  mov     [rsp+0B8h+lpSecurityAttributes], rcx; pcbData
0x18008bc6b  mov     qword ptr [rsp+0B8h+samDesired], r15; pvData
0x18008bc70  mov     qword ptr [rsp+0B8h+dwOptions], r15; unsigned int
0x18008bc75  mov     esi, 2
0x18008bc7a  mov     r9d, esi; dwFlags
0x18008bc7d  mov     r8, rax; lpValue
0x18008bc80  xor     edx, edx; lpSubKey
0x18008bc82  mov     rcx, [rsp+0B8h+hkey]; hkey
0x18008bc87  call    cs:__imp_RegGetValueW
0x18008bc8d  lea     ecx, [rax-2]
0x18008bc90  cmp     ecx, 1
0x18008bc93  jbe     loc_18008BDBB
0x18008bc99  test    eax, eax
0x18008bc9b  jz      short loc_18008BCD7
0x18008bc9d  mov     rcx, [rsp+0B8h]; this
0x18008bca5  mov     r9d, eax; char *
0x18008bca8  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bcaf  mov     edx, 26Ah; void *
0x18008bcb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008bcb9  mov     ebx, eax
0x18008bcbb  lea     rcx, [rsp+0B8h+hkey]
0x18008bcc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bcc5  nop
0x18008bcc6  lea     rcx, [rsp+0B8h+hKey]
0x18008bccb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bcd0  mov     eax, ebx
0x18008bcd2  jmp     loc_18008BDFD
0x18008bcd7  xorps   xmm0, xmm0
0x18008bcda  movups  [rsp+0B8h+var_50], xmm0
0x18008bcdf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008bce7  movdqu  [rsp+0B8h+var_40], xmm1
0x18008bced  mov     word ptr [rsp+0B8h+var_50], r15w
0x18008bcf3  xor     r8d, r8d
0x18008bcf6  mov     edx, [rsp+0B8h+pcbData]
0x18008bcfa  shr     rdx, 1
0x18008bcfd  lea     rcx, [rsp+0B8h+var_50]
0x18008bd02  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18008bd07  mov     rcx, rdi
0x18008bd0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008bd0f  mov     rbx, rax
0x18008bd12  lea     rcx, [rsp+0B8h+var_50]
0x18008bd17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008bd1c  lea     rcx, [rsp+0B8h+pcbData]
0x18008bd21  mov     [rsp+0B8h+lpSecurityAttributes], rcx; pcbData
0x18008bd26  mov     qword ptr [rsp+0B8h+samDesired], rax; pvData
0x18008bd2b  mov     qword ptr [rsp+0B8h+dwOptions], r15; unsigned int
0x18008bd30  mov     r9d, esi; dwFlags
0x18008bd33  mov     r8, rbx; lpValue
0x18008bd36  xor     edx, edx; lpSubKey
0x18008bd38  mov     rcx, [rsp+0B8h+hkey]; hkey
0x18008bd3d  call    cs:__imp_RegGetValueW
0x18008bd43  test    eax, eax
0x18008bd45  jz      short loc_18008BD89
0x18008bd47  mov     rcx, [rsp+0B8h]; this
0x18008bd4f  mov     r9d, eax; char *
0x18008bd52  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bd59  mov     edx, 26Eh; void *
0x18008bd5e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008bd63  mov     ebx, eax
0x18008bd65  lea     rcx, [rsp+0B8h+var_50]
0x18008bd6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008bd6f  nop
0x18008bd70  lea     rcx, [rsp+0B8h+hkey]
0x18008bd75  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bd7a  nop
0x18008bd7b  lea     rcx, [rsp+0B8h+hKey]
0x18008bd80  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bd85  mov     eax, ebx
0x18008bd87  jmp     short loc_18008BDFD
0x18008bd89  lea     rdx, [rsp+0B8h+var_50]
0x18008bd8e  mov     rcx, r14
0x18008bd91  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008bd96  nop
0x18008bd97  lea     rcx, [rsp+0B8h+var_50]
0x18008bd9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008bda1  nop
0x18008bda2  lea     rcx, [rsp+0B8h+hkey]
0x18008bda7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bdac  nop
0x18008bdad  lea     rcx, [rsp+0B8h+hKey]
0x18008bdb2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bdb7  xor     eax, eax
0x18008bdb9  jmp     short loc_18008BDFD
0x18008bdbb  lea     rcx, [rsp+0B8h+hkey]
0x18008bdc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bdc5  nop
0x18008bdc6  lea     rcx, [rsp+0B8h+hKey]
0x18008bdcb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008bdd0  xor     eax, eax
0x18008bdd2  jmp     short loc_18008BDFD
0x18008bdd4  mov     rcx, [rsp+0B8h]; this
0x18008bddc  mov     ebx, 80070057h
0x18008bde1  mov     r9d, ebx; char *
0x18008bde4  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008bdeb  mov     edx, 247h; void *
0x18008bdf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008bdf5  mov     eax, ebx
0x18008bdf7  jmp     short loc_18008BDFD
0x18008bdf9  mov     eax, [rsp+0B8h+pcbData]
0x18008bdfd  mov     rcx, [rsp+0B8h+var_30]
0x18008be05  xor     rcx, rsp; StackCookie
0x18008be08  call    __security_check_cookie
0x18008be0d  add     rsp, 90h
0x18008be14  pop     r15
0x18008be16  pop     r14
0x18008be18  pop     rdi
0x18008be19  pop     rsi
0x18008be1a  pop     rbx
0x18008be1b  retn
```
