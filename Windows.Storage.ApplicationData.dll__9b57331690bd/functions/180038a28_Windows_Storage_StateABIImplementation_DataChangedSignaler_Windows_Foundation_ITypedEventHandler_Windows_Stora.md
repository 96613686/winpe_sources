# Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::StartWorkerThread(void)

- ea: `0x180038a28`
- end: `0x180038ad4`
- name: `?StartWorkerThread@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@AEAAJXZ`
- size: `172`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037204`

## callees

- `0x1800022b0`
- `0x18001c288`
- `0x18001fe88`
- `0x180021fc4`
- `0x180038a28`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180038a67`
- `ntdll!RtlLeaveCriticalSection` at `0x180038ac1`
- `ntdll!RtlLeaveCriticalSection` at `0x180038a67`
- `ntdll!RtlLeaveCriticalSection` at `0x180038ac1`
- `ntdll!RtlEnterCriticalSection` at `0x180038a47`
- `ntdll!RtlEnterCriticalSection` at `0x180038a47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180038a79`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180038a79`

## string_xrefs

- `0x180038a97`: `CreateThreadpoolWait`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::StartWorkerThread(
        Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)
{
  void *v3; // rdx
  __int64 *v4; // rax
  __int64 v5; // rdi
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int LastErrorMsg; // ebx
  void *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  if ( !this->changedNotifyEvent.m_ptr )
    return 0;
  RtlEnterCriticalSection(&this->threadLock);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
    (Windows::Storage::RestrictedApplicationDataServer *)&v9,
    (Windows::Storage::RestrictedApplicationDataServer_vtbl *)this);
  v5 = *v4;
  if ( this->waitJob )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
    return 0;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::WorkerThreadProcedure,
                     v3,
                     0);
  this->waitJob = ThreadpoolWait;
  if ( !ThreadpoolWait )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( this->waitJob )
  {
    Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::ListenForEvent(this);
    LastErrorMsg = 0;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     0x5Cu,
                     "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIDataChangedSignaler.cpp",
                     "CreateThreadpoolWait");
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
  return LastErrorMsg;
}

```

## disassembly

```asm
0x180038a28  mov     [rsp+10h], rbx
0x180038a2d  push    rdi
0x180038a2e  sub     rsp, 20h
0x180038a32  cmp     qword ptr [this+8], 0
0x180038a37  mov     rbx, this
0x180038a3a  jnz     short loc_180038A43
0x180038a3c  xor     eax, eax
0x180038a3e  jmp     loc_180038AC9
0x180038a43  add     this, 20h ; ' '; CriticalSection
0x180038a47  call    cs:__imp_RtlEnterCriticalSection
0x180038a4d  mov     rdx, rbx
0x180038a50  lea     this, [rsp+30h]; _This
0x180038a55  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180038a5a  cmp     qword ptr [rbx], 0
0x180038a5e  mov     rdi, [rax]
0x180038a61  jz      short loc_180038A6F
0x180038a63  lea     this, [rdi+20h]; CriticalSection
0x180038a67  call    cs:__imp_RtlLeaveCriticalSection
0x180038a6d  jmp     short loc_180038A3C
0x180038a6f  xor     r8d, r8d; pcbe
0x180038a72  lea     this, ?WorkerThreadProcedure@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180038a79  call    cs:__imp_CreateThreadpoolWait
0x180038a7f  mov     [rbx], rax
0x180038a82  test    rax, rax
0x180038a85  jnz     short loc_180038A8C
0x180038a87  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->waitJob != nullptr")
0x180038a8c  cmp     qword ptr [rbx], 0
0x180038a90  jnz     short loc_180038AB3
0x180038a92  mov     this, [rsp+28h]; callerReturnAddress
0x180038a97  lea     r9, aCreatethreadpo; "CreateThreadpoolWait"
0x180038a9e  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\statemanage"...
0x180038aa5  mov     edx, 5Ch ; '\'; lineNumber
0x180038aaa  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180038aaf  mov     ebx, eax
0x180038ab1  jmp     short loc_180038ABD
0x180038ab3  mov     this, rbx; this
0x180038ab6  call    ?ListenForEvent@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@AEAAXXZ; Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::ListenForEvent(void)
0x180038abb  xor     ebx, ebx
0x180038abd  lea     this, [rdi+20h]; CriticalSection
0x180038ac1  call    cs:__imp_RtlLeaveCriticalSection
0x180038ac7  mov     eax, ebx
0x180038ac9  mov     rbx, [rsp+38h]
0x180038ace  add     rsp, 20h
0x180038ad2  pop     rdi
0x180038ad3  retn
```
