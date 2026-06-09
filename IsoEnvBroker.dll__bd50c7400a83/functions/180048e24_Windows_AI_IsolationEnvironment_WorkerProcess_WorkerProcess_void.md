# Windows::AI::IsolationEnvironment::WorkerProcess::~WorkerProcess(void)

- ea: `0x180048e24`
- end: `0x180048e95`
- name: `??1WorkerProcess@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::WorkerProcess *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048ea0`

## callees

- `0x180012ad0`
- `0x180048e24`
- `0x18004f9a4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048e70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048e70`

## pseudocode

```c
void __fastcall Windows::AI::IsolationEnvironment::WorkerProcess::~WorkerProcess(
        Windows::AI::IsolationEnvironment::WorkerProcess *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'};
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  *((_QWORD *)this + 3) = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
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
0x180048e24  push    rbx
0x180048e26  sub     rsp, 20h
0x180048e2a  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess@123@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'}
0x180048e31  mov     rbx, rcx
0x180048e34  mov     [rcx], rax
0x180048e37  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x180048e3e  mov     [rcx+8], rax
0x180048e42  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess@123@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x180048e49  mov     [rcx+10h], rax
0x180048e4d  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180048e54  mov     [rcx+18h], rax
0x180048e58  call    ?KillTheProcess@WorkerProcess@IsolationEnvironment@AI@Windows@@AEAAXXZ; Windows::AI::IsolationEnvironment::WorkerProcess::KillTheProcess(void)
0x180048e5d  mov     rcx, [rbx+40h]; hObject
0x180048e61  test    rcx, rcx
0x180048e64  jz      short loc_180048E6C
0x180048e66  call    cs:__imp_CloseHandle
0x180048e6c  mov     rcx, [rbx+30h]; string
0x180048e70  call    cs:__imp_WindowsDeleteString
0x180048e76  mov     qword ptr [rbx+30h], 0
0x180048e7e  mov     rcx, [rbx+28h]
0x180048e82  test    rcx, rcx
0x180048e85  jns     short loc_180048E8F
0x180048e87  add     rcx, rcx
0x180048e8a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180048e8f  add     rsp, 20h
0x180048e93  pop     rbx
0x180048e94  retn
```
