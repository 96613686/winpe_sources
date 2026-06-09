# DeleteTreeEnrollmentSid

- ea: `0x18008c26c`
- end: `0x18008c4a1`
- name: `DeleteTreeEnrollmentSid`
- size: `565`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180069de0`

## callees

- `0x18001ce5c`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x18008c26c`
- `0x18008e86c`
- `0x18008faa4`
- `0x1800a0174`
- `0x180100418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c309`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c38a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c43d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c309`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c38a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c43d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008c3e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008c3e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c2ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c2ed`

## string_xrefs

- `0x18008c2df`: `SOFTWARE\Microsoft\DeclaredConfiguration\OrchestrationInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeleteTreeEnrollmentSid(LPCWSTR *a1)
{
  unsigned int v2; // ebx
  int v3; // edi
  LSTATUS v4; // ebx
  int i; // esi
  int ResultsEnrollmentIdKey; // eax
  LSTATUS v7; // eax
  signed int v8; // eax
  bool v9; // cc
  const WCHAR *v10; // rcx
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-10h] BYREF
  char v15; // [rsp+78h] [rbp-8h]
  DWORD cSubKeys; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C8h] [rbp+48h] BYREF
  HKEY v18; // [rsp+D0h] [rbp+50h] BYREF
  HKEY v19; // [rsp+D8h] [rbp+58h] BYREF

  v18 = 0;
  v19 = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    goto LABEL_35;
  }
  v3 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl'::`2'::impl) )
  {
    p_hKey = &hKey;
    phkResult = 0;
    v15 = 1;
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\DeclaredConfiguration\\OrchestrationInformation",
           0,
           0xF003Fu,
           &phkResult);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( !v4 )
      RegDeleteTreeW(hKey, *a1);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
LABEL_34:
      v2 = v3;
      goto LABEL_35;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v18,
      0);
    if ( i )
    {
      if ( i != 1 )
        goto LABEL_13;
      p_hKey = &v18;
      phkResult = 0;
      v15 = 1;
      ResultsEnrollmentIdKey = GetResultsEnrollmentIdKey(a1, &phkResult);
    }
    else
    {
      p_hKey = &v18;
      phkResult = 0;
      v15 = 1;
      ResultsEnrollmentIdKey = GetEnrollmentIdKey(a1, &phkResult);
    }
    v3 = ResultsEnrollmentIdKey;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
LABEL_13:
    if ( v3 < 0 )
      goto LABEL_34;
    v7 = RegDeleteTreeW(v18, a1[1]);
    v2 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 != -2147024894 )
        goto LABEL_35;
      v3 = 0;
    }
    v8 = RegQueryInfoKeyW(v18, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v9 = v8 <= 0;
    if ( v8 )
    {
LABEL_29:
      if ( !v9 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v2 = 0;
      if ( v8 != -2147024894 )
        v2 = v8;
      goto LABEL_35;
    }
    if ( !cSubKeys )
      break;
LABEL_25:
    ;
  }
  phkResult = 0;
  v15 = 1;
  p_hKey = &v19;
  v10 = qword_18018A530;
  if ( i )
    v10 = qword_18018A410;
  v3 = DCCDNUtil_GetHKey(v10, &phkResult, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v3 >= 0 )
  {
    v8 = RegDeleteTreeW(v19, *a1);
    v9 = v8 <= 0;
    if ( v8 )
      goto LABEL_29;
    goto LABEL_25;
  }
  v2 = 0;
  if ( v3 != -2147024894 )
    v2 = v3;
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  return v2;
}

```

## disassembly

```asm
0x18008c26c  push    rbp
0x18008c26e  push    rbx
0x18008c26f  push    rsi
0x18008c270  push    rdi
0x18008c271  push    r12
0x18008c273  push    r14
0x18008c275  push    r15
0x18008c277  mov     rbp, rsp
0x18008c27a  sub     rsp, 80h
0x18008c281  mov     r14, rcx
0x18008c284  xor     r15d, r15d
0x18008c287  mov     [rbp+arg_10], r15
0x18008c28b  mov     [rbp+arg_18], r15
0x18008c28f  mov     [rbp+hKey], r15
0x18008c293  mov     [rbp+cSubKeys], r15d
0x18008c297  mov     [rbp+cbMaxSubKeyLen], r15d
0x18008c29b  test    rcx, rcx
0x18008c29e  jnz     short loc_18008C2AA
0x18008c2a0  mov     ebx, 80070057h
0x18008c2a5  jmp     loc_18008C470
0x18008c2aa  mov     edi, r15d
0x18008c2ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::GetImpl(void)'::`2'::impl
0x18008c2b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_EnterpriseDesktopAppManagementCsp_Support>::__private_IsEnabled(void)
0x18008c2b9  test    al, al
0x18008c2bb  jz      short loc_18008C30F
0x18008c2bd  lea     rax, [rbp+hKey]
0x18008c2c1  mov     [rbp+var_18], rax
0x18008c2c5  mov     [rbp+var_10], r15
0x18008c2c9  mov     [rbp+var_8], 1
0x18008c2cd  lea     rax, [rbp+var_10]
0x18008c2d1  mov     [rsp+80h+phkResult], rax; phkResult
0x18008c2d6  mov     r9d, 0F003Fh; samDesired
0x18008c2dc  xor     r8d, r8d; ulOptions
0x18008c2df  lea     rdx, aSoftwareMicros_21; "SOFTWARE\\Microsoft\\DeclaredConfigurat"...
0x18008c2e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008c2ed  call    cs:__imp_RegOpenKeyExW
0x18008c2f3  mov     ebx, eax
0x18008c2f5  lea     rcx, [rbp+var_18]
0x18008c2f9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008c2fe  test    ebx, ebx
0x18008c300  jnz     short loc_18008C30F
0x18008c302  mov     rdx, [r14]; lpSubKey
0x18008c305  mov     rcx, [rbp+hKey]; hKey
0x18008c309  call    cs:__imp_RegDeleteTreeW
0x18008c30f  mov     esi, r15d
0x18008c312  mov     r12d, 80070002h
0x18008c318  cmp     esi, 2
0x18008c31b  jge     loc_18008C46E
0x18008c321  xor     edx, edx
0x18008c323  lea     rcx, [rbp+arg_10]
0x18008c327  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008c32c  test    esi, esi
0x18008c32e  jz      short loc_18008C353
0x18008c330  cmp     esi, 1
0x18008c333  jnz     short loc_18008C37A
0x18008c335  lea     rax, [rbp+arg_10]
0x18008c339  mov     [rbp+var_18], rax
0x18008c33d  mov     [rbp+var_10], r15
0x18008c341  mov     [rbp+var_8], sil
0x18008c345  lea     rdx, [rbp+var_10]
0x18008c349  mov     rcx, r14
0x18008c34c  call    GetResultsEnrollmentIdKey
0x18008c351  jmp     short loc_18008C36F
0x18008c353  lea     rax, [rbp+arg_10]
0x18008c357  mov     [rbp+var_18], rax
0x18008c35b  mov     [rbp+var_10], r15
0x18008c35f  mov     [rbp+var_8], 1
0x18008c363  lea     rdx, [rbp+var_10]
0x18008c367  mov     rcx, r14
0x18008c36a  call    GetEnrollmentIdKey
0x18008c36f  mov     edi, eax
0x18008c371  lea     rcx, [rbp+var_18]
0x18008c375  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008c37a  test    edi, edi
0x18008c37c  js      loc_18008C46E
0x18008c382  mov     rdx, [r14+8]; lpSubKey
0x18008c386  mov     rcx, [rbp+arg_10]; hKey
0x18008c38a  call    cs:__imp_RegDeleteTreeW
0x18008c390  mov     ebx, eax
0x18008c392  test    eax, eax
0x18008c394  jz      short loc_18008C3AD
0x18008c396  jle     short loc_18008C3A1
0x18008c398  movzx   ebx, ax
0x18008c39b  or      ebx, 80070000h
0x18008c3a1  cmp     ebx, r12d
0x18008c3a4  jnz     loc_18008C470
0x18008c3aa  mov     edi, r15d
0x18008c3ad  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18008c3b2  mov     [rsp+80h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18008c3b7  mov     [rsp+80h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18008c3bc  mov     [rsp+80h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18008c3c1  mov     [rsp+80h+lpcValues], r15; lpcValues
0x18008c3c6  mov     [rsp+80h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18008c3cb  lea     rax, [rbp+cbMaxSubKeyLen]
0x18008c3cf  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18008c3d4  lea     rax, [rbp+cSubKeys]
0x18008c3d8  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18008c3dd  xor     r9d, r9d; lpReserved
0x18008c3e0  xor     r8d, r8d; lpcchClass
0x18008c3e3  xor     edx, edx; lpClass
0x18008c3e5  mov     rcx, [rbp+arg_10]; hKey
0x18008c3e9  call    cs:__imp_RegQueryInfoKeyW
0x18008c3ef  test    eax, eax
0x18008c3f1  jnz     short loc_18008C459
0x18008c3f3  cmp     [rbp+cSubKeys], r15d
0x18008c3f7  jnz     short loc_18008C447
0x18008c3f9  lea     rax, [rbp+arg_18]
0x18008c3fd  mov     [rbp+var_10], r15
0x18008c401  mov     [rbp+var_8], 1
0x18008c405  xor     r8d, r8d; int
0x18008c408  lea     rdx, [rbp+var_10]; HKEY *
0x18008c40c  mov     [rbp+var_18], rax
0x18008c410  test    esi, esi
0x18008c412  mov     rcx, cs:qword_18018A530
0x18008c419  jz      short loc_18008C422
0x18008c41b  mov     rcx, cs:qword_18018A410; lpSubKey
0x18008c422  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18008c427  mov     edi, eax
0x18008c429  lea     rcx, [rbp+var_18]
0x18008c42d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008c432  test    edi, edi
0x18008c434  js      short loc_18008C44E
0x18008c436  mov     rdx, [r14]; lpSubKey
0x18008c439  mov     rcx, [rbp+arg_18]; hKey
0x18008c43d  call    cs:__imp_RegDeleteTreeW
0x18008c443  test    eax, eax
0x18008c445  jnz     short loc_18008C459
0x18008c447  inc     esi
0x18008c449  jmp     loc_18008C318
0x18008c44e  mov     ebx, r15d
0x18008c451  cmp     edi, r12d
0x18008c454  cmovnz  ebx, edi
0x18008c457  jmp     short loc_18008C470
0x18008c459  jle     short loc_18008C463
0x18008c45b  movzx   eax, ax
0x18008c45e  or      eax, 80070000h
0x18008c463  mov     ebx, r15d
0x18008c466  cmp     eax, r12d
0x18008c469  cmovnz  ebx, eax
0x18008c46c  jmp     short loc_18008C470
0x18008c46e  mov     ebx, edi
0x18008c470  lea     rcx, [rbp+hKey]
0x18008c474  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c479  nop
0x18008c47a  lea     rcx, [rbp+arg_18]
0x18008c47e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c483  nop
0x18008c484  lea     rcx, [rbp+arg_10]
0x18008c488  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c48d  mov     eax, ebx
0x18008c48f  add     rsp, 80h
0x18008c496  pop     r15
0x18008c498  pop     r14
0x18008c49a  pop     r12
0x18008c49c  pop     rdi
0x18008c49d  pop     rsi
0x18008c49e  pop     rbx
0x18008c49f  pop     rbp
0x18008c4a0  retn
```
