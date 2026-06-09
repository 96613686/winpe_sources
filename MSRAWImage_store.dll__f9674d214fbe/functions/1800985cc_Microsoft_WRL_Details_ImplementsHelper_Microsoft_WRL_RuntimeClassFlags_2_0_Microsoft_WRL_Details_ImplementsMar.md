# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800985cc`
- end: `0x1800985ee`
- name: `??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWICRawMetadataBlockReaderBase@@@Details@23@UIWICMetadataBlockReader@@U?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `34`
- prototype: `__int64 __fastcall(CWICRawMetadataBlockReaderBase *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180098650`
- `0x1800988e0`

## callees

- `0x1800967ac`
- `0x1800986cc`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWICRawMetadataBlockReaderBase>,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>(
        CWICRawMetadataBlockReaderBase *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 18);
  CWICRawMetadataBlockReaderBase::~CWICRawMetadataBlockReaderBase(this);
}

```

## disassembly

```asm
0x1800985cc  push    rbx
0x1800985ce  sub     rsp, 20h
0x1800985d2  mov     rbx, rcx
0x1800985d5  add     rcx, 90h
0x1800985dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800985e1  mov     rcx, rbx; this
0x1800985e4  add     rsp, 20h
0x1800985e8  pop     rbx
0x1800985e9  jmp     ??1CWICRawMetadataBlockReaderBase@@QEAA@XZ; CWICRawMetadataBlockReaderBase::~CWICRawMetadataBlockReaderBase(void)
```
