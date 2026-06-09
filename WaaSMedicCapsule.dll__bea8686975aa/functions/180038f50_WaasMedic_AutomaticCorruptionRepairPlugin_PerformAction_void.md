# WaasMedic::AutomaticCorruptionRepairPlugin::PerformAction(void)

- ea: `0x180038f50`
- end: `0x1800392db`
- name: `?PerformAction@AutomaticCorruptionRepairPlugin@WaasMedic@@UEAAJXZ`
- size: `907`
- prototype: `__int64 __fastcall(WaasMedic::AutomaticCorruptionRepairPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `16`
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
- `0x180038f50`
- `0x1800392e4`
- `0x1800395c4`
- `0x180039d3c`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800391f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800391f4`

## string_xrefs

- `0x18003901e`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x1800391ac`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180039202`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x18003923b`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x18003929c`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x1800390a2`: `SYSTEM\WaaS\Plugin`
- `0x1800390c7`: `SYSTEM\WaaS\Plugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::AutomaticCorruptionRepairPlugin::PerformAction(
        WaasMedic::AutomaticCorruptionRepairPlugin *this)
{
  __int64 (__fastcall ***v2)(_QWORD, _OWORD *, _OWORD *, _DWORD *); // rdi
  __int64 (__fastcall *v3)(_QWORD, _OWORD *, _OWORD *, _DWORD *); // r14
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // edi
  const OLECHAR *v10; // r8
  void *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  int v14; // ecx
  void *v16; // rbx
  signed __int32 v17; // esi
  HANDLE ProcessHeap; // rax
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-79h]
  _BYTE v21[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  __int64 v23; // [rsp+40h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-51h] BYREF
  int v25; // [rsp+50h] [rbp-49h] BYREF
  int v26; // [rsp+54h] [rbp-45h] BYREF
  _DWORD v27[2]; // [rsp+58h] [rbp-41h] BYREF
  char v28; // [rsp+60h] [rbp-39h]
  _BYTE v29[4]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v30[4]; // [rsp+6Ch] [rbp-2Dh] BYREF
  _OWORD v31[2]; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v32[2]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v28 = 0;
  v27[0] = 5;
  v27[1] = 2;
  v2 = (__int64 (__fastcall ***)(_QWORD, _OWORD *, _OWORD *, _DWORD *))*((_QWORD *)this + 13);
  v3 = **v2;
  memset(v32, 0, sizeof(v32));
  std::wstring::_Construct<1,unsigned short const *>(v32, L"ACRIterationCount", 17);
  v4 = *((_QWORD *)this + 14);
  memset(v31, 0, sizeof(v31));
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  std::wstring::_Construct<1,unsigned short const *>(v31, v4, v5);
  v6 = v3(v2, v31, v32, v27);
  std::wstring::~wstring(v31);
  std::wstring::~wstring(v32);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
      (const char *)(unsigned int)v6,
      v20);
    return (unsigned int)v6;
  }
  v21[0] = 0;
  while ( 1 )
  {
    winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper((winrt::Windows::Internal::WaasMedicDocked::CBSHelper *)&v22);
    v25 = 1;
    v26 = 0;
    v6 = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::Initialize(
                      &v22,
                      v29,
                      &v26,
                      &v25);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v6,
        v20);
      goto LABEL_49;
    }
    winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(
      &v22,
      &v23);
    v6 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,unsigned int>::get(&v23);
    if ( v6 == -2146498527 )
    {
      if ( v23 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
      return 2147943623LL;
    }
    LOBYTE(v20) = 0;
    v9 = WaasMedic::RegSetDwordValue(v7, L"SYSTEM\\WaaS\\Plugin", L"EscalateToMCR", 1);
    if ( v9 < 0 )
    {
      v19 = 226;
      goto LABEL_37;
    }
    LOBYTE(v20) = 0;
    v9 = WaasMedic::RegSetDwordValue(v8, L"SYSTEM\\WaaS\\Plugin", L"EscalatetoInPlaceUpgrade", 0);
    if ( v9 < 0 )
    {
      v19 = 228;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v9,
        v20);
LABEL_38:
      if ( v23 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
      return (unsigned int)v9;
    }
    if ( v6 < 0 )
      break;
    lpMem = 0;
    v9 = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::GetSessionReport(
                      &v22,
                      v30,
                      &lpMem,
                      v21);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
        (const char *)(unsigned int)v9,
        v20);
      v16 = lpMem;
      if ( lpMem )
      {
        v17 = _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 6, 0xFFFFFFFF);
        if ( v17 == 1 )
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v16);
        }
        else if ( v17 - 1 < 0 )
        {
LABEL_32:
          abort();
        }
        lpMem = 0;
      }
      goto LABEL_38;
    }
    if ( lpMem )
      v10 = (const OLECHAR *)*((_QWORD *)lpMem + 2);
    else
      v10 = &word_18006939C;
    LogLevelW(4u, L"CBS Report: %s", v10);
    v11 = lpMem;
    if ( lpMem )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          goto LABEL_32;
      }
      else
      {
        v13 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v13, 0, v11);
      }
      lpMem = 0;
    }
    if ( v23 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
    if ( v22 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
    if ( v21[0] )
    {
      v14 = v27[0]--;
      if ( v14 > 0 )
        continue;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE7,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
    (const char *)(unsigned int)v6,
    v20);
  if ( v23 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
LABEL_49:
  if ( v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180038f50  push    rbp
0x180038f52  push    rbx
0x180038f53  push    rsi
0x180038f54  push    rdi
0x180038f55  push    r14
0x180038f57  push    r15
0x180038f59  lea     rbp, [rsp-2Fh]
0x180038f5e  sub     rsp, 0C8h
0x180038f65  mov     rax, cs:__security_cookie
0x180038f6c  xor     rax, rsp
0x180038f6f  mov     [rbp+57h+var_40], rax
0x180038f73  mov     rbx, rcx
0x180038f76  xor     r15d, r15d
0x180038f79  mov     [rbp+57h+var_90], r15b
0x180038f7d  mov     [rbp+57h+var_98], 5
0x180038f84  mov     [rbp+57h+var_94], 2
0x180038f8b  mov     rdi, [rcx+68h]
0x180038f8f  mov     rax, [rdi]
0x180038f92  mov     r14, [rax]
0x180038f95  xorps   xmm0, xmm0
0x180038f98  movups  [rbp+57h+var_60], xmm0
0x180038f9c  xorps   xmm1, xmm1
0x180038f9f  movdqu  [rbp+57h+var_50], xmm1
0x180038fa4  lea     r8d, [r15+11h]
0x180038fa8  lea     rdx, aAcriterationco; "ACRIterationCount"
0x180038faf  lea     rcx, [rbp+57h+var_60]
0x180038fb3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180038fb8  nop
0x180038fb9  mov     rdx, [rbx+70h]
0x180038fbd  xorps   xmm0, xmm0
0x180038fc0  movups  [rbp+57h+var_80], xmm0
0x180038fc4  xorps   xmm1, xmm1
0x180038fc7  movdqu  [rbp+57h+var_70], xmm1
0x180038fcc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038fd0  mov     r8, rsi
0x180038fd3  inc     r8
0x180038fd6  cmp     [rdx+r8*2], r15w
0x180038fdb  jnz     short loc_180038FD3
0x180038fdd  lea     rcx, [rbp+57h+var_80]
0x180038fe1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180038fe6  nop
0x180038fe7  lea     r9, [rbp+57h+var_98]
0x180038feb  lea     r8, [rbp+57h+var_60]
0x180038fef  lea     rdx, [rbp+57h+var_80]
0x180038ff3  mov     rcx, rdi
0x180038ff6  mov     rax, r14
0x180038ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ffe  mov     ebx, eax
0x180039000  lea     rcx, [rbp+57h+var_80]; void *
0x180039004  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039009  nop
0x18003900a  lea     rcx, [rbp+57h+var_60]; void *
0x18003900e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039013  test    ebx, ebx
0x180039015  jns     short loc_180039034
0x180039017  mov     rcx, [rbp+5Fh]; this
0x18003901b  mov     r9d, ebx; char *
0x18003901e  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180039025  mov     edx, 0D2h; void *
0x18003902a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003902f  jmp     loc_1800392BD
0x180039034  mov     [rbp+57h+var_C0], r15b
0x180039038  mov     r14d, 1
0x18003903e  lea     rcx, [rbp+57h+var_B8]; this
0x180039042  call    ??0CBSHelper@WaasMedicDocked@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper(void)
0x180039047  nop
0x180039048  mov     [rbp+57h+var_A0], r14d
0x18003904c  mov     [rbp+57h+var_9C], r15d
0x180039050  lea     r9, [rbp+57h+var_A0]
0x180039054  lea     r8, [rbp+57h+var_9C]
0x180039058  lea     rdx, [rbp+57h+var_88]
0x18003905c  lea     rcx, [rbp+57h+var_B8]
0x180039060  call    ?Initialize@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4CorruptionRepairAction@WaasMedicDocked@Internal@Windows@3@AEBW4CorruptionRepairOption@5673@@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::Initialize(winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairAction const &,winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairOption const &)
0x180039065  mov     ebx, [rax]
0x180039067  test    ebx, ebx
0x180039069  js      loc_180039295
0x18003906f  lea     rdx, [rbp+57h+var_B0]
0x180039073  lea     rcx, [rbp+57h+var_B8]
0x180039077  call    ?PerformCorruptionRepair@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::PerformCorruptionRepair(void)
0x18003907c  nop
0x18003907d  lea     rcx, [rbp+57h+var_B0]
0x180039081  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@I@Foundation@Windows@winrt@@I@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<uint>,uint>::get(void)
0x180039086  mov     ebx, eax
0x180039088  cmp     eax, 800F0821h
0x18003908d  jz      loc_18003926F
0x180039093  mov     byte ptr [rsp+0F0h+var_D0], r15b; int
0x180039098  mov     r9d, r14d
0x18003909b  lea     r8, aEscalatetomcr; "EscalateToMCR"
0x1800390a2  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x1800390a9  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x1800390ae  mov     edi, eax
0x1800390b0  test    eax, eax
0x1800390b2  js      loc_180039233
0x1800390b8  mov     byte ptr [rsp+0F0h+var_D0], r15b; int
0x1800390bd  xor     r9d, r9d
0x1800390c0  lea     r8, aEscalatetoinpl; "EscalatetoInPlaceUpgrade"
0x1800390c7  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x1800390ce  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x1800390d3  mov     edi, eax
0x1800390d5  test    eax, eax
0x1800390d7  js      loc_18003922C
0x1800390dd  test    ebx, ebx
0x1800390df  js      loc_1800391FB
0x1800390e5  mov     [rbp+57h+lpMem], r15
0x1800390e9  lea     r9, [rbp+57h+var_C0]
0x1800390ed  lea     r8, [rbp+57h+lpMem]
0x1800390f1  lea     rdx, [rbp+57h+var_84]
0x1800390f5  lea     rcx, [rbp+57h+var_B8]
0x1800390f9  call    ?GetSessionReport@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEAUhstring@3@AEA_N@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::GetSessionReport(winrt::hstring &,bool &)
0x1800390fe  mov     edi, [rax]
0x180039100  test    edi, edi
0x180039102  js      loc_1800391A5
0x180039108  mov     rax, [rbp+57h+lpMem]
0x18003910c  test    rax, rax
0x18003910f  jz      short loc_180039117
0x180039111  mov     r8, [rax+10h]
0x180039115  jmp     short loc_18003911E
0x180039117  lea     r8, word_18006939C
0x18003911e  lea     rdx, aCbsReportS; "CBS Report: %s"
0x180039125  mov     ecx, 4; unsigned __int8
0x18003912a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003912f  nop
0x180039130  mov     rbx, [rbp+57h+lpMem]
0x180039134  test    rbx, rbx
0x180039137  jz      short loc_180039166
0x180039139  mov     eax, esi
0x18003913b  lock xadd [rbx+18h], eax
0x180039140  sub     eax, 1
0x180039143  jnz     short loc_18003915A
0x180039145  nop
0x180039146  call    WINRT_IMPL_GetProcessHeap
0x18003914b  mov     rcx, rax; hHeap
0x18003914e  mov     r8, rbx; lpMem
0x180039151  xor     edx, edx; dwFlags
0x180039153  call    WINRT_IMPL_HeapFree
0x180039158  jmp     short loc_180039162
0x18003915a  test    eax, eax
0x18003915c  js      loc_1800391F4
0x180039162  mov     [rbp+57h+lpMem], r15
0x180039166  cmp     [rbp+57h+var_B0], r15
0x18003916a  jz      short loc_180039176
0x18003916c  lea     rcx, [rbp+57h+var_B0]
0x180039170  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180039175  nop
0x180039176  cmp     [rbp+57h+var_B8], r15
0x18003917a  jz      short loc_180039185
0x18003917c  lea     rcx, [rbp+57h+var_B8]
0x180039180  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180039185  cmp     [rbp+57h+var_C0], r15b
0x180039189  jz      short loc_18003919E
0x18003918b  mov     eax, [rbp+57h+var_98]
0x18003918e  mov     ecx, eax
0x180039190  sub     eax, r14d
0x180039193  mov     [rbp+57h+var_98], eax
0x180039196  test    ecx, ecx
0x180039198  jg      loc_18003903E
0x18003919e  xor     eax, eax
0x1800391a0  jmp     loc_1800392BF
0x1800391a5  mov     rcx, [rbp+5Fh]; this
0x1800391a9  mov     r9d, edi; char *
0x1800391ac  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800391b3  mov     edx, 0EAh; void *
0x1800391b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391bd  nop
0x1800391be  mov     rbx, [rbp+57h+lpMem]
0x1800391c2  test    rbx, rbx
0x1800391c5  jz      loc_18003924C
0x1800391cb  lock xadd [rbx+18h], esi
0x1800391d0  lea     eax, [rsi-1]
0x1800391d3  test    eax, eax
0x1800391d5  jnz     short loc_1800391EC
0x1800391d7  nop
0x1800391d8  call    WINRT_IMPL_GetProcessHeap
0x1800391dd  mov     rcx, rax; hHeap
0x1800391e0  mov     r8, rbx; lpMem
0x1800391e3  xor     edx, edx; dwFlags
0x1800391e5  call    WINRT_IMPL_HeapFree
0x1800391ea  jmp     short loc_1800391EE
0x1800391ec  js      short loc_1800391F4
0x1800391ee  mov     [rbp+57h+lpMem], r15
0x1800391f2  jmp     short loc_18003924C
0x1800391f4  call    cs:__imp_abort
0x1800391fb  mov     rcx, [rbp+5Fh]; this
0x1800391ff  mov     r9d, ebx; char *
0x180039202  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180039209  mov     edx, 0E7h; void *
0x18003920e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039213  nop
0x180039214  cmp     [rbp+57h+var_B0], r15
0x180039218  jz      loc_1800392AE
0x18003921e  lea     rcx, [rbp+57h+var_B0]
0x180039222  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180039227  jmp     loc_1800392AE
0x18003922c  mov     edx, 0E4h
0x180039231  jmp     short loc_180039238
0x180039233  mov     edx, 0E2h; void *
0x180039238  mov     r9d, edi; char *
0x18003923b  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180039242  mov     rcx, [rbp+5Fh]; this
0x180039246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003924b  nop
0x18003924c  cmp     [rbp+57h+var_B0], r15
0x180039250  jz      short loc_18003925C
0x180039252  lea     rcx, [rbp+57h+var_B0]
0x180039256  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003925b  nop
0x18003925c  cmp     [rbp+57h+var_B8], r15
0x180039260  jz      short loc_18003926B
0x180039262  lea     rcx, [rbp+57h+var_B8]
0x180039266  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003926b  mov     eax, edi
0x18003926d  jmp     short loc_1800392BF
0x18003926f  cmp     [rbp+57h+var_B0], r15
0x180039273  jz      short loc_18003927F
0x180039275  lea     rcx, [rbp+57h+var_B0]
0x180039279  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003927e  nop
0x18003927f  cmp     [rbp+57h+var_B8], r15
0x180039283  jz      short loc_18003928E
0x180039285  lea     rcx, [rbp+57h+var_B8]
0x180039289  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003928e  mov     eax, 800704C7h
0x180039293  jmp     short loc_1800392BF
0x180039295  mov     rcx, [rbp+5Fh]; this
0x180039299  mov     r9d, ebx; char *
0x18003929c  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800392a3  mov     edx, 0D8h; void *
0x1800392a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392ad  nop
0x1800392ae  cmp     [rbp+57h+var_B8], r15
0x1800392b2  jz      short loc_1800392BD
0x1800392b4  lea     rcx, [rbp+57h+var_B8]
0x1800392b8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800392bd  mov     eax, ebx
0x1800392bf  mov     rcx, [rbp+57h+var_40]
0x1800392c3  xor     rcx, rsp; StackCookie
0x1800392c6  call    __security_check_cookie
0x1800392cb  add     rsp, 0C8h
0x1800392d2  pop     r15
0x1800392d4  pop     r14
0x1800392d6  pop     rdi
0x1800392d7  pop     rsi
0x1800392d8  pop     rbx
0x1800392d9  pop     rbp
0x1800392da  retn
```
