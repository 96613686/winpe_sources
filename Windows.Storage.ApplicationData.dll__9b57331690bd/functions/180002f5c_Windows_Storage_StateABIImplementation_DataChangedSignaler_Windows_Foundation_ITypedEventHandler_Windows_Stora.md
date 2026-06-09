# Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::TerminateWorkerThread(void)

- ea: `0x180002f5c`
- end: `0x180002fc8`
- name: `?TerminateWorkerThread@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@AEAAJXZ`
- size: `108`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002ebc`

## callees

- `0x180002f5c`
- `0x180003048`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180002f8a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002f8a`
- `ntdll!RtlEnterCriticalSection` at `0x180002f6d`
- `ntdll!RtlEnterCriticalSection` at `0x180002f6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002fa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180002fa2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002fb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180002fb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002fb9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180002fb9`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::TerminateWorkerThread(
        Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)
{
  RtlEnterCriticalSection(&this->threadLock);
  if ( this->waitJob )
  {
    SetThreadpoolWait(this->waitJob, 0, 0);
    WaitForThreadpoolWaitCallbacks(this->waitJob, 1);
    CloseThreadpoolWait(this->waitJob);
    this->waitJob = 0;
  }
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &this->changedNotifyEvent,
    0);
  RtlLeaveCriticalSection(&this->threadLock);
  return 0;
}

```

## disassembly

```asm
0x180002f5c  mov     [rsp+arg_0], rbx
0x180002f61  push    rdi
0x180002f62  sub     rsp, 20h
0x180002f66  mov     rbx, this
0x180002f69  add     this, 20h ; ' '; CriticalSection
0x180002f6d  call    cs:__imp_RtlEnterCriticalSection
0x180002f73  mov     this, [rbx]; pwa
0x180002f76  test    this, this
0x180002f79  jnz     short loc_180002F9D
0x180002f7b  lea     this, [rbx+8]; this
0x180002f7f  xor     edx, edx; ptr
0x180002f81  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180002f86  lea     this, [rbx+20h]; CriticalSection
0x180002f8a  call    cs:__imp_RtlLeaveCriticalSection
0x180002f90  mov     rbx, [rsp+28h+arg_0]
0x180002f95  xor     eax, eax
0x180002f97  add     rsp, 20h
0x180002f9b  pop     rdi
0x180002f9c  retn
0x180002f9d  xor     r8d, r8d; pftTimeout
0x180002fa0  xor     edx, edx; h
0x180002fa2  call    cs:__imp_SetThreadpoolWait
0x180002fa8  mov     this, [rbx]; pwa
0x180002fab  mov     edx, 1; fCancelPendingCallbacks
0x180002fb0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180002fb6  mov     this, [rbx]; pwa
0x180002fb9  call    cs:__imp_CloseThreadpoolWait
0x180002fbf  mov     qword ptr [rbx], 0
0x180002fc6  jmp     short loc_180002F7B
```
