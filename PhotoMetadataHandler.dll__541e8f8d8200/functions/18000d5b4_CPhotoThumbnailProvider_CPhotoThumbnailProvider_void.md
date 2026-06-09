# CPhotoThumbnailProvider::~CPhotoThumbnailProvider(void)

- ea: `0x18000d5b4`
- end: `0x18000d5f9`
- name: `??1CPhotoThumbnailProvider@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CPhotoThumbnailProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d55c`

## callees

- `0x180007804`
- `0x18000d600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d5c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d5c1`

## pseudocode

```c
void __fastcall CPhotoThumbnailProvider::~CPhotoThumbnailProvider(CPhotoThumbnailProvider *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 144);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 136);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 128);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 24);
}

```

## disassembly

```asm
0x18000d5b4  push    rbx
0x18000d5b6  sub     rsp, 20h
0x18000d5ba  mov     rbx, rcx
0x18000d5bd  add     rcx, 58h ; 'X'; lpCriticalSection
0x18000d5c1  call    cs:__imp_DeleteCriticalSection
0x18000d5c7  lea     rcx, [rbx+90h]
0x18000d5ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d5d3  lea     rcx, [rbx+88h]
0x18000d5da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d5df  lea     rcx, [rbx+80h]
0x18000d5e6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d5eb  lea     rcx, [rbx+18h]
0x18000d5ef  add     rsp, 20h
0x18000d5f3  pop     rbx
0x18000d5f4  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
