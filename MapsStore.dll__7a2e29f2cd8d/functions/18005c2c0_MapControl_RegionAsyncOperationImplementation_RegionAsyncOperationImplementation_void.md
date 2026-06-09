# MapControl::RegionAsyncOperationImplementation::~RegionAsyncOperationImplementation(void)

- ea: `0x18005c2c0`
- end: `0x18005c3e0`
- name: `??1RegionAsyncOperationImplementation@MapControl@@UEAA@XZ`
- size: `288`
- prototype: `void __fastcall(MapControl::RegionAsyncOperationImplementation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005c590`

## callees

- `0x180016cbc`
- `0x18001b9e0`
- `0x18001e8f8`
- `0x18002f15c`
- `0x18002f420`
- `0x180049e74`
- `0x18005c2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c3af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c3af`

## pseudocode

```c
void __fastcall MapControl::RegionAsyncOperationImplementation::~RegionAsyncOperationImplementation(
        MapControl::RegionAsyncOperationImplementation *this)
{
  Pal::UntypedAsyncOperationCancelList *v2; // rdi
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // rcx
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx

  *(_QWORD *)this = &MapControl::RegionAsyncOperationImplementation::`vftable';
  v2 = (MapControl::RegionAsyncOperationImplementation *)((char *)this + 344);
  Pal::UntypedAsyncOperationCancelList::cancelAll((LPCRITICAL_SECTION)((char *)this + 344));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 101);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 99);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 97);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 95);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 93);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 91);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 89);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 87);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 85);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 83);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  std::_Hash<std::_Umap_traits<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>,std::_Uhash_compare<MapControl::VersionRequestId,std::hash<MapControl::VersionRequestId>,std::equal_to<MapControl::VersionRequestId>>,std::allocator<std::pair<MapControl::VersionRequestId const,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>>,1>>::~_Hash<std::_Umap_traits<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>,std::_Uhash_compare<MapControl::VersionRequestId,std::hash<MapControl::VersionRequestId>,std::equal_to<MapControl::VersionRequestId>>,std::allocator<std::pair<MapControl::VersionRequestId const,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>>,1>>((char *)this + 592);
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy((char *)this + 512);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 57);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList(v2);
  MapControl::RegionAsyncOperation::~RegionAsyncOperation(this);
}

```

## disassembly

```asm
0x18005c2c0  mov     [rsp+arg_0], rbx
0x18005c2c5  push    rdi
0x18005c2c6  sub     rsp, 20h
0x18005c2ca  mov     rbx, rcx
0x18005c2cd  lea     rax, ??_7RegionAsyncOperationImplementation@MapControl@@6B@; const MapControl::RegionAsyncOperationImplementation::`vftable'
0x18005c2d4  mov     [rcx], rax
0x18005c2d7  lea     rdi, [rcx+158h]
0x18005c2de  mov     rcx, rdi; lpCriticalSection
0x18005c2e1  call    ?cancelAll@UntypedAsyncOperationCancelList@Pal@@QEAAXXZ; Pal::UntypedAsyncOperationCancelList::cancelAll(void)
0x18005c2e6  mov     rcx, [rbx+328h]; this
0x18005c2ed  test    rcx, rcx
0x18005c2f0  jz      short loc_18005C2F7
0x18005c2f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c2f7  mov     rcx, [rbx+318h]; this
0x18005c2fe  test    rcx, rcx
0x18005c301  jz      short loc_18005C308
0x18005c303  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c308  mov     rcx, [rbx+308h]; this
0x18005c30f  test    rcx, rcx
0x18005c312  jz      short loc_18005C319
0x18005c314  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c319  mov     rcx, [rbx+2F8h]; this
0x18005c320  test    rcx, rcx
0x18005c323  jz      short loc_18005C32A
0x18005c325  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c32a  mov     rcx, [rbx+2E8h]; this
0x18005c331  test    rcx, rcx
0x18005c334  jz      short loc_18005C33B
0x18005c336  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c33b  mov     rcx, [rbx+2D8h]; this
0x18005c342  test    rcx, rcx
0x18005c345  jz      short loc_18005C34C
0x18005c347  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c34c  mov     rcx, [rbx+2C8h]; this
0x18005c353  test    rcx, rcx
0x18005c356  jz      short loc_18005C35D
0x18005c358  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c35d  mov     rcx, [rbx+2B8h]; this
0x18005c364  test    rcx, rcx
0x18005c367  jz      short loc_18005C36E
0x18005c369  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c36e  mov     rcx, [rbx+2A8h]; this
0x18005c375  test    rcx, rcx
0x18005c378  jz      short loc_18005C37F
0x18005c37a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c37f  mov     rcx, [rbx+298h]; this
0x18005c386  test    rcx, rcx
0x18005c389  jz      short loc_18005C390
0x18005c38b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c390  lea     rcx, [rbx+250h]
0x18005c397  call    ??1?$_Hash@V?$_Umap_traits@VVersionRequestId@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@V?$_Uhash_compare@VVersionRequestId@MapControl@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$equal_to@VVersionRequestId@MapControl@@@4@@4@V?$allocator@U?$pair@$$CBVVersionRequestId@MapControl@@V?$shared_ptr@VCacheEntry@?$MemoryCache@VVersionRequestId@MapControl@@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@U?$hash@VVersionRequestId@MapControl@@@std@@U?$AlwaysTruePredicate@V?$PresentSharedPtr@VVersionSnapshot@MapControl@@@Core@@@4@@Utility@@@std@@@std@@@4@$00@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>,std::_Uhash_compare<MapControl::VersionRequestId,std::hash<MapControl::VersionRequestId>,std::equal_to<MapControl::VersionRequestId>>,std::allocator<std::pair<MapControl::VersionRequestId const,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>>,1>>::~_Hash<std::_Umap_traits<MapControl::VersionRequestId,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>,std::_Uhash_compare<MapControl::VersionRequestId,std::hash<MapControl::VersionRequestId>,std::equal_to<MapControl::VersionRequestId>>,std::allocator<std::pair<MapControl::VersionRequestId const,std::shared_ptr<Utility::MemoryCache<MapControl::VersionRequestId,Core::PresentSharedPtr<MapControl::VersionSnapshot>,std::hash<MapControl::VersionRequestId>,Core::AlwaysTruePredicate<Core::PresentSharedPtr<MapControl::VersionSnapshot>>>::CacheEntry>>>,1>>(void)
0x18005c39c  lea     rcx, [rbx+200h]
0x18005c3a3  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x18005c3a8  lea     rcx, [rbx+1D0h]; lpCriticalSection
0x18005c3af  call    cs:__imp_DeleteCriticalSection
0x18005c3b5  mov     rcx, [rbx+1C8h]; this
0x18005c3bc  test    rcx, rcx
0x18005c3bf  jz      short loc_18005C3C6
0x18005c3c1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c3c6  mov     rcx, rdi; this
0x18005c3c9  call    ??1UntypedAsyncOperationCancelList@Pal@@QEAA@XZ; Pal::UntypedAsyncOperationCancelList::~UntypedAsyncOperationCancelList(void)
0x18005c3ce  mov     rcx, rbx; this
0x18005c3d1  mov     rbx, [rsp+28h+arg_0]
0x18005c3d6  add     rsp, 20h
0x18005c3da  pop     rdi
0x18005c3db  jmp     ??1RegionAsyncOperation@MapControl@@UEAA@XZ; MapControl::RegionAsyncOperation::~RegionAsyncOperation(void)
```
