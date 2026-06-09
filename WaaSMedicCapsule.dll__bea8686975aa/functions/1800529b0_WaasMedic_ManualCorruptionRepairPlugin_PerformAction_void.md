# WaasMedic::ManualCorruptionRepairPlugin::PerformAction(void)

- ea: `0x1800529b0`
- end: `0x180052def`
- name: `?PerformAction@ManualCorruptionRepairPlugin@WaasMedic@@UEAAJXZ`
- size: `1087`
- prototype: `__int64 __fastcall(WaasMedic::ManualCorruptionRepairPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003bb0`
- `0x18000487c`
- `0x1800048d0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18002543c`
- `0x180029168`
- `0x18003741c`
- `0x1800384c4`
- `0x18003874c`
- `0x1800392e4`
- `0x1800395c4`
- `0x180039d3c`
- `0x1800529b0`
- `0x180052df8`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180052cf0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180052cf0`

## string_xrefs

- `0x180052b9e`: `SYSTEM\WaaS\Plugin`
- `0x180052bc3`: `SYSTEM\WaaS\Plugin`
- `0x180052a96`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`
- `0x180052ca8`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`
- `0x180052cfe`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`
- `0x180052d2f`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`
- `0x180052d4f`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`
- `0x180052db0`: `onecore\enduser\waasmedic\lib\plugins\manualcorruptionrepairplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::ManualCorruptionRepairPlugin::PerformAction(
        WaasMedic::ManualCorruptionRepairPlugin *this)
{
  char IsEnabled; // al
  __int64 (__fastcall ***v3)(_QWORD, __int128 *, __int128 *, _DWORD *); // rdi
  __int64 (__fastcall *v4)(_QWORD, __int128 *, __int128 *, _DWORD *); // r14
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // edi
  int v14; // eax
  const OLECHAR *v15; // r8
  void *v16; // rbx
  int v17; // eax
  HANDLE v18; // rax
  int v19; // ecx
  void *v21; // rbx
  int v22; // esi
  HANDLE ProcessHeap; // rax
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-79h]
  _BYTE v26[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v27; // [rsp+38h] [rbp-61h] BYREF
  __int64 v28; // [rsp+40h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v30[2]; // [rsp+50h] [rbp-49h] BYREF
  char v31; // [rsp+58h] [rbp-41h]
  int v32; // [rsp+60h] [rbp-39h] BYREF
  int v33; // [rsp+64h] [rbp-35h] BYREF
  _BYTE v34[4]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v35[4]; // [rsp+6Ch] [rbp-2Dh] BYREF
  __int128 v36; // [rsp+70h] [rbp-29h] BYREF
  __int128 v37; // [rsp+80h] [rbp-19h]
  __int128 v38; // [rsp+90h] [rbp-9h] BYREF
  __int128 v39; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v31 = 0;
  v30[0] = *((_DWORD *)this + 40);
  v30[1] = 2;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseMCRIterationCount>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseMCRIterationCount>::GetImpl'::`2'::impl);
  v3 = (__int64 (__fastcall ***)(_QWORD, __int128 *, __int128 *, _DWORD *))*((_QWORD *)this + 13);
  v4 = **v3;
  if ( IsEnabled )
  {
    v38 = 0;
    v39 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v38, L"MCRIterationCount", 17);
    v5 = *((_QWORD *)this + 14);
    v36 = 0;
    v37 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    std::wstring::_Construct<1,unsigned short const *>(&v36, v5, v6);
    v7 = v4(v3, &v36, &v38, v30);
    std::wstring::~wstring(&v36);
    std::wstring::~wstring(&v38);
    if ( v7 < 0 )
    {
      v8 = 258;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v7,
        v25);
      return (unsigned int)v7;
    }
  }
  else
  {
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v36, L"ACRIterationCount", 17);
    v9 = *((_QWORD *)this + 14);
    v38 = 0;
    v39 = 0;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v9 + 2 * v10) );
    std::wstring::_Construct<1,unsigned short const *>(&v38, v9, v10);
    v7 = v4(v3, &v38, &v36, v30);
    std::wstring::~wstring(&v38);
    std::wstring::~wstring(&v36);
    if ( v7 < 0 )
    {
      v8 = 262;
      goto LABEL_6;
    }
  }
  v26[0] = 0;
  while ( 1 )
  {
    winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper((winrt::Windows::Internal::WaasMedicDocked::CBSHelper *)&v27);
    v32 = 1;
    v33 = 1;
    v7 = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::Initialize(
                      &v27,
                      v34,
                      &v33,
                      &v32);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10D,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v7,
        v25);
      goto LABEL_55;
    }
    winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(
      &v27,
      &v28);
    v7 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,unsigned int>::get(&v28);
    if ( v7 == -2146498527 )
    {
      if ( v28 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
      if ( v27 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
      return 2147943623LL;
    }
    LOBYTE(v25) = 0;
    v13 = WaasMedic::RegSetDwordValue(v11, L"SYSTEM\\WaaS\\Plugin", L"EscalatetoInPlaceUpgrade", 1);
    if ( v13 < 0 )
    {
      v24 = 279;
      goto LABEL_43;
    }
    LOBYTE(v25) = 0;
    v14 = WaasMedic::RegSetDwordValue(v12, L"SYSTEM\\WaaS\\Plugin", L"EscalateToMCR", 0);
    v13 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v14,
        v25);
      v24 = 281;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v13,
        v25);
LABEL_44:
      if ( v28 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
      if ( v27 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
      return (unsigned int)v13;
    }
    if ( v7 < 0 )
      break;
    lpMem = 0;
    v13 = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::GetSessionReport(
                       &v27,
                       v35,
                       &lpMem,
                       v26);
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v13,
        v25);
      v21 = lpMem;
      if ( lpMem )
      {
        v22 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
        if ( v22 )
        {
          if ( v22 < 0 )
LABEL_38:
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v21);
        }
        lpMem = 0;
      }
      goto LABEL_44;
    }
    if ( lpMem )
      v15 = (const OLECHAR *)*((_QWORD *)lpMem + 2);
    else
      v15 = &word_18006939C;
    LogLevelW(4u, L"CBS Report: %s", v15);
    v16 = lpMem;
    if ( lpMem )
    {
      v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          goto LABEL_38;
      }
      else
      {
        v18 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v18, 0, v16);
      }
      lpMem = 0;
    }
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
    if ( v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
    if ( v26[0] )
    {
      v19 = v30[0]--;
      if ( v19 > 0 )
        continue;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11B,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\manualcorruptionrepairplugin.cpp",
    (const char *)(unsigned int)v7,
    v25);
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
LABEL_55:
  if ( v27 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800529b0  push    rbp
0x1800529b2  push    rbx
0x1800529b3  push    rsi
0x1800529b4  push    rdi
0x1800529b5  push    r14
0x1800529b7  push    r15
0x1800529b9  lea     rbp, [rsp-2Fh]
0x1800529be  sub     rsp, 0C8h
0x1800529c5  mov     rax, cs:__security_cookie
0x1800529cc  xor     rax, rsp
0x1800529cf  mov     [rbp+57h+var_40], rax
0x1800529d3  mov     rbx, rcx
0x1800529d6  xor     r15d, r15d
0x1800529d9  mov     [rbp+57h+var_98], r15b
0x1800529dd  mov     eax, [rcx+0A0h]
0x1800529e3  mov     [rbp+57h+var_A0], eax
0x1800529e6  mov     [rbp+57h+var_9C], 2
0x1800529ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseMCRIterationCount@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseMCRIterationCount@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseMCRIterationCount> `wil::Feature<__WilFeatureTraits_Feature_UseMCRIterationCount>::GetImpl(void)'::`2'::impl
0x1800529f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseMCRIterationCount@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseMCRIterationCount>::__private_IsEnabled(void)
0x1800529f9  mov     rdi, [rbx+68h]
0x1800529fd  xorps   xmm0, xmm0
0x180052a00  xorps   xmm1, xmm1
0x180052a03  lea     r8d, [r15+11h]
0x180052a07  test    al, al
0x180052a09  mov     rax, [rdi]
0x180052a0c  mov     r14, [rax]
0x180052a0f  jz      loc_180052AAE
0x180052a15  movups  [rbp+57h+var_60], xmm0
0x180052a19  movdqu  [rbp+57h+var_50], xmm1
0x180052a1e  lea     rdx, aMcriterationco; "MCRIterationCount"
0x180052a25  lea     rcx, [rbp+57h+var_60]
0x180052a29  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180052a2e  nop
0x180052a2f  mov     rdx, [rbx+70h]
0x180052a33  xorps   xmm0, xmm0
0x180052a36  movups  [rbp+57h+var_80], xmm0
0x180052a3a  xorps   xmm1, xmm1
0x180052a3d  movdqu  [rbp+57h+var_70], xmm1
0x180052a42  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052a46  mov     r8, rsi
0x180052a49  inc     r8
0x180052a4c  cmp     [rdx+r8*2], r15w
0x180052a51  jnz     short loc_180052A49
0x180052a53  lea     rcx, [rbp+57h+var_80]
0x180052a57  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180052a5c  nop
0x180052a5d  lea     r9, [rbp+57h+var_A0]
0x180052a61  lea     r8, [rbp+57h+var_60]
0x180052a65  lea     rdx, [rbp+57h+var_80]
0x180052a69  mov     rcx, rdi
0x180052a6c  mov     rax, r14
0x180052a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a74  mov     ebx, eax
0x180052a76  lea     rcx, [rbp+57h+var_80]; void *
0x180052a7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052a7f  nop
0x180052a80  lea     rcx, [rbp+57h+var_60]; void *
0x180052a84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052a89  test    ebx, ebx
0x180052a8b  jns     loc_180052B30
0x180052a91  mov     edx, 102h; void *
0x180052a96  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052a9d  mov     r9d, ebx; char *
0x180052aa0  mov     rcx, [rbp+5Fh]; this
0x180052aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052aa9  jmp     loc_180052DD1
0x180052aae  movups  [rbp+57h+var_80], xmm0
0x180052ab2  movdqu  [rbp+57h+var_70], xmm1
0x180052ab7  lea     rdx, aAcriterationco; "ACRIterationCount"
0x180052abe  lea     rcx, [rbp+57h+var_80]
0x180052ac2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180052ac7  nop
0x180052ac8  mov     rdx, [rbx+70h]
0x180052acc  xorps   xmm0, xmm0
0x180052acf  movups  [rbp+57h+var_60], xmm0
0x180052ad3  xorps   xmm1, xmm1
0x180052ad6  movdqu  [rbp+57h+var_50], xmm1
0x180052adb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180052adf  mov     r8, rsi
0x180052ae2  inc     r8
0x180052ae5  cmp     [rdx+r8*2], r15w
0x180052aea  jnz     short loc_180052AE2
0x180052aec  lea     rcx, [rbp+57h+var_60]
0x180052af0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180052af5  nop
0x180052af6  lea     r9, [rbp+57h+var_A0]
0x180052afa  lea     r8, [rbp+57h+var_80]
0x180052afe  lea     rdx, [rbp+57h+var_60]
0x180052b02  mov     rcx, rdi
0x180052b05  mov     rax, r14
0x180052b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b0d  mov     ebx, eax
0x180052b0f  lea     rcx, [rbp+57h+var_60]; void *
0x180052b13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052b18  nop
0x180052b19  lea     rcx, [rbp+57h+var_80]; void *
0x180052b1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052b22  test    ebx, ebx
0x180052b24  jns     short loc_180052B30
0x180052b26  mov     edx, 106h
0x180052b2b  jmp     loc_180052A96
0x180052b30  mov     [rbp+57h+var_C0], r15b
0x180052b34  mov     r14d, 1
0x180052b3a  lea     rcx, [rbp+57h+var_B8]; this
0x180052b3e  call    ??0CBSHelper@WaasMedicDocked@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper(void)
0x180052b43  nop
0x180052b44  mov     [rbp+57h+var_90], r14d
0x180052b48  mov     [rbp+57h+var_8C], r14d
0x180052b4c  lea     r9, [rbp+57h+var_90]
0x180052b50  lea     r8, [rbp+57h+var_8C]
0x180052b54  lea     rdx, [rbp+57h+var_88]
0x180052b58  lea     rcx, [rbp+57h+var_B8]
0x180052b5c  call    ?Initialize@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4CorruptionRepairAction@WaasMedicDocked@Internal@Windows@3@AEBW4CorruptionRepairOption@5673@@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::Initialize(winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairAction const &,winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairOption const &)
0x180052b61  mov     ebx, [rax]
0x180052b63  test    ebx, ebx
0x180052b65  js      loc_180052DA9
0x180052b6b  lea     rdx, [rbp+57h+var_B0]
0x180052b6f  lea     rcx, [rbp+57h+var_B8]
0x180052b73  call    ?PerformCorruptionRepair@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(void)
0x180052b78  nop
0x180052b79  lea     rcx, [rbp+57h+var_B0]
0x180052b7d  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@I@Foundation@Windows@winrt@@I@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<uint>,uint>::get(void)
0x180052b82  mov     ebx, eax
0x180052b84  cmp     eax, 800F0821h
0x180052b89  jz      loc_180052D83
0x180052b8f  mov     byte ptr [rsp+0F0h+var_D0], r15b; int
0x180052b94  mov     r9d, r14d
0x180052b97  lea     r8, aEscalatetoinpl; "EscalatetoInPlaceUpgrade"
0x180052b9e  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x180052ba5  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x180052baa  mov     edi, eax
0x180052bac  test    eax, eax
0x180052bae  js      loc_180052D47
0x180052bb4  mov     byte ptr [rsp+0F0h+var_D0], r15b; int
0x180052bb9  xor     r9d, r9d
0x180052bbc  lea     r8, aEscalatetomcr; "EscalateToMCR"
0x180052bc3  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x180052bca  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x180052bcf  mov     edi, eax
0x180052bd1  test    eax, eax
0x180052bd3  js      loc_180052D28
0x180052bd9  test    ebx, ebx
0x180052bdb  js      loc_180052CF7
0x180052be1  mov     [rbp+57h+lpMem], r15
0x180052be5  lea     r9, [rbp+57h+var_C0]
0x180052be9  lea     r8, [rbp+57h+lpMem]
0x180052bed  lea     rdx, [rbp+57h+var_84]
0x180052bf1  lea     rcx, [rbp+57h+var_B8]
0x180052bf5  call    ?GetSessionReport@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEAUhstring@3@AEA_N@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::GetSessionReport(winrt::hstring &,bool &)
0x180052bfa  mov     edi, [rax]
0x180052bfc  test    edi, edi
0x180052bfe  js      loc_180052CA1
0x180052c04  mov     rax, [rbp+57h+lpMem]
0x180052c08  test    rax, rax
0x180052c0b  jz      short loc_180052C13
0x180052c0d  mov     r8, [rax+10h]
0x180052c11  jmp     short loc_180052C1A
0x180052c13  lea     r8, word_18006939C
0x180052c1a  lea     rdx, aCbsReportS; "CBS Report: %s"
0x180052c21  mov     ecx, 4; unsigned __int8
0x180052c26  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180052c2b  nop
0x180052c2c  mov     rbx, [rbp+57h+lpMem]
0x180052c30  test    rbx, rbx
0x180052c33  jz      short loc_180052C62
0x180052c35  mov     eax, esi
0x180052c37  lock xadd [rbx+18h], eax
0x180052c3c  sub     eax, 1
0x180052c3f  jnz     short loc_180052C56
0x180052c41  nop
0x180052c42  call    WINRT_IMPL_GetProcessHeap
0x180052c47  mov     rcx, rax; hHeap
0x180052c4a  mov     r8, rbx; lpMem
0x180052c4d  xor     edx, edx; dwFlags
0x180052c4f  call    WINRT_IMPL_HeapFree
0x180052c54  jmp     short loc_180052C5E
0x180052c56  test    eax, eax
0x180052c58  js      loc_180052CF0
0x180052c5e  mov     [rbp+57h+lpMem], r15
0x180052c62  cmp     [rbp+57h+var_B0], r15
0x180052c66  jz      short loc_180052C72
0x180052c68  lea     rcx, [rbp+57h+var_B0]
0x180052c6c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052c71  nop
0x180052c72  cmp     [rbp+57h+var_B8], r15
0x180052c76  jz      short loc_180052C81
0x180052c78  lea     rcx, [rbp+57h+var_B8]
0x180052c7c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052c81  cmp     [rbp+57h+var_C0], r15b
0x180052c85  jz      short loc_180052C9A
0x180052c87  mov     eax, [rbp+57h+var_A0]
0x180052c8a  mov     ecx, eax
0x180052c8c  sub     eax, r14d
0x180052c8f  mov     [rbp+57h+var_A0], eax
0x180052c92  test    ecx, ecx
0x180052c94  jg      loc_180052B3A
0x180052c9a  xor     eax, eax
0x180052c9c  jmp     loc_180052DD3
0x180052ca1  mov     rcx, [rbp+5Fh]; this
0x180052ca5  mov     r9d, edi; char *
0x180052ca8  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052caf  mov     edx, 11Eh; void *
0x180052cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052cb9  nop
0x180052cba  mov     rbx, [rbp+57h+lpMem]
0x180052cbe  test    rbx, rbx
0x180052cc1  jz      loc_180052D60
0x180052cc7  lock xadd [rbx+18h], esi
0x180052ccc  sub     esi, 1
0x180052ccf  jnz     short loc_180052CE6
0x180052cd1  nop
0x180052cd2  call    WINRT_IMPL_GetProcessHeap
0x180052cd7  mov     rcx, rax; hHeap
0x180052cda  mov     r8, rbx; lpMem
0x180052cdd  xor     edx, edx; dwFlags
0x180052cdf  call    WINRT_IMPL_HeapFree
0x180052ce4  jmp     short loc_180052CEA
0x180052ce6  test    esi, esi
0x180052ce8  js      short loc_180052CF0
0x180052cea  mov     [rbp+57h+lpMem], r15
0x180052cee  jmp     short loc_180052D60
0x180052cf0  call    cs:__imp_abort
0x180052cf7  mov     rcx, [rbp+5Fh]; this
0x180052cfb  mov     r9d, ebx; char *
0x180052cfe  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052d05  mov     edx, 11Bh; void *
0x180052d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d0f  nop
0x180052d10  cmp     [rbp+57h+var_B0], r15
0x180052d14  jz      loc_180052DC2
0x180052d1a  lea     rcx, [rbp+57h+var_B0]
0x180052d1e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052d23  jmp     loc_180052DC2
0x180052d28  mov     rcx, [rbp+5Fh]; this
0x180052d2c  mov     r9d, edi; char *
0x180052d2f  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052d36  mov     edx, 0EEh; void *
0x180052d3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d40  mov     edx, 119h
0x180052d45  jmp     short loc_180052D4C
0x180052d47  mov     edx, 117h; void *
0x180052d4c  mov     r9d, edi; char *
0x180052d4f  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052d56  mov     rcx, [rbp+5Fh]; this
0x180052d5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d5f  nop
0x180052d60  cmp     [rbp+57h+var_B0], r15
0x180052d64  jz      short loc_180052D70
0x180052d66  lea     rcx, [rbp+57h+var_B0]
0x180052d6a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052d6f  nop
0x180052d70  cmp     [rbp+57h+var_B8], r15
0x180052d74  jz      short loc_180052D7F
0x180052d76  lea     rcx, [rbp+57h+var_B8]
0x180052d7a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052d7f  mov     eax, edi
0x180052d81  jmp     short loc_180052DD3
0x180052d83  cmp     [rbp+57h+var_B0], r15
0x180052d87  jz      short loc_180052D93
0x180052d89  lea     rcx, [rbp+57h+var_B0]
0x180052d8d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052d92  nop
0x180052d93  cmp     [rbp+57h+var_B8], r15
0x180052d97  jz      short loc_180052DA2
0x180052d99  lea     rcx, [rbp+57h+var_B8]
0x180052d9d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052da2  mov     eax, 800704C7h
0x180052da7  jmp     short loc_180052DD3
0x180052da9  mov     rcx, [rbp+5Fh]; this
0x180052dad  mov     r9d, ebx; char *
0x180052db0  lea     r8, aOnecoreEnduser_15; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180052db7  mov     edx, 10Dh; void *
0x180052dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052dc1  nop
0x180052dc2  cmp     [rbp+57h+var_B8], r15
0x180052dc6  jz      short loc_180052DD1
0x180052dc8  lea     rcx, [rbp+57h+var_B8]
0x180052dcc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180052dd1  mov     eax, ebx
0x180052dd3  mov     rcx, [rbp+57h+var_40]
0x180052dd7  xor     rcx, rsp; StackCookie
0x180052dda  call    __security_check_cookie
0x180052ddf  add     rsp, 0C8h
0x180052de6  pop     r15
0x180052de8  pop     r14
0x180052dea  pop     rdi
0x180052deb  pop     rsi
0x180052dec  pop     rbx
0x180052ded  pop     rbp
0x180052dee  retn
```
