# RetrieveResultsRegKeyFromUriData(DeclaredConfigurationScopeData *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180099c54`
- end: `0x18009a2de`
- name: `?RetrieveResultsRegKeyFromUriData@@YAXPEAUDeclaredConfigurationScopeData@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEAV23@2@Z`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180097f4c`

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
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004b500`
- `0x18004eb5c`
- `0x1800725e0`
- `0x180099c54`
- `0x1801006c8`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099f51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009a09e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180099f51`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009a09e`

## string_xrefs

- `0x180099f77`: `UriCount`
- `0x180099d2f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099d67`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a1e9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a205`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a221`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a23d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a24f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a28e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a2ad`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18009a2cc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180099fa8`: `URI%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall RetrieveResultsRegKeyFromUriData(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        _QWORD *a3,
        _QWORD *a4,
        char **a5,
        char **a6)
{
  const unsigned __int16 *v8; // rsi
  int EnrollmentIdSidStateDocIdKey; // ebx
  int RegistryString; // eax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebx
  const unsigned __int16 *v16; // rdx
  unsigned int i; // r13d
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  int RegistryDWORD; // eax
  unsigned int v23; // ecx
  const unsigned __int16 *v24; // rdx
  int v25; // ebx
  _QWORD *v26; // rdx
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  unsigned int v29; // r12d
  unsigned int j; // edi
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  const unsigned __int16 *v35; // rdx
  int v36; // ebx
  _QWORD *v37; // rdx
  __int64 v38; // rbx
  __int64 v39; // r8
  unsigned int v41; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v42; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v43; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+34h] [rbp-CCh]
  __int64 v45; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  char **v48; // [rsp+50h] [rbp-B0h]
  char **v49; // [rsp+58h] [rbp-A8h]
  void **p_Block; // [rsp+60h] [rbp-A0h]
  char v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  _QWORD *v53; // [rsp+78h] [rbp-88h]
  _QWORD *v54; // [rsp+80h] [rbp-80h]
  HKEY *v55; // [rsp+88h] [rbp-78h] BYREF
  HKEY v56; // [rsp+90h] [rbp-70h] BYREF
  char v57; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v58[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v59; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v60[4]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v61[16]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v62[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v63[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v64[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v65[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v66[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v67[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v68[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int16 v69[16]; // [rsp+1E8h] [rbp+E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v8 = a2;
  v52 = a2;
  v53 = a3;
  v54 = a4;
  v48 = a5;
  v49 = a6;
  if ( !a1 || !a5 || !a6 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E3E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80070057LL,
      v41);
  v42 = 0;
  Block = 0;
  p_Block = &Block;
  v51 = 1;
  v55 = &v42;
  v56 = 0;
  v57 = 1;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const unsigned __int16 **)a2;
  EnrollmentIdSidStateDocIdKey = DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(a1, a2, &v56, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v55);
  if ( EnrollmentIdSidStateDocIdKey < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E54,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)EnrollmentIdSidStateDocIdKey,
      v41);
  RegistryString = DCCDNUtil_GetRegistryString(v42, 0, L"MostRecentVersion", (unsigned __int16 **)&Block);
  if ( RegistryString < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E61,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)RegistryString,
      v41);
  v11 = std::wstring::wstring((__int64)v66, (__int64)L"cooked");
  v12 = std::wstring::wstring((__int64)v65, (__int64)L"\\");
  v13 = std::wstring::wstring((__int64)v64, (__int64)Block);
  v14 = std::operator+<unsigned short>(v63, v13, v12);
  std::operator+<unsigned short>(v62, v14, v11);
  std::wstring::_Tidy_deallocate(v63);
  std::wstring::_Tidy_deallocate(v64);
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(v66);
  v15 = 1;
  v44 = 1;
  v69[0] = 0;
  v43 = 0;
  v16 = (const unsigned __int16 *)v62;
  if ( v62[3] > (unsigned __int16 *)7 )
    v16 = v62[0];
  DCCDNUtil_GetRegistryDWORD(v42, v16, L"CspCount", &v43);
  for ( i = 0; ; ++i )
  {
    if ( i >= v43 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2EC4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x80070057LL,
        v41);
    v18 = StringCchPrintfW(v69, 0xFu, L"CSP%d", v15);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E73,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v18,
        v41);
    v19 = std::wstring::wstring((__int64)v61, (__int64)L"\\");
    v20 = std::operator+<unsigned short>(v60, v62, v19);
    std::operator+<unsigned short>(v58, v20, v69);
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(v61);
    v41 = 0;
    v21 = (const unsigned __int16 *)v58;
    if ( v59 > 7 )
      v21 = v58[0];
    RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v42, v21, L"ProviderType", &v41);
    v23 = v41;
    if ( RegistryDWORD < 0 )
      v23 = 1;
    if ( v23 != 1 )
    {
      if ( v23 == 2 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2EBB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)0x80004001LL,
          v41);
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2EBF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)0x8000FFFFLL,
        v41);
    }
    v45 = 0;
    v55 = (HKEY *)&v45;
    v56 = 0;
    v57 = 1;
    v24 = (const unsigned __int16 *)v58;
    if ( v59 > 7 )
      v24 = v58[0];
    v25 = DCCDNUtil_GetRegistryString(v42, v24, L"csp", (unsigned __int16 **)&v56);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v55);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E87,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v25,
        v41);
    v26 = a3[3] <= 7u ? a3 : (_QWORD *)*a3;
    if ( !(unsigned int)_o__wcsnicmp(v45, v26, 260) )
      break;
LABEL_41:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v45);
    std::wstring::_Tidy_deallocate(v58);
    v15 = ++v44;
  }
  v41 = 0;
  v27 = (const unsigned __int16 *)v58;
  if ( v59 > 7 )
    v27 = v58[0];
  v28 = DCCDNUtil_GetRegistryDWORD(v42, v27, L"UriCount", &v41);
  if ( v28 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E93,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v28,
      v41);
  v29 = 1;
  v61[0] = 0;
  for ( j = 0; ; ++j )
  {
    if ( j >= v41 )
      goto LABEL_41;
    v31 = StringCchPrintfW(v61, 0xFu, L"URI%d", v29);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E9E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v31,
        v41);
    v32 = std::wstring::wstring((__int64)v68, (__int64)v61);
    v33 = std::wstring::wstring((__int64)v67, (__int64)L"\\");
    v34 = std::operator+<unsigned short>(&v55, v58, v33);
    std::operator+<unsigned short>(v60, v34, v32);
    std::wstring::_Tidy_deallocate(&v55);
    std::wstring::_Tidy_deallocate(v67);
    std::wstring::_Tidy_deallocate(v68);
    v47 = 0;
    v55 = (HKEY *)&v47;
    v56 = 0;
    v57 = 1;
    v35 = (const unsigned __int16 *)v60;
    if ( v60[3] > (unsigned __int16 *)7 )
      v35 = v60[0];
    v36 = DCCDNUtil_GetRegistryString(v42, v35, L"uri", (unsigned __int16 **)&v56);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v55);
    if ( v36 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2EA7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v36,
        v41);
    v37 = a4[3] <= 7u ? a4 : (_QWORD *)*a4;
    if ( !(unsigned int)_o__wcsnicmp(v47, v37, 260) )
      break;
    ++v29;
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v47);
    std::wstring::_Tidy_deallocate(v60);
  }
  v38 = -1;
  v39 = -1;
  do
    ++v39;
  while ( v69[v39] );
  std::wstring::_Assign<unsigned short>(v48, v69, (char *)v39);
  do
    ++v38;
  while ( v61[v38] );
  std::wstring::_Assign<unsigned short>(v49, v61, (char *)v38);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v47);
  std::wstring::_Tidy_deallocate(v60);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v45);
  std::wstring::_Tidy_deallocate(v58);
  std::wstring::_Tidy_deallocate(v62);
  operator delete(Block);
  Block = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
  std::wstring::_Tidy_deallocate(v8);
  std::wstring::_Tidy_deallocate(a3);
  return std::wstring::_Tidy_deallocate(a4);
}

```

## disassembly

```asm
0x180099c54  push    rbp
0x180099c56  push    rbx
0x180099c57  push    rsi
0x180099c58  push    rdi
0x180099c59  push    r12
0x180099c5b  push    r13
0x180099c5d  push    r14
0x180099c5f  push    r15
0x180099c61  lea     rbp, [rsp-118h]
0x180099c69  sub     rsp, 218h
0x180099c70  mov     rax, cs:__security_cookie
0x180099c77  xor     rax, rsp
0x180099c7a  mov     [rbp+150h+var_48], rax
0x180099c81  mov     r15, r9
0x180099c84  mov     r14, r8
0x180099c87  mov     rsi, rdx
0x180099c8a  mov     [rsp+250h+var_1E0], rdx
0x180099c8f  mov     [rsp+250h+var_1D8], r8
0x180099c94  mov     [rbp+150h+var_1D0], r9
0x180099c98  mov     rax, [rbp+150h+arg_20]
0x180099c9f  mov     [rsp+250h+var_200], rax
0x180099ca4  mov     rdx, [rbp+150h+arg_28]
0x180099cab  mov     [rsp+250h+var_1F8], rdx
0x180099cb0  xor     r12d, r12d
0x180099cb3  test    rcx, rcx
0x180099cb6  jz      loc_18009A2BF
0x180099cbc  test    rax, rax
0x180099cbf  jz      loc_18009A2BF
0x180099cc5  test    rdx, rdx
0x180099cc8  jz      loc_18009A2BF
0x180099cce  mov     [rsp+250h+var_228], r12
0x180099cd3  mov     [rsp+250h+Block], r12
0x180099cd8  lea     rax, [rsp+250h+Block]
0x180099cdd  mov     [rsp+250h+var_1F0], rax
0x180099ce2  lea     edx, [r12+1]
0x180099ce7  mov     [rsp+250h+var_1E8], dl
0x180099ceb  lea     rax, [rsp+250h+var_228]
0x180099cf0  mov     [rbp+150h+var_1C8], rax
0x180099cf4  mov     [rbp+150h+var_1C0], r12
0x180099cf8  mov     [rbp+150h+var_1B8], dl
0x180099cfb  cmp     qword ptr [rsi+18h], 7
0x180099d00  jbe     short loc_180099D07
0x180099d02  mov     rdx, [rsi]
0x180099d05  jmp     short loc_180099D0A
0x180099d07  mov     rdx, rsi; unsigned __int16 *
0x180099d0a  xor     r9d, r9d; int
0x180099d0d  lea     r8, [rbp+150h+var_1C0]; HKEY *
0x180099d11  call    ?DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z; DeclaredConfigurationStore_GetEnrollmentIdSidStateDocIdKey(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)
0x180099d16  mov     ebx, eax
0x180099d18  lea     rcx, [rbp+150h+var_1C8]
0x180099d1c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180099d21  test    ebx, ebx
0x180099d23  jns     short loc_180099D41
0x180099d25  mov     rcx, [rbp+158h]; this
0x180099d2c  mov     r9d, ebx; char *
0x180099d2f  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180099d36  mov     edx, 2E54h; void *
0x180099d3b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180099d41  lea     r9, [rsp+250h+Block]; unsigned __int16 **
0x180099d46  lea     r8, aMostrecentvers; "MostRecentVersion"
0x180099d4d  xor     edx, edx; unsigned __int16 *
0x180099d4f  mov     rcx, [rsp+250h+var_228]; HKEY
0x180099d54  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180099d59  test    eax, eax
0x180099d5b  jns     short loc_180099D79
0x180099d5d  mov     rcx, [rbp+158h]; this
0x180099d64  mov     r9d, eax; char *
0x180099d67  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180099d6e  mov     edx, 2E61h; void *
0x180099d73  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180099d79  lea     rdx, aCooked; "cooked"
0x180099d80  lea     rcx, [rbp+150h+var_C8]
0x180099d87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099d8c  mov     rdi, rax
0x180099d8f  lea     rdx, StringValue; "\\"
0x180099d96  lea     rcx, [rbp+150h+var_E8]
0x180099d9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099d9f  mov     rbx, rax
0x180099da2  mov     rdx, [rsp+250h+Block]
0x180099da7  lea     rcx, [rbp+150h+var_108]
0x180099dab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099db0  nop
0x180099db1  mov     r8, rbx
0x180099db4  mov     rdx, rax
0x180099db7  lea     rcx, [rbp+150h+var_128]
0x180099dbb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180099dc0  nop
0x180099dc1  mov     r8, rdi
0x180099dc4  mov     rdx, rax
0x180099dc7  lea     rcx, [rbp+150h+var_148]
0x180099dcb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180099dd0  nop
0x180099dd1  lea     rcx, [rbp+150h+var_128]
0x180099dd5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099dda  nop
0x180099ddb  lea     rcx, [rbp+150h+var_108]
0x180099ddf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099de4  nop
0x180099de5  lea     rcx, [rbp+150h+var_E8]
0x180099de9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099dee  nop
0x180099def  lea     rcx, [rbp+150h+var_C8]
0x180099df6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099dfb  mov     edi, 1
0x180099e00  mov     ebx, edi
0x180099e02  mov     [rsp+250h+var_21C], ebx
0x180099e06  mov     [rbp+150h+var_68], r12w
0x180099e0e  mov     [rsp+250h+var_220], r12d
0x180099e13  lea     rdx, [rbp+150h+var_148]
0x180099e17  cmp     [rbp+150h+var_130], 7
0x180099e1c  cmova   rdx, [rbp+150h+var_148]; unsigned __int16 *
0x180099e21  lea     r9, [rsp+250h+var_220]; unsigned int *
0x180099e26  lea     r8, aCspcount_0; "CspCount"
0x180099e2d  mov     rcx, [rsp+250h+var_228]; HKEY
0x180099e32  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099e37  mov     r13d, r12d
0x180099e3a  cmp     r13d, [rsp+250h+var_220]
0x180099e3f  jnb     loc_18009A2A0
0x180099e45  mov     r9d, ebx
0x180099e48  lea     r8, aCspD; "CSP%d"
0x180099e4f  mov     edx, 0Fh; unsigned __int64
0x180099e54  lea     rcx, [rbp+150h+var_68]; unsigned __int16 *
0x180099e5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099e60  test    eax, eax
0x180099e62  js      loc_18009A284
0x180099e68  lea     rdx, StringValue; "\\"
0x180099e6f  lea     rcx, [rbp+150h+var_168]
0x180099e73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099e78  nop
0x180099e79  mov     r8, rax
0x180099e7c  lea     rdx, [rbp+150h+var_148]
0x180099e80  lea     rcx, [rbp+150h+var_188]
0x180099e84  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180099e89  nop
0x180099e8a  lea     r8, [rbp+150h+var_68]
0x180099e91  mov     rdx, rax
0x180099e94  lea     rcx, [rbp+150h+var_1A8]
0x180099e98  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180099e9d  nop
0x180099e9e  lea     rcx, [rbp+150h+var_188]
0x180099ea2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099ea7  nop
0x180099ea8  lea     rcx, [rbp+150h+var_168]
0x180099eac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099eb1  mov     [rsp+250h+var_230], r12d; int
0x180099eb6  lea     rdx, [rbp+150h+var_1A8]
0x180099eba  cmp     [rbp+150h+var_190], 7
0x180099ebf  cmova   rdx, [rbp+150h+var_1A8]; unsigned __int16 *
0x180099ec4  lea     r9, [rsp+250h+var_230]; unsigned int *
0x180099ec9  lea     r8, aProvidertype_0; "ProviderType"
0x180099ed0  mov     rcx, [rsp+250h+var_228]; HKEY
0x180099ed5  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099eda  mov     ecx, [rsp+250h+var_230]
0x180099ede  test    eax, eax
0x180099ee0  cmovs   ecx, edi
0x180099ee3  cmp     ecx, edi
0x180099ee5  jnz     loc_18009A24F
0x180099eeb  mov     [rsp+250h+var_218], r12
0x180099ef0  lea     rax, [rsp+250h+var_218]
0x180099ef5  mov     [rbp+150h+var_1C8], rax
0x180099ef9  mov     [rbp+150h+var_1C0], r12
0x180099efd  mov     [rbp+150h+var_1B8], dil
0x180099f01  lea     rdx, [rbp+150h+var_1A8]
0x180099f05  cmp     [rbp+150h+var_190], 7
0x180099f0a  cmova   rdx, [rbp+150h+var_1A8]; unsigned __int16 *
0x180099f0f  lea     r9, [rbp+150h+var_1C0]; unsigned __int16 **
0x180099f13  lea     r8, aCsp_0; "csp"
0x180099f1a  mov     rcx, [rsp+250h+var_228]; HKEY
0x180099f1f  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180099f24  mov     ebx, eax
0x180099f26  lea     rcx, [rbp+150h+var_1C8]
0x180099f2a  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180099f2f  test    ebx, ebx
0x180099f31  js      loc_18009A233
0x180099f37  cmp     qword ptr [r14+18h], 7
0x180099f3c  jbe     short loc_180099F43
0x180099f3e  mov     rdx, [r14]
0x180099f41  jmp     short loc_180099F46
0x180099f43  mov     rdx, r14
0x180099f46  mov     r8d, 104h
0x180099f4c  mov     rcx, [rsp+250h+var_218]
0x180099f51  call    cs:__imp__o__wcsnicmp
0x180099f57  test    eax, eax
0x180099f59  jnz     loc_18009A0E4
0x180099f5f  mov     [rsp+250h+var_230], r12d; int
0x180099f64  lea     rdx, [rbp+150h+var_1A8]
0x180099f68  cmp     [rbp+150h+var_190], 7
0x180099f6d  cmova   rdx, [rbp+150h+var_1A8]; unsigned __int16 *
0x180099f72  lea     r9, [rsp+250h+var_230]; unsigned int *
0x180099f77  lea     r8, aUricount; "UriCount"
0x180099f7e  mov     rcx, [rsp+250h+var_228]; HKEY
0x180099f83  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180099f88  test    eax, eax
0x180099f8a  js      loc_18009A217
0x180099f90  mov     r12d, edi
0x180099f93  xor     ebx, ebx
0x180099f95  mov     [rbp+150h+var_168], bx
0x180099f99  mov     edi, ebx
0x180099f9b  cmp     edi, [rsp+250h+var_230]
0x180099f9f  jnb     loc_18009A0C6
0x180099fa5  mov     r9d, r12d
0x180099fa8  lea     r8, aUriD_0; "URI%d"
0x180099faf  mov     edx, 0Fh; unsigned __int64
0x180099fb4  lea     rcx, [rbp+150h+var_168]; unsigned __int16 *
0x180099fb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180099fbd  test    eax, eax
0x180099fbf  js      loc_18009A1FB
0x180099fc5  lea     rdx, [rbp+150h+var_168]
0x180099fc9  lea     rcx, [rbp+150h+var_88]
0x180099fd0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099fd5  mov     rbx, rax
0x180099fd8  lea     rdx, StringValue; "\\"
0x180099fdf  lea     rcx, [rbp+150h+var_A8]
0x180099fe6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180099feb  nop
0x180099fec  mov     r8, rax
0x180099fef  lea     rdx, [rbp+150h+var_1A8]
0x180099ff3  lea     rcx, [rbp+150h+var_1C8]
0x180099ff7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180099ffc  nop
0x180099ffd  mov     r8, rbx
0x18009a000  mov     rdx, rax
0x18009a003  lea     rcx, [rbp+150h+var_188]
0x18009a007  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18009a00c  nop
0x18009a00d  lea     rcx, [rbp+150h+var_1C8]
0x18009a011  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a016  nop
0x18009a017  lea     rcx, [rbp+150h+var_A8]
0x18009a01e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a023  nop
0x18009a024  lea     rcx, [rbp+150h+var_88]
0x18009a02b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a030  mov     [rsp+250h+var_208], 0
0x18009a039  lea     rax, [rsp+250h+var_208]
0x18009a03e  mov     [rbp+150h+var_1C8], rax
0x18009a042  mov     [rbp+150h+var_1C0], 0
0x18009a04a  mov     [rbp+150h+var_1B8], 1
0x18009a04e  lea     rdx, [rbp+150h+var_188]
0x18009a052  cmp     [rbp+150h+var_170], 7
0x18009a057  cmova   rdx, [rbp+150h+var_188]; unsigned __int16 *
0x18009a05c  lea     r9, [rbp+150h+var_1C0]; unsigned __int16 **
0x18009a060  lea     r8, aUri_1; "uri"
0x18009a067  mov     rcx, [rsp+250h+var_228]; HKEY
0x18009a06c  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18009a071  mov     ebx, eax
0x18009a073  lea     rcx, [rbp+150h+var_1C8]
0x18009a077  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18009a07c  test    ebx, ebx
0x18009a07e  js      loc_18009A1DF
0x18009a084  cmp     qword ptr [r15+18h], 7
0x18009a089  jbe     short loc_18009A090
0x18009a08b  mov     rdx, [r15]
0x18009a08e  jmp     short loc_18009A093
0x18009a090  mov     rdx, r15
0x18009a093  mov     r8d, 104h
0x18009a099  mov     rcx, [rsp+250h+var_208]
0x18009a09e  call    cs:__imp__o__wcsnicmp
0x18009a0a4  test    eax, eax
0x18009a0a6  jz      short loc_18009A10A
0x18009a0a8  inc     r12d
0x18009a0ab  lea     rcx, [rsp+250h+var_208]
0x18009a0b0  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a0b5  nop
0x18009a0b6  lea     rcx, [rbp+150h+var_188]
0x18009a0ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a0bf  inc     edi
0x18009a0c1  jmp     loc_180099F9B
0x18009a0c6  lea     rcx, [rsp+250h+var_218]
0x18009a0cb  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a0d0  nop
0x18009a0d1  lea     rcx, [rbp+150h+var_1A8]
0x18009a0d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a0da  xor     r12d, r12d
0x18009a0dd  lea     edi, [r12+1]
0x18009a0e2  jmp     short loc_18009A0F8
0x18009a0e4  lea     rcx, [rsp+250h+var_218]
0x18009a0e9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18009a0ee  nop
0x18009a0ef  lea     rcx, [rbp+150h+var_1A8]
0x18009a0f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009a0f8  mov     ebx, [rsp+250h+var_21C]
0x18009a0fc  add     ebx, edi
0x18009a0fe  mov     [rsp+250h+var_21C], ebx
0x18009a102  add     r13d, edi
0x18009a105  jmp     loc_180099E3A
0x18009a10a  lea     rax, [rbp+150h+var_68]
0x18009a111  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009a115  mov     r8, rbx
0x18009a118  xor     edi, edi
0x18009a11a  inc     r8
0x18009a11d  cmp     [rax+r8*2], di
0x18009a122  jnz     short loc_18009A11A
0x18009a124  lea     rdx, [rbp+150h+var_68]
0x18009a12b  mov     rcx, [rsp+250h+var_200]
0x18009a130  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009a135  lea     rax, [rbp+150h+var_168]
0x18009a139  inc     rbx
0x18009a13c  cmp     [rax+rbx*2], di
0x18009a140  jnz     short loc_18009A139
  ... truncated ...
```
