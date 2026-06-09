# Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::~WorkerProcess2(void)

- ea: `0x18005d994`
- end: `0x18005da05`
- name: `??1WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::Preview::WorkerProcess2 *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005da10`

## callees

- `0x180012ad0`
- `0x18004f9a4`
- `0x18005d994`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d9d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d9d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d9e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d9e0`

## pseudocode

```c
void __fastcall Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::~WorkerProcess2(
        Windows::AI::IsolationEnvironment::Preview::WorkerProcess2 *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'};
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 3) = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  Windows::AI::IsolationEnvironment::WorkerProcess::KillTheProcess(this);
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    CloseHandle(v2);
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  v3 = *((_QWORD *)this + 5);
  if ( v3 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v3);
}

```

## disassembly

```asm
0x18005d994  push    rbx
0x18005d996  sub     rsp, 20h
0x18005d99a  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess_Exp2@1234@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'}
0x18005d9a1  mov     rbx, rcx
0x18005d9a4  mov     [rcx], rax
0x18005d9a7  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d9ae  mov     [rcx+8], rax
0x18005d9b2  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess_Exp2@1234@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d9b9  mov     [rcx+10h], rax
0x18005d9bd  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005d9c4  mov     [rcx+18h], rax
0x18005d9c8  call    ?KillTheProcess@WorkerProcess@IsolationEnvironment@AI@Windows@@AEAAXXZ; Windows::AI::IsolationEnvironment::WorkerProcess::KillTheProcess(void)
0x18005d9cd  mov     rcx, [rbx+40h]; hObject
0x18005d9d1  test    rcx, rcx
0x18005d9d4  jz      short loc_18005D9DC
0x18005d9d6  call    cs:__imp_CloseHandle
0x18005d9dc  mov     rcx, [rbx+30h]; string
0x18005d9e0  call    cs:__imp_WindowsDeleteString
0x18005d9e6  mov     qword ptr [rbx+30h], 0
0x18005d9ee  mov     rcx, [rbx+28h]
0x18005d9f2  test    rcx, rcx
0x18005d9f5  jns     short loc_18005D9FF
0x18005d9f7  add     rcx, rcx
0x18005d9fa  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005d9ff  add     rsp, 20h
0x18005da03  pop     rbx
0x18005da04  retn
```
