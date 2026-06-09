# MapControl::RegionDefinition::deserialize(std::shared_ptr<std::vector<uchar,std::allocator<uchar>> const> const &,unsigned __int64)

- ea: `0x18004c748`
- end: `0x18004ce27`
- name: `?deserialize@RegionDefinition@MapControl@@AEAA?AV?$Result@VDecodeError@MapControl@@_K@Core@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@_K@Z`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004c64c`

## callees

- `0x18000d090`
- `0x180011d28`
- `0x180012720`
- `0x180013420`
- `0x18001409c`
- `0x1800140f0`
- `0x180014d44`
- `0x180016d58`
- `0x180017aa8`
- `0x18001b9e0`
- `0x180025790`
- `0x18002bd94`
- `0x18002f7fc`
- `0x180041030`
- `0x180047038`
- `0x18004abd0`
- `0x18004b09c`
- `0x18004b0d4`
- `0x18004b210`
- `0x18004b6e4`
- `0x18004b7f4`
- `0x18004b848`
- `0x18004b914`
- `0x18004ba14`
- `0x18004bb7c`
- `0x18004bba0`
- `0x18004c748`
- `0x18004ce30`
- `0x18004cf28`
- `0x18004d0c4`
- `0x18004d0e4`
- `0x18004d19c`
- `0x18004d260`
- `0x1800654f4`
- `0x180065630`
- `0x180065e7c`
- `0x1800661b8`
- `0x1800662d0`
- `0x1800663c4`
- `0x180066438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004c85e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004c85e`

## string_xrefs

- `0x18004c7de`: `RegionDefinition::deserialize Invalid version`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MapControl::RegionDefinition::deserialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *Error; // rax
  _DWORD *v9; // r12
  const char *v10; // rax
  _BYTE *v11; // rcx
  const char **v12; // rax
  std::_Ref_count_base *Value; // rdi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned __int64 v19; // r14
  unsigned __int64 i; // rdi
  std::_Ref_count_base **v21; // rcx
  int v22; // edi
  unsigned int v23; // r14d
  int *v24; // r15
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  void *v31; // rcx
  _QWORD *v32; // rdi
  _QWORD *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  _QWORD *v36; // r12
  unsigned __int64 v37; // r15
  unsigned __int64 k; // r14
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  void *v42; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v43; // [rsp+28h] [rbp-D8h]
  _BYTE v44[16]; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v47[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  _QWORD *j; // [rsp+78h] [rbp-88h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h]
  const char *v51; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v52; // [rsp+90h] [rbp-70h]
  std::_Ref_count_base *v53[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v54; // [rsp+B8h] [rbp-48h]
  _QWORD v55[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v56; // [rsp+D0h] [rbp-30h]
  char v57; // [rsp+D8h] [rbp-28h]
  __int128 v58; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v59[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v60[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v61[16]; // [rsp+110h] [rbp+10h] BYREF
  double v62; // [rsp+120h] [rbp+20h] BYREF
  char v63; // [rsp+128h] [rbp+28h]
  _BYTE v64[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v65[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v66[24]; // [rsp+150h] [rbp+50h] BYREF

  v48 = a4;
  MicrosoftMapsFlatObjectModel::Reader::Reader(v44, a3, a4, *(_QWORD *)(*(_QWORD *)a3 + 8LL) - a4 - **(_QWORD **)a3);
  MicrosoftMapsFlatObjectModel::Reader::read(v44, v59);
  if ( !v59[8] )
  {
    Error = (_QWORD *)Core::Result<MapControl::DecodeError,int>::getError(v59);
    *(_BYTE *)(a2 + 8) = 0;
    *(_QWORD *)a2 = *Error;
    goto LABEL_74;
  }
  v9 = (_DWORD *)Core::Result<MapControl::DecodeError,bool>::getResult(v59);
  if ( (unsigned int)(*v9 - 1) > 1 )
  {
    v10 = "RegionDefinition::deserialize Invalid version";
LABEL_5:
    *(_BYTE *)(a2 + 8) = 0;
LABEL_6:
    *(_QWORD *)a2 = v10;
    goto LABEL_74;
  }
  MapControl::BinaryReader::readInt64(v44, v60);
  v11 = v60;
  if ( !v60[8] )
    goto LABEL_8;
  v50 = *(_QWORD *)Core::Result<MapControl::DecodeError,bool>::getResult(v60);
  MapControl::BinaryReader::readString(v44, v66);
  if ( !v66[16] )
  {
    v12 = (const char **)Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(v66);
    goto LABEL_9;
  }
  Value = (std::_Ref_count_base *)Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v66);
  gsl::details::span_iterator<gsl::span<Pal::PerformanceEventId const,-1>,0>::span_iterator<gsl::span<Pal::PerformanceEventId const,-1>,0>(
    &v58,
    Value,
    *(_QWORD *)Value);
  if ( *(__int64 *)Value < 0 )
  {
    _o_terminate(v15, v14, v16, v17);
    __debugbreak();
  }
  v53[0] = Value;
  v53[1] = 0;
  v18 = std::wstring::wstring(v55, v53, &v58);
  *(_QWORD *)a1 = *(_QWORD *)MapControl::RegionId::parse(&j, v18);
  std::wstring::_Tidy_deallocate(v55);
  MapControl::BinaryReader::readInt64(v44, v61);
  v11 = v61;
  if ( !v61[8] )
  {
LABEL_8:
    v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(v11);
LABEL_9:
    *(_BYTE *)(a2 + 8) = 0;
LABEL_10:
    v10 = *v12;
    goto LABEL_6;
  }
  *(_QWORD *)(a1 + 8) = *(_QWORD *)Core::Result<MapControl::DecodeError,bool>::getResult(v61);
  MapControl::BinaryReader::readBoolean(v44, &v51);
  if ( !(_BYTE)v52 )
  {
    v10 = v51;
    goto LABEL_5;
  }
  *(_BYTE *)(a1 + 24) = *(_BYTE *)Core::Result<MapControl::DecodeError,bool>::getResult(&v51);
  MapControl::BinaryReader::readDouble(v44, &v62);
  if ( !v63 )
  {
    v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(&v62);
    goto LABEL_9;
  }
  **(_QWORD **)(a1 + 16) = **(_QWORD **)Pal::Date::Date(v47, (unsigned int)(int)(v62 * 1000000.0));
  Microsoft::WRL::Details::MakeAllocator<Pal::Detail::OfflineDetectorWrapper>::~MakeAllocator<Pal::Detail::OfflineDetectorWrapper>(v47);
  MicrosoftMapsFlatObjectModel::Reader::read(v44, v64);
  if ( !v64[8] )
  {
    v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(v64);
    goto LABEL_9;
  }
  v19 = *(int *)Core::Result<MapControl::DecodeError,bool>::getResult(v64);
  for ( i = 0; i < v19; ++i )
  {
    MapControl::BinaryReader::readDouble(v44, &v51);
    if ( !(_BYTE)v52 )
    {
      v21 = (std::_Ref_count_base **)&v51;
      goto LABEL_28;
    }
    MapControl::BinaryReader::readDouble(v44, v53);
    if ( !LOBYTE(v53[1]) )
    {
      v21 = v53;
LABEL_28:
      v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(v21);
      *(_BYTE *)(a2 + 8) = 0;
      goto LABEL_10;
    }
  }
  v22 = 0;
  v46 = 0;
  MapControl::RegionDefinition::deserializeRanges(v55, a3, a4 + v45, &v46);
  if ( !v56 )
  {
    *(_BYTE *)(a2 + 8) = 0;
    *(_QWORD *)a2 = v55[0];
    Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>(v55);
    goto LABEL_74;
  }
  std::shared_ptr<MapControl::LocalIndex>::operator=(a1 + 32, v55);
  Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>(v55);
  v23 = v46;
  MicrosoftMapsFlatObjectModel::Reader::skipField(v44, v53, (unsigned int)v46);
  if ( !LOBYTE(v53[1]) )
  {
    v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(v53);
LABEL_34:
    *(_BYTE *)(a2 + 8) = 0;
    goto LABEL_10;
  }
  MicrosoftMapsFlatObjectModel::Reader::read(v44, v65);
  if ( !v65[8] )
  {
    v12 = (const char **)Core::Result<MapControl::DecodeError,int>::getError(v65);
    goto LABEL_34;
  }
  v24 = (int *)Core::Result<MapControl::DecodeError,bool>::getResult(v65);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(&v42);
  std::vector<std::vector<int>>::reserve(&v42, *v24);
  while ( v22 < *v24 )
  {
    MicrosoftMapsFlatObjectModel::Reader::read(v44, &v51);
    if ( !(_BYTE)v52 )
    {
      v30 = (_QWORD *)Core::Result<MapControl::DecodeError,int>::getError(&v51);
      *(_BYTE *)(a2 + 8) = 0;
      *(_QWORD *)a2 = *v30;
LABEL_46:
      v31 = v42;
      if ( !v42 )
        goto LABEL_74;
      goto LABEL_73;
    }
    v26 = Core::Result<MapControl::DecodeError,bool>::getResult(&v51);
    std::vector<int>::_Emplace_one_at_back<int>(a1 + 48, v26);
    MapControl::RegionDefinition::deserializeIntArray(v55, a3, v48 + v45, &v46);
    if ( !v57 )
    {
      v29 = (_QWORD *)Core::Result<MapControl::DecodeError,std::vector<int>>::getError(v55);
      *(_BYTE *)(a2 + 8) = 0;
      *(_QWORD *)a2 = *v29;
      Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(v55);
      goto LABEL_46;
    }
    v27 = Core::Result<MapControl::DecodeError,std::vector<MicrosoftMapsFlatObjectModel::Range>>::getResult(v55);
    std::vector<std::vector<int>>::emplace_back<std::vector<int>>(&v42, v27);
    v23 = v46;
    MicrosoftMapsFlatObjectModel::Reader::skipField(v44, v53, (unsigned int)v46);
    if ( !LOBYTE(v53[1]) )
    {
      v28 = (_QWORD *)Core::Result<MapControl::DecodeError,int>::getError(v53);
      *(_BYTE *)(a2 + 8) = 0;
      *(_QWORD *)a2 = *v28;
      Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(v55);
      goto LABEL_72;
    }
    Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(v55);
    ++v22;
  }
  if ( *v9 == 2 )
  {
    v32 = v42;
    v33 = (_QWORD *)v43;
    for ( j = (_QWORD *)v43; v32 != v33; v33 = j )
    {
      if ( *v32 == v32[1] )
      {
        v34 = a1 + 72;
        *(_OWORD *)v53 = 0;
        v35 = *(_QWORD *)(a1 + 80);
        if ( v35 == *(_QWORD *)(a1 + 88) )
          std::vector<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>::_Emplace_reallocate<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>(
            v34,
            v35,
            v53);
        else
          std::vector<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>::_Emplace_back_with_unused_capacity<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>(
            v34,
            v53);
        if ( v53[1] )
          std::_Ref_count_base::_Decref(v53[1]);
      }
      else
      {
        MapControl::RegionDefinition::deserializeIntArray(v53, a3, v48 + v45, &v46);
        if ( !v54 )
        {
          v40 = (_QWORD *)Core::Result<MapControl::DecodeError,std::vector<int>>::getError(v53);
          *(_BYTE *)(a2 + 8) = 0;
          *(_QWORD *)a2 = *v40;
          Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(v53);
LABEL_68:
          v31 = v42;
          if ( !v42 )
            goto LABEL_74;
          goto LABEL_73;
        }
        v36 = (_QWORD *)Core::Result<MapControl::DecodeError,std::vector<MicrosoftMapsFlatObjectModel::Range>>::getResult(v53);
        std::make_shared<std::unordered_set<MapControl::PersistentDataId>,>(&v51);
        std::_Hash<std::_Uset_traits<MapControl::PersistentDataId,std::_Uhash_compare<MapControl::PersistentDataId,std::hash<MapControl::PersistentDataId>,std::equal_to<MapControl::PersistentDataId>>,std::allocator<MapControl::PersistentDataId>,0>>::reserve(
          v51,
          (__int64)(v32[1] - *v32) >> 2);
        v37 = (__int64)(v36[1] - *v36) >> 2;
        if ( (__int64)(v32[1] - *v32) >> 2 < v37 )
          v37 = (__int64)(v32[1] - *v32) >> 2;
        for ( k = 0; k < v37; ++k )
        {
          v47[0] = *(_DWORD *)(*v32 + 4 * k);
          v47[1] = *(_DWORD *)(*v36 + 4 * k);
          std::_Hash<std::_Uset_traits<MapControl::PersistentDataId,std::_Uhash_compare<MapControl::PersistentDataId,std::hash<MapControl::PersistentDataId>,std::equal_to<MapControl::PersistentDataId>>,std::allocator<MapControl::PersistentDataId>,0>>::emplace<MapControl::PersistentDataId>(
            v51,
            v55,
            v47);
        }
        std::vector<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>::emplace_back<std::shared_ptr<std::unordered_set<MapControl::PersistentDataId>>>(
          a1 + 72,
          &v51);
        if ( v52 )
          std::_Ref_count_base::_Decref(v52);
        Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(v53);
        v23 = v46;
      }
      MicrosoftMapsFlatObjectModel::Reader::skipField(v44, &v58, v23);
      if ( !BYTE8(v58) )
      {
        v39 = (_QWORD *)Core::Result<MapControl::DecodeError,int>::getError(&v58);
        *(_BYTE *)(a2 + 8) = 0;
        *(_QWORD *)a2 = *v39;
        goto LABEL_68;
      }
      v32 += 3;
    }
  }
  *(_BYTE *)(a2 + 8) = 1;
  *(_QWORD *)a2 = v50;
LABEL_72:
  v31 = v42;
  if ( !v42 )
    goto LABEL_74;
LABEL_73:
  std::_Destroy_range<std::allocator<std::vector<int>>>(v31, v43, v25);
  std::_Deallocate<16>(v42, 8 * ((__int64)(*((_QWORD *)&v43 + 1) - (_QWORD)v42) >> 3));
  v42 = 0;
  v43 = 0;
LABEL_74:
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v44);
  return a2;
}

```

## disassembly

```asm
0x18004c748  push    rbp
0x18004c74a  push    rbx
0x18004c74b  push    rsi
0x18004c74c  push    rdi
0x18004c74d  push    r12
0x18004c74f  push    r13
0x18004c751  push    r14
0x18004c753  push    r15
0x18004c755  lea     rbp, [rsp-78h]
0x18004c75a  sub     rsp, 178h
0x18004c761  mov     rax, cs:__security_cookie
0x18004c768  xor     rax, rsp
0x18004c76b  mov     [rbp+0B0h+var_48], rax
0x18004c76f  mov     r15, r9
0x18004c772  mov     [rsp+1B0h+var_140], r9
0x18004c777  mov     r13, r8
0x18004c77a  mov     rbx, rdx
0x18004c77d  mov     rsi, rcx
0x18004c780  mov     rax, [r8]
0x18004c783  mov     r9, [rax+8]
0x18004c787  sub     r9, r15
0x18004c78a  sub     r9, [rax]
0x18004c78d  mov     r8, r15
0x18004c790  mov     rdx, r13
0x18004c793  lea     rcx, [rsp+1B0h+var_178]
0x18004c798  call    ??0Reader@MicrosoftMapsFlatObjectModel@@QEAA@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@_K1@Z; MicrosoftMapsFlatObjectModel::Reader::Reader(std::shared_ptr<std::vector<uchar> const> const &,unsigned __int64,unsigned __int64)
0x18004c79d  nop
0x18004c79e  lea     rdx, [rbp+0B0h+var_C0]
0x18004c7a2  lea     rcx, [rsp+1B0h+var_178]
0x18004c7a7  call    ?read@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@H@Core@@XZ; MicrosoftMapsFlatObjectModel::Reader::read(void)
0x18004c7ac  xor     r14d, r14d
0x18004c7af  lea     rcx, [rbp+0B0h+var_C0]
0x18004c7b3  cmp     [rbp+0B0h+var_B8], r14b
0x18004c7b7  jnz     short loc_18004C7CD
0x18004c7b9  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004c7be  mov     [rbx+8], r14b
0x18004c7c2  mov     rcx, [rax]
0x18004c7c5  mov     [rbx], rcx
0x18004c7c8  jmp     loc_18004CDFA
0x18004c7cd  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004c7d2  mov     r12, rax
0x18004c7d5  mov     ecx, [rax]
0x18004c7d7  dec     ecx
0x18004c7d9  cmp     ecx, 1
0x18004c7dc  jbe     short loc_18004C7F1
0x18004c7de  lea     rax, aRegiondefiniti; "RegionDefinition::deserialize Invalid v"...
0x18004c7e5  mov     [rbx+8], r14b
0x18004c7e9  mov     [rbx], rax
0x18004c7ec  jmp     loc_18004CDFA
0x18004c7f1  lea     rdx, [rbp+0B0h+var_B0]
0x18004c7f5  lea     rcx, [rsp+1B0h+var_178]
0x18004c7fa  call    ?readInt64@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@_J@Core@@XZ; MapControl::BinaryReader::readInt64(void)
0x18004c7ff  lea     rcx, [rbp+0B0h+var_B0]
0x18004c803  cmp     [rbp+0B0h+var_A8], r14b
0x18004c807  jnz     short loc_18004C817
0x18004c809  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004c80e  mov     [rbx+8], r14b
0x18004c812  mov     rax, [rax]
0x18004c815  jmp     short loc_18004C7E9
0x18004c817  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004c81c  mov     rax, [rax]
0x18004c81f  mov     [rbp+0B0h+var_130], rax
0x18004c823  lea     rdx, [rbp+0B0h+var_60]
0x18004c827  lea     rcx, [rsp+1B0h+var_178]
0x18004c82c  call    ?readString@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@V?$basic_string_span@$$CBD$0?0@gsl@@@Core@@XZ; MapControl::BinaryReader::readString(void)
0x18004c831  lea     rcx, [rbp+0B0h+var_60]
0x18004c835  cmp     [rbp+0B0h+var_50], r14b
0x18004c839  jnz     short loc_18004C842
0x18004c83b  call    ?getError@?$Result@UError@MapDataTypesRegistry@MapControl@@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAAEAUError@MapDataTypesRegistry@MapControl@@XZ; Core::Result<MapControl::MapDataTypesRegistry::Error,std::shared_ptr<MapControl::EndpointDescription>>::getError(void)
0x18004c840  jmp     short loc_18004C80E
0x18004c842  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x18004c847  mov     rdi, rax
0x18004c84a  mov     r8, [rax]
0x18004c84d  mov     rdx, rax
0x18004c850  lea     rcx, [rbp+0B0h+var_D0]
0x18004c854  call    ??0?$span_iterator@V?$span@$$CBVPerformanceEventId@Pal@@$0?0@gsl@@$0A@@details@gsl@@QEAA@PEBV?$span@$$CBVPerformanceEventId@Pal@@$0?0@2@_J@Z; gsl::details::span_iterator<gsl::span<Pal::PerformanceEventId const,-1>,0>::span_iterator<gsl::span<Pal::PerformanceEventId const,-1>,0>(gsl::span<Pal::PerformanceEventId const,-1> const *,__int64)
0x18004c859  cmp     [rdi], r14
0x18004c85c  jge     short loc_18004C865
0x18004c85e  call    cs:__imp__o_terminate
0x18004c864  int     3; Trap to Debugger
0x18004c865  movaps  xmm0, [rbp+0B0h+var_D0]
0x18004c869  movdqa  [rbp+0B0h+var_D0], xmm0
0x18004c86e  mov     [rbp+0B0h+var_110], rdi
0x18004c872  mov     [rbp+0B0h+var_110+8], r14
0x18004c876  lea     r8, [rbp+0B0h+var_D0]
0x18004c87a  lea     rdx, [rbp+0B0h+var_110]
0x18004c87e  lea     rcx, [rbp+0B0h+var_F0]
0x18004c882  call    ??$?0V?$span_iterator@V?$span@$$CBD$0?0@gsl@@$0A@@details@gsl@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$span_iterator@V?$span@$$CBD$0?0@gsl@@$0A@@details@gsl@@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(gsl::details::span_iterator<gsl::span<char const,-1>,0>,gsl::details::span_iterator<gsl::span<char const,-1>,0>,std::allocator<ushort> const &)
0x18004c887  nop
0x18004c888  mov     rdx, rax
0x18004c88b  lea     rcx, [rsp+1B0h+var_138]
0x18004c890  call    ?parse@RegionId@MapControl@@SA?AV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::RegionId::parse(std::wstring const &)
0x18004c895  mov     rcx, [rax]
0x18004c898  mov     [rsi], rcx
0x18004c89b  lea     rcx, [rbp+0B0h+var_F0]
0x18004c89f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c8a4  lea     rdx, [rbp+0B0h+var_A0]
0x18004c8a8  lea     rcx, [rsp+1B0h+var_178]
0x18004c8ad  call    ?readInt64@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@_J@Core@@XZ; MapControl::BinaryReader::readInt64(void)
0x18004c8b2  lea     rcx, [rbp+0B0h+var_A0]
0x18004c8b6  cmp     [rbp+0B0h+var_98], r14b
0x18004c8ba  jz      loc_18004C809
0x18004c8c0  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004c8c5  mov     rcx, [rax]
0x18004c8c8  mov     [rsi+8], rcx
0x18004c8cc  lea     rdx, [rbp+0B0h+var_128]
0x18004c8d0  lea     rcx, [rsp+1B0h+var_178]
0x18004c8d5  call    ?readBoolean@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@_N@Core@@XZ; MapControl::BinaryReader::readBoolean(void)
0x18004c8da  cmp     byte ptr [rbp+0B0h+var_120], r14b
0x18004c8de  jnz     short loc_18004C8E9
0x18004c8e0  mov     rax, [rbp+0B0h+var_128]
0x18004c8e4  jmp     loc_18004C7E5
0x18004c8e9  lea     rcx, [rbp+0B0h+var_128]
0x18004c8ed  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004c8f2  mov     cl, [rax]
0x18004c8f4  mov     [rsi+18h], cl
0x18004c8f7  lea     rdx, [rbp+0B0h+var_90]
0x18004c8fb  lea     rcx, [rsp+1B0h+var_178]
0x18004c900  call    ?readDouble@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@N@Core@@XZ; MapControl::BinaryReader::readDouble(void)
0x18004c905  cmp     [rbp+0B0h+var_88], r14b
0x18004c909  jnz     short loc_18004C919
0x18004c90b  lea     rcx, [rbp+0B0h+var_90]
0x18004c90f  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004c914  jmp     loc_18004C80E
0x18004c919  movsd   xmm0, [rbp+0B0h+var_90]
0x18004c91e  mulsd   xmm0, cs:__real@412e848000000000
0x18004c926  cvttsd2si rdx, xmm0
0x18004c92b  lea     rcx, [rsp+1B0h+var_148]
0x18004c930  call    ??0Date@Pal@@QEAA@VTimeSpanSinceEpoch@1@@Z; Pal::Date::Date(Pal::TimeSpanSinceEpoch)
0x18004c935  mov     rax, [rax]
0x18004c938  mov     rcx, [rsi+10h]
0x18004c93c  mov     rax, [rax]
0x18004c93f  mov     [rcx], rax
0x18004c942  lea     rcx, [rsp+1B0h+var_148]
0x18004c947  call    ??1?$MakeAllocator@VOfflineDetectorWrapper@Detail@Pal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Pal::Detail::OfflineDetectorWrapper>::~MakeAllocator<Pal::Detail::OfflineDetectorWrapper>(void)
0x18004c94c  lea     rdx, [rbp+0B0h+var_80]
0x18004c950  lea     rcx, [rsp+1B0h+var_178]
0x18004c955  call    ?read@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@H@Core@@XZ; MicrosoftMapsFlatObjectModel::Reader::read(void)
0x18004c95a  lea     rcx, [rbp+0B0h+var_80]
0x18004c95e  cmp     [rbp+0B0h+var_78], r14b
0x18004c962  jnz     short loc_18004C96E
0x18004c964  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004c969  jmp     loc_18004C80E
0x18004c96e  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004c973  movsxd  r14, dword ptr [rax]
0x18004c976  xor     edi, edi
0x18004c978  cmp     rdi, r14
0x18004c97b  jnb     short loc_18004C9C2
0x18004c97d  lea     rdx, [rbp+0B0h+var_128]
0x18004c981  lea     rcx, [rsp+1B0h+var_178]
0x18004c986  call    ?readDouble@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@N@Core@@XZ; MapControl::BinaryReader::readDouble(void)
0x18004c98b  cmp     byte ptr [rbp+0B0h+var_120], 0
0x18004c98f  jz      short loc_18004C9BC
0x18004c991  lea     rdx, [rbp+0B0h+var_110]
0x18004c995  lea     rcx, [rsp+1B0h+var_178]
0x18004c99a  call    ?readDouble@BinaryReader@MapControl@@QEAA?AV?$Result@VDecodeError@MapControl@@N@Core@@XZ; MapControl::BinaryReader::readDouble(void)
0x18004c99f  cmp     byte ptr [rbp+0B0h+var_110+8], 0
0x18004c9a3  jz      short loc_18004C9AA
0x18004c9a5  inc     rdi
0x18004c9a8  jmp     short loc_18004C978
0x18004c9aa  lea     rcx, [rbp+0B0h+var_110]
0x18004c9ae  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004c9b3  mov     byte ptr [rbx+8], 0
0x18004c9b7  jmp     loc_18004C812
0x18004c9bc  lea     rcx, [rbp+0B0h+var_128]
0x18004c9c0  jmp     short loc_18004C9AE
0x18004c9c2  xor     edi, edi
0x18004c9c4  mov     [rsp+1B0h+var_150], rdi
0x18004c9c9  movsxd  r8, [rsp+1B0h+var_168]
0x18004c9ce  add     r8, r15
0x18004c9d1  lea     r9, [rsp+1B0h+var_150]
0x18004c9d6  mov     rdx, r13
0x18004c9d9  lea     rcx, [rbp+0B0h+var_F0]
0x18004c9dd  call    ?deserializeRanges@RegionDefinition@MapControl@@SA?AV?$Result@VDecodeError@MapControl@@V?$shared_ptr@V?$RangeSet@H@Utility@@@std@@@Core@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@_KPEA_K@Z; MapControl::RegionDefinition::deserializeRanges(std::shared_ptr<std::vector<uchar> const> const &,unsigned __int64,unsigned __int64 *)
0x18004c9e2  cmp     [rbp+0B0h+var_E0], dil
0x18004c9e6  jnz     short loc_18004CA01
0x18004c9e8  mov     [rbx+8], dil
0x18004c9ec  mov     rax, [rbp+0B0h+var_F0]
0x18004c9f0  mov     [rbx], rax
0x18004c9f3  lea     rcx, [rbp+0B0h+var_F0]
0x18004c9f7  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VOdvsRegionCatalogIndex@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>(void)
0x18004c9fc  jmp     loc_18004CDFA
0x18004ca01  lea     rcx, [rsi+20h]
0x18004ca05  lea     rdx, [rbp+0B0h+var_F0]
0x18004ca09  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x18004ca0e  lea     rcx, [rbp+0B0h+var_F0]
0x18004ca12  call    ??1?$Result@VDecodeError@MapControl@@V?$shared_ptr@VOdvsRegionCatalogIndex@MapControl@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>::~Result<MapControl::DecodeError,std::shared_ptr<MapControl::OdvsRegionCatalogIndex>>(void)
0x18004ca17  mov     r14, [rsp+1B0h+var_150]
0x18004ca1c  mov     r8d, r14d
0x18004ca1f  lea     rdx, [rbp+0B0h+var_110]
0x18004ca23  lea     rcx, [rsp+1B0h+var_178]
0x18004ca28  call    ?skipField@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@X@Core@@H@Z; MicrosoftMapsFlatObjectModel::Reader::skipField(int)
0x18004ca2d  cmp     byte ptr [rbp+0B0h+var_110+8], dil
0x18004ca31  jnz     short loc_18004CA45
0x18004ca33  lea     rcx, [rbp+0B0h+var_110]
0x18004ca37  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004ca3c  mov     [rbx+8], dil
0x18004ca40  jmp     loc_18004C812
0x18004ca45  lea     rdx, [rbp+0B0h+var_70]
0x18004ca49  lea     rcx, [rsp+1B0h+var_178]
0x18004ca4e  call    ?read@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@H@Core@@XZ; MicrosoftMapsFlatObjectModel::Reader::read(void)
0x18004ca53  lea     rcx, [rbp+0B0h+var_70]
0x18004ca57  cmp     [rbp+0B0h+var_68], dil
0x18004ca5b  jnz     short loc_18004CA64
0x18004ca5d  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004ca62  jmp     short loc_18004CA3C
0x18004ca64  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004ca69  mov     r15, rax
0x18004ca6c  lea     rcx, [rsp+1B0h+var_190]; void *
0x18004ca71  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<int,unsigned __int64>>> const &)
0x18004ca76  nop
0x18004ca77  movsxd  rdx, dword ptr [r15]
0x18004ca7a  lea     rcx, [rsp+1B0h+var_190]
0x18004ca7f  call    ?reserve@?$vector@V?$vector@HV?$allocator@H@std@@@std@@V?$allocator@V?$vector@HV?$allocator@H@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::vector<int>>::reserve(unsigned __int64)
0x18004ca84  cmp     edi, [r15]
0x18004ca87  jge     loc_18004CBB9
0x18004ca8d  lea     rdx, [rbp+0B0h+var_128]
0x18004ca91  lea     rcx, [rsp+1B0h+var_178]
0x18004ca96  call    ?read@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@H@Core@@XZ; MicrosoftMapsFlatObjectModel::Reader::read(void)
0x18004ca9b  xor     r14d, r14d
0x18004ca9e  lea     rcx, [rbp+0B0h+var_128]
0x18004caa2  cmp     byte ptr [rbp+0B0h+var_120], r14b
0x18004caa6  jz      loc_18004CB5C
0x18004caac  call    ?getResult@?$Result@VDecodeError@MapControl@@_N@Core@@QEAAAEA_NXZ; Core::Result<MapControl::DecodeError,bool>::getResult(void)
0x18004cab1  lea     rcx, [rsi+30h]
0x18004cab5  mov     rdx, rax
0x18004cab8  call    ??$_Emplace_one_at_back@H@?$vector@HV?$allocator@H@std@@@std@@AEAAAEAH$$QEAH@Z; std::vector<int>::_Emplace_one_at_back<int>(int &&)
0x18004cabd  movsxd  r8, [rsp+1B0h+var_168]
0x18004cac2  add     r8, [rsp+1B0h+var_140]
0x18004cac7  lea     r9, [rsp+1B0h+var_150]
0x18004cacc  mov     rdx, r13
0x18004cacf  lea     rcx, [rbp+0B0h+var_F0]
0x18004cad3  call    ?deserializeIntArray@RegionDefinition@MapControl@@CA?AV?$Result@VDecodeError@MapControl@@V?$vector@HV?$allocator@H@std@@@std@@@Core@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@_KPEA_K@Z; MapControl::RegionDefinition::deserializeIntArray(std::shared_ptr<std::vector<uchar> const> const &,unsigned __int64,unsigned __int64 *)
0x18004cad8  nop
0x18004cad9  lea     rcx, [rbp+0B0h+var_F0]
0x18004cadd  cmp     [rbp+0B0h+var_D8], r14b
0x18004cae1  jz      short loc_18004CB42
0x18004cae3  call    ?getResult@?$Result@VDecodeError@MapControl@@V?$vector@VRange@MicrosoftMapsFlatObjectModel@@V?$allocator@VRange@MicrosoftMapsFlatObjectModel@@@std@@@std@@@Core@@QEAAAEAV?$vector@VRange@MicrosoftMapsFlatObjectModel@@V?$allocator@VRange@MicrosoftMapsFlatObjectModel@@@std@@@std@@XZ; Core::Result<MapControl::DecodeError,std::vector<MicrosoftMapsFlatObjectModel::Range>>::getResult(void)
0x18004cae8  mov     rdx, rax
0x18004caeb  lea     rcx, [rsp+1B0h+var_190]
0x18004caf0  call    ??$emplace_back@V?$vector@HV?$allocator@H@std@@@std@@@?$vector@V?$vector@HV?$allocator@H@std@@@std@@V?$allocator@V?$vector@HV?$allocator@H@std@@@std@@@2@@std@@QEAAAEAV?$vector@HV?$allocator@H@std@@@1@$$QEAV21@@Z; std::vector<std::vector<int>>::emplace_back<std::vector<int>>(std::vector<int> &&)
0x18004caf5  mov     r14, [rsp+1B0h+var_150]
0x18004cafa  mov     r8d, r14d
0x18004cafd  lea     rdx, [rbp+0B0h+var_110]
0x18004cb01  lea     rcx, [rsp+1B0h+var_178]
0x18004cb06  call    ?skipField@Reader@MicrosoftMapsFlatObjectModel@@QEAA?AV?$Result@VDecodeError@MapControl@@X@Core@@H@Z; MicrosoftMapsFlatObjectModel::Reader::skipField(int)
0x18004cb0b  cmp     byte ptr [rbp+0B0h+var_110+8], 0
0x18004cb0f  jz      short loc_18004CB21
0x18004cb11  lea     rcx, [rbp+0B0h+var_F0]
0x18004cb15  call    ??1?$Result@VDecodeError@MapControl@@V?$vector@HV?$allocator@H@std@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(void)
0x18004cb1a  inc     edi
0x18004cb1c  jmp     loc_18004CA84
0x18004cb21  lea     rcx, [rbp+0B0h+var_110]
0x18004cb25  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004cb2a  mov     byte ptr [rbx+8], 0
0x18004cb2e  mov     rax, [rax]
0x18004cb31  mov     [rbx], rax
0x18004cb34  lea     rcx, [rbp+0B0h+var_F0]
0x18004cb38  call    ??1?$Result@VDecodeError@MapControl@@V?$vector@HV?$allocator@H@std@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(void)
0x18004cb3d  jmp     loc_18004CDA8
0x18004cb42  call    ?getError@?$Result@VDecodeError@MapControl@@V?$vector@HV?$allocator@H@std@@@std@@@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,std::vector<int>>::getError(void)
0x18004cb47  mov     [rbx+8], r14b
0x18004cb4b  mov     rax, [rax]
0x18004cb4e  mov     [rbx], rax
0x18004cb51  lea     rcx, [rbp+0B0h+var_F0]
0x18004cb55  call    ??1?$Result@VDecodeError@MapControl@@V?$vector@HV?$allocator@H@std@@@std@@@Core@@QEAA@XZ; Core::Result<MapControl::DecodeError,std::vector<int>>::~Result<MapControl::DecodeError,std::vector<int>>(void)
0x18004cb5a  jmp     short loc_18004CB6B
0x18004cb5c  call    ?getError@?$Result@VDecodeError@MapControl@@H@Core@@QEAAAEAVDecodeError@MapControl@@XZ; Core::Result<MapControl::DecodeError,int>::getError(void)
0x18004cb61  mov     [rbx+8], r14b
0x18004cb65  mov     rax, [rax]
0x18004cb68  mov     [rbx], rax
0x18004cb6b  mov     rcx, [rsp+1B0h+var_190]
0x18004cb70  test    rcx, rcx
0x18004cb73  jz      loc_18004CDFA
0x18004cb79  mov     rdx, qword ptr [rsp+1B0h+var_188]
0x18004cb7e  call    ??$_Destroy_range@V?$allocator@V?$vector@HV?$allocator@H@std@@@std@@@std@@@std@@YAXPEAV?$vector@HV?$allocator@H@std@@@0@QEAV10@AEAV?$allocator@V?$vector@HV?$allocator@H@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::vector<int>>>(std::vector<int> *,std::vector<int> * const,std::allocator<std::vector<int>> &)
0x18004cb83  mov     rcx, [rsp+1B0h+var_190]
0x18004cb88  mov     rax, qword ptr [rsp+1B0h+var_188+8]
0x18004cb8d  sub     rax, rcx
0x18004cb90  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18004cb9a  sar     rax, 3
0x18004cb9e  imul    rax, rdx
0x18004cba2  lea     rdx, [rax+rax*2]
0x18004cba6  shl     rdx, 3
0x18004cbaa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004cbaf  mov     [rsp+1B0h+var_190], r14
0x18004cbb4  jmp     loc_18004CDF1
0x18004cbb9  cmp     dword ptr [r12], 2
0x18004cbbe  jnz     loc_18004CD9D
0x18004cbc4  mov     rdi, [rsp+1B0h+var_190]
0x18004cbc9  mov     rax, qword ptr [rsp+1B0h+var_188]
0x18004cbce  mov     [rsp+1B0h+var_138], rax
0x18004cbd3  xor     r15d, r15d
0x18004cbd6  cmp     rdi, rax
0x18004cbd9  jz      loc_18004CD9D
0x18004cbdf  mov     rax, [rdi+8]
0x18004cbe3  cmp     [rdi], rax
0x18004cbe6  jnz     short loc_18004CC2A
0x18004cbe8  lea     rcx, [rsi+48h]
0x18004cbec  xorps   xmm0, xmm0
  ... truncated ...
```
