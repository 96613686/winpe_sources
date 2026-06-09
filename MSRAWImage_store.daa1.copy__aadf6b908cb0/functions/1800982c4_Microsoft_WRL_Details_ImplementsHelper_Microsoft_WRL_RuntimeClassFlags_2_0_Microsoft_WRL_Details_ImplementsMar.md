# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800982c4`
- end: `0x180098358`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWICRawMetadataBlockReaderBase@@@Details@23@UIWICMetadataBlockReader@@U?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180098404`

## callees

- `0x1800060a0`
- `0x180095a74`
- `0x180098290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800982e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800982e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx

  *(_QWORD *)a1 = &CWICRawMetadataBlockReaderBase::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_BYTE *)(a1 + 76) = 0;
  `eh vector constructor iterator'(
    (void *)(a1 + 80),
    8u,
    2u,
    Microsoft::WRL::ComPtr<IWICMetadataReader>::ComPtr<IWICMetadataReader>,
    (void (*)(void *))Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::~ComPtr<IWICMetadataBlockReader>);
  *(_DWORD *)(a1 + 96) = 0;
  Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(a1 + 112);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
  return a1;
}

```

## disassembly

```asm
0x1800982c4  mov     [rsp+arg_0], rcx
0x1800982c9  push    rbx
0x1800982ca  sub     rsp, 40h
0x1800982ce  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800982d7  mov     rbx, rcx
0x1800982da  lea     rax, ??_7CWICRawMetadataBlockReaderBase@@6B@; const CWICRawMetadataBlockReaderBase::`vftable'
0x1800982e1  mov     [rcx], rax
0x1800982e4  add     rcx, 10h; lpCriticalSection
0x1800982e8  call    cs:__imp_InitializeCriticalSection
0x1800982ef  nop     dword ptr [rax+rax+00h]
0x1800982f4  nop
0x1800982f5  mov     qword ptr [rbx+38h], 0
0x1800982fd  mov     qword ptr [rbx+40h], 0
0x180098305  mov     dword ptr [rbx+48h], 0
0x18009830c  mov     byte ptr [rbx+4Ch], 0
0x180098310  lea     rcx, [rbx+50h]; void *
0x180098314  lea     rax, ??1?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::~ComPtr<IWICMetadataBlockReader>(void)
0x18009831b  mov     [rsp+48h+var_28], rax; void (*)(void *)
0x180098320  lea     r9, ??0?$ComPtr@UIWICMetadataReader@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180098327  mov     edx, 8; unsigned __int64
0x18009832c  lea     r8d, [rdx-6]; unsigned __int64
0x180098330  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180098335  mov     dword ptr [rbx+60h], 0
0x18009833c  lea     rcx, [rbx+70h]
0x180098340  call    ??0?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>(void)
0x180098345  add     rcx, 8; this
0x180098349  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18009834e  mov     rax, rbx
0x180098351  add     rsp, 40h
0x180098355  pop     rbx
0x180098356  retn
```
