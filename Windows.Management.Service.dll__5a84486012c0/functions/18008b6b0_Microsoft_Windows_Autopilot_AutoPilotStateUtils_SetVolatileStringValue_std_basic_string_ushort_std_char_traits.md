# Microsoft::Windows::Autopilot::AutoPilotStateUtils::SetVolatileStringValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18008b6b0`
- end: `0x18008b8cd`
- name: `?SetVolatileStringValue@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dce60`
- `0x1800dd0f4`

## callees

- `0x180067a54`
- `0x1800775c4`
- `0x18007ff90`
- `0x18008019c`
- `0x180084208`
- `0x180089614`
- `0x18008b6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008b863`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008b863`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b767`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b7f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b767`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b7f0`

## string_xrefs

- `0x18008b787`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b80e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008b8a6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::SetVolatileStringValue(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  signed int v6; // ebx
  __int64 v7; // rdx
  bool v8; // al
  const WCHAR *v9; // rdx
  LSTATUS Key; // eax
  const WCHAR *v11; // rax
  LSTATUS v12; // eax
  __int64 v13; // rdx
  const BYTE *v14; // rbx
  const WCHAR *v15; // rax
  LSTATUS v16; // eax
  int dwOptions; // [rsp+20h] [rbp-40h]
  int dwOptionsa; // [rsp+20h] [rbp-40h]
  int dwOptionsb; // [rsp+20h] [rbp-40h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    v6 = -2147467263;
    v7 = 631;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v6,
      dwOptions);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)(a1 + 16) || !*(_QWORD *)(a2 + 16) )
  {
    v6 = -2147024809;
    v7 = 632;
    goto LABEL_23;
  }
  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v8 = ZTPIsStateSeparationEnabled();
  v9 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings\\Volatile";
  if ( !v8 )
    v9 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings\\Volatile";
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 1u, 0x2001Fu, 0, hKey, 0);
  v6 = Key;
  if ( Key > 0 )
    v6 = (unsigned __int16)Key | 0x80070000;
  if ( v6 >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v12 = RegCreateKeyExW(hKey[0], v11, 0, 0, 1u, 0x2001Fu, 0, &phkResult, 0);
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    if ( v6 >= 0 )
    {
      v14 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v16 = RegSetValueExW(phkResult, v15, 0, 1u, v14, 2 * *(_DWORD *)(a3 + 16) + 2);
      v6 = v16;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( v6 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v6 = 0;
        goto LABEL_21;
      }
      v13 = 665;
    }
    else
    {
      v13 = 656;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v6,
      dwOptionsb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x284,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
      (const char *)(unsigned int)v6,
      dwOptionsa);
  }
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008b6b0  mov     [rsp-18h+arg_0], rbx
0x18008b6b5  mov     [rsp-18h+arg_8], rsi
0x18008b6ba  push    rbp
0x18008b6bb  push    rdi
0x18008b6bc  push    r14
0x18008b6be  mov     rbp, rsp
0x18008b6c1  sub     rsp, 60h
0x18008b6c5  mov     r14, r8
0x18008b6c8  mov     rsi, rdx
0x18008b6cb  mov     rdi, rcx
0x18008b6ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x18008b6d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x18008b6da  test    al, al
0x18008b6dc  jnz     short loc_18008B6ED
0x18008b6de  mov     ebx, 80004001h
0x18008b6e3  mov     edx, 277h
0x18008b6e8  jmp     loc_18008B8A3
0x18008b6ed  cmp     qword ptr [rdi+10h], 0
0x18008b6f2  jz      loc_18008B899
0x18008b6f8  cmp     qword ptr [rsi+10h], 0
0x18008b6fd  jz      loc_18008B899
0x18008b703  mov     [rbp+hKey], 0
0x18008b70b  xor     edx, edx
0x18008b70d  lea     rcx, [rbp+hKey]
0x18008b711  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008b716  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008b71b  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Provisioning\\Auto"...
0x18008b722  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x18008b729  test    al, al
0x18008b72b  cmovz   rdx, rcx; lpSubKey
0x18008b72f  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008b738  lea     rax, [rbp+hKey]
0x18008b73c  mov     [rsp+60h+phkResult], rax; phkResult
0x18008b741  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008b74a  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18008b752  mov     [rsp+60h+dwOptions], 1; int
0x18008b75a  xor     r9d, r9d; lpClass
0x18008b75d  xor     r8d, r8d; Reserved
0x18008b760  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008b767  call    cs:__imp_RegCreateKeyExW
0x18008b76d  mov     ebx, eax
0x18008b76f  test    eax, eax
0x18008b771  jle     short loc_18008B77C
0x18008b773  movzx   ebx, ax
0x18008b776  or      ebx, 80070000h
0x18008b77c  test    ebx, ebx
0x18008b77e  jns     short loc_18008B79D
0x18008b780  mov     rcx, [rbp+18h]; this
0x18008b784  mov     r9d, ebx; char *
0x18008b787  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b78e  mov     edx, 284h; void *
0x18008b793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b798  jmp     loc_18008B88E
0x18008b79d  mov     [rbp+arg_18], 0
0x18008b7a5  xor     edx, edx
0x18008b7a7  lea     rcx, [rbp+arg_18]
0x18008b7ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008b7b0  mov     rcx, rdi
0x18008b7b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008b7b8  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008b7c1  lea     rcx, [rbp+arg_18]
0x18008b7c5  mov     [rsp+60h+phkResult], rcx; phkResult
0x18008b7ca  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008b7d3  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18008b7db  mov     [rsp+60h+dwOptions], 1; int
0x18008b7e3  xor     r9d, r9d; lpClass
0x18008b7e6  xor     r8d, r8d; Reserved
0x18008b7e9  mov     rdx, rax; lpSubKey
0x18008b7ec  mov     rcx, [rbp+hKey]; hKey
0x18008b7f0  call    cs:__imp_RegCreateKeyExW
0x18008b7f6  mov     ebx, eax
0x18008b7f8  test    eax, eax
0x18008b7fa  jle     short loc_18008B805
0x18008b7fc  movzx   ebx, ax
0x18008b7ff  or      ebx, 80070000h
0x18008b805  test    ebx, ebx
0x18008b807  jns     short loc_18008B82C
0x18008b809  mov     edx, 290h; void *
0x18008b80e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b815  mov     r9d, ebx; char *
0x18008b818  mov     rcx, [rbp+18h]; this
0x18008b81c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b821  lea     rcx, [rbp+arg_18]
0x18008b825  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b82a  jmp     short loc_18008B88E
0x18008b82c  mov     rcx, r14
0x18008b82f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008b834  mov     rbx, rax
0x18008b837  mov     rcx, rsi
0x18008b83a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008b83f  mov     edx, [r14+10h]
0x18008b843  lea     edx, ds:2[rdx*2]
0x18008b84a  mov     [rsp+60h+samDesired], edx; cbData
0x18008b84e  mov     qword ptr [rsp+60h+dwOptions], rbx; lpData
0x18008b853  mov     r9d, 1; dwType
0x18008b859  xor     r8d, r8d; Reserved
0x18008b85c  mov     rdx, rax; lpValueName
0x18008b85f  mov     rcx, [rbp+arg_18]; hKey
0x18008b863  call    cs:__imp_RegSetValueExW
0x18008b869  mov     ebx, eax
0x18008b86b  test    eax, eax
0x18008b86d  jle     short loc_18008B878
0x18008b86f  movzx   ebx, ax
0x18008b872  or      ebx, 80070000h
0x18008b878  test    ebx, ebx
0x18008b87a  jns     short loc_18008B883
0x18008b87c  mov     edx, 299h
0x18008b881  jmp     short loc_18008B80E
0x18008b883  lea     rcx, [rbp+arg_18]
0x18008b887  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b88c  xor     ebx, ebx
0x18008b88e  lea     rcx, [rbp+hKey]
0x18008b892  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008b897  jmp     short loc_18008B8B6
0x18008b899  mov     ebx, 80070057h
0x18008b89e  mov     edx, 278h; void *
0x18008b8a3  mov     r9d, ebx; char *
0x18008b8a6  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008b8ad  mov     rcx, [rbp+18h]; this
0x18008b8b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b8b6  mov     eax, ebx
0x18008b8b8  lea     r11, [rsp+60h+var_s0]
0x18008b8bd  mov     rbx, [r11+20h]
0x18008b8c1  mov     rsi, [r11+28h]
0x18008b8c5  mov     rsp, r11
0x18008b8c8  pop     r14
0x18008b8ca  pop     rdi
0x18008b8cb  pop     rbp
0x18008b8cc  retn
```
