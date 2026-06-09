# DeclaredConfigurationStore_ReadResultData

- ea: `0x180081a94`
- end: `0x180081fde`
- name: `DeclaredConfigurationStore_ReadResultData`
- size: `1354`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, LPCWSTR lpValueName, DWORD cbData)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180076c10`
- `0x180081ff0`
- `0x1800870b0`
- `0x18008bb70`

## callees

- `0x18000be80`
- `0x18000bf4c`
- `0x18000c8f4`
- `0x180018b30`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18005860c`
- `0x18005f8cc`
- `0x18005fa30`
- `0x18005fcf8`
- `0x1800600bc`
- `0x180081a94`
- `0x18008f874`
- `0x18008fc10`
- `0x1801007e8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081d1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081db2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081f39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081d1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081db2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081f39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081dee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081f7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081dee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081f7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081cd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081ef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081cd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081ef7`
- `OLEAUT32!__imp_SysAllocString` at `0x180081e04`
- `OLEAUT32!__imp_SysAllocString` at `0x180081e04`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_ReadResultData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        LPCWSTR lpValueName,
        __int64 cbData)
{
  __int64 v8; // rdi
  unsigned __int16 *v9; // rsi
  int v10; // eax
  int v11; // ebx
  int RegistryMultiString; // eax
  const OLECHAR *v13; // r12
  HKEY v14; // rcx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  BYTE *v19; // rax
  BYTE *v20; // r15
  LSTATUS v21; // eax
  HKEY v22; // rcx
  __int64 v23; // rdx
  DWORD v24; // r15d
  HKEY v25; // rcx
  LSTATUS v26; // eax
  LSTATUS Value; // eax
  DWORD Type; // [rsp+30h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-30h] BYREF
  HKEY v33; // [rsp+50h] [rbp-28h] BYREF
  void *p_hKey; // [rsp+58h] [rbp-20h] BYREF
  __int64 v35; // [rsp+60h] [rbp-18h] BYREF
  char v36; // [rsp+68h] [rbp-10h]

  hKey = 0;
  v8 = cbData;
  if ( cbData && lpValueName && a1 && a2 && a3 )
  {
    v35 = 0;
    v36 = 1;
    p_hKey = &hKey;
    if ( a4 )
      GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey(a1, a2, a3, a4, (__int64)&v35, 0);
    else
      GetResultsEnrollmentIdSidStateDocIdVersionKey(a1, a2, a3, (unsigned int)&v35, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    v9 = 0;
    v32 = 0;
    if ( a5 )
    {
      v35 = 0;
      v36 = 1;
      p_hKey = &v32;
      if ( a6 )
        v10 = DCStringCchPrintfAllStrings(&v35, L"%s\\%s", 2);
      else
        v10 = DCStringCchPrintfAllStrings(&v35, L"%s", 1);
      v11 = v10;
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_hKey);
      if ( v11 < 0 )
        goto LABEL_83;
      v9 = v32;
    }
    if ( *(_WORD *)v8 != 3 )
    {
      if ( *(_WORD *)v8 == 5 )
        goto LABEL_58;
      if ( *(_WORD *)v8 != 8 )
      {
        if ( *(_WORD *)v8 != 20 )
        {
          if ( *(_WORD *)v8 != 8200 )
          {
            if ( *(_WORD *)v8 == 8209 )
            {
              phkResult = 0;
              LODWORD(cbData) = 0;
              v11 = DCGetRegistryBinary(hKey, v9, lpValueName, &phkResult, &cbData);
              if ( v11 >= 0 )
              {
                v11 = DCInlineSetBinaryToVariant(phkResult, (unsigned int)cbData, v8);
                if ( v11 >= 0 )
                {
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&phkResult);
LABEL_85:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  return 0;
                }
              }
              std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&phkResult);
LABEL_83:
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return (unsigned int)v11;
            }
LABEL_64:
            v11 = -2147418113;
            goto LABEL_83;
          }
LABEL_61:
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            goto LABEL_64;
          v33 = 0;
          RegistryMultiString = DCCDNUtil_GetRegistryMultiString(
                                  hKey,
                                  v32,
                                  lpValueName,
                                  (unsigned __int16 **)&v33,
                                  (unsigned int *)&cbData);
          if ( RegistryMultiString >= 0 )
          {
            *(_WORD *)v8 = 8200;
            MultiStringToSafeArray((OLECHAR *)v33, v23, (struct tagSAFEARRAY **)(v8 + 8));
            v22 = v33;
            goto LABEL_57;
          }
LABEL_27:
          v11 = RegistryMultiString;
          goto LABEL_83;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        {
          cbData = 0;
          RegistryMultiString = DCGetRegistryQWORD(hKey, v32, lpValueName, &cbData);
          if ( RegistryMultiString < 0 )
            goto LABEL_27;
          *(_WORD *)v8 = 20;
          goto LABEL_29;
        }
LABEL_58:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_61;
        cbData = 0;
        RegistryMultiString = DCGetRegistryQWORD(hKey, v32, lpValueName, &cbData);
        if ( RegistryMultiString < 0 )
          goto LABEL_27;
        *(_WORD *)v8 = 5;
LABEL_29:
        *(_QWORD *)(v8 + 8) = cbData;
        goto LABEL_85;
      }
      v13 = 0;
      v14 = hKey;
      Type = 1;
      phkResult = 0;
      LODWORD(cbData) = 0;
      if ( hKey )
      {
        if ( v9 )
        {
          v15 = RegOpenKeyExW(hKey, v9, 0, 0x20119u, &phkResult);
          v11 = v15;
          if ( v15 )
          {
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
            goto LABEL_53;
          }
          v14 = phkResult;
        }
        else
        {
          phkResult = hKey;
        }
        v16 = RegQueryValueExW(v14, lpValueName, 0, &Type, 0, (LPDWORD)&cbData);
        v11 = v16;
        if ( v16 )
        {
          if ( v16 > 0 )
            v11 = (unsigned __int16)v16 | 0x80070000;
        }
        else if ( Type == 1 )
        {
          v17 = ((unsigned __int64)(unsigned int)cbData >> 1) + 1;
          v18 = 2 * v17;
          if ( !is_mul_ok(v17, 2u) )
            v18 = -1;
          v19 = (BYTE *)operator new[](v18, (const struct std::nothrow_t *)std::nothrow);
          v20 = v19;
          if ( v19 )
          {
            memset_0(v19, 0, v17);
            v21 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, v20, (LPDWORD)&cbData);
            v11 = v21;
            if ( v21 )
            {
              if ( v21 > 0 )
                v11 = (unsigned __int16)v21 | 0x80070000;
              operator delete(v20);
            }
            else
            {
              v11 = 0;
              v13 = (const OLECHAR *)v20;
            }
          }
          else
          {
            v11 = -2147024882;
          }
        }
        else
        {
          v11 = -2147418113;
        }
      }
      else
      {
        v11 = -2147024809;
      }
      if ( !v9 )
      {
LABEL_55:
        if ( v11 < 0 )
          goto LABEL_83;
        *(_WORD *)v8 = 8;
        *(_QWORD *)(v8 + 8) = SysAllocString(v13);
        v22 = (HKEY)v13;
LABEL_57:
        operator delete(v22);
        goto LABEL_85;
      }
LABEL_53:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_55;
    }
    v24 = 0;
    v25 = hKey;
    Type = 0;
    LODWORD(cbData) = 4;
    v33 = 0;
    LODWORD(phkResult) = 4;
    if ( hKey )
    {
      if ( v9 )
      {
        v26 = RegOpenKeyExW(hKey, v9, 0, 0x20119u, &v33);
        v11 = v26;
        if ( v26 )
        {
          if ( v26 > 0 )
            v11 = (unsigned __int16)v26 | 0x80070000;
LABEL_80:
          if ( v33 )
            RegCloseKey(v33);
LABEL_82:
          if ( v11 >= 0 )
          {
            *(_WORD *)v8 = 3;
            *(_DWORD *)(v8 + 8) = v24;
            goto LABEL_85;
          }
          goto LABEL_83;
        }
        v25 = v33;
      }
      else
      {
        v33 = hKey;
      }
      Value = RegQueryValueExW(v25, lpValueName, 0, (LPDWORD)&cbData, (LPBYTE)&Type, (LPDWORD)&phkResult);
      v11 = Value;
      if ( Value )
      {
        if ( Value > 0 )
          v11 = (unsigned __int16)Value | 0x80070000;
      }
      else if ( (_DWORD)cbData == 4 )
      {
        v11 = 0;
        v24 = Type;
      }
      else
      {
        v11 = -2147418113;
      }
    }
    else
    {
      v11 = -2147024809;
    }
    if ( !v9 )
      goto LABEL_82;
    goto LABEL_80;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180081a94  push    rbp
0x180081a96  push    rbx
0x180081a97  push    rsi
0x180081a98  push    rdi
0x180081a99  push    r12
0x180081a9b  push    r13
0x180081a9d  push    r14
0x180081a9f  push    r15
0x180081aa1  mov     rbp, rsp
0x180081aa4  sub     rsp, 78h
0x180081aa8  xor     r13d, r13d
0x180081aab  mov     [rbp+hKey], r13
0x180081aaf  mov     rdi, [rbp+cbData]
0x180081ab6  test    rdi, rdi
0x180081ab9  jz      loc_180081FBF
0x180081abf  mov     r14, [rbp+lpValueName]
0x180081ac3  test    r14, r14
0x180081ac6  jz      loc_180081FBF
0x180081acc  test    rcx, rcx
0x180081acf  jz      loc_180081FBF
0x180081ad5  test    rdx, rdx
0x180081ad8  jz      loc_180081FBF
0x180081ade  test    r8, r8
0x180081ae1  jz      loc_180081FBF
0x180081ae7  lea     rax, [rbp+hKey]
0x180081aeb  mov     [rbp+var_18], r13
0x180081aef  mov     [rbp+var_10], 1
0x180081af3  mov     [rbp+var_20], rax
0x180081af7  test    r9, r9
0x180081afa  jnz     short loc_180081B0C
0x180081afc  mov     dword ptr [rsp+78h+phkResult], r13d
0x180081b01  lea     r9, [rbp+var_18]
0x180081b05  call    GetResultsEnrollmentIdSidStateDocIdVersionKey
0x180081b0a  jmp     short loc_180081B1F
0x180081b0c  mov     dword ptr [rsp+78h+lpcbData], r13d
0x180081b11  lea     rax, [rbp+var_18]
0x180081b15  mov     [rsp+78h+phkResult], rax
0x180081b1a  call    GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey
0x180081b1f  lea     rcx, [rbp+var_20]
0x180081b23  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180081b28  mov     rsi, r13
0x180081b2b  mov     [rbp+var_30], r13
0x180081b2f  mov     r15d, 2
0x180081b35  mov     r9, [rbp+arg_20]
0x180081b39  test    r9, r9
0x180081b3c  jz      short loc_180081BA6
0x180081b3e  mov     rax, [rbp+arg_28]
0x180081b42  mov     [rbp+var_18], r13
0x180081b46  mov     [rbp+var_10], 1
0x180081b4a  test    rax, rax
0x180081b4d  jz      short loc_180081B71
0x180081b4f  lea     rcx, [rbp+var_30]
0x180081b53  mov     [rbp+var_20], rcx
0x180081b57  mov     [rsp+78h+phkResult], rax
0x180081b5c  mov     r8d, r15d
0x180081b5f  lea     rdx, aSS; "%s\\%s"
0x180081b66  lea     rcx, [rbp+var_18]
0x180081b6a  call    DCStringCchPrintfAllStrings
0x180081b6f  jmp     short loc_180081B8F
0x180081b71  lea     rax, [rbp+var_30]
0x180081b75  mov     [rbp+var_20], rax
0x180081b79  mov     r8d, 1
0x180081b7f  lea     rdx, aS; "%s"
0x180081b86  lea     rcx, [rbp+var_18]
0x180081b8a  call    DCStringCchPrintfAllStrings
0x180081b8f  mov     ebx, eax
0x180081b91  lea     rcx, [rbp+var_20]
0x180081b95  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180081b9a  test    ebx, ebx
0x180081b9c  js      loc_180081F88
0x180081ba2  mov     rsi, [rbp+var_30]
0x180081ba6  movzx   ecx, word ptr [rdi]
0x180081ba9  mov     eax, 3
0x180081bae  sub     ecx, eax
0x180081bb0  jz      loc_180081EB4
0x180081bb6  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x180081bbd  sub     ecx, r15d
0x180081bc0  jz      loc_180081E1B
0x180081bc6  sub     ecx, eax
0x180081bc8  jz      loc_180081C9A
0x180081bce  sub     ecx, 0Ch
0x180081bd1  jz      short loc_180081C4C
0x180081bd3  sub     ecx, 1FF4h
0x180081bd9  jz      loc_180081E57
0x180081bdf  cmp     ecx, 9
0x180081be2  jnz     loc_180081EAA
0x180081be8  mov     [rbp+var_40], r13
0x180081bec  mov     dword ptr [rbp+cbData], r13d
0x180081bf3  lea     rax, [rbp+cbData]
0x180081bfa  mov     [rsp+78h+phkResult], rax
0x180081bff  lea     r9, [rbp+var_40]
0x180081c03  mov     r8, r14
0x180081c06  mov     rdx, rsi
0x180081c09  mov     rcx, [rbp+hKey]
0x180081c0d  call    DCGetRegistryBinary
0x180081c12  mov     ebx, eax
0x180081c14  test    eax, eax
0x180081c16  jns     short loc_180081C26
0x180081c18  lea     rcx, [rbp+var_40]
0x180081c1c  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x180081c21  jmp     loc_180081F88
0x180081c26  mov     r8, rdi
0x180081c29  mov     edx, dword ptr [rbp+cbData]; Size
0x180081c2f  mov     rcx, [rbp+var_40]; Src
0x180081c33  call    DCInlineSetBinaryToVariant
0x180081c38  mov     ebx, eax
0x180081c3a  lea     rcx, [rbp+var_40]
0x180081c3e  test    eax, eax
0x180081c40  js      short loc_180081C1C
0x180081c42  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x180081c47  jmp     loc_180081FA8
0x180081c4c  mov     rcx, rbx
0x180081c4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180081c54  test    al, al
0x180081c56  jz      loc_180081E1B
0x180081c5c  mov     [rbp+cbData], r13
0x180081c63  lea     r9, [rbp+cbData]
0x180081c6a  mov     r8, r14
0x180081c6d  mov     rdx, [rbp+var_30]
0x180081c71  mov     rcx, [rbp+hKey]
0x180081c75  call    DCGetRegistryQWORD
0x180081c7a  test    eax, eax
0x180081c7c  jns     short loc_180081C85
0x180081c7e  mov     ebx, eax
0x180081c80  jmp     loc_180081F88
0x180081c85  mov     word ptr [rdi], 14h
0x180081c8a  mov     rax, [rbp+cbData]
0x180081c91  mov     [rdi+8], rax
0x180081c95  jmp     loc_180081FA8
0x180081c9a  mov     r12, r13
0x180081c9d  mov     rcx, [rbp+hKey]; hKey
0x180081ca1  mov     [rbp+Type], 1
0x180081ca8  mov     [rbp+var_40], r13
0x180081cac  mov     dword ptr [rbp+cbData], r13d
0x180081cb3  test    rcx, rcx
0x180081cb6  jz      loc_180081DDB
0x180081cbc  test    rsi, rsi
0x180081cbf  jz      short loc_180081CFC
0x180081cc1  lea     rax, [rbp+var_40]
0x180081cc5  mov     [rsp+78h+phkResult], rax; phkResult
0x180081cca  mov     r9d, 20119h; samDesired
0x180081cd0  xor     r8d, r8d; ulOptions
0x180081cd3  mov     rdx, rsi; lpSubKey
0x180081cd6  call    cs:__imp_RegOpenKeyExW
0x180081cdc  mov     ebx, eax
0x180081cde  test    eax, eax
0x180081ce0  jz      short loc_180081CF6
0x180081ce2  jle     loc_180081DE5
0x180081ce8  movzx   ebx, ax
0x180081ceb  or      ebx, 80070000h
0x180081cf1  jmp     loc_180081DE5
0x180081cf6  mov     rcx, [rbp+var_40]
0x180081cfa  jmp     short loc_180081D00
0x180081cfc  mov     [rbp+var_40], rcx
0x180081d00  lea     rax, [rbp+cbData]
0x180081d07  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180081d0c  mov     [rsp+78h+phkResult], r13; lpData
0x180081d11  lea     r9, [rbp+Type]; lpType
0x180081d15  xor     r8d, r8d; lpReserved
0x180081d18  mov     rdx, r14; lpValueName
0x180081d1b  call    cs:__imp_RegQueryValueExW
0x180081d21  mov     ebx, eax
0x180081d23  test    eax, eax
0x180081d25  jz      short loc_180081D3B
0x180081d27  jle     loc_180081DE0
0x180081d2d  movzx   ebx, ax
0x180081d30  or      ebx, 80070000h
0x180081d36  jmp     loc_180081DE0
0x180081d3b  cmp     [rbp+Type], 1
0x180081d3f  jz      short loc_180081D4B
0x180081d41  mov     ebx, 8000FFFFh
0x180081d46  jmp     loc_180081DE0
0x180081d4b  mov     ebx, dword ptr [rbp+cbData]
0x180081d51  shr     rbx, 1
0x180081d54  inc     rbx
0x180081d57  mov     rax, r15
0x180081d5a  mul     rbx
0x180081d5d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180081d64  cmovb   rax, rcx
0x180081d68  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081d6f  mov     rcx, rax; unsigned __int64
0x180081d72  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180081d77  mov     r15, rax
0x180081d7a  test    rax, rax
0x180081d7d  jnz     short loc_180081D86
0x180081d7f  mov     ebx, 8007000Eh
0x180081d84  jmp     short loc_180081DE0
0x180081d86  mov     r8, rbx; Size
0x180081d89  xor     edx, edx; Val
0x180081d8b  mov     rcx, r15; void *
0x180081d8e  call    memset_0
0x180081d93  lea     rax, [rbp+cbData]
0x180081d9a  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180081d9f  mov     [rsp+78h+phkResult], r15; lpData
0x180081da4  lea     r9, [rbp+Type]; lpType
0x180081da8  xor     r8d, r8d; lpReserved
0x180081dab  mov     rdx, r14; lpValueName
0x180081dae  mov     rcx, [rbp+var_40]; hKey
0x180081db2  call    cs:__imp_RegQueryValueExW
0x180081db8  mov     ebx, eax
0x180081dba  test    eax, eax
0x180081dbc  jz      short loc_180081DD3
0x180081dbe  jle     short loc_180081DC9
0x180081dc0  movzx   ebx, ax
0x180081dc3  or      ebx, 80070000h
0x180081dc9  mov     rcx, r15; Block
0x180081dcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180081dd1  jmp     short loc_180081DE0
0x180081dd3  mov     ebx, r13d
0x180081dd6  mov     r12, r15
0x180081dd9  jmp     short loc_180081DE0
0x180081ddb  mov     ebx, 80070057h
0x180081de0  test    rsi, rsi
0x180081de3  jz      short loc_180081DF4
0x180081de5  mov     rcx, [rbp+var_40]; hKey
0x180081de9  test    rcx, rcx
0x180081dec  jz      short loc_180081DF4
0x180081dee  call    cs:__imp_RegCloseKey
0x180081df4  test    ebx, ebx
0x180081df6  js      loc_180081F88
0x180081dfc  mov     word ptr [rdi], 8
0x180081e01  mov     rcx, r12; psz
0x180081e04  call    cs:__imp_SysAllocString
0x180081e0a  mov     [rdi+8], rax
0x180081e0e  mov     rcx, r12; Block
0x180081e11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180081e16  jmp     loc_180081FA8
0x180081e1b  mov     rcx, rbx
0x180081e1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180081e23  test    al, al
0x180081e25  jz      short loc_180081E57
0x180081e27  mov     [rbp+cbData], r13
0x180081e2e  lea     r9, [rbp+cbData]
0x180081e35  mov     r8, r14
0x180081e38  mov     rdx, [rbp+var_30]
0x180081e3c  mov     rcx, [rbp+hKey]
0x180081e40  call    DCGetRegistryQWORD
0x180081e45  test    eax, eax
0x180081e47  js      loc_180081C7E
0x180081e4d  mov     word ptr [rdi], 5
0x180081e52  jmp     loc_180081C8A
0x180081e57  mov     rcx, rbx
0x180081e5a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x180081e5f  test    al, al
0x180081e61  jz      short loc_180081EAA
0x180081e63  mov     [rbp+var_28], r13
0x180081e67  lea     rax, [rbp+cbData]
0x180081e6e  mov     [rsp+78h+phkResult], rax; unsigned int *
0x180081e73  lea     r9, [rbp+var_28]; unsigned __int16 **
0x180081e77  mov     r8, r14; unsigned __int16 *
0x180081e7a  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180081e7e  mov     rcx, [rbp+hKey]; HKEY
0x180081e82  call    ?DCCDNUtil_GetRegistryMultiString@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; DCCDNUtil_GetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x180081e87  test    eax, eax
0x180081e89  js      loc_180081C7E
0x180081e8f  mov     word ptr [rdi], 2008h
0x180081e94  lea     r8, [rdi+8]; struct tagSAFEARRAY **
0x180081e98  mov     rcx, [rbp+var_28]; strIn
0x180081e9c  call    ?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z; MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)
0x180081ea1  mov     rcx, [rbp+var_28]
0x180081ea5  jmp     loc_180081E11
0x180081eaa  mov     ebx, 8000FFFFh
0x180081eaf  jmp     loc_180081F88
0x180081eb4  mov     r15d, r13d
0x180081eb7  mov     rcx, [rbp+hKey]; hKey
0x180081ebb  mov     [rbp+Type], r13d
0x180081ebf  mov     r12d, 4
0x180081ec5  mov     dword ptr [rbp+cbData], r12d
0x180081ecc  mov     [rbp+var_28], r13
0x180081ed0  mov     dword ptr [rbp+var_40], r12d
0x180081ed4  test    rcx, rcx
0x180081ed7  jz      loc_180081F6B
0x180081edd  test    rsi, rsi
0x180081ee0  jz      short loc_180081F16
0x180081ee2  lea     rax, [rbp+var_28]
0x180081ee6  mov     [rsp+78h+phkResult], rax; phkResult
0x180081eeb  mov     r9d, 20119h; samDesired
0x180081ef1  xor     r8d, r8d; ulOptions
0x180081ef4  mov     rdx, rsi; lpSubKey
0x180081ef7  call    cs:__imp_RegOpenKeyExW
0x180081efd  mov     ebx, eax
0x180081eff  test    eax, eax
0x180081f01  jz      short loc_180081F10
0x180081f03  jle     short loc_180081F75
0x180081f05  movzx   ebx, ax
0x180081f08  or      ebx, 80070000h
0x180081f0e  jmp     short loc_180081F75
0x180081f10  mov     rcx, [rbp+var_28]
0x180081f14  jmp     short loc_180081F1A
0x180081f16  mov     [rbp+var_28], rcx
0x180081f1a  lea     rax, [rbp+var_40]
0x180081f1e  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180081f23  lea     rax, [rbp+Type]
0x180081f27  mov     [rsp+78h+phkResult], rax; lpData
0x180081f2c  lea     r9, [rbp+cbData]; lpType
0x180081f33  xor     r8d, r8d; lpReserved
0x180081f36  mov     rdx, r14; lpValueName
0x180081f39  call    cs:__imp_RegQueryValueExW
0x180081f3f  mov     ebx, eax
0x180081f41  test    eax, eax
  ... truncated ...
```
