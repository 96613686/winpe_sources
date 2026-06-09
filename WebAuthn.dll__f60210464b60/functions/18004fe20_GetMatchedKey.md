# GetMatchedKey

- ea: `0x18004fe20`
- end: `0x1800501c3`
- name: `GetMatchedKey`
- size: `931`
- prototype: `__int64 __usercall@<rax>(NCRYPT_PROV_HANDLE hProvider@<rcx>, LPCWSTR pszKeyName@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800164c8`

## callees

- `0x18000cb50`
- `0x180016834`
- `0x1800176c4`
- `0x180017764`
- `0x180017a88`
- `0x180020584`
- `0x1800205e4`
- `0x180020614`
- `0x180036da4`
- `0x18004fe20`

## import_xrefs

- `ngcutils!NgcAreStringsEqual` at `0x18004ff34`
- `ngcutils!NgcAreStringsEqual` at `0x18004ff34`
- `ncrypt!NCryptOpenKey` at `0x18004fe6f`
- `ncrypt!NCryptOpenKey` at `0x18004fe6f`
- `ncrypt!NCryptGetProperty` at `0x180050150`
- `ncrypt!NCryptGetProperty` at `0x180050150`

## string_xrefs

- `0x18004fe7f`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18004fedc`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18004ff95`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x180050006`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x180050079`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18005015e`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x180050059`: `NgcUserSid`

## pseudocode

```c
__int64 __fastcall GetMatchedKey(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszKeyName, _WORD *a3, _QWORD *a4, _BYTE *a5)
{
  SECURITY_STATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r12
  __int64 v11; // r15
  int PropertyValue; // eax
  __int64 v13; // rdx
  __int64 v14; // rdi
  unsigned int v15; // r15d
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // r14
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rsi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // r15
  __int64 v28; // rdx
  SECURITY_STATUS Property; // eax
  int dwFlags; // [rsp+20h] [rbp-58h]
  int dwFlagsa; // [rsp+20h] [rbp-58h]
  int v33; // [rsp+30h] [rbp-48h] BYREF
  DWORD pcbResult; // [rsp+34h] [rbp-44h] BYREF
  __int64 v35; // [rsp+38h] [rbp-40h] BYREF
  __int64 v36; // [rsp+40h] [rbp-38h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-30h] BYREF
  __int64 v38; // [rsp+50h] [rbp-28h] BYREF
  __int64 v39; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v40[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  *a4 = 0;
  phKey = 0;
  *a5 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v8 = NCryptOpenKey(hProvider, &phKey, pszKeyName, 0, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)v8,
      dwFlags);
    goto LABEL_45;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( pszKeyName[v11] );
  v35 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  PropertyValue = GetPropertyValue(phKey, L"NgcDomainName");
  v9 = PropertyValue;
  if ( PropertyValue < 0 )
  {
    v13 = 668;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)PropertyValue,
      dwFlags);
LABEL_8:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v35);
    goto LABEL_45;
  }
  v14 = v35;
  v15 = 2 * v11 + 50;
  if ( v35 )
  {
    v33 = 0;
    PropertyValue = NgcAreStringsEqual(a3, v35, &v33);
    v9 = PropertyValue;
    if ( PropertyValue < 0 )
    {
      v13 = 682;
      goto LABEL_7;
    }
    if ( *a3 && !v33 )
    {
LABEL_12:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v35);
      v9 = 0;
      goto LABEL_45;
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v14 + 2 * v16) );
    v15 += 2 * v16 + 2;
  }
  else if ( a3 || MEMORY[0] )
  {
    goto LABEL_12;
  }
  v36 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  v17 = GetPropertyValue(phKey, L"NgcTenantDomainName");
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BB,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)v17,
      dwFlags);
LABEL_22:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v36);
    goto LABEL_8;
  }
  v18 = v36;
  if ( v36 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(v36 + 2 * v19) );
    v15 += 2 * v19 + 2;
  }
  v38 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v38,
    0);
  v20 = GetPropertyValue(phKey, L"NgcAccountId");
  v9 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)v20,
      dwFlags);
LABEL_29:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v38);
    goto LABEL_22;
  }
  v21 = v38;
  if ( v38 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v38 + 2 * v22) );
    v15 += 2 * v22 + 2;
  }
  v39 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v39,
    0);
  v23 = GetPropertyValue(phKey, L"NgcUserSid");
  v9 = v23;
  if ( v23 < 0 )
  {
    v24 = (unsigned int)v23;
    v25 = 721;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)v24,
      dwFlags);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v39);
    goto LABEL_29;
  }
  v26 = v39;
  if ( v39 )
  {
    do
      ++v10;
    while ( *(_WORD *)(v39 + 2 * v10) );
    v15 += 2 * v10 + 2;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(v40, v15);
  v27 = v40[0];
  if ( !v40[0] )
  {
    v9 = -2147024882;
    v25 = 728;
    v24 = 2147942414LL;
    goto LABEL_36;
  }
  v28 = v40[0] + 32LL;
  v40[0] += 48LL;
  CopyAndUpdatePointerInUserIdKeyInfo(v40, v28, pszKeyName);
  CopyAndUpdatePointerInUserIdKeyInfo(v40, v27, v14);
  CopyAndUpdatePointerInUserIdKeyInfo(v40, v27 + 8, v18);
  CopyAndUpdatePointerInUserIdKeyInfo(v40, v27 + 16, v21);
  CopyAndUpdatePointerInUserIdKeyInfo(v40, v27 + 24, v26);
  pcbResult = 0;
  Property = NCryptGetProperty(phKey, L"NgcContainerStatus", (PBYTE)(v27 + 40), 4u, &pcbResult, 0);
  if ( Property < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)(unsigned int)Property,
      dwFlagsa);
  *a5 = 1;
  *a4 = v27;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v39);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v38);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v36);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v35);
  v9 = 0;
LABEL_45:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  return v9;
}

```

## disassembly

```asm
0x18004fe20  mov     [rsp-40h+arg_18], r9
0x18004fe25  push    rbp
0x18004fe26  push    rbx
0x18004fe27  push    rsi
0x18004fe28  push    rdi
0x18004fe29  push    r12
0x18004fe2b  push    r13
0x18004fe2d  push    r14
0x18004fe2f  push    r15
0x18004fe31  mov     rbp, rsp
0x18004fe34  sub     rsp, 78h
0x18004fe38  mov     rax, [rbp+arg_20]
0x18004fe3c  xor     r14d, r14d
0x18004fe3f  mov     r13, rdx
0x18004fe42  mov     [r9], r14
0x18004fe45  mov     rbx, rcx
0x18004fe48  mov     [rbp+phKey], r14
0x18004fe4c  xor     edx, edx
0x18004fe4e  lea     rcx, [rbp+phKey]
0x18004fe52  mov     [rax], r14b
0x18004fe55  mov     rsi, r8
0x18004fe58  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004fe5d  xor     r9d, r9d; dwLegacyKeySpec
0x18004fe60  mov     [rsp+78h+dwFlags], r14d; int
0x18004fe65  mov     r8, r13; pszKeyName
0x18004fe68  lea     rdx, [rbp+phKey]; phKey
0x18004fe6c  mov     rcx, rbx; hProvider
0x18004fe6f  call    cs:__imp_NCryptOpenKey
0x18004fe75  mov     ebx, eax
0x18004fe77  test    eax, eax
0x18004fe79  jns     short loc_18004FE98
0x18004fe7b  mov     rcx, [rbp+40h]; this
0x18004fe7f  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004fe86  mov     r9d, eax; char *
0x18004fe89  mov     edx, 292h; void *
0x18004fe8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fe93  jmp     loc_1800501A7
0x18004fe98  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004fe9c  mov     r15, r12
0x18004fe9f  inc     r15
0x18004fea2  cmp     [r13+r15*2+0], r14w
0x18004fea8  jnz     short loc_18004FE9F
0x18004feaa  xor     edx, edx
0x18004feac  mov     [rbp+var_40], r14
0x18004feb0  lea     rcx, [rbp+var_40]
0x18004feb4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004feb9  mov     rcx, [rbp+phKey]; hObject
0x18004febd  lea     r8, [rbp+var_40]
0x18004fec1  lea     rdx, aNgcdomainname; "NgcDomainName"
0x18004fec8  call    GetPropertyValue
0x18004fecd  mov     ebx, eax
0x18004fecf  test    eax, eax
0x18004fed1  jns     short loc_18004FEF9
0x18004fed3  mov     edx, 29Ch; void *
0x18004fed8  mov     rcx, [rbp+40h]; this
0x18004fedc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004fee3  mov     r9d, eax; char *
0x18004fee6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004feeb  lea     rcx, [rbp+var_40]
0x18004feef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004fef4  jmp     loc_1800501A7
0x18004fef9  mov     rdi, [rbp+var_40]
0x18004fefd  lea     r15d, ds:32h[r15*2]
0x18004ff05  test    rdi, rdi
0x18004ff08  jnz     short loc_18004FF26
0x18004ff0a  test    rsi, rsi
0x18004ff0d  jnz     short loc_18004FF15
0x18004ff0f  cmp     [r14], r14w
0x18004ff13  jz      short loc_18004FF68
0x18004ff15  lea     rcx, [rbp+var_40]
0x18004ff19  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ff1e  mov     ebx, r14d
0x18004ff21  jmp     loc_1800501A7
0x18004ff26  lea     r8, [rbp+var_48]
0x18004ff2a  mov     [rbp+var_48], r14d
0x18004ff2e  mov     rdx, rdi
0x18004ff31  mov     rcx, rsi
0x18004ff34  call    cs:__imp_NgcAreStringsEqual
0x18004ff3a  mov     ebx, eax
0x18004ff3c  test    eax, eax
0x18004ff3e  jns     short loc_18004FF47
0x18004ff40  mov     edx, 2AAh
0x18004ff45  jmp     short loc_18004FED8
0x18004ff47  cmp     [rsi], r14w
0x18004ff4b  jz      short loc_18004FF53
0x18004ff4d  cmp     [rbp+var_48], r14d
0x18004ff51  jz      short loc_18004FF15
0x18004ff53  mov     rax, r12
0x18004ff56  inc     rax
0x18004ff59  cmp     [rdi+rax*2], r14w
0x18004ff5e  jnz     short loc_18004FF56
0x18004ff60  lea     r15d, [r15+rax*2]
0x18004ff64  add     r15d, 2
0x18004ff68  xor     edx, edx
0x18004ff6a  mov     [rbp+var_38], r14
0x18004ff6e  lea     rcx, [rbp+var_38]
0x18004ff72  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004ff77  mov     rcx, [rbp+phKey]; hObject
0x18004ff7b  lea     r8, [rbp+var_38]
0x18004ff7f  lea     rdx, aNgctenantdomai; "NgcTenantDomainName"
0x18004ff86  call    GetPropertyValue
0x18004ff8b  mov     ebx, eax
0x18004ff8d  test    eax, eax
0x18004ff8f  jns     short loc_18004FFB7
0x18004ff91  mov     rcx, [rbp+40h]; this
0x18004ff95  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18004ff9c  mov     r9d, eax; char *
0x18004ff9f  mov     edx, 2BBh; void *
0x18004ffa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ffa9  lea     rcx, [rbp+var_38]
0x18004ffad  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004ffb2  jmp     loc_18004FEEB
0x18004ffb7  mov     r14, [rbp+var_38]
0x18004ffbb  xor     ecx, ecx
0x18004ffbd  test    r14, r14
0x18004ffc0  jz      short loc_18004FFD7
0x18004ffc2  mov     rax, r12
0x18004ffc5  inc     rax
0x18004ffc8  cmp     [r14+rax*2], cx
0x18004ffcd  jnz     short loc_18004FFC5
0x18004ffcf  lea     r15d, [r15+rax*2]
0x18004ffd3  add     r15d, 2
0x18004ffd7  mov     [rbp+var_28], rcx
0x18004ffdb  xor     edx, edx
0x18004ffdd  lea     rcx, [rbp+var_28]
0x18004ffe1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004ffe6  mov     rcx, [rbp+phKey]; hObject
0x18004ffea  lea     r8, [rbp+var_28]
0x18004ffee  lea     rdx, aNgcaccountid; "NgcAccountId"
0x18004fff5  call    GetPropertyValue
0x18004fffa  xor     ecx, ecx
0x18004fffc  mov     ebx, eax
0x18004fffe  test    eax, eax
0x180050000  jns     short loc_180050025
0x180050002  mov     rcx, [rbp+40h]; this
0x180050006  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18005000d  mov     r9d, eax; char *
0x180050010  mov     edx, 2C6h; void *
0x180050015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005001a  lea     rcx, [rbp+var_28]
0x18005001e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180050023  jmp     short loc_18004FFA9
0x180050025  mov     rsi, [rbp+var_28]
0x180050029  test    rsi, rsi
0x18005002c  jz      short loc_180050042
0x18005002e  mov     rax, r12
0x180050031  inc     rax
0x180050034  cmp     [rsi+rax*2], cx
0x180050038  jnz     short loc_180050031
0x18005003a  lea     r15d, [r15+rax*2]
0x18005003e  add     r15d, 2
0x180050042  mov     [rbp+var_20], rcx
0x180050046  xor     edx, edx
0x180050048  lea     rcx, [rbp+var_20]
0x18005004c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180050051  mov     rcx, [rbp+phKey]; hObject
0x180050055  lea     r8, [rbp+var_20]
0x180050059  lea     rdx, aNgcusersid; "NgcUserSid"
0x180050060  call    GetPropertyValue
0x180050065  xor     ecx, ecx
0x180050067  mov     ebx, eax
0x180050069  test    eax, eax
0x18005006b  jns     short loc_180050090
0x18005006d  mov     r9d, eax; char *
0x180050070  mov     edx, 2D1h; void *
0x180050075  mov     rcx, [rbp+40h]; this
0x180050079  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180050080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050085  lea     rcx, [rbp+var_20]
0x180050089  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18005008e  jmp     short loc_18005001A
0x180050090  mov     rbx, [rbp+var_20]
0x180050094  test    rbx, rbx
0x180050097  jz      short loc_1800500AB
0x180050099  inc     r12
0x18005009c  cmp     [rbx+r12*2], cx
0x1800500a1  jnz     short loc_180050099
0x1800500a3  lea     r15d, [r15+r12*2]
0x1800500a7  add     r15d, 2
0x1800500ab  mov     edx, r15d
0x1800500ae  lea     rcx, [rbp+var_18]
0x1800500b2  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800500b7  mov     r15, [rbp+var_18]
0x1800500bb  xor     r12d, r12d
0x1800500be  test    r15, r15
0x1800500c1  jnz     short loc_1800500D2
0x1800500c3  mov     ebx, 8007000Eh
0x1800500c8  mov     edx, 2D8h
0x1800500cd  mov     r9d, ebx
0x1800500d0  jmp     short loc_180050075
0x1800500d2  lea     rax, [r15+30h]
0x1800500d6  mov     r8, r13
0x1800500d9  lea     rdx, [r15+20h]
0x1800500dd  mov     [rbp+var_18], rax
0x1800500e1  lea     rcx, [rbp+var_18]
0x1800500e5  call    CopyAndUpdatePointerInUserIdKeyInfo
0x1800500ea  mov     r8, rdi
0x1800500ed  lea     rcx, [rbp+var_18]
0x1800500f1  mov     rdx, r15
0x1800500f4  call    CopyAndUpdatePointerInUserIdKeyInfo
0x1800500f9  lea     rdx, [r15+8]
0x1800500fd  mov     r8, r14
0x180050100  lea     rcx, [rbp+var_18]
0x180050104  call    CopyAndUpdatePointerInUserIdKeyInfo
0x180050109  lea     rdx, [r15+10h]
0x18005010d  mov     r8, rsi
0x180050110  lea     rcx, [rbp+var_18]
0x180050114  call    CopyAndUpdatePointerInUserIdKeyInfo
0x180050119  lea     rdx, [r15+18h]
0x18005011d  mov     r8, rbx
0x180050120  lea     rcx, [rbp+var_18]
0x180050124  call    CopyAndUpdatePointerInUserIdKeyInfo
0x180050129  mov     rcx, [rbp+phKey]; hObject
0x18005012d  lea     rax, [rbp+pcbResult]
0x180050131  lea     r8, [r15+28h]; pbOutput
0x180050135  mov     [rsp+78h+var_50], r12d; dwFlags
0x18005013a  mov     r9d, 4; cbOutput
0x180050140  mov     qword ptr [rsp+78h+dwFlags], rax; int
0x180050145  lea     rdx, aNgccontainerst; "NgcContainerStatus"
0x18005014c  mov     [rbp+pcbResult], r12d
0x180050150  call    cs:__imp_NCryptGetProperty
0x180050156  test    eax, eax
0x180050158  jns     short loc_180050172
0x18005015a  mov     rcx, [rbp+40h]; this
0x18005015e  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x180050165  mov     r9d, eax; char *
0x180050168  mov     edx, 2EDh; void *
0x18005016d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050172  mov     rax, [rbp+arg_20]
0x180050176  lea     rcx, [rbp+var_20]
0x18005017a  mov     byte ptr [rax], 1
0x18005017d  mov     rax, [rbp+arg_18]
0x180050181  mov     [rax], r15
0x180050184  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180050189  lea     rcx, [rbp+var_28]
0x18005018d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180050192  lea     rcx, [rbp+var_38]
0x180050196  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18005019b  lea     rcx, [rbp+var_40]
0x18005019f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800501a4  mov     ebx, r12d
0x1800501a7  lea     rcx, [rbp+phKey]
0x1800501ab  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800501b0  mov     eax, ebx
0x1800501b2  add     rsp, 78h
0x1800501b6  pop     r15
0x1800501b8  pop     r14
0x1800501ba  pop     r13
0x1800501bc  pop     r12
0x1800501be  pop     rdi
0x1800501bf  pop     rsi
0x1800501c0  pop     rbx
0x1800501c1  pop     rbp
0x1800501c2  retn
```
