# CConstraintModel::Initialize(void)

- ea: `0x1800b5ee0`
- end: `0x1800b6893`
- name: `?Initialize@CConstraintModel@@QEAAJXZ`
- size: `2483`
- prototype: `__int64 __fastcall(CConstraintModel *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801040a8`

## callees

- `0x180016540`
- `0x180016870`
- `0x1800ab580`
- `0x1800b196c`
- `0x1800b30ac`
- `0x1800b5ee0`
- `0x1800b689c`
- `0x1800b6968`
- `0x1800b69c4`
- `0x1800b6af4`
- `0x1800b6bc0`
- `0x1800befa8`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x180105334`
- `0x180159628`
- `0x18015998c`
- `0x18015a1a0`
- `0x18015a2d4`
- `0x18015a368`
- `0x18015a400`
- `0x18015b434`
- `0x18015b4d0`
- `0x18015b80c`
- `0x18015b874`
- `0x18015b978`
- `0x18015ba40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b5f69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b5f69`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b604a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b6368`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b604a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b6368`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5fae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b62d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5fae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b62d6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6093`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b63b1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b6093`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b63b1`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800b629f`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800b629f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800b626f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800b626f`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800b621e`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800b621e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800b61f1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800b61f1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800b6539`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800b6539`

## string_xrefs

- `0x1800b661f`: `Parsing XML %s, %s`
- `0x1800b668f`: `Parsing XML %s failed`
- `0x1800b62cc`: `SYSTEM\MultiMedia\DeviceCapability\ResourceSettings\XMLConfig`
- `0x1800b5fa4`: `System\MultiMedia\DeviceCapability\ResourceSettings\XMLConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall CConstraintModel::Initialize(CConstraintModel *this)
{
  CConstraintModel *v1; // r15
  DWORD v2; // esi
  DWORD i; // edi
  BYTE *v4; // rcx
  WCHAR *v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rax
  bool v8; // bl
  _QWORD *v9; // rax
  __int64 v10; // r8
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 DeviceInfoList; // rax
  __int64 v15; // rdi
  unsigned int v16; // r14d
  HKEY v17; // rax
  BYTE *v18; // rcx
  WCHAR *p_Dst; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rax
  bool v22; // bl
  _QWORD *v23; // rax
  __int64 v24; // r8
  int v25; // edi
  _QWORD *v26; // rbx
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  const WCHAR **v30; // rsi
  const WCHAR *v31; // r8
  _QWORD *v32; // rdx
  const WCHAR *v33; // rdx
  int v34; // ecx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 **v37; // rcx
  __int64 k; // rax
  __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // r14
  unsigned __int64 v44; // rsi
  __int64 v45; // rdx
  __int64 v46; // r8
  unsigned __int64 j; // rcx
  __int64 *m; // rcx
  DWORD Type; // [rsp+40h] [rbp-7E8h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-7E4h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-7E0h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-7D8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-7D0h] BYREF
  int pvData; // [rsp+5Ch] [rbp-7CCh] BYREF
  __int128 v56; // [rsp+60h] [rbp-7C8h] BYREF
  CConstraintModel *v57; // [rsp+70h] [rbp-7B8h]
  HKEY v58; // [rsp+78h] [rbp-7B0h] BYREF
  _BYTE v59[16]; // [rsp+80h] [rbp-7A8h] BYREF
  _BYTE v60[80]; // [rsp+90h] [rbp-798h] BYREF
  _BYTE v61[8]; // [rsp+E0h] [rbp-748h] BYREF
  __int64 v62; // [rsp+E8h] [rbp-740h]
  __int64 v63; // [rsp+130h] [rbp-6F8h] BYREF
  unsigned __int64 v64; // [rsp+138h] [rbp-6F0h]
  __int64 v65; // [rsp+140h] [rbp-6E8h]
  int v66; // [rsp+148h] [rbp-6E0h]
  __int128 v67; // [rsp+150h] [rbp-6D8h] BYREF
  _OWORD v68[2]; // [rsp+160h] [rbp-6C8h] BYREF
  BYTE v69[32]; // [rsp+180h] [rbp-6A8h] BYREF
  BYTE Data[2]; // [rsp+1A0h] [rbp-688h] BYREF
  _BYTE v71[526]; // [rsp+1A2h] [rbp-686h] BYREF
  WCHAR ValueName; // [rsp+3B0h] [rbp-478h] BYREF
  _BYTE v73[526]; // [rsp+3B2h] [rbp-476h] BYREF
  WCHAR Dst; // [rsp+5C0h] [rbp-268h] BYREF
  _BYTE v75[526]; // [rsp+5C2h] [rbp-266h] BYREF

  v1 = this;
  v57 = this;
  v56 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(&v56);
  v2 = 0;
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
         L"ConstraintModelTest",
         0x18u,
         0,
         &pvData,
         &pcbData)
    || pcbData != 4
    || !pvData )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v15 = DeviceInfoList;
    if ( DeviceInfoList == -1 )
      goto LABEL_44;
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_MEDIA, 0, 0, 0, 0) )
      goto LABEL_43;
    v16 = 0;
    v67 = 0;
    memset(v68, 0, sizeof(v68));
    LODWORD(v67) = 48;
LABEL_24:
    if ( !(unsigned int)DevObjEnumDeviceInfo(v15, v16, &v67) )
    {
      v1 = v57;
LABEL_43:
      DevObjDestroyDeviceInfoList(v15);
      goto LABEL_44;
    }
    v17 = (HKEY)DevObjOpenDevRegKey(v15, &v67, 1);
    v58 = v17;
    if ( v17 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      goto LABEL_41;
    phkResult = 0;
    if ( RegOpenKeyExW(v17, L"SYSTEM\\MultiMedia\\DeviceCapability\\ResourceSettings\\XMLConfig", 0, 1u, &phkResult) )
      goto LABEL_40;
    while ( 1 )
    {
      ValueName = 0;
      memset_0(v73, 0, 0x206u);
      *(_WORD *)Data = 0;
      memset_0(v71, 0, 0x206u);
      cchValueName = 260;
      cbData = 520;
      Type = 0;
      if ( RegEnumValueW(phkResult, v2, &ValueName, &cchValueName, 0, &Type, Data, &cbData) )
      {
        v2 = 0;
LABEL_40:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_41:
        ++v16;
        v67 = 0;
        memset(v68, 0, sizeof(v68));
        LODWORD(v67) = 48;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
        goto LABEL_24;
      }
      if ( Type == 2 )
      {
        Dst = 0;
        memset_0(v75, 0, 0x206u);
        if ( ExpandEnvironmentStringsW((LPCWSTR)Data, &Dst, 0x104u) )
        {
          v18 = Data;
          p_Dst = &Dst;
          v20 = 4;
          do
          {
            *(_OWORD *)v18 = *(_OWORD *)p_Dst;
            *((_OWORD *)v18 + 1) = *((_OWORD *)p_Dst + 1);
            *((_OWORD *)v18 + 2) = *((_OWORD *)p_Dst + 2);
            *((_OWORD *)v18 + 3) = *((_OWORD *)p_Dst + 3);
            *((_OWORD *)v18 + 4) = *((_OWORD *)p_Dst + 4);
            *((_OWORD *)v18 + 5) = *((_OWORD *)p_Dst + 5);
            *((_OWORD *)v18 + 6) = *((_OWORD *)p_Dst + 6);
            *((_OWORD *)v18 + 7) = *((_OWORD *)p_Dst + 7);
            v18 += 128;
            p_Dst += 64;
            --v20;
          }
          while ( v20 );
          *(_QWORD *)v18 = *(_QWORD *)p_Dst;
        }
      }
      else if ( Type != 1 )
      {
        goto LABEL_38;
      }
      std::wstring::wstring(v69, &ValueName);
      v21 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                        &v56,
                        v59,
                        v69);
      v22 = *v21 == (_QWORD)v56;
      std::wstring::~wstring(v69);
      if ( v22 )
      {
        std::wstring::wstring(v69, &ValueName);
        v23 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(&v56, &v63, v69);
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&Data[2 * v24] );
        std::wstring::_Assign<unsigned short>(*v23 + 64LL, Data);
        std::wstring::~wstring(v69);
      }
LABEL_38:
      ++v2;
    }
  }
  phkResult = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\MultiMedia\\DeviceCapability\\ResourceSettings\\XMLConfig",
         0,
         0x20019u,
         &phkResult) )
  {
    goto LABEL_20;
  }
  for ( i = 0; ; ++i )
  {
    ValueName = 0;
    memset_0(v73, 0, 0x206u);
    *(_WORD *)Data = 0;
    memset_0(v71, 0, 0x206u);
    cchValueName = 260;
    cbData = 520;
    Type = 0;
    if ( RegEnumValueW(phkResult, i, &ValueName, &cchValueName, 0, &Type, Data, &cbData) )
      break;
    if ( Type == 2 )
    {
      Dst = 0;
      memset_0(v75, 0, 0x206u);
      if ( ExpandEnvironmentStringsW((LPCWSTR)Data, &Dst, 0x104u) )
      {
        v4 = Data;
        v5 = &Dst;
        v6 = 4;
        do
        {
          *(_OWORD *)v4 = *(_OWORD *)v5;
          *((_OWORD *)v4 + 1) = *((_OWORD *)v5 + 1);
          *((_OWORD *)v4 + 2) = *((_OWORD *)v5 + 2);
          *((_OWORD *)v4 + 3) = *((_OWORD *)v5 + 3);
          *((_OWORD *)v4 + 4) = *((_OWORD *)v5 + 4);
          *((_OWORD *)v4 + 5) = *((_OWORD *)v5 + 5);
          *((_OWORD *)v4 + 6) = *((_OWORD *)v5 + 6);
          *((_OWORD *)v4 + 7) = *((_OWORD *)v5 + 7);
          v4 += 128;
          v5 += 64;
          --v6;
        }
        while ( v6 );
        *(_QWORD *)v4 = *(_QWORD *)v5;
      }
    }
    else if ( Type != 1 || !cchValueName )
    {
      continue;
    }
    std::wstring::wstring(&v63, &ValueName);
    v7 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                     &v56,
                     &v58,
                     &v63);
    v8 = *v7 == (_QWORD)v56;
    std::wstring::~wstring(&v63);
    if ( v8 )
    {
      std::wstring::wstring(&v63, &ValueName);
      v9 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(&v56, v59, &v63);
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&Data[2 * v10] );
      std::wstring::_Assign<unsigned short>(*v9 + 64LL, Data);
      std::wstring::~wstring(&v63);
    }
  }
  v1 = v57;
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_44:
  v25 = 0;
  v26 = *(_QWORD **)v56;
  while ( 2 )
  {
    if ( v25 >= 0 && v26 != (_QWORD *)v56 )
    {
      cbData = 31;
      ATL::CAtlMap<ResourceConsumer *,ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *,ResourceConsumerTraits,ATL::CElementTraits<ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *>>::CAtlMap<ResourceConsumer *,ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *,ResourceConsumerTraits,ATL::CElementTraits<ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *>>(
        (unsigned int)v61,
        v11,
        v12,
        v13,
        LODWORD(FLOAT_2_25));
      v67 = 0;
      memset(v68, 0, 24);
      DWORD2(v68[1]) = 10;
      ATL::CAtlMap<ResourceConsumer *,ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *,ResourceConsumerTraits,ATL::CElementTraits<ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *>>::CAtlMap<ResourceConsumer *,ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *,ResourceConsumerTraits,ATL::CElementTraits<ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *>>(
        (unsigned int)v60,
        v27,
        v28,
        v29,
        LODWORD(FLOAT_2_25));
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v30 = (const WCHAR **)(v26 + 8);
      if ( v26[11] <= 7u )
        v31 = (const WCHAR *)(v26 + 8);
      else
        v31 = *v30;
      v32 = v26 + 4;
      if ( v26[7] > 7u )
        v32 = (_QWORD *)*v32;
      LogOutput(L"Parsing XML %s, %s", v32, v31);
      if ( v26[11] <= 7u )
        v33 = (const WCHAR *)(v26 + 8);
      else
        v33 = *v30;
      if ( (int)CConstraintModelXMLParser::GetConstraintsFromXML(
                  (CConstraintModel *)((char *)v1 + 232),
                  v33,
                  (__int64)&v67,
                  (__int64)v60,
                  (__int64)&v63) < 0 )
      {
        if ( v26[11] > 7u )
          v30 = (const WCHAR **)*v30;
        LogError(L"Parsing XML %s failed", v30);
        goto LABEL_59;
      }
      if ( (int)CConstraintModel::VerifyNoRepeatedResourcesOrConsumers(
                  v34,
                  (int)v1 + 8,
                  (unsigned int)v61,
                  (int)v1 + 128,
                  (__int64)v60) < 0 )
        goto LABEL_59;
      v40 = v62 + *((_QWORD *)v1 + 2);
      if ( v40 > 0xF )
        LogError(L"Number of resource types is %d which is larger than max %d", v40, 15);
      v25 = CConstraintModel::CopyResourceIDMap(v39, v61, (char *)v1 + 8);
      if ( v25 < 0
        || (v25 = CConstraintModel::CopyResourceLimits(v41, &v67, (char *)v1 + 80), v25 < 0)
        || (v25 = CConstraintModel::CopyResourceConsumptionMap(v42, v60, (char *)v1 + 128), v25 < 0) )
      {
LABEL_59:
        LogOutput(L"Cleaning resource consumption information due to unrecoverable error");
        CConstraintModel::CleanResourceConsumptionMap(v35, v60);
        CConstraintModel::CleanResourceExclusiveEndpoint(v36, &v63);
      }
      else
      {
        v43 = *((_QWORD *)v1 + 26);
        v44 = v64;
        if ( !(unsigned __int8)ATL::CAtlArray<ATL::CAtlArray<EndpointInfo *,ATL::CElementTraits<EndpointInfo *>> *,ATL::CElementTraits<ATL::CAtlArray<EndpointInfo *,ATL::CElementTraits<EndpointInfo *>> *>>::SetCount(
                                 (char *)v1 + 200,
                                 v64 + v43) )
          ATL::AtlThrowImpl(-2147024882);
        v45 = v63;
        v46 = *((_QWORD *)v1 + 25) + 8 * v43;
        for ( j = 0; j < v44; ++j )
          *(_QWORD *)(v46 + 8 * j) = *(_QWORD *)(v45 + 8 * j);
        v25 = 0;
      }
      ATL::CAtlArray<EndpointInfo *,ATL::CElementTraits<EndpointInfo *>>::~CAtlArray<EndpointInfo *,ATL::CElementTraits<EndpointInfo *>>(&v63);
      ATL::CAtlMap<ResourceConsumer *,ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *,ResourceConsumerTraits,ATL::CElementTraits<ATL::CAtlList<_ResourceInfo,ResourceInfoTraits> *>>::RemoveAll(v60);
      ATL::CAtlList<_ResourceInfo,ResourceInfoTraits>::RemoveAll(&v67);
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ResourceValue,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ResourceValue>>::RemoveAll(v61);
      v37 = (__int64 **)v26[2];
      if ( *((_BYTE *)v37 + 25) )
      {
        for ( k = v26[1]; !*(_BYTE *)(k + 25) && v26 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
          v26 = (_QWORD *)k;
        v26 = (_QWORD *)k;
      }
      else
      {
        v26 = (_QWORD *)v26[2];
        for ( m = *v37; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v26 = m;
      }
      continue;
    }
    break;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v56);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800b5ee0  mov     rax, rsp
0x1800b5ee3  push    rbx
0x1800b5ee4  push    rsi
0x1800b5ee5  push    rdi
0x1800b5ee6  push    r12
0x1800b5ee8  push    r14
0x1800b5eea  push    r15
0x1800b5eec  sub     rsp, 7F8h
0x1800b5ef3  movaps  xmmword ptr [rax-48h], xmm6
0x1800b5ef7  mov     rax, cs:__security_cookie
0x1800b5efe  xor     rax, rsp
0x1800b5f01  mov     [rsp+828h+var_58], rax
0x1800b5f09  mov     r15, rcx
0x1800b5f0c  mov     [rsp+828h+var_7B8], rcx
0x1800b5f11  xorps   xmm0, xmm0
0x1800b5f14  movdqu  [rsp+828h+var_7C8], xmm0
0x1800b5f1a  lea     rcx, [rsp+828h+var_7C8]
0x1800b5f1f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800b5f24  nop
0x1800b5f25  xor     esi, esi
0x1800b5f27  mov     [rsp+828h+var_7CC], esi
0x1800b5f2b  lea     r14d, [rsi+4]
0x1800b5f2f  mov     [rsp+828h+var_7D0], r14d
0x1800b5f34  lea     rax, [rsp+828h+var_7D0]
0x1800b5f39  mov     [rsp+828h+pcbData], rax; pcbData
0x1800b5f3e  lea     rax, [rsp+828h+var_7CC]
0x1800b5f43  mov     [rsp+828h+pvData], rax; pvData
0x1800b5f48  mov     [rsp+828h+pdwType], rsi; pdwType
0x1800b5f4d  lea     r9d, [rsi+18h]; dwFlags
0x1800b5f51  lea     r8, aConstraintmode; "ConstraintModelTest"
0x1800b5f58  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b5f5f  mov     rbx, 0FFFFFFFF80000002h
0x1800b5f66  mov     rcx, rbx; hkey
0x1800b5f69  call    cs:__imp_RegGetValueW
0x1800b5f6f  test    eax, eax
0x1800b5f71  jnz     loc_1800B61E2
0x1800b5f77  cmp     [rsp+828h+var_7D0], r14d
0x1800b5f7c  jnz     loc_1800B61E2
0x1800b5f82  cmp     [rsp+828h+var_7CC], esi
0x1800b5f86  jz      loc_1800B61E2
0x1800b5f8c  mov     [rsp+828h+phkResult], rsi
0x1800b5f91  lea     rax, [rsp+828h+phkResult]
0x1800b5f96  mov     [rsp+828h+pdwType], rax; phkResult
0x1800b5f9b  mov     r9d, 20019h; samDesired
0x1800b5fa1  xor     r8d, r8d; ulOptions
0x1800b5fa4  lea     rdx, aSystemMultimed; "System\\MultiMedia\\DeviceCapability\\R"...
0x1800b5fab  mov     rcx, rbx; hKey
0x1800b5fae  call    cs:__imp_RegOpenKeyExW
0x1800b5fb4  test    eax, eax
0x1800b5fb6  jnz     loc_1800B61D3
0x1800b5fbc  mov     edi, esi
0x1800b5fbe  mov     r15d, 206h
0x1800b5fc4  lea     r12d, [r14+7Ch]
0x1800b5fc8  mov     [rsp+828h+ValueName], si
0x1800b5fd0  mov     r8, r15; Size
0x1800b5fd3  xor     edx, edx; Val
0x1800b5fd5  lea     rcx, [rsp+828h+var_476]; void *
0x1800b5fdd  call    memset_0
0x1800b5fe2  mov     word ptr [rsp+828h+Data], si
0x1800b5fea  mov     r8, r15; Size
0x1800b5fed  xor     edx, edx; Val
0x1800b5fef  lea     rcx, [rsp+828h+var_686]; void *
0x1800b5ff7  call    memset_0
0x1800b5ffc  mov     [rsp+828h+cchValueName], 104h
0x1800b6004  mov     [rsp+828h+cbData], 208h
0x1800b600c  mov     [rsp+828h+Type], esi
0x1800b6010  lea     rax, [rsp+828h+cbData]
0x1800b6015  mov     [rsp+828h+lpcbData], rax; lpcbData
0x1800b601a  lea     rax, [rsp+828h+Data]
0x1800b6022  mov     [rsp+828h+pcbData], rax; lpData
0x1800b6027  lea     rax, [rsp+828h+Type]
0x1800b602c  mov     [rsp+828h+pvData], rax; lpType
0x1800b6031  mov     [rsp+828h+pdwType], rsi; lpReserved
0x1800b6036  lea     r9, [rsp+828h+cchValueName]; lpcchValueName
0x1800b603b  lea     r8, [rsp+828h+ValueName]; lpValueName
0x1800b6043  mov     edx, edi; dwIndex
0x1800b6045  mov     rcx, [rsp+828h+phkResult]; hKey
0x1800b604a  call    cs:__imp_RegEnumValueW
0x1800b6050  test    eax, eax
0x1800b6052  jnz     loc_1800B61CE
0x1800b6058  cmp     [rsp+828h+Type], 2
0x1800b605d  jnz     loc_1800B6102
0x1800b6063  mov     [rsp+828h+Dst], si
0x1800b606b  mov     r8, r15; Size
0x1800b606e  xor     edx, edx; Val
0x1800b6070  lea     rcx, [rsp+828h+var_266]; void *
0x1800b6078  call    memset_0
0x1800b607d  mov     r8d, 104h; nSize
0x1800b6083  lea     rdx, [rsp+828h+Dst]; lpDst
0x1800b608b  lea     rcx, [rsp+828h+Data]; lpSrc
0x1800b6093  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b6099  test    eax, eax
0x1800b609b  jz      short loc_1800B6117
0x1800b609d  lea     rcx, [rsp+828h+Data]
0x1800b60a5  lea     rax, [rsp+828h+Dst]
0x1800b60ad  mov     rdx, r14
0x1800b60b0  movups  xmm0, xmmword ptr [rax]
0x1800b60b3  movups  xmmword ptr [rcx], xmm0
0x1800b60b6  movups  xmm1, xmmword ptr [rax+10h]
0x1800b60ba  movups  xmmword ptr [rcx+10h], xmm1
0x1800b60be  movups  xmm0, xmmword ptr [rax+20h]
0x1800b60c2  movups  xmmword ptr [rcx+20h], xmm0
0x1800b60c6  movups  xmm1, xmmword ptr [rax+30h]
0x1800b60ca  movups  xmmword ptr [rcx+30h], xmm1
0x1800b60ce  movups  xmm0, xmmword ptr [rax+40h]
0x1800b60d2  movups  xmmword ptr [rcx+40h], xmm0
0x1800b60d6  movups  xmm1, xmmword ptr [rax+50h]
0x1800b60da  movups  xmmword ptr [rcx+50h], xmm1
0x1800b60de  movups  xmm0, xmmword ptr [rax+60h]
0x1800b60e2  movups  xmmword ptr [rcx+60h], xmm0
0x1800b60e6  movups  xmm1, xmmword ptr [rax+70h]
0x1800b60ea  movups  xmmword ptr [rcx+70h], xmm1
0x1800b60ee  add     rcx, r12
0x1800b60f1  add     rax, r12
0x1800b60f4  sub     rdx, 1
0x1800b60f8  jnz     short loc_1800B60B0
0x1800b60fa  mov     rax, [rax]
0x1800b60fd  mov     [rcx], rax
0x1800b6100  jmp     short loc_1800B6117
0x1800b6102  cmp     [rsp+828h+Type], 1
0x1800b6107  jnz     loc_1800B61C7
0x1800b610d  cmp     [rsp+828h+cchValueName], esi
0x1800b6111  jz      loc_1800B61C7
0x1800b6117  lea     rdx, [rsp+828h+ValueName]
0x1800b611f  lea     rcx, [rsp+828h+var_6F8]
0x1800b6127  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b612c  lea     r8, [rsp+828h+var_6F8]
0x1800b6134  lea     rdx, [rsp+828h+var_7B0]
0x1800b6139  lea     rcx, [rsp+828h+var_7C8]
0x1800b613e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800b6143  mov     rcx, qword ptr [rsp+828h+var_7C8]
0x1800b6148  cmp     [rax], rcx
0x1800b614b  setz    bl
0x1800b614e  lea     rcx, [rsp+828h+var_6F8]; void *
0x1800b6156  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b615b  test    bl, bl
0x1800b615d  jz      short loc_1800B61C7
0x1800b615f  lea     rdx, [rsp+828h+ValueName]
0x1800b6167  lea     rcx, [rsp+828h+var_6F8]
0x1800b616f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6174  nop
0x1800b6175  lea     r8, [rsp+828h+var_6F8]
0x1800b617d  lea     rdx, [rsp+828h+var_7A8]
0x1800b6185  lea     rcx, [rsp+828h+var_7C8]
0x1800b618a  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800b618f  lea     rcx, [rsp+828h+Data]
0x1800b6197  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b619b  inc     r8
0x1800b619e  cmp     [rcx+r8*2], si
0x1800b61a3  jnz     short loc_1800B619B
0x1800b61a5  mov     rcx, [rax]
0x1800b61a8  add     rcx, 40h ; '@'
0x1800b61ac  lea     rdx, [rsp+828h+Data]
0x1800b61b4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b61b9  nop
0x1800b61ba  lea     rcx, [rsp+828h+var_6F8]; void *
0x1800b61c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b61c7  inc     edi
0x1800b61c9  jmp     loc_1800B5FC8
0x1800b61ce  mov     r15, [rsp+828h+var_7B8]
0x1800b61d3  lea     rcx, [rsp+828h+phkResult]
0x1800b61d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b61dd  jmp     loc_1800B653F
0x1800b61e2  mov     [rsp+828h+pdwType], rsi
0x1800b61e7  xor     r9d, r9d
0x1800b61ea  xor     r8d, r8d
0x1800b61ed  xor     edx, edx
0x1800b61ef  xor     ecx, ecx
0x1800b61f1  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800b61f7  mov     rdi, rax
0x1800b61fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b61fe  jz      loc_1800B653F
0x1800b6204  mov     [rsp+828h+pvData], rsi
0x1800b6209  mov     [rsp+828h+pdwType], rsi
0x1800b620e  xor     r9d, r9d
0x1800b6211  xor     r8d, r8d
0x1800b6214  lea     rdx, GUID_DEVCLASS_MEDIA
0x1800b621b  mov     rcx, rax
0x1800b621e  call    cs:__imp_DevObjGetClassDevs
0x1800b6224  test    eax, eax
0x1800b6226  jz      loc_1800B6536
0x1800b622c  mov     r14d, esi
0x1800b622f  xorps   xmm0, xmm0
0x1800b6232  movups  [rsp+828h+var_6D8], xmm0
0x1800b623a  movups  [rsp+828h+var_6C8], xmm0
0x1800b6242  movups  [rsp+828h+var_6B8], xmm0
0x1800b624a  mov     dword ptr [rsp+828h+var_6D8], 30h ; '0'
0x1800b6255  mov     r15d, 206h
0x1800b625b  mov     r12d, 80h
0x1800b6261  lea     r8, [rsp+828h+var_6D8]
0x1800b6269  mov     edx, r14d
0x1800b626c  mov     rcx, rdi
0x1800b626f  call    cs:__imp_DevObjEnumDeviceInfo
0x1800b6275  test    eax, eax
0x1800b6277  jz      loc_1800B6531
0x1800b627d  mov     dword ptr [rsp+828h+pvData], 20019h
0x1800b6285  mov     dword ptr [rsp+828h+pdwType], 2
0x1800b628d  xor     r9d, r9d
0x1800b6290  lea     r8d, [r9+1]
0x1800b6294  lea     rdx, [rsp+828h+var_6D8]
0x1800b629c  mov     rcx, rdi
0x1800b629f  call    cs:__imp_DevObjOpenDevRegKey
0x1800b62a5  mov     [rsp+828h+var_7B0], rax
0x1800b62aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b62ae  jz      loc_1800B64F9
0x1800b62b4  mov     [rsp+828h+phkResult], rsi
0x1800b62b9  lea     rcx, [rsp+828h+phkResult]
0x1800b62be  mov     [rsp+828h+pdwType], rcx; phkResult
0x1800b62c3  mov     r9d, 1; samDesired
0x1800b62c9  xor     r8d, r8d; ulOptions
0x1800b62cc  lea     rdx, aSystemMultimed_0; "SYSTEM\\MultiMedia\\DeviceCapability\\R"...
0x1800b62d3  mov     rcx, rax; hKey
0x1800b62d6  call    cs:__imp_RegOpenKeyExW
0x1800b62dc  test    eax, eax
0x1800b62de  jnz     loc_1800B64EF
0x1800b62e4  xor     ebx, ebx
0x1800b62e6  mov     [rsp+828h+ValueName], bx
0x1800b62ee  mov     r8, r15; Size
0x1800b62f1  xor     edx, edx; Val
0x1800b62f3  lea     rcx, [rsp+828h+var_476]; void *
0x1800b62fb  call    memset_0
0x1800b6300  mov     word ptr [rsp+828h+Data], bx
0x1800b6308  mov     r8, r15; Size
0x1800b630b  xor     edx, edx; Val
0x1800b630d  lea     rcx, [rsp+828h+var_686]; void *
0x1800b6315  call    memset_0
0x1800b631a  mov     [rsp+828h+cchValueName], 104h
0x1800b6322  mov     [rsp+828h+cbData], 208h
0x1800b632a  mov     [rsp+828h+Type], ebx
0x1800b632e  lea     rax, [rsp+828h+cbData]
0x1800b6333  mov     [rsp+828h+lpcbData], rax; lpcbData
0x1800b6338  lea     rax, [rsp+828h+Data]
0x1800b6340  mov     [rsp+828h+pcbData], rax; lpData
0x1800b6345  lea     rax, [rsp+828h+Type]
0x1800b634a  mov     [rsp+828h+pvData], rax; lpType
0x1800b634f  mov     [rsp+828h+pdwType], rbx; lpReserved
0x1800b6354  lea     r9, [rsp+828h+cchValueName]; lpcchValueName
0x1800b6359  lea     r8, [rsp+828h+ValueName]; lpValueName
0x1800b6361  mov     edx, esi; dwIndex
0x1800b6363  mov     rcx, [rsp+828h+phkResult]; hKey
0x1800b6368  call    cs:__imp_RegEnumValueW
0x1800b636e  test    eax, eax
0x1800b6370  jnz     loc_1800B64ED
0x1800b6376  cmp     [rsp+828h+Type], 2
0x1800b637b  jnz     loc_1800B6422
0x1800b6381  mov     [rsp+828h+Dst], bx
0x1800b6389  mov     r8, r15; Size
0x1800b638c  xor     edx, edx; Val
0x1800b638e  lea     rcx, [rsp+828h+var_266]; void *
0x1800b6396  call    memset_0
0x1800b639b  mov     r8d, 104h; nSize
0x1800b63a1  lea     rdx, [rsp+828h+Dst]; lpDst
0x1800b63a9  lea     rcx, [rsp+828h+Data]; lpSrc
0x1800b63b1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b63b7  test    eax, eax
0x1800b63b9  jz      short loc_1800B642D
0x1800b63bb  lea     rcx, [rsp+828h+Data]
0x1800b63c3  lea     rax, [rsp+828h+Dst]
0x1800b63cb  mov     edx, 4
0x1800b63d0  movups  xmm0, xmmword ptr [rax]
0x1800b63d3  movups  xmmword ptr [rcx], xmm0
0x1800b63d6  movups  xmm1, xmmword ptr [rax+10h]
0x1800b63da  movups  xmmword ptr [rcx+10h], xmm1
0x1800b63de  movups  xmm0, xmmword ptr [rax+20h]
0x1800b63e2  movups  xmmword ptr [rcx+20h], xmm0
0x1800b63e6  movups  xmm1, xmmword ptr [rax+30h]
0x1800b63ea  movups  xmmword ptr [rcx+30h], xmm1
0x1800b63ee  movups  xmm0, xmmword ptr [rax+40h]
0x1800b63f2  movups  xmmword ptr [rcx+40h], xmm0
0x1800b63f6  movups  xmm1, xmmword ptr [rax+50h]
0x1800b63fa  movups  xmmword ptr [rcx+50h], xmm1
0x1800b63fe  movups  xmm0, xmmword ptr [rax+60h]
0x1800b6402  movups  xmmword ptr [rcx+60h], xmm0
0x1800b6406  movups  xmm1, xmmword ptr [rax+70h]
0x1800b640a  movups  xmmword ptr [rcx+70h], xmm1
0x1800b640e  add     rcx, r12
0x1800b6411  add     rax, r12
0x1800b6414  sub     rdx, 1
0x1800b6418  jnz     short loc_1800B63D0
0x1800b641a  mov     rax, [rax]
0x1800b641d  mov     [rcx], rax
0x1800b6420  jmp     short loc_1800B642D
0x1800b6422  cmp     [rsp+828h+Type], 1
0x1800b6427  jnz     loc_1800B64E6
0x1800b642d  lea     rdx, [rsp+828h+ValueName]
0x1800b6435  lea     rcx, [rsp+828h+var_6A8]
0x1800b643d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b6442  lea     r8, [rsp+828h+var_6A8]
0x1800b644a  lea     rdx, [rsp+828h+var_7A8]
0x1800b6452  lea     rcx, [rsp+828h+var_7C8]
0x1800b6457  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800b645c  mov     rcx, qword ptr [rsp+828h+var_7C8]
0x1800b6461  cmp     [rax], rcx
0x1800b6464  setz    bl
0x1800b6467  lea     rcx, [rsp+828h+var_6A8]; void *
0x1800b646f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b6474  test    bl, bl
0x1800b6476  jz      short loc_1800B64E4
0x1800b6478  lea     rdx, [rsp+828h+ValueName]
0x1800b6480  lea     rcx, [rsp+828h+var_6A8]
  ... truncated ...
```
