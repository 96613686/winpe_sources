# RemotePullSubscription::~RemotePullSubscription(void)

- ea: `0x180013e6c`
- end: `0x180013f65`
- name: `??1RemotePullSubscription@@UEAA@XZ`
- size: `249`
- prototype: `void __fastcall(RemotePullSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180013e30`

## callees

- `0x180007aa0`
- `0x180013e6c`
- `0x180015730`
- `0x180015768`
- `0x1800157bc`
- `0x18001585c`
- `0x180015880`
- `0x1800158b8`
- `0x180038da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ea2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ea2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013eba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013eb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013eb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180013ec8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180013ec8`

## pseudocode

```c
void __fastcall RemotePullSubscription::~RemotePullSubscription(RemotePullSubscription *this)
{
  PTP_WAIT *v2; // rsi
  void *v3; // rdx

  *(_QWORD *)this = &RemotePullSubscription::`vftable';
  if ( !*((_BYTE *)this + 272) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = (PTP_WAIT *)((char *)this + 184);
  if ( *((_QWORD *)this + 23) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 7);
    SetThreadpoolWait(*v2, 0, 0);
    ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
    WaitForThreadpoolWaitCallbacks(*v2, 1);
  }
  DestroyRpcQueryChannelInfo(*((_DWORD *)this + 67), *((struct tag_EvtRpcQueryChannelInfo **)this + 26));
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    Session::RemoveControllableObject(*((Session **)this + 4), v3);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>((char *)this + 224);
  wmi::AutoRef<Object>::Release((char *)this + 216);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 200);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 192);
  tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&private: static void RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&private: static void RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>((char *)this + 184);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 176);
  tlx::unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 48);
  tlx::unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>((char *)this + 40);
  wmi::AutoRef<Object>::Release((char *)this + 32);
  *(_QWORD *)this = &wmi::RefBase::`vftable';
}

```

## disassembly

```asm
0x180013e6c  push    rbx
0x180013e6e  push    rsi
0x180013e6f  push    rdi
0x180013e70  push    r14
0x180013e72  sub     rsp, 28h
0x180013e76  mov     rdi, rcx
0x180013e79  lea     rax, ??_7RemotePullSubscription@@6B@; const RemotePullSubscription::`vftable'
0x180013e80  mov     [rcx], rax
0x180013e83  cmp     byte ptr [rcx+110h], 0
0x180013e8a  jnz     short loc_180013E91
0x180013e8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013e91  lea     rsi, [rdi+0B8h]
0x180013e98  cmp     qword ptr [rsi], 0
0x180013e9c  jz      short loc_180013ECE
0x180013e9e  lea     rcx, [rdi+38h]; SRWLock
0x180013ea2  call    cs:__imp_AcquireSRWLockExclusive
0x180013ea8  xor     r8d, r8d; pftTimeout
0x180013eab  xor     edx, edx; h
0x180013ead  mov     rcx, [rsi]; pwa
0x180013eb0  call    cs:__imp_SetThreadpoolWait
0x180013eb6  lea     rcx, [rdi+38h]; SRWLock
0x180013eba  call    cs:__imp_ReleaseSRWLockExclusive
0x180013ec0  mov     edx, 1; fCancelPendingCallbacks
0x180013ec5  mov     rcx, [rsi]; pwa
0x180013ec8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180013ece  mov     rdx, [rdi+0D0h]; struct tag_EvtRpcQueryChannelInfo *
0x180013ed5  mov     ecx, [rdi+10Ch]; unsigned int
0x180013edb  call    ?DestroyRpcQueryChannelInfo@@YAXKPEAUtag_EvtRpcQueryChannelInfo@@@Z; DestroyRpcQueryChannelInfo(ulong,tag_EvtRpcQueryChannelInfo *)
0x180013ee0  mov     rdx, [rdi+30h]; void *
0x180013ee4  test    rdx, rdx
0x180013ee7  jz      short loc_180013EF2
0x180013ee9  mov     rcx, [rdi+20h]; this
0x180013eed  call    ?RemoveControllableObject@Session@@QEAA_NPEAX@Z; Session::RemoveControllableObject(void *)
0x180013ef2  lea     rcx, [rdi+0E0h]
0x180013ef9  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180013efe  lea     rcx, [rdi+0D8h]; void *
0x180013f05  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180013f0a  lea     rcx, [rdi+0C8h]
0x180013f11  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180013f16  lea     rcx, [rdi+0C0h]
0x180013f1d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180013f22  mov     rcx, rsi
0x180013f25  call    ??1?$unique_any@U?$handle_traits@PEAU_TP_WAIT@@$$A6AXPEAU1@@Z$1?WaitAndCloseThreadpoolWait@RemotePullSubscription@@CAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>::~unique_any<tlx::handle_traits<_TP_WAIT *,void (_TP_WAIT *),&RemotePullSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *),0>>(void)
0x180013f2a  lea     rcx, [rdi+0B0h]
0x180013f31  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180013f36  lea     rcx, [rdi+30h]
0x180013f3a  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(void)
0x180013f3f  lea     rcx, [rdi+28h]
0x180013f43  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(void)
0x180013f48  lea     rcx, [rdi+20h]; void *
0x180013f4c  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x180013f51  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180013f58  mov     [rdi], rax
0x180013f5b  add     rsp, 28h
0x180013f5f  pop     r14
0x180013f61  pop     rdi
0x180013f62  pop     rsi
0x180013f63  pop     rbx
0x180013f64  retn
```
