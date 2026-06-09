# Windows::Networking::UX::Internal::MBStateMachine::MBStateMachine(void)

- ea: `0x18004d430`
- end: `0x18004d57d`
- name: `??0MBStateMachine@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `333`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180039ee8`

## callees

- `0x18000ccb0`
- `0x18004d430`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004d4be`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004d4be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d4fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d4fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Windows::Networking::UX::Internal::MBStateMachine *__fastcall Windows::Networking::UX::Internal::MBStateMachine::MBStateMachine(
        Windows::Networking::UX::Internal::MBStateMachine *this)
{
  *((_QWORD *)this + 4) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBStateMachineContext>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &Windows::Networking::UX::Internal::MBStateMachine::`vftable';
  *((_QWORD *)this + 1) = &Windows::Networking::UX::Internal::MBStateMachine::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Networking::UX::Internal::MBStateMachine::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBStateMachineContext>'};
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 9) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 152), 0, 0);
  *((_WORD *)this + 96) = 256;
  *((_DWORD *)this + 49) = 0;
  *((_DWORD *)this + 59) = 16;
  *((_DWORD *)this + 60) = 4;
  *((_BYTE *)this + 252) = 0;
  *((_QWORD *)this + 33) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 32) = 1;
  *((_WORD *)this + 136) = 0;
  *((_BYTE *)this + 274) = 0;
  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateMachine::MBStateMachine", 28, "Enter");
  *(_OWORD *)((char *)this + 88) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *(_OWORD *)((char *)this + 136) = 0;
  *((_DWORD *)this + 61) = -1;
  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateMachine::MBStateMachine", 34, "Exit");
  return this;
}

```

## disassembly

```asm
0x18004d430  push    rbx
0x18004d432  sub     rsp, 20h
0x18004d436  mov     rbx, rcx
0x18004d439  mov     qword ptr [rcx+20h], 1
0x18004d441  lea     rax, ??_7?$RuntimeClass@UIMBConnectionFlow@Internal@UX@Networking@Windows@@UIMBStateMachineContext@2345@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable'
0x18004d448  mov     [rcx], rax
0x18004d44b  lea     rax, ??_7?$RuntimeClass@UIMBConnectionFlow@Internal@UX@Networking@Windows@@UIMBStateMachineContext@2345@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable'{for `IWeakReferenceSource'}
0x18004d452  mov     [rcx+8], rax
0x18004d456  lea     rax, ??_7?$RuntimeClass@UIMBConnectionFlow@Internal@UX@Networking@Windows@@UIMBStateMachineContext@2345@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBStateMachineContext@Internal@UX@Networking@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Networking::UX::Internal::IMBConnectionFlow,Windows::Networking::UX::Internal::IMBStateMachineContext>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBStateMachineContext>'}
0x18004d45d  mov     [rcx+10h], rax
0x18004d461  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004d468  test    rcx, rcx
0x18004d46b  jz      short loc_18004D47A
0x18004d46d  mov     rax, [rcx]
0x18004d470  mov     rax, [rax+8]
0x18004d474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d479  nop
0x18004d47a  lea     rax, ??_7MBStateMachine@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBStateMachine::`vftable'
0x18004d481  mov     [rbx], rax
0x18004d484  lea     rax, ??_7MBStateMachine@Internal@UX@Networking@Windows@@6BIWeakReferenceSource@@@; const Windows::Networking::UX::Internal::MBStateMachine::`vftable'{for `IWeakReferenceSource'}
0x18004d48b  mov     [rbx+8], rax
0x18004d48f  lea     rax, ??_7MBStateMachine@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIMBStateMachineContext@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBStateMachine::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Networking::UX::Internal::IMBStateMachineContext>'}
0x18004d496  mov     [rbx+10h], rax
0x18004d49a  mov     qword ptr [rbx+28h], 0
0x18004d4a2  mov     qword ptr [rbx+30h], 0
0x18004d4aa  mov     qword ptr [rbx+48h], 0
0x18004d4b2  lea     rcx, [rbx+98h]; lpCriticalSection
0x18004d4b9  xor     r8d, r8d; Flags
0x18004d4bc  xor     edx, edx; dwSpinCount
0x18004d4be  call    cs:__imp_InitializeCriticalSectionEx
0x18004d4c4  mov     word ptr [rbx+0C0h], 100h
0x18004d4cd  mov     dword ptr [rbx+0C4h], 0
0x18004d4d7  mov     dword ptr [rbx+0ECh], 10h
0x18004d4e1  mov     dword ptr [rbx+0F0h], 4
0x18004d4eb  mov     byte ptr [rbx+0FCh], 0
0x18004d4f2  xor     r9d, r9d; lpName
0x18004d4f5  xor     r8d, r8d; bInitialState
0x18004d4f8  xor     edx, edx; bManualReset
0x18004d4fa  xor     ecx, ecx; lpEventAttributes
0x18004d4fc  call    cs:__imp_CreateEventW
0x18004d502  mov     [rbx+108h], rax
0x18004d509  mov     qword ptr [rbx+100h], 1
0x18004d514  mov     word ptr [rbx+110h], 0
0x18004d51d  mov     byte ptr [rbx+112h], 0
0x18004d524  lea     r8, aEnter; "Enter"
0x18004d52b  mov     edx, 1Ch; unsigned int
0x18004d530  lea     rcx, aWindowsNetwork_160; "Windows::Networking::UX::Internal::MBSt"...
0x18004d537  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18004d53c  xorps   xmm0, xmm0
0x18004d53f  movups  xmmword ptr [rbx+58h], xmm0
0x18004d543  movups  xmmword ptr [rbx+68h], xmm0
0x18004d547  movups  xmmword ptr [rbx+78h], xmm0
0x18004d54b  movups  xmmword ptr [rbx+88h], xmm0
0x18004d552  mov     dword ptr [rbx+0F4h], 0FFFFFFFFh
0x18004d55c  lea     r8, aExit; "Exit"
0x18004d563  mov     edx, 22h ; '"'; unsigned int
0x18004d568  lea     rcx, aWindowsNetwork_160; "Windows::Networking::UX::Internal::MBSt"...
0x18004d56f  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18004d574  mov     rax, rbx
0x18004d577  add     rsp, 20h
0x18004d57b  pop     rbx
0x18004d57c  retn
```
