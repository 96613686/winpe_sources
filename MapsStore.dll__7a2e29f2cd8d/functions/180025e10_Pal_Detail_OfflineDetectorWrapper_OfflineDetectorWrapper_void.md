# Pal::Detail::OfflineDetectorWrapper::~OfflineDetectorWrapper(void)

- ea: `0x180025e10`
- end: `0x180025e62`
- name: `??1OfflineDetectorWrapper@Detail@Pal@@UEAA@XZ`
- size: `82`
- prototype: `void __fastcall(Pal::Detail::OfflineDetectorWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026db0`

## callees

- `0x180016cbc`
- `0x180019f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025e47`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025e47`

## pseudocode

```c
void __fastcall Pal::Detail::OfflineDetectorWrapper::~OfflineDetectorWrapper(Pal::Detail::OfflineDetectorWrapper *this)
{
  *(_QWORD *)this = &Pal::Detail::OfflineDetectorWrapper::`vftable'{for `ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 176);
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x180025e10  push    rbx
0x180025e12  sub     rsp, 20h
0x180025e16  lea     rax, ??_7OfflineDetectorWrapper@Detail@Pal@@6BINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@ABI@@@; const Pal::Detail::OfflineDetectorWrapper::`vftable'{for `ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler'}
0x180025e1d  mov     rbx, rcx
0x180025e20  mov     [rcx], rax
0x180025e23  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UINetworkStatusChangedEventHandler@Connectivity@Networking@Windows@ABI@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ABI::Windows::Networking::Connectivity::INetworkStatusChangedEventHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180025e2a  mov     [rcx+8], rax
0x180025e2e  add     rcx, 0B0h
0x180025e35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025e3a  lea     rcx, [rbx+58h]
0x180025e3e  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x180025e43  lea     rcx, [rbx+30h]; lpCriticalSection
0x180025e47  call    cs:__imp_DeleteCriticalSection
0x180025e4d  lea     rcx, [rbx+20h]
0x180025e51  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180025e58  add     rsp, 20h
0x180025e5c  pop     rbx
0x180025e5d  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
