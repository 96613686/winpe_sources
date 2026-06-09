# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(ulong,EtwProviderConfigWithFilter *)

- ea: `0x180022ae4`
- end: `0x180023828`
- name: `?AddProvidersWithFilters_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJKPEAUEtwProviderConfigWithFilter@@@Z`
- size: `3396`
- prototype: `__int64 __fastcall(struct _GUID *this, unsigned int, struct EtwProviderConfigWithFilter *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c978`
- `0x18001e5b0`

## callees

- `0x180009298`
- `0x180010120`
- `0x180010540`
- `0x18001a578`
- `0x18001a798`
- `0x18001a818`
- `0x180020338`
- `0x180020c74`
- `0x180020ccc`
- `0x180022ae4`
- `0x180023828`
- `0x180023bb0`
- `0x180023f74`
- `0x180024fd0`
- `0x180025444`
- `0x1800263f8`
- `0x180026d84`
- `0x18003d864`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180049b50`
- `0x18004a03c`
- `0x18004ad26`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180022b5f`
- `VCRUNTIME140!memcmp` at `0x180023074`
- `VCRUNTIME140!memcmp` at `0x18002309d`
- `VCRUNTIME140!memcmp` at `0x1800230cf`
- `VCRUNTIME140!memcmp` at `0x180022b5f`
- `VCRUNTIME140!memcmp` at `0x180023074`
- `VCRUNTIME140!memcmp` at `0x18002309d`
- `VCRUNTIME140!memcmp` at `0x1800230cf`
- `KERNEL32!WaitForSingleObject` at `0x180022c29`
- `KERNEL32!WaitForSingleObject` at `0x180022c29`
- `KERNEL32!Sleep` at `0x180022df9`
- `KERNEL32!Sleep` at `0x180022df9`
- `ole32!StringFromGUID2` at `0x180022f98`
- `ole32!StringFromGUID2` at `0x180023343`
- `ole32!StringFromGUID2` at `0x180022f98`
- `ole32!StringFromGUID2` at `0x180023343`

## string_xrefs

- `0x180022d16`: `Heap session cannot be configured to accept all events in a debugger collection session`
- `0x180022e52`: `Failed to enable the heap provider because it was already enabled.`
- `0x180022eff`: `Failed to enable the system provider on Win7 because it was already enabled.`
- `0x180022fd3`: `Failed to enable provider %s because it was already enabled in %d sessions.`
- `0x18002336b`: `Skipping configuration for provider: %s. Invalid configuration type.`
- `0x180022bc3`: `Invalid ETW session type combination: %d - %d`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(
        struct _GUID *this,
        unsigned int a2,
        struct EtwProviderConfigWithFilter *a3)
{
  signed int v4; // esi
  unsigned int v5; // r14d
  char *v6; // r15
  unsigned int SessionType; // eax
  int started; // ebx
  unsigned __int8 *Data4; // r14
  __int64 v10; // rcx
  void *v11; // rcx
  __int64 result; // rax
  __int64 v13; // rax
  int v14; // ebx
  int v15; // edi
  int v16; // esi
  int v17; // r14d
  int v18; // r15d
  GUID *v19; // rdx
  struct _GUID *v20; // rcx
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v21; // rax
  unsigned int v22; // edx
  unsigned int Data1; // ecx
  DWORD v24; // eax
  const unsigned __int16 *v25; // r8
  const struct _GUID *v26; // rdx
  struct _GUID *v27; // rax
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v28; // rbx
  void (__fastcall **v29)(_QWORD); // rax
  void *v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // r8
  volatile signed __int32 *v33; // r12
  __int64 v34; // rdx
  __int64 v35; // rcx
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v36; // rdx
  volatile signed __int32 *v37; // rbx
  __int64 v38; // rcx
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v39; // r10
  const GUID *v40; // r9
  int v41; // edx
  int v42; // edx
  int v43; // edx
  int v44; // edx
  int v45; // edx
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v46; // rdi
  _QWORD *v47; // rax
  unsigned __int64 v48; // rdx
  int v49; // esi
  int updated; // edi
  int v51; // eax
  unsigned int v52; // [rsp+30h] [rbp-1B8h]
  unsigned int v53; // [rsp+30h] [rbp-1B8h]
  unsigned int v54; // [rsp+30h] [rbp-1B8h]
  GUID *rguid; // [rsp+38h] [rbp-1B0h]
  GUID *rguida; // [rsp+38h] [rbp-1B0h]
  struct _GUID *v57[2]; // [rsp+40h] [rbp-1A8h] BYREF
  bool v58; // [rsp+50h] [rbp-198h]
  unsigned int v59; // [rsp+54h] [rbp-194h]
  struct _GUID *v60; // [rsp+58h] [rbp-190h]
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v61[2]; // [rsp+60h] [rbp-188h] BYREF
  struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *v62[2]; // [rsp+70h] [rbp-178h] BYREF
  unsigned int v63; // [rsp+80h] [rbp-168h]
  int v64; // [rsp+84h] [rbp-164h]
  __int64 v65; // [rsp+88h] [rbp-160h]
  int pExceptionObject; // [rsp+90h] [rbp-158h] BYREF
  int v67; // [rsp+94h] [rbp-154h] BYREF
  struct EtwProviderConfigWithFilter *v68; // [rsp+98h] [rbp-150h]
  unsigned __int8 *v69; // [rsp+A0h] [rbp-148h]
  char v70[16]; // [rsp+A8h] [rbp-140h] BYREF
  char v71[24]; // [rsp+B8h] [rbp-130h] BYREF
  OLECHAR sz[8]; // [rsp+D0h] [rbp-118h] BYREF
  char v73; // [rsp+E0h] [rbp-108h]
  int v74; // [rsp+E4h] [rbp-104h]
  __int64 v75; // [rsp+E8h] [rbp-100h]
  __int64 v76; // [rsp+F0h] [rbp-F8h]
  char v77; // [rsp+F8h] [rbp-F0h]
  int v78; // [rsp+FCh] [rbp-ECh]
  __int128 v79; // [rsp+100h] [rbp-E8h]
  char v80[14]; // [rsp+110h] [rbp-D8h] BYREF
  __int16 v81; // [rsp+11Eh] [rbp-CAh]
  char v82[24]; // [rsp+128h] [rbp-C0h] BYREF
  int v83; // [rsp+140h] [rbp-A8h] BYREF
  _QWORD *v84; // [rsp+148h] [rbp-A0h]
  __int64 v85; // [rsp+150h] [rbp-98h]
  __int64 v86; // [rsp+158h] [rbp-90h] BYREF
  __int128 v87; // [rsp+160h] [rbp-88h]
  __int64 v88; // [rsp+170h] [rbp-78h]
  __int64 v89; // [rsp+178h] [rbp-70h]
  __int128 v90; // [rsp+180h] [rbp-68h]
  __int128 v91; // [rsp+190h] [rbp-58h]

  v68 = a3;
  v63 = a2;
  v60 = this;
  v4 = -1;
  v59 = -1;
  v5 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v6 = (char *)a3 + 56 * v5;
      if ( !memcmp(v6, &GUID_NULL, 0x10u) )
        goto LABEL_14;
      SessionType = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetSessionType(v6);
      if ( v4 == -1 )
      {
        v4 = SessionType;
        v59 = SessionType;
      }
      else if ( v4 != SessionType && (v4 != 1 || SessionType != 3) )
      {
        if ( v4 != 3 || SessionType != 1 )
        {
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"Invalid ETW session type combination: %d - %d",
            (unsigned int)v4,
            SessionType);
LABEL_14:
          started = -2147024809;
LABEL_24:
          _mm_lfence();
          return (unsigned int)started;
        }
        v4 = 1;
        v59 = 1;
      }
      if ( ++v5 >= v63 )
        break;
      a3 = v68;
    }
  }
  Data4 = this[8 * (__int64)v4 + 178].Data4;
  v69 = Data4;
  if ( LOBYTE(this[54].Data1) )
  {
    if ( !*(_QWORD *)Data4
      || (v10 = *((_QWORD *)Data4 + 1)) == 0
      || !*(_QWORD *)(*(_QWORD *)Data4 + 16LL)
      || (v11 = *(void **)(v10 + 32)) == 0
      || !WaitForSingleObject(v11, 0) )
    {
      started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(
                  (__int64)this,
                  v4,
                  (__int64)this[8 * (__int64)v4 + 178].Data4);
      if ( started < 0 )
        goto LABEL_24;
      if ( Data4[104] )
      {
        _mm_lfence();
        started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(
                    (__int64)this,
                    v4);
        if ( started < 0 )
          goto LABEL_24;
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD, unsigned __int8 *))(**(_QWORD **)&this[245].Data1 + 24LL))(
          *(_QWORD *)&this[245].Data1,
          this[165].Data4);
      }
    }
  }
  v13 = 0;
  v14 = HIDWORD(v61[1]);
  v15 = HIDWORD(v61[1]);
  v16 = HIDWORD(v61[1]);
  v17 = HIDWORD(v61[1]);
  v18 = HIDWORD(v61[1]);
  while ( 1 )
  {
    v64 = v13;
    if ( (unsigned int)v13 >= v63 )
      return 0;
    v19 = (GUID *)((char *)v68 + 56 * v13);
    rguid = v19;
    if ( *(_DWORD *)&v19[1].Data2 == 2 || *(_DWORD *)&v19[1].Data2 == 5 )
    {
      v20 = v60;
      if ( !LOBYTE(v60[54].Data1) )
        return 2147942487LL;
    }
    else
    {
      v20 = v60;
    }
    if ( LOBYTE(v20[246].Data1) && v59 == 1 && (v19[1].Data1 & 4) != 0 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Heap session cannot be configured to accept all events in a debugger collection session");
      return 2147942487LL;
    }
    if ( !v20[44].Data4[0] && (v19[1].Data1 & 1) == 0 )
      return 3775987799LL;
    *(_OWORD *)v61 = 0;
    v62[0] = 0;
    std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(
      &v20[174],
      v62);
    v21 = v62[0];
    v58 = v62[0] == *(struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal **)v60[174].Data4;
    if ( v58 )
      break;
    v38 = *((_QWORD *)v62[0] + 5);
    if ( v38 )
      _InterlockedIncrement((volatile signed __int32 *)(v38 + 8));
    v39 = (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)*((_QWORD *)v21 + 4);
    v62[0] = v39;
    v33 = (volatile signed __int32 *)*((_QWORD *)v21 + 5);
    v61[0] = v39;
    v61[1] = (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)v33;
    v40 = rguid;
    v41 = *(_DWORD *)&rguid[1].Data2;
    if ( !v41 )
      goto LABEL_130;
    v42 = v41 - 1;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( !v43 )
        goto LABEL_109;
      v44 = v43 - 1;
      if ( !v44 )
      {
LABEL_130:
        v51 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::MergeKeywordsAndLevel(
                v39,
                *(_QWORD *)rguid[1].Data4,
                rguid[2].Data1);
        goto LABEL_131;
      }
      v45 = v44 - 1;
      if ( v45 )
      {
        if ( v45 == 1 )
        {
LABEL_109:
          memset_0(sz, 0, 0xD0u);
          v46 = v62[0];
          *(_OWORD *)sz = *(_OWORD *)v62[0];
          v73 = *((_BYTE *)v62[0] + 16);
          v74 = *((_DWORD *)v62[0] + 5);
          v75 = *((_QWORD *)v62[0] + 3);
          v76 = *((_QWORD *)v62[0] + 4);
          v77 = *((_BYTE *)v62[0] + 40);
          v78 = *((_DWORD *)v62[0] + 11);
          v79 = *((_OWORD *)v62[0] + 3);
          std::vector<unsigned char>::vector<unsigned char>(v80, (char *)v62[0] + 64);
          std::vector<unsigned char>::vector<unsigned char>(v82, (char *)v46 + 88);
          v69 = (unsigned __int8 *)&v83;
          v83 = *((_DWORD *)v46 + 28);
          v84 = 0;
          v85 = 0;
          v47 = operator new(0x18u);
          *v47 = v47;
          v47[1] = v47;
          v84 = v47;
          v86 = 0;
          v87 = 0;
          v88 = *((_QWORD *)v46 + 20);
          v89 = *((_QWORD *)v46 + 21);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
            &v86,
            (__int64)(*((_QWORD *)v46 + 18) - *((_QWORD *)v46 + 17)) >> 3,
            v47);
          std::_Hash<std::_Uset_traits<enum StackEventType,std::_Uhash_compare<enum StackEventType,std::hash<enum StackEventType>,std::equal_to<enum StackEventType>>,std::allocator<enum StackEventType>,0>>::_Insert_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum StackEventType>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum StackEventType>>,std::_Iterator_base0>>(
            &v83,
            **((_QWORD **)v46 + 15));
          v90 = *((_OWORD *)v46 + 11);
          v91 = *((_OWORD *)v46 + 12);
          v48 = *(_QWORD *)rguid[1].Data4;
          if ( v48
            && (v49 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::MergeKeywordsAndLevel(
                        (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)sz,
                        v48,
                        rguid[2].Data1),
                v49 < 0) )
          {
            _mm_lfence();
            Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::~EtwProviderConfigInternal((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)sz);
            if ( v33 )
            {
              if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
              }
            }
            return (unsigned int)v49;
          }
          else
          {
            std::_Hash<std::_Uset_traits<enum StackEventType,std::_Uhash_compare<enum StackEventType,std::hash<enum StackEventType>,std::equal_to<enum StackEventType>>,std::allocator<enum StackEventType>,0>>::clear(&v83);
            updated = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeEtwProviderConfigGenericProperties(
                        (struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)sz,
                        (unsigned __int8 **)rguid);
            if ( updated < 0
              || (_mm_lfence(),
                  updated = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(
                              v60,
                              v59,
                              (__int64)sz),
                  updated < 0) )
            {
              _mm_lfence();
              Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::~EtwProviderConfigInternal((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)sz);
              if ( v33 )
              {
                if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                  if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
                }
              }
              return (unsigned int)updated;
            }
            else
            {
              Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::~EtwProviderConfigInternal((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *)sz);
              if ( v33 )
              {
                if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                  if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
                }
              }
              return 0;
            }
          }
        }
        rguida = (GUID *)((char *)_logger + 112);
        if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
        {
          if ( !StringFromGUID2(v40, sz, 39) )
          {
            v67 = -2147024882;
            throw (long *)&v67;
          }
          v81 = 0;
          WORD6(v87) = 0;
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)rguida,
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
            L"Skipping configuration for provider: %s. Invalid configuration type.",
            sz);
        }
        goto LABEL_145;
      }
    }
    v51 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::MergeStackEvents(
            v39,
            *(_DWORD *)rguid[1].Data4,
            *(enum StackEventType **)&rguid[2].Data1);
LABEL_131:
    v54 = v51;
    if ( v51 < 0 )
    {
      _mm_lfence();
      if ( v33 && _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
        goto LABEL_134;
      return v54;
    }
    result = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeEtwProviderConfigGenericProperties(
               v62[0],
               (unsigned __int8 **)rguid);
    v54 = result;
    if ( (int)result < 0 )
      goto LABEL_137;
    v36 = v62[0];
    ++*((_DWORD *)v62[0] + 11);
LABEL_141:
    if ( !LOBYTE(v60[54].Data1) )
      goto LABEL_145;
    result = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(
               v60,
               v59,
               (__int64)v36);
    v54 = result;
    if ( (int)result < 0 )
    {
LABEL_137:
      _mm_lfence();
      if ( !v33 || _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) != 1 )
        return result;
LABEL_134:
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
      {
        v29 = *(void (__fastcall ***)(_QWORD))v33;
        v30 = (void *)v33;
LABEL_80:
        ((void (__fastcall **)(void *))v29)[1](v30);
      }
      return v54;
    }
    if ( v58 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v60[245].Data1 + 24LL))(*(_QWORD *)&v60[245].Data1, rguid);
    }
LABEL_145:
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    v13 = (unsigned int)(v64 + 1);
  }
  if ( *(_DWORD *)&rguid[1].Data2 != 2 && *(_DWORD *)&rguid[1].Data2 != 5 )
  {
    if ( v59 == 1 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v60[245].Data1 + 40LL))(*(_QWORD *)&v60[245].Data1) )
        goto LABEL_65;
      _mm_lfence();
      v22 = 0;
      v52 = 0;
      Data1 = v60[224].Data1;
      LODWORD(v65) = Data1;
      if ( Data1 )
      {
        v24 = *(_DWORD *)&v60[223].Data4[4] / Data1;
        LODWORD(v62[0]) = v24;
        _mm_lfence();
        while ( 1 )
        {
          Sleep(v24);
          if ( !(*(unsigned int (__fastcall **)(_QWORD, GUID *))(**(_QWORD **)&v60[245].Data1 + 40LL))(
                  *(_QWORD *)&v60[245].Data1,
                  rguid) )
            break;
          v22 = v52 + 1;
          v52 = v22;
          Data1 = v65;
          v24 = (DWORD)v62[0];
          if ( v22 >= (unsigned int)v65 )
            goto LABEL_50;
        }
LABEL_65:
        v53 = 0;
        v57[0] = (struct _GUID *)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::IsEventFromTargetProcess;
        LODWORD(v57[1]) = 1048;
        HIDWORD(v57[1]) = v14;
        if ( v59 > 1 )
        {
          if ( !memcmp(rguid, qword_180056DA8, 0x10u) )
          {
            v27 = (struct _GUID *)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::IsExpectedStackwalkEvent;
            HIDWORD(v57[1]) = v16;
            goto LABEL_74;
          }
          if ( !memcmp(rguid, qword_180056D98, 0x10u) )
          {
            v27 = (struct _GUID *)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::IsExpectedImmersiveShellEvent;
            HIDWORD(v57[1]) = v17;
            goto LABEL_70;
          }
          if ( !memcmp(rguid, qword_180056D88, 0x10u) )
          {
            v27 = (struct _GUID *)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::IsExpectedDWMEvent;
            HIDWORD(v57[1]) = v18;
LABEL_70:
            v53 = 0x40000000;
LABEL_74:
            LODWORD(v57[1]) = 0;
            v57[0] = v27;
          }
          *(_OWORD *)v62 = *(_OWORD *)v57;
          result = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal::CreateFromUser(
                     (__int64)rguid,
                     v53,
                     (__int128 *)v62,
                     v61);
          v54 = result;
          if ( (int)result < 0
            || (_mm_lfence(),
                v62[0] = v61[0],
                result = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::MergeEtwProviderConfigGenericProperties(
                           v61[0],
                           (unsigned __int8 **)rguid),
                v54 = result,
                (int)result < 0) )
          {
            _mm_lfence();
            v28 = v61[1];
            if ( !v61[1] || _InterlockedExchangeAdd((volatile signed __int32 *)v61[1] + 2, 0xFFFFFFFF) != 1 )
              return result;
            (**(void (__fastcall ***)(struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal *))v28)(v28);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 3, 0xFFFFFFFF) == 1 )
            {
              v29 = *(void (__fastcall ***)(_QWORD))v28;
              v30 = v28;
              goto LABEL_80;
            }
            return v54;
          }
          _mm_lfence();
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            v31 = (__int64 *)std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal>>>,0>>::_Try_emplace<_GUID const &,>(
                               &v60[174],
                               v70,
                               rguid);
            _mm_lfence();
            v32 = *v31;
            v33 = (volatile signed __int32 *)v61[1];
            if ( v61[1] )
              _InterlockedIncrement((volatile signed __int32 *)v61[1] + 2);
            *(struct Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwProviderConfigInternal **)(v32 + 32) = v62[0];
            v65 = *(_QWORD *)(v32 + 40);
            v34 = v65;
            *(_QWORD *)(v32 + 40) = v33;
            if ( v34 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(__int64))v34)(v34);
                v35 = v65;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v65 + 12), 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
              }
            }
            std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::emplace<_GUID const &>(
              v69 + 16,
              v71,
              rguid);
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002325C);
              v37 = (volatile signed __int32 *)v61[1];
              if ( v61[1] )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v61[1] + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
                  if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
                }
              }
              return 2147942414LL;
            }
          }
          v36 = v62[0];
          goto LABEL_141;
        }
        v27 = (struct _GUID *)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::IsExpectedSystemEvent;
        HIDWORD(v57[1]) = v15;
        goto LABEL_74;
      }
LABEL_50:
      if ( v22 != Data1 )
        goto LABEL_65;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Failed to enable the heap provider because it was already enabled.");
      *(_OWORD *)v57 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)v57,
        -518979515,
        L"Heap",
        *(_WORD *)v60[43].Data4);
      v26 = (const struct _GUID *)L"<unknown error>";
      if ( v57[0] )
        v26 = v57[0];
    }
    else if ( !v60[223].Data4[2] || v59 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v60[245].Data1 + 40LL))(*(_QWORD *)&v60[245].Data1) < 8 )
        goto LABEL_65;
      _mm_lfence();
      if ( !StringFromGUID2(rguid, sz, 39) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      v81 = 0;
      WORD6(v87) = 0;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Failed to enable provider %s because it was already enabled in %d sessions.",
        sz,
        8);
      *(_OWORD *)v57 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)v57,
        -518979515,
        sz,
        *(_WORD *)v60[43].Data4);
      v26 = (const struct _GUID *)L"<unknown error>";
      if ( v57[0] )
        v26 = v57[0];
    }
    else
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v60[245].Data1 + 40LL))(*(_QWORD *)&v60[245].Data1) )
        goto LABEL_65;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"Failed to enable the system provider on Win7 because it was already enabled.");
      *(_OWORD *)v57 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)v57,
        -518979515,
        L"NT Kernel Session (Windows 7)",
        *(_WORD *)v60[43].Data4);
      v26 = (const struct _GUID *)L"<unknown error>";
      if ( v57[0] )
        v26 = v57[0];
    }
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v26, v25);
    started = (int)v57[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v57);
    return (unsigned int)started;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180022ae4  mov     [rsp+arg_8], rbx
0x180022ae9  mov     [rsp+arg_18], rsi
0x180022aee  push    rdi
0x180022aef  push    r12
0x180022af1  push    r13
0x180022af3  push    r14
0x180022af5  push    r15
0x180022af7  sub     rsp, 1C0h
0x180022afe  mov     rax, cs:__security_cookie
0x180022b05  xor     rax, rsp
0x180022b08  mov     [rsp+1E8h+var_38], rax
0x180022b10  mov     [rsp+1E8h+var_150], r8
0x180022b18  mov     [rsp+1E8h+var_168], edx
0x180022b1f  mov     rdi, rcx
0x180022b22  mov     [rsp+1E8h+var_190], rcx
0x180022b27  or      r13d, 0FFFFFFFFh
0x180022b2b  mov     esi, r13d
0x180022b2e  mov     [rsp+1E8h+var_194], r13d
0x180022b33  xor     r12d, r12d
0x180022b36  mov     r14d, r12d
0x180022b39  test    edx, edx
0x180022b3b  jz      loc_180022BE0
0x180022b41  lea     ebx, [r13+2]
0x180022b45  mov     eax, r14d
0x180022b48  imul    r15, rax, 38h ; '8'
0x180022b4c  add     r15, r8
0x180022b4f  mov     r8d, 10h; Size
0x180022b55  lea     rdx, GUID_NULL; Buf2
0x180022b5c  mov     rcx, r15; Buf1
0x180022b5f  call    cs:__imp_memcmp
0x180022b65  test    eax, eax
0x180022b67  jz      short loc_180022BD6
0x180022b69  mov     rcx, r15
0x180022b6c  call    ?GetSessionType@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@CA?AW4EtwSessionType@1234@AEBU_GUID@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetSessionType(_GUID const &)
0x180022b71  cmp     esi, r13d
0x180022b74  jnz     short loc_180022B7E
0x180022b76  mov     esi, eax
0x180022b78  mov     [rsp+1E8h+var_194], eax
0x180022b7c  jmp     short loc_180022B9A
0x180022b7e  cmp     esi, eax
0x180022b80  jz      short loc_180022B9A
0x180022b82  cmp     esi, ebx
0x180022b84  jnz     short loc_180022B8B
0x180022b86  cmp     eax, 3
0x180022b89  jz      short loc_180022B9A
0x180022b8b  cmp     esi, 3
0x180022b8e  jnz     short loc_180022BB1
0x180022b90  cmp     eax, ebx
0x180022b92  jnz     short loc_180022BB1
0x180022b94  mov     esi, ebx
0x180022b96  mov     [rsp+1E8h+var_194], ebx
0x180022b9a  add     r14d, ebx
0x180022b9d  cmp     r14d, [rsp+1E8h+var_168]
0x180022ba5  jnb     short loc_180022BE0
0x180022ba7  mov     r8, [rsp+1E8h+var_150]
0x180022baf  jmp     short loc_180022B45
0x180022bb1  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180022bb8  add     rcx, 38h ; '8'; this
0x180022bbc  mov     [rsp+1E8h+var_1C8], eax
0x180022bc0  mov     r9d, esi
0x180022bc3  lea     r8, aInvalidEtwSess; "Invalid ETW session type combination: %"...
0x180022bca  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180022bd1  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180022bd6  mov     ebx, 80070057h
0x180022bdb  jmp     loc_180022C69
0x180022be0  movsxd  r14, esi
0x180022be3  shl     r14, 7
0x180022be7  add     r14, 0B28h
0x180022bee  add     r14, rdi
0x180022bf1  mov     [rsp+1E8h+var_148], r14
0x180022bf9  mov     al, [rdi+360h]
0x180022bff  test    al, al
0x180022c01  jz      loc_180022C8D
0x180022c07  mov     rax, [r14]
0x180022c0a  test    rax, rax
0x180022c0d  jz      short loc_180022C33
0x180022c0f  mov     rcx, [r14+8]
0x180022c13  test    rcx, rcx
0x180022c16  jz      short loc_180022C33
0x180022c18  cmp     [rax+10h], r12
0x180022c1c  jz      short loc_180022C33
0x180022c1e  mov     rcx, [rcx+20h]; hHandle
0x180022c22  test    rcx, rcx
0x180022c25  jz      short loc_180022C33
0x180022c27  xor     edx, edx; dwMilliseconds
0x180022c29  call    cs:__imp_WaitForSingleObject
0x180022c2f  test    eax, eax
0x180022c31  jnz     short loc_180022C8D
0x180022c33  mov     r8, r14
0x180022c36  mov     edx, esi
0x180022c38  mov     rcx, rdi
0x180022c3b  call    ?CreateAndStartEtwSession@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJW4EtwSessionType@1234@AEAUEtwSessionInformation@1234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionType,Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &)
0x180022c40  mov     ebx, eax
0x180022c42  test    eax, eax
0x180022c44  js      short loc_180022C69
0x180022c46  cmp     [r14+68h], r12b
0x180022c4a  jz      short loc_180022C8D
0x180022c4c  lfence
0x180022c4f  lea     r14, [rdi+0A58h]
0x180022c56  mov     r8, r14
0x180022c59  mov     edx, esi
0x180022c5b  mov     rcx, rdi
0x180022c5e  call    ?UpdateEtwSession_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJW4EtwSessionType@1234@AEBU_GUID@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionType,_GUID const &)
0x180022c63  mov     ebx, eax
0x180022c65  test    eax, eax
0x180022c67  jns     short loc_180022C73
0x180022c69  lfence
0x180022c6c  mov     eax, ebx
0x180022c6e  jmp     loc_180023659
0x180022c73  lfence
0x180022c76  mov     rcx, [rdi+0F50h]
0x180022c7d  mov     rax, [rcx]
0x180022c80  mov     rdx, r14
0x180022c83  mov     rax, [rax+18h]
0x180022c87  call    cs:__guard_dispatch_icall_fptr
0x180022c8d  mov     eax, r12d
0x180022c90  mov     ebx, dword ptr [rsp+1E8h+var_188+0Ch]
0x180022c94  mov     edi, dword ptr [rsp+1E8h+var_188+0Ch]
0x180022c98  mov     esi, dword ptr [rsp+1E8h+var_188+0Ch]
0x180022c9c  mov     r14d, dword ptr [rsp+1E8h+var_188+0Ch]
0x180022ca1  mov     r15d, dword ptr [rsp+1E8h+var_188+0Ch]
0x180022ca6  mov     [rsp+1E8h+var_164], eax
0x180022cad  cmp     eax, [rsp+1E8h+var_168]
0x180022cb4  jnb     loc_180023657
0x180022cba  imul    rdx, rax, 38h ; '8'
0x180022cbe  add     rdx, [rsp+1E8h+var_150]
0x180022cc6  mov     [rsp+1E8h+rguid], rdx
0x180022ccb  cmp     dword ptr [rdx+14h], 2
0x180022ccf  jz      short loc_180022CD7
0x180022cd1  cmp     dword ptr [rdx+14h], 5
0x180022cd5  jnz     short loc_180022CF0
0x180022cd7  mov     rcx, [rsp+1E8h+var_190]
0x180022cdc  mov     al, [rcx+360h]
0x180022ce2  test    al, al
0x180022ce4  jnz     short loc_180022CF5
0x180022ce6  mov     eax, 80070057h
0x180022ceb  jmp     loc_180023659
0x180022cf0  mov     rcx, [rsp+1E8h+var_190]
0x180022cf5  cmp     [rcx+0F60h], r12b
0x180022cfc  jz      short loc_180022D2B
0x180022cfe  cmp     [rsp+1E8h+var_194], 1
0x180022d03  jnz     short loc_180022D2B
0x180022d05  test    byte ptr [rdx+10h], 4
0x180022d09  jz      short loc_180022D2B
0x180022d0b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180022d12  add     rcx, 70h ; 'p'; this
0x180022d16  lea     r8, aHeapSessionCan; "Heap session cannot be configured to ac"...
0x180022d1d  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180022d24  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180022d29  jmp     short loc_180022CE6
0x180022d2b  mov     al, [rcx+2C8h]
0x180022d31  test    al, al
0x180022d33  jnz     short loc_180022D45
0x180022d35  test    byte ptr [rdx+10h], 1
0x180022d39  jnz     short loc_180022D45
0x180022d3b  mov     eax, 0E1110057h
0x180022d40  jmp     loc_180023659
0x180022d45  xorps   xmm1, xmm1
0x180022d48  movdqu  xmmword ptr [rsp+1E8h+var_188], xmm1
0x180022d4e  mov     [rsp+1E8h+var_178], r12
0x180022d53  add     rcx, 0AE0h
0x180022d5a  mov     r8, rdx
0x180022d5d  lea     rdx, [rsp+1E8h+var_178]
0x180022d62  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@HV?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@H@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,int,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,int>>,0>>::find(_GUID const &)
0x180022d67  mov     r8, [rsp+1E8h+var_190]
0x180022d6c  mov     rax, [rsp+1E8h+var_178]
0x180022d71  cmp     rax, [r8+0AE8h]
0x180022d78  setz    [rsp+1E8h+var_198]
0x180022d7d  jnz     loc_1800232B7
0x180022d83  mov     rdx, [rsp+1E8h+rguid]
0x180022d88  cmp     dword ptr [rdx+14h], 2
0x180022d8c  jz      loc_1800232AD
0x180022d92  cmp     dword ptr [rdx+14h], 5
0x180022d96  jz      loc_1800232AD
0x180022d9c  mov     eax, [rsp+1E8h+var_194]
0x180022da0  cmp     eax, 1
0x180022da3  jnz     loc_180022EC2
0x180022da9  mov     rcx, [r8+0F50h]
0x180022db0  mov     rax, [rcx]
0x180022db3  mov     rax, [rax+28h]
0x180022db7  call    cs:__guard_dispatch_icall_fptr
0x180022dbd  cmp     eax, 1
0x180022dc0  jb      loc_18002303A
0x180022dc6  lfence
0x180022dc9  mov     edx, r12d
0x180022dcc  mov     [rsp+1E8h+var_1B8], edx
0x180022dd0  mov     rax, [rsp+1E8h+var_190]
0x180022dd5  mov     ecx, [rax+0E00h]
0x180022ddb  mov     dword ptr [rsp+1E8h+var_160], ecx
0x180022de2  test    ecx, ecx
0x180022de4  jz      short loc_180022E3F
0x180022de6  xor     edx, edx
0x180022de8  mov     eax, [rax+0DFCh]
0x180022dee  div     ecx
0x180022df0  mov     dword ptr [rsp+1E8h+var_178], eax
0x180022df4  lfence
0x180022df7  mov     ecx, eax; dwMilliseconds
0x180022df9  call    cs:__imp_Sleep
0x180022dff  mov     rax, [rsp+1E8h+var_190]
0x180022e04  mov     rcx, [rax+0F50h]
0x180022e0b  mov     rdx, [rcx]
0x180022e0e  mov     rax, [rdx+28h]
0x180022e12  mov     rdx, [rsp+1E8h+rguid]
0x180022e17  call    cs:__guard_dispatch_icall_fptr
0x180022e1d  cmp     eax, 1
0x180022e20  jb      loc_18002303A
0x180022e26  mov     edx, [rsp+1E8h+var_1B8]
0x180022e2a  inc     edx
0x180022e2c  mov     [rsp+1E8h+var_1B8], edx
0x180022e30  mov     ecx, dword ptr [rsp+1E8h+var_160]
0x180022e37  cmp     edx, ecx
0x180022e39  mov     eax, dword ptr [rsp+1E8h+var_178]
0x180022e3d  jb      short loc_180022DF7
0x180022e3f  cmp     edx, ecx
0x180022e41  jnz     loc_18002303A
0x180022e47  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180022e4e  add     rcx, 70h ; 'p'; this
0x180022e52  lea     r8, aFailedToEnable_0; "Failed to enable the heap provider beca"...
0x180022e59  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180022e60  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180022e65  xorps   xmm0, xmm0
0x180022e68  movups  xmmword ptr [rsp+1E8h+var_1A8], xmm0
0x180022e6d  mov     rax, [rsp+1E8h+var_190]
0x180022e72  movzx   r9d, word ptr [rax+2B8h]; unsigned __int16
0x180022e7a  lea     r8, aHeap; "Heap"
0x180022e81  mov     edx, 0E1110045h; int
0x180022e86  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180022e8b  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x180022e90  nop
0x180022e91  lea     rdx, aUnknownError; "<unknown error>"
0x180022e98  cmp     [rsp+1E8h+var_1A8], r12
0x180022e9d  cmovnz  rdx, [rsp+1E8h+var_1A8]; struct _GUID *
0x180022ea3  lea     rcx, IID_ICollectionSession; this
0x180022eaa  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180022eaf  mov     ebx, dword ptr [rsp+1E8h+var_1A8+8]
0x180022eb3  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180022eb8  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180022ebd  jmp     loc_1800232B2
0x180022ec2  cmp     [r8+0DFAh], r12b
0x180022ec9  jz      loc_180022F65
0x180022ecf  test    eax, eax
0x180022ed1  jnz     loc_180022F65
0x180022ed7  mov     rcx, [r8+0F50h]
0x180022ede  mov     rax, [rcx]
0x180022ee1  mov     rax, [rax+28h]
0x180022ee5  call    cs:__guard_dispatch_icall_fptr
0x180022eeb  cmp     eax, 1
0x180022eee  jb      loc_18002303A
0x180022ef4  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180022efb  add     rcx, 70h ; 'p'; this
0x180022eff  lea     r8, aFailedToEnable_2; "Failed to enable the system provider on"...
0x180022f06  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180022f0d  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180022f12  xorps   xmm0, xmm0
0x180022f15  movups  xmmword ptr [rsp+1E8h+var_1A8], xmm0
0x180022f1a  mov     rax, [rsp+1E8h+var_190]
0x180022f1f  movzx   r9d, word ptr [rax+2B8h]; unsigned __int16
0x180022f27  lea     r8, aNtKernelSessio; "NT Kernel Session (Windows 7)"
0x180022f2e  mov     edx, 0E1110045h; int
0x180022f33  lea     rcx, [rsp+1E8h+var_1A8]; this
0x180022f38  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x180022f3d  nop
0x180022f3e  lea     rdx, aUnknownError; "<unknown error>"
0x180022f45  cmp     [rsp+1E8h+var_1A8], r12
0x180022f4a  cmovnz  rdx, [rsp+1E8h+var_1A8]; struct _GUID *
0x180022f50  lea     rcx, IID_ICollectionSession; this
0x180022f57  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180022f5c  mov     ebx, dword ptr [rsp+1E8h+var_1A8+8]
0x180022f60  jmp     loc_180022EB3
0x180022f65  mov     rcx, [r8+0F50h]
0x180022f6c  mov     rax, [rcx]
0x180022f6f  mov     rax, [rax+28h]
0x180022f73  call    cs:__guard_dispatch_icall_fptr
0x180022f79  cmp     eax, 8
0x180022f7c  jb      loc_18002303A
0x180022f82  lfence
0x180022f85  mov     r8d, 27h ; '''; cchMax
0x180022f8b  lea     rdx, [rsp+1E8h+sz]; lpsz
0x180022f93  mov     rcx, [rsp+1E8h+rguid]; rguid
0x180022f98  call    cs:__imp_StringFromGUID2
0x180022f9e  test    eax, eax
0x180022fa0  jz      loc_1800237E8
0x180022fa6  mov     [rsp+1E8h+var_CA], r12w
0x180022faf  mov     [rsp+1E8h+var_7C], r12w
0x180022fb8  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180022fbf  add     rcx, 70h ; 'p'; this
0x180022fc3  mov     [rsp+1E8h+var_1C8], 8
0x180022fcb  lea     r9, [rsp+1E8h+sz]
0x180022fd3  lea     r8, aFailedToEnable; "Failed to enable provider %s because it"...
0x180022fda  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180022fe1  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180022fe6  xorps   xmm0, xmm0
0x180022fe9  movups  xmmword ptr [rsp+1E8h+var_1A8], xmm0
0x180022fee  mov     rax, [rsp+1E8h+var_190]
0x180022ff3  movzx   r9d, word ptr [rax+2B8h]; unsigned __int16
0x180022ffb  lea     r8, [rsp+1E8h+sz]; unsigned __int16 *
0x180023003  mov     edx, 0E1110045h; int
0x180023008  lea     rcx, [rsp+1E8h+var_1A8]; this
0x18002300d  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x180023012  nop
  ... truncated ...
```
