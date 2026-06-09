# Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::~WorkerProcess1(void)

- ea: `0x1800545f0`
- end: `0x180054656`
- name: `??1WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(Windows::AI::IsolationEnvironment::Preview::WorkerProcess1 *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054660`

## callees

- `0x180012ad0`
- `0x1800545f0`
- `0x180055734`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054631`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054631`

## pseudocode

```c
void __fastcall Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::~WorkerProcess1(
        Windows::AI::IsolationEnvironment::Preview::WorkerProcess1 *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable';
  *((_QWORD *)this + 1) = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::KillTheProcess(this);
  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
    CloseHandle(v2);
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  v3 = *((_QWORD *)this + 4);
  if ( v3 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v3);
}

```

## disassembly

```asm
0x1800545f0  push    rbx
0x1800545f2  sub     rsp, 20h
0x1800545f6  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'
0x1800545fd  mov     rbx, rcx
0x180054600  mov     [rcx], rax
0x180054603  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `IWeakReferenceSource'}
0x18005460a  mov     [rcx+8], rax
0x18005460e  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180054615  mov     [rcx+10h], rax
0x180054619  call    ?KillTheProcess@WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@AEAAXXZ; Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::KillTheProcess(void)
0x18005461e  mov     rcx, [rbx+38h]; hObject
0x180054622  test    rcx, rcx
0x180054625  jz      short loc_18005462D
0x180054627  call    cs:__imp_CloseHandle
0x18005462d  mov     rcx, [rbx+28h]; string
0x180054631  call    cs:__imp_WindowsDeleteString
0x180054637  mov     qword ptr [rbx+28h], 0
0x18005463f  mov     rcx, [rbx+20h]
0x180054643  test    rcx, rcx
0x180054646  jns     short loc_180054650
0x180054648  add     rcx, rcx
0x18005464b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180054650  add     rsp, 20h
0x180054654  pop     rbx
0x180054655  retn
```
