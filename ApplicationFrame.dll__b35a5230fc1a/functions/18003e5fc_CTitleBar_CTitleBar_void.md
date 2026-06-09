# CTitleBar::~CTitleBar(void)

- ea: `0x18003e5fc`
- end: `0x18003e78f`
- name: `??1CTitleBar@@UEAA@XZ`
- size: `403`
- prototype: `void __fastcall(CTitleBar *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003977c`

## callees

- `0x180004c98`
- `0x1800050a4`
- `0x18001044c`
- `0x18001c720`
- `0x18001e260`
- `0x18003e5fc`
- `0x18003e7ac`
- `0x180043c54`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e624`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e624`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTitleBar::~CTitleBar(CTitleBar *this)
{
  std::_Ref_count_base *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  TitleBarTelemetry::TitleBarControlHovered::~TitleBarControlHovered((CTitleBar *)((char *)this + 1592));
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 1512);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 480);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 456);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 56);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 424);
  Microsoft::WRL::ComPtr<CreationThreadDispatcher>::InternalRelease((char *)this + 416);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 408);
  v3 = *((_QWORD *)this + 50);
  if ( v3 )
  {
    *((_QWORD *)this + 50) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 49);
  if ( v4 )
  {
    *((_QWORD *)this + 49) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 384);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 376);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 368);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 360);
  `eh vector destructor iterator'(
    (char *)this + 248,
    8u,
    0xEu,
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>);
  `eh vector destructor iterator'(
    (char *)this + 136,
    8u,
    0xEu,
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 128);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 120);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
  {
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  *((_DWORD *)this + 25) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>((CTitleBar *)((char *)this + 16));
}

```

## disassembly

```asm
0x18003e5fc  push    rbx
0x18003e5fe  sub     rsp, 20h
0x18003e602  mov     rbx, rcx
0x18003e605  add     rcx, 638h; this
0x18003e60c  call    ??1TitleBarControlHovered@TitleBarTelemetry@@QEAA@XZ; TitleBarTelemetry::TitleBarControlHovered::~TitleBarControlHovered(void)
0x18003e611  lea     rcx, [rbx+5E8h]
0x18003e618  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e61d  lea     rcx, [rbx+248h]; lpCriticalSection
0x18003e624  call    cs:__imp_DeleteCriticalSection
0x18003e62a  lea     rcx, [rbx+1E0h]
0x18003e631  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e636  lea     rcx, [rbx+1C8h]
0x18003e63d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e642  mov     rcx, [rbx+1C0h]; this
0x18003e649  test    rcx, rcx
0x18003e64c  jz      short loc_18003E653
0x18003e64e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003e653  lea     rcx, [rbx+1A8h]
0x18003e65a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e65f  lea     rcx, [rbx+1A0h]
0x18003e666  call    ?InternalRelease@?$ComPtr@VCreationThreadDispatcher@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CreationThreadDispatcher>::InternalRelease(void)
0x18003e66b  lea     rcx, [rbx+198h]
0x18003e672  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e677  nop
0x18003e678  mov     rcx, [rbx+190h]
0x18003e67f  test    rcx, rcx
0x18003e682  jz      short loc_18003E69C
0x18003e684  mov     qword ptr [rbx+190h], 0
0x18003e68f  mov     rax, [rcx]
0x18003e692  mov     rax, [rax+10h]
0x18003e696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e69b  nop
0x18003e69c  mov     rcx, [rbx+188h]
0x18003e6a3  test    rcx, rcx
0x18003e6a6  jz      short loc_18003E6C0
0x18003e6a8  mov     qword ptr [rbx+188h], 0
0x18003e6b3  mov     rax, [rcx]
0x18003e6b6  mov     rax, [rax+10h]
0x18003e6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6bf  nop
0x18003e6c0  lea     rcx, [rbx+180h]
0x18003e6c7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e6cc  lea     rcx, [rbx+178h]
0x18003e6d3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e6d8  lea     rcx, [rbx+170h]
0x18003e6df  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e6e4  lea     rcx, [rbx+168h]
0x18003e6eb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e6f0  lea     rcx, [rbx+0F8h]; void *
0x18003e6f7  lea     r9, ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x18003e6fe  mov     edx, 8; unsigned __int64
0x18003e703  lea     r8d, [rdx+6]; unsigned __int64
0x18003e707  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003e70c  lea     rcx, [rbx+88h]; void *
0x18003e713  lea     r9, ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x18003e71a  mov     edx, 8; unsigned __int64
0x18003e71f  lea     r8d, [rdx+6]; unsigned __int64
0x18003e723  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003e728  lea     rcx, [rbx+80h]
0x18003e72f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e734  lea     rcx, [rbx+78h]
0x18003e738  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18003e73d  nop
0x18003e73e  mov     rcx, [rbx+70h]
0x18003e742  test    rcx, rcx
0x18003e745  jz      short loc_18003E75C
0x18003e747  mov     qword ptr [rbx+70h], 0
0x18003e74f  mov     rax, [rcx]
0x18003e752  mov     rax, [rax+10h]
0x18003e756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e75b  nop
0x18003e75c  mov     rcx, [rbx+68h]
0x18003e760  test    rcx, rcx
0x18003e763  jz      short loc_18003E77A
0x18003e765  mov     qword ptr [rbx+68h], 0
0x18003e76d  mov     rax, [rcx]
0x18003e770  mov     rax, [rax+10h]
0x18003e774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e779  nop
0x18003e77a  mov     dword ptr [rbx+64h], 0C0000001h
0x18003e781  lea     rcx, [rbx+10h]; this
0x18003e785  add     rsp, 20h
0x18003e789  pop     rbx
0x18003e78a  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithGITSite@@@Details@23@U?$ChainInterfaces@UIApplicationFrameTitleBarInternal@@UIApplicationFrameTitleBar2@@UIApplicationFrameTitleBar@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,Microsoft::WRL::ChainInterfaces<IApplicationFrameTitleBarInternal,IApplicationFrameTitleBar2,IApplicationFrameTitleBar,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>(void)
```
