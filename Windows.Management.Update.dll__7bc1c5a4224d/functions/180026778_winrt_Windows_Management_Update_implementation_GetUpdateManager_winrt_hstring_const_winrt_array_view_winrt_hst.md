# winrt::Windows::Management::Update::implementation::GetUpdateManager(winrt::hstring const &,winrt::array_view<winrt::hstring const>)

- ea: `0x180026778`
- end: `0x180026bdf`
- name: `?GetUpdateManager@implementation@Update@Management@Windows@winrt@@YA?AUWindowsUpdateManager@2345@AEBUhstring@5@U?$array_view@$$CBUhstring@winrt@@@5@@Z`
- size: `1127`
- prototype: `IUnknown **__fastcall(IUnknown **, IUnknown *, __int64 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800134d0`
- `0x180013590`

## callees

- `0x1800028f0`
- `0x180004ce0`
- `0x180005010`
- `0x180005380`
- `0x180005bd0`
- `0x1800080b0`
- `0x180016fe4`
- `0x180017bec`
- `0x18001c7d4`
- `0x18001c81c`
- `0x18001c8a0`
- `0x18001d50c`
- `0x180026778`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800269f7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026a72`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026ab1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800269f7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026a72`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026ab1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026805`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026805`

## string_xrefs

- `0x180026b6d`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180026b82`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x180026b97`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x180026bb8`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`
- `0x180026bcd`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowsupdatemanager.cpp`

## pseudocode

```c
IUnknown **__fastcall winrt::Windows::Management::Update::implementation::GetUpdateManager(
        IUnknown **a1,
        IUnknown *a2,
        __int64 *a3)
{
  IUnknown *v4; // r12
  int *Release; // r15
  HRESULT v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r13
  __int64 v10; // rax
  int *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  LPVOID v16; // rbx
  __int64 (__fastcall *v17)(LPVOID, int *, __int128 *, __int128 *); // rdi
  __int128 *v18; // r8
  int v19; // eax
  HRESULT v20; // eax
  IUnknown *v21; // rcx
  IUnknown *v22; // r14
  int v23; // eax
  HRESULT v24; // eax
  void (*v25)(void); // rax
  HRESULT v26; // eax
  IUnknown *v27; // rcx
  int v28; // eax
  int ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  int ppvb; // [rsp+20h] [rbp-89h]
  int ppvc; // [rsp+20h] [rbp-89h]
  IUnknown *pProxy; // [rsp+40h] [rbp-69h] BYREF
  IUnknown *v35; // [rsp+48h] [rbp-61h] BYREF
  LPVOID v36; // [rsp+50h] [rbp-59h] BYREF
  int v37; // [rsp+58h] [rbp-51h]
  IUnknown *v38; // [rsp+60h] [rbp-49h]
  IUnknown **v39; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v40[24]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v41; // [rsp+90h] [rbp-19h]
  __int128 v42; // [rsp+98h] [rbp-11h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-1h]
  __int128 v44; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = a2;
  v38 = a2;
  v39 = a1;
  v42 = 0;
  v43 = 0;
  Release = &dword_18002EB94;
  std::wstring::_Construct<1,unsigned short const *>(&v42, &dword_18002EB94, 0);
  v37 = 4;
  v36 = 0;
  v7 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_f0e6970d_b5ad_430e_a0ce_7e3aedc453ff,
         &v36);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v7,
      ppv);
  pProxy = 0;
  v44 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    web::json::value::array(&v35);
    if ( *((_DWORD *)a3 + 2) )
    {
      v8 = 0;
      v9 = *a3;
      do
      {
        memset(v40, 0, sizeof(v40));
        v41 = 0;
        v10 = *(_QWORD *)(v9 + 8LL * v8);
        if ( v10 )
        {
          v11 = *(int **)(v10 + 16);
          v12 = *(unsigned int *)(v10 + 4);
        }
        else
        {
          v11 = &dword_18002EB94;
          v12 = 0;
        }
        std::wstring::_Construct<1,unsigned short const *>(v40, v11, v12);
        v13 = web::json::value::value(&v39, v40);
        v14 = web::json::value::operator[](&v35, v8);
        web::json::value::operator=(v14, v13);
        if ( v39 )
          ((void (__fastcall *)(IUnknown **, __int64))(*v39)[24].lpVtbl)(v39, 1);
        ++v8;
      }
      while ( v8 < *((_DWORD *)a3 + 2) );
      v4 = v38;
    }
    v15 = web::json::value::serialize(&v35, v40);
    if ( &v42 != (__int128 *)v15 )
    {
      std::wstring::_Tidy_deallocate(&v42);
      v42 = *(_OWORD *)v15;
      v43 = *(_OWORD *)(v15 + 16);
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 7;
      *(_WORD *)v15 = 0;
    }
    std::wstring::_Tidy_deallocate(v40);
    v44 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>;
    if ( v35 )
      ((void (__fastcall *)(IUnknown *, __int64))v35->lpVtbl[8].QueryInterface)(v35, 1);
  }
  v16 = v36;
  v17 = *(__int64 (__fastcall **)(LPVOID, int *, __int128 *, __int128 *))(*(_QWORD *)v36 + 48LL);
  if ( pProxy )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
  v18 = &v42;
  if ( *((_QWORD *)&v43 + 1) > 7u )
    v18 = (__int128 *)v42;
  if ( v4->lpVtbl )
    Release = (int *)v4->lpVtbl->Release;
  v19 = v17(v16, Release, v18, &v44);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owsupdatemanager.cpp",
      (const char *)(unsigned int)v19,
      (int)&pProxy);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl'::`2'::impl) )
  {
    v20 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v20,
        ppva);
    if ( pProxy )
    {
      v35 = 0;
      *(_DWORD *)v40 = 0;
      *(_OWORD *)&v40[8] = 0;
      v23 = ((__int64 (__fastcall *)(IUnknown *, __int128 *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
              pProxy,
              &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>,
              &v35);
      if ( v23 < 0 )
        winrt::throw_hresult((unsigned int)v23, v40);
      v21 = v35;
      v22 = v35;
    }
    else
    {
      v21 = 0;
      v22 = 0;
    }
    v38 = v21;
    v24 = CoSetProxyBlanket(v21, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v24,
        ppvb);
    *a1 = v22;
    if ( pProxy )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
    if ( v36 )
    {
      v25 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
LABEL_43:
      v25();
    }
  }
  else
  {
    v26 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wi"
                      "ndowsupdatemanager.cpp",
        (const char *)(unsigned int)v26,
        ppvc);
    v27 = pProxy;
    if ( pProxy )
    {
      v35 = 0;
      *(_DWORD *)v40 = 0;
      *(_OWORD *)&v40[8] = 0;
      v28 = ((__int64 (__fastcall *)(IUnknown *, __int128 *, IUnknown **))pProxy->lpVtbl->QueryInterface)(
              pProxy,
              &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>,
              &v35);
      if ( v28 < 0 )
        winrt::throw_hresult((unsigned int)v28, v40);
      *a1 = v35;
      v27 = pProxy;
    }
    else
    {
      *a1 = 0;
    }
    if ( v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
    if ( v36 )
    {
      v25 = *(void (**)(void))(*(_QWORD *)v36 + 16LL);
      goto LABEL_43;
    }
  }
  std::wstring::_Tidy_deallocate(&v42);
  return a1;
}

```

## disassembly

```asm
0x180026778  mov     [rsp-8+arg_10], rbx
0x18002677d  push    rbp
0x18002677e  push    rsi
0x18002677f  push    rdi
0x180026780  push    r12
0x180026782  push    r13
0x180026784  push    r14
0x180026786  push    r15
0x180026788  lea     rbp, [rsp-27h]
0x18002678d  sub     rsp, 0D0h
0x180026794  mov     rax, cs:__security_cookie
0x18002679b  xor     rax, rsp
0x18002679e  mov     [rbp+57h+var_38], rax
0x1800267a2  mov     r14, r8
0x1800267a5  mov     r12, rdx
0x1800267a8  mov     [rbp+57h+var_A0], rdx
0x1800267ac  mov     rsi, rcx
0x1800267af  mov     [rbp+57h+var_98], rcx
0x1800267b3  xor     r13d, r13d
0x1800267b6  mov     [rbp+57h+var_A8], r13d
0x1800267ba  xorps   xmm0, xmm0
0x1800267bd  movups  [rbp+57h+var_68], xmm0
0x1800267c1  xorps   xmm1, xmm1
0x1800267c4  movdqu  [rbp+57h+var_58], xmm1
0x1800267c9  xor     r8d, r8d
0x1800267cc  lea     r15, dword_18002EB94
0x1800267d3  mov     rdx, r15
0x1800267d6  lea     rcx, [rbp+57h+var_68]
0x1800267da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800267df  nop
0x1800267e0  lea     r8d, [r13+4]; dwClsContext
0x1800267e4  mov     [rbp+57h+var_A8], r8d
0x1800267e8  mov     [rbp+57h+var_B0], r13
0x1800267ec  lea     rax, [rbp+57h+var_B0]
0x1800267f0  mov     [rsp+100h+ppv], rax; int
0x1800267f5  lea     r9, _GUID_f0e6970d_b5ad_430e_a0ce_7e3aedc453ff; riid
0x1800267fc  xor     edx, edx; pUnkOuter
0x1800267fe  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180026805  call    cs:__imp_CoCreateInstance
0x18002680b  mov     rcx, [rbp+5Fh]; this
0x18002680f  test    eax, eax
0x180026811  js      loc_180026B6A
0x180026817  mov     [rbp+57h+pProxy], r13
0x18002681b  movups  xmm0, cs:??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180026822  movdqu  [rbp+57h+var_48], xmm0
0x180026827  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x18002682e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x180026833  test    al, al
0x180026835  jz      loc_18002695D
0x18002683b  lea     rcx, [rbp+57h+var_B8]
0x18002683f  call    ?array@value@json@web@@SA?AV123@XZ; web::json::value::array(void)
0x180026844  nop
0x180026845  cmp     [r14+8], r13d
0x180026849  jbe     loc_1800268EA
0x18002684f  mov     edi, r13d
0x180026852  mov     r13, [r14]
0x180026855  mov     r12d, edi
0x180026858  xorps   xmm0, xmm0
0x18002685b  movups  [rbp+57h+var_88], xmm0
0x18002685f  mov     [rbp+57h+var_78], 0
0x180026867  mov     [rbp+57h+var_70], 0
0x18002686f  mov     rax, [r13+r12*8+0]
0x180026874  test    rax, rax
0x180026877  jz      short loc_180026883
0x180026879  mov     rdx, [rax+10h]
0x18002687d  mov     r8d, [rax+4]
0x180026881  jmp     short loc_180026889
0x180026883  mov     rdx, r15
0x180026886  xor     r8d, r8d
0x180026889  lea     rcx, [rbp+57h+var_88]
0x18002688d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026892  lea     rdx, [rbp+57h+var_88]
0x180026896  lea     rcx, [rbp+57h+var_98]
0x18002689a  call    ??0value@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::value(std::wstring)
0x18002689f  mov     rbx, rax
0x1800268a2  mov     rdx, r12
0x1800268a5  lea     rcx, [rbp+57h+var_B8]
0x1800268a9  call    ??Avalue@json@web@@QEAAAEAV012@_K@Z; web::json::value::operator[](unsigned __int64)
0x1800268ae  mov     rcx, rax
0x1800268b1  mov     rdx, rbx
0x1800268b4  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x1800268b9  nop
0x1800268ba  mov     rcx, [rbp+57h+var_98]
0x1800268be  test    rcx, rcx
0x1800268c1  jz      short loc_1800268D7
0x1800268c3  mov     rax, [rcx]
0x1800268c6  mov     edx, 1
0x1800268cb  mov     rax, [rax+0C0h]
0x1800268d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268d7  inc     edi
0x1800268d9  cmp     edi, [r14+8]
0x1800268dd  jb      loc_180026855
0x1800268e3  mov     r12, [rbp+57h+var_A0]
0x1800268e7  xor     r13d, r13d
0x1800268ea  lea     rdx, [rbp+57h+var_88]
0x1800268ee  lea     rcx, [rbp+57h+var_B8]
0x1800268f2  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x1800268f7  mov     rbx, rax
0x1800268fa  lea     rax, [rbp+57h+var_68]
0x1800268fe  cmp     rax, rbx
0x180026901  jz      short loc_18002692B
0x180026903  lea     rcx, [rbp+57h+var_68]
0x180026907  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002690c  movups  xmm0, xmmword ptr [rbx]
0x18002690f  movups  [rbp+57h+var_68], xmm0
0x180026913  movups  xmm1, xmmword ptr [rbx+10h]
0x180026917  movups  [rbp+57h+var_58], xmm1
0x18002691b  mov     [rbx+10h], r13
0x18002691f  mov     qword ptr [rbx+18h], 7
0x180026927  mov     [rbx], r13w
0x18002692b  lea     rcx, [rbp+57h+var_88]
0x18002692f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026934  movups  xmm0, cs:??$guid_v@UIWindowsUpdateManager2@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager2>
0x18002693b  movdqu  [rbp+57h+var_48], xmm0
0x180026940  mov     rcx, [rbp+57h+var_B8]
0x180026944  test    rcx, rcx
0x180026947  jz      short loc_18002695D
0x180026949  mov     rax, [rcx]
0x18002694c  mov     edx, 1
0x180026951  mov     rax, [rax+0C0h]
0x180026958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002695d  mov     rbx, [rbp+57h+var_B0]
0x180026961  mov     rax, [rbx]
0x180026964  mov     rdi, [rax+30h]
0x180026968  cmp     [rbp+57h+pProxy], r13
0x18002696c  jz      short loc_180026977
0x18002696e  lea     rcx, [rbp+57h+pProxy]
0x180026972  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026977  lea     r8, [rbp+57h+var_68]
0x18002697b  cmp     qword ptr [rbp+57h+var_58+8], 7
0x180026980  cmova   r8, qword ptr [rbp+57h+var_68]
0x180026985  mov     rax, [r12]
0x180026989  test    rax, rax
0x18002698c  jz      short loc_180026992
0x18002698e  mov     r15, [rax+10h]
0x180026992  lea     rax, [rbp+57h+pProxy]
0x180026996  mov     [rsp+100h+ppv], rax; int
0x18002699b  lea     r9, [rbp+57h+var_48]
0x18002699f  mov     rdx, r15
0x1800269a2  mov     rcx, rbx
0x1800269a5  mov     rax, rdi
0x1800269a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ad  mov     rcx, [rbp+5Fh]; this
0x1800269b1  test    eax, eax
0x1800269b3  js      loc_180026B7F
0x1800269b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UOvNext@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext> `wil::Feature<__WilFeatureTraits_Feature_UOvNext>::GetImpl(void)'::`2'::impl
0x1800269c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::__private_IsEnabled(void)
0x1800269c5  mov     [rsp+100h+dwCapabilities], r13d; dwCapabilities
0x1800269ca  or      ebx, 0FFFFFFFFh
0x1800269cd  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800269d1  mov     [rsp+100h+pAuthInfo], r13; pAuthInfo
0x1800269d6  mov     r8d, ebx; dwAuthzSvc
0x1800269d9  mov     edx, ebx; dwAuthnSvc
0x1800269db  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x1800269e3  mov     dword ptr [rsp+100h+ppv], r13d; int
0x1800269e8  test    al, al
0x1800269ea  jz      loc_180026AAD
0x1800269f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800269f4  mov     r9, rdi; pServerPrincName
0x1800269f7  call    cs:__imp_CoSetProxyBlanket
0x1800269fd  mov     rcx, [rbp+5Fh]; this
0x180026a01  test    eax, eax
0x180026a03  js      loc_180026B94
0x180026a09  mov     rcx, [rbp+57h+pProxy]
0x180026a0d  test    rcx, rcx
0x180026a10  jnz     short loc_180026A1A
0x180026a12  mov     rcx, r13
0x180026a15  mov     r14, r13
0x180026a18  jmp     short loc_180026A4F
0x180026a1a  mov     [rbp+57h+var_B8], r13
0x180026a1e  mov     dword ptr [rbp+57h+var_88], r13d
0x180026a22  xorps   xmm0, xmm0
0x180026a25  movdqu  [rbp+57h+var_88+8], xmm0
0x180026a2a  mov     rax, [rcx]
0x180026a2d  lea     r8, [rbp+57h+var_B8]
0x180026a31  lea     rdx, ??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180026a38  mov     rax, [rax]
0x180026a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a40  test    eax, eax
0x180026a42  js      loc_180026BA9
0x180026a48  mov     rcx, [rbp+57h+var_B8]; pProxy
0x180026a4c  mov     r14, rcx
0x180026a4f  mov     [rbp+57h+var_A0], rcx
0x180026a53  mov     [rsp+100h+dwCapabilities], r13d; dwCapabilities
0x180026a58  mov     [rsp+100h+pAuthInfo], r13; pAuthInfo
0x180026a5d  mov     [rsp+100h+dwImpLevel], 3; dwImpLevel
0x180026a65  mov     dword ptr [rsp+100h+ppv], r13d; int
0x180026a6a  mov     r9, rdi; pServerPrincName
0x180026a6d  mov     r8d, ebx; dwAuthzSvc
0x180026a70  mov     edx, ebx; dwAuthnSvc
0x180026a72  call    cs:__imp_CoSetProxyBlanket
0x180026a78  mov     rcx, [rbp+5Fh]; this
0x180026a7c  test    eax, eax
0x180026a7e  js      loc_180026BB5
0x180026a84  mov     [rsi], r14
0x180026a87  cmp     [rbp+57h+pProxy], r13
0x180026a8b  jz      short loc_180026A97
0x180026a8d  lea     rcx, [rbp+57h+pProxy]
0x180026a91  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026a96  nop
0x180026a97  mov     rcx, [rbp+57h+var_B0]
0x180026a9b  test    rcx, rcx
0x180026a9e  jz      loc_180026B2B
0x180026aa4  mov     rax, [rcx]
0x180026aa7  mov     rax, [rax+10h]
0x180026aab  jmp     short loc_180026B25
0x180026aad  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180026ab1  call    cs:__imp_CoSetProxyBlanket
0x180026ab7  mov     rcx, [rbp+5Fh]; this
0x180026abb  test    eax, eax
0x180026abd  js      loc_180026BCA
0x180026ac3  mov     rcx, [rbp+57h+pProxy]
0x180026ac7  test    rcx, rcx
0x180026aca  jnz     short loc_180026AD1
0x180026acc  mov     [rsi], r13
0x180026acf  jmp     short loc_180026B06
0x180026ad1  mov     [rbp+57h+var_B8], r13
0x180026ad5  mov     dword ptr [rbp+57h+var_88], r13d
0x180026ad9  xorps   xmm0, xmm0
0x180026adc  movdqu  [rbp+57h+var_88+8], xmm0
0x180026ae1  mov     rax, [rcx]
0x180026ae4  lea     r8, [rbp+57h+var_B8]
0x180026ae8  lea     rdx, ??$guid_v@UIWindowsUpdateManager@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsUpdateManager>
0x180026aef  mov     rax, [rax]
0x180026af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026af7  test    eax, eax
0x180026af9  js      short loc_180026B5E
0x180026afb  mov     rax, [rbp+57h+var_B8]
0x180026aff  mov     [rsi], rax
0x180026b02  mov     rcx, [rbp+57h+pProxy]
0x180026b06  test    rcx, rcx
0x180026b09  jz      short loc_180026B15
0x180026b0b  lea     rcx, [rbp+57h+pProxy]
0x180026b0f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026b14  nop
0x180026b15  mov     rcx, [rbp+57h+var_B0]
0x180026b19  test    rcx, rcx
0x180026b1c  jz      short loc_180026B2B
0x180026b1e  mov     rdx, [rcx]
0x180026b21  mov     rax, [rdx+10h]
0x180026b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b2a  nop
0x180026b2b  lea     rcx, [rbp+57h+var_68]
0x180026b2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026b34  mov     rax, rsi
0x180026b37  mov     rcx, [rbp+57h+var_38]
0x180026b3b  xor     rcx, rsp; StackCookie
0x180026b3e  call    __security_check_cookie
0x180026b43  mov     rbx, [rsp+100h+arg_10]
0x180026b4b  add     rsp, 0D0h
0x180026b52  pop     r15
0x180026b54  pop     r14
0x180026b56  pop     r13
0x180026b58  pop     r12
0x180026b5a  pop     rdi
0x180026b5b  pop     rsi
0x180026b5c  pop     rbp
0x180026b5d  retn
0x180026b5e  lea     rdx, [rbp+57h+var_88]
0x180026b62  mov     ecx, eax
0x180026b64  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026b6a  mov     r9d, eax; char *
0x180026b6d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026b74  mov     edx, 1CBEh; void *
0x180026b79  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180026b7f  mov     r9d, eax; char *
0x180026b82  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180026b89  mov     edx, 26h ; '&'; void *
0x180026b8e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180026b94  mov     r9d, eax; char *
0x180026b97  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180026b9e  mov     edx, 35h ; '5'; void *
0x180026ba3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180026ba9  lea     rdx, [rbp+57h+var_88]
0x180026bad  mov     ecx, eax
0x180026baf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180026bb5  mov     r9d, eax; char *
0x180026bb8  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180026bbf  mov     edx, 43h ; 'C'; void *
0x180026bc4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180026bca  mov     r9d, eax; char *
0x180026bcd  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180026bd4  mov     edx, 52h ; 'R'; void *
0x180026bd9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
