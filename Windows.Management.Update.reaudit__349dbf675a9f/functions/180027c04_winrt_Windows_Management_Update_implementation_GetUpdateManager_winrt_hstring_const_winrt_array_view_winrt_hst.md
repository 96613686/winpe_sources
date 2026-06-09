# winrt::Windows::Management::Update::implementation::GetUpdateManager(winrt::hstring const &,winrt::array_view<winrt::hstring const>)

- ea: `0x180027c04`
- end: `0x180028080`
- name: `?GetUpdateManager@implementation@Update@Management@Windows@winrt@@YA?AUWindowsUpdateManager@2345@AEBUhstring@5@U?$array_view@$$CBUhstring@winrt@@@5@@Z`
- size: `1148`
- prototype: `IUnknown **__fastcall(IUnknown **, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800140d0`
- `0x180014190`

## callees

- `0x180002880`
- `0x180005330`
- `0x1800055f0`
- `0x180005930`
- `0x1800061c0`
- `0x1800085f0`
- `0x180017c3c`
- `0x1800188d4`
- `0x18001d9e8`
- `0x18001da30`
- `0x18001db60`
- `0x18001e7a4`
- `0x180027c04`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027c8d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027e7c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027efd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027f45`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027e7c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027efd`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180027f45`

## string_xrefs

- `0x18002800e`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180028023`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x180028038`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x180028059`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x18002806e`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
IUnknown **__fastcall winrt::Windows::Management::Update::implementation::GetUpdateManager(
        IUnknown **a1,
        __int64 a2,
        __int64 a3)
{
  IUnknown *pAuthInfo; // r15
  const unsigned __int16 *v7; // r12
  HRESULT v8; // eax
  __int64 v9; // rsi
  __int64 *v10; // rdi
  __int64 v11; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, const unsigned __int16 *, __int128 *, __int128 *); // rdi
  __int128 *v19; // r8
  int v20; // eax
  HRESULT v21; // eax
  IUnknown *v22; // rcx
  IUnknown *v23; // rsi
  int v24; // eax
  HRESULT v25; // eax
  void (*v26)(void); // rax
  HRESULT v27; // eax
  IUnknown *v28; // rax
  int v29; // eax
  int ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  int ppvb; // [rsp+20h] [rbp-89h]
  int ppvc; // [rsp+20h] [rbp-89h]
  IUnknown *pProxy; // [rsp+40h] [rbp-69h] BYREF
  IUnknown *v36; // [rsp+48h] [rbp-61h] BYREF
  LPVOID v37; // [rsp+50h] [rbp-59h] BYREF
  IUnknown *v38; // [rsp+58h] [rbp-51h] BYREF
  int v39; // [rsp+60h] [rbp-49h]
  _BYTE v40[24]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v41; // [rsp+88h] [rbp-21h]
  __int128 v42; // [rsp+90h] [rbp-19h] BYREF
  __int128 v43; // [rsp+A0h] [rbp-9h]
  __int128 v44; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v38 = (IUnknown *)a1;
  pAuthInfo = 0;
  v42 = 0;
  v43 = 0;
  v7 = &dword_180030C44;
  std::wstring::_Construct<1,unsigned short const *>(&v42, &dword_180030C44, 0);
  v39 = 4;
  v37 = 0;
  v8 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_f0e6970d_b5ad_430e_a0ce_7e3aedc453ff,
         &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v8,
      ppv);
  pProxy = 0;
  v44 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    web::json::value::array(&v36);
    if ( *(_DWORD *)(a3 + 8) )
    {
      v9 = 0;
      v10 = *(__int64 **)a3;
      pAuthInfo = (IUnknown *)*(unsigned int *)(a3 + 8);
      do
      {
        memset(v40, 0, sizeof(v40));
        v41 = 0;
        v11 = *v10;
        if ( *v10 )
        {
          v12 = *(const unsigned __int16 **)(v11 + 16);
          v13 = *(unsigned int *)(v11 + 4);
        }
        else
        {
          v12 = &dword_180030C44;
          v13 = 0;
        }
        std::wstring::_Construct<1,unsigned short const *>(v40, v12, v13);
        v14 = web::json::value::value(&v38, v40);
        v15 = web::json::value::operator[](&v36, v9);
        web::json::value::operator=(v15, v14);
        if ( v38 )
          ((void (__fastcall *)(IUnknown *, __int64))v38->lpVtbl[8].QueryInterface)(v38, 1);
        ++v9;
        ++v10;
        pAuthInfo = (IUnknown *)((char *)pAuthInfo - 1);
      }
      while ( pAuthInfo );
    }
    v16 = web::json::value::serialize(&v36, v40);
    if ( &v42 != (__int128 *)v16 )
    {
      std::wstring::_Tidy_deallocate(&v42);
      v42 = *(_OWORD *)v16;
      v43 = *(_OWORD *)(v16 + 16);
      *(_QWORD *)(v16 + 16) = pAuthInfo;
      *(_QWORD *)(v16 + 24) = 7;
      *(_WORD *)v16 = (_WORD)pAuthInfo;
    }
    std::wstring::_Tidy_deallocate(v40);
    v44 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>;
    if ( v36 )
      ((void (__fastcall *)(IUnknown *, __int64))v36->lpVtbl[8].QueryInterface)(v36, 1);
  }
  v17 = v37;
  v18 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int128 *, __int128 *))(*(_QWORD *)v37 + 48LL);
  if ( pProxy != pAuthInfo )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
  v19 = &v42;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    v19 = (__int128 *)v42;
  if ( *(_QWORD *)a2 )
    v7 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  v20 = v18(v17, v7, v19, &v44);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owsupdatemanager.cpp",
      (const char *)(unsigned int)v20,
      (int)&pProxy);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v21 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            (DWORD)pAuthInfo,
            3u,
            pAuthInfo,
            (DWORD)pAuthInfo);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v21,
        ppva);
    if ( pProxy )
    {
      v36 = pAuthInfo;
      *(_DWORD *)v40 = (_DWORD)pAuthInfo;
      *(_OWORD *)&v40[8] = 0;
      v24 = ((__int64 (__fastcall *)(IUnknown *, __int128 *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
              pProxy,
              &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>,
              &v36);
      if ( v24 < 0 )
        winrt::throw_hresult((unsigned int)v24, v40);
      v22 = v36;
      v23 = v36;
    }
    else
    {
      v22 = pAuthInfo;
      v23 = pAuthInfo;
    }
    v38 = v22;
    v25 = CoSetProxyBlanket(
            v22,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            (DWORD)pAuthInfo,
            3u,
            pAuthInfo,
            (DWORD)pAuthInfo);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v25,
        ppvb);
    *a1 = v23;
    if ( pProxy != pAuthInfo )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
    if ( v37 )
    {
      v26 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
LABEL_42:
      v26();
    }
  }
  else
  {
    v27 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            (DWORD)pAuthInfo,
            3u,
            pAuthInfo,
            (DWORD)pAuthInfo);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v27,
        ppvc);
    v28 = pProxy;
    if ( pProxy )
    {
      v36 = pAuthInfo;
      *(_DWORD *)v40 = (_DWORD)pAuthInfo;
      *(_OWORD *)&v40[8] = 0;
      v29 = ((__int64 (__fastcall *)(IUnknown *, __int128 *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
              pProxy,
              &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>,
              &v36);
      if ( v29 < 0 )
        winrt::throw_hresult((unsigned int)v29, v40);
      *a1 = v36;
      v28 = pProxy;
    }
    else
    {
      *a1 = pAuthInfo;
    }
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
    if ( v37 )
    {
      v26 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
      goto LABEL_42;
    }
  }
  std::wstring::_Tidy_deallocate(&v42);
  return a1;
}

```

## disassembly

```asm
0x180027c04  mov     [rsp-8+arg_10], rbx
0x180027c09  push    rbp
0x180027c0a  push    rsi
0x180027c0b  push    rdi
0x180027c0c  push    r12
0x180027c0e  push    r13
0x180027c10  push    r14
0x180027c12  push    r15
0x180027c14  lea     rbp, [rsp-27h]
0x180027c19  sub     rsp, 0D0h
0x180027c20  mov     rax, cs:__security_cookie
0x180027c27  xor     rax, rsp
0x180027c2a  mov     [rbp+57h+var_40], rax
0x180027c2e  mov     rbx, r8
0x180027c31  mov     r13, rdx
0x180027c34  mov     r14, rcx
0x180027c37  mov     [rbp+57h+var_A8], rcx
0x180027c3b  xor     r15d, r15d
0x180027c3e  mov     [rbp+57h+var_A0], r15d
0x180027c42  xorps   xmm0, xmm0
0x180027c45  movups  [rbp+57h+var_70], xmm0
0x180027c49  xorps   xmm1, xmm1
0x180027c4c  movdqu  [rbp+57h+var_60], xmm1
0x180027c51  xor     r8d, r8d
0x180027c54  lea     r12, dword_180030C44
0x180027c5b  mov     rdx, r12
0x180027c5e  lea     rcx, [rbp+57h+var_70]
0x180027c62  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027c67  nop
0x180027c68  lea     r8d, [r15+4]; dwClsContext
0x180027c6c  mov     [rbp+57h+var_A0], r8d
0x180027c70  mov     [rbp+57h+var_B0], r15
0x180027c74  lea     rax, [rbp+57h+var_B0]
0x180027c78  mov     [rsp+100h+ppv], rax; int
0x180027c7d  lea     r9, _GUID_f0e6970d_b5ad_430e_a0ce_7e3aedc453ff; riid
0x180027c84  xor     edx, edx; pUnkOuter
0x180027c86  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180027c8d  call    cs:__imp_CoCreateInstance
0x180027c94  nop     dword ptr [rax+rax+00h]
0x180027c99  mov     rcx, [rbp+5Fh]; this
0x180027c9d  test    eax, eax
0x180027c9f  js      loc_18002800B
0x180027ca5  mov     [rbp+57h+pProxy], r15
0x180027ca9  movups  xmm0, cs:??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180027cb0  movdqu  [rbp+57h+var_50], xmm0
0x180027cb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180027cbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180027cc1  test    al, al
0x180027cc3  jz      loc_180027DE2
0x180027cc9  lea     rcx, [rbp+57h+var_B8]
0x180027ccd  call    ?array@value@json@web@@SA?AV123@XZ; web::json::value::array(void)
0x180027cd2  nop
0x180027cd3  cmp     [rbx+8], r15d
0x180027cd7  jbe     loc_180027D6F
0x180027cdd  mov     esi, r15d
0x180027ce0  mov     rdi, [rbx]
0x180027ce3  mov     r15d, [rbx+8]
0x180027ce7  xorps   xmm0, xmm0
0x180027cea  movups  [rbp+57h+var_90], xmm0
0x180027cee  and     [rbp+57h+var_80], 0
0x180027cf3  and     [rbp+57h+var_78], 0
0x180027cf8  mov     rax, [rdi]
0x180027cfb  test    rax, rax
0x180027cfe  jz      short loc_180027D0A
0x180027d00  mov     rdx, [rax+10h]
0x180027d04  mov     r8d, [rax+4]
0x180027d08  jmp     short loc_180027D10
0x180027d0a  mov     rdx, r12
0x180027d0d  xor     r8d, r8d
0x180027d10  lea     rcx, [rbp+57h+var_90]
0x180027d14  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027d19  lea     rdx, [rbp+57h+var_90]
0x180027d1d  lea     rcx, [rbp+57h+var_A8]
0x180027d21  call    ??0value@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::value(std::wstring)
0x180027d26  mov     rbx, rax
0x180027d29  mov     rdx, rsi
0x180027d2c  lea     rcx, [rbp+57h+var_B8]
0x180027d30  call    ??Avalue@json@web@@QEAAAEAV012@_K@Z; web::json::value::operator[](unsigned __int64)
0x180027d35  mov     rcx, rax
0x180027d38  mov     rdx, rbx
0x180027d3b  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180027d40  nop
0x180027d41  mov     rcx, [rbp+57h+var_A8]
0x180027d45  test    rcx, rcx
0x180027d48  jz      short loc_180027D5E
0x180027d4a  mov     rax, [rcx]
0x180027d4d  mov     edx, 1
0x180027d52  mov     rax, [rax+0C0h]
0x180027d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d5e  inc     rsi
0x180027d61  add     rdi, 8
0x180027d65  sub     r15, 1
0x180027d69  jnz     loc_180027CE7
0x180027d6f  lea     rdx, [rbp+57h+var_90]
0x180027d73  lea     rcx, [rbp+57h+var_B8]
0x180027d77  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x180027d7c  mov     rbx, rax
0x180027d7f  lea     rax, [rbp+57h+var_70]
0x180027d83  cmp     rax, rbx
0x180027d86  jz      short loc_180027DB0
0x180027d88  lea     rcx, [rbp+57h+var_70]
0x180027d8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027d91  movups  xmm0, xmmword ptr [rbx]
0x180027d94  movups  [rbp+57h+var_70], xmm0
0x180027d98  movups  xmm1, xmmword ptr [rbx+10h]
0x180027d9c  movups  [rbp+57h+var_60], xmm1
0x180027da0  mov     [rbx+10h], r15
0x180027da4  mov     qword ptr [rbx+18h], 7
0x180027dac  mov     [rbx], r15w
0x180027db0  lea     rcx, [rbp+57h+var_90]
0x180027db4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027db9  movups  xmm0, cs:??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x180027dc0  movdqu  [rbp+57h+var_50], xmm0
0x180027dc5  mov     rcx, [rbp+57h+var_B8]
0x180027dc9  test    rcx, rcx
0x180027dcc  jz      short loc_180027DE2
0x180027dce  mov     rax, [rcx]
0x180027dd1  mov     edx, 1
0x180027dd6  mov     rax, [rax+0C0h]
0x180027ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027de2  mov     rbx, [rbp+57h+var_B0]
0x180027de6  mov     rax, [rbx]
0x180027de9  mov     rdi, [rax+30h]
0x180027ded  cmp     [rbp+57h+pProxy], r15
0x180027df1  jz      short loc_180027DFC
0x180027df3  lea     rcx, [rbp+57h+pProxy]
0x180027df7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027dfc  lea     r8, [rbp+57h+var_70]
0x180027e00  cmp     qword ptr [rbp+57h+var_60+8], 7
0x180027e05  cmova   r8, qword ptr [rbp+57h+var_70]
0x180027e0a  mov     rax, [r13+0]
0x180027e0e  test    rax, rax
0x180027e11  jz      short loc_180027E17
0x180027e13  mov     r12, [rax+10h]
0x180027e17  lea     rax, [rbp+57h+pProxy]
0x180027e1b  mov     [rsp+100h+ppv], rax; int
0x180027e20  lea     r9, [rbp+57h+var_50]
0x180027e24  mov     rdx, r12
0x180027e27  mov     rcx, rbx
0x180027e2a  mov     rax, rdi
0x180027e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e32  mov     rcx, [rbp+5Fh]; this
0x180027e36  test    eax, eax
0x180027e38  js      loc_180028020
0x180027e3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x180027e45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180027e4a  mov     [rsp+100h+dwCapabilities], r15d; dwCapabilities
0x180027e4f  or      ebx, 0FFFFFFFFh
0x180027e52  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180027e56  mov     [rsp+100h+pAuthInfo], r15; pAuthInfo
0x180027e5b  mov     r8d, ebx; dwAuthzSvc
0x180027e5e  mov     edx, ebx; dwAuthnSvc
0x180027e60  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x180027e68  mov     dword ptr [rsp+100h+ppv], r15d; int
0x180027e6d  test    al, al
0x180027e6f  jz      loc_180027F41
0x180027e75  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027e79  mov     r9, rdi; pServerPrincName
0x180027e7c  call    cs:__imp_CoSetProxyBlanket
0x180027e83  nop     dword ptr [rax+rax+00h]
0x180027e88  mov     rcx, [rbp+5Fh]; this
0x180027e8c  test    eax, eax
0x180027e8e  js      loc_180028035
0x180027e94  mov     rcx, [rbp+57h+pProxy]
0x180027e98  test    rcx, rcx
0x180027e9b  jnz     short loc_180027EA5
0x180027e9d  mov     rcx, r15
0x180027ea0  mov     rsi, r15
0x180027ea3  jmp     short loc_180027EDA
0x180027ea5  mov     [rbp+57h+var_B8], r15
0x180027ea9  mov     dword ptr [rbp+57h+var_90], r15d
0x180027ead  xorps   xmm0, xmm0
0x180027eb0  movdqu  [rbp+57h+var_90+8], xmm0
0x180027eb5  mov     rax, [rcx]
0x180027eb8  lea     r8, [rbp+57h+var_B8]
0x180027ebc  lea     rdx, ??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180027ec3  mov     rax, [rax]
0x180027ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ecb  test    eax, eax
0x180027ecd  js      loc_18002804A
0x180027ed3  mov     rcx, [rbp+57h+var_B8]; pProxy
0x180027ed7  mov     rsi, rcx
0x180027eda  mov     [rbp+57h+var_A8], rcx
0x180027ede  mov     [rsp+100h+dwCapabilities], r15d; dwCapabilities
0x180027ee3  mov     [rsp+100h+pAuthInfo], r15; pAuthInfo
0x180027ee8  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x180027ef0  mov     dword ptr [rsp+100h+ppv], r15d; int
0x180027ef5  mov     r9, rdi; pServerPrincName
0x180027ef8  mov     r8d, ebx; dwAuthzSvc
0x180027efb  mov     edx, ebx; dwAuthnSvc
0x180027efd  call    cs:__imp_CoSetProxyBlanket
0x180027f04  nop     dword ptr [rax+rax+00h]
0x180027f09  mov     rcx, [rbp+5Fh]; this
0x180027f0d  test    eax, eax
0x180027f0f  js      loc_180028056
0x180027f15  mov     [r14], rsi
0x180027f18  cmp     [rbp+57h+pProxy], r15
0x180027f1c  jz      short loc_180027F28
0x180027f1e  lea     rcx, [rbp+57h+pProxy]
0x180027f22  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027f27  nop
0x180027f28  mov     rcx, [rbp+57h+var_B0]
0x180027f2c  test    rcx, rcx
0x180027f2f  jz      loc_180027FCB
0x180027f35  mov     rax, [rcx]
0x180027f38  mov     rax, [rax+10h]
0x180027f3c  jmp     loc_180027FC5
0x180027f41  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180027f45  call    cs:__imp_CoSetProxyBlanket
0x180027f4c  nop     dword ptr [rax+rax+00h]
0x180027f51  mov     rcx, [rbp+5Fh]; this
0x180027f55  test    eax, eax
0x180027f57  js      loc_18002806B
0x180027f5d  mov     rax, [rbp+57h+pProxy]
0x180027f61  test    rax, rax
0x180027f64  jnz     short loc_180027F6B
0x180027f66  mov     [r14], r15
0x180027f69  jmp     short loc_180027FA6
0x180027f6b  mov     [rbp+57h+var_B8], r15
0x180027f6f  mov     dword ptr [rbp+57h+var_90], r15d
0x180027f73  xorps   xmm0, xmm0
0x180027f76  movdqu  [rbp+57h+var_90+8], xmm0
0x180027f7b  mov     rcx, [rax]
0x180027f7e  mov     r9, [rcx]
0x180027f81  lea     r8, [rbp+57h+var_B8]
0x180027f85  lea     rdx, ??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180027f8c  mov     rcx, rax
0x180027f8f  mov     rax, r9
0x180027f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f97  test    eax, eax
0x180027f99  js      short loc_180027FFF
0x180027f9b  mov     rax, [rbp+57h+var_B8]
0x180027f9f  mov     [r14], rax
0x180027fa2  mov     rax, [rbp+57h+pProxy]
0x180027fa6  test    rax, rax
0x180027fa9  jz      short loc_180027FB5
0x180027fab  lea     rcx, [rbp+57h+pProxy]
0x180027faf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027fb4  nop
0x180027fb5  mov     rcx, [rbp+57h+var_B0]
0x180027fb9  test    rcx, rcx
0x180027fbc  jz      short loc_180027FCB
0x180027fbe  mov     rdx, [rcx]
0x180027fc1  mov     rax, [rdx+10h]
0x180027fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fca  nop
0x180027fcb  lea     rcx, [rbp+57h+var_70]
0x180027fcf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027fd4  mov     rax, r14
0x180027fd7  mov     rcx, [rbp+57h+var_40]
0x180027fdb  xor     rcx, rsp; StackCookie
0x180027fde  call    __security_check_cookie
0x180027fe3  mov     rbx, [rsp+100h+arg_10]
0x180027feb  add     rsp, 0D0h
0x180027ff2  pop     r15
0x180027ff4  pop     r14
0x180027ff6  pop     r13
0x180027ff8  pop     r12
0x180027ffa  pop     rdi
0x180027ffb  pop     rsi
0x180027ffc  pop     rbp
0x180027ffd  retn
0x180027fff  lea     rdx, [rbp+57h+var_90]
0x180028003  mov     ecx, eax
0x180028005  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002800b  mov     r9d, eax; char *
0x18002800e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028015  mov     edx, 1C60h; void *
0x18002801a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028020  mov     r9d, eax; char *
0x180028023  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002802a  mov     edx, 26h ; '&'; void *
0x18002802f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028035  mov     r9d, eax; char *
0x180028038  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002803f  mov     edx, 35h ; '5'; void *
0x180028044  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002804a  lea     rdx, [rbp+57h+var_90]
0x18002804e  mov     ecx, eax
0x180028050  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028056  mov     r9d, eax; char *
0x180028059  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180028060  mov     edx, 43h ; 'C'; void *
0x180028065  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002806b  mov     r9d, eax; char *
0x18002806e  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180028075  mov     edx, 52h ; 'R'; void *
0x18002807a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
