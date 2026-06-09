# DeclaredConfigurationStore_ReadResultData_1

- ea: `0x1800baf74`
- end: `0x1800bb4b4`
- name: `DeclaredConfigurationStore_ReadResultData_1`
- size: `1344`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, LPCWSTR lpValueName, DWORD cbData)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1800c0f2c`

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
- `0x1800baf74`
- `0x1800c3ff8`
- `0x1800c40c4`
- `0x1801007e8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb1f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb288`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb40f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb1f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb288`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb40f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb454`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb1ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb3cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb1ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb3cd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bb2da`
- `OLEAUT32!__imp_SysAllocString` at `0x1800bb2da`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_ReadResultData_1(
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
      GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey_0(a1, a2, a3, a4, (__int64)&v35);
    else
      GetResultsEnrollmentIdSidStateDocIdVersionKey_1(a1, a2, a3, &v35);
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
0x1800baf74  push    rbp
0x1800baf76  push    rbx
0x1800baf77  push    rsi
0x1800baf78  push    rdi
0x1800baf79  push    r12
0x1800baf7b  push    r13
0x1800baf7d  push    r14
0x1800baf7f  push    r15
0x1800baf81  mov     rbp, rsp
0x1800baf84  sub     rsp, 78h
0x1800baf88  xor     r13d, r13d
0x1800baf8b  mov     [rbp+hKey], r13
0x1800baf8f  mov     rdi, [rbp+cbData]
0x1800baf96  test    rdi, rdi
0x1800baf99  jz      loc_1800BB495
0x1800baf9f  mov     r14, [rbp+lpValueName]
0x1800bafa3  test    r14, r14
0x1800bafa6  jz      loc_1800BB495
0x1800bafac  test    rcx, rcx
0x1800bafaf  jz      loc_1800BB495
0x1800bafb5  test    rdx, rdx
0x1800bafb8  jz      loc_1800BB495
0x1800bafbe  test    r8, r8
0x1800bafc1  jz      loc_1800BB495
0x1800bafc7  lea     rax, [rbp+hKey]
0x1800bafcb  mov     [rbp+var_18], r13
0x1800bafcf  mov     [rbp+var_10], 1
0x1800bafd3  mov     [rbp+var_20], rax
0x1800bafd7  test    r9, r9
0x1800bafda  jnz     short loc_1800BAFE7
0x1800bafdc  lea     r9, [rbp+var_18]
0x1800bafe0  call    GetResultsEnrollmentIdSidStateDocIdVersionKey_1
0x1800bafe5  jmp     short loc_1800BAFF5
0x1800bafe7  lea     rax, [rbp+var_18]
0x1800bafeb  mov     [rsp+78h+phkResult], rax
0x1800baff0  call    GetResultsContainerIdEnrollmentIdSidStateDocIdVersionKey_0
0x1800baff5  lea     rcx, [rbp+var_20]
0x1800baff9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800baffe  mov     rsi, r13
0x1800bb001  mov     [rbp+var_30], r13
0x1800bb005  mov     r15d, 2
0x1800bb00b  mov     r9, [rbp+arg_20]
0x1800bb00f  test    r9, r9
0x1800bb012  jz      short loc_1800BB07C
0x1800bb014  mov     rax, [rbp+arg_28]
0x1800bb018  mov     [rbp+var_18], r13
0x1800bb01c  mov     [rbp+var_10], 1
0x1800bb020  test    rax, rax
0x1800bb023  jz      short loc_1800BB047
0x1800bb025  lea     rcx, [rbp+var_30]
0x1800bb029  mov     [rbp+var_20], rcx
0x1800bb02d  mov     [rsp+78h+phkResult], rax
0x1800bb032  mov     r8d, r15d
0x1800bb035  lea     rdx, aSS; "%s\\%s"
0x1800bb03c  lea     rcx, [rbp+var_18]
0x1800bb040  call    DCStringCchPrintfAllStrings
0x1800bb045  jmp     short loc_1800BB065
0x1800bb047  lea     rax, [rbp+var_30]
0x1800bb04b  mov     [rbp+var_20], rax
0x1800bb04f  mov     r8d, 1
0x1800bb055  lea     rdx, aS; "%s"
0x1800bb05c  lea     rcx, [rbp+var_18]
0x1800bb060  call    DCStringCchPrintfAllStrings
0x1800bb065  mov     ebx, eax
0x1800bb067  lea     rcx, [rbp+var_20]
0x1800bb06b  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800bb070  test    ebx, ebx
0x1800bb072  js      loc_1800BB45E
0x1800bb078  mov     rsi, [rbp+var_30]
0x1800bb07c  movzx   ecx, word ptr [rdi]
0x1800bb07f  mov     eax, 3
0x1800bb084  sub     ecx, eax
0x1800bb086  jz      loc_1800BB38A
0x1800bb08c  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800bb093  sub     ecx, r15d
0x1800bb096  jz      loc_1800BB2F1
0x1800bb09c  sub     ecx, eax
0x1800bb09e  jz      loc_1800BB170
0x1800bb0a4  sub     ecx, 0Ch
0x1800bb0a7  jz      short loc_1800BB122
0x1800bb0a9  sub     ecx, 1FF4h
0x1800bb0af  jz      loc_1800BB32D
0x1800bb0b5  cmp     ecx, 9
0x1800bb0b8  jnz     loc_1800BB380
0x1800bb0be  mov     [rbp+var_40], r13
0x1800bb0c2  mov     dword ptr [rbp+cbData], r13d
0x1800bb0c9  lea     rax, [rbp+cbData]
0x1800bb0d0  mov     [rsp+78h+phkResult], rax
0x1800bb0d5  lea     r9, [rbp+var_40]
0x1800bb0d9  mov     r8, r14
0x1800bb0dc  mov     rdx, rsi
0x1800bb0df  mov     rcx, [rbp+hKey]
0x1800bb0e3  call    DCGetRegistryBinary
0x1800bb0e8  mov     ebx, eax
0x1800bb0ea  test    eax, eax
0x1800bb0ec  jns     short loc_1800BB0FC
0x1800bb0ee  lea     rcx, [rbp+var_40]
0x1800bb0f2  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800bb0f7  jmp     loc_1800BB45E
0x1800bb0fc  mov     r8, rdi
0x1800bb0ff  mov     edx, dword ptr [rbp+cbData]; Size
0x1800bb105  mov     rcx, [rbp+var_40]; Src
0x1800bb109  call    DCInlineSetBinaryToVariant
0x1800bb10e  mov     ebx, eax
0x1800bb110  lea     rcx, [rbp+var_40]
0x1800bb114  test    eax, eax
0x1800bb116  js      short loc_1800BB0F2
0x1800bb118  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x1800bb11d  jmp     loc_1800BB47E
0x1800bb122  mov     rcx, rbx
0x1800bb125  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800bb12a  test    al, al
0x1800bb12c  jz      loc_1800BB2F1
0x1800bb132  mov     [rbp+cbData], r13
0x1800bb139  lea     r9, [rbp+cbData]
0x1800bb140  mov     r8, r14
0x1800bb143  mov     rdx, [rbp+var_30]
0x1800bb147  mov     rcx, [rbp+hKey]
0x1800bb14b  call    DCGetRegistryQWORD
0x1800bb150  test    eax, eax
0x1800bb152  jns     short loc_1800BB15B
0x1800bb154  mov     ebx, eax
0x1800bb156  jmp     loc_1800BB45E
0x1800bb15b  mov     word ptr [rdi], 14h
0x1800bb160  mov     rax, [rbp+cbData]
0x1800bb167  mov     [rdi+8], rax
0x1800bb16b  jmp     loc_1800BB47E
0x1800bb170  mov     r12, r13
0x1800bb173  mov     rcx, [rbp+hKey]; hKey
0x1800bb177  mov     [rbp+Type], 1
0x1800bb17e  mov     [rbp+var_40], r13
0x1800bb182  mov     dword ptr [rbp+cbData], r13d
0x1800bb189  test    rcx, rcx
0x1800bb18c  jz      loc_1800BB2B1
0x1800bb192  test    rsi, rsi
0x1800bb195  jz      short loc_1800BB1D2
0x1800bb197  lea     rax, [rbp+var_40]
0x1800bb19b  mov     [rsp+78h+phkResult], rax; phkResult
0x1800bb1a0  mov     r9d, 20119h; samDesired
0x1800bb1a6  xor     r8d, r8d; ulOptions
0x1800bb1a9  mov     rdx, rsi; lpSubKey
0x1800bb1ac  call    cs:__imp_RegOpenKeyExW
0x1800bb1b2  mov     ebx, eax
0x1800bb1b4  test    eax, eax
0x1800bb1b6  jz      short loc_1800BB1CC
0x1800bb1b8  jle     loc_1800BB2BB
0x1800bb1be  movzx   ebx, ax
0x1800bb1c1  or      ebx, 80070000h
0x1800bb1c7  jmp     loc_1800BB2BB
0x1800bb1cc  mov     rcx, [rbp+var_40]
0x1800bb1d0  jmp     short loc_1800BB1D6
0x1800bb1d2  mov     [rbp+var_40], rcx
0x1800bb1d6  lea     rax, [rbp+cbData]
0x1800bb1dd  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bb1e2  mov     [rsp+78h+phkResult], r13; lpData
0x1800bb1e7  lea     r9, [rbp+Type]; lpType
0x1800bb1eb  xor     r8d, r8d; lpReserved
0x1800bb1ee  mov     rdx, r14; lpValueName
0x1800bb1f1  call    cs:__imp_RegQueryValueExW
0x1800bb1f7  mov     ebx, eax
0x1800bb1f9  test    eax, eax
0x1800bb1fb  jz      short loc_1800BB211
0x1800bb1fd  jle     loc_1800BB2B6
0x1800bb203  movzx   ebx, ax
0x1800bb206  or      ebx, 80070000h
0x1800bb20c  jmp     loc_1800BB2B6
0x1800bb211  cmp     [rbp+Type], 1
0x1800bb215  jz      short loc_1800BB221
0x1800bb217  mov     ebx, 8000FFFFh
0x1800bb21c  jmp     loc_1800BB2B6
0x1800bb221  mov     ebx, dword ptr [rbp+cbData]
0x1800bb227  shr     rbx, 1
0x1800bb22a  inc     rbx
0x1800bb22d  mov     rax, r15
0x1800bb230  mul     rbx
0x1800bb233  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bb23a  cmovb   rax, rcx
0x1800bb23e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bb245  mov     rcx, rax; unsigned __int64
0x1800bb248  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bb24d  mov     r15, rax
0x1800bb250  test    rax, rax
0x1800bb253  jnz     short loc_1800BB25C
0x1800bb255  mov     ebx, 8007000Eh
0x1800bb25a  jmp     short loc_1800BB2B6
0x1800bb25c  mov     r8, rbx; Size
0x1800bb25f  xor     edx, edx; Val
0x1800bb261  mov     rcx, r15; void *
0x1800bb264  call    memset_0
0x1800bb269  lea     rax, [rbp+cbData]
0x1800bb270  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bb275  mov     [rsp+78h+phkResult], r15; lpData
0x1800bb27a  lea     r9, [rbp+Type]; lpType
0x1800bb27e  xor     r8d, r8d; lpReserved
0x1800bb281  mov     rdx, r14; lpValueName
0x1800bb284  mov     rcx, [rbp+var_40]; hKey
0x1800bb288  call    cs:__imp_RegQueryValueExW
0x1800bb28e  mov     ebx, eax
0x1800bb290  test    eax, eax
0x1800bb292  jz      short loc_1800BB2A9
0x1800bb294  jle     short loc_1800BB29F
0x1800bb296  movzx   ebx, ax
0x1800bb299  or      ebx, 80070000h
0x1800bb29f  mov     rcx, r15; Block
0x1800bb2a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb2a7  jmp     short loc_1800BB2B6
0x1800bb2a9  mov     ebx, r13d
0x1800bb2ac  mov     r12, r15
0x1800bb2af  jmp     short loc_1800BB2B6
0x1800bb2b1  mov     ebx, 80070057h
0x1800bb2b6  test    rsi, rsi
0x1800bb2b9  jz      short loc_1800BB2CA
0x1800bb2bb  mov     rcx, [rbp+var_40]; hKey
0x1800bb2bf  test    rcx, rcx
0x1800bb2c2  jz      short loc_1800BB2CA
0x1800bb2c4  call    cs:__imp_RegCloseKey
0x1800bb2ca  test    ebx, ebx
0x1800bb2cc  js      loc_1800BB45E
0x1800bb2d2  mov     word ptr [rdi], 8
0x1800bb2d7  mov     rcx, r12; psz
0x1800bb2da  call    cs:__imp_SysAllocString
0x1800bb2e0  mov     [rdi+8], rax
0x1800bb2e4  mov     rcx, r12; Block
0x1800bb2e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bb2ec  jmp     loc_1800BB47E
0x1800bb2f1  mov     rcx, rbx
0x1800bb2f4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800bb2f9  test    al, al
0x1800bb2fb  jz      short loc_1800BB32D
0x1800bb2fd  mov     [rbp+cbData], r13
0x1800bb304  lea     r9, [rbp+cbData]
0x1800bb30b  mov     r8, r14
0x1800bb30e  mov     rdx, [rbp+var_30]
0x1800bb312  mov     rcx, [rbp+hKey]
0x1800bb316  call    DCGetRegistryQWORD
0x1800bb31b  test    eax, eax
0x1800bb31d  js      loc_1800BB154
0x1800bb323  mov     word ptr [rdi], 5
0x1800bb328  jmp     loc_1800BB160
0x1800bb32d  mov     rcx, rbx
0x1800bb330  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800bb335  test    al, al
0x1800bb337  jz      short loc_1800BB380
0x1800bb339  mov     [rbp+var_28], r13
0x1800bb33d  lea     rax, [rbp+cbData]
0x1800bb344  mov     [rsp+78h+phkResult], rax; unsigned int *
0x1800bb349  lea     r9, [rbp+var_28]; unsigned __int16 **
0x1800bb34d  mov     r8, r14; unsigned __int16 *
0x1800bb350  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800bb354  mov     rcx, [rbp+hKey]; HKEY
0x1800bb358  call    ?DCCDNUtil_GetRegistryMultiString@@YAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z; DCCDNUtil_GetRegistryMultiString(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)
0x1800bb35d  test    eax, eax
0x1800bb35f  js      loc_1800BB154
0x1800bb365  mov     word ptr [rdi], 2008h
0x1800bb36a  lea     r8, [rdi+8]; struct tagSAFEARRAY **
0x1800bb36e  mov     rcx, [rbp+var_28]; strIn
0x1800bb372  call    ?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z; MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)
0x1800bb377  mov     rcx, [rbp+var_28]
0x1800bb37b  jmp     loc_1800BB2E7
0x1800bb380  mov     ebx, 8000FFFFh
0x1800bb385  jmp     loc_1800BB45E
0x1800bb38a  mov     r15d, r13d
0x1800bb38d  mov     rcx, [rbp+hKey]; hKey
0x1800bb391  mov     [rbp+Type], r13d
0x1800bb395  mov     r12d, 4
0x1800bb39b  mov     dword ptr [rbp+cbData], r12d
0x1800bb3a2  mov     [rbp+var_28], r13
0x1800bb3a6  mov     dword ptr [rbp+var_40], r12d
0x1800bb3aa  test    rcx, rcx
0x1800bb3ad  jz      loc_1800BB441
0x1800bb3b3  test    rsi, rsi
0x1800bb3b6  jz      short loc_1800BB3EC
0x1800bb3b8  lea     rax, [rbp+var_28]
0x1800bb3bc  mov     [rsp+78h+phkResult], rax; phkResult
0x1800bb3c1  mov     r9d, 20119h; samDesired
0x1800bb3c7  xor     r8d, r8d; ulOptions
0x1800bb3ca  mov     rdx, rsi; lpSubKey
0x1800bb3cd  call    cs:__imp_RegOpenKeyExW
0x1800bb3d3  mov     ebx, eax
0x1800bb3d5  test    eax, eax
0x1800bb3d7  jz      short loc_1800BB3E6
0x1800bb3d9  jle     short loc_1800BB44B
0x1800bb3db  movzx   ebx, ax
0x1800bb3de  or      ebx, 80070000h
0x1800bb3e4  jmp     short loc_1800BB44B
0x1800bb3e6  mov     rcx, [rbp+var_28]
0x1800bb3ea  jmp     short loc_1800BB3F0
0x1800bb3ec  mov     [rbp+var_28], rcx
0x1800bb3f0  lea     rax, [rbp+var_40]
0x1800bb3f4  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800bb3f9  lea     rax, [rbp+Type]
0x1800bb3fd  mov     [rsp+78h+phkResult], rax; lpData
0x1800bb402  lea     r9, [rbp+cbData]; lpType
0x1800bb409  xor     r8d, r8d; lpReserved
0x1800bb40c  mov     rdx, r14; lpValueName
0x1800bb40f  call    cs:__imp_RegQueryValueExW
0x1800bb415  mov     ebx, eax
0x1800bb417  test    eax, eax
0x1800bb419  jz      short loc_1800BB428
0x1800bb41b  jle     short loc_1800BB446
  ... truncated ...
```
