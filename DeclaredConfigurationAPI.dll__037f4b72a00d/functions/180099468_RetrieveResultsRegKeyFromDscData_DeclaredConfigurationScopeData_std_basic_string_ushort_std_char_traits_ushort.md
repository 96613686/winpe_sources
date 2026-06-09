# RetrieveResultsRegKeyFromDscData(DeclaredConfigurationScopeData *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180099468`
- end: `0x180099c4e`
- name: `?RetrieveResultsRegKeyFromDscData@@YAXPEAUDeclaredConfigurationScopeData@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11V?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@PEAV23@@Z`
- size: `2022`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180098410`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x180011fe0`
- `0x18001438c`
- `0x180018ac0`
- `0x18001924c`
- `0x1800192b4`
- `0x180019d38`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001cec8`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004b500`
- `0x18004eb5c`
- `0x18005124c`
- `0x180054b5c`
- `0x180055a14`
- `0x1800725e0`
- `0x180099468`
- `0x18009ff30`
- `0x1800a0ce4`
- `0x1801006c8`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099754`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800997cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099a15`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099754`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800997cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099a15`

## string_xrefs

- `0x180099519`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099551`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099a93`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099aaf`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099acb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099ae7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099bc9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099be5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099c01`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099c1d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099c3c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=33
__int64 __fastcall RetrieveResultsRegKeyFromDscData(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        char **a6)
{
  const unsigned __int16 *v8; // rsi
  int EnrollmentIdSidStateDocIdKey; // ebx
  int RegistryString; // eax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // edi
  const unsigned __int16 *v16; // rdx
  unsigned int i; // r13d
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  int RegistryDWORD; // eax
  int v23; // ecx
  const unsigned __int16 *v24; // rdx
  int v25; // ebx
  _QWORD *v26; // rdx
  const unsigned __int16 *v27; // rdx
  int v28; // ebx
  _QWORD *v29; // rdx
  unsigned int v30; // ebx
  const unsigned __int16 *v31; // rdx
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  const unsigned __int16 *v39; // rdx
  int v40; // eax
  const unsigned __int16 *v41; // rdx
  int v42; // eax
  __int64 v43; // rbx
  __int64 v44; // rdi
  _QWORD *v45; // rdx
  _QWORD *v46; // rcx
  __int64 v47; // r8
  __int64 v49; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v50; // [rsp+28h] [rbp-D8h] BYREF
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v52; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v54; // [rsp+48h] [rbp-B8h] BYREF
  int v55; // [rsp+4Ch] [rbp-B4h]
  __int64 v56; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v57; // [rsp+58h] [rbp-A8h] BYREF
  void **p_Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  char v60; // [rsp+70h] [rbp-90h]
  _QWORD v61[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  char **v63; // [rsp+90h] [rbp-70h]
  HKEY *v64; // [rsp+98h] [rbp-68h] BYREF
  HKEY v65; // [rsp+A0h] [rbp-60h] BYREF
  char v66; // [rsp+A8h] [rbp-58h]
  _QWORD *v67; // [rsp+B0h] [rbp-50h]
  unsigned __int16 **v68; // [rsp+B8h] [rbp-48h]
  char v69; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v70; // [rsp+C8h] [rbp-38h]
  _QWORD *v71; // [rsp+D0h] [rbp-30h]
  _QWORD *v72; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v73[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v74; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v75[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v76; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v77[4]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v78[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v79[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v80[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v81[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v82[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v83[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v84[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v85[32]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v86[16]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v8 = a2;
  v70 = a2;
  v71 = a3;
  v72 = a4;
  v67 = a5;
  v63 = a6;
  v50 = 0;
  v57 = 0;
  v68 = &v57;
  v69 = 1;
  v64 = &v50;
  v65 = 0;
  v66 = 1;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const unsigned __int16 **)a2;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v65, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v64);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2EE4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
      v49);
  RegistryString = DCCDNUtil_GetRegistryString(v50, 0, L"MostRecentVersion", &v57);
  if ( RegistryString < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2EF1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)RegistryString,
      v49);
  v11 = std::wstring::wstring((__int64)v84, (__int64)L"cooked");
  v12 = std::wstring::wstring((__int64)v83, (__int64)L"\\");
  v13 = std::wstring::wstring((__int64)v82, (__int64)v57);
  v14 = std::operator+<unsigned short>(v81, v13, v12);
  std::operator+<unsigned short>(v77, v14, v11);
  std::wstring::_Tidy_deallocate(v81);
  std::wstring::_Tidy_deallocate(v82);
  std::wstring::_Tidy_deallocate(v83);
  std::wstring::_Tidy_deallocate(v84);
  v15 = 1;
  v55 = 1;
  v86[0] = 0;
  v54 = 0;
  v16 = (const unsigned __int16 *)v77;
  if ( v77[3] > (unsigned __int16 *)7 )
    v16 = v77[0];
  DCCDNUtil_GetRegistryDWORD(v50, v16, L"CspCount", &v54);
  for ( i = 0; ; ++i )
  {
    if ( i >= v54 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2F8F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x80070057LL,
        v49);
    v18 = StringCchPrintfW(v86, 0xFu, L"CSP%d", v15);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2F03,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v18,
        v49);
    v19 = std::wstring::wstring((__int64)v78, (__int64)L"\\");
    v20 = std::operator+<unsigned short>(v75, v77, v19);
    std::operator+<unsigned short>(v73, v20, v86);
    std::wstring::_Tidy_deallocate(v75);
    std::wstring::_Tidy_deallocate(v78);
    LODWORD(v49) = 0;
    v21 = (const unsigned __int16 *)v73;
    if ( v74 > 7 )
      v21 = v73[0];
    RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v50, v21, L"ProviderType", (unsigned int *)&v49);
    v23 = v49;
    if ( RegistryDWORD < 0 )
      v23 = 2;
    if ( v23 != 2 )
      goto LABEL_60;
    v53 = 0;
    p_Block = (void **)&v53;
    v59 = 0;
    v60 = 1;
    v24 = (const unsigned __int16 *)v73;
    if ( v74 > 7 )
      v24 = v73[0];
    v25 = DCCDNUtil_GetRegistryString(v50, v24, L"namespace", &v59);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_Block);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2F17,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v25,
        v49);
    v26 = a3[3] <= 7u ? a3 : (_QWORD *)*a3;
    if ( !(unsigned int)_o__wcsnicmp(v53, v26, 260) )
      break;
LABEL_59:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v53);
LABEL_60:
    std::wstring::_Tidy_deallocate(v73);
LABEL_61:
    v55 = ++v15;
  }
  v56 = 0;
  p_Block = (void **)&v56;
  v59 = 0;
  v60 = 1;
  v27 = (const unsigned __int16 *)v73;
  if ( v74 > 7 )
    v27 = v73[0];
  v28 = DCCDNUtil_GetRegistryString(v50, v27, L"className", &v59);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_Block);
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F22,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v28,
      v49);
  if ( a4[3] <= 7u )
    v29 = a4;
  else
    v29 = (_QWORD *)*a4;
  v30 = 0;
  if ( (unsigned int)_o__wcsnicmp(v56, v29, 260) )
  {
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v56);
    goto LABEL_59;
  }
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v61);
  LODWORD(v49) = 0;
  v31 = (const unsigned __int16 *)v73;
  if ( v74 > 7 )
    v31 = v73[0];
  v32 = DCCDNUtil_GetRegistryDWORD(v50, v31, L"KeyValueCount", (unsigned int *)&v49);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F2E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v32,
      v49);
  v78[0] = 0;
  v33 = v49;
  if ( (_DWORD)v49 )
  {
    do
    {
      v34 = StringCchPrintfW(v78, 0xFu, L"KeyValue%d", ++v30, v49);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2F38,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v34,
          v49);
      v35 = std::wstring::wstring((__int64)v79, (__int64)L"\\");
      v36 = std::operator+<unsigned short>(v85, v73, v35);
      std::operator+<unsigned short>(v75, v36, v78);
      std::wstring::_Tidy_deallocate(v85);
      std::wstring::_Tidy_deallocate(v79);
      v52 = 0;
      Block = 0;
      p_Block = &Block;
      v59 = (unsigned __int16 *)&v52;
      v60 = 1;
      LODWORD(v49) = 0;
      v37 = (const unsigned __int16 *)v75;
      if ( v76 > 7 )
        v37 = v75[0];
      v38 = DCCDNUtil_GetRegistryDWORD(v50, v37, L"Key", (unsigned int *)&v49);
      if ( v38 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2F4C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v38,
          v49);
      if ( (_DWORD)v49 )
      {
        v39 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v39 = v75[0];
        v40 = DCCDNUtil_GetRegistryString(v50, v39, L"Name", (unsigned __int16 **)&Block);
        if ( v40 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2F58,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v40,
            v49);
        v41 = (const unsigned __int16 *)v75;
        if ( v76 > 7 )
          v41 = v75[0];
        v42 = DCCDNUtil_GetRegistryString(v50, v41, L"value", &v52);
        if ( v42 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2F5F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v42,
            v49);
        std::wstring::wstring((__int64)v79, (__int64)Block);
        std::wstring::wstring((__int64)v80, (__int64)v52);
        std::map<std::wstring,std::wstring>::insert<std::pair<std::wstring,std::wstring>,0>(v61, &v64, v79);
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v79);
      }
      operator delete(Block);
      Block = 0;
      operator delete(v52);
      v52 = 0;
      std::wstring::_Tidy_deallocate(v75);
    }
    while ( v30 < v33 );
  }
  v43 = *a5;
  v44 = a5[1];
  while ( v43 != v44 )
  {
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
      v61,
      &v62,
      v43);
    if ( v62 == v61[0] )
      goto LABEL_57;
    v45 = (_QWORD *)(v43 + 32);
    if ( *(_QWORD *)(v43 + 56) > 7u )
      v45 = (_QWORD *)*v45;
    v46 = (_QWORD *)(v62 + 64);
    if ( *(_QWORD *)(v62 + 88) > 7u )
      v46 = (_QWORD *)*v46;
    if ( (unsigned int)_o__wcsnicmp(v46, v45, 260) )
    {
LABEL_57:
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v61,
        v61);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v56);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v53);
      std::wstring::_Tidy_deallocate(v73);
      v15 = v55;
      goto LABEL_61;
    }
    v43 += 64;
  }
  v47 = -1;
  do
    ++v47;
  while ( v86[v47] );
  std::wstring::_Assign<unsigned short>(v63, v86, (char *)v47);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
    v61,
    v61);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v56);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v53);
  std::wstring::_Tidy_deallocate(v73);
  std::wstring::_Tidy_deallocate(v77);
  operator delete(v57);
  v57 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v50);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(a4);
  return std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(a5);
}

```

## disassembly

```asm
0x180099468  push    rbp
0x18009946a  push    rbx
0x18009946b  push    rsi
0x18009946c  push    rdi
0x18009946d  push    r12
0x18009946f  push    r13
0x180099471  push    r14
0x180099473  push    r15
0x180099475  lea     rbp, [rsp-178h]
0x18009947d  sub     rsp, 278h
0x180099484  mov     rax, cs:__security_cookie
0x18009948b  xor     rax, rsp
0x18009948e  mov     [rbp+1B0h+var_50], rax
0x180099495  mov     r15, r9
0x180099498  mov     r14, r8
0x18009949b  mov     rsi, rdx
0x18009949e  mov     [rbp+1B0h+var_1E8], rdx
0x1800994a2  mov     [rbp+1B0h+var_1E0], r8
0x1800994a6  mov     [rbp+1B0h+var_1D8], r9
0x1800994aa  mov     r12, [rbp+1B0h+arg_20]
0x1800994b1  mov     [rbp+1B0h+var_200], r12
0x1800994b5  mov     rax, [rbp+1B0h+arg_28]
0x1800994bc  mov     [rbp+1B0h+var_220], rax
0x1800994c0  xor     edi, edi
0x1800994c2  mov     [rsp+2B0h+var_288], rdi
0x1800994c7  mov     [rsp+2B0h+var_258], rdi
0x1800994cc  lea     rax, [rsp+2B0h+var_258]
0x1800994d1  mov     [rbp+1B0h+var_1F8], rax
0x1800994d5  mov     [rbp+1B0h+var_1F0], 1
0x1800994d9  lea     rax, [rsp+2B0h+var_288]
0x1800994de  mov     [rbp+1B0h+var_218], rax
0x1800994e2  mov     [rbp+1B0h+var_210], rdi
0x1800994e6  mov     [rbp+1B0h+var_208], 1
0x1800994ea  cmp     qword ptr [rdx+18h], 7
0x1800994ef  jbe     short loc_1800994F4
0x1800994f1  mov     rdx, [rdx]; unsigned __int16 *
0x1800994f4  xor     r9d, r9d; int
0x1800994f7  lea     r8, [rbp+1B0h+var_210]; HKEY *
0x1800994fb  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180099500  mov     ebx, eax
0x180099502  lea     rcx, [rbp+1B0h+var_218]
0x180099506  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009950b  test    ebx, ebx
0x18009950d  jns     short loc_18009952B
0x18009950f  mov     rcx, [rbp+1B8h]; this
0x180099516  mov     r9d, ebx; char *
0x180099519  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180099520  mov     edx, 2EE4h; void *
0x180099525  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18009952b  lea     r9, [rsp+2B0h+var_258]; unsigned __int16 **
0x180099530  lea     r8, aMostrecentvers; "MostRecentVersion"
0x180099537  xor     edx, edx; unsigned __int16 *
0x180099539  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x18009953e  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180099543  test    eax, eax
0x180099545  jns     short loc_180099563
0x180099547  mov     rcx, [rbp+1B8h]; this
0x18009954e  mov     r9d, eax; char *
0x180099551  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180099558  mov     edx, 2EF1h; void *
0x18009955d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180099563  lea     rdx, aCooked; "cooked"
0x18009956a  lea     rcx, [rbp+1B0h+var_B0]
0x180099571  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099576  mov     rdi, rax
0x180099579  lea     rdx, StringValue; "\\"
0x180099580  lea     rcx, [rbp+1B0h+var_D0]
0x180099587  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009958c  mov     rbx, rax
0x18009958f  mov     rdx, [rsp+2B0h+var_258]
0x180099594  lea     rcx, [rbp+1B0h+var_F0]
0x18009959b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800995a0  nop
0x1800995a1  mov     r8, rbx
0x1800995a4  mov     rdx, rax
0x1800995a7  lea     rcx, [rbp+1B0h+var_110]
0x1800995ae  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800995b3  nop
0x1800995b4  mov     r8, rdi
0x1800995b7  mov     rdx, rax
0x1800995ba  lea     rcx, [rbp+1B0h+var_190]
0x1800995be  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800995c3  nop
0x1800995c4  lea     rcx, [rbp+1B0h+var_110]
0x1800995cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800995d0  nop
0x1800995d1  lea     rcx, [rbp+1B0h+var_F0]
0x1800995d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800995dd  nop
0x1800995de  lea     rcx, [rbp+1B0h+var_D0]
0x1800995e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800995ea  nop
0x1800995eb  lea     rcx, [rbp+1B0h+var_B0]
0x1800995f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800995f7  mov     edi, 1
0x1800995fc  mov     [rsp+2B0h+var_264], edi
0x180099600  xor     ebx, ebx
0x180099602  mov     [rbp+1B0h+var_70], bx
0x180099609  mov     [rsp+2B0h+var_268], ebx
0x18009960d  lea     rdx, [rbp+1B0h+var_190]
0x180099611  cmp     [rbp+1B0h+var_178], 7
0x180099616  cmova   rdx, [rbp+1B0h+var_190]; unsigned __int16 *
0x18009961b  lea     r9, [rsp+2B0h+var_268]; unsigned int *
0x180099620  lea     r8, aCspcount_0; "CspCount"
0x180099627  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x18009962c  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099631  mov     r13d, ebx
0x180099634  cmp     r13d, [rsp+2B0h+var_268]
0x180099639  jnb     loc_180099C2F
0x18009963f  mov     r9d, edi
0x180099642  lea     r8, aCspD; "CSP%d"
0x180099649  mov     edx, 0Fh; unsigned __int64
0x18009964e  lea     rcx, [rbp+1B0h+var_70]; unsigned __int16 *
0x180099655  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009965a  test    eax, eax
0x18009965c  js      loc_180099C13
0x180099662  lea     rdx, StringValue; "\\"
0x180099669  lea     rcx, [rbp+1B0h+var_170]
0x18009966d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099672  nop
0x180099673  mov     r8, rax
0x180099676  lea     rdx, [rbp+1B0h+var_190]
0x18009967a  lea     rcx, [rbp+1B0h+var_1B0]
0x18009967e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180099683  nop
0x180099684  lea     r8, [rbp+1B0h+var_70]
0x18009968b  mov     rdx, rax
0x18009968e  lea     rcx, [rbp+1B0h+var_1D0]
0x180099692  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180099697  nop
0x180099698  lea     rcx, [rbp+1B0h+var_1B0]
0x18009969c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800996a1  nop
0x1800996a2  lea     rcx, [rbp+1B0h+var_170]
0x1800996a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800996ab  mov     dword ptr [rsp+2B0h+var_290], ebx; int
0x1800996af  lea     rdx, [rbp+1B0h+var_1D0]
0x1800996b3  cmp     [rbp+1B0h+var_1B8], 7
0x1800996b8  cmova   rdx, [rbp+1B0h+var_1D0]; unsigned __int16 *
0x1800996bd  lea     r9, [rsp+2B0h+var_290]; unsigned int *
0x1800996c2  lea     r8, aProvidertype_0; "ProviderType"
0x1800996c9  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x1800996ce  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800996d3  mov     ecx, dword ptr [rsp+2B0h+var_290]
0x1800996d7  test    eax, eax
0x1800996d9  mov     eax, 2
0x1800996de  cmovs   ecx, eax
0x1800996e1  cmp     ecx, eax
0x1800996e3  jnz     loc_180099A72
0x1800996e9  mov     [rsp+2B0h+var_270], rbx
0x1800996ee  lea     rax, [rsp+2B0h+var_270]
0x1800996f3  mov     [rsp+2B0h+var_250], rax
0x1800996f8  mov     [rsp+2B0h+var_248], rbx
0x1800996fd  mov     [rsp+2B0h+var_240], 1
0x180099702  lea     rdx, [rbp+1B0h+var_1D0]
0x180099706  cmp     [rbp+1B0h+var_1B8], 7
0x18009970b  cmova   rdx, [rbp+1B0h+var_1D0]; unsigned __int16 *
0x180099710  lea     r9, [rsp+2B0h+var_248]; unsigned __int16 **
0x180099715  lea     r8, aNamespace; "namespace"
0x18009971c  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x180099721  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180099726  mov     ebx, eax
0x180099728  lea     rcx, [rsp+2B0h+var_250]
0x18009972d  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180099732  test    ebx, ebx
0x180099734  js      loc_180099BF7
0x18009973a  cmp     qword ptr [r14+18h], 7
0x18009973f  jbe     short loc_180099746
0x180099741  mov     rdx, [r14]
0x180099744  jmp     short loc_180099749
0x180099746  mov     rdx, r14
0x180099749  mov     r8d, 104h
0x18009974f  mov     rcx, [rsp+2B0h+var_270]
0x180099754  call    cs:__imp__o__wcsnicmp
0x18009975a  xor     ebx, ebx
0x18009975c  test    eax, eax
0x18009975e  jnz     loc_180099A67
0x180099764  mov     [rsp+2B0h+var_260], rbx
0x180099769  lea     rax, [rsp+2B0h+var_260]
0x18009976e  mov     [rsp+2B0h+var_250], rax
0x180099773  mov     [rsp+2B0h+var_248], rbx
0x180099778  mov     [rsp+2B0h+var_240], 1
0x18009977d  lea     rdx, [rbp+1B0h+var_1D0]
0x180099781  cmp     [rbp+1B0h+var_1B8], 7
0x180099786  cmova   rdx, [rbp+1B0h+var_1D0]; unsigned __int16 *
0x18009978b  lea     r9, [rsp+2B0h+var_248]; unsigned __int16 **
0x180099790  lea     r8, aClassname; "className"
0x180099797  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x18009979c  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800997a1  mov     ebx, eax
0x1800997a3  lea     rcx, [rsp+2B0h+var_250]
0x1800997a8  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800997ad  test    ebx, ebx
0x1800997af  js      loc_180099BDB
0x1800997b5  cmp     qword ptr [r15+18h], 7
0x1800997ba  jbe     short loc_1800997C1
0x1800997bc  mov     rdx, [r15]
0x1800997bf  jmp     short loc_1800997C4
0x1800997c1  mov     rdx, r15
0x1800997c4  mov     r8d, 104h
0x1800997ca  mov     rcx, [rsp+2B0h+var_260]
0x1800997cf  call    cs:__imp__o__wcsnicmp
0x1800997d5  xor     ebx, ebx
0x1800997d7  test    eax, eax
0x1800997d9  jnz     loc_180099A5C
0x1800997df  lea     rcx, [rsp+2B0h+var_238]
0x1800997e4  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1800997e9  nop
0x1800997ea  mov     dword ptr [rsp+2B0h+var_290], ebx; int
0x1800997ee  lea     rdx, [rbp+1B0h+var_1D0]
0x1800997f2  cmp     [rbp+1B0h+var_1B8], 7
0x1800997f7  cmova   rdx, [rbp+1B0h+var_1D0]; unsigned __int16 *
0x1800997fc  lea     r9, [rsp+2B0h+var_290]; unsigned int *
0x180099801  lea     r8, aKeyvaluecount; "KeyValueCount"
0x180099808  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x18009980d  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099812  test    eax, eax
0x180099814  js      loc_180099BBF
0x18009981a  mov     [rbp+1B0h+var_170], bx
0x18009981e  mov     edi, dword ptr [rsp+2B0h+var_290]
0x180099822  test    edi, edi
0x180099824  jz      loc_1800999C5
0x18009982a  inc     ebx
0x18009982c  mov     r9d, ebx
0x18009982f  lea     r8, aKeyvalueD; "KeyValue%d"
0x180099836  mov     edx, 0Fh; unsigned __int64
0x18009983b  lea     rcx, [rbp+1B0h+var_170]; unsigned __int16 *
0x18009983f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099844  test    eax, eax
0x180099846  js      loc_180099ADD
0x18009984c  lea     rdx, StringValue; "\\"
0x180099853  lea     rcx, [rbp+1B0h+var_150]
0x180099857  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009985c  nop
0x18009985d  mov     r8, rax
0x180099860  lea     rdx, [rbp+1B0h+var_1D0]
0x180099864  lea     rcx, [rbp+1B0h+var_90]
0x18009986b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180099870  nop
0x180099871  lea     r8, [rbp+1B0h+var_170]
0x180099875  mov     rdx, rax
0x180099878  lea     rcx, [rbp+1B0h+var_1B0]
0x18009987c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180099881  nop
0x180099882  lea     rcx, [rbp+1B0h+var_90]
0x180099889  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009988e  nop
0x18009988f  lea     rcx, [rbp+1B0h+var_150]
0x180099893  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099898  xor     ecx, ecx
0x18009989a  mov     [rsp+2B0h+var_278], rcx
0x18009989f  mov     [rsp+2B0h+Block], rcx
0x1800998a4  lea     rax, [rsp+2B0h+Block]
0x1800998a9  mov     [rsp+2B0h+var_250], rax
0x1800998ae  lea     rax, [rsp+2B0h+var_278]
0x1800998b3  mov     [rsp+2B0h+var_248], rax
0x1800998b8  mov     [rsp+2B0h+var_240], 1
0x1800998bd  mov     dword ptr [rsp+2B0h+var_290], ecx; int
0x1800998c1  lea     rdx, [rbp+1B0h+var_1B0]
0x1800998c5  cmp     [rbp+1B0h+var_198], 7
0x1800998ca  cmova   rdx, [rbp+1B0h+var_1B0]; unsigned __int16 *
0x1800998cf  lea     r9, [rsp+2B0h+var_290]; unsigned int *
0x1800998d4  lea     r8, aKey; "Key"
0x1800998db  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x1800998e0  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800998e5  xor     ecx, ecx
0x1800998e7  test    eax, eax
0x1800998e9  js      loc_180099AC1
0x1800998ef  cmp     dword ptr [rsp+2B0h+var_290], ecx
0x1800998f3  jz      loc_18009998F
0x1800998f9  lea     rdx, [rbp+1B0h+var_1B0]
0x1800998fd  cmp     [rbp+1B0h+var_198], 7
0x180099902  cmova   rdx, [rbp+1B0h+var_1B0]; unsigned __int16 *
0x180099907  lea     r9, [rsp+2B0h+Block]; unsigned __int16 **
0x18009990c  lea     r8, aName; "Name"
0x180099913  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x180099918  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18009991d  test    eax, eax
0x18009991f  js      loc_180099AA5
0x180099925  lea     rdx, [rbp+1B0h+var_1B0]
0x180099929  cmp     [rbp+1B0h+var_198], 7
0x18009992e  cmova   rdx, [rbp+1B0h+var_1B0]; unsigned __int16 *
0x180099933  lea     r9, [rsp+2B0h+var_278]; unsigned __int16 **
0x180099938  lea     r8, aValue_0; "value"
0x18009993f  mov     rcx, [rsp+2B0h+var_288]; HKEY
0x180099944  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180099949  test    eax, eax
0x18009994b  js      loc_180099A89
0x180099951  mov     rdx, [rsp+2B0h+Block]
0x180099956  lea     rcx, [rbp+1B0h+var_150]
0x18009995a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009995f  nop
0x180099960  mov     rdx, [rsp+2B0h+var_278]
0x180099965  lea     rcx, [rbp+1B0h+var_130]
0x18009996c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099971  nop
0x180099972  lea     r8, [rbp+1B0h+var_150]
0x180099976  lea     rdx, [rbp+1B0h+var_218]
0x18009997a  lea     rcx, [rsp+2B0h+var_238]
0x18009997f  call    ??$insert@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::map<std::wstring,std::wstring>::insert<std::pair<std::wstring,std::wstring>,0>(std::pair<std::wstring,std::wstring> &&)
  ... truncated ...
```
