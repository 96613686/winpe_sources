# MapsStoreManager::~MapsStoreManager(void)

- ea: `0x18001744c`
- end: `0x1800175e2`
- name: `??1MapsStoreManager@@AEAA@XZ`
- size: `406`
- prototype: `void __fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180096b30`

## callees

- `0x18000ef38`
- `0x180011d28`
- `0x180012720`
- `0x180014fd0`
- `0x180016eb8`
- `0x180016f14`
- `0x1800172f4`
- `0x180017318`
- `0x180017334`
- `0x18001744c`
- `0x180019f3c`
- `0x18001b9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017587`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017587`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800175db`

## pseudocode

```c
void __fastcall MapsStoreManager::~MapsStoreManager(MapsStoreManager *this)
{
  char *v1; // rdi
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rcx

  v1 = (char *)this + 192;
  if ( *((_QWORD *)this + 26) )
    __int2c();
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 79);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::wstring::_Tidy_deallocate((char *)this + 592);
  std::unique_ptr<MapRegionNode>::~unique_ptr<MapRegionNode>((char *)this + 584);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 72);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  std::wstring::_Tidy_deallocate((char *)this + 536);
  std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(
    v5,
    *((_QWORD *)this + 63));
  std::_Deallocate<16>(*((void **)this + 63), 0x18u);
  std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(
    v6,
    *((_QWORD *)this + 61));
  std::_Deallocate<16>(*((void **)this + 61), 0x18u);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 432);
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 53);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 51);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 49);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 47);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 45);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 43);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 41);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  std::_Hash<std::_Uset_traits<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::_Uhash_compare<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::hash<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,std::equal_to<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>>,std::allocator<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,0>>::~_Hash<std::_Uset_traits<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::_Uhash_compare<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::hash<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,std::equal_to<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>>,std::allocator<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,0>>((char *)this + 256);
  std::_Hash<std::_Umap_traits<void *,MapsStoreManager::GridRequestValue,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,MapsStoreManager::GridRequestValue>>,0>>::~_Hash<std::_Umap_traits<void *,MapsStoreManager::GridRequestValue,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,MapsStoreManager::GridRequestValue>>,0>>(v1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  std::unique_ptr<MapControl::RegionManager>::~unique_ptr<MapControl::RegionManager>((char *)this + 144);
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 17);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 120);
  std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>((char *)this + 112);
  std::wstring::_Tidy_deallocate((char *)this + 80);
  std::wstring::_Tidy_deallocate((char *)this + 48);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001744c  mov     [rsp+arg_0], rbx
0x180017451  push    rdi
0x180017452  sub     rsp, 20h
0x180017456  lea     rdi, [rcx+0C0h]
0x18001745d  mov     rbx, rcx
0x180017460  cmp     qword ptr [rdi+10h], 0
0x180017465  jz      short loc_180017469
0x180017467  int     2Ch; Windows NT - assertion failure
0x180017469  mov     rcx, [rcx+278h]; this
0x180017470  test    rcx, rcx
0x180017473  jz      short loc_18001747A
0x180017475  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001747a  lea     rcx, [rbx+250h]
0x180017481  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017486  lea     rcx, [rbx+248h]
0x18001748d  call    ??1?$unique_ptr@VMapRegionNode@@U?$default_delete@VMapRegionNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<MapRegionNode>::~unique_ptr<MapRegionNode>(void)
0x180017492  mov     rcx, [rbx+240h]; this
0x180017499  test    rcx, rcx
0x18001749c  jz      short loc_1800174A3
0x18001749e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800174a3  lea     rcx, [rbx+218h]
0x1800174aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800174af  mov     rdx, [rbx+1F8h]
0x1800174b6  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@std@@@?$_List_node@VRegionId@MapControl@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(std::allocator<std::_List_node<MapControl::RegionId,void *>> &,std::_List_node<MapControl::RegionId,void *> *)
0x1800174bb  mov     rcx, [rbx+1F8h]
0x1800174c2  mov     edx, 18h
0x1800174c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800174cc  mov     rdx, [rbx+1E8h]
0x1800174d3  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@std@@@?$_List_node@VRegionId@MapControl@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(std::allocator<std::_List_node<MapControl::RegionId,void *>> &,std::_List_node<MapControl::RegionId,void *> *)
0x1800174d8  mov     rcx, [rbx+1E8h]
0x1800174df  mov     edx, 18h
0x1800174e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800174e9  lea     rcx, [rbx+1B0h]
0x1800174f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800174f5  mov     rcx, [rbx+1A8h]; this
0x1800174fc  test    rcx, rcx
0x1800174ff  jz      short loc_180017506
0x180017501  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017506  mov     rcx, [rbx+198h]; this
0x18001750d  test    rcx, rcx
0x180017510  jz      short loc_180017517
0x180017512  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017517  mov     rcx, [rbx+188h]; this
0x18001751e  test    rcx, rcx
0x180017521  jz      short loc_180017528
0x180017523  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017528  mov     rcx, [rbx+178h]; this
0x18001752f  test    rcx, rcx
0x180017532  jz      short loc_180017539
0x180017534  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017539  mov     rcx, [rbx+168h]; this
0x180017540  test    rcx, rcx
0x180017543  jz      short loc_18001754A
0x180017545  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001754a  mov     rcx, [rbx+158h]; this
0x180017551  test    rcx, rcx
0x180017554  jz      short loc_18001755B
0x180017556  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001755b  mov     rcx, [rbx+148h]; this
0x180017562  test    rcx, rcx
0x180017565  jz      short loc_18001756C
0x180017567  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001756c  lea     rcx, [rbx+100h]
0x180017573  call    ??1?$_Hash@V?$_Uset_traits@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@V?$_Uhash_compare@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@U?$hash@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@U?$equal_to@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@@2@V?$allocator@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::_Uhash_compare<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::hash<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,std::equal_to<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>>,std::allocator<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,0>>::~_Hash<std::_Uset_traits<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::_Uhash_compare<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>,std::hash<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,std::equal_to<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>>,std::allocator<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>,0>>(void)
0x180017578  mov     rcx, rdi
0x18001757b  call    ??1?$_Hash@V?$_Umap_traits@PEAXUGridRequestValue@MapsStoreManager@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXUGridRequestValue@MapsStoreManager@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<void *,MapsStoreManager::GridRequestValue,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,MapsStoreManager::GridRequestValue>>,0>>::~_Hash<std::_Umap_traits<void *,MapsStoreManager::GridRequestValue,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,MapsStoreManager::GridRequestValue>>,0>>(void)
0x180017580  lea     rcx, [rbx+98h]; lpCriticalSection
0x180017587  call    cs:__imp_DeleteCriticalSection
0x18001758d  lea     rcx, [rbx+90h]
0x180017594  call    ??1?$unique_ptr@VRegionManager@MapControl@@U?$default_delete@VRegionManager@MapControl@@@std@@@std@@QEAA@XZ; std::unique_ptr<MapControl::RegionManager>::~unique_ptr<MapControl::RegionManager>(void)
0x180017599  mov     rcx, [rbx+88h]; this
0x1800175a0  test    rcx, rcx
0x1800175a3  jz      short loc_1800175AA
0x1800175a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800175aa  lea     rcx, [rbx+78h]
0x1800175ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175b3  lea     rcx, [rbx+70h]
0x1800175b7  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x1800175bc  lea     rcx, [rbx+50h]
0x1800175c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800175c5  lea     rcx, [rbx+30h]
0x1800175c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800175ce  mov     rcx, rbx
0x1800175d1  mov     rbx, [rsp+28h+arg_0]
0x1800175d6  add     rsp, 20h
0x1800175da  pop     rdi
0x1800175db  jmp     cs:__imp_DeleteCriticalSection
```
