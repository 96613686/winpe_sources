# Windows::Media::Devices::AudioDeviceModulesManager::~AudioDeviceModulesManager(void)

- ea: `0x140014c44`
- end: `0x140014d01`
- name: `??1AudioDeviceModulesManager@Devices@Media@Windows@@MEAA@XZ`
- size: `189`
- prototype: `void __fastcall(Windows::Media::Devices::AudioDeviceModulesManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400149f0`

## callees

- `0x140008124`
- `0x14000a39c`
- `0x1400127d8`
- `0x140014c44`
- `0x14001505c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014cb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014cb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014c81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014ce1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140014ce1`

## pseudocode

```c
void __fastcall Windows::Media::Devices::AudioDeviceModulesManager::~AudioDeviceModulesManager(
        Windows::Media::Devices::AudioDeviceModulesManager *this)
{
  RTL_SRWLOCK *v2; // rbx

  *(_QWORD *)this = &Windows::Media::Devices::AudioDeviceModulesManager::`vftable';
  *((_QWORD *)this + 1) = &Windows::Media::Devices::AudioDeviceModulesManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Media::Devices::AudioDeviceModulesManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( *((_BYTE *)this + 128) )
  {
    v2 = (RTL_SRWLOCK *)((char *)this + 64);
    AcquireSRWLockExclusive((PSRWLOCK)this + 8);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 13) + 72LL))(
      *((_QWORD *)this + 13),
      *((_QWORD *)this + 15));
    wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 112);
    *((_BYTE *)this + 128) = 0;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset((char *)this + 104);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 112);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 104);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 80);
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::IAudioDeviceModulesManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::IAudioDeviceModulesManager,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x140014c44  mov     [rsp+arg_0], rbx
0x140014c49  push    rdi
0x140014c4a  sub     rsp, 20h
0x140014c4e  mov     rdi, rcx
0x140014c51  lea     rax, ??_7AudioDeviceModulesManager@Devices@Media@Windows@@6B@; const Windows::Media::Devices::AudioDeviceModulesManager::`vftable'
0x140014c58  mov     [rcx], rax
0x140014c5b  lea     rax, ??_7AudioDeviceModulesManager@Devices@Media@Windows@@6BIWeakReferenceSource@@@; const Windows::Media::Devices::AudioDeviceModulesManager::`vftable'{for `IWeakReferenceSource'}
0x140014c62  mov     [rcx+8], rax
0x140014c66  lea     rax, ??_7AudioDeviceModulesManager@Devices@Media@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Media::Devices::AudioDeviceModulesManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140014c6d  mov     [rcx+10h], rax
0x140014c71  cmp     byte ptr [rcx+80h], 0
0x140014c78  jz      short loc_140014CB9
0x140014c7a  lea     rbx, [rcx+40h]
0x140014c7e  mov     rcx, rbx; SRWLock
0x140014c81  call    cs:__imp_AcquireSRWLockExclusive
0x140014c87  mov     rcx, [rdi+68h]
0x140014c8b  mov     rax, [rcx]
0x140014c8e  mov     rdx, [rdi+78h]
0x140014c92  mov     rax, [rax+48h]
0x140014c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c9b  lea     rcx, [rdi+70h]
0x140014c9f  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140014ca4  mov     byte ptr [rdi+80h], 0
0x140014cab  test    rbx, rbx
0x140014cae  jz      short loc_140014CB9
0x140014cb0  mov     rcx, rbx; SRWLock
0x140014cb3  call    cs:__imp_ReleaseSRWLockExclusive
0x140014cb9  lea     rcx, [rdi+68h]
0x140014cbd  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x140014cc2  lea     rcx, [rdi+70h]
0x140014cc6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140014ccb  lea     rcx, [rdi+68h]
0x140014ccf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140014cd4  lea     rcx, [rdi+50h]
0x140014cd8  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVAudioDeviceBroker@Internal@Devices@Media@Windows@@PEAVAudioDeviceBrokerChangedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x140014cdd  mov     rcx, [rdi+48h]; string
0x140014ce1  call    cs:__imp_WindowsDeleteString
0x140014ce7  mov     qword ptr [rdi+48h], 0
0x140014cef  mov     rcx, rdi
0x140014cf2  mov     rbx, [rsp+28h+arg_0]
0x140014cf7  add     rsp, 20h
0x140014cfb  pop     rdi
0x140014cfc  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAudioDeviceModulesManager@Devices@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::IAudioDeviceModulesManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::IAudioDeviceModulesManager,Microsoft::WRL::FtmBase>(void)
```
