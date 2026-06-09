# Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::beginGetImpl<MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer>(MapControl::PersistentDataKey const &,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer)

- ea: `0x180056974`
- end: `0x180056c96`
- name: `??$beginGetImpl@W4NetworkUsagePreference@MapControl@@VLoadChunkIndexOperationTracer@2@@?$ComputableMemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@7@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@AEAA?AV?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Pal@@@std@@AEBUPersistentDataKey@MapControl@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@W4NetworkUsagePreference@5@VLoadChunkIndexOperationTracer@5@@Z`
- size: `802`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800594a0`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x180013420`
- `0x1800140f0`
- `0x180014108`
- `0x180016770`
- `0x180016d58`
- `0x180017a58`
- `0x18001b9e0`
- `0x1800247cc`
- `0x1800257cc`
- `0x18002b9f8`
- `0x18002e4c0`
- `0x180031334`
- `0x180037ddc`
- `0x180040398`
- `0x180046450`
- `0x180053fa0`
- `0x180056710`
- `0x180056974`
- `0x180056fa0`
- `0x1800570f4`
- `0x180058434`
- `0x1800587cc`
- `0x180058858`
- `0x180059bb8`
- `0x180059e10`
- `0x180083758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056b45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056b73`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::beginGetImpl<enum MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  __int64 v9; // r14
  __int64 Value; // rax
  __int64 *v11; // rdi
  __int64 (__fastcall *v12)(); // rbx
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  std::_Ref_count_base *v22; // r8
  __int64 v23; // rax
  std::_Ref_count_base *v24; // rbx
  __int64 (__fastcall *v26)(); // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v27; // [rsp+38h] [rbp-C8h]
  _QWORD *v28; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v32; // [rsp+70h] [rbp-90h]
  _QWORD v33[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v35; // [rsp+B0h] [rbp-50h]
  _BYTE v36[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v37[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v38[56]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v39[3]; // [rsp+118h] [rbp+18h] BYREF

  v30[0] = a4;
  v33[3] = a6;
  v36[16] = 0;
  v28 = a1;
  v26 = Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::cancelGet;
  ____0P8__ComputableMemoryCache_UBlobId_PersistentMapsCache_MapControl__V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UHashFunction_123_U__AlwaysTruePredicate_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std___Core____V_Utility__EAAXAEBV__AsyncOperationImplementation_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UBlobId_PersistentMapsCache_MapControl___Pal___ZPEAV01_AEBU___Ph__00_std______Compressed_pair_P8__ComputableMemoryCache_UBlobId_PersistentMapsCache_MapControl__V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UHashFunction_123_U__AlwaysTruePredicate_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std___Core____V_Utility__EAAXAEBV__AsyncOperationImplementation_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UBlobId_PersistentMapsCache_MapControl___Pal___ZV__tuple_PEAV__ComputableMemoryCache_UBlobId_PersistentMapsCache_MapControl__V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UHashFunction_123_U__AlwaysTruePredicate_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std___Core____V_Utility__U___Ph__00_std___std___0A__std__QEAA_U_One_then_variadic_args_t_1___QEAP8__ComputableMemoryCache_UBlobId_PersistentMapsCache_MapControl__V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UHashFunction_123_U__AlwaysTruePredicate_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std___Core____V_Utility__EAAXAEBV__AsyncOperationImplementation_V__shared_ptr___CBV__vector_EV__allocator_E_std___std___std__UBlobId_PersistentMapsCache_MapControl___Pal___Z__QEAPEAV34_AEBU___Ph__00_1__Z(
    v33,
    (__int64)a2,
    &v26,
    (__int64)&v28);
  std::make_shared<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>,std::_Binder<std::_Unforced,void (Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::*)(Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const> const &),Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&> *,std::_Ph<1> const &>,MapControl::PersistentDataKey const &>(
    &v31,
    v33,
    a3);
  v35 = 0;
  Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::getScopedLock(a1 + 2, v29);
  if ( (unsigned __int8)Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::get(
                          *a1,
                          a3,
                          v36) )
  {
    v9 = v31;
    Value = Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v36);
    Core::Optional<std::shared_ptr<MapControl::OdvsChunkIndex>>::operator=(v9 + 224, Value);
    Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(v9, 1);
  }
  else
  {
    v11 = (__int64 *)v29[0];
    std::_Tree<std::_Tmap_traits<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>,std::less<MapControl::PersistentDataKey>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>,0>>::find(
      v29[0],
      &v26,
      a3);
    v12 = v26;
    if ( v26 == (__int64 (__fastcall *)())*v11 )
    {
      memset_0(v37, 0, 0x60u);
      Core::PresentSharedPtr<Utility::CompositePriorityTag>::make_shared<>(v37);
      Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(v38);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(v39);
      std::_Tree<std::_Tmap_traits<MapControl::PersistentDataKey const,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>,std::less<MapControl::PersistentDataKey const>,std::allocator<std::pair<MapControl::PersistentDataKey const,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>>>,0>>::_Emplace<MapControl::PersistentDataKey const &,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>>(
        v11,
        (__int64)&v26,
        a3,
        (__int64)v37);
      v12 = v26;
      Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>::~RequestInternal<1>(v37);
      if ( v35 )
      {
        Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v34);
        v13 = (__int64 *)std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
                           &v26,
                           (char *)v12 + 48);
        v14 = *v13;
        *v13 = *v15;
        *v15 = v14;
        v16 = v13[1];
        v13[1] = v15[1];
        v15[1] = v16;
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
      }
      else
      {
        std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
          v34,
          (char *)v12 + 48);
        v35 = 1;
      }
    }
    std::vector<std::shared_ptr<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>>>::emplace_back<std::shared_ptr<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>> const &>(
      (char *)v12 + 120,
      &v31);
    v17 = *((_QWORD *)v12 + 6);
    v9 = v31;
    LODWORD(v28) = *(_DWORD *)(v31 + 24);
    v26 = (__int64 (__fastcall *)())(v17 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    v18 = (_QWORD *)std::map<unsigned int,std::shared_ptr<Pal::PriorityTag>>::_Try_emplace<unsigned int const &,>(
                      v17 + 48,
                      v33,
                      &v28);
    std::shared_ptr<MapControl::OdvsChunkIndex>::operator=(*v18 + 40LL, v30[0]);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
  }
  Pal::ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>::~ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>(v29);
  if ( v35 )
  {
    v19 = (__int64 *)Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(v34);
    v20 = *v19;
    v21 = v19[1];
    if ( v21 )
      _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
    v29[0] = v20;
    v29[1] = v19[1];
    Pal::StaticVariableBase<Core::PresentSharedPtr<Pal::PriorityTag>>::StaticVariableBase<Core::PresentSharedPtr<Pal::PriorityTag>>(
      v30,
      v29);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    v23 = std::_Func_class<std::shared_ptr<Pal::AsyncInfo>,MapControl::PersistentDataKey const &,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer &&>::operator()(
            (int)a1 + 72,
            (unsigned int)&v26,
            a3,
            (unsigned int)v30,
            a5,
            a6);
    Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,enum MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::registerGetItemOperation(
      a1,
      a3,
      v23);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v30);
  }
  *a2 = 0;
  a2[1] = 0;
  v24 = v32;
  if ( v32 )
    _InterlockedIncrement((volatile signed __int32 *)v32 + 2);
  *a2 = v9;
  a2[1] = v24;
  if ( v35 )
  {
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v34);
    v35 = 0;
  }
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  Core::Optional<std::shared_ptr<MapControl::EndpointDescription>>::clear(v36);
  Core::Optional<unsigned int>::clear(a6 + 4);
  return a2;
}

```

## disassembly

```asm
0x180056974  push    rbp
0x180056976  push    rbx
0x180056977  push    rsi
0x180056978  push    rdi
0x180056979  push    r12
0x18005697b  push    r13
0x18005697d  push    r14
0x18005697f  push    r15
0x180056981  lea     rbp, [rsp-48h]
0x180056986  sub     rsp, 148h
0x18005698d  mov     rax, cs:__security_cookie
0x180056994  xor     rax, rsp
0x180056997  mov     [rbp+80h+var_50], rax
0x18005699b  mov     [rsp+180h+var_128], r9
0x1800569a0  mov     r15, r8
0x1800569a3  mov     rsi, rdx
0x1800569a6  mov     r12, rcx
0x1800569a9  mov     [rsp+180h+var_150], rdx
0x1800569ae  mov     r13, [rbp+80h+arg_28]
0x1800569b5  mov     [rbp+80h+var_E8], r13
0x1800569b9  xor     edi, edi
0x1800569bb  mov     [rbp+80h+var_B8], dil
0x1800569bf  mov     [rsp+180h+var_140], rcx
0x1800569c4  lea     rax, ?cancelGet@?$ComputableMemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@7@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@AEAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@Z; Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::cancelGet(Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const> const &)
0x1800569cb  mov     [rsp+180h+var_150], rax
0x1800569d0  lea     r9, [rsp+180h+var_140]
0x1800569d5  lea     r8, [rsp+180h+var_150]
0x1800569da  lea     rcx, [rbp+80h+var_100]
0x1800569de  call    ??$?0P8?$ComputableMemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@$$V@Utility@@EAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UBlobId@PersistentMapsCache@MapControl@@@Pal@@@ZPEAV01@AEBU?$_Ph@$00@std@@@?$_Compressed_pair@P8?$ComputableMemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@$$V@Utility@@EAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UBlobId@PersistentMapsCache@MapControl@@@Pal@@@ZV?$tuple@PEAV?$ComputableMemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@$$V@Utility@@U?$_Ph@$00@std@@@std@@$0A@@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAP8?$ComputableMemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@$$V@Utility@@EAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UBlobId@PersistentMapsCache@MapControl@@@Pal@@@Z$$QEAPEAV34@AEBU?$_Ph@$00@1@@Z
0x1800569e3  mov     r8, r15
0x1800569e6  lea     rdx, [rbp+80h+var_100]
0x1800569ea  lea     rcx, [rsp+180h+var_118]
0x1800569ef  call    ??$make_shared@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@V?$_Binder@U_Unforced@std@@P8?$ComputableMemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@7@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@EAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@ZPEAV34@AEBU?$_Ph@$00@2@@std@@AEBUPersistentDataKey@MapControl@@@std@@YA?AV?$shared_ptr@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@0@$$QEAV?$_Binder@U_Unforced@std@@P8?$ComputableMemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@7@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@EAAXAEBV?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@ZPEAV34@AEBU?$_Ph@$00@2@@0@AEBUPersistentDataKey@MapControl@@@Z; std::make_shared<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>,std::_Binder<std::_Unforced,void (Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::*)(Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const> const &),Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&> *,std::_Ph<1> const &>,MapControl::PersistentDataKey const &>(std::_Binder<std::_Unforced,void (Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::*)(Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const> const &),Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&> *,std::_Ph<1> const &> &&,MapControl::PersistentDataKey const &)
0x1800569f4  nop
0x1800569f5  mov     [rbp+80h+var_D0], dil
0x1800569f9  lea     rcx, [r12+10h]
0x1800569fe  lea     rdx, [rsp+180h+var_138]
0x180056a03  call    ?getScopedLock@?$Lockable@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@Pal@@QEAA?AV?$ScopedLockableValue@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@2@XZ; Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::getScopedLock(void)
0x180056a08  nop
0x180056a09  lea     r8, [rbp+80h+var_C8]
0x180056a0d  mov     rdx, r15
0x180056a10  mov     rcx, [r12]
0x180056a14  call    ?get@?$MemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@@Utility@@QEAA_NAEBUPersistentDataKey@MapControl@@PEAV?$Optional@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@@Z; Utility::MemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>>::get(MapControl::PersistentDataKey const &,Core::Optional<std::shared_ptr<MapControl::OdvsChunkIndex>> *)
0x180056a19  test    al, al
0x180056a1b  jz      short loc_180056A4D
0x180056a1d  mov     r14, [rsp+180h+var_118]
0x180056a22  lea     rcx, [rbp+80h+var_C8]
0x180056a26  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x180056a2b  lea     rcx, [r14+0E0h]
0x180056a32  mov     rdx, rax
0x180056a35  call    ??4?$Optional@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@QEAAAEAV01@$$QEAV?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Z; Core::Optional<std::shared_ptr<MapControl::OdvsChunkIndex>>::operator=(std::shared_ptr<MapControl::OdvsChunkIndex> &&)
0x180056a3a  mov     edx, cs:dword_1800A518C
0x180056a40  mov     rcx, r14
0x180056a43  call    ?setSucceededOrFailedInternal@UntypedAsyncOperation@Pal@@AEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(Core::StatusCode)
0x180056a48  jmp     loc_180056B7B
0x180056a4d  mov     r8, r15
0x180056a50  lea     rdx, [rsp+180h+var_150]
0x180056a55  mov     rdi, [rsp+180h+var_138]
0x180056a5a  mov     rcx, rdi
0x180056a5d  call    ?find@?$_Tree@V?$_Tmap_traits@UPersistentDataKey@MapControl@@V?$list@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@V?$allocator@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@@2@@std@@U?$less@UPersistentDataKey@MapControl@@@4@V?$allocator@U?$pair@$$CBUPersistentDataKey@MapControl@@V?$list@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@V?$allocator@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUPersistentDataKey@MapControl@@V?$list@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@V?$allocator@V?$shared_ptr@VPersistentCacheInternalRemoveAsyncOperation@MapControl@@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBUPersistentDataKey@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::PersistentDataKey,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>,std::less<MapControl::PersistentDataKey>,std::allocator<std::pair<MapControl::PersistentDataKey const,std::list<std::shared_ptr<MapControl::PersistentCacheInternalRemoveAsyncOperation>>>>,0>>::find(MapControl::PersistentDataKey const &)
0x180056a62  mov     rbx, [rsp+180h+var_150]
0x180056a67  cmp     rbx, [rdi]
0x180056a6a  jnz     loc_180056B1A
0x180056a70  xor     edx, edx; Val
0x180056a72  lea     r8d, [rdx+60h]; Size
0x180056a76  lea     rcx, [rbp+80h+var_B0]; void *
0x180056a7a  call    memset_0
0x180056a7f  lea     rcx, [rbp+80h+var_B0]
0x180056a83  call    ??$make_shared@$$V@?$PresentSharedPtr@VCompositePriorityTag@Utility@@@Core@@SA?AV01@XZ; Core::PresentSharedPtr<Utility::CompositePriorityTag>::make_shared<>(void)
0x180056a88  lea     rcx, [rbp+80h+var_A0]
0x180056a8c  call    ??0?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@QEAA@XZ; Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(void)
0x180056a91  lea     rcx, [rbp+80h+var_68]; void *
0x180056a95  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@H_K@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<int,unsigned __int64>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<int,unsigned __int64>>> const &)
0x180056a9a  nop
0x180056a9b  lea     r9, [rbp+80h+var_B0]
0x180056a9f  mov     r8, r15
0x180056aa2  lea     rdx, [rsp+180h+var_150]
0x180056aa7  mov     rcx, rdi
0x180056aaa  call    ??$_Emplace@AEBUPersistentDataKey@MapControl@@U?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@@?$_Tree@V?$_Tmap_traits@$$CBUPersistentDataKey@MapControl@@U?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@U?$less@$$CBUPersistentDataKey@MapControl@@@std@@V?$allocator@U?$pair@$$CBUPersistentDataKey@MapControl@@U?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@@std@@@7@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUPersistentDataKey@MapControl@@U?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@@std@@PEAX@std@@_N@1@AEBUPersistentDataKey@MapControl@@$$QEAU?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@@Z; std::_Tree<std::_Tmap_traits<MapControl::PersistentDataKey const,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>,std::less<MapControl::PersistentDataKey const>,std::allocator<std::pair<MapControl::PersistentDataKey const,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>>>,0>>::_Emplace<MapControl::PersistentDataKey const &,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>>(MapControl::PersistentDataKey const &,Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1> &&)
0x180056aaf  mov     rbx, [rsp+180h+var_150]
0x180056ab4  lea     rcx, [rbp+80h+var_B0]
0x180056ab8  call    ??1?$RequestInternal@$00@?$ComputableMemoryCacheTraits@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@QEAA@XZ; Utility::ComputableMemoryCacheTraits<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::RequestInternal<1>::~RequestInternal<1>(void)
0x180056abd  lea     rcx, [rbp+80h+var_E0]
0x180056ac1  cmp     [rbp+80h+var_D0], 0
0x180056ac5  jnz     short loc_180056AD6
0x180056ac7  lea     rdx, [rbx+30h]
0x180056acb  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180056ad0  mov     [rbp+80h+var_D0], 1
0x180056ad4  jmp     short loc_180056B1A
0x180056ad6  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x180056adb  mov     r8, rax
0x180056ade  lea     rdx, [rbx+30h]
0x180056ae2  lea     rcx, [rsp+180h+var_150]
0x180056ae7  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180056aec  mov     rdx, rax
0x180056aef  mov     rcx, [rax]
0x180056af2  mov     rax, [r8]
0x180056af5  mov     [rdx], rax
0x180056af8  mov     [r8], rcx
0x180056afb  mov     rcx, [rdx+8]
0x180056aff  mov     rax, [r8+8]
0x180056b03  mov     [rdx+8], rax
0x180056b07  mov     [r8+8], rcx
0x180056b0b  mov     rcx, [rsp+180h+var_148]; this
0x180056b10  test    rcx, rcx
0x180056b13  jz      short loc_180056B1A
0x180056b15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056b1a  lea     rcx, [rbx+78h]
0x180056b1e  lea     rdx, [rsp+180h+var_118]
0x180056b23  call    ??$emplace_back@AEBV?$shared_ptr@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@std@@@?$vector@V?$shared_ptr@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@std@@V?$allocator@V?$shared_ptr@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@V?$AsyncOperationImplementation@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@$$CBUPersistentDataKey@MapControl@@@Pal@@@1@AEBV21@@Z; std::vector<std::shared_ptr<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>>>::emplace_back<std::shared_ptr<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>> const &>(std::shared_ptr<Pal::AsyncOperationImplementation<std::shared_ptr<MapControl::OdvsChunkIndex>,MapControl::PersistentDataKey const>> const &)
0x180056b28  mov     rbx, [rbx+30h]
0x180056b2c  mov     r14, [rsp+180h+var_118]
0x180056b31  mov     eax, [r14+18h]
0x180056b35  mov     dword ptr [rsp+180h+var_140], eax
0x180056b39  lea     rdi, [rbx+8]
0x180056b3d  mov     [rsp+180h+var_150], rdi
0x180056b42  mov     rcx, rdi; lpCriticalSection
0x180056b45  call    cs:__imp_EnterCriticalSection
0x180056b4b  nop
0x180056b4c  lea     rcx, [rbx+30h]
0x180056b50  lea     r8, [rsp+180h+var_140]
0x180056b55  lea     rdx, [rbp+80h+var_100]
0x180056b59  call    ??$_Try_emplace@AEBI$$V@?$map@IV?$shared_ptr@VPriorityTag@Pal@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VPriorityTag@Pal@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$shared_ptr@VPriorityTag@Pal@@@std@@@std@@PEAX@std@@_N@1@AEBI@Z; std::map<uint,std::shared_ptr<Pal::PriorityTag>>::_Try_emplace<uint const &,>(uint const &)
0x180056b5e  mov     rcx, [rax]
0x180056b61  add     rcx, 28h ; '('
0x180056b65  mov     rdx, [rsp+180h+var_128]
0x180056b6a  call    ??4?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<MapControl::OdvsChunkIndex>::operator=(std::shared_ptr<MapControl::OdvsChunkIndex> const &)
0x180056b6f  nop
0x180056b70  mov     rcx, rdi; lpCriticalSection
0x180056b73  call    cs:__imp_LeaveCriticalSection
0x180056b79  xor     edi, edi
0x180056b7b  lea     rcx, [rsp+180h+var_138]
0x180056b80  call    ??1?$ScopedLockableValue@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@AEBVExceptionEventArgs@Pal@@@Core@@@Pal@@$01@Core@@@Pal@@QEAA@XZ; Pal::ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>::~ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>(void)
0x180056b85  cmp     [rbp+80h+var_D0], dil
0x180056b89  jz      loc_180056C23
0x180056b8f  lea     rcx, [rbp+80h+var_E0]
0x180056b93  call    ?getValue@?$Optional@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@Core@@QEAAAEAV?$PresentSharedPtr@VVersionSnapshot@MapControl@@@2@XZ; Core::Optional<Core::PresentSharedPtr<MapControl::VersionSnapshot>>::getValue(void)
0x180056b98  mov     rdx, [rax]
0x180056b9b  mov     rcx, [rax+8]
0x180056b9f  test    rcx, rcx
0x180056ba2  jz      short loc_180056BA8
0x180056ba4  lock inc dword ptr [rcx+8]
0x180056ba8  mov     [rsp+180h+var_138], rdx
0x180056bad  mov     r8, [rax+8]
0x180056bb1  mov     [rsp+180h+var_130], r8
0x180056bb6  lea     rdx, [rsp+180h+var_138]
0x180056bbb  lea     rcx, [rsp+180h+var_128]
0x180056bc0  call    ??$?0V?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@@?$StaticVariableBase@V?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@@Pal@@QEAA@$$QEAV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@@Z; Pal::StaticVariableBase<Core::PresentSharedPtr<Pal::PriorityTag>>::StaticVariableBase<Core::PresentSharedPtr<Pal::PriorityTag>>(Core::PresentSharedPtr<Pal::PriorityTag> &&)
0x180056bc5  test    r8, r8
0x180056bc8  jz      short loc_180056BD3
0x180056bca  mov     rcx, r8; this
0x180056bcd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056bd2  nop
0x180056bd3  lea     rcx, [r12+48h]
0x180056bd8  mov     [rsp+180h+var_158], r13
0x180056bdd  mov     eax, dword ptr [rbp+80h+arg_20]
0x180056be3  mov     [rsp+180h+var_160], eax
0x180056be7  lea     r9, [rsp+180h+var_128]
0x180056bec  mov     r8, r15
0x180056bef  lea     rdx, [rsp+180h+var_150]
0x180056bf4  call    ??R?$_Func_class@V?$shared_ptr@VAsyncInfo@Pal@@@std@@AEBUPersistentDataKey@MapControl@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@W4NetworkUsagePreference@4@$$QEAVLoadChunkIndexOperationTracer@4@@std@@QEBA?AV?$shared_ptr@VAsyncInfo@Pal@@@1@AEBUPersistentDataKey@MapControl@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@W4NetworkUsagePreference@4@$$QEAVLoadChunkIndexOperationTracer@4@@Z; std::_Func_class<std::shared_ptr<Pal::AsyncInfo>,MapControl::PersistentDataKey const &,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer &&>::operator()(MapControl::PersistentDataKey const &,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference,MapControl::LoadChunkIndexOperationTracer &&)
0x180056bf9  nop
0x180056bfa  mov     r8, rax
0x180056bfd  mov     rdx, r15
0x180056c00  mov     rcx, r12
0x180056c03  call    ?registerGetItemOperation@?$ComputableMemoryCache@$$CBUPersistentDataKey@MapControl@@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@U?$hash@$$CBUPersistentDataKey@MapControl@@@4@U?$AlwaysTruePredicate@V?$shared_ptr@VOdvsChunkIndex@MapControl@@@std@@@Core@@AEBV?$PresentSharedPtr@VPriorityTag@Pal@@@7@$$CBW4NetworkUsagePreference@2@$$QEAVLoadChunkIndexOperationTracer@2@@Utility@@AEAAXAEBUPersistentDataKey@MapControl@@$$QEAV?$shared_ptr@VAsyncInfo@Pal@@@std@@@Z; Utility::ComputableMemoryCache<MapControl::PersistentDataKey const,std::shared_ptr<MapControl::OdvsChunkIndex>,std::hash<MapControl::PersistentDataKey const>,Core::AlwaysTruePredicate<std::shared_ptr<MapControl::OdvsChunkIndex>>,Core::PresentSharedPtr<Pal::PriorityTag> const &,MapControl::NetworkUsagePreference const,MapControl::LoadChunkIndexOperationTracer &&>::registerGetItemOperation(MapControl::PersistentDataKey const &,std::shared_ptr<Pal::AsyncInfo> &&)
0x180056c08  nop
0x180056c09  mov     rcx, [rsp+180h+var_148]; this
0x180056c0e  test    rcx, rcx
0x180056c11  jz      short loc_180056C19
0x180056c13  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056c18  nop
0x180056c19  lea     rcx, [rsp+180h+var_128]
0x180056c1e  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180056c23  mov     [rsi], rdi
0x180056c26  mov     [rsi+8], rdi
0x180056c2a  mov     rbx, [rsp+180h+var_110]
0x180056c2f  test    rbx, rbx
0x180056c32  jz      short loc_180056C38
0x180056c34  lock inc dword ptr [rbx+8]
0x180056c38  mov     [rsi], r14
0x180056c3b  mov     [rsi+8], rbx
0x180056c3f  cmp     [rbp+80h+var_D0], dil
0x180056c43  jz      short loc_180056C52
0x180056c45  lea     rcx, [rbp+80h+var_E0]
0x180056c49  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180056c4e  mov     [rbp+80h+var_D0], dil
0x180056c52  test    rbx, rbx
0x180056c55  jz      short loc_180056C60
0x180056c57  mov     rcx, rbx; this
0x180056c5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056c5f  nop
0x180056c60  lea     rcx, [rbp+80h+var_C8]
0x180056c64  call    ?clear@?$Optional@V?$shared_ptr@VEndpointDescription@MapControl@@@std@@@Core@@QEAAXXZ; Core::Optional<std::shared_ptr<MapControl::EndpointDescription>>::clear(void)
0x180056c69  nop
0x180056c6a  lea     rcx, [r13+4]
0x180056c6e  call    ?clear@?$Optional@I@Core@@QEAAXXZ; Core::Optional<uint>::clear(void)
0x180056c73  mov     rax, rsi
0x180056c76  mov     rcx, [rbp+80h+var_50]
0x180056c7a  xor     rcx, rsp; StackCookie
0x180056c7d  call    __security_check_cookie
0x180056c82  add     rsp, 148h
0x180056c89  pop     r15
0x180056c8b  pop     r14
0x180056c8d  pop     r13
0x180056c8f  pop     r12
0x180056c91  pop     rdi
0x180056c92  pop     rsi
0x180056c93  pop     rbx
0x180056c94  pop     rbp
0x180056c95  retn
```
