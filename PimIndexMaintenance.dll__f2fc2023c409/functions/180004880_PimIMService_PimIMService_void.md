# PimIMService::~PimIMService(void)

- ea: `0x180004880`
- end: `0x180004a4e`
- name: `??1PimIMService@@UEAA@XZ`
- size: `462`
- prototype: `void __fastcall(PimIMService *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004b50`
- `0x1800216c0`

## callees

- `0x18000133c`
- `0x180003d38`
- `0x18000428c`
- `0x180004880`
- `0x18000b5b8`
- `0x18000b614`
- `0x18000b634`
- `0x18000b654`
- `0x18000b960`
- `0x180020568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800048c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800048c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049d0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000497f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000497f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004991`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004991`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000490d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000491f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004931`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004943`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000490d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000491f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004931`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004943`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004955`

## pseudocode

```c
void __fastcall PimIMService::~PimIMService(PimIMService *this)
{
  __int64 **v2; // rbx
  __int64 *v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // rax
  struct _TP_WORK *v6; // rcx
  struct _TP_WORK *v7; // rcx
  struct _TP_WORK *v8; // rcx
  struct _TP_WORK *v9; // rcx
  struct _TP_WORK *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  MetadataUpdates *v12; // rcx

  *(_QWORD *)this = &PimIMService::`vftable'{for `ServiceBase'};
  *((_QWORD *)this + 23) = &PimIMService::`vftable'{for `IndexedFiltering::IIndexManagerClient'};
  *((_QWORD *)this + 24) = &PimIMService::`vftable'{for `CUnknownPrivate'};
  *((_QWORD *)this + 26) = &PimIMService::`vftable'{for `IUSAdviseSink'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 648));
  v2 = (__int64 **)((char *)this + 624);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = (__int64 *)v3[1];
    v5 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v5 + 8) = v4;
    operator delete(v3);
  }
  *((_QWORD *)this + 80) = 0;
  v6 = (struct _TP_WORK *)*((_QWORD *)this + 76);
  if ( v6 )
    CloseThreadpoolWork(v6);
  v7 = (struct _TP_WORK *)*((_QWORD *)this + 74);
  if ( v7 )
    CloseThreadpoolWork(v7);
  v8 = (struct _TP_WORK *)*((_QWORD *)this + 72);
  if ( v8 )
    CloseThreadpoolWork(v8);
  v9 = (struct _TP_WORK *)*((_QWORD *)this + 70);
  if ( v9 )
    CloseThreadpoolWork(v9);
  v10 = (struct _TP_WORK *)*((_QWORD *)this + 68);
  if ( v10 )
    CloseThreadpoolWork(v10);
  tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete((char *)this + 536);
  tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::_Delete((char *)this + 512);
  if ( *((_QWORD *)this + 63) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 61);
  if ( v11 )
    CloseThreadpoolTimer(v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 58);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 368);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 312);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 304);
  v12 = (MetadataUpdates *)*((_QWORD *)this + 36);
  if ( v12 )
    tlx::_delete<MetadataUpdates>(v12);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_ClearList((char *)this + 248);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_FreeBuckets((char *)this + 248);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 27);
  *((_QWORD *)this + 24) = &_CUnknownBase::`vftable';
  ServiceBase::~ServiceBase(this);
}

```

## disassembly

```asm
0x180004880  mov     [rsp+arg_0], rbx
0x180004885  push    rdi
0x180004886  sub     rsp, 20h
0x18000488a  lea     rax, ??_7PimIMService@@6BServiceBase@@@; const PimIMService::`vftable'{for `ServiceBase'}
0x180004891  mov     rdi, rcx
0x180004894  mov     [rcx], rax
0x180004897  lea     rax, ??_7PimIMService@@6BIIndexManagerClient@IndexedFiltering@@@; const PimIMService::`vftable'{for `IndexedFiltering::IIndexManagerClient'}
0x18000489e  mov     [rcx+0B8h], rax
0x1800048a5  lea     rax, ??_7PimIMService@@6BCUnknownPrivate@@@; const PimIMService::`vftable'{for `CUnknownPrivate'}
0x1800048ac  mov     [rcx+0C0h], rax
0x1800048b3  lea     rax, ??_7PimIMService@@6BIUSAdviseSink@@@; const PimIMService::`vftable'{for `IUSAdviseSink'}
0x1800048ba  mov     [rcx+0D0h], rax
0x1800048c1  add     rcx, 288h; lpCriticalSection
0x1800048c8  call    cs:__imp_DeleteCriticalSection
0x1800048ce  lea     rbx, [rdi+270h]
0x1800048d5  mov     rcx, [rbx]; Block
0x1800048d8  cmp     rcx, rbx
0x1800048db  jz      short loc_1800048F9
0x1800048dd  mov     rdx, [rcx+8]
0x1800048e1  mov     rax, [rcx]
0x1800048e4  mov     [rdx], rax
0x1800048e7  mov     [rax+8], rdx
0x1800048eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800048f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800048f7  jmp     short loc_1800048D5
0x1800048f9  mov     qword ptr [rbx+10h], 0
0x180004901  mov     rcx, [rdi+260h]; pwk
0x180004908  test    rcx, rcx
0x18000490b  jz      short loc_180004913
0x18000490d  call    cs:__imp_CloseThreadpoolWork
0x180004913  mov     rcx, [rdi+250h]; pwk
0x18000491a  test    rcx, rcx
0x18000491d  jz      short loc_180004925
0x18000491f  call    cs:__imp_CloseThreadpoolWork
0x180004925  mov     rcx, [rdi+240h]; pwk
0x18000492c  test    rcx, rcx
0x18000492f  jz      short loc_180004937
0x180004931  call    cs:__imp_CloseThreadpoolWork
0x180004937  mov     rcx, [rdi+230h]; pwk
0x18000493e  test    rcx, rcx
0x180004941  jz      short loc_180004949
0x180004943  call    cs:__imp_CloseThreadpoolWork
0x180004949  mov     rcx, [rdi+220h]; pwk
0x180004950  test    rcx, rcx
0x180004953  jz      short loc_18000495B
0x180004955  call    cs:__imp_CloseThreadpoolWork
0x18000495b  lea     rcx, [rdi+218h]
0x180004962  call    ?_Delete@?$auto_xxx@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete(void)
0x180004967  lea     rcx, [rdi+200h]
0x18000496e  call    ?_Delete@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::_Delete(void)
0x180004973  mov     rcx, [rdi+1F8h]
0x18000497a  test    rcx, rcx
0x18000497d  jz      short loc_180004985
0x18000497f  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180004985  mov     rcx, [rdi+1E8h]; pti
0x18000498c  test    rcx, rcx
0x18000498f  jz      short loc_180004997
0x180004991  call    cs:__imp_CloseThreadpoolTimer
0x180004997  lea     rcx, [rdi+1D0h]
0x18000499e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800049a3  lea     rcx, [rdi+1A0h]; lpCriticalSection
0x1800049aa  call    cs:__imp_DeleteCriticalSection
0x1800049b0  lea     rcx, [rdi+178h]; lpCriticalSection
0x1800049b7  call    cs:__imp_DeleteCriticalSection
0x1800049bd  lea     rcx, [rdi+170h]
0x1800049c4  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800049c9  lea     rcx, [rdi+140h]; lpCriticalSection
0x1800049d0  call    cs:__imp_DeleteCriticalSection
0x1800049d6  lea     rcx, [rdi+138h]
0x1800049dd  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800049e2  lea     rcx, [rdi+130h]
0x1800049e9  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800049ee  mov     rcx, [rdi+120h]; Block
0x1800049f5  test    rcx, rcx
0x1800049f8  jz      short loc_1800049FF
0x1800049fa  call    ??$_delete@UMetadataUpdates@@@tlx@@YAXPEAUMetadataUpdates@@@Z; tlx::_delete<MetadataUpdates>(MetadataUpdates *)
0x1800049ff  lea     rbx, [rdi+0F8h]
0x180004a06  mov     rcx, rbx
0x180004a09  call    ?_ClearList@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_ClearList(void)
0x180004a0e  mov     rcx, rbx
0x180004a11  call    ?_FreeBuckets@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_FreeBuckets(void)
0x180004a16  lea     rcx, [rdi+0E0h]
0x180004a1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a22  lea     rcx, [rdi+0D8h]
0x180004a29  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004a2e  lea     rax, ??_7_CUnknownBase@@6B@; const _CUnknownBase::`vftable'
0x180004a35  mov     rcx, rdi; this
0x180004a38  mov     [rdi+0C0h], rax
0x180004a3f  mov     rbx, [rsp+28h+arg_0]
0x180004a44  add     rsp, 20h
0x180004a48  pop     rdi
0x180004a49  jmp     ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
```
