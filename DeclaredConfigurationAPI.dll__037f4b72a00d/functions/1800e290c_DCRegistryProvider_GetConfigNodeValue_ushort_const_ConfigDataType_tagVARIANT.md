# DCRegistryProvider::GetConfigNodeValue(ushort const *,ConfigDataType,tagVARIANT *)

- ea: `0x1800e290c`
- end: `0x1800e3064`
- name: `?GetConfigNodeValue@DCRegistryProvider@@QEBAJPEBGW4ConfigDataType@@PEAUtagVARIANT@@@Z`
- size: `1880`
- prototype: `int __high(const unsigned __int16 *, enum ConfigDataType, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e72b0`
- `0x1800e8bb8`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x180019270`
- `0x1800192f8`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18004babc`
- `0x18005860c`
- `0x18005feac`
- `0x1800ce488`
- `0x1800e290c`
- `0x1800e306c`
- `0x180100534`
- `0x1801006c8`
- `0x1801007e8`
- `0x1801009b0`
- `0x180100ad8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2a7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2b7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2a7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e2b7d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2e1e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e2e1e`
- `OLEAUT32!__imp_VariantInit` at `0x1800e2bad`
- `OLEAUT32!__imp_VariantInit` at `0x1800e2bad`

## string_xrefs

- `0x1800e2957`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e29e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2aaa`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2d06`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2df9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2e3b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2f67`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DCRegistryProvider::GetConfigNodeValue(__int64 a1, __int64 a2, int a3, struct tagVARIANT *a4)
{
  __int64 v6; // rdx
  int v8; // edx
  int v9; // ecx
  int v10; // eax
  signed int RegistryBinary; // edi
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  __int64 v14; // rdx
  unsigned __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rdx
  LSTATUS v19; // eax
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  const unsigned __int16 *v24; // r8
  int v25; // eax
  const unsigned __int16 *v26; // r8
  int RegistryDWORD; // eax
  const unsigned __int16 *v28; // r8
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  const unsigned __int16 *v36; // r8
  OLECHAR **p_psz; // rcx
  BSTR v38; // rax
  OLECHAR **p_strIn; // rcx
  const unsigned __int16 *v40; // r8
  int RegistryQWORD; // eax
  const unsigned __int16 *v42; // r8
  __int64 v43; // rdx
  unsigned __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // eax
  int dwOptions; // [rsp+20h] [rbp-118h]
  int dwOptionsa; // [rsp+20h] [rbp-118h]
  int dwOptionsb; // [rsp+20h] [rbp-118h]
  int dwOptionsc; // [rsp+20h] [rbp-118h]
  int dwOptionsd; // [rsp+20h] [rbp-118h]
  int dwOptionse; // [rsp+20h] [rbp-118h]
  HKEY v53; // [rsp+50h] [rbp-E8h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-E0h] BYREF
  OLECHAR *strIn; // [rsp+60h] [rbp-D8h] BYREF
  unsigned __int8 *Src; // [rsp+68h] [rbp-D0h] BYREF
  void *p_Src; // [rsp+70h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-C0h] BYREF
  char v59; // [rsp+80h] [rbp-B8h]
  unsigned __int16 *v60[3]; // [rsp+90h] [rbp-A8h] BYREF
  unsigned __int64 v61; // [rsp+A8h] [rbp-90h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-88h] BYREF
  unsigned __int64 v63; // [rsp+C8h] [rbp-70h]
  _BYTE v64[32]; // [rsp+D0h] [rbp-68h] BYREF
  _BYTE v65[32]; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  if ( !a2 )
  {
    v6 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x80070057LL,
      dwOptionsa);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v6 = 251;
    goto LABEL_3;
  }
  if ( a3 == 8 )
  {
    v6 = 255;
    goto LABEL_3;
  }
  std::wstring::wstring((__int64)v64);
  std::wstring::wstring((__int64)lpSubKey);
  std::wstring::wstring((__int64)v60);
  v10 = DCRegistryProvider::ParseFullRegPathUri(v9, v8, (unsigned int)v64, (unsigned int)lpSubKey, (__int64)v60);
  RegistryBinary = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)(unsigned int)v10,
      dwOptionsb);
LABEL_82:
    std::wstring::_Tidy_deallocate(v60);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v64);
    return (unsigned int)RegistryBinary;
  }
  v53 = 0;
  if ( (unsigned int)std::wstring::compare(v64, L"device") )
  {
    try
    {
      v16 = std::operator+<unsigned short>(v65, v64, L"\\");
      v17 = std::operator+<unsigned short>(&p_Src, v16, lpSubKey);
      std::wstring::operator=(lpSubKey, v17);
      std::wstring::_Tidy_deallocate(&p_Src);
      std::wstring::_Tidy_deallocate(v65);
      p_Src = &v53;
      phkResult = 0;
      v59 = 1;
      v18 = (const WCHAR *)lpSubKey;
      if ( v63 > 7 )
        v18 = lpSubKey[0];
      v19 = RegCreateKeyExW(HKEY_USERS, v18, 0, 0, 0, 0x20119u, 0, &phkResult, 0);
      RegistryBinary = v19;
      if ( v19 > 0 )
        RegistryBinary = (unsigned __int16)v19 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_Src);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)0x8007000ELL,
        dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      std::wstring::_Tidy_deallocate(v60);
      std::wstring::_Tidy_deallocate(lpSubKey);
      std::wstring::_Tidy_deallocate(v64);
      return 2147942414LL;
    }
    if ( RegistryBinary < 0 )
    {
      v14 = 296;
      goto LABEL_17;
    }
  }
  else
  {
    p_Src = &v53;
    phkResult = 0;
    v59 = 1;
    v12 = (const WCHAR *)lpSubKey;
    if ( v63 > 7 )
      v12 = lpSubKey[0];
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 0, 0x20119u, 0, &phkResult, 0);
    RegistryBinary = v13;
    if ( v13 > 0 )
      RegistryBinary = (unsigned __int16)v13 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_Src);
    if ( RegistryBinary < 0 )
    {
      v14 = 275;
LABEL_17:
      v15 = (unsigned int)RegistryBinary;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)v15,
        dwOptionsc);
LABEL_81:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      goto LABEL_82;
    }
  }
  VariantInit(a4);
  LODWORD(psz) = 0;
  if ( a3 <= 6 )
  {
    if ( a3 == 6 )
    {
      Src = 0;
      p_Src = &Src;
      phkResult = 0;
      v59 = 1;
      v28 = (const unsigned __int16 *)v60;
      if ( v61 > 7 )
        v28 = v60[0];
      RegistryBinary = DCCDNUtil_GetRegistryBinary(v53, 0, v28, (unsigned __int8 **)&phkResult, (unsigned int *)&psz);
      wil::details::out_param_t<std::unique_ptr<unsigned char>>::~out_param_t<std::unique_ptr<unsigned char>>(&p_Src);
      if ( RegistryBinary >= 0 )
      {
        v31 = DCSetBinaryToVariant(Src, (unsigned int)psz, a4);
        RegistryBinary = v31;
        if ( v31 >= 0 )
        {
          std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Src);
          goto LABEL_85;
        }
        v29 = (unsigned int)v31;
        v30 = 363;
      }
      else
      {
        v29 = (unsigned int)RegistryBinary;
        v30 = 362;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)v29,
        dwOptionsd);
      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Src);
      goto LABEL_81;
    }
    if ( !a3 )
    {
      LODWORD(psz) = 0;
      v26 = (const unsigned __int16 *)v60;
      if ( v61 > 7 )
        v26 = v60[0];
      RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v53, 0, v26, (unsigned int *)&psz);
      RegistryBinary = RegistryDWORD;
      if ( RegistryDWORD < 0 )
      {
        v15 = (unsigned int)RegistryDWORD;
        v14 = 307;
        goto LABEL_18;
      }
      a4->vt = 3;
LABEL_45:
      a4->lVal = (int)psz;
      goto LABEL_85;
    }
    v20 = a3 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 || (v23 = v22 - 1) == 0 )
        {
          RegistryBinary = -2147467263;
          v14 = 378;
          goto LABEL_17;
        }
        if ( v23 == 1 )
        {
          LODWORD(psz) = 0;
          v24 = (const unsigned __int16 *)v60;
          if ( v61 > 7 )
            v24 = v60[0];
          v25 = DCCDNUtil_GetRegistryDWORD(v53, 0, v24, (unsigned int *)&psz);
          RegistryBinary = v25;
          if ( v25 < 0 )
          {
            v15 = (unsigned int)v25;
            v14 = 316;
            goto LABEL_18;
          }
          a4->vt = 11;
          goto LABEL_45;
        }
LABEL_59:
        RegistryBinary = -2147418113;
        v14 = 382;
        goto LABEL_17;
      }
      goto LABEL_67;
    }
LABEL_60:
    psz = 0;
    p_Src = &psz;
    phkResult = 0;
    v59 = 1;
    v36 = (const unsigned __int16 *)v60;
    if ( v61 > 7 )
      v36 = v60[0];
    RegistryBinary = DCCDNUtil_GetRegistryString(v53, 0, v36, (unsigned __int16 **)&phkResult);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_Src);
    if ( RegistryBinary < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)(unsigned int)RegistryBinary,
        dwOptionsc);
      p_psz = &psz;
LABEL_80:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(p_psz);
      goto LABEL_81;
    }
    a4->vt = 8;
    v38 = SysAllocString(psz);
    a4->llVal = (LONGLONG)v38;
    if ( !v38 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)0x8007000ELL,
        dwOptionsc);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&psz);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
      RegistryBinary = -2147024882;
      goto LABEL_82;
    }
    p_strIn = &psz;
LABEL_84:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(p_strIn);
    goto LABEL_85;
  }
  v32 = a3 - 7;
  if ( !v32 )
  {
    strIn = 0;
    p_Src = &strIn;
    phkResult = 0;
    v59 = 1;
    v42 = (const unsigned __int16 *)v60;
    if ( v61 > 7 )
      v42 = v60[0];
    RegistryBinary = DCCDNUtil_GetRegistryMultiString(
                       v53,
                       0,
                       v42,
                       (unsigned __int16 **)&phkResult,
                       (unsigned int *)&psz);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_Src);
    if ( RegistryBinary >= 0 )
    {
      a4->vt = 8200;
      v46 = MultiStringToSafeArray(strIn, v43, &a4->parray);
      RegistryBinary = v46;
      if ( v46 >= 0 )
      {
        p_strIn = &strIn;
        goto LABEL_84;
      }
      v44 = (unsigned int)v46;
      v45 = 355;
    }
    else
    {
      v44 = (unsigned int)RegistryBinary;
      v45 = 353;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)v44,
      dwOptionse);
    p_psz = &strIn;
    goto LABEL_80;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    RegistryBinary = -2147418113;
    v14 = 372;
    goto LABEL_17;
  }
  v34 = v33 - 1;
  if ( v34 )
  {
    v35 = v34 - 2;
    if ( !v35 )
    {
LABEL_67:
      strIn = 0;
      v40 = (const unsigned __int16 *)v60;
      if ( v61 > 7 )
        v40 = v60[0];
      RegistryQWORD = DCCDNUtil_GetRegistryQWORD(v53, 0, v40, (unsigned __int64 *)&strIn);
      RegistryBinary = RegistryQWORD;
      if ( RegistryQWORD < 0 )
      {
        v15 = (unsigned int)RegistryQWORD;
        v14 = 326;
        goto LABEL_18;
      }
      a4->vt = 20;
      a4->llVal = (LONGLONG)strIn;
      goto LABEL_85;
    }
    if ( (unsigned int)(v35 - 1) >= 2 )
      goto LABEL_59;
    goto LABEL_60;
  }
LABEL_85:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v53);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v64);
  return 0;
}

```

## disassembly

```asm
0x1800e290c  mov     [rsp+arg_0], rbx
0x1800e2911  mov     [rsp+arg_10], rsi
0x1800e2916  push    rdi
0x1800e2917  push    r14
0x1800e2919  push    r15
0x1800e291b  sub     rsp, 120h
0x1800e2922  mov     rax, cs:__security_cookie
0x1800e2929  xor     rax, rsp
0x1800e292c  mov     [rsp+138h+var_28], rax
0x1800e2934  mov     rsi, r9
0x1800e2937  mov     ebx, r8d
0x1800e293a  xor     r14d, r14d
0x1800e293d  test    rdx, rdx
0x1800e2940  jnz     short loc_1800E296A
0x1800e2942  mov     edx, 0FAh; void *
0x1800e2947  mov     ebx, 80070057h
0x1800e294c  mov     rcx, [rsp+138h]; this
0x1800e2954  mov     r9d, ebx; char *
0x1800e2957  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e295e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2963  mov     eax, ebx
0x1800e2965  jmp     loc_1800E303B
0x1800e296a  test    rsi, rsi
0x1800e296d  jnz     short loc_1800E2976
0x1800e296f  mov     edx, 0FBh
0x1800e2974  jmp     short loc_1800E2947
0x1800e2976  mov     r15d, 8
0x1800e297c  cmp     ebx, r15d
0x1800e297f  jnz     short loc_1800E2988
0x1800e2981  mov     edx, 0FFh
0x1800e2986  jmp     short loc_1800E2947
0x1800e2988  lea     rcx, [rsp+138h+var_68]
0x1800e2990  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e2995  nop
0x1800e2996  lea     rcx, [rsp+138h+lpSubKey]
0x1800e299e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e29a3  nop
0x1800e29a4  lea     rcx, [rsp+138h+var_A8]
0x1800e29ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e29b1  nop
0x1800e29b2  lea     rax, [rsp+138h+var_A8]
0x1800e29ba  mov     qword ptr [rsp+138h+dwOptions], rax; int
0x1800e29bf  lea     r9, [rsp+138h+lpSubKey]
0x1800e29c7  lea     r8, [rsp+138h+var_68]
0x1800e29cf  call    ?ParseFullRegPathUri@DCRegistryProvider@@AEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; DCRegistryProvider::ParseFullRegPathUri(ushort const *,std::wstring &,std::wstring &,std::wstring &)
0x1800e29d4  mov     edi, eax
0x1800e29d6  test    eax, eax
0x1800e29d8  jns     short loc_1800E29FB
0x1800e29da  mov     rcx, [rsp+138h]; this
0x1800e29e2  mov     r9d, eax; char *
0x1800e29e5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e29ec  mov     edx, 105h; void *
0x1800e29f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e29f6  jmp     loc_1800E2F92
0x1800e29fb  mov     [rsp+138h+var_E8], r14
0x1800e2a00  lea     rdx, aDevice_4; "device"
0x1800e2a07  lea     rcx, [rsp+138h+var_68]
0x1800e2a0f  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800e2a14  test    eax, eax
0x1800e2a16  jnz     loc_1800E2AC3
0x1800e2a1c  lea     rax, [rsp+138h+var_E8]
0x1800e2a21  mov     [rsp+138h+var_C8], rax
0x1800e2a26  mov     [rsp+138h+var_C0], r14
0x1800e2a2b  mov     [rsp+138h+var_B8], 1
0x1800e2a33  lea     rdx, [rsp+138h+lpSubKey]
0x1800e2a3b  cmp     [rsp+138h+var_70], 7
0x1800e2a44  cmova   rdx, [rsp+138h+lpSubKey]; lpSubKey
0x1800e2a4d  mov     [rsp+138h+lpdwDisposition], r14; lpdwDisposition
0x1800e2a52  lea     rax, [rsp+138h+var_C0]
0x1800e2a57  mov     [rsp+138h+phkResult], rax; phkResult
0x1800e2a5c  mov     [rsp+138h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800e2a61  mov     [rsp+138h+samDesired], 20119h; samDesired
0x1800e2a69  mov     [rsp+138h+dwOptions], r14d; int
0x1800e2a6e  xor     r9d, r9d; lpClass
0x1800e2a71  xor     r8d, r8d; Reserved
0x1800e2a74  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e2a7b  call    cs:__imp_RegCreateKeyExW
0x1800e2a81  mov     edi, eax
0x1800e2a83  test    eax, eax
0x1800e2a85  jle     short loc_1800E2A90
0x1800e2a87  movzx   edi, ax
0x1800e2a8a  or      edi, 80070000h
0x1800e2a90  lea     rcx, [rsp+138h+var_C8]
0x1800e2a95  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e2a9a  test    edi, edi
0x1800e2a9c  jns     loc_1800E2BAA
0x1800e2aa2  mov     edx, 113h; void *
0x1800e2aa7  mov     r9d, edi; char *
0x1800e2aaa  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2ab1  mov     rcx, [rsp+138h]; this
0x1800e2ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2abe  jmp     loc_1800E2F87
0x1800e2ac3  lea     r8, StringValue; "\\"
0x1800e2aca  lea     rdx, [rsp+138h+var_68]
0x1800e2ad2  lea     rcx, [rsp+138h+var_48]
0x1800e2ada  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e2adf  nop
0x1800e2ae0  lea     r8, [rsp+138h+lpSubKey]
0x1800e2ae8  mov     rdx, rax
0x1800e2aeb  lea     rcx, [rsp+138h+var_C8]
0x1800e2af0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e2af5  mov     rdx, rax
0x1800e2af8  lea     rcx, [rsp+138h+lpSubKey]
0x1800e2b00  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e2b05  lea     rcx, [rsp+138h+var_C8]
0x1800e2b0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2b0f  nop
0x1800e2b10  lea     rcx, [rsp+138h+var_48]
0x1800e2b18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2b1d  nop
0x1800e2b1e  lea     rax, [rsp+138h+var_E8]
0x1800e2b23  mov     [rsp+138h+var_C8], rax
0x1800e2b28  mov     [rsp+138h+var_C0], r14
0x1800e2b2d  mov     [rsp+138h+var_B8], 1
0x1800e2b35  lea     rdx, [rsp+138h+lpSubKey]
0x1800e2b3d  cmp     [rsp+138h+var_70], 7
0x1800e2b46  cmova   rdx, [rsp+138h+lpSubKey]; lpSubKey
0x1800e2b4f  mov     [rsp+138h+lpdwDisposition], r14; lpdwDisposition
0x1800e2b54  lea     rax, [rsp+138h+var_C0]
0x1800e2b59  mov     [rsp+138h+phkResult], rax; phkResult
0x1800e2b5e  mov     [rsp+138h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800e2b63  mov     [rsp+138h+samDesired], 20119h; samDesired
0x1800e2b6b  mov     [rsp+138h+dwOptions], r14d; dwOptions
0x1800e2b70  xor     r9d, r9d; lpClass
0x1800e2b73  xor     r8d, r8d; Reserved
0x1800e2b76  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800e2b7d  call    cs:__imp_RegCreateKeyExW
0x1800e2b83  mov     edi, eax
0x1800e2b85  test    eax, eax
0x1800e2b87  jle     short loc_1800E2B92
0x1800e2b89  movzx   edi, ax
0x1800e2b8c  or      edi, 80070000h
0x1800e2b92  lea     rcx, [rsp+138h+var_C8]
0x1800e2b97  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e2b9c  test    edi, edi
0x1800e2b9e  jns     short loc_1800E2BAA
0x1800e2ba0  mov     edx, 128h
0x1800e2ba5  jmp     loc_1800E2AA7
0x1800e2baa  mov     rcx, rsi; pvarg
0x1800e2bad  call    cs:__imp_VariantInit
0x1800e2bb3  mov     dword ptr [rsp+138h+psz], r14d
0x1800e2bb8  cmp     ebx, 6
0x1800e2bbb  jg      loc_1800E2D5A
0x1800e2bc1  jz      loc_1800E2C9D
0x1800e2bc7  test    ebx, ebx
0x1800e2bc9  jz      short loc_1800E2C49
0x1800e2bcb  sub     ebx, 1
0x1800e2bce  jz      loc_1800E2D97
0x1800e2bd4  sub     ebx, 1
0x1800e2bd7  jz      loc_1800E2E76
0x1800e2bdd  sub     ebx, 1
0x1800e2be0  jz      short loc_1800E2C3A
0x1800e2be2  sub     ebx, 1
0x1800e2be5  jz      short loc_1800E2C3A
0x1800e2be7  cmp     ebx, 1
0x1800e2bea  jnz     loc_1800E2D88
0x1800e2bf0  mov     dword ptr [rsp+138h+psz], r14d
0x1800e2bf5  lea     r8, [rsp+138h+var_A8]
0x1800e2bfd  cmp     [rsp+138h+var_90], 7
0x1800e2c06  cmova   r8, [rsp+138h+var_A8]; unsigned __int16 *
0x1800e2c0f  lea     r9, [rsp+138h+psz]; unsigned int *
0x1800e2c14  xor     edx, edx; unsigned __int16 *
0x1800e2c16  mov     rcx, [rsp+138h+var_E8]; HKEY
0x1800e2c1b  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800e2c20  mov     edi, eax
0x1800e2c22  test    eax, eax
0x1800e2c24  jns     short loc_1800E2C33
0x1800e2c26  mov     r9d, eax
0x1800e2c29  mov     edx, 13Ch
0x1800e2c2e  jmp     loc_1800E2AAA
0x1800e2c33  mov     word ptr [rsi], 0Bh
0x1800e2c38  jmp     short loc_1800E2C91
0x1800e2c3a  mov     edi, 80004001h
0x1800e2c3f  mov     edx, 17Ah
0x1800e2c44  jmp     loc_1800E2AA7
0x1800e2c49  mov     dword ptr [rsp+138h+psz], r14d
0x1800e2c4e  lea     r8, [rsp+138h+var_A8]
0x1800e2c56  cmp     [rsp+138h+var_90], 7
0x1800e2c5f  cmova   r8, [rsp+138h+var_A8]; unsigned __int16 *
0x1800e2c68  lea     r9, [rsp+138h+psz]; unsigned int *
0x1800e2c6d  xor     edx, edx; unsigned __int16 *
0x1800e2c6f  mov     rcx, [rsp+138h+var_E8]; HKEY
0x1800e2c74  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800e2c79  mov     edi, eax
0x1800e2c7b  test    eax, eax
0x1800e2c7d  jns     short loc_1800E2C8C
0x1800e2c7f  mov     r9d, eax
0x1800e2c82  mov     edx, 133h
0x1800e2c87  jmp     loc_1800E2AAA
0x1800e2c8c  mov     word ptr [rsi], 3
0x1800e2c91  mov     eax, dword ptr [rsp+138h+psz]
0x1800e2c95  mov     [rsi+8], eax
0x1800e2c98  jmp     loc_1800E2FCA
0x1800e2c9d  mov     [rsp+138h+Src], r14
0x1800e2ca2  lea     rax, [rsp+138h+Src]
0x1800e2ca7  mov     [rsp+138h+var_C8], rax
0x1800e2cac  mov     [rsp+138h+var_C0], r14
0x1800e2cb1  mov     [rsp+138h+var_B8], 1
0x1800e2cb9  lea     r8, [rsp+138h+var_A8]
0x1800e2cc1  cmp     [rsp+138h+var_90], 7
0x1800e2cca  cmova   r8, [rsp+138h+var_A8]; unsigned __int16 *
0x1800e2cd3  lea     rax, [rsp+138h+psz]
0x1800e2cd8  mov     qword ptr [rsp+138h+dwOptions], rax; int
0x1800e2cdd  lea     r9, [rsp+138h+var_C0]; unsigned __int8 **
0x1800e2ce2  xor     edx, edx; unsigned __int16 *
0x1800e2ce4  mov     rcx, [rsp+138h+var_E8]; HKEY
0x1800e2ce9  call    ?DCCDNUtil_GetRegistryBinary@@YAJPEAUHKEY__@@PEBG1PEAPEAEPEAK@Z; DCCDNUtil_GetRegistryBinary(HKEY__ *,ushort const *,ushort const *,uchar * *,ulong *)
0x1800e2cee  mov     edi, eax
0x1800e2cf0  lea     rcx, [rsp+138h+var_C8]
0x1800e2cf5  call    ??1?$out_param_t@V?$unique_ptr@EU?$default_delete@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar>>::~out_param_t<std::unique_ptr<uchar>>(void)
0x1800e2cfa  test    edi, edi
0x1800e2cfc  jns     short loc_1800E2D2A
0x1800e2cfe  mov     r9d, edi; char *
0x1800e2d01  mov     edx, 16Ah; void *
0x1800e2d06  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2d0d  mov     rcx, [rsp+138h]; this
0x1800e2d15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2d1a  nop
0x1800e2d1b  lea     rcx, [rsp+138h+Src]
0x1800e2d20  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800e2d25  jmp     loc_1800E2F87
0x1800e2d2a  mov     r8, rsi; struct tagVARIANT *
0x1800e2d2d  mov     edx, dword ptr [rsp+138h+psz]; Size
0x1800e2d31  mov     rcx, [rsp+138h+Src]; Src
0x1800e2d36  call    ?DCSetBinaryToVariant@@YAJPEAEKPEAUtagVARIANT@@@Z; DCSetBinaryToVariant(uchar *,ulong,tagVARIANT *)
0x1800e2d3b  mov     edi, eax
0x1800e2d3d  test    eax, eax
0x1800e2d3f  jns     short loc_1800E2D4B
0x1800e2d41  mov     r9d, eax
0x1800e2d44  mov     edx, 16Bh
0x1800e2d49  jmp     short loc_1800E2D06
0x1800e2d4b  lea     rcx, [rsp+138h+Src]
0x1800e2d50  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800e2d55  jmp     loc_1800E2FCA
0x1800e2d5a  sub     ebx, 7
0x1800e2d5d  jz      loc_1800E2EDB
0x1800e2d63  sub     ebx, 1
0x1800e2d66  jz      loc_1800E2ECC
0x1800e2d6c  sub     ebx, 1
0x1800e2d6f  jz      loc_1800E2FCA
0x1800e2d75  sub     ebx, 2
0x1800e2d78  jz      loc_1800E2E76
0x1800e2d7e  sub     ebx, 1
0x1800e2d81  jz      short loc_1800E2D97
0x1800e2d83  cmp     ebx, 1
0x1800e2d86  jz      short loc_1800E2D97
0x1800e2d88  mov     edi, 8000FFFFh
0x1800e2d8d  mov     edx, 17Eh
0x1800e2d92  jmp     loc_1800E2AA7
0x1800e2d97  mov     [rsp+138h+psz], r14
0x1800e2d9c  lea     rax, [rsp+138h+psz]
0x1800e2da1  mov     [rsp+138h+var_C8], rax
0x1800e2da6  mov     [rsp+138h+var_C0], r14
0x1800e2dab  mov     [rsp+138h+var_B8], 1
0x1800e2db3  lea     r8, [rsp+138h+var_A8]
0x1800e2dbb  cmp     [rsp+138h+var_90], 7
0x1800e2dc4  cmova   r8, [rsp+138h+var_A8]; unsigned __int16 *
0x1800e2dcd  lea     r9, [rsp+138h+var_C0]; unsigned __int16 **
0x1800e2dd2  xor     edx, edx; unsigned __int16 *
0x1800e2dd4  mov     rcx, [rsp+138h+var_E8]; HKEY
0x1800e2dd9  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800e2dde  mov     edi, eax
0x1800e2de0  lea     rcx, [rsp+138h+var_C8]
0x1800e2de5  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800e2dea  test    edi, edi
0x1800e2dec  jns     short loc_1800E2E15
0x1800e2dee  mov     rcx, [rsp+138h]; this
0x1800e2df6  mov     r9d, edi; char *
0x1800e2df9  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2e00  mov     edx, 151h; void *
0x1800e2e05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2e0a  nop
0x1800e2e0b  lea     rcx, [rsp+138h+psz]
0x1800e2e10  jmp     loc_1800E2F81
0x1800e2e15  mov     [rsi], r15w
0x1800e2e19  mov     rcx, [rsp+138h+psz]; psz
0x1800e2e1e  call    cs:__imp_SysAllocString
0x1800e2e24  mov     [rsi+8], rax
0x1800e2e28  test    rax, rax
0x1800e2e2b  jnz     short loc_1800E2E6C
0x1800e2e2d  mov     rcx, [rsp+138h]; this
0x1800e2e35  mov     r9d, 8007000Eh; char *
0x1800e2e3b  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2e42  mov     edx, 154h; void *
0x1800e2e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2e4c  nop
0x1800e2e4d  lea     rcx, [rsp+138h+psz]
0x1800e2e52  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800e2e57  nop
0x1800e2e58  lea     rcx, [rsp+138h+var_E8]
0x1800e2e5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e2e62  mov     edi, 8007000Eh
0x1800e2e67  jmp     loc_1800E2F92
0x1800e2e6c  lea     rcx, [rsp+138h+psz]
0x1800e2e71  jmp     loc_1800E2FC4
0x1800e2e76  mov     [rsp+138h+strIn], r14
0x1800e2e7b  lea     r8, [rsp+138h+var_A8]
0x1800e2e83  cmp     [rsp+138h+var_90], 7
0x1800e2e8c  cmova   r8, [rsp+138h+var_A8]; unsigned __int16 *
0x1800e2e95  lea     r9, [rsp+138h+strIn]; unsigned __int64 *
  ... truncated ...
```
