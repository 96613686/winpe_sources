# Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::~DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>(void)

- ea: `0x180002ebc`
- end: `0x180002f55`
- name: `??1?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aaf8`

## callees

- `0x180002ebc`
- `0x180002f5c`
- `0x180002fd0`
- `0x18000308c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f32`
- `ntdll!RtlDeleteCriticalSection` at `0x180002efa`
- `ntdll!RtlDeleteCriticalSection` at `0x180002efa`
- `ext-ms-win-appmodel-state-ext-l1-2-0!UnsubscribeStateChangeNotification` at `0x180002ed7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!UnsubscribeStateChangeNotification` at `0x180002ed7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002f3d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002f4d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002f3d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateChangeNotification` at `0x180002f4d`

## pseudocode

```c
void __fastcall Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::~DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>(
        Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData> *this)
{
  tag_HSTATE_NOTIFICATION *m_ptr; // rsi
  tag_HSTATE_NOTIFICATION *v3; // rcx
  void *v4; // rcx
  DWORD LastError; // ebx

  if ( this->hStateNotification.m_ptr )
  {
    UnsubscribeStateChangeNotification();
    m_ptr = this->hStateNotification.m_ptr;
    if ( m_ptr )
    {
      LastError = GetLastError();
      CloseStateChangeNotification(m_ptr);
      SetLastError(LastError);
    }
    this->hStateNotification.m_ptr = 0;
  }
  Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::TerminateWorkerThread(this);
  RtlDeleteCriticalSection(&this->threadLock);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>(&this->eventSourceRoaming);
  v3 = this->hStateNotification.m_ptr;
  if ( v3 )
    CloseStateChangeNotification(v3);
  v4 = this->changedNotifyEvent.m_ptr;
  if ( v4 )
    wil::details::CloseHandle(v4);
}

```

## disassembly

```asm
0x180002ebc  mov     [rsp+arg_0], rbx
0x180002ec1  mov     [rsp+arg_8], rsi
0x180002ec6  push    rdi
0x180002ec7  sub     rsp, 20h
0x180002ecb  mov     rdi, this
0x180002ece  mov     this, [this+10h]
0x180002ed2  test    this, this
0x180002ed5  jz      short loc_180002EEE
0x180002ed7  call    cs:__imp_UnsubscribeStateChangeNotification
0x180002edd  mov     rsi, [rdi+10h]
0x180002ee1  test    rsi, rsi
0x180002ee4  jnz     short loc_180002F32
0x180002ee6  mov     qword ptr [rdi+10h], 0
0x180002eee  mov     this, rdi; this
0x180002ef1  call    ?TerminateWorkerThread@?$DataChangedSignaler@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIApplicationData@Storage@3@@StateABIImplementation@Storage@Windows@@AEAAJXZ; Windows::Storage::StateABIImplementation::DataChangedSignaler<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Windows::Storage::IApplicationData>::TerminateWorkerThread(void)
0x180002ef6  lea     this, [rdi+20h]; CriticalSection
0x180002efa  call    cs:__imp_RtlDeleteCriticalSection
0x180002f00  lea     this, [rdi+48h]; this
0x180002f04  call    ??1?$EventSource@U?$ITypedEventHandler@PEAVApplicationData@Storage@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<Windows::Storage::ApplicationData *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180002f09  mov     this, [rdi+10h]
0x180002f0d  test    this, this
0x180002f10  jnz     short loc_180002F4D
0x180002f12  mov     this, [rdi+8]; handle
0x180002f16  test    this, this
0x180002f19  jnz     short loc_180002F2B
0x180002f1b  mov     rbx, [rsp+28h+arg_0]
0x180002f20  mov     rsi, [rsp+28h+arg_8]
0x180002f25  add     rsp, 20h
0x180002f29  pop     rdi
0x180002f2a  retn
0x180002f2b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002f30  jmp     short loc_180002F1B
0x180002f32  call    cs:__imp_GetLastError
0x180002f38  mov     this, rsi
0x180002f3b  mov     ebx, eax
0x180002f3d  call    cs:__imp_CloseStateChangeNotification
0x180002f43  mov     ecx, ebx; dwErrCode
0x180002f45  call    cs:__imp_SetLastError
0x180002f4b  jmp     short loc_180002EE6
0x180002f4d  call    cs:__imp_CloseStateChangeNotification
0x180002f53  jmp     short loc_180002F12
```
