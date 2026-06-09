# Windows::Networking::UX::Internal::WlanStateMachine::~WlanStateMachine(void)

- ea: `0x180065464`
- end: `0x180065569`
- name: `??1WlanStateMachine@Internal@UX@Networking@Windows@@QEAA@XZ`
- size: `261`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanStateMachine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048424`

## callees

- `0x180008e30`
- `0x18000bbf4`
- `0x1800644b8`
- `0x180065464`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800654c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800654b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800654b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065544`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::WlanStateMachine::~WlanStateMachine(
        Windows::Networking::UX::Internal::WlanStateMachine *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8

  *(_QWORD *)this = &Windows::Networking::UX::Internal::WlanStateMachine::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 32);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 32) = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 360);
  WindowsDeleteString(*((HSTRING *)this + 44));
  *((_QWORD *)this + 44) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v3 = *((_QWORD *)this + 36);
  *((_QWORD *)this + 36) = 0;
  if ( v3 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>();
  v4 = *((_QWORD *)this + 31);
  if ( v4 )
  {
    *((_QWORD *)this + 31) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  CloseHandle(*((HANDLE *)this + 30));
  *((_QWORD *)this + 30) = 0;
  v5 = *((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  if ( v5 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>();
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 56,
    v6,
    v7);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
    (char *)this + 8,
    v8,
    v9);
}

```

## disassembly

```asm
0x180065464  push    rbx
0x180065466  sub     rsp, 20h
0x18006546a  mov     rbx, rcx
0x18006546d  lea     rax, ??_7WlanStateMachine@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::WlanStateMachine::`vftable'
0x180065474  mov     [rcx], rax
0x180065477  mov     rcx, [rcx+100h]
0x18006547e  test    rcx, rcx
0x180065481  jz      short loc_18006549E
0x180065483  mov     rax, [rcx]
0x180065486  mov     edx, 1
0x18006548b  mov     rax, [rax]
0x18006548e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065493  mov     qword ptr [rbx+100h], 0
0x18006549e  lea     rcx, [rbx+168h]
0x1800654a5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800654aa  mov     rcx, [rbx+160h]; string
0x1800654b1  call    cs:__imp_WindowsDeleteString
0x1800654b7  mov     qword ptr [rbx+160h], 0
0x1800654c2  lea     rcx, [rbx+128h]; lpCriticalSection
0x1800654c9  call    cs:__imp_DeleteCriticalSection
0x1800654cf  nop
0x1800654d0  mov     rdx, [rbx+120h]
0x1800654d7  mov     qword ptr [rbx+120h], 0
0x1800654e2  test    rdx, rdx
0x1800654e5  jz      short loc_1800654ED
0x1800654e7  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x1800654ec  nop
0x1800654ed  mov     rcx, [rbx+0F8h]
0x1800654f4  test    rcx, rcx
0x1800654f7  jz      short loc_180065511
0x1800654f9  mov     qword ptr [rbx+0F8h], 0
0x180065504  mov     rax, [rcx]
0x180065507  mov     rax, [rax+10h]
0x18006550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065510  nop
0x180065511  mov     rcx, [rbx+0F0h]; hObject
0x180065518  call    cs:__imp_CloseHandle
0x18006551e  mov     qword ptr [rbx+0F0h], 0
0x180065529  mov     rdx, [rbx+50h]
0x18006552d  mov     qword ptr [rbx+50h], 0
0x180065535  test    rdx, rdx
0x180065538  jz      short loc_180065540
0x18006553a  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18006553f  nop
0x180065540  mov     rcx, [rbx+40h]; string
0x180065544  call    cs:__imp_WindowsDeleteString
0x18006554a  mov     qword ptr [rbx+40h], 0
0x180065552  lea     rcx, [rbx+38h]
0x180065556  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006555b  lea     rcx, [rbx+8]
0x18006555f  add     rsp, 20h
0x180065563  pop     rbx
0x180065564  jmp     ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
```
