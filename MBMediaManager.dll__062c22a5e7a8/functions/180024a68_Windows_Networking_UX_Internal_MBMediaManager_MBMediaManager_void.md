# Windows::Networking::UX::Internal::MBMediaManager::MBMediaManager(void)

- ea: `0x180024a68`
- end: `0x180024adf`
- name: `??0MBMediaManager@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `119`
- prototype: `Windows::Networking::UX::Internal::MBMediaManager *__fastcall(Windows::Networking::UX::Internal::MBMediaManager *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800120c0`

## callees

- `0x180018610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180024aa8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180024aa8`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180024a96`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180024a96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Windows::Networking::UX::Internal::MBMediaManager *__fastcall Windows::Networking::UX::Internal::MBMediaManager::MBMediaManager(
        Windows::Networking::UX::Internal::MBMediaManager *this)
{
  Windows::Networking::UX::Internal::MBMediaManager *result; // rax

  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>();
  *(_QWORD *)this = &Windows::Networking::UX::Internal::MBMediaManager::`vftable';
  *((_QWORD *)this + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 9) = &Windows::Networking::UX::Internal::MBMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Networking::UX::Internal::INlmListener>'};
  *((_DWORD *)this + 24) = SHTaskPoolGetUniqueContext();
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 104), 0, 0);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = -1;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 21) = 0;
  result = this;
  *((_DWORD *)this + 4) = 2;
  return result;
}

```

## disassembly

```asm
0x180024a68  push    rbx
0x180024a6a  sub     rsp, 20h
0x180024a6e  mov     rbx, rcx
0x180024a71  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VMediaManagerBase@Internal@UX@Networking@Windows@@VINlmListener@5678@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>(void)
0x180024a76  lea     rax, ??_7MBMediaManager@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBMediaManager::`vftable'
0x180024a7d  mov     [rbx], rax
0x180024a80  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VMediaManagerBase@Internal@UX@Networking@Windows@@VINlmListener@5678@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Networking::UX::Internal::MediaManagerBase,Windows::Networking::UX::Internal::INlmListener>::`vftable'{for `IWeakReferenceSource'}
0x180024a87  mov     [rbx+40h], rax
0x180024a8b  lea     rax, ??_7MBMediaManager@Internal@UX@Networking@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00VINlmListener@Internal@UX@Networking@Windows@@@Details@WRL@Microsoft@@@; const Windows::Networking::UX::Internal::MBMediaManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Networking::UX::Internal::INlmListener>'}
0x180024a92  mov     [rbx+48h], rax
0x180024a96  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180024a9c  lea     rcx, [rbx+68h]; lpCriticalSection
0x180024aa0  xor     r8d, r8d; Flags
0x180024aa3  xor     edx, edx; dwSpinCount
0x180024aa5  mov     [rbx+60h], eax
0x180024aa8  call    cs:__imp_InitializeCriticalSectionEx
0x180024aae  xor     eax, eax
0x180024ab0  mov     [rbx+90h], rax
0x180024ab7  mov     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x180024ac2  mov     [rbx+0A0h], eax
0x180024ac8  mov     [rbx+0A8h], rax
0x180024acf  mov     rax, rbx
0x180024ad2  mov     dword ptr [rbx+10h], 2
0x180024ad9  add     rsp, 20h
0x180024add  pop     rbx
0x180024ade  retn
```
