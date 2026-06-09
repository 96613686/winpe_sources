# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x180004090`
- end: `0x1800040f6`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIApplicationData@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `102`
- prototype: `void __fastcall(Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003e78`
- `0x180003fa8`

## callees

- `0x180004090`
- `0x180004100`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040ca`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800040ee`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800040ee`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData> > *m_callback; // rcx
  unsigned int m_threadId; // ebx

  m_callback = this->m_callback;
  if ( m_callback )
    ((void (__fastcall *)(Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData> > *, __int64))m_callback->~Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData> >)(
      m_callback,
      1);
  m_threadId = this->m_asyncHandler.m_threadId;
  this->m_callback = 0;
  if ( GetCurrentThreadId() != m_threadId )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement(&this->m_completionsAllowed);
  Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(&this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> >,Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion> >);
}

```

## disassembly

```asm
0x180004090  mov     [rsp+arg_0], rbx
0x180004095  push    rdi
0x180004096  sub     rsp, 20h
0x18000409a  mov     rdi, this
0x18000409d  mov     this, [this+108h]
0x1800040a4  test    this, this
0x1800040a7  jz      short loc_1800040B9
0x1800040a9  mov     rax, [this]
0x1800040ac  mov     edx, 1
0x1800040b1  mov     rax, [rax]
0x1800040b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b9  mov     ebx, [rdi+158h]
0x1800040bf  mov     qword ptr [rdi+108h], 0
0x1800040ca  call    cs:__imp_GetCurrentThreadId
0x1800040d0  cmp     eax, ebx
0x1800040d2  jnz     short loc_1800040EE
0x1800040d4  lock inc dword ptr [rdi+110h]
0x1800040db  lea     this, [rdi+8]
0x1800040df  mov     rbx, [rsp+28h+arg_0]
0x1800040e4  add     rsp, 20h
0x1800040e8  pop     rdi
0x1800040e9  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
0x1800040ee  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x1800040f4  jmp     short loc_1800040D4
```
