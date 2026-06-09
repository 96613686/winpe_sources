# ClipboardDataObjectTask::~ClipboardDataObjectTask(void)

- ea: `0x18002ff94`
- end: `0x18003006d`
- name: `??1ClipboardDataObjectTask@@UEAA@XZ`
- size: `217`
- prototype: `void __fastcall(ClipboardDataObjectTask *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180091cb0`

## callees

- `0x18000a0e8`
- `0x18002ff94`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003004d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003004d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003002a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003002a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002ffdd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002ffdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002ffd3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002ffd3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030001`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180030001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ffbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ffbd`

## pseudocode

```c
void __fastcall ClipboardDataObjectTask::~ClipboardDataObjectTask(ClipboardDataObjectTask *this)
{
  bool v1; // zf
  Microsoft::WRL::ComPtr<IOSTaskCompletion> *p_m_spTaskCompletion; // rdi
  IOSTaskCompletion *ptr; // rdx
  _TP_TIMER *ThreadpoolTimer; // rax
  _FILETIME ftTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = this->m_pCancellationTimer == 0;
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::IClipboardTaskCompletion::IUnknown::lpVtbl = (struct IUnknownVtbl *)ClipboardDataObjectTask::`vftable'{for `IClipboardTaskCompletion'};
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::lpVtbl = (struct IUnknownVtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( !v1 )
  {
    if ( this->m_dwCancellationThreadId != GetCurrentThreadId() )
      WaitForThreadpoolTimerCallbacks(this->m_pCancellationTimer, 1);
    CloseThreadpoolTimer(this->m_pCancellationTimer);
    this->m_pCancellationTimer = 0;
  }
  p_m_spTaskCompletion = &this->m_spTaskCompletion;
  ptr = this->m_spTaskCompletion.ptr_;
  if ( ptr )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ClipboardDataObjectTask::MTATaskCleanupWorker, ptr, 0);
    if ( ThreadpoolTimer )
    {
      p_m_spTaskCompletion->ptr_ = 0;
      ftTime = (_FILETIME)-30000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &ftTime, 0, 0);
    }
    else
    {
      ((void (__fastcall *)(IOSTaskCompletion *))p_m_spTaskCompletion->ptr_->lpVtbl[1].Release)(p_m_spTaskCompletion->ptr_);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->m_spTaskCompletion);
  DeleteCriticalSection(&this->m_CallCS.cs_);
  this->refcount_ = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->marshaller_);
}

```

## disassembly

```asm
0x18002ff94  mov     [rsp+arg_8], rbx
0x18002ff99  push    rdi
0x18002ff9a  sub     rsp, 20h
0x18002ff9e  cmp     qword ptr [this+60h], 0
0x18002ffa3  lea     rax, ??_7ClipboardDataObjectTask@@6BIClipboardTaskCompletion@@@; const ClipboardDataObjectTask::`vftable'{for `IClipboardTaskCompletion'}
0x18002ffaa  mov     [this], rax
0x18002ffad  mov     rbx, this
0x18002ffb0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClipboardTaskCompletion@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002ffb7  mov     [this+8], rax
0x18002ffbb  jz      short loc_18002FFEB
0x18002ffbd  call    cs:__imp_GetCurrentThreadId
0x18002ffc3  mov     edx, [rbx+6Ch]
0x18002ffc6  cmp     edx, eax
0x18002ffc8  jz      short loc_18002FFD9
0x18002ffca  mov     this, [rbx+60h]; pti
0x18002ffce  mov     edx, 1; fCancelPendingCallbacks
0x18002ffd3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002ffd9  mov     this, [rbx+60h]; pti
0x18002ffdd  call    cs:__imp_CloseThreadpoolTimer
0x18002ffe3  mov     qword ptr [rbx+60h], 0
0x18002ffeb  lea     rdi, [rbx+78h]
0x18002ffef  mov     rdx, [rdi]; pv
0x18002fff2  test    rdx, rdx
0x18002fff5  jz      short loc_180030041
0x18002fff7  xor     r8d, r8d; pcbe
0x18002fffa  lea     this, ?MTATaskCleanupWorker@ClipboardDataObjectTask@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180030001  call    cs:__imp_CreateThreadpoolTimer
0x180030007  test    rax, rax
0x18003000a  jz      short loc_180030032
0x18003000c  xor     r9d, r9d; msWindowLength
0x18003000f  mov     qword ptr [rdi], 0
0x180030016  xor     r8d, r8d; msPeriod
0x180030019  mov     qword ptr [rsp+28h+ftTime.dwLowDateTime], 0FFFFFFFFFE363C80h
0x180030022  lea     rdx, [rsp+28h+ftTime]; pftDueTime
0x180030027  mov     this, rax; pti
0x18003002a  call    cs:__imp_SetThreadpoolTimer
0x180030030  jmp     short loc_180030041
0x180030032  mov     this, [rdi]
0x180030035  mov     rax, [this]
0x180030038  mov     rax, [rax+28h]
0x18003003c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030041  mov     this, rdi; this
0x180030044  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180030049  lea     this, [rbx+30h]; lpCriticalSection
0x18003004d  call    cs:__imp_DeleteCriticalSection
0x180030053  lea     this, [rbx+20h]
0x180030057  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18003005e  mov     rbx, [rsp+28h+arg_8]
0x180030063  add     rsp, 20h
0x180030067  pop     rdi
0x180030068  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
