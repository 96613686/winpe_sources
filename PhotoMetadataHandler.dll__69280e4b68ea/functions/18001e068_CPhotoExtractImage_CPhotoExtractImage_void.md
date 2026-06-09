# CPhotoExtractImage::~CPhotoExtractImage(void)

- ea: `0x18001e068`
- end: `0x18001e0b6`
- name: `??1CPhotoExtractImage@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CPhotoExtractImage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017a78`

## callees

- `0x180008b54`
- `0x18000d404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e078`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e078`

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
0x18001e068  push    rbx
0x18001e06a  sub     rsp, 20h
0x18001e06e  mov     rbx, rcx
0x18001e071  add     rcx, 270h; lpCriticalSection
0x18001e078  call    cs:__imp_DeleteCriticalSection
0x18001e07f  nop     dword ptr [rax+rax+00h]
0x18001e084  lea     rcx, [rbx+2A8h]
0x18001e08b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e090  lea     rcx, [rbx+2A0h]
0x18001e097  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e09c  lea     rcx, [rbx+298h]
0x18001e0a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e0a8  lea     rcx, [rbx+20h]
0x18001e0ac  add     rsp, 20h
0x18001e0b0  pop     rbx
0x18001e0b1  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
