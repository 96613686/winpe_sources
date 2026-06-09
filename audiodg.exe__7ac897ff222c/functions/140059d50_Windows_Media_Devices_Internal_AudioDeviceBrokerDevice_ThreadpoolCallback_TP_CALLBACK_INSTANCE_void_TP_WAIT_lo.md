# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::ThreadpoolCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140059d50`
- end: `0x140059f2e`
- name: `?ThreadpoolCallback@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `478`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140008124`
- `0x1400132f0`
- `0x1400233a0`
- `0x1400378e4`
- `0x14003affc`
- `0x140059d50`
- `0x140059fc8`
- `0x14005d148`
- `0x140084d54`
- `0x1400855fc`
- `0x140085b70`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140059e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140059e7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140059e65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140059edd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140059e65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140059edd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140059efd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140059efd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140059f13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140059f13`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::ThreadpoolCallback(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 *Ptr; // rcx
  __int64 v7; // rax
  struct Windows::Storage::Streams::IBuffer *v8; // rsi
  Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *v9; // rax
  __int64 v10; // rbx
  Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *v11; // rbx
  int v12; // [rsp+20h] [rbp-40h] BYREF
  struct Windows::Storage::Streams::IBuffer *v13; // [rsp+28h] [rbp-38h] BYREF
  Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+38h] [rbp-28h] BYREF
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp-20h] BYREF
  RTL_SRWLOCK *v17; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-10h] BYREF
  char v19; // [rsp+88h] [rbp+28h] BYREF

  wil::CoInitializeEx(&v19);
  if ( Context )
  {
    v12 = 0;
    while ( (*(int (__fastcall **)(PVOID, int *))(*(_QWORD *)Context[24].Ptr + 56LL))(Context[24].Ptr, &v12) >= 0 && v12 )
    {
      v15 = 0;
      v13 = 0;
      Ptr = (__int64 *)Context[24].Ptr;
      v7 = *Ptr;
      v13 = 0;
      (*(void (__fastcall **)(__int64 *, _QWORD, struct Windows::Storage::Streams::IBuffer **))(v7 + 48))(Ptr, 0, &v13);
      if ( v13 )
      {
        (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)Context[24].Ptr + 96LL))(Context[24].Ptr, 0);
        v8 = v13;
        v9 = (Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs *)operator new(
                                                                                       0x48u,
                                                                                       (const struct std::nothrow_t *)std::nothrow);
        v14 = v9;
        v10 = 0;
        if ( v9 )
        {
          v10 = Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs::AudioDeviceBrokerChangedEventArgs(
                  v9,
                  v8);
          v14 = 0;
        }
        Microsoft::WRL::Details::MakeAllocator<GraphStreamingResourceManager>::~MakeAllocator<GraphStreamingResourceManager>(&v14);
        v15 = v10;
        if ( v10 )
        {
          v17 = (RTL_SRWLOCK *)v10;
          v16 = Context;
          v14 = 0;
          AcquireSRWLockExclusive(Context + 20);
          Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v14, &Context[19]);
          if ( Context != (RTL_SRWLOCK *)-160LL )
            ReleaseSRWLockExclusive(Context + 20);
          v11 = v14;
          if ( v14 )
          {
            v18[0] = &v16;
            v18[1] = &v17;
            Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9d7fead59395791ab94fec2ef4162c73_,Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
              v18,
              v14,
              &Context[19]);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
          }
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
      wil::com_ptr_t<Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs,wil::err_returncode_policy>::~com_ptr_t<Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs,wil::err_returncode_policy>(&v15);
    }
    AcquireSRWLockExclusive(Context + 27);
    v17 = Context + 27;
    if ( !LOBYTE(Context[28].Ptr) )
      SetThreadpoolWait(Wait, Context[23].Ptr, 0);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  }
  if ( v19 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140059d50  mov     [rsp-18h+arg_0], rbx
0x140059d55  mov     [rsp-18h+arg_10], rsi
0x140059d5a  push    rbp
0x140059d5b  push    rdi
0x140059d5c  push    r14
0x140059d5e  mov     rbp, rsp
0x140059d61  sub     rsp, 60h
0x140059d65  mov     r14, r8
0x140059d68  mov     rdi, rdx
0x140059d6b  lea     rcx, [rbp+arg_8]
0x140059d6f  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x140059d74  nop
0x140059d75  test    rdi, rdi
0x140059d78  jz      loc_140059F0D
0x140059d7e  mov     [rbp+var_40], 0
0x140059d85  mov     rcx, [rdi+0C0h]
0x140059d8c  mov     rax, [rcx]
0x140059d8f  lea     rdx, [rbp+var_40]
0x140059d93  mov     rax, [rax+38h]
0x140059d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059d9c  test    eax, eax
0x140059d9e  js      loc_140059ED3
0x140059da4  cmp     [rbp+var_40], 0
0x140059da8  jbe     loc_140059ED3
0x140059dae  mov     [rbp+var_28], 0
0x140059db6  mov     [rbp+var_38], 0
0x140059dbe  mov     rcx, [rdi+0C0h]
0x140059dc5  mov     rax, [rcx]
0x140059dc8  mov     [rbp+var_38], 0
0x140059dd0  lea     r8, [rbp+var_38]
0x140059dd4  xor     edx, edx
0x140059dd6  mov     rax, [rax+30h]
0x140059dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059ddf  cmp     [rbp+var_38], 0
0x140059de4  jz      loc_140059EBB
0x140059dea  mov     rcx, [rdi+0C0h]
0x140059df1  mov     rax, [rcx]
0x140059df4  xor     edx, edx
0x140059df6  mov     rax, [rax+60h]
0x140059dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059dff  mov     rsi, [rbp+var_38]
0x140059e03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140059e0a  mov     ecx, 48h ; 'H'; unsigned __int64
0x140059e0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140059e14  mov     [rbp+var_30], rax
0x140059e18  xor     ebx, ebx
0x140059e1a  test    rax, rax
0x140059e1d  jz      short loc_140059E35
0x140059e1f  mov     rdx, rsi; struct Windows::Storage::Streams::IBuffer *
0x140059e22  mov     rcx, rax; this
0x140059e25  call    ??0AudioDeviceBrokerChangedEventArgs@Internal@Devices@Media@Windows@@QEAA@PEAUIBuffer@Streams@Storage@4@@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs::AudioDeviceBrokerChangedEventArgs(Windows::Storage::Streams::IBuffer *)
0x140059e2a  mov     rbx, rax
0x140059e2d  mov     [rbp+var_30], 0
0x140059e35  lea     rcx, [rbp+var_30]
0x140059e39  call    ??1?$MakeAllocator@VGraphStreamingResourceManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<GraphStreamingResourceManager>::~MakeAllocator<GraphStreamingResourceManager>(void)
0x140059e3e  mov     [rbp+var_28], rbx
0x140059e42  test    rbx, rbx
0x140059e45  jz      short loc_140059EBB
0x140059e47  lea     rsi, [rdi+98h]
0x140059e4e  mov     [rbp+var_18], rbx
0x140059e52  mov     [rbp+var_20], rdi
0x140059e56  mov     [rbp+var_30], 0
0x140059e5e  lea     rbx, [rsi+8]
0x140059e62  mov     rcx, rbx; SRWLock
0x140059e65  call    cs:__imp_AcquireSRWLockExclusive
0x140059e6b  mov     rdx, rsi
0x140059e6e  lea     rcx, [rbp+var_30]
0x140059e72  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x140059e77  test    rbx, rbx
0x140059e7a  jz      short loc_140059E85
0x140059e7c  mov     rcx, rbx; SRWLock
0x140059e7f  call    cs:__imp_ReleaseSRWLockExclusive
0x140059e85  mov     rbx, [rbp+var_30]
0x140059e89  test    rbx, rbx
0x140059e8c  jz      short loc_140059EBB
0x140059e8e  lea     rax, [rbp+var_20]
0x140059e92  mov     [rbp+var_10], rax
0x140059e96  lea     rax, [rbp+var_18]
0x140059e9a  mov     [rbp+var_8], rax
0x140059e9e  mov     r8, rsi
0x140059ea1  mov     rdx, rbx
0x140059ea4  lea     rcx, [rbp+var_10]
0x140059ea8  call    ??$InvokeDelegates@V_lambda_9d7fead59395791ab94fec2ef4162c73_@@U?$ITypedEventHandler@PEAVAudioDeviceModulesManager@Devices@Media@Windows@@PEAVAudioDeviceModuleNotificationEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_9d7fead59395791ab94fec2ef4162c73_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVAudioDeviceModulesManager@Devices@Media@Windows@@PEAVAudioDeviceModuleNotificationEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_9d7fead59395791ab94fec2ef4162c73_,Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_9d7fead59395791ab94fec2ef4162c73_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Devices::AudioDeviceModulesManager *,Windows::Media::Devices::AudioDeviceModuleNotificationEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x140059ead  test    rbx, rbx
0x140059eb0  jz      short loc_140059EBB
0x140059eb2  mov     rcx, rbx
0x140059eb5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x140059eba  nop
0x140059ebb  lea     rcx, [rbp+var_38]
0x140059ebf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140059ec4  nop
0x140059ec5  lea     rcx, [rbp+var_28]
0x140059ec9  call    ??1?$com_ptr_t@VAudioDeviceBrokerChangedEventArgs@Internal@Devices@Media@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs,wil::err_returncode_policy>::~com_ptr_t<Windows::Media::Devices::Internal::AudioDeviceBrokerChangedEventArgs,wil::err_returncode_policy>(void)
0x140059ece  jmp     loc_140059D85
0x140059ed3  lea     rbx, [rdi+0D8h]
0x140059eda  mov     rcx, rbx; SRWLock
0x140059edd  call    cs:__imp_AcquireSRWLockExclusive
0x140059ee3  mov     [rbp+var_18], rbx
0x140059ee7  cmp     byte ptr [rdi+0E0h], 0
0x140059eee  jnz     short loc_140059F03
0x140059ef0  xor     r8d, r8d; pftTimeout
0x140059ef3  mov     rdx, [rdi+0B8h]; h
0x140059efa  mov     rcx, r14; pwa
0x140059efd  call    cs:__imp_SetThreadpoolWait
0x140059f03  lea     rcx, [rbp+var_18]
0x140059f07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140059f0c  nop
0x140059f0d  cmp     [rbp+arg_8], 0
0x140059f11  jz      short loc_140059F19
0x140059f13  call    cs:__imp_CoUninitialize
0x140059f19  lea     r11, [rsp+60h+var_s0]
0x140059f1e  mov     rbx, [r11+20h]
0x140059f22  mov     rsi, [r11+30h]
0x140059f26  mov     rsp, r11
0x140059f29  pop     r14
0x140059f2b  pop     rdi
0x140059f2c  pop     rbp
0x140059f2d  retn
```
