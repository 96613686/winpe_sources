# dxg::svc::Host::ShutdownService(void)

- ea: `0x180026074`
- end: `0x1800260cd`
- name: `?ShutdownService@Host@svc@dxg@@SAXXZ`
- size: `89`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e8e0`
- `0x18000fb50`
- `0x1800115f0`
- `0x180026210`

## callees

- `0x18000e418`
- `0x18000e700`
- `0x180026044`
- `0x180026074`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dxg::svc::Host::ShutdownService(void)
{
  void *v0; // rdx
  _BYTE v1[24]; // [rsp+20h] [rbp-18h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v1, &g::ShutdownMutex);
  if ( !g::ShutdownCallbackInvoked )
  {
    if ( qword_180042E18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180042E18 + 16LL))(qword_180042E18);
    wil::details::SetEvent(g::ShutdownEvent, v0);
    g::ShutdownCallbackInvoked = 1;
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v1);
}

```

## disassembly

```asm
0x180026074  sub     rsp, 38h
0x180026078  lea     rdx, ?ShutdownMutex@g@@3Vmutex@std@@A; std::mutex g::ShutdownMutex
0x18002607f  lea     rcx, [rsp+38h+var_18]
0x180026084  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180026089  nop
0x18002608a  cmp     cs:?ShutdownCallbackInvoked@g@@3_NA, 0; bool g::ShutdownCallbackInvoked
0x180026091  jnz     short loc_1800260BE
0x180026093  mov     rcx, cs:qword_180042E18
0x18002609a  test    rcx, rcx
0x18002609d  jz      short loc_1800260AB
0x18002609f  mov     rax, [rcx]
0x1800260a2  mov     rax, [rax+10h]
0x1800260a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ab  mov     rcx, cs:?ShutdownEvent@g@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; this
0x1800260b2  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800260b7  mov     cs:?ShutdownCallbackInvoked@g@@3_NA, 1; bool g::ShutdownCallbackInvoked
0x1800260be  lea     rcx, [rsp+38h+var_18]
0x1800260c3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800260c8  add     rsp, 38h
0x1800260cc  retn
```
