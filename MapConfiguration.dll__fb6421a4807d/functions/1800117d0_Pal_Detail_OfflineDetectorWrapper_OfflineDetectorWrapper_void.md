# Pal::Detail::OfflineDetectorWrapper::~OfflineDetectorWrapper(void)

- ea: `0x1800117d0`
- end: `0x180011822`
- name: `??1OfflineDetectorWrapper@Detail@Pal@@UEAA@XZ`
- size: `82`
- prototype: `void __fastcall(Pal::Detail::OfflineDetectorWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012a00`

## callees

- `0x18000b4b8`
- `0x180014cd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011807`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011807`

## pseudocode

```c
void __fastcall Pal::Detail::OfflineDetectorWrapper::~OfflineDetectorWrapper(Pal::Detail::OfflineDetectorWrapper *this)
{
  *(_QWORD *)this = &Pal::Detail::OfflineDetectorWrapper::`vftable'{for `ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 176);
  std::_Func_class<void,>::_Tidy((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x1800117d0  push    rbx
0x1800117d2  sub     rsp, 20h
0x1800117d6  lea     rax, ??_7OfflineDetectorWrapper@Detail@Pal@@6BINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@ABI@@@; const Pal::Detail::OfflineDetectorWrapper::`vftable'{for `ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler'}
0x1800117dd  mov     rbx, rcx
0x1800117e0  mov     [rcx], rax
0x1800117e3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800117ea  mov     [rcx+8], rax
0x1800117ee  add     rcx, 0B0h
0x1800117f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800117fa  lea     rcx, [rbx+58h]
0x1800117fe  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180011803  lea     rcx, [rbx+30h]; lpCriticalSection
0x180011807  call    cs:__imp_DeleteCriticalSection
0x18001180d  lea     rcx, [rbx+20h]
0x180011811  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180011818  add     rsp, 20h
0x18001181c  pop     rbx
0x18001181d  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
