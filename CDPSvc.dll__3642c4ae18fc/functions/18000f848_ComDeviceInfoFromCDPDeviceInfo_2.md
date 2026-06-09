# ComDeviceInfoFromCDPDeviceInfo_2

- ea: `0x18000f848`
- end: `0x1800106bd`
- name: `ComDeviceInfoFromCDPDeviceInfo_2`
- size: `3701`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ab24`

## callees

- `0x180003e60`
- `0x180004fa0`
- `0x180007230`
- `0x180007e40`
- `0x1800085e0`
- `0x1800099b0`
- `0x18000a380`
- `0x18000cbd4`
- `0x18000cc2c`
- `0x18000cce4`
- `0x18000e9c8`
- `0x18000f848`
- `0x1800108e8`
- `0x180016b74`
- `0x180022a90`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fc58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fe9b`

## string_xrefs

- `0x18000f975`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fa34`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fafc`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fb86`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000fd9e`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18000ff85`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18001031e`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall ComDeviceInfoFromCDPDeviceInfo_2(__int64 a1, __int64 a2)
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
    v21 = ComEndpointFromCDPEndpoint(*((_QWORD *)v99 + i), v19 + 40LL * i);
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
    v24 = ComResourceFromCDPResource_1(*((_QWORD *)v100 + j), v34 + 40LL * j);
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
    v40 = ComApplicationFromCDPApplication_0(*((_QWORD *)v102 + k), v53 + 24LL * k);
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
  v59 = CopyString(v58);
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
  v59 = CopyString(v66);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 676;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v121,
    0);
  v67 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1);
  v59 = CopyString(v67);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 677;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v120,
    0);
  v68 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
  v59 = CopyString(v68);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 678;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v119,
    0);
  v69 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
  v59 = CopyString(v69);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 679;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v118,
    0);
  v70 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
  v59 = CopyString(v70);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 680;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v117,
    0);
  v71 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 176LL))(a1);
  v59 = CopyString(v71);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 681;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v116,
    0);
  v72 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
  v59 = CopyString(v72);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 682;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v115,
    0);
  v73 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
  v59 = CopyString(v73);
  if ( v59 < 0 )
  {
    LODWORD(v101) = 683;
    goto LABEL_69;
  }
  wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
    &v114,
    0);
  v74 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 192LL))(a1);
  v59 = CopyString(v74);
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
    v76 = CopyString(v75);
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
    v76 = CopyString(v79);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 690;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v111,
      0);
    v80 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 40LL))(v123[0]);
    v76 = CopyString(v80);
    if ( v76 < 0 )
    {
      LODWORD(v101) = 691;
      goto LABEL_96;
    }
    wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
      &v110,
      0);
    v81 = (char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v123[0] + 48LL))(v123[0]);
    v76 = CopyString(v81);
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
0x18000f848  mov     [rsp-8+arg_8], rbx
0x18000f84d  push    rbp
0x18000f84e  push    rsi
0x18000f84f  push    rdi
0x18000f850  push    r12
0x18000f852  push    r13
0x18000f854  push    r14
0x18000f856  push    r15
0x18000f858  lea     rbp, [rsp-40h]
0x18000f85d  sub     rsp, 140h
0x18000f864  mov     rdi, rdx
0x18000f867  mov     rbx, rcx
0x18000f86a  xor     r12d, r12d
0x18000f86d  test    rcx, rcx
0x18000f870  jnz     short loc_18000F87C
0x18000f872  mov     eax, 80070057h
0x18000f877  jmp     loc_18000FE6E
0x18000f87c  test    rdi, rdi
0x18000f87f  jnz     short loc_18000F88B
0x18000f881  mov     eax, 80004003h
0x18000f886  jmp     loc_18000FE6E
0x18000f88b  mov     rax, [rcx]
0x18000f88e  mov     rax, [rax+30h]
0x18000f892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f897  movzx   eax, ax
0x18000f89a  mov     [rdi+1Ch], eax
0x18000f89d  mov     rax, [rbx]
0x18000f8a0  mov     rcx, rbx
0x18000f8a3  mov     rax, [rax+38h]
0x18000f8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ac  movzx   eax, ax
0x18000f8af  mov     [rdi+20h], eax
0x18000f8b2  mov     rax, [rbx]
0x18000f8b5  mov     rcx, rbx
0x18000f8b8  mov     rax, [rax+40h]
0x18000f8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8c1  mov     [rdi+24h], eax
0x18000f8c4  mov     [rdi+18h], r12w
0x18000f8c9  mov     rax, [rbx]
0x18000f8cc  mov     rcx, rbx
0x18000f8cf  mov     rax, [rax+50h]
0x18000f8d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8d8  movzx   eax, al
0x18000f8db  mov     [rdi+30h], eax
0x18000f8de  mov     rax, [rbx]
0x18000f8e1  mov     rcx, rbx
0x18000f8e4  mov     rax, [rax+58h]
0x18000f8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ed  movzx   eax, al
0x18000f8f0  mov     [rdi+38h], eax
0x18000f8f3  mov     [rdi+60h], r12w
0x18000f8f8  mov     rax, [rbx]
0x18000f8fb  mov     rcx, rbx
0x18000f8fe  mov     rax, [rax+0A0h]
0x18000f905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f90a  movzx   eax, al
0x18000f90d  mov     [rdi+64h], eax
0x18000f910  mov     rax, [rbx]
0x18000f913  mov     rcx, rbx
0x18000f916  mov     rax, [rax+0C8h]
0x18000f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f922  movzx   eax, al
0x18000f925  mov     [rdi+34h], eax
0x18000f928  mov     rax, [rbx]
0x18000f92b  mov     rcx, rbx
0x18000f92e  mov     rax, [rax+0D8h]
0x18000f935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93a  mov     [rdi+0B8h], eax
0x18000f940  mov     rax, [rbx]
0x18000f943  xor     r8d, r8d
0x18000f946  lea     r9, [rbp+70h+arg_18]
0x18000f94d  xor     edx, edx
0x18000f94f  mov     rcx, rbx
0x18000f952  mov     rax, [rax+28h]
0x18000f956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f95b  test    eax, eax
0x18000f95d  jns     short loc_18000F98F
0x18000f95f  mov     dword ptr [rsp+170h+var_140], eax
0x18000f963  mov     dword ptr [rsp+170h+var_128], 217h
0x18000f96b  lea     rax, [rsp+170h+var_128]
0x18000f970  mov     [rsp+170h+var_150], rax
0x18000f975  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000f97c  lea     r8, [rsp+170h+var_140]
0x18000f981  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000f986  mov     eax, dword ptr [rsp+170h+var_140]
0x18000f98a  jmp     loc_18000FE6E
0x18000f98f  mov     [rsp+170h+var_138], r12
0x18000f994  lea     rax, [rsp+170h+var_138]
0x18000f999  mov     [rbp+70h+var_68], rax
0x18000f99d  lea     rax, [rbp+70h+arg_18]
0x18000f9a4  mov     [rbp+70h+var_60], rax
0x18000f9a8  lea     rax, [rbp+70h+var_68]
0x18000f9ac  mov     [rsp+170h+var_110], rax
0x18000f9b1  movzx   eax, [rbp+70h+arg_18]
0x18000f9b8  test    ax, ax
0x18000f9bb  jz      loc_18000FA75
0x18000f9c1  mov     edx, eax
0x18000f9c3  lea     rcx, [rsp+170h+var_100]
0x18000f9c8  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x18000f9cd  mov     rdx, rax
0x18000f9d0  lea     rcx, [rsp+170h+var_138]
0x18000f9d5  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000f9da  mov     rcx, [rsp+170h+var_100]; void *
0x18000f9df  mov     [rsp+170h+var_100], r12
0x18000f9e4  test    rcx, rcx
0x18000f9e7  jz      short loc_18000F9EE
0x18000f9e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f9ee  mov     rdx, [rsp+170h+var_138]
0x18000f9f3  test    rdx, rdx
0x18000f9f6  jz      loc_18000FE4A
0x18000f9fc  mov     rax, [rbx]
0x18000f9ff  lea     r9, [rbp+70h+arg_18]
0x18000fa06  movzx   r8d, [rbp+70h+arg_18]
0x18000fa0e  mov     rcx, rbx
0x18000fa11  mov     rax, [rax+28h]
0x18000fa15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa1a  test    eax, eax
0x18000fa1c  jns     short loc_18000FA6E
0x18000fa1e  mov     dword ptr [rsp+170h+var_140], eax
0x18000fa22  mov     dword ptr [rsp+170h+var_128], 22Ch
0x18000fa2a  lea     rax, [rsp+170h+var_128]
0x18000fa2f  mov     [rsp+170h+var_150], rax
0x18000fa34  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fa3b  lea     r8, [rsp+170h+var_140]
0x18000fa40  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000fa45  nop
0x18000fa46  lea     rcx, [rsp+170h+var_110]
0x18000fa4b  call    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7______ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___
0x18000fa50  nop
0x18000fa51  mov     rcx, [rsp+170h+var_138]; void *
0x18000fa56  mov     [rsp+170h+var_138], r12
0x18000fa5b  test    rcx, rcx
0x18000fa5e  jz      loc_18000F986
0x18000fa64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fa69  jmp     loc_18000F986
0x18000fa6e  movzx   eax, [rbp+70h+arg_18]
0x18000fa75  mov     [rsp+170h+var_118], r12
0x18000fa7a  movzx   eax, ax
0x18000fa7d  lea     rcx, [rax+rax*4]
0x18000fa81  shl     rcx, 3; cb
0x18000fa85  call    cs:__imp_CoTaskMemAlloc
0x18000fa8b  mov     rdx, rax
0x18000fa8e  lea     rcx, [rsp+170h+var_118]
0x18000fa93  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000fa98  mov     rcx, [rsp+170h+var_118]
0x18000fa9d  mov     [rsp+170h+var_128], rcx
0x18000faa2  test    rcx, rcx
0x18000faa5  jz      loc_18000FE3D
0x18000faab  mov     esi, r12d
0x18000faae  mov     r14d, 1
0x18000fab4  movzx   eax, [rbp+70h+arg_18]
0x18000fabb  cmp     esi, eax
0x18000fabd  jge     short loc_18000FB1F
0x18000fabf  movsxd  r8, esi
0x18000fac2  lea     rax, [r8+r8*4]
0x18000fac6  lea     rdx, [rcx+rax*8]
0x18000faca  mov     rcx, [rsp+170h+var_138]
0x18000facf  mov     rcx, [rcx+r8*8]
0x18000fad3  call    ComEndpointFromCDPEndpoint
0x18000fad8  test    eax, eax
0x18000fada  js      short loc_18000FAE6
0x18000fadc  add     esi, r14d
0x18000fadf  mov     rcx, [rsp+170h+var_128]
0x18000fae4  jmp     short loc_18000FAB4
0x18000fae6  mov     dword ptr [rsp+170h+var_140], eax
0x18000faea  mov     dword ptr [rsp+170h+var_128], 23Dh
0x18000faf2  lea     rax, [rsp+170h+var_128]
0x18000faf7  mov     [rsp+170h+var_150], rax
0x18000fafc  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fb03  lea     r8, [rsp+170h+var_140]
0x18000fb08  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000fb0d  nop
0x18000fb0e  xor     edx, edx
0x18000fb10  lea     rcx, [rsp+170h+var_118]
0x18000fb15  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000fb1a  jmp     loc_18000FA46
0x18000fb1f  mov     [rsp+170h+var_130], r12
0x18000fb24  mov     [rbp+70h+arg_0], r12w
0x18000fb2c  mov     [rsp+170h+var_108], r12
0x18000fb31  lea     rax, [rsp+170h+var_130]
0x18000fb36  mov     [rbp+70h+var_58], rax
0x18000fb3a  lea     rax, [rbp+70h+arg_0]
0x18000fb41  mov     [rbp+70h+var_50], rax
0x18000fb45  lea     rax, [rbp+70h+var_58]
0x18000fb49  mov     [rsp+170h+var_F8], rax
0x18000fb4e  mov     rax, [rbx]
0x18000fb51  xor     r8d, r8d
0x18000fb54  lea     r9, [rbp+70h+arg_0]
0x18000fb5b  xor     edx, edx
0x18000fb5d  mov     rcx, rbx
0x18000fb60  mov     rax, [rax+88h]
0x18000fb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6c  test    eax, eax
0x18000fb6e  jns     short loc_18000FBCD
0x18000fb70  mov     dword ptr [rsp+170h+var_128], 250h
0x18000fb78  mov     dword ptr [rsp+170h+var_140], eax
0x18000fb7c  lea     rax, [rsp+170h+var_128]
0x18000fb81  mov     [rsp+170h+var_150], rax
0x18000fb86  lea     r9, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000fb8d  lea     r8, [rsp+170h+var_140]
0x18000fb92  call    ??$Log@AEAJAEAY0EA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0EA@$$CBD$$QEAH@Z; Log<long &,char const (&)[64],int>(CDPLogLevel,char const *,long &,char const (&)[64],int &&)
0x18000fb97  nop
0x18000fb98  lea     rcx, [rsp+170h+var_F8]
0x18000fb9d  call    ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7______ScopeWarden__lambda_e15f1604efc37812d9ca2198c67d17a7___
0x18000fba2  nop
0x18000fba3  xor     edx, edx
0x18000fba5  lea     rcx, [rsp+170h+var_108]
0x18000fbaa  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000fbaf  nop
0x18000fbb0  mov     rcx, [rsp+170h+var_130]; void *
0x18000fbb5  mov     [rsp+170h+var_130], r12
0x18000fbba  test    rcx, rcx
0x18000fbbd  jz      loc_18000FB0E
0x18000fbc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fbc8  jmp     loc_18000FB0E
0x18000fbcd  movzx   eax, [rbp+70h+arg_0]
0x18000fbd4  test    ax, ax
0x18000fbd7  jz      short loc_18000FC4D
0x18000fbd9  mov     edx, eax
0x18000fbdb  lea     rcx, [rsp+170h+var_100]
0x18000fbe0  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPResource@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPResource@@U?$default_delete@$$BY0A@PEAVICDPResource@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPResource * [0]>(unsigned __int64)
0x18000fbe5  mov     rdx, rax
0x18000fbe8  lea     rcx, [rsp+170h+var_130]
0x18000fbed  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000fbf2  mov     rcx, [rsp+170h+var_100]; void *
0x18000fbf7  mov     [rsp+170h+var_100], r12
0x18000fbfc  test    rcx, rcx
0x18000fbff  jz      short loc_18000FC06
0x18000fc01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fc06  mov     rdx, [rsp+170h+var_130]
0x18000fc0b  test    rdx, rdx
0x18000fc0e  jz      loc_18000FE10
0x18000fc14  mov     rax, [rbx]
0x18000fc17  lea     r9, [rbp+70h+arg_0]
0x18000fc1e  movzx   r8d, [rbp+70h+arg_0]
0x18000fc26  mov     rcx, rbx
0x18000fc29  mov     rax, [rax+88h]
0x18000fc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc35  test    eax, eax
0x18000fc37  jns     short loc_18000FC46
0x18000fc39  mov     dword ptr [rsp+170h+var_128], 256h
0x18000fc41  jmp     loc_18000FB78
0x18000fc46  movzx   eax, [rbp+70h+arg_0]
0x18000fc4d  movzx   eax, ax
0x18000fc50  lea     rcx, [rax+rax*4]
0x18000fc54  shl     rcx, 3; cb
0x18000fc58  call    cs:__imp_CoTaskMemAlloc
0x18000fc5e  mov     rdx, rax
0x18000fc61  lea     rcx, [rsp+170h+var_108]
0x18000fc66  call    ?reset@?$unique_ptr@UCDPComApplication@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUCDPComApplication@@@Z; wistd::unique_ptr<CDPComApplication,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(CDPComApplication *)
0x18000fc6b  mov     rcx, [rsp+170h+var_108]
0x18000fc70  mov     [rsp+170h+var_140], rcx
0x18000fc75  test    rcx, rcx
0x18000fc78  jz      loc_18000FE10
0x18000fc7e  mov     esi, r12d
0x18000fc81  cmp     si, [rbp+70h+arg_0]
0x18000fc88  jnb     short loc_18000FCC0
0x18000fc8a  movzx   r8d, si
0x18000fc8e  lea     rax, [r8+r8*4]
0x18000fc92  lea     rdx, [rcx+rax*8]
0x18000fc96  mov     rcx, [rsp+170h+var_130]
0x18000fc9b  mov     rcx, [rcx+r8*8]
0x18000fc9f  call    ComResourceFromCDPResource_1
0x18000fca4  test    eax, eax
0x18000fca6  js      short loc_18000FCB3
0x18000fca8  add     si, r14w
0x18000fcac  mov     rcx, [rsp+170h+var_140]
0x18000fcb1  jmp     short loc_18000FC81
0x18000fcb3  mov     dword ptr [rsp+170h+var_128], 266h
0x18000fcbb  jmp     loc_18000FB78
0x18000fcc0  mov     [rsp+170h+var_120], r12
0x18000fcc5  mov     [rbp+70h+arg_10], r12w
0x18000fccd  mov     [rbp+70h+var_F0], r12
0x18000fcd1  lea     rax, [rsp+170h+var_120]
0x18000fcd6  mov     [rbp+70h+var_48], rax
0x18000fcda  lea     rax, [rbp+70h+arg_10]
0x18000fce1  mov     [rbp+70h+var_40], rax
0x18000fce5  lea     rax, [rbp+70h+var_48]
0x18000fce9  mov     [rsp+170h+var_100], rax
0x18000fcee  mov     rax, [rbx]
0x18000fcf1  xor     r8d, r8d
0x18000fcf4  lea     r9, [rbp+70h+arg_10]
0x18000fcfb  xor     edx, edx
0x18000fcfd  mov     rcx, rbx
0x18000fd00  mov     rax, [rax+0B8h]
0x18000fd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd0c  cmp     eax, 8004010Dh
0x18000fd11  jnz     loc_18000FE89
0x18000fd17  movzx   eax, [rbp+70h+arg_10]
0x18000fd1e  test    ax, ax
0x18000fd21  jz      loc_18000FE90
0x18000fd27  mov     edx, eax
0x18000fd29  lea     rcx, [rbp+70h+var_E8]
0x18000fd2d  call    ??$make_unique_nothrow@$$BY0A@PEAVICDPEndpointAccount@@@wil@@YA?AV?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ICDPEndpointAccount * [0]>(unsigned __int64)
0x18000fd32  mov     rdx, rax
0x18000fd35  lea     rcx, [rsp+170h+var_120]
0x18000fd3a  call    ??4?$unique_ptr@$$BY0A@PEAVICDPEndpointAccount@@U?$default_delete@$$BY0A@PEAVICDPEndpointAccount@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>>::operator=(wistd::unique_ptr<ICDPEndpointAccount * [0],wistd::default_delete<ICDPEndpointAccount * [0]>> &&)
0x18000fd3f  mov     rcx, [rbp+70h+var_E8]; void *
0x18000fd43  mov     [rbp+70h+var_E8], r12
0x18000fd47  test    rcx, rcx
  ... truncated ...
```
