# RegistrationEndpointImpl::RegisterHandler(NotificationPlatform *,INotificationHandler *,IHandlerAssetCollection *,IUnknown *)

- ea: `0x18004a5cc`
- end: `0x18004ac2a`
- name: `?RegisterHandler@RegistrationEndpointImpl@@SAJPEAVNotificationPlatform@@PEAUINotificationHandler@@PEAUIHandlerAssetCollection@@PEAUIUnknown@@@Z`
- size: `1630`
- prototype: `__int64 __fastcall(struct NotificationPlatform *, struct INotificationHandler *, struct IHandlerAssetCollection *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a4a0`

## callees

- `0x180004e38`
- `0x18000e090`
- `0x18000e5f4`
- `0x180011618`
- `0x180013360`
- `0x1800189f8`
- `0x18004a53c`
- `0x18004a5cc`
- `0x18004ac30`
- `0x18004ad88`
- `0x18004bae0`
- `0x180069cb8`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a82f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004aad3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004a82f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004aad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a872`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ab7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall RegistrationEndpointImpl::RegisterHandler(
        struct NotificationPlatform *a1,
        struct INotificationHandler *a2,
        struct IHandlerAssetCollection *a3,
        struct IUnknown *a4)
{
  int IsReadOnlyMode; // eax
  struct INotificationHandler *v9; // rdx
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, LPVOID, struct INotificationHandler **); // rbx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  const WCHAR *v19; // rbx
  const WCHAR *v20; // r8
  __int64 v21; // rdx
  const WCHAR *v22; // rcx
  int v23; // eax
  struct INotificationHandler *v24; // rcx
  void **v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rdx
  char v29; // cl
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  const WCHAR *v34; // r8
  __int64 v35; // rdx
  __int64 (__fastcall *v36)(struct INotificationHandler *, LPCWCH *); // rbx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-C8h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-C8h]
  bool v42; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+38h] [rbp-B0h] BYREF
  LPCWCH lpString1; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+48h] [rbp-A0h]
  __int64 v46; // [rsp+50h] [rbp-98h]
  struct INotificationHandler *v47; // [rsp+58h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-88h] BYREF
  LPCWCH v49; // [rsp+68h] [rbp-80h] BYREF
  __int64 v50; // [rsp+70h] [rbp-78h]
  __int64 v51; // [rsp+78h] [rbp-70h]
  void *v52[2]; // [rsp+80h] [rbp-68h] BYREF
  __m128i si128; // [rsp+90h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v42 = 0;
  IsReadOnlyMode = RegistrationEndpointImpl::IsReadOnlyMode(a1, &v42);
  if ( IsReadOnlyMode < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3FF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)IsReadOnlyMode,
      bIgnoreCase);
  if ( v42 )
    return 0;
  v11 = WpnDatabaseHelpers::OverrideSettingsToDefaultInHandler(a2, v9);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x406,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
  v43 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a1 + 18))(
          *((_QWORD *)a1 + 18),
          &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
          &v43);
  if ( v12 >= 0 && !v43 )
  {
    v12 = -2143420155;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)0x803E0105LL,
      bIgnoreCase);
  }
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x409,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
  pv = 0;
  v13 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
  if ( pv && *(_WORD *)pv )
  {
    v47 = 0;
    v14 = v43;
    v15 = *(__int64 (__fastcall **)(__int64, LPVOID, struct INotificationHandler **))(*(_QWORD *)v43 + 192LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v16 = v15(v14, pv, &v47);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x412,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v16,
        bIgnoreCase);
    lpString1 = 0;
    v45 = 0;
    v46 = 0;
    v17 = *(_QWORD *)v47;
    v45 = -1;
    v46 = -1;
    v18 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(v17 + 48))(v47, &lpString1);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x415,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
    v19 = &word_180124798;
    v20 = &word_180124798;
    if ( off_18015C358 )
      v20 = off_18015C358;
    LODWORD(v21) = v45;
    if ( v45 == -1 )
    {
      if ( lpString1 )
      {
        v21 = -1;
        do
          ++v21;
        while ( lpString1[v21] );
      }
      else
      {
        LODWORD(v21) = 0;
      }
    }
    v22 = &word_180124798;
    if ( lpString1 )
      v22 = lpString1;
    if ( CompareStringOrdinal(v22, v21, v20, -(off_18015C358 != 0), 0) == 2 )
    {
      v23 = RegistrationEndpointImpl::MigrateSecondaryTilesForParent(a1, v47);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x41A,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
          (const char *)(unsigned int)v23,
          bIgnoreCase);
    }
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    v45 = 0;
    v46 = 0;
    v24 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(struct INotificationHandler *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  else
  {
    v19 = &word_180124798;
  }
  GetContainerUserSid(v52, a4);
  v25 = v52;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = (void **)v52[0];
  v26 = (*(__int64 (__fastcall **)(struct INotificationHandler *, void **))(*(_QWORD *)a2 + 112LL))(a2, v25);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)v26,
      bIgnoreCase);
  v27 = (*(__int64 (__fastcall **)(__int64, struct INotificationHandler *))(*(_QWORD *)v43 + 184LL))(v43, a2);
  v28 = 0x80000000LL;
  if ( (int)(v27 + 0x80000000) < 0 || (v29 = 1, v27 == -2018572269) )
    v29 = 0;
  if ( v29 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x423,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)v27,
      bIgnoreCase);
  if ( v27 == -2018572269 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64, struct INotificationHandler *))(*(_QWORD *)v43 + 200LL))(v43, a2);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCase);
  }
  if ( a3 )
  {
    lpString1 = 0;
    v45 = -1;
    v46 = -1;
    v31 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 24LL))(a2, &lpString1);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v31,
        bIgnoreCase);
    v32 = (*(__int64 (__fastcall **)(__int64, LPCWCH, struct IHandlerAssetCollection *))(*(_QWORD *)v43 + 160LL))(
            v43,
            lpString1,
            a3);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v32,
        bIgnoreCase);
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
  }
  LOBYTE(v28) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_40836377>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_40836377>::GetImpl'::`2'::impl,
    v28);
  v49 = 0;
  v50 = -1;
  v51 = -1;
  v33 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 48LL))(a2, &v49);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x445,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
      (const char *)(unsigned int)v33,
      bIgnoreCase);
  v34 = &word_180124798;
  if ( L"app:system" )
    v34 = L"app:system";
  LODWORD(v35) = v50;
  if ( v50 == -1 )
  {
    if ( v49 )
    {
      v35 = -1;
      do
        ++v35;
      while ( v49[v35] );
    }
    else
    {
      LODWORD(v35) = 0;
    }
  }
  if ( v49 )
    v19 = v49;
  if ( CompareStringOrdinal(v19, v35, v34, -(L"app:system" != 0), 0) == 2 )
  {
    lpString1 = 0;
    v45 = 0;
    v46 = 0;
    v36 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPCWCH *))(*(_QWORD *)a2 + 24LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
    v45 = -1;
    v46 = -1;
    v37 = v36(a2, &lpString1);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v37,
        bIgnoreCasea);
    v38 = RegistrationEndpointImpl::UnblockRawChannelForApp(a1, lpString1);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\registrationendpoint.cpp",
        (const char *)(unsigned int)v38,
        bIgnoreCasea);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
  }
  if ( v49 )
  {
    CoTaskMemFree((LPVOID)v49);
    v49 = 0;
  }
  v50 = 0;
  v51 = 0;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v52[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v52[0]) = 0;
  if ( pv )
    CoTaskMemFree(pv);
  v39 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  return 0;
}

```

## disassembly

```asm
0x18004a5cc  push    rbx
0x18004a5ce  push    rsi
0x18004a5cf  push    rdi
0x18004a5d0  push    r12
0x18004a5d2  push    r13
0x18004a5d4  push    r14
0x18004a5d6  push    r15
0x18004a5d8  sub     rsp, 0B0h
0x18004a5df  mov     rax, cs:__security_cookie
0x18004a5e6  xor     rax, rsp
0x18004a5e9  mov     [rsp+0E8h+var_48], rax
0x18004a5f1  mov     r14, r9
0x18004a5f4  mov     r12, r8
0x18004a5f7  mov     rsi, rdx
0x18004a5fa  mov     r15, rcx
0x18004a5fd  xor     r13d, r13d
0x18004a600  mov     [rsp+0E8h+var_B8], r13b
0x18004a605  lea     rdx, [rsp+0E8h+var_B8]; bool *
0x18004a60a  call    ?IsReadOnlyMode@RegistrationEndpointImpl@@CAJPEAVNotificationPlatform@@PEA_N@Z; RegistrationEndpointImpl::IsReadOnlyMode(NotificationPlatform *,bool *)
0x18004a60f  mov     rcx, [rsp+0E8h]; this
0x18004a617  test    eax, eax
0x18004a619  jns     short loc_18004A62F
0x18004a61b  mov     r9d, eax; char *
0x18004a61e  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a625  mov     edx, 3FFh; void *
0x18004a62a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a62f  cmp     [rsp+0E8h+var_B8], r13b
0x18004a634  jz      short loc_18004A63D
0x18004a636  xor     eax, eax
0x18004a638  jmp     loc_18004AC06
0x18004a63d  mov     rcx, rsi; this
0x18004a640  call    ?OverrideSettingsToDefaultInHandler@WpnDatabaseHelpers@@YAJPEAUINotificationHandler@@@Z; WpnDatabaseHelpers::OverrideSettingsToDefaultInHandler(INotificationHandler *)
0x18004a645  mov     rcx, [rsp+0E8h]; this
0x18004a64d  test    eax, eax
0x18004a64f  jns     short loc_18004A665
0x18004a651  mov     r9d, eax; char *
0x18004a654  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a65b  mov     edx, 406h; void *
0x18004a660  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a665  mov     [rsp+0E8h+var_B0], r13
0x18004a66a  lea     rcx, [rsp+0E8h+var_B0]
0x18004a66f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a674  nop
0x18004a675  mov     rcx, [r15+90h]
0x18004a67c  mov     rax, [rcx]
0x18004a67f  lea     r8, [rsp+0E8h+var_B0]
0x18004a684  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x18004a68b  mov     rax, [rax]
0x18004a68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a693  mov     ebx, eax
0x18004a695  test    eax, eax
0x18004a697  js      short loc_18004A6C1
0x18004a699  cmp     [rsp+0E8h+var_B0], r13
0x18004a69e  jnz     short loc_18004A6C1
0x18004a6a0  mov     rcx, [rsp+0E8h]; this
0x18004a6a8  mov     ebx, 803E0105h
0x18004a6ad  mov     r9d, ebx; char *
0x18004a6b0  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a6b7  mov     edx, 400h; void *
0x18004a6bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a6c1  mov     rcx, [rsp+0E8h]; this
0x18004a6c9  test    ebx, ebx
0x18004a6cb  jns     short loc_18004A6E2
0x18004a6cd  mov     r9d, ebx; char *
0x18004a6d0  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a6d7  mov     edx, 409h; void *
0x18004a6dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a6e2  mov     [rsp+0E8h+pv], r13
0x18004a6e7  mov     rax, [rsi]
0x18004a6ea  lea     rdx, [rsp+0E8h+pv]
0x18004a6ef  mov     rcx, rsi
0x18004a6f2  mov     rax, [rax+28h]
0x18004a6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6fb  mov     rcx, [rsp+0E8h]; this
0x18004a703  test    eax, eax
0x18004a705  jns     short loc_18004A71B
0x18004a707  mov     r9d, eax; char *
0x18004a70a  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a711  mov     edx, 40Dh; void *
0x18004a716  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a71b  mov     rax, [rsp+0E8h+pv]
0x18004a720  test    rax, rax
0x18004a723  jz      loc_18004A8A5
0x18004a729  cmp     r13w, [rax]
0x18004a72d  jz      loc_18004A8A5
0x18004a733  mov     [rsp+0E8h+var_90], r13
0x18004a738  mov     rdi, [rsp+0E8h+var_B0]
0x18004a73d  mov     rax, [rdi]
0x18004a740  mov     rbx, [rax+0C0h]
0x18004a747  lea     rcx, [rsp+0E8h+var_90]
0x18004a74c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a751  lea     r8, [rsp+0E8h+var_90]
0x18004a756  mov     rdx, [rsp+0E8h+pv]
0x18004a75b  mov     rcx, rdi
0x18004a75e  mov     rax, rbx
0x18004a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a766  mov     rcx, [rsp+0E8h]; this
0x18004a76e  test    eax, eax
0x18004a770  jns     short loc_18004A786
0x18004a772  mov     r9d, eax; char *
0x18004a775  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a77c  mov     edx, 412h; void *
0x18004a781  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a786  mov     [rsp+0E8h+lpString1], r13
0x18004a78b  mov     [rsp+0E8h+var_A0], r13
0x18004a790  mov     [rsp+0E8h+var_98], r13
0x18004a795  mov     rcx, [rsp+0E8h+var_90]
0x18004a79a  mov     rax, [rcx]
0x18004a79d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004a7a1  mov     [rsp+0E8h+var_A0], rdi
0x18004a7a6  mov     [rsp+0E8h+var_98], rdi
0x18004a7ab  lea     rdx, [rsp+0E8h+lpString1]
0x18004a7b0  mov     rax, [rax+30h]
0x18004a7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7b9  mov     rcx, [rsp+0E8h]; this
0x18004a7c1  test    eax, eax
0x18004a7c3  jns     short loc_18004A7D9
0x18004a7c5  mov     r9d, eax; char *
0x18004a7c8  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a7cf  mov     edx, 415h; void *
0x18004a7d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a7d9  mov     rcx, cs:off_18015C358; "app:immersive"
0x18004a7e0  mov     rax, rcx
0x18004a7e3  neg     rax
0x18004a7e6  sbb     r9d, r9d; cchCount2
0x18004a7e9  lea     rbx, word_180124798
0x18004a7f0  mov     r8, rbx
0x18004a7f3  test    rcx, rcx
0x18004a7f6  cmovnz  r8, rcx; lpString2
0x18004a7fa  mov     rdx, [rsp+0E8h+var_A0]
0x18004a7ff  mov     rax, [rsp+0E8h+lpString1]
0x18004a804  cmp     rdx, rdi
0x18004a807  jnz     short loc_18004A820
0x18004a809  test    rax, rax
0x18004a80c  jz      short loc_18004A81D
0x18004a80e  mov     rdx, rdi
0x18004a811  inc     rdx
0x18004a814  cmp     [rax+rdx*2], r13w
0x18004a819  jnz     short loc_18004A811
0x18004a81b  jmp     short loc_18004A820
0x18004a81d  mov     rdx, r13; cchCount1
0x18004a820  mov     rcx, rbx
0x18004a823  test    rax, rax
0x18004a826  cmovnz  rcx, rax; lpString1
0x18004a82a  mov     [rsp+0E8h+bIgnoreCase], r13d; int
0x18004a82f  call    cs:__imp_CompareStringOrdinal
0x18004a835  cmp     eax, 2
0x18004a838  jnz     short loc_18004A868
0x18004a83a  mov     rdx, [rsp+0E8h+var_90]; struct INotificationHandler *
0x18004a83f  mov     rcx, r15; struct NotificationPlatform *
0x18004a842  call    ?MigrateSecondaryTilesForParent@RegistrationEndpointImpl@@CAJPEAVNotificationPlatform@@PEAUINotificationHandler@@@Z; RegistrationEndpointImpl::MigrateSecondaryTilesForParent(NotificationPlatform *,INotificationHandler *)
0x18004a847  mov     rcx, [rsp+0E8h]; this
0x18004a84f  test    eax, eax
0x18004a851  jns     short loc_18004A868
0x18004a853  mov     r9d, eax; char *
0x18004a856  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a85d  mov     edx, 41Ah; void *
0x18004a862  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a868  mov     rcx, [rsp+0E8h+lpString1]; pv
0x18004a86d  test    rcx, rcx
0x18004a870  jz      short loc_18004A87D
0x18004a872  call    cs:__imp_CoTaskMemFree
0x18004a878  mov     [rsp+0E8h+lpString1], r13
0x18004a87d  mov     [rsp+0E8h+var_A0], r13
0x18004a882  mov     [rsp+0E8h+var_98], r13
0x18004a887  mov     rcx, [rsp+0E8h+var_90]
0x18004a88c  test    rcx, rcx
0x18004a88f  jz      short loc_18004A8A3
0x18004a891  mov     [rsp+0E8h+var_90], r13
0x18004a896  mov     rax, [rcx]
0x18004a899  mov     rax, [rax+10h]
0x18004a89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8a2  nop
0x18004a8a3  jmp     short loc_18004A8B0
0x18004a8a5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004a8a9  lea     rbx, word_180124798
0x18004a8b0  mov     rdx, r14
0x18004a8b3  lea     rcx, [rsp+0E8h+var_68]
0x18004a8bb  call    ?GetContainerUserSid@@YA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUnknown@@@Z; GetContainerUserSid(IUnknown *)
0x18004a8c0  nop
0x18004a8c1  mov     rax, [rsi]
0x18004a8c4  lea     rdx, [rsp+0E8h+var_68]
0x18004a8cc  cmp     [rsp+0E8h+var_50], 7
0x18004a8d5  cmova   rdx, [rsp+0E8h+var_68]
0x18004a8de  mov     rcx, rsi
0x18004a8e1  mov     rax, [rax+70h]
0x18004a8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8ea  mov     rcx, [rsp+0E8h]; this
0x18004a8f2  test    eax, eax
0x18004a8f4  jns     short loc_18004A90A
0x18004a8f6  mov     r9d, eax; char *
0x18004a8f9  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a900  mov     edx, 41Fh; void *
0x18004a905  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a90a  mov     rcx, [rsp+0E8h+var_B0]
0x18004a90f  mov     rax, [rcx]
0x18004a912  mov     rdx, rsi
0x18004a915  mov     rax, [rax+0B8h]
0x18004a91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a921  mov     edx, 80000000h
0x18004a926  lea     ecx, [rax+rdx]
0x18004a929  test    edx, ecx
0x18004a92b  jnz     short loc_18004A936
0x18004a92d  cmp     eax, 87AF0813h
0x18004a932  mov     cl, 1
0x18004a934  jnz     short loc_18004A939
0x18004a936  mov     cl, r13b
0x18004a939  mov     r10, [rsp+0E8h]
0x18004a941  test    cl, cl
0x18004a943  jz      short loc_18004A95C
0x18004a945  mov     r9d, eax; char *
0x18004a948  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a94f  mov     edx, 423h; void *
0x18004a954  mov     rcx, r10; this
0x18004a957  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a95c  cmp     eax, 87AF0813h
0x18004a961  jnz     short loc_18004A99A
0x18004a963  mov     rcx, [rsp+0E8h+var_B0]
0x18004a968  mov     rax, [rcx]
0x18004a96b  mov     rdx, rsi
0x18004a96e  mov     rax, [rax+0C8h]
0x18004a975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a97a  mov     rcx, [rsp+0E8h]; this
0x18004a982  test    eax, eax
0x18004a984  jns     short loc_18004A99A
0x18004a986  mov     r9d, eax; char *
0x18004a989  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a990  mov     edx, 426h; void *
0x18004a995  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a99a  test    r12, r12
0x18004a99d  jz      loc_18004AA33
0x18004a9a3  mov     [rsp+0E8h+lpString1], r13
0x18004a9a8  mov     [rsp+0E8h+var_A0], rdi
0x18004a9ad  mov     [rsp+0E8h+var_98], rdi
0x18004a9b2  mov     rax, [rsi]
0x18004a9b5  lea     rdx, [rsp+0E8h+lpString1]
0x18004a9ba  mov     rcx, rsi
0x18004a9bd  mov     rax, [rax+18h]
0x18004a9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9c6  mov     rcx, [rsp+0E8h]; this
0x18004a9ce  test    eax, eax
0x18004a9d0  jns     short loc_18004A9E6
0x18004a9d2  mov     r9d, eax; char *
0x18004a9d5  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004a9dc  mov     edx, 42Dh; void *
0x18004a9e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a9e6  mov     rcx, [rsp+0E8h+var_B0]
0x18004a9eb  mov     rax, [rcx]
0x18004a9ee  mov     r8, r12
0x18004a9f1  mov     rdx, [rsp+0E8h+lpString1]
0x18004a9f6  mov     rax, [rax+0A0h]
0x18004a9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa02  mov     rcx, [rsp+0E8h]; this
0x18004aa0a  test    eax, eax
0x18004aa0c  jns     short loc_18004AA23
0x18004aa0e  mov     r9d, eax; char *
0x18004aa11  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004aa18  mov     edx, 42Eh; void *
0x18004aa1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004aa23  mov     rcx, [rsp+0E8h+lpString1]; pv
0x18004aa28  test    rcx, rcx
0x18004aa2b  jz      short loc_18004AA33
0x18004aa2d  call    cs:__imp_CoTaskMemFree
0x18004aa33  mov     dl, 1
0x18004aa35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40836377@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40836377@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40836377> `wil::Feature<__WilFeatureTraits_Feature_40836377>::GetImpl(void)'::`2'::impl
0x18004aa3c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40836377@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40836377>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004aa41  mov     [rsp+0E8h+var_80], r13
0x18004aa46  mov     [rsp+0E8h+var_78], rdi
0x18004aa4b  mov     [rsp+0E8h+var_70], rdi
0x18004aa50  mov     rax, [rsi]
0x18004aa53  lea     rdx, [rsp+0E8h+var_80]
0x18004aa58  mov     rcx, rsi
0x18004aa5b  mov     rax, [rax+30h]
0x18004aa5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa64  mov     rcx, [rsp+0E8h]; this
0x18004aa6c  test    eax, eax
0x18004aa6e  jns     short loc_18004AA84
0x18004aa70  mov     r9d, eax; char *
0x18004aa73  lea     r8, aOnecoreuapBase_152; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004aa7a  mov     edx, 445h; void *
0x18004aa7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004aa84  mov     rcx, cs:off_18011DEB0; "app:system"
0x18004aa8b  mov     rax, rcx
0x18004aa8e  neg     rax
0x18004aa91  sbb     r9d, r9d; cchCount2
0x18004aa94  mov     r8, rbx
0x18004aa97  test    rcx, rcx
0x18004aa9a  cmovnz  r8, rcx; lpString2
0x18004aa9e  mov     rdx, [rsp+0E8h+var_78]
0x18004aaa3  mov     rax, [rsp+0E8h+var_80]
0x18004aaa8  cmp     rdx, rdi
0x18004aaab  jnz     short loc_18004AAC4
0x18004aaad  test    rax, rax
0x18004aab0  jz      short loc_18004AAC1
0x18004aab2  mov     rdx, rdi
0x18004aab5  inc     rdx
0x18004aab8  cmp     [rax+rdx*2], r13w
0x18004aabd  jnz     short loc_18004AAB5
0x18004aabf  jmp     short loc_18004AAC4
0x18004aac1  mov     rdx, r13; cchCount1
  ... truncated ...
```
