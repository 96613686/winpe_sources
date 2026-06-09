# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetGraphDataUpdates(_GUID const &,tagSAFEARRAY *,GraphDataUpdates *)

- ea: `0x180005530`
- end: `0x180005ee0`
- name: `?GetGraphDataUpdates@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJAEBU_GUID@@PEAUtagSAFEARRAY@@PEAUGraphDataUpdates@@@Z`
- size: `2480`
- prototype: `HRESULT __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this, struct _GUID *, struct tagSAFEARRAY *, OLECHAR *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800023c4`
- `0x180005530`
- `0x1800080e4`
- `0x18000817c`
- `0x18000856c`
- `0x180008ea8`
- `0x18000a0f0`
- `0x18003d864`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180041a48`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x180005a5f`
- `VCRUNTIME140!memcpy` at `0x180005a5f`
- `VCRUNTIME140!memset` at `0x180005a10`
- `VCRUNTIME140!memset` at `0x180005a6c`
- `VCRUNTIME140!memset` at `0x180005a10`
- `VCRUNTIME140!memset` at `0x180005a6c`
- `KERNEL32!LocalFree` at `0x180005e1c`
- `KERNEL32!LocalFree` at `0x180005e1c`
- `KERNEL32!LeaveCriticalSection` at `0x180005e64`
- `KERNEL32!LeaveCriticalSection` at `0x180005e64`
- `KERNEL32!EnterCriticalSection` at `0x180005675`
- `KERNEL32!EnterCriticalSection` at `0x180005675`
- `ole32!CoTaskMemRealloc` at `0x180005d5d`
- `ole32!CoTaskMemRealloc` at `0x180005d5d`
- `ole32!CoTaskMemAlloc` at `0x18000578e`
- `ole32!CoTaskMemAlloc` at `0x1800059ee`
- `ole32!CoTaskMemAlloc` at `0x18000578e`
- `ole32!CoTaskMemAlloc` at `0x1800059ee`
- `ole32!CoTaskMemFree` at `0x180005ad5`
- `ole32!CoTaskMemFree` at `0x180005b22`
- `ole32!CoTaskMemFree` at `0x180005b2f`
- `ole32!CoTaskMemFree` at `0x180005c32`
- `ole32!CoTaskMemFree` at `0x180005d21`
- `ole32!CoTaskMemFree` at `0x180005d2b`
- `ole32!CoTaskMemFree` at `0x180005ad5`
- `ole32!CoTaskMemFree` at `0x180005b22`
- `ole32!CoTaskMemFree` at `0x180005b2f`
- `ole32!CoTaskMemFree` at `0x180005c32`
- `ole32!CoTaskMemFree` at `0x180005d21`
- `ole32!CoTaskMemFree` at `0x180005d2b`
- `ole32!StringFromGUID2` at `0x180005c83`
- `ole32!StringFromGUID2` at `0x180005d75`
- `ole32!StringFromGUID2` at `0x180005c83`
- `ole32!StringFromGUID2` at `0x180005d75`
- `OLEAUT32!__imp_SysAllocString` at `0x180005aa3`
- `OLEAUT32!__imp_SysAllocString` at `0x180005ab1`
- `OLEAUT32!__imp_SysAllocString` at `0x180005bde`
- `OLEAUT32!__imp_SysAllocString` at `0x180005aa3`
- `OLEAUT32!__imp_SysAllocString` at `0x180005ab1`
- `OLEAUT32!__imp_SysAllocString` at `0x180005bde`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c01`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c01`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e2b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800055a2`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800055a2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180005742`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180005742`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180005728`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180005728`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005845`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005845`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800055c9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800055c9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180005a3d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180005a7e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180005a3d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180005a7e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180005a8a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180005a8a`

## string_xrefs

- `0x180005614`: `GetGraphDataUpdates`
- `0x180005ba7`: `Agent ({%08x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}) logged %d points for '%s' counter.`

## pseudocode

```c
HRESULT __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetGraphDataUpdates(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *this,
        struct _GUID *a2,
        struct tagSAFEARRAY *a3,
        OLECHAR *a4)
{
  OLECHAR *v4; // rsi
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *v7; // r14
  int v8; // r15d
  HRESULT result; // eax
  int v10; // eax
  const unsigned __int16 *v11; // r8
  const struct _GUID *v12; // rdx
  int v13; // ebx
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r9
  __int64 v17; // rdx
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rcx
  __int64 v20; // rcx
  __int64 v21; // rbx
  HRESULT LBound; // eax
  __int64 v23; // r12
  _OWORD *v24; // rax
  __int64 v25; // rcx
  GUID *v26; // rbx
  int (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // rcx
  int v28; // esi
  HRESULT Element; // eax
  unsigned int k; // r14d
  __int64 v31; // rbx
  _QWORD *v32; // rbx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  _QWORD *v35; // rax
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // r14
  void *v38; // rcx
  __int64 v39; // r14
  __int64 v40; // xmm6_8
  BSTR v41; // rsi
  BSTR v42; // rax
  OLECHAR *v43; // rdx
  __int64 v44; // rsi
  _QWORD *v45; // rbx
  OLECHAR *v46; // rdx
  const unsigned __int16 *v47; // r8
  const wchar_t *v48; // rdx
  __int64 v49; // rax
  LPVOID v50; // rax
  const unsigned __int16 *v51; // r8
  const wchar_t *v52; // rdx
  __int64 v53; // [rsp+28h] [rbp-E0h]
  __int64 v54; // [rsp+30h] [rbp-D8h]
  OLECHAR *psz[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-B0h]
  GUID *rguid; // [rsp+60h] [rbp-A8h]
  __int64 v58; // [rsp+68h] [rbp-A0h]
  _QWORD v59[3]; // [rsp+70h] [rbp-98h] BYREF
  void *v60; // [rsp+88h] [rbp-80h]
  _QWORD v61[3]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v62[7]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v63[16]; // [rsp+E0h] [rbp-28h] BYREF
  int v64; // [rsp+F0h] [rbp-18h] BYREF
  unsigned int v65; // [rsp+F4h] [rbp-14h] BYREF
  void *Src; // [rsp+F8h] [rbp-10h] BYREF
  OLECHAR *pv; // [rsp+100h] [rbp-8h] BYREF
  LPVOID v68; // [rsp+108h] [rbp+0h] BYREF
  LPVOID v69; // [rsp+110h] [rbp+8h] BYREF
  _QWORD *v70; // [rsp+118h] [rbp+10h] BYREF
  VARTYPE pvt[2]; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v72; // [rsp+124h] [rbp+1Ch] BYREF
  unsigned int v73; // [rsp+128h] [rbp+20h] BYREF
  LONG rgIndices; // [rsp+12Ch] [rbp+24h] BYREF
  __int64 v75; // [rsp+130h] [rbp+28h] BYREF
  LONG plUbound; // [rsp+138h] [rbp+30h] BYREF
  LONG plLbound[3]; // [rsp+13Ch] [rbp+34h] BYREF
  OLECHAR sz[39]; // [rsp+148h] [rbp+40h] BYREF
  __int16 v79; // [rsp+196h] [rbp+8Eh]
  __int16 v80; // [rsp+1E4h] [rbp+DCh]
  void *v81; // [rsp+228h] [rbp+120h] BYREF
  __int64 v82; // [rsp+230h] [rbp+128h]

  v4 = a4;
  psz[1] = a4;
  rguid = a2;
  v7 = this;
  v59[0] = this;
  if ( !a4 || !a3 )
    return -2147467261;
  if ( (a3->fFeatures & 0x100) == 0 )
    return -2147024809;
  v8 = 1;
  if ( SafeArrayGetDim(a3) != 1 )
    return -2147024809;
  if ( SLOBYTE(a3->fFeatures) < 0 )
  {
    result = SafeArrayGetVartype(a3, pvt);
    v64 = result;
    if ( result < 0 )
    {
      _mm_lfence();
      return result;
    }
    if ( pvt[0] != 8 )
      return -2147024809;
  }
  *(_DWORD *)v4 = 0;
  *((_QWORD *)v4 + 1) = 0;
  v10 = *((_DWORD *)v7 + 101);
  if ( v10 != 2 && v10 != 3 )
  {
    *(_OWORD *)&v59[1] = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)&v59[1],
      -518979512,
      L"GetGraphDataUpdates",
      *((_WORD *)v7 + 42));
    v12 = (const struct _GUID *)L"<unknown error>";
    if ( v59[1] )
      v12 = (const struct _GUID *)v59[1];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v12, v11);
    v13 = v59[2];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)&v59[1]);
    return v13;
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v7 + 31) + 200LL);
  v59[1] = v14;
  EnterCriticalSection(v14);
  v15 = *((_QWORD *)v7 + 31);
  v16 = 0xCBF29CE484222325uLL;
  v17 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v17 = 0x100000001B3LL * (*((unsigned __int8 *)&a2->Data1 + i) ^ (unsigned __int64)v17);
  for ( j = 0; j < 8; ++j )
    v16 = 0x100000001B3LL * (a2->Data4[j] ^ (unsigned __int64)v16);
  v20 = *(_QWORD *)(std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                      v15 + 240,
                      v63,
                      a2,
                      v17 ^ v16)
                  + 8);
  v58 = v20;
  if ( !v20 )
  {
    v20 = *(_QWORD *)(v15 + 248);
    v58 = v20;
  }
  if ( v20 == *(_QWORD *)(*((_QWORD *)v7 + 31) + 248LL) )
    goto LABEL_28;
  v21 = v20 + 32;
  v81 = (void *)(v20 + 32);
  if ( *(_BYTE *)(v20 + 40) )
    goto LABEL_104;
  LBound = SafeArrayGetLBound(a3, 1u, plLbound);
  v64 = LBound;
  if ( LBound < 0 || (_mm_lfence(), LBound = SafeArrayGetUBound(a3, 1u, &plUbound), v64 = LBound, LBound < 0) )
  {
    v8 = LBound;
    goto LABEL_104;
  }
  _mm_lfence();
  v23 = (unsigned int)(plUbound - plLbound[0] + 1);
  if ( plUbound - plLbound[0] == -1 )
  {
    v8 = 0;
    goto LABEL_104;
  }
  if ( (unsigned int)v23 >= 0x3333333 )
  {
LABEL_28:
    v8 = -2147024809;
    goto LABEL_104;
  }
  _mm_lfence();
  v24 = CoTaskMemAlloc(40 * v23);
  v69 = v24;
  if ( !v24 )
  {
    v8 = -2147024882;
    goto LABEL_104;
  }
  v65 = 0;
  v25 = v58;
  *v24 = *(_OWORD *)(v58 + 16);
  *((_QWORD *)v69 + 2) = 0;
  *((_QWORD *)v69 + 4) = 0;
  *((_DWORD *)v69 + 6) = 0;
  v62[0] = &v64;
  v62[1] = v21;
  v26 = rguid;
  v62[2] = rguid;
  v62[3] = &v69;
  v62[4] = &v65;
  v75 = 0;
  v27 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v25 + 32);
  v75 = 0;
  if ( v27 && (**v27)(v27, &GUID_4a0f857b_adc5_4858_8a75_f3b59b3f08d8, &v75) < 0 )
    v75 = 0;
  rgIndices = 0;
  if ( (int)v23 <= 0 )
  {
LABEL_86:
    v49 = v65;
    if ( v65 )
    {
      *(_DWORD *)v4 = v65;
      if ( (unsigned int)v49 >= (unsigned int)v23 )
        v50 = v69;
      else
        v50 = CoTaskMemRealloc(v69, 40 * v49);
      *((_QWORD *)v4 + 1) = v50;
    }
    v8 = 0;
    goto LABEL_101;
  }
  v28 = 0;
  while ( 1 )
  {
    pv = 0;
    Element = SafeArrayGetElement(a3, &rgIndices, &pv);
    v64 = Element;
    if ( Element < 0 )
    {
      v8 = Element;
      goto LABEL_97;
    }
    v73 = 0;
    v70 = 0;
    if ( *((_BYTE *)v7 + 87) && v75 )
    {
      *(_DWORD *)pvt = 0;
      Src = 0;
      v72 = 0;
      v68 = 0;
      v62[5] = &Src;
      v62[6] = &v68;
      v61[0] = &v64;
      v61[1] = pvt;
      v61[2] = &Src;
      v64 = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *, VARTYPE *, void **, unsigned int *, LPVOID *))(*(_QWORD *)v75 + 48LL))(
              v75,
              0,
              pv,
              pvt,
              &Src,
              &v72,
              &v68);
      if ( v64 )
      {
        if ( !StringFromGUID2(v26, sz, 39) )
        {
          LODWORD(psz[0]) = -2147024882;
          throw (long *)psz;
        }
        v79 = 0;
        v80 = 0;
        v81 = sz;
        v82 = v64;
        psz[1] = 0;
        v56 = 3775987720LL;
        DiagHubCommon::HResultFormatter::Init(
          (DiagHubCommon::HResultFormatter *)&psz[1],
          *((_WORD *)v7 + 42),
          -518979576,
          (const void **const)&v81);
        v48 = L"<unknown error>";
        if ( psz[1] )
          v48 = psz[1];
        DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const struct _GUID *)v48, v47);
        v8 = v56;
        DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)&psz[1]);
        goto LABEL_84;
      }
      if ( !*(_DWORD *)pvt || !Src || !v72 || !v68 || *(_DWORD *)pvt == -1 )
        goto LABEL_66;
      psz[0] = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        psz,
        L"[");
      for ( k = 0; k < v72; ++k )
      {
        if ( *((int *)psz[0] - 4) > 1 )
          ATL::CSimpleStringT<unsigned short,0>::Append(psz, L", ");
        v31 = 16LL * k;
        LODWORD(v54) = *(_DWORD *)((char *)v68 + v31 + 4);
        LODWORD(v53) = *(_DWORD *)((char *)v68 + v31 + 8);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          psz,
          L"{ \"pid\": %lu, \"begin\": { \"h\": %lu, \"l\": %lu }, \"points\": %lu }",
          *(unsigned int *)((char *)v68 + v31),
          HIDWORD(*(_QWORD *)((char *)v68 + v31 + 8)),
          v53,
          v54);
        v28 += *(_DWORD *)((char *)v68 + v31 + 4);
      }
      ATL::CSimpleStringT<unsigned short,0>::Append(psz, L"]");
      if ( v28 != *(_DWORD *)pvt )
      {
        v8 = -2147024809;
        v64 = -2147024809;
        goto LABEL_78;
      }
      v32 = 0;
      v33 = *(unsigned int *)pvt + 1LL;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v33 < 0x20
        || (v34 = 32 * v33, v34 > 0x7FFFFFFF)
        || (v35 = CoTaskMemAlloc((unsigned int)v34), (v32 = v35) == 0) )
      {
        v8 = -2147024882;
        v64 = -2147024882;
        CoTaskMemFree(v32);
LABEL_78:
        v46 = psz[0] - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)psz[0] - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
        }
LABEL_84:
        DiagHubCommon::ScopeGuard__lambda_236f62f4322e77d99ba010f4a26691b8___::_ScopeGuard__lambda_236f62f4322e77d99ba010f4a26691b8___(v61);
        CoTaskMemFree(Src);
        CoTaskMemFree(v68);
        goto LABEL_97;
      }
      memset(v35, 0, 32LL * (unsigned int)(*(_DWORD *)pvt + 1));
      v36 = 32LL * *(unsigned int *)pvt;
      v60 = Src;
      v37 = 32LL * (unsigned int)(*(_DWORD *)pvt + 1);
      v38 = v32 + 4;
      if ( v36 )
      {
        if ( v32 == (_QWORD *)-32LL )
        {
LABEL_55:
          *_errno() = 22;
LABEL_62:
          _invalid_parameter_noinfo();
          goto LABEL_63;
        }
        if ( Src && v37 >= v36 )
        {
          _mm_lfence();
          memcpy(v38, Src, 32LL * *(unsigned int *)pvt);
        }
        else
        {
          memset(v38, 0, 32LL * (unsigned int)(*(_DWORD *)pvt + 1));
          if ( !v60 )
            goto LABEL_55;
          if ( v37 < v36 )
          {
            *_errno() = 34;
            goto LABEL_62;
          }
        }
      }
LABEL_63:
      v39 = *(_QWORD *)Src;
      v40 = *((_QWORD *)Src + 1);
      v41 = SysAllocString(L"MultiProcess");
      v42 = SysAllocString(psz[0]);
      *v32 = v39;
      v32[1] = v40;
      v32[2] = v41;
      v32[3] = v42;
      v73 = *(_DWORD *)pvt + 1;
      v70 = v32;
      CoTaskMemFree(0);
      v43 = psz[0] - 12;
      v28 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)psz[0] - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
      }
      v26 = rguid;
      v7 = (Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *)v59[0];
LABEL_66:
      DiagHubCommon::ScopeGuard__lambda_236f62f4322e77d99ba010f4a26691b8___::_ScopeGuard__lambda_236f62f4322e77d99ba010f4a26691b8___(v61);
      CoTaskMemFree(Src);
      CoTaskMemFree(v68);
      goto LABEL_68;
    }
    v64 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, unsigned int *, _QWORD **))(**(_QWORD **)v81 + 40LL))(
            *(_QWORD *)v81,
            pv,
            &v73,
            &v70);
    if ( v64 )
      break;
LABEL_68:
    if ( v73 )
    {
      if ( v73 > 0x64 && *((_QWORD *)_logger + 28) != *((_QWORD *)_logger + 29) )
      {
        LODWORD(v53) = v73;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 224),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
          L"Agent ({%08x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}) logged %d points for '%s' counter.",
          v26->Data1,
          v53,
          pv);
      }
      v44 = 5LL * v65;
      v45 = v69;
      *(_OWORD *)((char *)v69 + 40 * v65) = *(_OWORD *)(v58 + 16);
      v45[v44 + 2] = SysAllocString(pv);
      LODWORD(v45[v44 + 3]) = v73;
      v45[v44 + 4] = v70;
      ++v65;
      SysFreeString(pv);
      v28 = 0;
    }
    else
    {
      SysFreeString(pv);
    }
    if ( ++rgIndices >= (int)v23 )
    {
      v4 = psz[1];
      goto LABEL_86;
    }
    v26 = rguid;
  }
  if ( !StringFromGUID2(v26, sz, 39) )
  {
    LODWORD(psz[0]) = -2147024882;
    throw (long *)psz;
  }
  v79 = 0;
  v80 = 0;
  v81 = sz;
  v82 = v64;
  psz[1] = 0;
  v56 = 3775987720LL;
  DiagHubCommon::HResultFormatter::Init(
    (DiagHubCommon::HResultFormatter *)&psz[1],
    *((_WORD *)v7 + 42),
    -518979576,
    (const void **const)&v81);
  v52 = L"<unknown error>";
  if ( psz[1] )
    v52 = psz[1];
  DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const struct _GUID *)v52, v51);
  v8 = v56;
  if ( psz[1] && psz[1] != &word_180055D48 && psz[1] != L"Out of memory" )
    LocalFree(psz[1]);
LABEL_97:
  SysFreeString(pv);
LABEL_101:
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  DiagHubCommon::ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___::_ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___(v62);
LABEL_104:
  LeaveCriticalSection(v14);
  return v8;
}

```

## disassembly

```asm
0x180005530  mov     rax, rsp
0x180005533  push    rbp
0x180005534  push    rbx
0x180005535  push    rsi
0x180005536  push    rdi
0x180005537  push    r12
0x180005539  push    r13
0x18000553b  push    r14
0x18000553d  push    r15
0x18000553f  lea     rbp, [rax-198h]
0x180005546  sub     rsp, 258h
0x18000554d  movaps  xmmword ptr [rax-58h], xmm6
0x180005551  mov     rax, cs:__security_cookie
0x180005558  xor     rax, rsp
0x18000555b  mov     [rbp+190h+var_60], rax
0x180005562  mov     rsi, r9
0x180005565  mov     [rsp+290h+psz+8], r9
0x18000556a  mov     r13, r8
0x18000556d  mov     r12, rdx
0x180005570  mov     [rsp+290h+rguid], rdx
0x180005575  mov     r14, rcx
0x180005578  mov     qword ptr [rsp+290h+var_228], rcx
0x18000557d  test    r9, r9
0x180005580  jz      loc_180005E76
0x180005586  test    r8, r8
0x180005589  jz      loc_180005E76
0x18000558f  mov     eax, 100h
0x180005594  test    [r8+2], ax
0x180005599  jz      loc_180005E6F
0x18000559f  mov     rcx, r8; psa
0x1800055a2  call    cs:__imp_SafeArrayGetDim
0x1800055a8  mov     r15d, 1
0x1800055ae  cmp     eax, r15d
0x1800055b1  jnz     loc_180005E6F
0x1800055b7  lea     ebx, [r15+7]
0x1800055bb  test    byte ptr [r13+2], 80h
0x1800055c0  jz      short loc_1800055E8
0x1800055c2  lea     rdx, [rbp+190h+pvt]; pvt
0x1800055c6  mov     rcx, r13; psa
0x1800055c9  call    cs:__imp_SafeArrayGetVartype
0x1800055cf  mov     [rbp+190h+var_1A8], eax
0x1800055d2  test    eax, eax
0x1800055d4  jns     short loc_1800055DE
0x1800055d6  lfence
0x1800055d9  jmp     loc_180005E7B
0x1800055de  cmp     [rbp+190h+pvt], bx
0x1800055e2  jnz     loc_180005E6F
0x1800055e8  mov     dword ptr [rsi], 0
0x1800055ee  mov     qword ptr [rsi+8], 0
0x1800055f6  mov     eax, [r14+194h]
0x1800055fd  cmp     eax, 2
0x180005600  jz      short loc_18000565F
0x180005602  cmp     eax, 3
0x180005605  jz      short loc_18000565F
0x180005607  xorps   xmm0, xmm0
0x18000560a  movups  xmmword ptr [rsp+290h+var_228+8], xmm0
0x18000560f  movzx   r9d, word ptr [r14+54h]; unsigned __int16
0x180005614  lea     r8, aGetgraphdataup; "GetGraphDataUpdates"
0x18000561b  mov     edx, 0E1110048h; int
0x180005620  lea     rcx, [rsp+290h+var_228+8]; this
0x180005625  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x18000562a  nop
0x18000562b  lea     rdx, aUnknownError; "<unknown error>"
0x180005632  mov     rax, qword ptr [rsp+290h+var_228+8]
0x180005637  test    rax, rax
0x18000563a  cmovnz  rdx, rax; struct _GUID *
0x18000563e  lea     rcx, IID_ICollectionSession; this
0x180005645  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18000564a  mov     ebx, dword ptr [rsp+290h+var_228+10h]
0x18000564e  lea     rcx, [rsp+290h+var_228+8]; this
0x180005653  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180005658  mov     eax, ebx
0x18000565a  jmp     loc_180005E7B
0x18000565f  mov     rdi, [r14+0F8h]
0x180005666  add     rdi, 0C8h
0x18000566d  mov     qword ptr [rsp+290h+var_228+8], rdi
0x180005672  mov     rcx, rdi; lpCriticalSection
0x180005675  call    cs:__imp_EnterCriticalSection
0x18000567b  nop
0x18000567c  mov     rbx, [r14+0F8h]
0x180005683  mov     r9, 0CBF29CE484222325h
0x18000568d  mov     rdx, r9
0x180005690  xor     ecx, ecx
0x180005692  mov     r8, 100000001B3h
0x18000569c  movzx   eax, byte ptr [r12+rcx]
0x1800056a1  xor     rdx, rax
0x1800056a4  imul    rdx, r8
0x1800056a8  add     rcx, r15
0x1800056ab  cmp     rcx, 8
0x1800056af  jb      short loc_18000569C
0x1800056b1  xor     ecx, ecx
0x1800056b3  movzx   eax, byte ptr [rcx+r12+8]
0x1800056b9  xor     r9, rax
0x1800056bc  imul    r9, r8
0x1800056c0  add     rcx, r15
0x1800056c3  cmp     rcx, 8
0x1800056c7  jb      short loc_1800056B3
0x1800056c9  xor     r9, rdx
0x1800056cc  mov     r8, r12
0x1800056cf  lea     rdx, [rbp+190h+var_1B8]
0x1800056d3  lea     rcx, [rbx+0F0h]
0x1800056da  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x1800056df  mov     rcx, [rax+8]
0x1800056e3  mov     [rsp+290h+var_230], rcx
0x1800056e8  test    rcx, rcx
0x1800056eb  jnz     short loc_1800056F9
0x1800056ed  mov     rcx, [rbx+0F8h]
0x1800056f4  mov     [rsp+290h+var_230], rcx
0x1800056f9  mov     rax, [r14+0F8h]
0x180005700  cmp     rcx, [rax+0F8h]
0x180005707  jz      short loc_180005778
0x180005709  lea     rbx, [rcx+20h]
0x18000570d  mov     [rbp+190h+var_70], rbx
0x180005714  cmp     byte ptr [rbx+8], 0
0x180005718  jnz     loc_180005E61
0x18000571e  lea     r8, [rbp+190h+plLbound]; plLbound
0x180005722  mov     edx, r15d; nDim
0x180005725  mov     rcx, r13; psa
0x180005728  call    cs:__imp_SafeArrayGetLBound
0x18000572e  mov     [rbp+190h+var_1A8], eax
0x180005731  test    eax, eax
0x180005733  js      short loc_18000574F
0x180005735  lfence
0x180005738  lea     r8, [rbp+190h+plUbound]; plUbound
0x18000573c  mov     edx, r15d; nDim
0x18000573f  mov     rcx, r13; psa
0x180005742  call    cs:__imp_SafeArrayGetUBound
0x180005748  mov     [rbp+190h+var_1A8], eax
0x18000574b  test    eax, eax
0x18000574d  jns     short loc_180005757
0x18000574f  mov     r15d, eax
0x180005752  jmp     loc_180005E61
0x180005757  lfence
0x18000575a  mov     r12d, [rbp+190h+plUbound]
0x18000575e  sub     r12d, [rbp+190h+plLbound]
0x180005762  add     r12d, r15d
0x180005765  jnz     short loc_18000576F
0x180005767  xor     r15d, r15d
0x18000576a  jmp     loc_180005E61
0x18000576f  cmp     r12d, 3333333h
0x180005776  jb      short loc_180005783
0x180005778  mov     r15d, 80070057h
0x18000577e  jmp     loc_180005E61
0x180005783  lfence
0x180005786  lea     rcx, [r12+r12*4]
0x18000578a  shl     rcx, 3; cb
0x18000578e  call    cs:__imp_CoTaskMemAlloc
0x180005794  mov     [rbp+190h+var_188], rax
0x180005798  xor     edx, edx
0x18000579a  test    rax, rax
0x18000579d  jnz     short loc_1800057AA
0x18000579f  mov     r15d, 8007000Eh
0x1800057a5  jmp     loc_180005E61
0x1800057aa  mov     [rbp+190h+var_1A4], edx
0x1800057ad  mov     rcx, [rsp+290h+var_230]
0x1800057b2  movups  xmm0, xmmword ptr [rcx+10h]
0x1800057b6  movdqu  xmmword ptr [rax], xmm0
0x1800057ba  mov     rax, [rbp+190h+var_188]
0x1800057be  mov     [rax+10h], rdx
0x1800057c2  mov     rax, [rbp+190h+var_188]
0x1800057c6  mov     [rax+20h], rdx
0x1800057ca  mov     rax, [rbp+190h+var_188]
0x1800057ce  mov     [rax+18h], edx
0x1800057d1  lea     rax, [rbp+190h+var_1A8]
0x1800057d5  mov     [rbp+190h+var_1F0], rax
0x1800057d9  mov     [rbp+190h+var_1E8], rbx
0x1800057dd  mov     rbx, [rsp+290h+rguid]
0x1800057e2  mov     [rbp+190h+var_1E0], rbx
0x1800057e6  lea     rax, [rbp+190h+var_188]
0x1800057ea  mov     [rbp+190h+var_1D8], rax
0x1800057ee  lea     rax, [rbp+190h+var_1A4]
0x1800057f2  mov     [rbp+190h+var_1D0], rax
0x1800057f6  mov     [rbp+190h+var_168], rdx
0x1800057fa  mov     rcx, [rcx+20h]
0x1800057fe  mov     [rbp+190h+var_168], rdx
0x180005802  test    rcx, rcx
0x180005805  jz      short loc_180005828
0x180005807  mov     rax, [rcx]
0x18000580a  lea     r8, [rbp+190h+var_168]
0x18000580e  lea     rdx, _GUID_4a0f857b_adc5_4858_8a75_f3b59b3f08d8
0x180005815  mov     rax, [rax]
0x180005818  call    cs:__guard_dispatch_icall_fptr
0x18000581e  xor     edx, edx
0x180005820  test    eax, eax
0x180005822  jns     short loc_180005828
0x180005824  mov     [rbp+190h+var_168], rdx
0x180005828  mov     [rbp+190h+rgIndices], edx
0x18000582b  test    r12d, r12d
0x18000582e  jle     loc_180005D3B
0x180005834  xor     esi, esi
0x180005836  mov     [rbp+190h+pv], rsi
0x18000583a  lea     r8, [rbp+190h+pv]; pv
0x18000583e  lea     rdx, [rbp+190h+rgIndices]; rgIndices
0x180005842  mov     rcx, r13; psa
0x180005845  call    cs:__imp_SafeArrayGetElement
0x18000584b  mov     [rbp+190h+var_1A8], eax
0x18000584e  test    eax, eax
0x180005850  js      loc_180005E24
0x180005856  mov     [rbp+190h+var_170], esi
0x180005859  mov     [rbp+190h+var_180], rsi
0x18000585d  cmp     [r14+57h], sil
0x180005861  jz      loc_180005B37
0x180005867  mov     rcx, [rbp+190h+var_168]
0x18000586b  test    rcx, rcx
0x18000586e  jz      loc_180005B37
0x180005874  mov     dword ptr [rbp+190h+pvt], esi
0x180005877  mov     [rbp+190h+Src], rsi
0x18000587b  mov     [rbp+190h+var_174], esi
0x18000587e  mov     [rbp+190h+var_190], rsi
0x180005882  lea     rax, [rbp+190h+Src]
0x180005886  mov     [rbp+190h+var_1C8], rax
0x18000588a  lea     rax, [rbp+190h+var_190]
0x18000588e  mov     [rbp+190h+var_1C0], rax
0x180005892  lea     rax, [rbp+190h+var_1A8]
0x180005896  mov     [rbp+190h+var_208], rax
0x18000589a  lea     rax, [rbp+190h+pvt]
0x18000589e  mov     [rbp+190h+var_200], rax
0x1800058a2  lea     rax, [rbp+190h+Src]
0x1800058a6  mov     [rbp+190h+var_1F8], rax
0x1800058aa  mov     rax, [rcx]
0x1800058ad  lea     rdx, [rbp+190h+var_190]
0x1800058b1  mov     [rsp+30h], rdx
0x1800058b6  lea     rdx, [rbp+190h+var_174]
0x1800058ba  mov     [rsp+290h+var_268], rdx
0x1800058bf  lea     rdx, [rbp+190h+Src]
0x1800058c3  mov     [rsp+290h+var_270], rdx
0x1800058c8  lea     r9, [rbp+190h+pvt]
0x1800058cc  mov     r8, [rbp+190h+pv]
0x1800058d0  xor     edx, edx
0x1800058d2  mov     rax, [rax+30h]
0x1800058d6  call    cs:__guard_dispatch_icall_fptr
0x1800058dc  mov     [rbp+190h+var_1A8], eax
0x1800058df  test    eax, eax
0x1800058e1  jnz     loc_180005C76
0x1800058e7  mov     eax, dword ptr [rbp+190h+pvt]
0x1800058ea  test    eax, eax
0x1800058ec  jz      loc_180005B11
0x1800058f2  cmp     [rbp+190h+Src], rsi
0x1800058f6  jz      loc_180005B11
0x1800058fc  cmp     [rbp+190h+var_174], esi
0x1800058ff  jbe     loc_180005B11
0x180005905  cmp     [rbp+190h+var_190], rsi
0x180005909  jz      loc_180005B11
0x18000590f  cmp     eax, 0FFFFFFFFh
0x180005912  jnb     loc_180005B11
0x180005918  mov     [rsp+290h+psz], 0
0x180005921  lea     rdx, asc_180054EC0; "["
0x180005928  lea     rcx, [rsp+290h+psz]
0x18000592d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180005932  nop
0x180005933  xor     r14d, r14d
0x180005936  cmp     [rbp+190h+var_174], r14d
0x18000593a  jbe     short loc_1800059A4
0x18000593c  mov     rax, [rsp+290h+psz]
0x180005941  cmp     [rax-10h], r15d
0x180005945  jle     short loc_180005958
0x180005947  lea     rdx, asc_180054EC4; ", "
0x18000594e  lea     rcx, [rsp+290h+psz]
0x180005953  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180005958  mov     ebx, r14d
0x18000595b  shl     rbx, 4
0x18000595f  mov     r8, [rbp+190h+var_190]
0x180005963  mov     r9, [rbx+r8+8]
0x180005968  shr     r9, 20h
0x18000596c  mov     eax, [rbx+r8+4]
0x180005971  mov     dword ptr [rsp+290h+var_268], eax
0x180005975  mov     eax, [rbx+r8+8]
0x18000597a  mov     dword ptr [rsp+290h+var_270], eax
0x18000597e  mov     r8d, [rbx+r8]
0x180005982  lea     rdx, aPidLuBeginHLuL; "{ \"pid\": %lu, \"begin\": { \"h\": %lu"...
0x180005989  lea     rcx, [rsp+290h+psz]
0x18000598e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180005993  mov     rax, [rbp+190h+var_190]
0x180005997  add     esi, [rbx+rax+4]
0x18000599b  add     r14d, r15d
0x18000599e  cmp     r14d, [rbp+190h+var_174]
0x1800059a2  jb      short loc_18000593C
0x1800059a4  lea     rdx, asc_180054F50; "]"
0x1800059ab  lea     rcx, [rsp+290h+psz]
0x1800059b0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800059b5  cmp     esi, dword ptr [rbp+190h+pvt]
0x1800059b8  jnz     loc_180005C3A
0x1800059be  xor     esi, esi
0x1800059c0  mov     ebx, esi
0x1800059c2  mov     ecx, dword ptr [rbp+190h+pvt]
0x1800059c5  inc     rcx
0x1800059c8  xor     edx, edx
0x1800059ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800059ce  div     rcx
0x1800059d1  cmp     rax, 20h ; ' '
0x1800059d5  jb      loc_180005C25
0x1800059db  shl     rcx, 5
0x1800059df  cmp     rcx, 7FFFFFFFh
0x1800059e6  ja      loc_180005C25
0x1800059ec  mov     ecx, ecx; cb
0x1800059ee  call    cs:__imp_CoTaskMemAlloc
0x1800059f4  mov     rbx, rax
0x1800059f7  test    rax, rax
0x1800059fa  jz      loc_180005C25
0x180005a00  mov     r8d, dword ptr [rbp+190h+pvt]
  ... truncated ...
```
