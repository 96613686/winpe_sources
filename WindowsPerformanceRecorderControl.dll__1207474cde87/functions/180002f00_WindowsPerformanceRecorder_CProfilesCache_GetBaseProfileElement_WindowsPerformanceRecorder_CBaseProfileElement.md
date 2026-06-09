# WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElement(WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *,ushort const *,WindowsPerformanceRecorder::CBaseProfileElement::CElementType,WindowsPerformanceRecorder::CBaseProfileElement * *)

- ea: `0x180002f00`
- end: `0x18000395b`
- name: `?GetBaseProfileElement@CProfilesCache@WindowsPerformanceRecorder@@QEAAJPEAUCBaseProfileElementCollection@CBaseProfileElement@2@PEBGW4CElementType@42@PEAPEAV42@@Z`
- size: `2651`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001b40`
- `0x180002244`
- `0x18000485c`
- `0x180005040`
- `0x180007400`
- `0x180015c6c`
- `0x180016104`
- `0x180017ae4`
- `0x180048734`
- `0x1800692a8`
- `0x18006965c`
- `0x18006999c`
- `0x18006a090`
- `0x18006a9a4`

## callees

- `0x180002f00`
- `0x18000e340`
- `0x18000eeb0`
- `0x1800103c0`
- `0x180016f5c`
- `0x18001c458`
- `0x18001e6e0`
- `0x1800218a8`
- `0x180022634`
- `0x180026b30`
- `0x18002ce90`
- `0x180044210`
- `0x18004ece0`
- `0x1800709b0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002fbb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002fbb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800038b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800038b3`
- `OLEAUT32!__imp_SysAllocString` at `0x180003271`
- `OLEAUT32!__imp_SysAllocString` at `0x180003271`
- `OLEAUT32!__imp_SysFreeString` at `0x180003268`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003315`
- `OLEAUT32!__imp_SysFreeString` at `0x180003481`
- `OLEAUT32!__imp_SysFreeString` at `0x180003268`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003315`
- `OLEAUT32!__imp_SysFreeString` at `0x180003481`

## string_xrefs

- `0x18000329d`: `COMGUARD`
- `0x180003342`: `COMGUARD`
- `0x1800035f5`: `COMGUARD`
- `0x18000357e`: `WPRControlMinimalBuiltinProfiles.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElement(
        WindowsPerformanceRecorder::CProfilesCache *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        BSTR *a5)
{
  WindowsPerformanceRecorder::CProfilesCache *v6; // r12
  unsigned __int16 *v7; // r15
  BSTR v8; // rcx
  WCHAR *v9; // r13
  OLECHAR *v10; // rsi
  wchar_t *v11; // rax
  __int64 v12; // r14
  unsigned int v13; // ebx
  OLECHAR *v14; // rbx
  __int64 v15; // rax
  OLECHAR *v16; // rcx
  volatile signed __int32 *v17; // r12
  __int64 v18; // r15
  BSTR v20; // rbx
  __int64 v21; // r13
  signed __int32 v22; // ecx
  bool v23; // cc
  volatile signed __int32 *v24; // rsi
  unsigned __int16 *v25; // rdx
  volatile signed __int32 *v26; // r14
  OLECHAR *v27; // rbx
  signed int ProfileFromFileOrString; // eax
  unsigned int v29; // r12d
  signed int v30; // eax
  __int64 v31; // rcx
  unsigned int v32; // ebx
  BSTR v33; // r9
  __int64 v34; // rcx
  BSTR v35; // rbx
  int v36; // eax
  ATL::CStringData *v37; // rcx
  __int64 v38; // rbx
  OLECHAR *v39; // rcx
  ATL::CStringData *v40; // rdx
  _QWORD *v41; // r15
  unsigned __int64 v42; // rbx
  OLECHAR *v43; // r12
  __int64 v44; // rax
  WCHAR *v45; // rcx
  __int64 v46; // rax
  int v47; // edx
  int v48; // r8d
  const unsigned __int16 *v49; // rdx
  __int64 v50; // r8
  unsigned __int16 *v51; // rbx
  __int64 v52; // r8
  BSTR *v53; // r14
  signed int BuiltInProfileFile; // eax
  int ProfileElementsFromCache; // r15d
  int v56; // eax
  __int64 v57; // rcx
  BSTR v58; // r9
  BSTR v59; // r14
  int v60; // eax
  __int64 v61; // rax
  int v62; // eax
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-120h]
  BSTR bstrString; // [rsp+30h] [rbp-118h] BYREF
  unsigned int v65; // [rsp+38h] [rbp-110h]
  wchar_t *Str; // [rsp+40h] [rbp-108h] BYREF
  unsigned __int16 *v67; // [rsp+48h] [rbp-100h] BYREF
  unsigned __int64 v68; // [rsp+50h] [rbp-F8h] BYREF
  WindowsPerformanceRecorder::CProfilesCache *v69; // [rsp+58h] [rbp-F0h]
  BSTR *v70; // [rsp+60h] [rbp-E8h]
  __int64 v71; // [rsp+68h] [rbp-E0h]
  ATL::CStringData *v72; // [rsp+70h] [rbp-D8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v74; // [rsp+88h] [rbp-C0h]
  ATL::CAtlException *v75; // [rsp+90h] [rbp-B8h] BYREF
  ATL::CAtlException *v76; // [rsp+98h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v77; // [rsp+B0h] [rbp-98h] BYREF
  char *v78; // [rsp+C0h] [rbp-88h]
  int v79; // [rsp+C8h] [rbp-80h]
  int v80; // [rsp+CCh] [rbp-7Ch]
  unsigned __int64 *v81; // [rsp+D0h] [rbp-78h]
  __int64 v82; // [rsp+D8h] [rbp-70h]
  const unsigned __int8 *v83; // [rsp+E0h] [rbp-68h]
  __int64 v84; // [rsp+E8h] [rbp-60h]
  WCHAR *v85; // [rsp+F0h] [rbp-58h]
  int v86; // [rsp+F8h] [rbp-50h]
  int v87; // [rsp+FCh] [rbp-4Ch]

  v74 = -2;
  v65 = a4;
  v71 = a2;
  v6 = a1;
  v69 = a1;
  v70 = a5;
  v7 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v67 = v7;
  Str = (wchar_t *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Str, a3);
  v9 = Str;
  v10 = Str - 12;
  if ( *((int *)Str - 4) > 0 )
  {
    v11 = wcschr(Str, 0x21u);
    if ( v11 )
    {
      v12 = v11 - v9;
      if ( (_DWORD)v12 != -1 )
      {
        v13 = 0;
        if ( (int)v12 >= 0 )
          v13 = v11 - v9;
        if ( (signed int)v13 < *((_DWORD *)v9 - 4) )
        {
          if ( !*(_QWORD *)v10
            || (v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 32LL))(*(_QWORD *)v10)) == 0 )
          {
            v15 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
          }
          ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&bstrString, v9, v13, v15);
          v14 = bstrString;
        }
        else
        {
          v14 = (OLECHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(v10) + 24);
          bstrString = v14;
        }
        v16 = v14 - 12;
        v17 = (volatile signed __int32 *)(v7 - 12);
        if ( v14 - 12 != v7 - 12 )
        {
          if ( *((int *)v17 + 4) >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
          {
            v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
            if ( _InterlockedExchangeAdd(v17 + 4, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17, v17);
            v7 = (unsigned __int16 *)(v18 + 24);
            v67 = v7;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&v67, v14, *((_DWORD *)v14 - 4));
            v7 = v67;
          }
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
        if ( !*((_DWORD *)v7 - 4) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10, v10);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
          return 3310880513LL;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          &Str,
          &bstrString);
        v20 = bstrString;
        v8 = bstrString - 12;
        if ( bstrString - 12 != v10 )
        {
          if ( *((int *)v10 + 4) >= 0 && *(_QWORD *)v8 == *(_QWORD *)v10 )
          {
            v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v8);
            v22 = _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 4, 0xFFFFFFFF);
            v23 = v22 <= 1;
            v8 = (BSTR)(unsigned int)(v22 - 1);
            if ( v23 )
              (*(void (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10, v10);
            v9 = (WCHAR *)(v21 + 24);
            Str = v9;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&Str, bstrString, *((_DWORD *)bstrString - 4));
            v9 = Str;
          }
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v20 - 3) + 8LL))(*((_QWORD *)v20 - 3));
        v6 = v69;
      }
    }
  }
  v24 = (volatile signed __int32 *)(v9 - 12);
  if ( !*((_DWORD *)v9 - 4) )
  {
    if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
    v25 = v7 - 12;
LABEL_108:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 4, 0xFFFFFFFF) > 1 )
      return 3310880513LL;
    v34 = *(_QWORD *)v25;
    goto LABEL_110;
  }
  v26 = (volatile signed __int32 *)(v7 - 12);
  if ( !*((_DWORD *)v7 - 4) )
  {
LABEL_71:
    bstrString = 0;
    v38 = v71;
    if ( (int)WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElementById(v8, &bstrString, v9, v71) < 0 )
    {
      *(_QWORD *)&EventDescriptor.Id = v9 - 12;
      v39 = (OLECHAR *)*((_QWORD *)v6 + 3);
      bstrString = v39;
      v40 = (ATL::CStringData *)*((_QWORD *)v6 + 4);
      v72 = v40;
      if ( v39 == (OLECHAR *)v40 )
        goto LABEL_132;
      while ( 2 )
      {
        v41 = *(_QWORD **)v39;
        if ( v38 == *(_QWORD *)v39 || !v9 )
          goto LABEL_84;
        v68 = v41[1];
        v42 = 0;
        if ( !v68 )
          goto LABEL_83;
        do
        {
          if ( v42 >= v41[1] )
            ATL::AtlThrowImpl(-2147024809);
          v43 = *(OLECHAR **)(*v41 + 8 * v42);
          v44 = (*(__int64 (__fastcall **)(OLECHAR *))(*(_QWORD *)v43 + 16LL))(v43);
          v45 = v9;
          v46 = v44 - (_QWORD)v9;
          do
          {
            v47 = *(WCHAR *)((char *)v45 + v46);
            v48 = *v45 - v47;
            if ( v48 )
              break;
            ++v45;
          }
          while ( v47 );
          if ( !v48 )
          {
            v56 = (*(__int64 (__fastcall **)(OLECHAR *))(*(_QWORD *)v43 + 8LL))(v43);
            if ( v65 != v56 )
              goto LABEL_60;
            *v70 = v43;
            goto LABEL_67;
          }
          ++v42;
        }
        while ( v42 < v68 );
        v39 = bstrString;
        v40 = v72;
LABEL_83:
        v38 = v71;
LABEL_84:
        v39 += 4;
        bstrString = v39;
        if ( v39 != (OLECHAR *)v40 )
          continue;
        break;
      }
      v6 = v69;
LABEL_132:
      try
      {
        v49 = L"WPRControlMinimalBuiltinProfiles.xml";
        if ( !WindowsPerformanceRecorder::CProfilesCache::sc_fUseMinimalBuiltInProfiles )
          v49 = (const unsigned __int16 *)&WindowsPerformanceRecorder::CProfilesCache::sc_WPRControlBuiltInProfileFileName;
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, v49);
      }
      catch ( ATL::CAtlException *v76 )
      {
        v65 = *(_DWORD *)v76;
        ATL::CStringData::Release(*(ATL::CStringData **)&EventDescriptor.Id);
        v37 = (ATL::CStringData *)(v67 - 12);
        goto LABEL_126;
      }
      bstrString = 0;
      LOBYTE(v50) = 1;
      v51 = v67;
      v53 = (BSTR *)((char *)v6 + 8);
      if ( (int)WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(v6, v67, v50, &bstrString) < 0
        || bstrString == *v53 )
      {
        BuiltInProfileFile = WindowsPerformanceRecorder::CProfilesCache::LoadBuiltInProfileFile(v6, v51);
        ProfileElementsFromCache = BuiltInProfileFile;
        if ( BuiltInProfileFile < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"GetBaseProfileElement",
            (const char *)0x54B,
            BuiltInProfileFile,
            "COMGUARD",
            (const char *)UserData);
          if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
            goto LABEL_93;
          goto LABEL_94;
        }
      }
      bstrString = 0;
      LOBYTE(v52) = 1;
      ProfileElementsFromCache = WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(
                                   v6,
                                   v51,
                                   v52,
                                   &bstrString);
      if ( ProfileElementsFromCache < 0 )
      {
        if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
LABEL_93:
          (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
LABEL_94:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v51 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v51 - 3) + 8LL))(*((_QWORD *)v51 - 3));
        return (unsigned int)ProfileElementsFromCache;
      }
      v58 = bstrString;
      if ( bstrString == *v53
        || (bstrString = 0,
            (int)WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElementById(
                   v57,
                   &bstrString,
                   v9,
                   *((_QWORD *)v58 + 6)) < 0)
        || (v59 = bstrString,
            v60 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString),
            v65 != v60) )
      {
        if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
        v25 = v51 - 12;
        goto LABEL_108;
      }
      *v70 = v59;
      if ( (unsigned int)dword_1800BDC60 > 1
        && (qword_1800BDC70 & 0x200000001000LL) != 0
        && (qword_1800BDC78 & 0x200000001000LL) == qword_1800BDC78 )
      {
        v68 = 0x2000000;
        if ( v9 )
        {
          v61 = -1;
          do
            ++v61;
          while ( v9[v61] );
          v62 = 2 * v61 + 2;
        }
        else
        {
          v9 = (WCHAR *)&LocaleName;
          v62 = 2;
        }
        v85 = v9;
        v86 = v62;
        v87 = 0;
        v83 = "GetBaseProfileElement";
        v84 = 22;
        v81 = &v68;
        v82 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 1;
        EventDescriptor.Keyword = 0x200000001000LL;
        v77.Ptr = (ULONGLONG)off_1800BDC68;
        v77.Size = (unsigned __int16)*off_1800BDC68;
        v77.Reserved = 2;
        v78 = byte_1800A550B;
        v79 = 48;
        v80 = 1;
        v65 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &v77);
      }
      if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v51 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v51 - 3) + 8LL))(*((_QWORD *)v51 - 3));
      return 0;
    }
LABEL_65:
    v35 = bstrString;
    v36 = (*(__int64 (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
    if ( v65 != v36 )
      goto LABEL_60;
    *v70 = v35;
LABEL_67:
    if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
    if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) <= 1 )
    {
      (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26, v26);
      return 0;
    }
    return 0;
  }
  v72 = (ATL::CStringData *)(v9 - 12);
  v68 = (unsigned __int64)(v7 - 12);
  bstrString = 0;
  if ( (int)WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(v6, v7, 0, &bstrString) < 0
    || bstrString == *((BSTR *)v6 + 1) )
  {
    v27 = 0;
    bstrString = 0;
    if ( v7 )
    {
      SysFreeString(0);
      v27 = SysAllocString(v7);
      bstrString = v27;
      if ( !v27 )
      {
        try
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        catch ( ATL::CAtlException *v75 )
        {
          v65 = *(_DWORD *)v75;
          SysFreeString(bstrString);
          ATL::CStringData::Release(v72);
          v37 = (ATL::CStringData *)v68;
LABEL_126:
          ATL::CStringData::Release(v37);
          return v65;
        }
      }
    }
    ProfileFromFileOrString = WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(
                                (char ***)v6,
                                v27,
                                1);
    v29 = ProfileFromFileOrString;
    if ( ProfileFromFileOrString < 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"GetBaseProfileElement",
        (const char *)0x4F7,
        ProfileFromFileOrString,
        "COMGUARD",
        (const char *)UserData);
      SysFreeString(v27);
      if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
      if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26, v7 - 12);
      return v29;
    }
    SysFreeString(v27);
    v6 = v69;
  }
  bstrString = 0;
  v30 = WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(v6, v7, 0, &bstrString);
  v32 = v30;
  if ( v30 >= 0 )
  {
    v33 = bstrString;
    if ( bstrString == *((BSTR *)v6 + 1) )
    {
LABEL_60:
      if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
      if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) > 1 )
        return 3310880513LL;
      v34 = *(_QWORD *)v26;
      v25 = (unsigned __int16 *)v26;
LABEL_110:
      (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v34 + 8LL))(v34, v25);
      return 3310880513LL;
    }
    bstrString = 0;
    if ( (int)WindowsPerformanceRecorder::CProfilesCache::GetBaseProfileElementById(
                v31,
                &bstrString,
                v9,
                *((_QWORD *)v33 + 6)) >= 0 )
      goto LABEL_65;
    goto LABEL_71;
  }
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)2,
    (unsigned __int8)"GetBaseProfileElement",
    (const char *)0x4FB,
    v30,
    "COMGUARD",
    (const char *)UserData);
  if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, WCHAR *))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24, v9 - 12);
  if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26, v7 - 12);
  return v32;
}

```

## disassembly

```asm
0x180002f00  push    rbx
0x180002f02  push    rsi
0x180002f03  push    rdi
0x180002f04  push    r12
0x180002f06  push    r13
0x180002f08  push    r14
0x180002f0a  push    r15
0x180002f0c  sub     rsp, 110h
0x180002f13  mov     [rsp+148h+var_C0], 0FFFFFFFFFFFFFFFEh
0x180002f1f  mov     rax, cs:__security_cookie
0x180002f26  xor     rax, rsp
0x180002f29  mov     [rsp+148h+var_48], rax
0x180002f31  mov     [rsp+148h+var_110], r9d
0x180002f36  mov     rbx, r8
0x180002f39  mov     [rsp+148h+var_E0], rdx
0x180002f3e  mov     r12, rcx
0x180002f41  mov     [rsp+148h+var_F0], rcx
0x180002f46  mov     rax, [rsp+148h+arg_20]
0x180002f4e  mov     [rsp+148h+var_E8], rax
0x180002f53  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002f5a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002f61  mov     rax, [rax+18h]
0x180002f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6a  lea     r15, [rax+18h]
0x180002f6e  mov     [rsp+148h+var_100], r15
0x180002f73  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002f7a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180002f81  mov     rax, [rax+18h]
0x180002f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f8a  add     rax, 18h
0x180002f8e  mov     [rsp+148h+Str], rax
0x180002f93  mov     rdx, rbx
0x180002f96  lea     rcx, [rsp+148h+Str]
0x180002f9b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180002fa0  mov     r13, [rsp+148h+Str]
0x180002fa5  lea     rsi, [r13-18h]
0x180002fa9  cmp     dword ptr [rsi+8], 0
0x180002fad  jle     loc_180003203
0x180002fb3  mov     edx, 21h ; '!'; Ch
0x180002fb8  mov     rcx, r13; Str
0x180002fbb  call    cs:__imp_wcschr
0x180002fc1  mov     r14, rax
0x180002fc4  test    rax, rax
0x180002fc7  jz      loc_180003203
0x180002fcd  sub     r14, r13
0x180002fd0  sar     r14, 1
0x180002fd3  cmp     r14d, 0FFFFFFFFh
0x180002fd7  jz      loc_180003203
0x180002fdd  xor     ebx, ebx
0x180002fdf  test    r14d, r14d
0x180002fe2  cmovns  ebx, r14d
0x180002fe6  cmp     ebx, [r13-10h]
0x180002fea  jl      short loc_180002FFF
0x180002fec  mov     rcx, rsi
0x180002fef  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180002ff4  lea     rbx, [rax+18h]
0x180002ff8  mov     [rsp+148h+bstrString], rbx
0x180002ffd  jmp     short loc_180003047
0x180002fff  mov     rcx, [rsi]
0x180003002  test    rcx, rcx
0x180003005  jz      short loc_180003018
0x180003007  mov     rax, [rcx]
0x18000300a  mov     rax, [rax+20h]
0x18000300e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003013  test    rax, rax
0x180003016  jnz     short loc_18000302F
0x180003018  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000301f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180003026  mov     rax, [rax+20h]
0x18000302a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302f  mov     r9, rax
0x180003032  mov     r8d, ebx
0x180003035  mov     rdx, r13
0x180003038  lea     rcx, [rsp+148h+bstrString]
0x18000303d  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ushort const *,int,ATL::IAtlStringMgr *)
0x180003042  mov     rbx, [rsp+148h+bstrString]
0x180003047  mov     rdx, rbx
0x18000304a  lea     rcx, [rbx-18h]
0x18000304e  lea     r12, [r15-18h]
0x180003052  cmp     rcx, r12
0x180003055  jz      short loc_1800030B9
0x180003057  cmp     dword ptr [r12+10h], 0
0x18000305d  jl      short loc_1800030A6
0x18000305f  mov     rax, [r12]
0x180003063  cmp     [rcx], rax
0x180003066  jnz     short loc_1800030A6
0x180003068  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000306d  mov     r15, rax
0x180003070  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180003077  mov     ecx, edi
0x180003079  lock xadd [r12+10h], ecx
0x180003080  sub     ecx, 1
0x180003083  jg      short loc_18000309B
0x180003085  mov     r8, [r12]
0x180003089  mov     rcx, [r8]
0x18000308c  mov     rax, [rcx+8]
0x180003090  mov     rdx, r12
0x180003093  mov     rcx, r8
0x180003096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309b  add     r15, 18h
0x18000309f  mov     [rsp+148h+var_100], r15
0x1800030a4  jmp     short loc_1800030C0
0x1800030a6  mov     r8d, [rdx-10h]
0x1800030aa  lea     rcx, [rsp+148h+var_100]
0x1800030af  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800030b4  mov     r15, [rsp+148h+var_100]
0x1800030b9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800030c0  lea     rdx, [rbx-18h]
0x1800030c4  mov     eax, edi
0x1800030c6  lock xadd [rdx+10h], eax
0x1800030cb  sub     eax, 1
0x1800030ce  jg      short loc_1800030DF
0x1800030d0  mov     rcx, [rdx]
0x1800030d3  mov     rax, [rcx]
0x1800030d6  mov     rax, [rax+8]
0x1800030da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030df  cmp     dword ptr [r15-10h], 0
0x1800030e4  jnz     short loc_18000312C
0x1800030e6  mov     eax, edi
0x1800030e8  lock xadd [rsi+10h], eax
0x1800030ed  sub     eax, 1
0x1800030f0  jg      short loc_180003105
0x1800030f2  mov     rcx, [rsi]
0x1800030f5  mov     rax, [rcx]
0x1800030f8  mov     rdx, rsi
0x1800030fb  mov     rax, [rax+8]
0x1800030ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003104  nop
0x180003105  lea     rdx, [r15-18h]
0x180003109  lock xadd [rdx+10h], edi
0x18000310e  sub     edi, 1
0x180003111  jg      short loc_180003122
0x180003113  mov     rcx, [rdx]
0x180003116  mov     rax, [rcx]
0x180003119  mov     rax, [rax+8]
0x18000311d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003122  mov     eax, 0C5580701h
0x180003127  jmp     loc_180003922
0x18000312c  lea     r8d, [r14+1]
0x180003130  mov     r9d, [r13-10h]
0x180003134  sub     r9d, r8d
0x180003137  lea     rdx, [rsp+148h+bstrString]; void *
0x18000313c  lea     rcx, [rsp+148h+Str]; void *
0x180003141  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180003146  nop
0x180003147  mov     rbx, [rsp+148h+bstrString]
0x18000314c  lea     rcx, [rbx-18h]
0x180003150  cmp     rcx, rsi
0x180003153  jz      short loc_1800031AD
0x180003155  cmp     dword ptr [rsi+10h], 0
0x180003159  jl      short loc_180003197
0x18000315b  mov     rax, [rsi]
0x18000315e  cmp     [rcx], rax
0x180003161  jnz     short loc_180003197
0x180003163  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180003168  mov     r13, rax
0x18000316b  mov     ecx, edi
0x18000316d  lock xadd [rsi+10h], ecx
0x180003172  sub     ecx, 1
0x180003175  jg      short loc_18000318C
0x180003177  mov     r8, [rsi]
0x18000317a  mov     rcx, [r8]
0x18000317d  mov     rax, [rcx+8]
0x180003181  mov     rdx, rsi
0x180003184  mov     rcx, r8
0x180003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318c  add     r13, 18h
0x180003190  mov     [rsp+148h+Str], r13
0x180003195  jmp     short loc_1800031AD
0x180003197  mov     r8d, [rbx-10h]
0x18000319b  mov     rdx, rbx
0x18000319e  lea     rcx, [rsp+148h+Str]
0x1800031a3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800031a8  mov     r13, [rsp+148h+Str]
0x1800031ad  lea     rdx, [rbx-18h]
0x1800031b1  mov     eax, edi
0x1800031b3  lock xadd [rdx+10h], eax
0x1800031b8  sub     eax, 1
0x1800031bb  jg      short loc_1800031CC
0x1800031bd  mov     rcx, [rdx]
0x1800031c0  mov     rax, [rcx]
0x1800031c3  mov     rax, [rax+8]
0x1800031c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cc  mov     r12, [rsp+148h+var_F0]
0x1800031d1  lea     rsi, [r13-18h]
0x1800031d5  cmp     dword ptr [rsi+8], 0
0x1800031d9  jnz     short loc_18000320C
0x1800031db  mov     eax, edi
0x1800031dd  lock xadd [rsi+10h], eax
0x1800031e2  sub     eax, 1
0x1800031e5  jg      short loc_1800031FA
0x1800031e7  mov     rcx, [rsi]
0x1800031ea  mov     rax, [rcx]
0x1800031ed  mov     rdx, rsi
0x1800031f0  mov     rax, [rax+8]
0x1800031f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f9  nop
0x1800031fa  lea     rdx, [r15-18h]
0x1800031fe  jmp     loc_180003729
0x180003203  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000320a  jmp     short loc_1800031D1
0x18000320c  lea     r14, [r15-18h]
0x180003210  cmp     dword ptr [r14+8], 0
0x180003215  jz      loc_18000349D
0x18000321b  mov     [rsp+148h+var_D8], rsi
0x180003220  mov     [rsp+148h+var_F8], r14
0x180003225  mov     [rsp+148h+bstrString], 0
0x18000322e  lea     r9, [rsp+148h+bstrString]
0x180003233  xor     r8d, r8d
0x180003236  mov     rdx, r15
0x180003239  mov     rcx, r12
0x18000323c  call    ?GetProfileElementsFromCache@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEBG_NAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@std@@@std@@@std@@@Z; WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(ushort const *,bool,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>>> &)
0x180003241  test    eax, eax
0x180003243  js      short loc_18000325A
0x180003245  mov     rax, [r12+8]
0x18000324a  cmp     [rsp+148h+bstrString], rax
0x18000324f  setnz   al
0x180003252  test    al, al
0x180003254  jnz     loc_180003320
0x18000325a  xor     ebx, ebx
0x18000325c  mov     [rsp+148h+bstrString], rbx
0x180003261  test    r15, r15
0x180003264  jz      short loc_180003288
0x180003266  xor     ecx, ecx; bstrString
0x180003268  call    cs:__imp_SysFreeString
0x18000326e  mov     rcx, r15; psz
0x180003271  call    cs:__imp_SysAllocString
0x180003277  mov     rbx, rax
0x18000327a  mov     [rsp+148h+bstrString], rax
0x18000327f  test    rax, rax
0x180003282  jz      loc_180003945
0x180003288  mov     r8b, 1; bool
0x18000328b  mov     rdx, rbx; unsigned __int16 *
0x18000328e  mov     rcx, r12; this
0x180003291  call    ?LoadProfileFromFileOrString@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEAG_N@Z; WindowsPerformanceRecorder::CProfilesCache::LoadProfileFromFileOrString(ushort *,bool)
0x180003296  mov     r12d, eax
0x180003299  test    eax, eax
0x18000329b  jns     short loc_180003312
0x18000329d  lea     rcx, aComguard; "COMGUARD"
0x1800032a4  mov     qword ptr [rsp+148h+UserDataCount], rcx; Format
0x1800032a9  mov     r9d, eax; unsigned int
0x1800032ac  mov     r8d, 4F7h; char *
0x1800032b2  lea     rdx, aGetbaseprofile; "GetBaseProfileElement"
0x1800032b9  mov     ecx, 2; this
0x1800032be  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800032c3  nop
0x1800032c4  mov     rcx, rbx; bstrString
0x1800032c7  call    cs:__imp_SysFreeString
0x1800032cd  nop
0x1800032ce  mov     eax, edi
0x1800032d0  lock xadd [rsi+10h], eax
0x1800032d5  sub     eax, 1
0x1800032d8  jg      short loc_1800032ED
0x1800032da  mov     rcx, [rsi]
0x1800032dd  mov     rax, [rcx]
0x1800032e0  mov     rdx, rsi
0x1800032e3  mov     rax, [rax+8]
0x1800032e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ec  nop
0x1800032ed  lock xadd [r14+10h], edi
0x1800032f3  sub     edi, 1
0x1800032f6  jg      short loc_18000330A
0x1800032f8  mov     rcx, [r14]
0x1800032fb  mov     rax, [rcx]
0x1800032fe  mov     rdx, r14
0x180003301  mov     rax, [rax+8]
0x180003305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330a  mov     eax, r12d
0x18000330d  jmp     loc_180003922
0x180003312  mov     rcx, rbx; bstrString
0x180003315  call    cs:__imp_SysFreeString
0x18000331b  mov     r12, [rsp+148h+var_F0]
0x180003320  mov     [rsp+148h+bstrString], 0
0x180003329  lea     r9, [rsp+148h+bstrString]
0x18000332e  xor     r8d, r8d
0x180003331  mov     rdx, r15
0x180003334  mov     rcx, r12
0x180003337  call    ?GetProfileElementsFromCache@CProfilesCache@WindowsPerformanceRecorder@@AEAAJPEBG_NAEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUCFileKey@Impl@WindowsPerformanceRecorder@@PEAUCBaseProfileElementCollection@CBaseProfileElement@3@@std@@@std@@@std@@@std@@@Z; WindowsPerformanceRecorder::CProfilesCache::GetProfileElementsFromCache(ushort const *,bool,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::Impl::CFileKey const,WindowsPerformanceRecorder::CBaseProfileElement::CBaseProfileElementCollection *>>>> &)
0x18000333c  mov     ebx, eax
0x18000333e  test    eax, eax
0x180003340  jns     short loc_1800033AC
0x180003342  lea     rcx, aComguard; "COMGUARD"
0x180003349  mov     qword ptr [rsp+148h+UserDataCount], rcx; Format
0x18000334e  mov     r9d, eax; unsigned int
0x180003351  mov     r8d, 4FBh; char *
0x180003357  lea     rdx, aGetbaseprofile; "GetBaseProfileElement"
0x18000335e  mov     ecx, 2; this
0x180003363  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180003368  nop
0x180003369  mov     eax, edi
0x18000336b  lock xadd [rsi+10h], eax
0x180003370  sub     eax, 1
0x180003373  jg      short loc_180003388
0x180003375  mov     rcx, [rsi]
0x180003378  mov     rax, [rcx]
0x18000337b  mov     rdx, rsi
0x18000337e  mov     rax, [rax+8]
0x180003382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003387  nop
0x180003388  lock xadd [r14+10h], edi
  ... truncated ...
```
