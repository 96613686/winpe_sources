# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::WriteDefaultOrderTokenValueNameToRegistry(void)

- ea: `0x1801946ec`
- end: `0x180194a52`
- name: `?WriteDefaultOrderTokenValueNameToRegistry@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJXZ`
- size: `870`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180191f4c`

## callees

- `0x18000b820`
- `0x18007755c`
- `0x18007ff90`
- `0x18008019c`
- `0x1800801fc`
- `0x1800839bc`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x18008a0a8`
- `0x18008dc5c`
- `0x18008dc94`
- `0x180174928`
- `0x1801946ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801948d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180194971`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019499d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801948d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180194971`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019499d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801947b3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801947b3`

## string_xrefs

- `0x1801949af`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x1801949ea`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::AutoPilotPolicyManager::WriteDefaultOrderTokenValueNameToRegistry(void)
{
  int IsEnabled; // ebx
  __m128i si128; // xmm6
  bool v3; // al
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  __int64 v6; // rdx
  int v7; // r14d
  int v8; // esi
  __int64 v9; // rdx
  wchar_t *v10; // rdx
  __int64 v11; // rax
  DWORD v12; // edi
  const BYTE *v13; // rbx
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  char v16; // bl
  const BYTE *v17; // rax
  unsigned int v18; // ebx
  DWORD dwOptions; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  __m128i v23; // [rsp+70h] [rbp-98h]
  _BYTE v24[32]; // [rsp+80h] [rbp-88h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v26; // [rsp+B0h] [rbp-58h]
  _OWORD v27[2]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v28[32]; // [rsp+E0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  if ( byte_1802B2488 )
    return 0;
  IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl);
  *(_OWORD *)hKey_8 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v23 = si128;
  LOWORD(hKey_8[0]) = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = ZTPIsStateSeparationEnabled();
  v4 = L"OSData\\Software\\Microsoft\\Provisioning\\Diagnostics\\Autopilot\\DefaultEvaluationOrder";
  if ( !v3 )
    v4 = L"Software\\Microsoft\\Provisioning\\Diagnostics\\Autopilot\\DefaultEvaluationOrder";
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( !v5 )
  {
    v7 = IsEnabled + 3;
    v8 = 0;
    do
    {
      std::wstring::wstring(v28, L"PolicySourceName_");
      v27[0] = 0;
      v27[1] = si128;
      LOWORD(v27[0]) = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        v9 = (unsigned int)dword_18024C860[v8];
      else
        v9 = (unsigned int)dword_18024C870[v8];
      std::_Integral_to_string<unsigned short,int>(v24, v9);
      std::wstring::operator=(v27, v24);
      std::wstring::_Tidy_deallocate(v24);
      std::wstring::append(v28, v27);
      v25 = 0;
      v26 = si128;
      LOWORD(v25) = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        v10 = off_1802168C0[v8];
      else
        v10 = off_1802168A0[v8];
      v11 = std::wstring::wstring(v24, v10);
      std::wstring::operator=(&v25, v11);
      std::wstring::_Tidy_deallocate(v24);
      v12 = 2 * v26.m128i_i32[0];
      v13 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
      v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
      v15 = RegSetValueExW(hKey, v14, 0, 1u, v13, v12);
      if ( v15 )
      {
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x12E,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
                (const char *)v15,
                dwOptionsa);
        std::wstring::_Tidy_deallocate(&v25);
        std::wstring::_Tidy_deallocate(v27);
        std::wstring::_Tidy_deallocate(v28);
        goto LABEL_26;
      }
      std::wstring::append(hKey_8, v27);
      if ( v8 < v7 - 1 )
        std::wstring::append(hKey_8, L";");
      std::wstring::_Tidy_deallocate(&v25);
      std::wstring::_Tidy_deallocate(v27);
      std::wstring::_Tidy_deallocate(v28);
      ++v8;
    }
    while ( v8 < v7 );
    v16 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl);
    v17 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(hKey_8);
    if ( v16 )
    {
      v5 = RegSetValueExW(hKey, L"DefaultPolicyOrderTag", 0, 1u, v17, 2 * v23.m128i_i32[0]);
      if ( v5 )
      {
        v6 = 320;
        goto LABEL_23;
      }
    }
    else
    {
      v5 = RegSetValueExW(hKey, L"DefaultPolicyOrder", 0, 1u, v17, 2 * v23.m128i_i32[0]);
      if ( v5 )
      {
        v6 = 330;
        goto LABEL_23;
      }
    }
    byte_1802B2488 = 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(hKey_8);
    return 0;
  }
  v6 = 275;
LABEL_23:
  v18 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v6,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicymanager.cpp",
          (const char *)v5,
          dwOptions);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(hKey_8);
  return v18;
}

```

## disassembly

```asm
0x1801946ec  mov     rax, rsp
0x1801946ef  push    rbp
0x1801946f0  push    rbx
0x1801946f1  push    rsi
0x1801946f2  push    rdi
0x1801946f3  push    r13
0x1801946f5  push    r14
0x1801946f7  lea     rbp, [rax-48h]
0x1801946fb  sub     rsp, 118h
0x180194702  movaps  xmmword ptr [rax-48h], xmm6
0x180194706  mov     rax, cs:__security_cookie
0x18019470d  xor     rax, rsp
0x180194710  mov     qword ptr [rbp+40h+var_48], rax
0x180194714  cmp     cs:byte_1802B2488, 0
0x18019471b  jz      short loc_180194724
0x18019471d  xor     eax, eax
0x18019471f  jmp     loc_180194A2E
0x180194724  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18019472b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180194730  movzx   ebx, al
0x180194733  xorps   xmm0, xmm0
0x180194736  movups  xmmword ptr [rsp+140h+hKey+8], xmm0
0x18019473b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180194743  movdqu  [rsp+140h+var_E0+8], xmm6
0x180194749  xor     ecx, ecx
0x18019474b  mov     word ptr [rsp+140h+hKey+8], cx
0x180194750  mov     [rsp+140h+hKey], rcx
0x180194755  xor     edx, edx
0x180194757  lea     rcx, [rsp+140h+hKey]
0x18019475c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180194761  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x180194766  lea     rcx, aSoftwareMicros_20; "Software\\Microsoft\\Provisioning\\Diag"...
0x18019476d  lea     rdx, aOsdataSoftware_11; "OSData\\Software\\Microsoft\\Provisioni"...
0x180194774  test    al, al
0x180194776  cmovz   rdx, rcx; lpSubKey
0x18019477a  mov     qword ptr [rsp+40h], 0; lpdwDisposition
0x180194783  lea     rax, [rsp+140h+hKey]
0x180194788  mov     [rsp+140h+phkResult], rax; phkResult
0x18019478d  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180194796  mov     [rsp+140h+samDesired], 2; samDesired
0x18019479e  mov     [rsp+140h+dwOptions], 0; dwOptions
0x1801947a6  xor     r9d, r9d; lpClass
0x1801947a9  xor     r8d, r8d; Reserved
0x1801947ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801947b3  call    cs:__imp_RegCreateKeyExW
0x1801947b9  test    eax, eax
0x1801947bb  jz      short loc_1801947C7
0x1801947bd  mov     edx, 113h
0x1801947c2  jmp     loc_1801949AC
0x1801947c7  lea     r14d, [rbx+3]
0x1801947cb  xor     esi, esi
0x1801947cd  lea     r13, __ImageBase
0x1801947d4  lea     rdx, aPolicysourcena; "PolicySourceName_"
0x1801947db  lea     rcx, [rbp+40h+var_68]
0x1801947df  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801947e4  xorps   xmm0, xmm0
0x1801947e7  movups  [rbp+40h+var_88], xmm0
0x1801947eb  movdqu  [rbp+40h+var_78], xmm6
0x1801947f0  xor     eax, eax
0x1801947f2  mov     word ptr [rbp+40h+var_88], ax
0x1801947f6  movsxd  rbx, esi
0x1801947f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180194800  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180194805  lea     rcx, [rsp+78h]
0x18019480a  test    al, al
0x18019480c  jz      short loc_180194818
0x18019480e  mov     edx, ds:rva dword_18024C860[r13+rbx*4]
0x180194816  jmp     short loc_180194820
0x180194818  mov     edx, ds:rva dword_18024C870[r13+rbx*4]
0x180194820  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x180194825  lea     rdx, [rsp+78h]
0x18019482a  lea     rcx, [rbp+40h+var_88]
0x18019482e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180194833  lea     rcx, [rsp+78h]
0x180194838  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019483d  lea     rdx, [rbp+40h+var_88]
0x180194841  lea     rcx, [rbp+40h+var_68]
0x180194845  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18019484a  xorps   xmm0, xmm0
0x18019484d  movups  [rbp+40h+var_A8], xmm0
0x180194851  movdqu  [rbp+40h+var_98], xmm6
0x180194856  xor     eax, eax
0x180194858  mov     word ptr [rbp+40h+var_A8], ax
0x18019485c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180194863  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x180194868  lea     rcx, [rsp+78h]
0x18019486d  test    al, al
0x18019486f  jz      short loc_18019487B
0x180194871  mov     rdx, ds:rva off_1802168C0[r13+rbx*8]; "AutoPilotPolicySource::Registry" ...
0x180194879  jmp     short loc_180194883
0x18019487b  mov     rdx, ds:rva off_1802168A0[r13+rbx*8]; "AutoPilotPolicySource::Registry" ...
0x180194883  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180194888  mov     rdx, rax
0x18019488b  lea     rcx, [rbp+40h+var_A8]
0x18019488f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180194894  lea     rcx, [rsp+78h]
0x180194899  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019489e  mov     eax, dword ptr [rbp+40h+var_98]
0x1801948a1  lea     edi, [rax+rax]
0x1801948a4  lea     rcx, [rbp+40h+var_A8]
0x1801948a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801948ad  mov     rbx, rax
0x1801948b0  lea     rcx, [rbp+40h+var_68]
0x1801948b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801948b9  mov     rdx, rax; lpValueName
0x1801948bc  mov     [rsp+140h+samDesired], edi; cbData
0x1801948c0  mov     qword ptr [rsp+140h+dwOptions], rbx; unsigned int
0x1801948c5  mov     r9d, 1; dwType
0x1801948cb  xor     r8d, r8d; Reserved
0x1801948ce  mov     rcx, [rsp+140h+hKey]; hKey
0x1801948d3  call    cs:__imp_RegSetValueExW
0x1801948d9  test    eax, eax
0x1801948db  jnz     loc_1801949E3
0x1801948e1  lea     rdx, [rbp+40h+var_88]
0x1801948e5  lea     rcx, [rsp+140h+hKey+8]
0x1801948ea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1801948ef  lea     eax, [r14-1]
0x1801948f3  cmp     esi, eax
0x1801948f5  jge     short loc_180194908
0x1801948f7  lea     rdx, asc_18022A700; ";"
0x1801948fe  lea     rcx, [rsp+140h+hKey+8]
0x180194903  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180194908  lea     rcx, [rbp+40h+var_A8]
0x18019490c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194911  lea     rcx, [rbp+40h+var_88]
0x180194915  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019491a  lea     rcx, [rbp+40h+var_68]
0x18019491e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194923  inc     esi
0x180194925  cmp     esi, r14d
0x180194928  jl      loc_1801947D4
0x18019492e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180194935  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18019493a  mov     bl, al
0x18019493c  lea     rcx, [rsp+140h+hKey+8]
0x180194941  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180194946  mov     rcx, rax
0x180194949  mov     r9d, 1; dwType
0x18019494f  xor     r8d, r8d; Reserved
0x180194952  test    bl, bl
0x180194954  jz      short loc_180194982
0x180194956  mov     edx, dword ptr [rsp+140h+var_E0+8]
0x18019495a  add     edx, edx
0x18019495c  mov     [rsp+140h+samDesired], edx; cbData
0x180194960  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x180194965  lea     rdx, aDefaultpolicyo_0; "DefaultPolicyOrderTag"
0x18019496c  mov     rcx, [rsp+140h+hKey]; hKey
0x180194971  call    cs:__imp_RegSetValueExW
0x180194977  test    eax, eax
0x180194979  jz      short loc_1801949C3
0x18019497b  mov     edx, 140h
0x180194980  jmp     short loc_1801949AC
0x180194982  mov     eax, dword ptr [rsp+140h+var_E0+8]
0x180194986  add     eax, eax
0x180194988  mov     [rsp+140h+samDesired], eax; cbData
0x18019498c  mov     qword ptr [rsp+140h+dwOptions], rcx; unsigned int
0x180194991  lea     rdx, aDefaultpolicyo; "DefaultPolicyOrder"
0x180194998  mov     rcx, [rsp+140h+hKey]; hKey
0x18019499d  call    cs:__imp_RegSetValueExW
0x1801949a3  test    eax, eax
0x1801949a5  jz      short loc_1801949C3
0x1801949a7  mov     edx, 14Ah; void *
0x1801949ac  mov     r9d, eax; char *
0x1801949af  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801949b6  mov     rcx, [rbp+48h]; this
0x1801949ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801949bf  mov     ebx, eax
0x1801949c1  jmp     short loc_180194A18
0x1801949c3  mov     cs:byte_1802B2488, 1
0x1801949ca  lea     rcx, [rsp+140h+hKey]
0x1801949cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801949d4  lea     rcx, [rsp+140h+hKey+8]
0x1801949d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801949de  jmp     loc_18019471D
0x1801949e3  mov     rcx, [rbp+48h]; this
0x1801949e7  mov     r9d, eax; char *
0x1801949ea  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801949f1  mov     edx, 12Eh; void *
0x1801949f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801949fb  mov     ebx, eax
0x1801949fd  lea     rcx, [rbp+40h+var_A8]
0x180194a01  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194a06  lea     rcx, [rbp+40h+var_88]
0x180194a0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194a0f  lea     rcx, [rbp+40h+var_68]
0x180194a13  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194a18  lea     rcx, [rsp+140h+hKey]
0x180194a1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180194a22  lea     rcx, [rsp+140h+hKey+8]
0x180194a27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180194a2c  mov     eax, ebx
0x180194a2e  mov     rcx, qword ptr [rbp+40h+var_48]
0x180194a32  xor     rcx, rsp; StackCookie
0x180194a35  call    __security_check_cookie
0x180194a3a  movaps  xmm6, [rsp+140h+var_48+8]
0x180194a42  add     rsp, 118h
0x180194a49  pop     r14
0x180194a4b  pop     r13
0x180194a4d  pop     rdi
0x180194a4e  pop     rsi
0x180194a4f  pop     rbx
0x180194a50  pop     rbp
0x180194a51  retn
```
