# SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a_

- ea: `0x1801fc10c`
- end: `0x1801fc706`
- name: `SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a___`
- size: `1530`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801fec50`

## callees

- `0x180070b78`
- `0x180082dd4`
- `0x180087238`
- `0x180098bf4`
- `0x1800a2854`
- `0x1800dc614`
- `0x1800e0d0c`
- `0x1800f0260`
- `0x1800f10e4`
- `0x1801fc05c`
- `0x1801fc10c`
- `0x1801fdd5c`
- `0x1801fefc4`
- `0x1801ff144`
- `0x180206084`
- `0x180206528`
- `0x180206544`
- `0x18020660c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801fc252`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801fc291`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801fc252`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801fc291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc36a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc63b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc6d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc36a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc40f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc63b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801fc6d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a_(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6)
{
  int v9; // eax
  const unsigned __int16 *v10; // rcx
  unsigned int v11; // r9d
  int AssociationPath; // eax
  unsigned int v13; // ebx
  int MachineID; // eax
  HKEY *v16; // rax
  HKEY *v17; // rax
  unsigned int Key; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  int SystemTimeFromRegKey; // eax
  unsigned int AssociationsHashVersion; // eax
  void *v26; // rbx
  int v27; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned __int16 *v30; // rdi
  int v31; // eax
  int v32; // eax
  unsigned int v33; // esi
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  int wHour; // [rsp+48h] [rbp-B8h]
  int wMinute; // [rsp+50h] [rbp-B0h]
  int wSecond; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v46; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v47; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME v48; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v47 = a3;
  LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_(
    a6,
    L"SetDefault-ProgIdAndHash: Association=%ls, ProgId=%ls",
    a4,
    a5);
  memset_0(SubKey, 0, 0x208u);
  v9 = IsFileExt(a4);
  AssociationPath = _GetAssociationPath(v10, v9 != 0, SubKey, v11);
  v13 = AssociationPath;
  if ( AssociationPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)AssociationPath,
      dwOptions);
    return v13;
  }
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  MachineID = GetMachineID((unsigned __int16 **)&pv);
  v13 = MachineID;
  if ( MachineID < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)MachineID,
      dwOptions);
    if ( pv )
      CoTaskMemFree(pv);
    return v13;
  }
  hKey = 0;
  v16 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !a1 )
    a1 = -2147483647;
  if ( RegCreateKeyExW((HKEY)a1, SubKey, 0, 0, 0, 0x2001Bu, 0, v16, 0) == 1021 )
  {
    v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW((HKEY)a1, SubKey, 0, 0, 1u, 0x2001Bu, 0, v17, 0);
    if ( Key )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xF9,
              (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
              (const char *)Key,
              dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( pv )
        CoTaskMemFree(pv);
      return v13;
    }
  }
  v19 = SHRegSetString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", &LocaleName);
  if ( (v19 & 0x1FFF0000) == 0x70000 )
    v19 = (unsigned __int16)v19;
  if ( v19 == 1021 )
  {
    v20 = RegSetVolatileString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", &LocaleName);
    v13 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v20,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( pv )
        CoTaskMemFree(pv);
      return v13;
    }
    v21 = RegSetVolatileString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", a5);
    v13 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v21,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( pv )
        CoTaskMemFree(pv);
      return v13;
    }
  }
  else
  {
    v23 = SHRegSetString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", a5);
    v13 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v23,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( pv )
        CoTaskMemFree(pv);
      return v13;
    }
  }
  v48 = 0;
  SystemTimeFromRegKey = GetSystemTimeFromRegKey(hKey, v22, &v48);
  v13 = SystemTimeFromRegKey;
  if ( SystemTimeFromRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)SystemTimeFromRegKey,
      dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( pv )
      CoTaskMemFree(pv);
    return v13;
  }
  v46 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v46,
      0);
    AssociationsHashVersion = getAssociationsHashVersion();
    v26 = pv;
    v27 = HashAssociationRotation(AssociationsHashVersion, (const unsigned __int16 *)pv, a3, a4, a5, &v48, &v46);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v27,
        dwOptionsb);
      if ( v46 )
        CoTaskMemFree(v46);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( v26 )
        CoTaskMemFree(v26);
      return v28;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v46,
      0);
    v26 = pv;
    v29 = HashAssociationRotation(1u, (const unsigned __int16 *)pv, a3, a4, a5, &v48, &v46);
    v28 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v29,
        dwOptionsb);
      if ( v46 )
        CoTaskMemFree(v46);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( v26 )
        CoTaskMemFree(v26);
      return v28;
    }
  }
  v30 = v46;
  v31 = SHRegSetString(hKey, L"UserChoiceLatest", L"Hash", v46);
  if ( (v31 & 0x1FFF0000) == 0x70000 )
    v31 = (unsigned __int16)v31;
  if ( v31 == 1021 && (v32 = RegSetVolatileString(hKey, L"UserChoiceLatest", L"Hash", v30), v33 = v32, v32 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)v32,
      dwOptionsb);
    if ( v30 )
      CoTaskMemFree(v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v26 )
      CoTaskMemFree(v26);
    return v33;
  }
  else
  {
    wSecond = v48.wSecond;
    wMinute = v48.wMinute;
    wHour = v48.wHour;
    LODWORD(lpdwDisposition) = v48.wDay;
    LODWORD(phkResult) = v48.wDayOfWeek;
    LODWORD(lpSecurityAttributes) = v48.wMonth;
    samDesired[0] = v48.wYear;
    LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_(
      a6,
      L"SetDefault-ProgIdAndHash: UserChoice Association=%ls, ProgId=%ls, U=%ls, T=%02d:%02d:%02d:%02d:%02d:%02d:%02d, H=%ls",
      a4,
      a5,
      v47,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      phkResult,
      lpdwDisposition,
      wHour,
      wMinute,
      wSecond,
      v30);
    if ( v30 )
      CoTaskMemFree(v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v26 )
      CoTaskMemFree(v26);
    return 0;
  }
}

```

## disassembly

```asm
0x1801fc10c  mov     [rsp-8+arg_8], rbx
0x1801fc111  push    rbp
0x1801fc112  push    rsi
0x1801fc113  push    rdi
0x1801fc114  push    r12
0x1801fc116  push    r13
0x1801fc118  push    r14
0x1801fc11a  push    r15
0x1801fc11c  lea     rbp, [rsp-1C0h]
0x1801fc124  sub     rsp, 2C0h
0x1801fc12b  mov     rax, cs:__security_cookie
0x1801fc132  xor     rax, rsp
0x1801fc135  mov     [rbp+1F0h+var_40], rax
0x1801fc13c  mov     r13, r9
0x1801fc13f  mov     rsi, r8
0x1801fc142  mov     [rbp+1F0h+var_268], r8
0x1801fc146  mov     rdi, rcx
0x1801fc149  mov     r12, [rbp+1F0h+arg_20]
0x1801fc150  mov     r9, r12
0x1801fc153  mov     r8, r13
0x1801fc156  lea     rdx, aSetdefaultProg; "SetDefault-ProgIdAndHash: Association=%"...
0x1801fc15d  mov     rcx, [rbp+1F0h+arg_28]
0x1801fc164  call    LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9___; LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_
0x1801fc169  xor     edx, edx; Val
0x1801fc16b  mov     r8d, 208h; Size
0x1801fc171  lea     rcx, [rbp+1F0h+SubKey]; void *
0x1801fc175  call    memset_0
0x1801fc17a  mov     rcx, r13; unsigned __int16 *
0x1801fc17d  call    ?IsFileExt@@YAHPEBG@Z; IsFileExt(ushort const *)
0x1801fc182  xor     r14d, r14d
0x1801fc185  test    eax, eax
0x1801fc187  setnz   dl; bool
0x1801fc18a  lea     r8, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1801fc18e  call    ?_GetAssociationPath@@YAJPEBG_NPEAGI@Z; _GetAssociationPath(ushort const *,bool,ushort *,uint)
0x1801fc193  mov     ebx, eax
0x1801fc195  test    eax, eax
0x1801fc197  jns     short loc_1801FC1BB
0x1801fc199  mov     rcx, [rbp+1F8h]; this
0x1801fc1a0  mov     r9d, eax; char *
0x1801fc1a3  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc1aa  mov     edx, 0D7h; void *
0x1801fc1af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc1b4  mov     eax, ebx
0x1801fc1b6  jmp     loc_1801FC6DC
0x1801fc1bb  mov     [rsp+2F0h+pv], r14
0x1801fc1c0  xor     edx, edx
0x1801fc1c2  lea     rcx, [rsp+2F0h+pv]
0x1801fc1c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801fc1cc  lea     rcx, [rsp+2F0h+pv]; unsigned __int16 **
0x1801fc1d1  call    ?GetMachineID@@YAJPEAPEAG@Z; GetMachineID(ushort * *)
0x1801fc1d6  mov     ebx, eax
0x1801fc1d8  test    eax, eax
0x1801fc1da  jns     short loc_1801FC20B
0x1801fc1dc  mov     rcx, [rbp+1F8h]; this
0x1801fc1e3  mov     r9d, eax; char *
0x1801fc1e6  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc1ed  mov     edx, 0E2h; void *
0x1801fc1f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc1f7  nop
0x1801fc1f8  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc1fd  test    rcx, rcx
0x1801fc200  jz      short loc_1801FC209
0x1801fc202  call    cs:__imp_CoTaskMemFree
0x1801fc208  nop
0x1801fc209  jmp     short loc_1801FC1B4
0x1801fc20b  mov     [rsp+2F0h+hKey], r14
0x1801fc210  lea     rcx, [rsp+2F0h+hKey]
0x1801fc215  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801fc21a  mov     rcx, 0FFFFFFFF80000001h
0x1801fc221  test    rdi, rdi
0x1801fc224  cmovz   rdi, rcx
0x1801fc228  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x1801fc22d  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1801fc232  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1801fc237  mov     ebx, 2001Bh
0x1801fc23c  mov     [rsp+2F0h+samDesired], ebx; samDesired
0x1801fc240  mov     [rsp+2F0h+dwOptions], r14d; int
0x1801fc245  xor     r9d, r9d; lpClass
0x1801fc248  xor     r8d, r8d; Reserved
0x1801fc24b  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1801fc24f  mov     rcx, rdi; hKey
0x1801fc252  call    cs:__imp_RegCreateKeyExW
0x1801fc258  cmp     eax, 3FDh
0x1801fc25d  jnz     short loc_1801FC2D9
0x1801fc25f  lea     rcx, [rsp+2F0h+hKey]
0x1801fc264  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1801fc269  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x1801fc26e  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1801fc273  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1801fc278  mov     [rsp+2F0h+samDesired], ebx; samDesired
0x1801fc27c  mov     [rsp+2F0h+dwOptions], 1; unsigned int
0x1801fc284  xor     r9d, r9d; lpClass
0x1801fc287  xor     r8d, r8d; Reserved
0x1801fc28a  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x1801fc28e  mov     rcx, rdi; hKey
0x1801fc291  call    cs:__imp_RegCreateKeyExW
0x1801fc297  test    eax, eax
0x1801fc299  jz      short loc_1801FC2D9
0x1801fc29b  mov     rcx, [rbp+1F8h]; this
0x1801fc2a2  mov     r9d, eax; char *
0x1801fc2a5  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc2ac  mov     edx, 0F9h; void *
0x1801fc2b1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801fc2b6  mov     ebx, eax
0x1801fc2b8  lea     rcx, [rsp+2F0h+hKey]
0x1801fc2bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc2c2  nop
0x1801fc2c3  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc2c8  test    rcx, rcx
0x1801fc2cb  jz      short loc_1801FC2D4
0x1801fc2cd  call    cs:__imp_CoTaskMemFree
0x1801fc2d3  nop
0x1801fc2d4  jmp     loc_1801FC1B4
0x1801fc2d9  lea     r9, LocaleName; unsigned __int16 *
0x1801fc2e0  lea     rdi, aProgid; "ProgId"
0x1801fc2e7  mov     r8, rdi; unsigned __int16 *
0x1801fc2ea  lea     r15, aUserchoicelate_0; "UserChoiceLatest\\ProgId"
0x1801fc2f1  mov     rdx, r15; unsigned __int16 *
0x1801fc2f4  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1801fc2f9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801fc2fe  mov     ecx, eax
0x1801fc300  and     ecx, 1FFF0000h
0x1801fc306  cmp     ecx, 70000h
0x1801fc30c  jnz     short loc_1801FC311
0x1801fc30e  movzx   eax, ax
0x1801fc311  mov     r8, rdi; unsigned __int16 *
0x1801fc314  mov     rdx, r15; unsigned __int16 *
0x1801fc317  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1801fc31c  cmp     eax, 3FDh
0x1801fc321  jnz     loc_1801FC3D0
0x1801fc327  lea     r9, LocaleName; unsigned __int16 *
0x1801fc32e  call    ?RegSetVolatileString@@YAJPEAUHKEY__@@PEBG11@Z; RegSetVolatileString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801fc333  mov     ebx, eax
0x1801fc335  test    eax, eax
0x1801fc337  jns     short loc_1801FC376
0x1801fc339  mov     rcx, [rbp+1F8h]; this
0x1801fc340  mov     r9d, eax; char *
0x1801fc343  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc34a  mov     edx, 100h; void *
0x1801fc34f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc354  nop
0x1801fc355  lea     rcx, [rsp+2F0h+hKey]
0x1801fc35a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc35f  nop
0x1801fc360  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc365  test    rcx, rcx
0x1801fc368  jz      short loc_1801FC371
0x1801fc36a  call    cs:__imp_CoTaskMemFree
0x1801fc370  nop
0x1801fc371  jmp     loc_1801FC1B4
0x1801fc376  mov     r9, r12; unsigned __int16 *
0x1801fc379  mov     r8, rdi; unsigned __int16 *
0x1801fc37c  mov     rdx, r15; unsigned __int16 *
0x1801fc37f  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1801fc384  call    ?RegSetVolatileString@@YAJPEAUHKEY__@@PEBG11@Z; RegSetVolatileString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801fc389  mov     ebx, eax
0x1801fc38b  test    eax, eax
0x1801fc38d  jns     loc_1801FC41B
0x1801fc393  mov     rcx, [rbp+1F8h]; this
0x1801fc39a  mov     r9d, eax; char *
0x1801fc39d  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc3a4  mov     edx, 101h; void *
0x1801fc3a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc3ae  nop
0x1801fc3af  lea     rcx, [rsp+2F0h+hKey]
0x1801fc3b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc3b9  nop
0x1801fc3ba  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc3bf  test    rcx, rcx
0x1801fc3c2  jz      short loc_1801FC3CB
0x1801fc3c4  call    cs:__imp_CoTaskMemFree
0x1801fc3ca  nop
0x1801fc3cb  jmp     loc_1801FC1B4
0x1801fc3d0  mov     r9, r12; unsigned __int16 *
0x1801fc3d3  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1801fc3d8  mov     ebx, eax
0x1801fc3da  test    eax, eax
0x1801fc3dc  jns     short loc_1801FC41B
0x1801fc3de  mov     rcx, [rbp+1F8h]; this
0x1801fc3e5  mov     r9d, eax; char *
0x1801fc3e8  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc3ef  mov     edx, 105h; void *
0x1801fc3f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc3f9  nop
0x1801fc3fa  lea     rcx, [rsp+2F0h+hKey]
0x1801fc3ff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc404  nop
0x1801fc405  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc40a  test    rcx, rcx
0x1801fc40d  jz      short loc_1801FC416
0x1801fc40f  call    cs:__imp_CoTaskMemFree
0x1801fc415  nop
0x1801fc416  jmp     loc_1801FC1B4
0x1801fc41b  xorps   xmm0, xmm0
0x1801fc41e  movups  xmmword ptr [rbp+1F0h+var_260.wYear], xmm0
0x1801fc422  lea     r8, [rbp+1F0h+var_260]; struct _SYSTEMTIME *
0x1801fc426  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1801fc42b  call    ?GetSystemTimeFromRegKey@@YAJPEAUHKEY__@@PEBGPEAU_SYSTEMTIME@@@Z; GetSystemTimeFromRegKey(HKEY__ *,ushort const *,_SYSTEMTIME *)
0x1801fc430  mov     ebx, eax
0x1801fc432  test    eax, eax
0x1801fc434  jns     short loc_1801FC473
0x1801fc436  mov     rcx, [rbp+1F8h]; this
0x1801fc43d  mov     r9d, eax; char *
0x1801fc440  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc447  mov     edx, 10Ah; void *
0x1801fc44c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc451  nop
0x1801fc452  lea     rcx, [rsp+2F0h+hKey]
0x1801fc457  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc45c  nop
0x1801fc45d  mov     rcx, [rsp+2F0h+pv]; pv
0x1801fc462  test    rcx, rcx
0x1801fc465  jz      short loc_1801FC46E
0x1801fc467  call    cs:__imp_CoTaskMemFree
0x1801fc46d  nop
0x1801fc46e  jmp     loc_1801FC1B4
0x1801fc473  mov     [rbp+1F0h+var_270], r14
0x1801fc477  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2> `wil::Feature<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::GetImpl(void)'::`2'::impl
0x1801fc47e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::__private_IsEnabled(void)
0x1801fc483  xor     edx, edx
0x1801fc485  lea     rcx, [rbp+1F0h+var_270]
0x1801fc489  test    al, al
0x1801fc48b  jz      loc_1801FC51E
0x1801fc491  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801fc496  call    ?getAssociationsHashVersion@@YAKXZ; getAssociationsHashVersion(void)
0x1801fc49b  lea     rcx, [rbp+1F0h+var_270]
0x1801fc49f  mov     [rsp+2F0h+lpSecurityAttributes], rcx; unsigned __int16 **
0x1801fc4a4  lea     rcx, [rbp+1F0h+var_260]
0x1801fc4a8  mov     qword ptr [rsp+2F0h+samDesired], rcx; struct _SYSTEMTIME *
0x1801fc4ad  mov     qword ptr [rsp+2F0h+dwOptions], r12; int
0x1801fc4b2  mov     r9, r13; unsigned __int16 *
0x1801fc4b5  mov     r8, rsi; unsigned __int16 *
0x1801fc4b8  mov     rbx, [rsp+2F0h+pv]
0x1801fc4bd  mov     rdx, rbx; unsigned __int16 *
0x1801fc4c0  mov     ecx, eax; unsigned int
0x1801fc4c2  call    ?HashAssociationRotation@@YAJIPEBG000AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociationRotation(uint,ushort const *,ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x1801fc4c7  mov     edi, eax
0x1801fc4c9  test    eax, eax
0x1801fc4cb  jns     loc_1801FC5A3
0x1801fc4d1  mov     rcx, [rbp+1F8h]; this
0x1801fc4d8  mov     r9d, eax; char *
0x1801fc4db  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc4e2  mov     edx, 10Fh; void *
0x1801fc4e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc4ec  nop
0x1801fc4ed  mov     rcx, [rbp+1F0h+var_270]; pv
0x1801fc4f1  test    rcx, rcx
0x1801fc4f4  jz      short loc_1801FC4FD
0x1801fc4f6  call    cs:__imp_CoTaskMemFree
0x1801fc4fc  nop
0x1801fc4fd  lea     rcx, [rsp+2F0h+hKey]
0x1801fc502  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc507  nop
0x1801fc508  test    rbx, rbx
0x1801fc50b  jz      short loc_1801FC517
0x1801fc50d  mov     rcx, rbx; pv
0x1801fc510  call    cs:__imp_CoTaskMemFree
0x1801fc516  nop
0x1801fc517  mov     eax, edi
0x1801fc519  jmp     loc_1801FC6DC
0x1801fc51e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801fc523  lea     rax, [rbp+1F0h+var_270]
0x1801fc527  mov     [rsp+2F0h+lpSecurityAttributes], rax; unsigned __int16 **
0x1801fc52c  lea     rax, [rbp+1F0h+var_260]
0x1801fc530  mov     qword ptr [rsp+2F0h+samDesired], rax; struct _SYSTEMTIME *
0x1801fc535  mov     qword ptr [rsp+2F0h+dwOptions], r12; int
0x1801fc53a  mov     r9, r13; unsigned __int16 *
0x1801fc53d  mov     r8, rsi; unsigned __int16 *
0x1801fc540  mov     rbx, [rsp+2F0h+pv]
0x1801fc545  mov     rdx, rbx; unsigned __int16 *
0x1801fc548  mov     ecx, 1; unsigned int
0x1801fc54d  call    ?HashAssociationRotation@@YAJIPEBG000AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociationRotation(uint,ushort const *,ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x1801fc552  mov     edi, eax
0x1801fc554  test    eax, eax
0x1801fc556  jns     short loc_1801FC5A3
0x1801fc558  mov     rcx, [rbp+1F8h]; this
0x1801fc55f  mov     r9d, eax; char *
0x1801fc562  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1801fc569  mov     edx, 113h; void *
0x1801fc56e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fc573  nop
0x1801fc574  mov     rcx, [rbp+1F0h+var_270]; pv
0x1801fc578  test    rcx, rcx
0x1801fc57b  jz      short loc_1801FC584
0x1801fc57d  call    cs:__imp_CoTaskMemFree
0x1801fc583  nop
0x1801fc584  lea     rcx, [rsp+2F0h+hKey]
0x1801fc589  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801fc58e  nop
0x1801fc58f  test    rbx, rbx
0x1801fc592  jz      short loc_1801FC59E
0x1801fc594  mov     rcx, rbx; pv
0x1801fc597  call    cs:__imp_CoTaskMemFree
0x1801fc59d  nop
0x1801fc59e  jmp     loc_1801FC517
0x1801fc5a3  mov     rdi, [rbp+1F0h+var_270]
0x1801fc5a7  mov     r9, rdi; unsigned __int16 *
0x1801fc5aa  lea     r8, aHash; "Hash"
0x1801fc5b1  lea     rdx, aUserchoicelate; "UserChoiceLatest"
0x1801fc5b8  mov     rcx, [rsp+2F0h+hKey]; HKEY
  ... truncated ...
```
