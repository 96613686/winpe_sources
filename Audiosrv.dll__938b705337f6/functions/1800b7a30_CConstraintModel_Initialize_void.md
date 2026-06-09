# CConstraintModel::Initialize(void)

- ea: `0x1800b7a30`
- end: `0x1800b83e3`
- name: `?Initialize@CConstraintModel@@QEAAJXZ`
- size: `2483`
- prototype: `__int64 __fastcall(CConstraintModel *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180103e18`

## callees

- `0x1800163f0`
- `0x180016720`
- `0x1800ad240`
- `0x1800b365c`
- `0x1800b4d9c`
- `0x1800b7a30`
- `0x1800b83ec`
- `0x1800b84b8`
- `0x1800b8514`
- `0x1800b8644`
- `0x1800b8710`
- `0x1800c0af8`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1801050a4`
- `0x180158918`
- `0x180158c7c`
- `0x180159490`
- `0x1801595c4`
- `0x180159658`
- `0x1801596f0`
- `0x18015a724`
- `0x18015a7c0`
- `0x18015aafc`
- `0x18015ab64`
- `0x18015ac68`
- `0x18015ad30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7ab9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7ab9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b7b9a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b7eb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b7b9a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b7eb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7afe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7e26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7afe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7e26`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b7be3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b7f01`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b7be3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800b7f01`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800b7def`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800b7def`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800b7dbf`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800b7dbf`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800b7d6e`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800b7d6e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800b7d41`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800b7d41`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800b8089`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800b8089`

## string_xrefs

- `0x1800b816f`: `Parsing XML %s, %s`
- `0x1800b81df`: `Parsing XML %s failed`
- `0x1800b7e1c`: `SYSTEM\MultiMedia\DeviceCapability\ResourceSettings\XMLConfig`
- `0x1800b7af4`: `System\MultiMedia\DeviceCapability\ResourceSettings\XMLConfig`

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
0x1800b7a30  mov     rax, rsp
0x1800b7a33  push    rbx
0x1800b7a34  push    rsi
0x1800b7a35  push    rdi
0x1800b7a36  push    r12
0x1800b7a38  push    r14
0x1800b7a3a  push    r15
0x1800b7a3c  sub     rsp, 7F8h
0x1800b7a43  movaps  xmmword ptr [rax-48h], xmm6
0x1800b7a47  mov     rax, cs:__security_cookie
0x1800b7a4e  xor     rax, rsp
0x1800b7a51  mov     [rsp+828h+var_58], rax
0x1800b7a59  mov     r15, rcx
0x1800b7a5c  mov     [rsp+828h+var_7B8], rcx
0x1800b7a61  xorps   xmm0, xmm0
0x1800b7a64  movdqu  [rsp+828h+var_7C8], xmm0
0x1800b7a6a  lea     rcx, [rsp+828h+var_7C8]
0x1800b7a6f  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800b7a74  nop
0x1800b7a75  xor     esi, esi
0x1800b7a77  mov     [rsp+828h+var_7CC], esi
0x1800b7a7b  lea     r14d, [rsi+4]
0x1800b7a7f  mov     [rsp+828h+var_7D0], r14d
0x1800b7a84  lea     rax, [rsp+828h+var_7D0]
0x1800b7a89  mov     [rsp+828h+pcbData], rax; pcbData
0x1800b7a8e  lea     rax, [rsp+828h+var_7CC]
0x1800b7a93  mov     [rsp+828h+pvData], rax; pvData
0x1800b7a98  mov     [rsp+828h+pdwType], rsi; pdwType
0x1800b7a9d  lea     r9d, [rsi+18h]; dwFlags
0x1800b7aa1  lea     r8, aConstraintmode; "ConstraintModelTest"
0x1800b7aa8  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b7aaf  mov     rbx, 0FFFFFFFF80000002h
0x1800b7ab6  mov     rcx, rbx; hkey
0x1800b7ab9  call    cs:__imp_RegGetValueW
0x1800b7abf  test    eax, eax
0x1800b7ac1  jnz     loc_1800B7D32
0x1800b7ac7  cmp     [rsp+828h+var_7D0], r14d
0x1800b7acc  jnz     loc_1800B7D32
0x1800b7ad2  cmp     [rsp+828h+var_7CC], esi
0x1800b7ad6  jz      loc_1800B7D32
0x1800b7adc  mov     [rsp+828h+phkResult], rsi
0x1800b7ae1  lea     rax, [rsp+828h+phkResult]
0x1800b7ae6  mov     [rsp+828h+pdwType], rax; phkResult
0x1800b7aeb  mov     r9d, 20019h; samDesired
0x1800b7af1  xor     r8d, r8d; ulOptions
0x1800b7af4  lea     rdx, aSystemMultimed; "System\\MultiMedia\\DeviceCapability\\R"...
0x1800b7afb  mov     rcx, rbx; hKey
0x1800b7afe  call    cs:__imp_RegOpenKeyExW
0x1800b7b04  test    eax, eax
0x1800b7b06  jnz     loc_1800B7D23
0x1800b7b0c  mov     edi, esi
0x1800b7b0e  mov     r15d, 206h
0x1800b7b14  lea     r12d, [r14+7Ch]
0x1800b7b18  mov     [rsp+828h+ValueName], si
0x1800b7b20  mov     r8, r15; Size
0x1800b7b23  xor     edx, edx; Val
0x1800b7b25  lea     rcx, [rsp+828h+var_476]; void *
0x1800b7b2d  call    memset_0
0x1800b7b32  mov     word ptr [rsp+828h+Data], si
0x1800b7b3a  mov     r8, r15; Size
0x1800b7b3d  xor     edx, edx; Val
0x1800b7b3f  lea     rcx, [rsp+828h+var_686]; void *
0x1800b7b47  call    memset_0
0x1800b7b4c  mov     [rsp+828h+cchValueName], 104h
0x1800b7b54  mov     [rsp+828h+cbData], 208h
0x1800b7b5c  mov     [rsp+828h+Type], esi
0x1800b7b60  lea     rax, [rsp+828h+cbData]
0x1800b7b65  mov     [rsp+828h+lpcbData], rax; lpcbData
0x1800b7b6a  lea     rax, [rsp+828h+Data]
0x1800b7b72  mov     [rsp+828h+pcbData], rax; lpData
0x1800b7b77  lea     rax, [rsp+828h+Type]
0x1800b7b7c  mov     [rsp+828h+pvData], rax; lpType
0x1800b7b81  mov     [rsp+828h+pdwType], rsi; lpReserved
0x1800b7b86  lea     r9, [rsp+828h+cchValueName]; lpcchValueName
0x1800b7b8b  lea     r8, [rsp+828h+ValueName]; lpValueName
0x1800b7b93  mov     edx, edi; dwIndex
0x1800b7b95  mov     rcx, [rsp+828h+phkResult]; hKey
0x1800b7b9a  call    cs:__imp_RegEnumValueW
0x1800b7ba0  test    eax, eax
0x1800b7ba2  jnz     loc_1800B7D1E
0x1800b7ba8  cmp     [rsp+828h+Type], 2
0x1800b7bad  jnz     loc_1800B7C52
0x1800b7bb3  mov     [rsp+828h+Dst], si
0x1800b7bbb  mov     r8, r15; Size
0x1800b7bbe  xor     edx, edx; Val
0x1800b7bc0  lea     rcx, [rsp+828h+var_266]; void *
0x1800b7bc8  call    memset_0
0x1800b7bcd  mov     r8d, 104h; nSize
0x1800b7bd3  lea     rdx, [rsp+828h+Dst]; lpDst
0x1800b7bdb  lea     rcx, [rsp+828h+Data]; lpSrc
0x1800b7be3  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b7be9  test    eax, eax
0x1800b7beb  jz      short loc_1800B7C67
0x1800b7bed  lea     rcx, [rsp+828h+Data]
0x1800b7bf5  lea     rax, [rsp+828h+Dst]
0x1800b7bfd  mov     rdx, r14
0x1800b7c00  movups  xmm0, xmmword ptr [rax]
0x1800b7c03  movups  xmmword ptr [rcx], xmm0
0x1800b7c06  movups  xmm1, xmmword ptr [rax+10h]
0x1800b7c0a  movups  xmmword ptr [rcx+10h], xmm1
0x1800b7c0e  movups  xmm0, xmmword ptr [rax+20h]
0x1800b7c12  movups  xmmword ptr [rcx+20h], xmm0
0x1800b7c16  movups  xmm1, xmmword ptr [rax+30h]
0x1800b7c1a  movups  xmmword ptr [rcx+30h], xmm1
0x1800b7c1e  movups  xmm0, xmmword ptr [rax+40h]
0x1800b7c22  movups  xmmword ptr [rcx+40h], xmm0
0x1800b7c26  movups  xmm1, xmmword ptr [rax+50h]
0x1800b7c2a  movups  xmmword ptr [rcx+50h], xmm1
0x1800b7c2e  movups  xmm0, xmmword ptr [rax+60h]
0x1800b7c32  movups  xmmword ptr [rcx+60h], xmm0
0x1800b7c36  movups  xmm1, xmmword ptr [rax+70h]
0x1800b7c3a  movups  xmmword ptr [rcx+70h], xmm1
0x1800b7c3e  add     rcx, r12
0x1800b7c41  add     rax, r12
0x1800b7c44  sub     rdx, 1
0x1800b7c48  jnz     short loc_1800B7C00
0x1800b7c4a  mov     rax, [rax]
0x1800b7c4d  mov     [rcx], rax
0x1800b7c50  jmp     short loc_1800B7C67
0x1800b7c52  cmp     [rsp+828h+Type], 1
0x1800b7c57  jnz     loc_1800B7D17
0x1800b7c5d  cmp     [rsp+828h+cchValueName], esi
0x1800b7c61  jz      loc_1800B7D17
0x1800b7c67  lea     rdx, [rsp+828h+ValueName]
0x1800b7c6f  lea     rcx, [rsp+828h+var_6F8]
0x1800b7c77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b7c7c  lea     r8, [rsp+828h+var_6F8]
0x1800b7c84  lea     rdx, [rsp+828h+var_7B0]
0x1800b7c89  lea     rcx, [rsp+828h+var_7C8]
0x1800b7c8e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800b7c93  mov     rcx, qword ptr [rsp+828h+var_7C8]
0x1800b7c98  cmp     [rax], rcx
0x1800b7c9b  setz    bl
0x1800b7c9e  lea     rcx, [rsp+828h+var_6F8]; void *
0x1800b7ca6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b7cab  test    bl, bl
0x1800b7cad  jz      short loc_1800B7D17
0x1800b7caf  lea     rdx, [rsp+828h+ValueName]
0x1800b7cb7  lea     rcx, [rsp+828h+var_6F8]
0x1800b7cbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b7cc4  nop
0x1800b7cc5  lea     r8, [rsp+828h+var_6F8]
0x1800b7ccd  lea     rdx, [rsp+828h+var_7A8]
0x1800b7cd5  lea     rcx, [rsp+828h+var_7C8]
0x1800b7cda  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800b7cdf  lea     rcx, [rsp+828h+Data]
0x1800b7ce7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b7ceb  inc     r8
0x1800b7cee  cmp     [rcx+r8*2], si
0x1800b7cf3  jnz     short loc_1800B7CEB
0x1800b7cf5  mov     rcx, [rax]
0x1800b7cf8  add     rcx, 40h ; '@'
0x1800b7cfc  lea     rdx, [rsp+828h+Data]
0x1800b7d04  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800b7d09  nop
0x1800b7d0a  lea     rcx, [rsp+828h+var_6F8]; void *
0x1800b7d12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b7d17  inc     edi
0x1800b7d19  jmp     loc_1800B7B18
0x1800b7d1e  mov     r15, [rsp+828h+var_7B8]
0x1800b7d23  lea     rcx, [rsp+828h+phkResult]
0x1800b7d28  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b7d2d  jmp     loc_1800B808F
0x1800b7d32  mov     [rsp+828h+pdwType], rsi
0x1800b7d37  xor     r9d, r9d
0x1800b7d3a  xor     r8d, r8d
0x1800b7d3d  xor     edx, edx
0x1800b7d3f  xor     ecx, ecx
0x1800b7d41  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800b7d47  mov     rdi, rax
0x1800b7d4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b7d4e  jz      loc_1800B808F
0x1800b7d54  mov     [rsp+828h+pvData], rsi
0x1800b7d59  mov     [rsp+828h+pdwType], rsi
0x1800b7d5e  xor     r9d, r9d
0x1800b7d61  xor     r8d, r8d
0x1800b7d64  lea     rdx, GUID_DEVCLASS_MEDIA
0x1800b7d6b  mov     rcx, rax
0x1800b7d6e  call    cs:__imp_DevObjGetClassDevs
0x1800b7d74  test    eax, eax
0x1800b7d76  jz      loc_1800B8086
0x1800b7d7c  mov     r14d, esi
0x1800b7d7f  xorps   xmm0, xmm0
0x1800b7d82  movups  [rsp+828h+var_6D8], xmm0
0x1800b7d8a  movups  [rsp+828h+var_6C8], xmm0
0x1800b7d92  movups  [rsp+828h+var_6B8], xmm0
0x1800b7d9a  mov     dword ptr [rsp+828h+var_6D8], 30h ; '0'
0x1800b7da5  mov     r15d, 206h
0x1800b7dab  mov     r12d, 80h
0x1800b7db1  lea     r8, [rsp+828h+var_6D8]
0x1800b7db9  mov     edx, r14d
0x1800b7dbc  mov     rcx, rdi
0x1800b7dbf  call    cs:__imp_DevObjEnumDeviceInfo
0x1800b7dc5  test    eax, eax
0x1800b7dc7  jz      loc_1800B8081
0x1800b7dcd  mov     dword ptr [rsp+828h+pvData], 20019h
0x1800b7dd5  mov     dword ptr [rsp+828h+pdwType], 2
0x1800b7ddd  xor     r9d, r9d
0x1800b7de0  lea     r8d, [r9+1]
0x1800b7de4  lea     rdx, [rsp+828h+var_6D8]
0x1800b7dec  mov     rcx, rdi
0x1800b7def  call    cs:__imp_DevObjOpenDevRegKey
0x1800b7df5  mov     [rsp+828h+var_7B0], rax
0x1800b7dfa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b7dfe  jz      loc_1800B8049
0x1800b7e04  mov     [rsp+828h+phkResult], rsi
0x1800b7e09  lea     rcx, [rsp+828h+phkResult]
0x1800b7e0e  mov     [rsp+828h+pdwType], rcx; phkResult
0x1800b7e13  mov     r9d, 1; samDesired
0x1800b7e19  xor     r8d, r8d; ulOptions
0x1800b7e1c  lea     rdx, aSystemMultimed_0; "SYSTEM\\MultiMedia\\DeviceCapability\\R"...
0x1800b7e23  mov     rcx, rax; hKey
0x1800b7e26  call    cs:__imp_RegOpenKeyExW
0x1800b7e2c  test    eax, eax
0x1800b7e2e  jnz     loc_1800B803F
0x1800b7e34  xor     ebx, ebx
0x1800b7e36  mov     [rsp+828h+ValueName], bx
0x1800b7e3e  mov     r8, r15; Size
0x1800b7e41  xor     edx, edx; Val
0x1800b7e43  lea     rcx, [rsp+828h+var_476]; void *
0x1800b7e4b  call    memset_0
0x1800b7e50  mov     word ptr [rsp+828h+Data], bx
0x1800b7e58  mov     r8, r15; Size
0x1800b7e5b  xor     edx, edx; Val
0x1800b7e5d  lea     rcx, [rsp+828h+var_686]; void *
0x1800b7e65  call    memset_0
0x1800b7e6a  mov     [rsp+828h+cchValueName], 104h
0x1800b7e72  mov     [rsp+828h+cbData], 208h
0x1800b7e7a  mov     [rsp+828h+Type], ebx
0x1800b7e7e  lea     rax, [rsp+828h+cbData]
0x1800b7e83  mov     [rsp+828h+lpcbData], rax; lpcbData
0x1800b7e88  lea     rax, [rsp+828h+Data]
0x1800b7e90  mov     [rsp+828h+pcbData], rax; lpData
0x1800b7e95  lea     rax, [rsp+828h+Type]
0x1800b7e9a  mov     [rsp+828h+pvData], rax; lpType
0x1800b7e9f  mov     [rsp+828h+pdwType], rbx; lpReserved
0x1800b7ea4  lea     r9, [rsp+828h+cchValueName]; lpcchValueName
0x1800b7ea9  lea     r8, [rsp+828h+ValueName]; lpValueName
0x1800b7eb1  mov     edx, esi; dwIndex
0x1800b7eb3  mov     rcx, [rsp+828h+phkResult]; hKey
0x1800b7eb8  call    cs:__imp_RegEnumValueW
0x1800b7ebe  test    eax, eax
0x1800b7ec0  jnz     loc_1800B803D
0x1800b7ec6  cmp     [rsp+828h+Type], 2
0x1800b7ecb  jnz     loc_1800B7F72
0x1800b7ed1  mov     [rsp+828h+Dst], bx
0x1800b7ed9  mov     r8, r15; Size
0x1800b7edc  xor     edx, edx; Val
0x1800b7ede  lea     rcx, [rsp+828h+var_266]; void *
0x1800b7ee6  call    memset_0
0x1800b7eeb  mov     r8d, 104h; nSize
0x1800b7ef1  lea     rdx, [rsp+828h+Dst]; lpDst
0x1800b7ef9  lea     rcx, [rsp+828h+Data]; lpSrc
0x1800b7f01  call    cs:__imp_ExpandEnvironmentStringsW
0x1800b7f07  test    eax, eax
0x1800b7f09  jz      short loc_1800B7F7D
0x1800b7f0b  lea     rcx, [rsp+828h+Data]
0x1800b7f13  lea     rax, [rsp+828h+Dst]
0x1800b7f1b  mov     edx, 4
0x1800b7f20  movups  xmm0, xmmword ptr [rax]
0x1800b7f23  movups  xmmword ptr [rcx], xmm0
0x1800b7f26  movups  xmm1, xmmword ptr [rax+10h]
0x1800b7f2a  movups  xmmword ptr [rcx+10h], xmm1
0x1800b7f2e  movups  xmm0, xmmword ptr [rax+20h]
0x1800b7f32  movups  xmmword ptr [rcx+20h], xmm0
0x1800b7f36  movups  xmm1, xmmword ptr [rax+30h]
0x1800b7f3a  movups  xmmword ptr [rcx+30h], xmm1
0x1800b7f3e  movups  xmm0, xmmword ptr [rax+40h]
0x1800b7f42  movups  xmmword ptr [rcx+40h], xmm0
0x1800b7f46  movups  xmm1, xmmword ptr [rax+50h]
0x1800b7f4a  movups  xmmword ptr [rcx+50h], xmm1
0x1800b7f4e  movups  xmm0, xmmword ptr [rax+60h]
0x1800b7f52  movups  xmmword ptr [rcx+60h], xmm0
0x1800b7f56  movups  xmm1, xmmword ptr [rax+70h]
0x1800b7f5a  movups  xmmword ptr [rcx+70h], xmm1
0x1800b7f5e  add     rcx, r12
0x1800b7f61  add     rax, r12
0x1800b7f64  sub     rdx, 1
0x1800b7f68  jnz     short loc_1800B7F20
0x1800b7f6a  mov     rax, [rax]
0x1800b7f6d  mov     [rcx], rax
0x1800b7f70  jmp     short loc_1800B7F7D
0x1800b7f72  cmp     [rsp+828h+Type], 1
0x1800b7f77  jnz     loc_1800B8036
0x1800b7f7d  lea     rdx, [rsp+828h+ValueName]
0x1800b7f85  lea     rcx, [rsp+828h+var_6A8]
0x1800b7f8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b7f92  lea     r8, [rsp+828h+var_6A8]
0x1800b7f9a  lea     rdx, [rsp+828h+var_7A8]
0x1800b7fa2  lea     rcx, [rsp+828h+var_7C8]
0x1800b7fa7  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800b7fac  mov     rcx, qword ptr [rsp+828h+var_7C8]
0x1800b7fb1  cmp     [rax], rcx
0x1800b7fb4  setz    bl
0x1800b7fb7  lea     rcx, [rsp+828h+var_6A8]; void *
0x1800b7fbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b7fc4  test    bl, bl
0x1800b7fc6  jz      short loc_1800B8034
0x1800b7fc8  lea     rdx, [rsp+828h+ValueName]
0x1800b7fd0  lea     rcx, [rsp+828h+var_6A8]
  ... truncated ...
```
