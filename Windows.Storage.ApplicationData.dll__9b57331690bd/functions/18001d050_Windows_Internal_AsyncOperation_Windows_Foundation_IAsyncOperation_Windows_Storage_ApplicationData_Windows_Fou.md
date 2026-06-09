# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x18001d050`
- end: `0x18001d116`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIApplicationData@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003e78`
- `0x18001d050`
- `0x180022498`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d087`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001d0c7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001d0c7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  HRESULT v2; // ebx
  Microsoft::WRL::CancelTransitionPolicy v3; // r8d
  void *v4; // r9
  DWORD CurrentThreadId; // eax
  Microsoft::WRL::CancelTransitionPolicy v6; // r8d
  void *v7; // r9

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, volatile int *))(**(_QWORD **)&this->m_callbackExecuteCount
                                                                         + 8LL))(
         *(_QWORD *)&this->m_callbackExecuteCount,
         0,
         0,
         &this->m_deferralsCompleted);
  if ( v2 < 0 )
  {
LABEL_5:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      (Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this,
      v2,
      v3,
      v4);
    return (unsigned int)v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  this->m_asyncHandler.m_apartment = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         LODWORD(this->m_marshalResultRetriever.m_agileRef.ptr_),
         HIDWORD(this->m_marshalResultRetriever.m_agileRef.ptr_),
         CurrentThreadId,
         0,
         (unsigned __int64)&this->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion> >
       & -(__int64)(this != (Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)8),
         0);
  if ( v2 < 0 )
  {
    if ( this->m_trustLevel )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        (Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this,
        v2,
        v6,
        v7);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      (Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)((char *)this - 8),
      Execute,
      (unsigned int)v2);
    goto LABEL_5;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001d050  mov     [rsp+arg_0], rbx
0x18001d055  mov     [rsp+arg_8], rsi
0x18001d05a  push    rdi
0x18001d05b  sub     rsp, 30h
0x18001d05f  mov     rdi, this
0x18001d062  xor     r8d, r8d
0x18001d065  mov     this, [this+100h]
0x18001d06c  xor     edx, edx
0x18001d06e  lea     r9, [rdi+118h]
0x18001d075  mov     rax, [this]
0x18001d078  mov     rax, [rax+8]
0x18001d07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d081  mov     ebx, eax
0x18001d083  test    eax, eax
0x18001d085  js      short loc_18001D0EC
0x18001d087  call    cs:__imp_GetCurrentThreadId
0x18001d08d  lea     rdx, [rdi+0C8h]
0x18001d094  mov     [rsp+38h+var_10], 0
0x18001d09d  lea     this, [rdi-8]
0x18001d0a1  mov     [rdi+150h], eax
0x18001d0a7  neg     this
0x18001d0aa  mov     ecx, [rdi+148h]
0x18001d0b0  sbb     r8, r8
0x18001d0b3  xor     r9d, r9d
0x18001d0b6  and     r8, rdx
0x18001d0b9  mov     edx, [rdi+14Ch]
0x18001d0bf  mov     [rsp+38h+var_18], r8
0x18001d0c4  mov     r8d, eax
0x18001d0c7  call    cs:__imp_SHTaskPoolQueueTask
0x18001d0cd  mov     ebx, eax
0x18001d0cf  test    eax, eax
0x18001d0d1  jns     short loc_18001D0F6
0x18001d0d3  mov     eax, [rdi+0F8h]
0x18001d0d9  test    eax, eax
0x18001d0db  jnz     short loc_18001D108
0x18001d0dd  mov     r8d, ebx; hr
0x18001d0e0  lea     edx, [rax+1]; stage
0x18001d0e3  lea     this, [rdi-8]; this
0x18001d0e7  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIApplicationData@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x18001d0ec  mov     edx, ebx; error
0x18001d0ee  mov     this, rdi; this
0x18001d0f1  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001d0f6  mov     rsi, [rsp+38h+arg_8]
0x18001d0fb  mov     eax, ebx
0x18001d0fd  mov     rbx, [rsp+38h+arg_0]
0x18001d102  add     rsp, 30h
0x18001d106  pop     rdi
0x18001d107  retn
0x18001d108  mov     edx, ebx; error
0x18001d10a  mov     this, rdi; this
0x18001d10d  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001d112  xor     ebx, ebx
0x18001d114  jmp     short loc_18001D0F6
```
