# CPhotoThumbnailProvider::~CPhotoThumbnailProvider(void)

- ea: `0x18000d274`
- end: `0x18000d2bf`
- name: `??1CPhotoThumbnailProvider@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(CPhotoThumbnailProvider *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d21c`

## callees

- `0x180008b54`
- `0x18000d404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d281`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d281`

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
0x18000d274  push    rbx
0x18000d276  sub     rsp, 20h
0x18000d27a  mov     rbx, rcx
0x18000d27d  add     rcx, 58h ; 'X'; lpCriticalSection
0x18000d281  call    cs:__imp_DeleteCriticalSection
0x18000d288  nop     dword ptr [rax+rax+00h]
0x18000d28d  lea     rcx, [rbx+90h]
0x18000d294  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d299  lea     rcx, [rbx+88h]
0x18000d2a0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d2a5  lea     rcx, [rbx+80h]
0x18000d2ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d2b1  lea     rcx, [rbx+18h]
0x18000d2b5  add     rsp, 20h
0x18000d2b9  pop     rbx
0x18000d2ba  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
