# CRAWWICDecoder::~CRAWWICDecoder(void)

- ea: `0x180095be0`
- end: `0x180095c4d`
- name: `??1CRAWWICDecoder@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CRAWWICDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180095d40`

## callees

- `0x180095bb0`
- `0x180095be0`
- `0x1800967ac`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180095c34`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180095c34`

## pseudocode

```c
void __fastcall CRAWWICDecoder::~CRAWWICDecoder(CRAWWICDecoder *this)
{
  __int64 v2; // rcx

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 192);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 168);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 152);
  v2 = *((_QWORD *)this + 18);
  if ( v2 )
  {
    *((_QWORD *)this + 18) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180095be0  push    rbx
0x180095be2  sub     rsp, 20h
0x180095be6  mov     rbx, rcx
0x180095be9  add     rcx, 0C0h
0x180095bf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095bf5  lea     rcx, [rbx+0A8h]
0x180095bfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095c01  lea     rcx, [rbx+98h]
0x180095c08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095c0d  mov     rcx, [rbx+90h]
0x180095c14  test    rcx, rcx
0x180095c17  jz      short loc_180095C30
0x180095c19  mov     qword ptr [rbx+90h], 0
0x180095c24  mov     rax, [rcx]
0x180095c27  mov     rax, [rax+10h]
0x180095c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c30  lea     rcx, [rbx+68h]; lpCriticalSection
0x180095c34  call    cs:__imp_DeleteCriticalSection
0x180095c3b  nop     dword ptr [rax+rax+00h]
0x180095c40  mov     rcx, rbx
0x180095c43  add     rsp, 20h
0x180095c47  pop     rbx
0x180095c48  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>(void)
```
