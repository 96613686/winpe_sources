# ComDeviceInfoFromCDPDeviceInfo

- ea: `0x18000cd08`
- end: `0x18000db61`
- name: `ComDeviceInfoFromCDPDeviceInfo`
- size: `3673`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e940`

## callees

- `0x180003e60`
- `0x1800085e0`
- `0x1800099b0`
- `0x18000cbd4`
- `0x18000cc2c`
- `0x18000cce4`
- `0x18000cd08`
- `0x18000e9c8`
- `0x1800108e8`
- `0x180012c2c`
- `0x180012da0`
- `0x180016808`
- `0x180016b74`
- `0x180018d18`
- `0x180022a90`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d35b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cf45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d35b`

## string_xrefs

- `0x18000ce35`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000cef4`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000cfbc`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000d046`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000d25e`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000d443`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000d7c8`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall ComDeviceInfoFromCDPDeviceInfo(__int64 a1, __int64 a2)
{
  __int64 v4; // r12
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned __int16 v9; // ax
  _QWORD *unique; // rax
  unsigned __int64 v11; // rdx
  void *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  unsigned __int64 v16; // rdx
  void *v17; // rcx
  LPVOID v18; // rax
  __int64 v19; // rcx
  int i; // esi
  int v21; // eax
  int v22; // edx
  int v23; // ecx
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  unsigned __int64 v27; // rdx
  void *v28; // rcx
  unsigned __int16 v29; // ax
  _QWORD *v30; // rax
  unsigned __int64 v31; // rdx
  void *v32; // rcx
  LPVOID v33; // rax
  __int64 v34; // rcx
  unsigned __int16 j; // si
  unsigned __int16 v36; // ax
  _QWORD *v37; // rax
  unsigned __int64 v38; // rdx
  void *v39; // rcx
  int v40; // eax
  int v41; // edx
  int v42; // ecx
  unsigned __int64 v43; // rdx
  void *v44; // rcx
  unsigned __int64 v45; // rdx
  void *v46; // rcx
  unsigned __int64 v47; // rdx
  void *v48; // rcx
  bool v49; // zf
  unsigned __int64 v50; // rdx
  void *v51; // rcx
  LPVOID v52; // rax
  __int64 v53; // r13
  unsigned __int16 k; // si
  __int64 v55; // rsi
  __int64 v56; // r14
  __int64 v57; // r15
  char *v58; // rax
  int v59; // eax
  int v60; // edx
  int v61; // ecx
  unsigned __int64 v62; // rdx
  void *v63; // rcx
  unsigned __int64 v64; // rdx
  void *v65; // rcx
  char *v66; // rax
  char *v67; // rax
  char *v68; // rax
  char *v69; // rax
  char *v70; // rax
  char *v71; // rax
  char *v72; // rax
  char *v73; // rax
  char *v74; // rax
  char *v75; // rax
  int v76; // eax
  int v77; // edx
  int v78; // ecx
  char *v79; // rax
  char *v80; // rax
  char *v81; // rax
  void *v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  unsigned __int64 v92; // rdx
  void *v93; // rcx
  unsigned __int64 v94; // rdx
  void *v95; // rcx
  unsigned __int64 v96; // rdx
  void *v97; // rcx
  __int64 v98; // [rsp+30h] [rbp-D0h] BYREF
  void *v99; // [rsp+38h] [rbp-C8h] BYREF
  void *v100; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v101; // [rsp+48h] [rbp-B8h] BYREF
  void *v102; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v103; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v104; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v105; // [rsp+68h] [rbp-98h] BYREF
  void *v106; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v107; // [rsp+78h] [rbp-88h] BYREF
  __int64 v108; // [rsp+80h] [rbp-80h] BYREF
  void *v109; // [rsp+88h] [rbp-78h] BYREF
  __int64 v110; // [rsp+90h] [rbp-70h] BYREF
  __int64 v111; // [rsp+98h] [rbp-68h] BYREF
  __int64 v112; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v113; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v114; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v115; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v116; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v117; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v118; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v119; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v120; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v121; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v122; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v123[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v124[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v125[2]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v126[9]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v127; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v128; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v129; // [rsp+198h] [rbp+98h] BYREF

  v4 = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  *(_DWORD *)(a2 + 28) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
  *(_DWORD *)(a2 + 32) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
  *(_DWORD *)(a2 + 36) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
  *(_WORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 48) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 80LL))(a1);
  *(_DWORD *)(a2 + 56) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
  *(_WORD *)(a2 + 96) = 0;
  *(_DWORD *)(a2 + 100) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
  *(_DWORD *)(a2 + 52) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 200LL))(a1);
  *(_DWORD *)(a2 + 184) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 216LL))(a1);
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, &v129);
  if ( v6 < 0 )
  {
    LODWORD(v98) = v6;
    LODWORD(v101) = 535;
    Log<long &,char const (&)[64],int>(
      v8,
      v7,
      (unsigned int)&v98,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (__int64)&v101);
    return (unsigned int)v98;
  }
  v99 = 0;
  v124[0] = &v99;
  v124[1] = &v129;
  v104 = v124;
  v9 = v129;
  if ( v129 )
  {
    unique = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v106, v129);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(
      &v99,
      unique);
    v12 = v106;
    v106 = 0;
    if ( v12 )
      operator delete(v12, v11);
    if ( !v99 )
      goto LABEL_57;
    v13 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 40LL))(
            a1,
            v99,
            v129,
            &v129);
    if ( v13 < 0 )
    {
      LODWORD(v98) = v13;
      LODWORD(v101) = 556;
      Log<long &,char const (&)[64],int>(
        v15,
        v14,
        (unsigned int)&v98,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (__int64)&v101);
LABEL_14:
      ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v104);
      v17 = v99;
      v99 = 0;
      goto LABEL_15;
    }
    v9 = v129;
  }
  v103 = 0;
  v18 = CoTaskMemAlloc(40LL * v9);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v103,
    v18);
  v19 = v103;
  v101 = v103;
  if ( !v103 )
  {
LABEL_56:
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v103,
      0);
LABEL_57:
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v104);
    v51 = v99;
    v49 = v99 == 0;
    v99 = 0;
    if ( !v49 )
      operator delete(v51, v50);
    return 2147942414LL;
  }
  for ( i = 0; i < v129; ++i )
  {
    v21 = ComEndpointFromCDPEndpoint_2(*((_QWORD *)v99 + i), v19 + 40LL * i);
    if ( v21 < 0 )
    {
      LODWORD(v98) = v21;
      LODWORD(v101) = 573;
      Log<long &,char const (&)[64],int>(
        v23,
        v22,
        (unsigned int)&v98,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (__int64)&v101);
LABEL_24:
      wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v103,
        0);
      goto LABEL_14;
    }
    v19 = v101;
  }
  v100 = 0;
  v127 = 0;
  v105 = 0;
  v125[0] = &v100;
  v125[1] = &v127;
  v107 = v125;
  v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 136LL))(
          a1,
          0,
          0,
          &v127);
  if ( v24 < 0 )
  {
    LODWORD(v101) = 592;
LABEL_27:
    LODWORD(v98) = v24;
    Log<long &,char const (&)[64],int>(
      v26,
      v25,
      (unsigned int)&v98,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (__int64)&v101);
LABEL_28:
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v107);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v105,
      0);
    v28 = v100;
    v100 = 0;
    if ( v28 )
      operator delete(v28, v27);
    goto LABEL_24;
  }
  v29 = v127;
  if ( v127 )
  {
    v30 = wil::make_unique_nothrow<ICDPResource * [0]>(&v106, v127);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(&v100, v30);
    v32 = v106;
    v106 = 0;
    if ( v32 )
      operator delete(v32, v31);
    if ( !v100 )
      goto LABEL_54;
    v24 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 136LL))(
            a1,
            v100,
            v127,
            &v127);
    if ( v24 < 0 )
    {
      LODWORD(v101) = 598;
      goto LABEL_27;
    }
    v29 = v127;
  }
  v33 = CoTaskMemAlloc(40LL * v29);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v105,
    v33);
  v34 = v105;
  v98 = v105;
  if ( !v105 )
  {
LABEL_54:
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v107);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v105,
      0);
    v48 = v100;
    v49 = v100 == 0;
    v100 = 0;
    if ( !v49 )
      operator delete(v48, v47);
    goto LABEL_56;
  }
  for ( j = 0; j < v127; ++j )
  {
    v24 = ComResourceFromCDPResource_2(*((_QWORD *)v100 + j), v34 + 40LL * j);
    if ( v24 < 0 )
    {
      LODWORD(v101) = 614;
      goto LABEL_27;
    }
    v34 = v98;
  }
  v102 = 0;
  v128 = 0;
  v108 = 0;
  v126[0] = &v102;
  v126[1] = &v128;
  v106 = v126;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
         a1,
         0,
         0,
         &v128) == -2147221235 )
  {
    v36 = v128;
    if ( !v128 )
      goto LABEL_61;
    v37 = wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(&v109, v128);
    wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(&v102, v37);
    v39 = v109;
    v109 = 0;
    if ( v39 )
      operator delete(v39, v38);
    if ( !v102 )
      goto LABEL_52;
    v40 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
            a1,
            v102,
            v128,
            &v128);
    if ( v40 < 0 )
    {
      LODWORD(v101) = 640;
LABEL_50:
      LODWORD(v98) = v40;
      Log<long &,char const (&)[64],int>(
        v42,
        v41,
        (unsigned int)&v98,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (__int64)&v101);
      ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v106);
      wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v108,
        0);
      v44 = v102;
      v102 = 0;
      if ( v44 )
        operator delete(v44, v43);
      goto LABEL_28;
    }
  }
  v36 = v128;
LABEL_61:
  v52 = CoTaskMemAlloc(24LL * v36);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v108,
    v52);
  v53 = v108;
  if ( !v108 )
  {
LABEL_52:
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v106);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v108,
      0);
    v46 = v102;
    v102 = 0;
    if ( v46 )
      operator delete(v46, v45);
    goto LABEL_54;
  }
  for ( k = 0; k < v128; ++k )
  {
    v40 = ComApplicationFromCDPApplication_1(*((_QWORD *)v102 + k), v53 + 24LL * k);
    if ( v40 < 0 )
    {
      LODWORD(v101) = 657;
      goto LABEL_50;
    }
  }
  v109 = 0;
  v122 = 0;
  v121 = 0;
  v120 = 0;
  v119 = 0;
  v118 = 0;
  v117 = 0;
  v116 = 0;
  v115 = 0;
  v114 = 0;
  v55 = 0;
  v113 = 0;
  v56 = 0;
  v112 = 0;
  v57 = 0;
  v111 = 0;
  v110 = 0;
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v109,
    0);
  v58 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v59 = CopyString_0(v58);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 675;
LABEL_69:
    LODWORD(v98) = v59;
    Log<long &,char const (&)[64],int>(
      v61,
      v60,
      (unsigned int)&v98,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (__int64)&v101);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v110);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v111);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v112);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v113);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v114);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v115);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v116);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v117);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v118);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v119);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v120);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v121);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v122);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v109);
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v106);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v108,
      0);
LABEL_70:
    v63 = v102;
    v102 = 0;
    if ( v63 )
      operator delete(v63, v62);
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v107);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v105,
      0);
    v65 = v100;
    v49 = v100 == 0;
    v100 = 0;
    if ( !v49 )
      operator delete(v65, v64);
    wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v103,
      0);
    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v104);
    v17 = v99;
    v99 = 0;
LABEL_15:
    if ( v17 )
      operator delete(v17, v16);
    return (unsigned int)v98;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v122,
    0);
  v66 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v59 = CopyString_0(v66);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 676;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v121,
    0);
  v67 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
  v59 = CopyString_0(v67);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 677;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v120,
    0);
  v68 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
  v59 = CopyString_0(v68);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 678;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v119,
    0);
  v69 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
  v59 = CopyString_0(v69);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 679;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v118,
    0);
  v70 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
  v59 = CopyString_0(v70);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 680;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v117,
    0);
  v71 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 176LL))(a1);
  v59 = CopyString_0(v71);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 681;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v116,
    0);
  v72 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
  v59 = CopyString_0(v72);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 682;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v115,
    0);
  v73 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
  v59 = CopyString_0(v73);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 683;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v114,
    0);
  v74 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 192LL))(a1);
  v59 = CopyString_0(v74);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 684;
    goto LABEL_69;
  }
  *(_OWORD *)v123 = 0;
  if ( (*(int (__fastcall **)(__int64, std::_Ref_count_base **))(*(_QWORD *)a1 + 208LL))(a1, v123) >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v113,
      0);
    v75 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 24LL))(v123[0]);
    v76 = CopyString_0(v75);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 689;
LABEL_96:
      LODWORD(v98) = v76;
      Log<long &,char const (&)[64],int>(
        v78,
        v77,
        (unsigned int)&v98,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (__int64)&v101);
      if ( v123[1] )
        std::_Ref_count_base::_Decref(v123[1]);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v110);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v111);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v112);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v113);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v114);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v115);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v116);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v117);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v118);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v119);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v120);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v121);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v122);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v109);
      ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v106);
      wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v108,
        0);
      goto LABEL_70;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v112,
      0);
    v79 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 32LL))(v123[0]);
    v76 = CopyString_0(v79);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 690;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v111,
      0);
    v80 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 40LL))(v123[0]);
    v76 = CopyString_0(v80);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 691;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v110,
      0);
    v81 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 48LL))(v123[0]);
    v76 = CopyString_0(v81);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 692;
      goto LABEL_96;
    }
    v55 = v113;
    v56 = v112;
    v57 = v111;
    v4 = v110;
  }
  v82 = v109;
  v109 = 0;
  *(_QWORD *)a2 = v82;
  v83 = v122;
  v122 = 0;
  *(_QWORD *)(a2 + 8) = v83;
  v84 = v121;
  v121 = 0;
  *(_QWORD *)(a2 + 40) = v84;
  v85 = v120;
  v120 = 0;
  *(_QWORD *)(a2 + 64) = v85;
  v86 = v119;
  v119 = 0;
  *(_QWORD *)(a2 + 72) = v86;
  v87 = v118;
  v118 = 0;
  *(_QWORD *)(a2 + 104) = v87;
  v88 = v117;
  v117 = 0;
  *(_QWORD *)(a2 + 120) = v88;
  v89 = v116;
  v116 = 0;
  *(_QWORD *)(a2 + 80) = v89;
  v90 = v115;
  v115 = 0;
  *(_QWORD *)(a2 + 112) = v90;
  v113 = 0;
  *(_QWORD *)(a2 + 160) = v55;
  v112 = 0;
  *(_QWORD *)(a2 + 168) = v56;
  v111 = 0;
  *(_QWORD *)(a2 + 152) = v57;
  v110 = 0;
  *(_QWORD *)(a2 + 176) = v4;
  v103 = 0;
  *(_QWORD *)(a2 + 16) = v101;
  *(_WORD *)(a2 + 24) = v129;
  v105 = 0;
  *(_QWORD *)(a2 + 88) = v98;
  *(_WORD *)(a2 + 96) = v127;
  v108 = 0;
  *(_QWORD *)(a2 + 128) = v53;
  *(_WORD *)(a2 + 136) = v128;
  v91 = v114;
  v114 = 0;
  *(_QWORD *)(a2 + 144) = v91;
  if ( v123[1] )
    std::_Ref_count_base::_Decref(v123[1]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v110);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v111);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v112);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v113);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v114);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v115);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v116);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v117);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v118);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v119);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v120);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v121);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v122);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v109);
  ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v106);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v108,
    0);
  v93 = v102;
  v102 = 0;
  if ( v93 )
    operator delete(v93, v92);
  ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v107);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v105,
    0);
  v95 = v100;
  v100 = 0;
  if ( v95 )
    operator delete(v95, v94);
  wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v103,
    0);
  ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___::_ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___(&v104);
  v97 = v99;
  v99 = 0;
  if ( v97 )
    operator delete(v97, v96);
  return 0;
}

```

## disassembly

```asm
0x18000cd08  mov     [rsp-8+arg_8], rbx
0x18000cd0d  push    rbp
0x18000cd0e  push    rsi
0x18000cd0f  push    rdi
0x18000cd10  push    r12
0x18000cd12  push    r13
0x18000cd14  push    r14
0x18000cd16  push    r15
0x18000cd18  lea     rbp, [rsp-40h]
0x18000cd1d  sub     rsp, 140h
0x18000cd24  mov     rdi, rdx
0x18000cd27  mov     rbx, rcx
0x18000cd2a  xor     r12d, r12d
0x18000cd2d  test    rcx, rcx
0x18000cd30  jnz     short loc_18000CD3C
0x18000cd32  mov     eax, 80070057h
0x18000cd37  jmp     loc_18000D32E
0x18000cd3c  test    rdi, rdi
0x18000cd3f  jnz     short loc_18000CD4B
0x18000cd41  mov     eax, 80004003h
0x18000cd46  jmp     loc_18000D32E
0x18000cd4b  mov     rax, [rcx]
0x18000cd4e  mov     rax, [rax+30h]
0x18000cd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd57  movzx   eax, ax
0x18000cd5a  mov     [rdi+1Ch], eax
0x18000cd5d  mov     rax, [rbx]
0x18000cd60  mov     rcx, rbx
0x18000cd63  mov     rax, [rax+38h]
0x18000cd67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd6c  movzx   eax, ax
0x18000cd6f  mov     [rdi+20h], eax
0x18000cd72  mov     rax, [rbx]
0x18000cd75  mov     rcx, rbx
0x18000cd78  mov     rax, [rax+40h]
0x18000cd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd81  mov     [rdi+24h], eax
0x18000cd84  mov     [rdi+18h], r12w
0x18000cd89  mov     rax, [rbx]
0x18000cd8c  mov     rcx, rbx
0x18000cd8f  mov     rax, [rax+50h]
0x18000cd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd98  movzx   eax, al
0x18000cd9b  mov     [rdi+30h], eax
0x18000cd9e  mov     rax, [rbx]
0x18000cda1  mov     rcx, rbx
0x18000cda4  mov     rax, [rax+58h]
0x18000cda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdad  movzx   eax, al
0x18000cdb0  mov     [rdi+38h], eax
0x18000cdb3  mov     [rdi+60h], r12w
0x18000cdb8  mov     rax, [rbx]
0x18000cdbb  mov     rcx, rbx
0x18000cdbe  mov     rax, [rax+0A0h]
0x18000cdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdca  movzx   eax, al
0x18000cdcd  mov     [rdi+64h], eax
0x18000cdd0  mov     rax, [rbx]
0x18000cdd3  mov     rcx, rbx
0x18000cdd6  mov     rax, [rax+0C8h]
0x18000cddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde2  movzx   eax, al
0x18000cde5  mov     [rdi+34h], eax
0x18000cde8  mov     rax, [rbx]
0x18000cdeb  mov     rcx, rbx
0x18000cdee  mov     rax, [rax+0D8h]
0x18000cdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdfa  mov     [rdi+0B8h], eax
0x18000ce00  mov     rax, [rbx]
0x18000ce03  xor     r8d, r8d
0x18000ce06  lea     r9, [rbp+70h+arg_18]
0x18000ce0d  xor     edx, edx
0x18000ce0f  mov     rcx, rbx
0x18000ce12  mov     rax, [rax+28h]
0x18000ce16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1b  test    eax, eax
0x18000ce1d  jns     short loc_18000CE4F
0x18000ce1f  mov     dword ptr [rsp+170h+var_140], eax
0x18000ce23  mov     dword ptr [rsp+170h+var_128], 217h
0x18000ce2b  lea     rax, [rsp+170h+var_128]
0x18000ce30  mov     [rsp+170h+var_150], rax
0x18000ce35  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000ce3c  lea     r8, [rsp+170h+var_140]
0x18000ce41  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000ce46  mov     eax, dword ptr [rsp+170h+var_140]
0x18000ce4a  jmp     loc_18000D32E
0x18000ce4f  mov     [rsp+170h+var_138], r12
0x18000ce54  lea     rax, [rsp+170h+var_138]
0x18000ce59  mov     [rbp+70h+var_68], rax
0x18000ce5d  lea     rax, [rbp+70h+arg_18]
0x18000ce64  mov     [rbp+70h+var_60], rax
0x18000ce68  lea     rax, [rbp+70h+var_68]
0x18000ce6c  mov     [rsp+170h+var_110], rax
0x18000ce71  movzx   eax, [rbp+70h+arg_18]
0x18000ce78  test    ax, ax
0x18000ce7b  jz      loc_18000CF35
0x18000ce81  mov     edx, eax
0x18000ce83  lea     rcx, [rsp+170h+var_100]
0x18000ce88  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x18000ce8d  mov     rdx, rax
0x18000ce90  lea     rcx, [rsp+170h+var_138]
0x18000ce95  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000ce9a  mov     rcx, [rsp+170h+var_100]; void *
0x18000ce9f  mov     [rsp+170h+var_100], r12
0x18000cea4  test    rcx, rcx
0x18000cea7  jz      short loc_18000CEAE
0x18000cea9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ceae  mov     rdx, [rsp+170h+var_138]
0x18000ceb3  test    rdx, rdx
0x18000ceb6  jz      loc_18000D30A
0x18000cebc  mov     rax, [rbx]
0x18000cebf  lea     r9, [rbp+70h+arg_18]
0x18000cec6  movzx   r8d, [rbp+70h+arg_18]
0x18000cece  mov     rcx, rbx
0x18000ced1  mov     rax, [rax+28h]
0x18000ced5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceda  test    eax, eax
0x18000cedc  jns     short loc_18000CF2E
0x18000cede  mov     dword ptr [rsp+170h+var_140], eax
0x18000cee2  mov     dword ptr [rsp+170h+var_128], 22Ch
0x18000ceea  lea     rax, [rsp+170h+var_128]
0x18000ceef  mov     [rsp+170h+var_150], rax
0x18000cef4  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000cefb  lea     r8, [rsp+170h+var_140]
0x18000cf00  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000cf05  nop
0x18000cf06  lea     rcx, [rsp+170h+var_110]
0x18000cf0b  call    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7______ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___
0x18000cf10  nop
0x18000cf11  mov     rcx, [rsp+170h+var_138]; void *
0x18000cf16  mov     [rsp+170h+var_138], r12
0x18000cf1b  test    rcx, rcx
0x18000cf1e  jz      loc_18000CE46
0x18000cf24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf29  jmp     loc_18000CE46
0x18000cf2e  movzx   eax, [rbp+70h+arg_18]
0x18000cf35  mov     [rsp+170h+var_118], r12
0x18000cf3a  movzx   eax, ax
0x18000cf3d  lea     rcx, [rax+rax*4]
0x18000cf41  shl     rcx, 3; cb
0x18000cf45  call    cs:__imp_CoTaskMemAlloc
0x18000cf4b  mov     rdx, rax
0x18000cf4e  lea     rcx, [rsp+170h+var_118]
0x18000cf53  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000cf58  mov     rcx, [rsp+170h+var_118]
0x18000cf5d  mov     [rsp+170h+var_128], rcx
0x18000cf62  test    rcx, rcx
0x18000cf65  jz      loc_18000D2FD
0x18000cf6b  mov     esi, r12d
0x18000cf6e  mov     r14d, 1
0x18000cf74  movzx   eax, [rbp+70h+arg_18]
0x18000cf7b  cmp     esi, eax
0x18000cf7d  jge     short loc_18000CFDF
0x18000cf7f  movsxd  r8, esi
0x18000cf82  lea     rax, [r8+r8*4]
0x18000cf86  lea     rdx, [rcx+rax*8]
0x18000cf8a  mov     rcx, [rsp+170h+var_138]
0x18000cf8f  mov     rcx, [rcx+r8*8]
0x18000cf93  call    ComEndpointFromCDPEndpoint_2
0x18000cf98  test    eax, eax
0x18000cf9a  js      short loc_18000CFA6
0x18000cf9c  add     esi, r14d
0x18000cf9f  mov     rcx, [rsp+170h+var_128]
0x18000cfa4  jmp     short loc_18000CF74
0x18000cfa6  mov     dword ptr [rsp+170h+var_140], eax
0x18000cfaa  mov     dword ptr [rsp+170h+var_128], 23Dh
0x18000cfb2  lea     rax, [rsp+170h+var_128]
0x18000cfb7  mov     [rsp+170h+var_150], rax
0x18000cfbc  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000cfc3  lea     r8, [rsp+170h+var_140]
0x18000cfc8  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000cfcd  nop
0x18000cfce  xor     edx, edx
0x18000cfd0  lea     rcx, [rsp+170h+var_118]
0x18000cfd5  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000cfda  jmp     loc_18000CF06
0x18000cfdf  mov     [rsp+170h+var_130], r12
0x18000cfe4  mov     [rbp+70h+arg_0], r12w
0x18000cfec  mov     [rsp+170h+var_108], r12
0x18000cff1  lea     rax, [rsp+170h+var_130]
0x18000cff6  mov     [rbp+70h+var_58], rax
0x18000cffa  lea     rax, [rbp+70h+arg_0]
0x18000d001  mov     [rbp+70h+var_50], rax
0x18000d005  lea     rax, [rbp+70h+var_58]
0x18000d009  mov     [rsp+170h+var_F8], rax
0x18000d00e  mov     rax, [rbx]
0x18000d011  xor     r8d, r8d
0x18000d014  lea     r9, [rbp+70h+arg_0]
0x18000d01b  xor     edx, edx
0x18000d01d  mov     rcx, rbx
0x18000d020  mov     rax, [rax+88h]
0x18000d027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d02c  test    eax, eax
0x18000d02e  jns     short loc_18000D08D
0x18000d030  mov     dword ptr [rsp+170h+var_128], 250h
0x18000d038  mov     dword ptr [rsp+170h+var_140], eax
0x18000d03c  lea     rax, [rsp+170h+var_128]
0x18000d041  mov     [rsp+170h+var_150], rax
0x18000d046  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000d04d  lea     r8, [rsp+170h+var_140]
0x18000d052  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000d057  nop
0x18000d058  lea     rcx, [rsp+170h+var_F8]
0x18000d05d  call    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7______ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___
0x18000d062  nop
0x18000d063  xor     edx, edx
0x18000d065  lea     rcx, [rsp+170h+var_108]
0x18000d06a  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000d06f  nop
0x18000d070  mov     rcx, [rsp+170h+var_130]; void *
0x18000d075  mov     [rsp+170h+var_130], r12
0x18000d07a  test    rcx, rcx
0x18000d07d  jz      loc_18000CFCE
0x18000d083  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d088  jmp     loc_18000CFCE
0x18000d08d  movzx   eax, [rbp+70h+arg_0]
0x18000d094  test    ax, ax
0x18000d097  jz      short loc_18000D10D
0x18000d099  mov     edx, eax
0x18000d09b  lea     rcx, [rsp+170h+var_100]
0x18000d0a0  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPResource@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPResource@@U?$default_delete@$$BY0A@PEAVICDPResource@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPResource * [0]>(unsigned __int64)
0x18000d0a5  mov     rdx, rax
0x18000d0a8  lea     rcx, [rsp+170h+var_130]
0x18000d0ad  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000d0b2  mov     rcx, [rsp+170h+var_100]; void *
0x18000d0b7  mov     [rsp+170h+var_100], r12
0x18000d0bc  test    rcx, rcx
0x18000d0bf  jz      short loc_18000D0C6
0x18000d0c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d0c6  mov     rdx, [rsp+170h+var_130]
0x18000d0cb  test    rdx, rdx
0x18000d0ce  jz      loc_18000D2D0
0x18000d0d4  mov     rax, [rbx]
0x18000d0d7  lea     r9, [rbp+70h+arg_0]
0x18000d0de  movzx   r8d, [rbp+70h+arg_0]
0x18000d0e6  mov     rcx, rbx
0x18000d0e9  mov     rax, [rax+88h]
0x18000d0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0f5  test    eax, eax
0x18000d0f7  jns     short loc_18000D106
0x18000d0f9  mov     dword ptr [rsp+170h+var_128], 256h
0x18000d101  jmp     loc_18000D038
0x18000d106  movzx   eax, [rbp+70h+arg_0]
0x18000d10d  movzx   eax, ax
0x18000d110  lea     rcx, [rax+rax*4]
0x18000d114  shl     rcx, 3; cb
0x18000d118  call    cs:__imp_CoTaskMemAlloc
0x18000d11e  mov     rdx, rax
0x18000d121  lea     rcx, [rsp+170h+var_108]
0x18000d126  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000d12b  mov     rcx, [rsp+170h+var_108]
0x18000d130  mov     [rsp+170h+var_140], rcx
0x18000d135  test    rcx, rcx
0x18000d138  jz      loc_18000D2D0
0x18000d13e  mov     esi, r12d
0x18000d141  cmp     si, [rbp+70h+arg_0]
0x18000d148  jnb     short loc_18000D180
0x18000d14a  movzx   r8d, si
0x18000d14e  lea     rax, [r8+r8*4]
0x18000d152  lea     rdx, [rcx+rax*8]
0x18000d156  mov     rcx, [rsp+170h+var_130]
0x18000d15b  mov     rcx, [rcx+r8*8]
0x18000d15f  call    ComResourceFromCDPResource_2
0x18000d164  test    eax, eax
0x18000d166  js      short loc_18000D173
0x18000d168  add     si, r14w
0x18000d16c  mov     rcx, [rsp+170h+var_140]
0x18000d171  jmp     short loc_18000D141
0x18000d173  mov     dword ptr [rsp+170h+var_128], 266h
0x18000d17b  jmp     loc_18000D038
0x18000d180  mov     [rsp+170h+var_120], r12
0x18000d185  mov     [rbp+70h+arg_10], r12w
0x18000d18d  mov     [rbp+70h+var_F0], r12
0x18000d191  lea     rax, [rsp+170h+var_120]
0x18000d196  mov     [rbp+70h+var_48], rax
0x18000d19a  lea     rax, [rbp+70h+arg_10]
0x18000d1a1  mov     [rbp+70h+var_40], rax
0x18000d1a5  lea     rax, [rbp+70h+var_48]
0x18000d1a9  mov     [rsp+170h+var_100], rax
0x18000d1ae  mov     rax, [rbx]
0x18000d1b1  xor     r8d, r8d
0x18000d1b4  lea     r9, [rbp+70h+arg_10]
0x18000d1bb  xor     edx, edx
0x18000d1bd  mov     rcx, rbx
0x18000d1c0  mov     rax, [rax+0B8h]
0x18000d1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1cc  cmp     eax, 8004010Dh
0x18000d1d1  jnz     loc_18000D349
0x18000d1d7  movzx   eax, [rbp+70h+arg_10]
0x18000d1de  test    ax, ax
0x18000d1e1  jz      loc_18000D350
0x18000d1e7  mov     edx, eax
0x18000d1e9  lea     rcx, [rbp+70h+var_E8]
0x18000d1ed  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x18000d1f2  mov     rdx, rax
0x18000d1f5  lea     rcx, [rsp+170h+var_120]
0x18000d1fa  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000d1ff  mov     rcx, [rbp+70h+var_E8]; void *
0x18000d203  mov     [rbp+70h+var_E8], r12
0x18000d207  test    rcx, rcx
  ... truncated ...
```
