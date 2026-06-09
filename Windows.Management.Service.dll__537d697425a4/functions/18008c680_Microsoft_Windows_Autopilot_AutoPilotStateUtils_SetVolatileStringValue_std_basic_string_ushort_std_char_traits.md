# Microsoft::Windows::Autopilot::AutoPilotStateUtils::SetVolatileStringValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18008c680`
- end: `0x18008c8b0`
- name: `?SetVolatileStringValue@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `560`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800df648`
- `0x1800df8e4`

## callees

- `0x180067e54`
- `0x180077e54`
- `0x180080984`
- `0x180080bac`
- `0x180084d80`
- `0x18008a454`
- `0x18008c680`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c83f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c83f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008c737`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008c7c6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008c737`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008c7c6`

## string_xrefs

- `0x18008c75d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008c7ea`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`
- `0x18008c888`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18008c680  mov     [rsp-18h+arg_0], rbx
0x18008c685  mov     [rsp-18h+arg_8], rsi
0x18008c68a  push    rbp
0x18008c68b  push    rdi
0x18008c68c  push    r14
0x18008c68e  mov     rbp, rsp
0x18008c691  sub     rsp, 60h
0x18008c695  mov     r14, r8
0x18008c698  mov     rsi, rdx
0x18008c69b  mov     rdi, rcx
0x18008c69e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x18008c6a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x18008c6aa  test    al, al
0x18008c6ac  jnz     short loc_18008C6BD
0x18008c6ae  mov     ebx, 80004001h
0x18008c6b3  mov     edx, 277h
0x18008c6b8  jmp     loc_18008C885
0x18008c6bd  cmp     qword ptr [rdi+10h], 0
0x18008c6c2  jz      loc_18008C87B
0x18008c6c8  cmp     qword ptr [rsi+10h], 0
0x18008c6cd  jz      loc_18008C87B
0x18008c6d3  mov     [rbp+hKey], 0
0x18008c6db  xor     edx, edx
0x18008c6dd  lea     rcx, [rbp+hKey]
0x18008c6e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008c6e6  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008c6eb  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Provisioning\\Auto"...
0x18008c6f2  lea     rdx, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x18008c6f9  test    al, al
0x18008c6fb  cmovz   rdx, rcx; lpSubKey
0x18008c6ff  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008c708  lea     rax, [rbp+hKey]
0x18008c70c  mov     [rsp+60h+phkResult], rax; phkResult
0x18008c711  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008c71a  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18008c722  mov     [rsp+60h+dwOptions], 1; int
0x18008c72a  xor     r9d, r9d; lpClass
0x18008c72d  xor     r8d, r8d; Reserved
0x18008c730  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008c737  call    cs:__imp_RegCreateKeyExW
0x18008c73e  nop     dword ptr [rax+rax+00h]
0x18008c743  mov     ebx, eax
0x18008c745  test    eax, eax
0x18008c747  jle     short loc_18008C752
0x18008c749  movzx   ebx, ax
0x18008c74c  or      ebx, 80070000h
0x18008c752  test    ebx, ebx
0x18008c754  jns     short loc_18008C773
0x18008c756  mov     rcx, [rbp+18h]; this
0x18008c75a  mov     r9d, ebx; char *
0x18008c75d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c764  mov     edx, 284h; void *
0x18008c769  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c76e  jmp     loc_18008C870
0x18008c773  mov     [rbp+arg_18], 0
0x18008c77b  xor     edx, edx
0x18008c77d  lea     rcx, [rbp+arg_18]
0x18008c781  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008c786  mov     rcx, rdi
0x18008c789  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008c78e  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18008c797  lea     rcx, [rbp+arg_18]
0x18008c79b  mov     [rsp+60h+phkResult], rcx; phkResult
0x18008c7a0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008c7a9  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18008c7b1  mov     [rsp+60h+dwOptions], 1; int
0x18008c7b9  xor     r9d, r9d; lpClass
0x18008c7bc  xor     r8d, r8d; Reserved
0x18008c7bf  mov     rdx, rax; lpSubKey
0x18008c7c2  mov     rcx, [rbp+hKey]; hKey
0x18008c7c6  call    cs:__imp_RegCreateKeyExW
0x18008c7cd  nop     dword ptr [rax+rax+00h]
0x18008c7d2  mov     ebx, eax
0x18008c7d4  test    eax, eax
0x18008c7d6  jle     short loc_18008C7E1
0x18008c7d8  movzx   ebx, ax
0x18008c7db  or      ebx, 80070000h
0x18008c7e1  test    ebx, ebx
0x18008c7e3  jns     short loc_18008C808
0x18008c7e5  mov     edx, 290h; void *
0x18008c7ea  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c7f1  mov     r9d, ebx; char *
0x18008c7f4  mov     rcx, [rbp+18h]; this
0x18008c7f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c7fd  lea     rcx, [rbp+arg_18]
0x18008c801  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c806  jmp     short loc_18008C870
0x18008c808  mov     rcx, r14
0x18008c80b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008c810  mov     rbx, rax
0x18008c813  mov     rcx, rsi
0x18008c816  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008c81b  mov     edx, [r14+10h]
0x18008c81f  lea     edx, ds:2[rdx*2]
0x18008c826  mov     [rsp+60h+samDesired], edx; cbData
0x18008c82a  mov     qword ptr [rsp+60h+dwOptions], rbx; lpData
0x18008c82f  mov     r9d, 1; dwType
0x18008c835  xor     r8d, r8d; Reserved
0x18008c838  mov     rdx, rax; lpValueName
0x18008c83b  mov     rcx, [rbp+arg_18]; hKey
0x18008c83f  call    cs:__imp_RegSetValueExW
0x18008c846  nop     dword ptr [rax+rax+00h]
0x18008c84b  mov     ebx, eax
0x18008c84d  test    eax, eax
0x18008c84f  jle     short loc_18008C85A
0x18008c851  movzx   ebx, ax
0x18008c854  or      ebx, 80070000h
0x18008c85a  test    ebx, ebx
0x18008c85c  jns     short loc_18008C865
0x18008c85e  mov     edx, 299h
0x18008c863  jmp     short loc_18008C7EA
0x18008c865  lea     rcx, [rbp+arg_18]
0x18008c869  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c86e  xor     ebx, ebx
0x18008c870  lea     rcx, [rbp+hKey]
0x18008c874  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c879  jmp     short loc_18008C898
0x18008c87b  mov     ebx, 80070057h
0x18008c880  mov     edx, 278h; void *
0x18008c885  mov     r9d, ebx; char *
0x18008c888  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008c88f  mov     rcx, [rbp+18h]; this
0x18008c893  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c898  mov     eax, ebx
0x18008c89a  lea     r11, [rsp+60h+var_s0]
0x18008c89f  mov     rbx, [r11+20h]
0x18008c8a3  mov     rsi, [r11+28h]
0x18008c8a7  mov     rsp, r11
0x18008c8aa  pop     r14
0x18008c8ac  pop     rdi
0x18008c8ad  pop     rbp
0x18008c8ae  retn
```
