# DeclaredConfigurationStore_ReadResultData_2

- ea: `0x1800ca3c4`
- end: `0x1800ca8ee`
- name: `DeclaredConfigurationStore_ReadResultData_2`
- size: `1322`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, LPCWSTR lpValueName, DWORD Type)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1800ca8f4`

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
- `0x1800ca3c4`
- `0x1800cba68`
- `0x1801007e8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca626`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca6bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca849`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca626`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca6bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ca849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca88e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca6fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ca88e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca5e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca5e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ca807`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ca711`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ca711`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_ReadResultData_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        LPCWSTR lpValueName,
        unsigned __int16 *Type)
{
  unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // rsi
  int v11; // eax
  int v12; // ebx
  int RegistryMultiString; // eax
  const OLECHAR *v14; // r12
  HKEY v15; // rcx
  LSTATUS v16; // eax
  LSTATUS Value; // eax
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rax
  BYTE *v20; // rax
  BYTE *v21; // r15
  LSTATUS v22; // eax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rdx
  int v25; // r15d
  HKEY v26; // rcx
  LSTATUS v27; // eax
  LSTATUS v28; // eax
  HKEY phkResult; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-38h] BYREF
  HKEY v33; // [rsp+48h] [rbp-30h] BYREF
  void *p_hKey; // [rsp+50h] [rbp-28h] BYREF
  __int64 v35; // [rsp+58h] [rbp-20h] BYREF
  char v36; // [rsp+60h] [rbp-18h]
  __int64 cbData; // [rsp+D8h] [rbp+60h] BYREF

  cbData = a4;
  hKey = 0;
  v8 = Type;
  if ( Type )
  {
    v9 = lpValueName;
    if ( lpValueName )
    {
      if ( a1 && a2 && a3 )
      {
        p_hKey = &hKey;
        v35 = 0;
        v36 = 1;
        GetResultsEnrollmentIdSidStateDocIdVersionKey_2(a1, a2, a3, &v35);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        v10 = 0;
        v32 = 0;
        if ( a5 )
        {
          v35 = 0;
          v36 = 1;
          p_hKey = &v32;
          if ( a6 )
            v11 = DCStringCchPrintfAllStrings(&v35, L"%s\\%s", 2);
          else
            v11 = DCStringCchPrintfAllStrings(&v35, L"%s", 1);
          v12 = v11;
          wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_hKey);
          if ( v12 < 0 )
            goto LABEL_80;
          v10 = v32;
        }
        if ( *v8 != 3 )
        {
          if ( *v8 == 5 )
            goto LABEL_55;
          if ( *v8 != 8 )
          {
            if ( *v8 != 20 )
            {
              if ( *v8 != 8200 )
              {
                if ( *v8 == 8209 )
                {
                  Type = 0;
                  LODWORD(cbData) = 0;
                  v12 = DCGetRegistryBinary(hKey, v10, v9, &Type, &cbData);
                  if ( v12 >= 0 )
                  {
                    v12 = DCInlineSetBinaryToVariant(Type, (unsigned int)cbData, (__int64)v8);
                    if ( v12 >= 0 )
                    {
                      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Type);
LABEL_82:
                      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
                      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                      return 0;
                    }
                  }
                  std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Type);
LABEL_80:
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  return (unsigned int)v12;
                }
LABEL_61:
                v12 = -2147418113;
                goto LABEL_80;
              }
LABEL_58:
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
                goto LABEL_61;
              Type = 0;
              RegistryMultiString = DCCDNUtil_GetRegistryMultiString(hKey, v32, v9, &Type, (unsigned int *)&cbData);
              if ( RegistryMultiString >= 0 )
              {
                *v8 = 8200;
                MultiStringToSafeArray(Type, v24, (struct tagSAFEARRAY **)v8 + 1);
                v23 = Type;
                goto LABEL_54;
              }
LABEL_24:
              v12 = RegistryMultiString;
              goto LABEL_80;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
            {
              cbData = 0;
              RegistryMultiString = DCGetRegistryQWORD(hKey, v32, v9, &cbData);
              if ( RegistryMultiString < 0 )
                goto LABEL_24;
              *v8 = 20;
              goto LABEL_26;
            }
LABEL_55:
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
              goto LABEL_58;
            cbData = 0;
            RegistryMultiString = DCGetRegistryQWORD(hKey, v32, v9, &cbData);
            if ( RegistryMultiString < 0 )
              goto LABEL_24;
            *v8 = 5;
LABEL_26:
            *((_QWORD *)v8 + 1) = cbData;
            goto LABEL_82;
          }
          v14 = 0;
          v15 = hKey;
          LODWORD(Type) = 1;
          phkResult = 0;
          LODWORD(cbData) = 0;
          if ( hKey )
          {
            if ( v10 )
            {
              v16 = RegOpenKeyExW(hKey, v10, 0, 0x20119u, &phkResult);
              v12 = v16;
              if ( v16 )
              {
                if ( v16 > 0 )
                  v12 = (unsigned __int16)v16 | 0x80070000;
                goto LABEL_50;
              }
              v15 = phkResult;
            }
            else
            {
              phkResult = hKey;
            }
            Value = RegQueryValueExW(v15, v9, 0, (LPDWORD)&Type, 0, (LPDWORD)&cbData);
            v12 = Value;
            if ( Value )
            {
              if ( Value > 0 )
                v12 = (unsigned __int16)Value | 0x80070000;
            }
            else if ( (_DWORD)Type == 1 )
            {
              v18 = ((unsigned __int64)(unsigned int)cbData >> 1) + 1;
              v19 = 2 * v18;
              if ( !is_mul_ok(v18, 2u) )
                v19 = -1;
              v20 = (BYTE *)operator new[](v19, (const struct std::nothrow_t *)std::nothrow);
              v21 = v20;
              if ( v20 )
              {
                memset_0(v20, 0, v18);
                v22 = RegQueryValueExW(phkResult, v9, 0, (LPDWORD)&Type, v21, (LPDWORD)&cbData);
                v12 = v22;
                if ( v22 )
                {
                  if ( v22 > 0 )
                    v12 = (unsigned __int16)v22 | 0x80070000;
                  operator delete(v21);
                }
                else
                {
                  v12 = 0;
                  v14 = (const OLECHAR *)v21;
                }
              }
              else
              {
                v12 = -2147024882;
              }
            }
            else
            {
              v12 = -2147418113;
            }
          }
          else
          {
            v12 = -2147024809;
          }
          if ( !v10 )
          {
LABEL_52:
            if ( v12 < 0 )
              goto LABEL_80;
            *v8 = 8;
            *((_QWORD *)v8 + 1) = SysAllocString(v14);
            v23 = (unsigned __int16 *)v14;
LABEL_54:
            operator delete(v23);
            goto LABEL_82;
          }
LABEL_50:
          if ( phkResult )
            RegCloseKey(phkResult);
          goto LABEL_52;
        }
        v25 = 0;
        v26 = hKey;
        LODWORD(Type) = 0;
        LODWORD(cbData) = 4;
        v33 = 0;
        LODWORD(phkResult) = 4;
        if ( hKey )
        {
          if ( v10 )
          {
            v27 = RegOpenKeyExW(hKey, v10, 0, 0x20119u, &v33);
            v12 = v27;
            if ( v27 )
            {
              if ( v27 > 0 )
                v12 = (unsigned __int16)v27 | 0x80070000;
LABEL_77:
              if ( v33 )
                RegCloseKey(v33);
LABEL_79:
              if ( v12 >= 0 )
              {
                *v8 = 3;
                *((_DWORD *)v8 + 2) = v25;
                goto LABEL_82;
              }
              goto LABEL_80;
            }
            v26 = v33;
          }
          else
          {
            v33 = hKey;
          }
          v28 = RegQueryValueExW(v26, v9, 0, (LPDWORD)&cbData, (LPBYTE)&Type, (LPDWORD)&phkResult);
          v12 = v28;
          if ( v28 )
          {
            if ( v28 > 0 )
              v12 = (unsigned __int16)v28 | 0x80070000;
          }
          else if ( (_DWORD)cbData == 4 )
          {
            v12 = 0;
            v25 = (int)Type;
          }
          else
          {
            v12 = -2147418113;
          }
        }
        else
        {
          v12 = -2147024809;
        }
        if ( !v10 )
          goto LABEL_79;
        goto LABEL_77;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800ca3c4  mov     [rsp-40h+cbData], r9
0x1800ca3c9  push    rbp
0x1800ca3ca  push    rbx
0x1800ca3cb  push    rsi
0x1800ca3cc  push    rdi
0x1800ca3cd  push    r12
0x1800ca3cf  push    r13
0x1800ca3d1  push    r14
0x1800ca3d3  push    r15
0x1800ca3d5  mov     rbp, rsp
0x1800ca3d8  sub     rsp, 78h
0x1800ca3dc  xor     r13d, r13d
0x1800ca3df  mov     [rbp+hKey], r13
0x1800ca3e3  mov     rdi, [rbp+Type]
0x1800ca3ea  test    rdi, rdi
0x1800ca3ed  jz      loc_1800CA8CF
0x1800ca3f3  mov     r14, [rbp+lpValueName]
0x1800ca3f7  test    r14, r14
0x1800ca3fa  jz      loc_1800CA8CF
0x1800ca400  test    rcx, rcx
0x1800ca403  jz      loc_1800CA8CF
0x1800ca409  test    rdx, rdx
0x1800ca40c  jz      loc_1800CA8CF
0x1800ca412  test    r8, r8
0x1800ca415  jz      loc_1800CA8CF
0x1800ca41b  lea     rax, [rbp+hKey]
0x1800ca41f  mov     [rbp+var_28], rax
0x1800ca423  mov     [rbp+var_20], r13
0x1800ca427  lea     r15d, [r13+1]
0x1800ca42b  mov     [rbp+var_18], r15b
0x1800ca42f  lea     r9, [rbp+var_20]
0x1800ca433  call    GetResultsEnrollmentIdSidStateDocIdVersionKey_2
0x1800ca438  lea     rcx, [rbp+var_28]
0x1800ca43c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800ca441  mov     esi, r13d
0x1800ca444  mov     [rbp+var_38], r13
0x1800ca448  mov     r9, [rbp+arg_20]
0x1800ca44c  test    r9, r9
0x1800ca44f  jz      short loc_1800CA4B7
0x1800ca451  mov     rax, [rbp+arg_28]
0x1800ca455  mov     [rbp+var_20], r13
0x1800ca459  mov     [rbp+var_18], r15b
0x1800ca45d  test    rax, rax
0x1800ca460  jz      short loc_1800CA485
0x1800ca462  lea     rcx, [rbp+var_38]
0x1800ca466  mov     [rbp+var_28], rcx
0x1800ca46a  mov     [rsp+78h+phkResult], rax
0x1800ca46f  lea     r8d, [r13+2]
0x1800ca473  lea     rdx, aSS; "%s\\%s"
0x1800ca47a  lea     rcx, [rbp+var_20]
0x1800ca47e  call    DCStringCchPrintfAllStrings
0x1800ca483  jmp     short loc_1800CA4A0
0x1800ca485  lea     rax, [rbp+var_38]
0x1800ca489  mov     [rbp+var_28], rax
0x1800ca48d  mov     r8d, r15d
0x1800ca490  lea     rdx, aS; "%s"
0x1800ca497  lea     rcx, [rbp+var_20]
0x1800ca49b  call    DCStringCchPrintfAllStrings
0x1800ca4a0  mov     ebx, eax
0x1800ca4a2  lea     rcx, [rbp+var_28]
0x1800ca4a6  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800ca4ab  test    ebx, ebx
0x1800ca4ad  js      loc_1800CA898
0x1800ca4b3  mov     rsi, [rbp+var_38]
0x1800ca4b7  movzx   ecx, word ptr [rdi]
0x1800ca4ba  mov     eax, 3
0x1800ca4bf  sub     ecx, eax
0x1800ca4c1  jz      loc_1800CA7C4
0x1800ca4c7  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800ca4ce  sub     ecx, 2
0x1800ca4d1  jz      loc_1800CA728
0x1800ca4d7  sub     ecx, eax
0x1800ca4d9  jz      loc_1800CA5A8
0x1800ca4df  sub     ecx, 0Ch
0x1800ca4e2  jz      short loc_1800CA563
0x1800ca4e4  sub     ecx, 1FF4h
0x1800ca4ea  jz      loc_1800CA75E
0x1800ca4f0  cmp     ecx, 9
0x1800ca4f3  jnz     loc_1800CA7BA
0x1800ca4f9  mov     [rbp+Type], r13
0x1800ca500  mov     dword ptr [rbp+cbData], r13d
0x1800ca504  lea     rax, [rbp+cbData]
0x1800ca508  mov     [rsp+78h+phkResult], rax
0x1800ca50d  lea     r9, [rbp+Type]
0x1800ca514  mov     r8, r14
0x1800ca517  mov     rdx, rsi
0x1800ca51a  mov     rcx, [rbp+hKey]
0x1800ca51e  call    DCGetRegistryBinary
0x1800ca523  mov     ebx, eax
0x1800ca525  test    eax, eax
0x1800ca527  jns     short loc_1800CA53A
0x1800ca529  lea     rcx, [rbp+Type]
0x1800ca530  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800ca535  jmp     loc_1800CA898
0x1800ca53a  mov     r8, rdi
0x1800ca53d  mov     edx, dword ptr [rbp+cbData]; Size
0x1800ca540  mov     rcx, [rbp+Type]; Src
0x1800ca547  call    DCInlineSetBinaryToVariant
0x1800ca54c  mov     ebx, eax
0x1800ca54e  lea     rcx, [rbp+Type]
0x1800ca555  test    eax, eax
0x1800ca557  js      short loc_1800CA530
0x1800ca559  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800ca55e  jmp     loc_1800CA8B8
0x1800ca563  mov     rcx, rbx
0x1800ca566  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800ca56b  test    al, al
0x1800ca56d  jz      loc_1800CA728
0x1800ca573  mov     [rbp+cbData], r13
0x1800ca577  lea     r9, [rbp+cbData]
0x1800ca57b  mov     r8, r14
0x1800ca57e  mov     rdx, [rbp+var_38]
0x1800ca582  mov     rcx, [rbp+hKey]
0x1800ca586  call    DCGetRegistryQWORD
0x1800ca58b  test    eax, eax
0x1800ca58d  jns     short loc_1800CA596
0x1800ca58f  mov     ebx, eax
0x1800ca591  jmp     loc_1800CA898
0x1800ca596  mov     word ptr [rdi], 14h
0x1800ca59b  mov     rax, [rbp+cbData]
0x1800ca59f  mov     [rdi+8], rax
0x1800ca5a3  jmp     loc_1800CA8B8
0x1800ca5a8  mov     r12, r13
0x1800ca5ab  mov     rcx, [rbp+hKey]; hKey
0x1800ca5af  mov     dword ptr [rbp+Type], r15d
0x1800ca5b6  mov     [rbp+var_48], r13
0x1800ca5ba  mov     dword ptr [rbp+cbData], r13d
0x1800ca5be  test    rcx, rcx
0x1800ca5c1  jz      loc_1800CA6E8
0x1800ca5c7  test    rsi, rsi
0x1800ca5ca  jz      short loc_1800CA607
0x1800ca5cc  lea     rax, [rbp+var_48]
0x1800ca5d0  mov     [rsp+78h+phkResult], rax; phkResult
0x1800ca5d5  mov     r9d, 20119h; samDesired
0x1800ca5db  xor     r8d, r8d; ulOptions
0x1800ca5de  mov     rdx, rsi; lpSubKey
0x1800ca5e1  call    cs:__imp_RegOpenKeyExW
0x1800ca5e7  mov     ebx, eax
0x1800ca5e9  test    eax, eax
0x1800ca5eb  jz      short loc_1800CA601
0x1800ca5ed  jle     loc_1800CA6F2
0x1800ca5f3  movzx   ebx, ax
0x1800ca5f6  or      ebx, 80070000h
0x1800ca5fc  jmp     loc_1800CA6F2
0x1800ca601  mov     rcx, [rbp+var_48]
0x1800ca605  jmp     short loc_1800CA60B
0x1800ca607  mov     [rbp+var_48], rcx
0x1800ca60b  lea     rax, [rbp+cbData]
0x1800ca60f  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800ca614  mov     [rsp+78h+phkResult], r13; lpData
0x1800ca619  lea     r9, [rbp+Type]; lpType
0x1800ca620  xor     r8d, r8d; lpReserved
0x1800ca623  mov     rdx, r14; lpValueName
0x1800ca626  call    cs:__imp_RegQueryValueExW
0x1800ca62c  mov     ebx, eax
0x1800ca62e  test    eax, eax
0x1800ca630  jz      short loc_1800CA646
0x1800ca632  jle     loc_1800CA6ED
0x1800ca638  movzx   ebx, ax
0x1800ca63b  or      ebx, 80070000h
0x1800ca641  jmp     loc_1800CA6ED
0x1800ca646  cmp     dword ptr [rbp+Type], r15d
0x1800ca64d  jz      short loc_1800CA659
0x1800ca64f  mov     ebx, 8000FFFFh
0x1800ca654  jmp     loc_1800CA6ED
0x1800ca659  mov     ebx, dword ptr [rbp+cbData]
0x1800ca65c  shr     rbx, 1
0x1800ca65f  inc     rbx
0x1800ca662  mov     eax, 2
0x1800ca667  mul     rbx
0x1800ca66a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ca671  cmovb   rax, rcx
0x1800ca675  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ca67c  mov     rcx, rax; unsigned __int64
0x1800ca67f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ca684  mov     r15, rax
0x1800ca687  test    rax, rax
0x1800ca68a  jnz     short loc_1800CA693
0x1800ca68c  mov     ebx, 8007000Eh
0x1800ca691  jmp     short loc_1800CA6ED
0x1800ca693  mov     r8, rbx; Size
0x1800ca696  xor     edx, edx; Val
0x1800ca698  mov     rcx, r15; void *
0x1800ca69b  call    memset_0
0x1800ca6a0  lea     rax, [rbp+cbData]
0x1800ca6a4  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800ca6a9  mov     [rsp+78h+phkResult], r15; lpData
0x1800ca6ae  lea     r9, [rbp+Type]; lpType
0x1800ca6b5  xor     r8d, r8d; lpReserved
0x1800ca6b8  mov     rdx, r14; lpValueName
0x1800ca6bb  mov     rcx, [rbp+var_48]; hKey
0x1800ca6bf  call    cs:__imp_RegQueryValueExW
0x1800ca6c5  mov     ebx, eax
0x1800ca6c7  test    eax, eax
0x1800ca6c9  jz      short loc_1800CA6E0
0x1800ca6cb  jle     short loc_1800CA6D6
0x1800ca6cd  movzx   ebx, ax
0x1800ca6d0  or      ebx, 80070000h
0x1800ca6d6  mov     rcx, r15; Block
0x1800ca6d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca6de  jmp     short loc_1800CA6ED
0x1800ca6e0  mov     ebx, r13d
0x1800ca6e3  mov     r12, r15
0x1800ca6e6  jmp     short loc_1800CA6ED
0x1800ca6e8  mov     ebx, 80070057h
0x1800ca6ed  test    rsi, rsi
0x1800ca6f0  jz      short loc_1800CA701
0x1800ca6f2  mov     rcx, [rbp+var_48]; hKey
0x1800ca6f6  test    rcx, rcx
0x1800ca6f9  jz      short loc_1800CA701
0x1800ca6fb  call    cs:__imp_RegCloseKey
0x1800ca701  test    ebx, ebx
0x1800ca703  js      loc_1800CA898
0x1800ca709  mov     word ptr [rdi], 8
0x1800ca70e  mov     rcx, r12; psz
0x1800ca711  call    cs:__imp_SysAllocString
0x1800ca717  mov     [rdi+8], rax
0x1800ca71b  mov     rcx, r12; Block
0x1800ca71e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca723  jmp     loc_1800CA8B8
0x1800ca728  mov     rcx, rbx
0x1800ca72b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800ca730  test    al, al
0x1800ca732  jz      short loc_1800CA75E
0x1800ca734  mov     [rbp+cbData], r13
0x1800ca738  lea     r9, [rbp+cbData]
0x1800ca73c  mov     r8, r14
0x1800ca73f  mov     rdx, [rbp+var_38]
0x1800ca743  mov     rcx, [rbp+hKey]
0x1800ca747  call    DCGetRegistryQWORD
0x1800ca74c  test    eax, eax
0x1800ca74e  js      loc_1800CA58F
0x1800ca754  mov     word ptr [rdi], 5
0x1800ca759  jmp     loc_1800CA59B
0x1800ca75e  mov     rcx, rbx
0x1800ca761  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800ca766  test    al, al
0x1800ca768  jz      short loc_1800CA7BA
0x1800ca76a  mov     [rbp+Type], r13
0x1800ca771  lea     rax, [rbp+cbData]
0x1800ca775  mov     [rsp+78h+phkResult], rax; unsigned int *
0x1800ca77a  lea     r9, [rbp+Type]; unsigned __int16 **
0x1800ca781  mov     r8, r14; unsigned __int16 *
0x1800ca784  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x1800ca788  mov     rcx, [rbp+hKey]; HKEY
0x1800ca78c  call    ?DCCDNUtil_GetRegistryMultiString@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; DCCDNUtil_GetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x1800ca791  test    eax, eax
0x1800ca793  js      loc_1800CA58F
0x1800ca799  mov     word ptr [rdi], 2008h
0x1800ca79e  lea     r8, [rdi+8]; struct tagSAFEARRAY **
0x1800ca7a2  mov     rcx, [rbp+Type]; strIn
0x1800ca7a9  call    ?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z; MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)
0x1800ca7ae  mov     rcx, [rbp+Type]
0x1800ca7b5  jmp     loc_1800CA71E
0x1800ca7ba  mov     ebx, 8000FFFFh
0x1800ca7bf  jmp     loc_1800CA898
0x1800ca7c4  mov     r15d, r13d
0x1800ca7c7  mov     rcx, [rbp+hKey]; hKey
0x1800ca7cb  mov     dword ptr [rbp+Type], r13d
0x1800ca7d2  mov     r12d, 4
0x1800ca7d8  mov     dword ptr [rbp+cbData], r12d
0x1800ca7dc  mov     [rbp+var_30], r13
0x1800ca7e0  mov     dword ptr [rbp+var_48], r12d
0x1800ca7e4  test    rcx, rcx
0x1800ca7e7  jz      loc_1800CA87B
0x1800ca7ed  test    rsi, rsi
0x1800ca7f0  jz      short loc_1800CA826
0x1800ca7f2  lea     rax, [rbp+var_30]
0x1800ca7f6  mov     [rsp+78h+phkResult], rax; phkResult
0x1800ca7fb  mov     r9d, 20119h; samDesired
0x1800ca801  xor     r8d, r8d; ulOptions
0x1800ca804  mov     rdx, rsi; lpSubKey
0x1800ca807  call    cs:__imp_RegOpenKeyExW
0x1800ca80d  mov     ebx, eax
0x1800ca80f  test    eax, eax
0x1800ca811  jz      short loc_1800CA820
0x1800ca813  jle     short loc_1800CA885
0x1800ca815  movzx   ebx, ax
0x1800ca818  or      ebx, 80070000h
0x1800ca81e  jmp     short loc_1800CA885
0x1800ca820  mov     rcx, [rbp+var_30]
0x1800ca824  jmp     short loc_1800CA82A
0x1800ca826  mov     [rbp+var_30], rcx
0x1800ca82a  lea     rax, [rbp+var_48]
0x1800ca82e  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800ca833  lea     rax, [rbp+Type]
0x1800ca83a  mov     [rsp+78h+phkResult], rax; lpData
0x1800ca83f  lea     r9, [rbp+cbData]; lpType
0x1800ca843  xor     r8d, r8d; lpReserved
0x1800ca846  mov     rdx, r14; lpValueName
0x1800ca849  call    cs:__imp_RegQueryValueExW
0x1800ca84f  mov     ebx, eax
0x1800ca851  test    eax, eax
0x1800ca853  jz      short loc_1800CA862
0x1800ca855  jle     short loc_1800CA880
0x1800ca857  movzx   ebx, ax
0x1800ca85a  or      ebx, 80070000h
0x1800ca860  jmp     short loc_1800CA880
0x1800ca862  cmp     dword ptr [rbp+cbData], r12d
0x1800ca866  jz      short loc_1800CA86F
  ... truncated ...
```
