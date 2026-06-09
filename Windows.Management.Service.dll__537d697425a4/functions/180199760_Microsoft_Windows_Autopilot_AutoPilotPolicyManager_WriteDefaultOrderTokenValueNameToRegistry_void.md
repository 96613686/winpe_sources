# Microsoft::Windows::Autopilot::AutoPilotPolicyManager::WriteDefaultOrderTokenValueNameToRegistry(void)

- ea: `0x180199760`
- end: `0x180199adf`
- name: `?WriteDefaultOrderTokenValueNameToRegistry@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@CAJXZ`
- size: `895`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180196f38`

## callees

- `0x18000b8f0`
- `0x180077de0`
- `0x180080984`
- `0x180080bac`
- `0x180080c10`
- `0x180084574`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x18008af70`
- `0x18008ed40`
- `0x18008ed78`
- `0x180178ed8`
- `0x180199760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019994d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801999f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180199a23`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019994d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801999f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180199a23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180199827`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180199827`

## string_xrefs

- `0x180199a3b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`
- `0x180199a76`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicymanager.cpp`

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

  if ( byte_1802B75B8 )
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
        v9 = (unsigned int)dword_180252750[v8];
      else
        v9 = (unsigned int)dword_180252760[v8];
      std::_Integral_to_string<unsigned short,int>(v24, v9);
      std::wstring::operator=(v27, v24);
      std::wstring::_Tidy_deallocate(v24);
      std::wstring::append(v28, v27);
      v25 = 0;
      v26 = si128;
      LOWORD(v25) = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
        v10 = off_18021C8B8[v8];
      else
        v10 = off_18021C8A0[v8];
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
    byte_1802B75B8 = 1;
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
0x180199760  mov     rax, rsp
0x180199763  push    rbp
0x180199764  push    rbx
0x180199765  push    rsi
0x180199766  push    rdi
0x180199767  push    r13
0x180199769  push    r14
0x18019976b  lea     rbp, [rax-48h]
0x18019976f  sub     rsp, 118h
0x180199776  movaps  xmmword ptr [rax-48h], xmm6
0x18019977a  mov     rax, cs:__security_cookie
0x180199781  xor     rax, rsp
0x180199784  mov     qword ptr [rbp+40h+var_48], rax
0x180199788  cmp     cs:byte_1802B75B8, 0
0x18019978f  jz      short loc_180199798
0x180199791  xor     eax, eax
0x180199793  jmp     loc_180199ABA
0x180199798  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18019979f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801997a4  movzx   ebx, al
0x1801997a7  xorps   xmm0, xmm0
0x1801997aa  movups  xmmword ptr [rsp+140h+hKey+8], xmm0
0x1801997af  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801997b7  movdqu  [rsp+140h+var_E0+8], xmm6
0x1801997bd  xor     ecx, ecx
0x1801997bf  mov     word ptr [rsp+140h+hKey+8], cx
0x1801997c4  mov     [rsp+140h+hKey], rcx
0x1801997c9  xor     edx, edx
0x1801997cb  lea     rcx, [rsp+140h+hKey]
0x1801997d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801997d5  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801997da  lea     rcx, aSoftwareMicros_20; "Software\\Microsoft\\Provisioning\\Diag"...
0x1801997e1  lea     rdx, aOsdataSoftware_11; "OSData\\Software\\Microsoft\\Provisioni"...
0x1801997e8  test    al, al
0x1801997ea  cmovz   rdx, rcx; lpSubKey
0x1801997ee  mov     qword ptr [rsp+40h], 0; lpdwDisposition
0x1801997f7  lea     rax, [rsp+140h+hKey]
0x1801997fc  mov     [rsp+140h+phkResult], rax; phkResult
0x180199801  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18019980a  mov     [rsp+140h+samDesired], 2; samDesired
0x180199812  mov     [rsp+140h+dwOptions], 0; dwOptions
0x18019981a  xor     r9d, r9d; lpClass
0x18019981d  xor     r8d, r8d; Reserved
0x180199820  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180199827  call    cs:__imp_RegCreateKeyExW
0x18019982e  nop     dword ptr [rax+rax+00h]
0x180199833  test    eax, eax
0x180199835  jz      short loc_180199841
0x180199837  mov     edx, 113h
0x18019983c  jmp     loc_180199A38
0x180199841  lea     r14d, [rbx+3]
0x180199845  xor     esi, esi
0x180199847  lea     r13, __ImageBase
0x18019984e  lea     rdx, aPolicysourcena; "PolicySourceName_"
0x180199855  lea     rcx, [rbp+40h+var_68]
0x180199859  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019985e  xorps   xmm0, xmm0
0x180199861  movups  [rbp+40h+var_88], xmm0
0x180199865  movdqu  [rbp+40h+var_78], xmm6
0x18019986a  xor     eax, eax
0x18019986c  mov     word ptr [rbp+40h+var_88], ax
0x180199870  movsxd  rbx, esi
0x180199873  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18019987a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18019987f  lea     rcx, [rsp+78h]
0x180199884  test    al, al
0x180199886  jz      short loc_180199892
0x180199888  mov     edx, ds:rva dword_180252750[r13+rbx*4]
0x180199890  jmp     short loc_18019989A
0x180199892  mov     edx, ds:rva dword_180252760[r13+rbx*4]
0x18019989a  call    ??$_Integral_to_string@GH@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@H@Z; std::_Integral_to_string<ushort,int>(int)
0x18019989f  lea     rdx, [rsp+78h]
0x1801998a4  lea     rcx, [rbp+40h+var_88]
0x1801998a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801998ad  lea     rcx, [rsp+78h]
0x1801998b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801998b7  lea     rdx, [rbp+40h+var_88]
0x1801998bb  lea     rcx, [rbp+40h+var_68]
0x1801998bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1801998c4  xorps   xmm0, xmm0
0x1801998c7  movups  [rbp+40h+var_A8], xmm0
0x1801998cb  movdqu  [rbp+40h+var_98], xmm6
0x1801998d0  xor     eax, eax
0x1801998d2  mov     word ptr [rbp+40h+var_A8], ax
0x1801998d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801998dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801998e2  lea     rcx, [rsp+78h]
0x1801998e7  test    al, al
0x1801998e9  jz      short loc_1801998F5
0x1801998eb  mov     rdx, ds:rva off_18021C8B8[r13+rbx*8]; "AutoPilotPolicySource::Registry" ...
0x1801998f3  jmp     short loc_1801998FD
0x1801998f5  mov     rdx, ds:rva off_18021C8A0[r13+rbx*8]; "AutoPilotPolicySource::Registry" ...
0x1801998fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180199902  mov     rdx, rax
0x180199905  lea     rcx, [rbp+40h+var_A8]
0x180199909  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18019990e  lea     rcx, [rsp+78h]
0x180199913  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199918  mov     eax, dword ptr [rbp+40h+var_98]
0x18019991b  lea     edi, [rax+rax]
0x18019991e  lea     rcx, [rbp+40h+var_A8]
0x180199922  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180199927  mov     rbx, rax
0x18019992a  lea     rcx, [rbp+40h+var_68]
0x18019992e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180199933  mov     rdx, rax; lpValueName
0x180199936  mov     [rsp+140h+samDesired], edi; cbData
0x18019993a  mov     qword ptr [rsp+140h+dwOptions], rbx; unsigned int
0x18019993f  mov     r9d, 1; dwType
0x180199945  xor     r8d, r8d; Reserved
0x180199948  mov     rcx, [rsp+140h+hKey]; hKey
0x18019994d  call    cs:__imp_RegSetValueExW
0x180199954  nop     dword ptr [rax+rax+00h]
0x180199959  test    eax, eax
0x18019995b  jnz     loc_180199A6F
0x180199961  lea     rdx, [rbp+40h+var_88]
0x180199965  lea     rcx, [rsp+140h+hKey+8]
0x18019996a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18019996f  lea     eax, [r14-1]
0x180199973  cmp     esi, eax
0x180199975  jge     short loc_180199988
0x180199977  lea     rdx, asc_180230740; ";"
0x18019997e  lea     rcx, [rsp+140h+hKey+8]
0x180199983  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180199988  lea     rcx, [rbp+40h+var_A8]
0x18019998c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199991  lea     rcx, [rbp+40h+var_88]
0x180199995  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019999a  lea     rcx, [rbp+40h+var_68]
0x18019999e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801999a3  inc     esi
0x1801999a5  cmp     esi, r14d
0x1801999a8  jl      loc_18019984E
0x1801999ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801999b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801999ba  mov     bl, al
0x1801999bc  lea     rcx, [rsp+140h+hKey+8]
0x1801999c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801999c6  mov     rcx, rax
0x1801999c9  mov     r9d, 1; dwType
0x1801999cf  xor     r8d, r8d; Reserved
0x1801999d2  test    bl, bl
0x1801999d4  jz      short loc_180199A08
0x1801999d6  mov     edx, dword ptr [rsp+140h+var_E0+8]
0x1801999da  add     edx, edx
0x1801999dc  mov     [rsp+140h+samDesired], edx; cbData
0x1801999e0  mov     qword ptr [rsp+140h+dwOptions], rax; lpData
0x1801999e5  lea     rdx, aDefaultpolicyo_0; "DefaultPolicyOrderTag"
0x1801999ec  mov     rcx, [rsp+140h+hKey]; hKey
0x1801999f1  call    cs:__imp_RegSetValueExW
0x1801999f8  nop     dword ptr [rax+rax+00h]
0x1801999fd  test    eax, eax
0x1801999ff  jz      short loc_180199A4F
0x180199a01  mov     edx, 140h
0x180199a06  jmp     short loc_180199A38
0x180199a08  mov     eax, dword ptr [rsp+140h+var_E0+8]
0x180199a0c  add     eax, eax
0x180199a0e  mov     [rsp+140h+samDesired], eax; cbData
0x180199a12  mov     qword ptr [rsp+140h+dwOptions], rcx; unsigned int
0x180199a17  lea     rdx, aDefaultpolicyo; "DefaultPolicyOrder"
0x180199a1e  mov     rcx, [rsp+140h+hKey]; hKey
0x180199a23  call    cs:__imp_RegSetValueExW
0x180199a2a  nop     dword ptr [rax+rax+00h]
0x180199a2f  test    eax, eax
0x180199a31  jz      short loc_180199A4F
0x180199a33  mov     edx, 14Ah; void *
0x180199a38  mov     r9d, eax; char *
0x180199a3b  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199a42  mov     rcx, [rbp+48h]; this
0x180199a46  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180199a4b  mov     ebx, eax
0x180199a4d  jmp     short loc_180199AA4
0x180199a4f  mov     cs:byte_1802B75B8, 1
0x180199a56  lea     rcx, [rsp+140h+hKey]
0x180199a5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199a60  lea     rcx, [rsp+140h+hKey+8]
0x180199a65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199a6a  jmp     loc_180199791
0x180199a6f  mov     rcx, [rbp+48h]; this
0x180199a73  mov     r9d, eax; char *
0x180199a76  lea     r8, aOnecoreuapAdmi_147; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199a7d  mov     edx, 12Eh; void *
0x180199a82  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180199a87  mov     ebx, eax
0x180199a89  lea     rcx, [rbp+40h+var_A8]
0x180199a8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199a92  lea     rcx, [rbp+40h+var_88]
0x180199a96  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199a9b  lea     rcx, [rbp+40h+var_68]
0x180199a9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199aa4  lea     rcx, [rsp+140h+hKey]
0x180199aa9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199aae  lea     rcx, [rsp+140h+hKey+8]
0x180199ab3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180199ab8  mov     eax, ebx
0x180199aba  mov     rcx, qword ptr [rbp+40h+var_48]
0x180199abe  xor     rcx, rsp; StackCookie
0x180199ac1  call    __security_check_cookie
0x180199ac6  movaps  xmm6, [rsp+140h+var_48+8]
0x180199ace  add     rsp, 118h
0x180199ad5  pop     r14
0x180199ad7  pop     r13
0x180199ad9  pop     rdi
0x180199ada  pop     rsi
0x180199adb  pop     rbx
0x180199adc  pop     rbp
0x180199add  retn
```
