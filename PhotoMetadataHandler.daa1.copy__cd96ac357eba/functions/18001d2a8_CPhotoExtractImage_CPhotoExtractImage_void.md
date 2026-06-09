# CPhotoExtractImage::~CPhotoExtractImage(void)

- ea: `0x18001d2a8`
- end: `0x18001d2f0`
- name: `??1CPhotoExtractImage@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(CPhotoExtractImage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001701c`

## callees

- `0x180007804`
- `0x18000d600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d2b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001d2b8`

## pseudocode

```c
void __fastcall CPhotoExtractImage::~CPhotoExtractImage(CPhotoExtractImage *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 680);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 672);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 664);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 32);
}

```

## disassembly

```asm
0x18001d2a8  push    rbx
0x18001d2aa  sub     rsp, 20h
0x18001d2ae  mov     rbx, rcx
0x18001d2b1  add     rcx, 270h; lpCriticalSection
0x18001d2b8  call    cs:__imp_DeleteCriticalSection
0x18001d2be  lea     rcx, [rbx+2A8h]
0x18001d2c5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d2ca  lea     rcx, [rbx+2A0h]
0x18001d2d1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d2d6  lea     rcx, [rbx+298h]
0x18001d2dd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d2e2  lea     rcx, [rbx+20h]
0x18001d2e6  add     rsp, 20h
0x18001d2ea  pop     rbx
0x18001d2eb  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
