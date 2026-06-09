# PhotoDocumentLoadWorker::~PhotoDocumentLoadWorker(void)

- ea: `0x18001ef6c`
- end: `0x18001f056`
- name: `??1PhotoDocumentLoadWorker@@UEAA@XZ`
- size: `234`
- prototype: `void __fastcall(PhotoDocumentLoadWorker *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001eef4`
- `0x1800611f0`

## callees

- `0x18000cb74`
- `0x18001ef6c`
- `0x18001f05c`
- `0x18001f16c`
- `0x18001f190`
- `0x1800366e0`
- `0x180037084`
- `0x1800378c0`
- `0x180061110`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001efbe`
- `KERNEL32!DeleteCriticalSection` at `0x18001efef`
- `KERNEL32!DeleteCriticalSection` at `0x18001f020`
- `KERNEL32!DeleteCriticalSection` at `0x18001efbe`
- `KERNEL32!DeleteCriticalSection` at `0x18001efef`
- `KERNEL32!DeleteCriticalSection` at `0x18001f020`

## pseudocode

```c
void __fastcall PhotoDocumentLoadWorker::~PhotoDocumentLoadWorker(PhotoDocumentLoadWorker *this)
{
  Base::Thread *v2; // rdi

  *(_QWORD *)this = &PhotoDocumentLoadWorker::`vftable'{for `IPhotoDocumentLoadWorker'};
  *((_QWORD *)this + 1) = &PhotoDocumentLoadWorker::`vftable'{for `IProgressCallback'};
  v2 = (PhotoDocumentLoadWorker *)((char *)this + 16);
  *((_QWORD *)this + 2) = &PhotoDocumentLoadWorker::`vftable'{for `Base::Thread'};
  PhotoDocumentLoadWorker::Abort(this);
  while ( Base::Thread::IsActive(v2) )
    Base::Thread::WaitForDeath(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  ATL::CHandle::~CHandle((PhotoDocumentLoadWorker *)((char *)this + 424));
  ATL::CHandle::~CHandle((PhotoDocumentLoadWorker *)((char *)this + 416));
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>((char *)this + 392);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>((char *)this + 344);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>((char *)this + 336);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>((char *)this + 328);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  ATL::CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>::~CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>((char *)this + 248);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>((char *)this + 96);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 40);
  Base::Thread::~Thread(v2);
}

```

## disassembly

```asm
0x18001ef6c  mov     [rsp+arg_0], rbx
0x18001ef71  push    rdi
0x18001ef72  sub     rsp, 20h
0x18001ef76  mov     rbx, rcx
0x18001ef79  lea     rax, ??_7PhotoDocumentLoadWorker@@6BIPhotoDocumentLoadWorker@@@; const PhotoDocumentLoadWorker::`vftable'{for `IPhotoDocumentLoadWorker'}
0x18001ef80  mov     [rcx], rax
0x18001ef83  lea     rax, ??_7PhotoDocumentLoadWorker@@6BIProgressCallback@@@; const PhotoDocumentLoadWorker::`vftable'{for `IProgressCallback'}
0x18001ef8a  mov     [rcx+8], rax
0x18001ef8e  lea     rdi, [rcx+10h]
0x18001ef92  lea     rax, ??_7PhotoDocumentLoadWorker@@6BThread@Base@@@; const PhotoDocumentLoadWorker::`vftable'{for `Base::Thread'}
0x18001ef99  mov     [rdi], rax
0x18001ef9c  call    ?Abort@PhotoDocumentLoadWorker@@UEAAJXZ; PhotoDocumentLoadWorker::Abort(void)
0x18001efa1  jmp     short loc_18001EFAB
0x18001efa3  mov     rcx, rdi; this
0x18001efa6  call    ?WaitForDeath@Thread@Base@@QEBAXXZ; Base::Thread::WaitForDeath(void)
0x18001efab  mov     rcx, rdi; this
0x18001efae  call    ?IsActive@Thread@Base@@QEBA_NXZ; Base::Thread::IsActive(void)
0x18001efb3  test    al, al
0x18001efb5  jnz     short loc_18001EFA3
0x18001efb7  lea     rcx, [rbx+1C0h]; lpCriticalSection
0x18001efbe  call    cs:__imp_DeleteCriticalSection
0x18001efc4  lea     rcx, [rbx+1A8h]; this
0x18001efcb  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001efd0  lea     rcx, [rbx+1A0h]; this
0x18001efd7  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18001efdc  lea     rcx, [rbx+188h]
0x18001efe3  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001efe8  lea     rcx, [rbx+160h]; lpCriticalSection
0x18001efef  call    cs:__imp_DeleteCriticalSection
0x18001eff5  lea     rcx, [rbx+158h]
0x18001effc  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f001  lea     rcx, [rbx+150h]
0x18001f008  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f00d  lea     rcx, [rbx+148h]
0x18001f014  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f019  lea     rcx, [rbx+118h]; lpCriticalSection
0x18001f020  call    cs:__imp_DeleteCriticalSection
0x18001f026  lea     rcx, [rbx+0F8h]
0x18001f02d  call    ??1?$CAtlArray@VLayerDefinition@PhotoDocumentLoadWorker@@V?$CElementTraits@VLayerDefinition@PhotoDocumentLoadWorker@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>::~CAtlArray<PhotoDocumentLoadWorker::LayerDefinition,ATL::CElementTraits<PhotoDocumentLoadWorker::LayerDefinition>>(void)
0x18001f032  lea     rcx, [rbx+60h]
0x18001f036  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f03b  lea     rcx, [rbx+28h]
0x18001f03f  call    ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18001f044  mov     rcx, rdi; this
0x18001f047  mov     rbx, [rsp+28h+arg_0]
0x18001f04c  add     rsp, 20h
0x18001f050  pop     rdi
0x18001f051  jmp     ??1Thread@Base@@UEAA@XZ; Base::Thread::~Thread(void)
```
