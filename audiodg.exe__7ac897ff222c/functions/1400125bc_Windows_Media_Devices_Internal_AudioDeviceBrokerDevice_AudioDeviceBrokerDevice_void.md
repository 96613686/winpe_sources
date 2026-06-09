# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::~AudioDeviceBrokerDevice(void)

- ea: `0x1400125bc`
- end: `0x14001271e`
- name: `??1AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@UEAA@XZ`
- size: `354`
- prototype: `void __fastcall(Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140012580`

## callees

- `0x140008124`
- `0x140011e00`
- `0x1400125bc`
- `0x140012724`
- `0x140012780`
- `0x1400127bc`
- `0x1400127d8`
- `0x140016f30`
- `0x1400378e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400126b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400126b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400126f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400126f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400126de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400126de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400126fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400126fd`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x140012713`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x140012713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001266e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001266e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012680`

## pseudocode

```c
void __fastcall Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::~AudioDeviceBrokerDevice(
        Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *this)
{
  _QWORD *v2; // rsi
  void *v3; // rdx
  wil::details *v4; // rcx
  char *v5; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable';
  v2 = (_QWORD *)((char *)this + 144);
  *((_QWORD *)this + 1) = &Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
    (char *)this + 144,
    0);
  if ( *((_QWORD *)this + 22) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 27);
    v5 = (char *)this + 216;
    *((_BYTE *)this + 224) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    SetThreadpoolWait(*((PTP_WAIT *)this + 22), 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 22), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 22));
    *((_QWORD *)this + 22) = 0;
  }
  *((_BYTE *)this + 208) = 1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 112,
    0);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 192);
  v4 = (wil::details *)*((_QWORD *)this + 23);
  if ( v4 )
    wil::details::CloseHandle(v4, v3);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 152);
  if ( *v2 )
    CM_Unregister_Notification();
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 112);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 104);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::Internal::IAudioDeviceBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::Internal::IAudioDeviceBroker,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1400125bc  mov     [rsp+arg_8], rbx
0x1400125c1  mov     [rsp+arg_10], rsi
0x1400125c6  push    rdi
0x1400125c7  sub     rsp, 20h
0x1400125cb  lea     rax, ??_7AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@6B@; const Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable'
0x1400125d2  mov     rdi, rcx
0x1400125d5  mov     [rcx], rax
0x1400125d8  lea     rsi, [rcx+90h]
0x1400125df  lea     rax, ??_7AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@6BIWeakReferenceSource@@@; const Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable'{for `IWeakReferenceSource'}
0x1400125e6  xor     edx, edx
0x1400125e8  mov     [rcx+8], rax
0x1400125ec  lea     rax, ??_7AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400125f3  mov     [rcx+10h], rax
0x1400125f7  mov     rcx, rsi
0x1400125fa  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x1400125ff  cmp     qword ptr [rdi+0B0h], 0
0x140012607  jnz     loc_1400126AC
0x14001260d  xor     edx, edx
0x14001260f  mov     byte ptr [rdi+0D0h], 1
0x140012616  lea     rcx, [rdi+70h]
0x14001261a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14001261f  lea     rcx, [rdi+0C0h]
0x140012626  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001262b  mov     rcx, [rdi+0B8h]; this
0x140012632  test    rcx, rcx
0x140012635  jnz     short loc_1400126A5
0x140012637  lea     rcx, [rdi+98h]
0x14001263e  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVAudioDeviceBroker@Internal@Devices@Media@Windows@@PEAVAudioDeviceBrokerChangedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::Internal::AudioDeviceBroker *,Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x140012643  mov     rcx, [rsi]
0x140012646  test    rcx, rcx
0x140012649  jnz     loc_140012713
0x14001264f  lea     rcx, [rdi+70h]
0x140012653  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140012658  lea     rcx, [rdi+68h]
0x14001265c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012661  lea     rcx, [rdi+60h]
0x140012665  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001266a  mov     rcx, [rdi+50h]; string
0x14001266e  call    cs:__imp_WindowsDeleteString
0x140012674  mov     qword ptr [rdi+50h], 0
0x14001267c  mov     rcx, [rdi+40h]; string
0x140012680  call    cs:__imp_WindowsDeleteString
0x140012686  mov     rcx, rdi
0x140012689  mov     qword ptr [rdi+40h], 0
0x140012691  mov     rbx, [rsp+28h+arg_8]
0x140012696  mov     rsi, [rsp+28h+arg_10]
0x14001269b  add     rsp, 20h
0x14001269f  pop     rdi
0x1400126a0  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAudioDeviceBroker@Internal@Devices@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::Internal::IAudioDeviceBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Devices::Internal::IAudioDeviceBroker,Microsoft::WRL::FtmBase>(void)
0x1400126a5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400126aa  jmp     short loc_140012637
0x1400126ac  lea     rbx, [rdi+0D8h]
0x1400126b3  mov     rcx, rbx; SRWLock
0x1400126b6  call    cs:__imp_AcquireSRWLockExclusive
0x1400126bc  lea     rcx, [rsp+28h+arg_0]
0x1400126c1  mov     [rsp+28h+arg_0], rbx
0x1400126c6  mov     byte ptr [rdi+0E0h], 1
0x1400126cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400126d2  mov     rcx, [rdi+0B0h]; pwa
0x1400126d9  xor     r8d, r8d; pftTimeout
0x1400126dc  xor     edx, edx; h
0x1400126de  call    cs:__imp_SetThreadpoolWait
0x1400126e4  mov     rcx, [rdi+0B0h]; pwa
0x1400126eb  mov     edx, 1; fCancelPendingCallbacks
0x1400126f0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1400126f6  mov     rcx, [rdi+0B0h]; pwa
0x1400126fd  call    cs:__imp_CloseThreadpoolWait
0x140012703  mov     qword ptr [rdi+0B0h], 0
0x14001270e  jmp     loc_14001260D
0x140012713  call    cs:__imp_CM_Unregister_Notification
0x140012719  jmp     loc_14001264F
```
