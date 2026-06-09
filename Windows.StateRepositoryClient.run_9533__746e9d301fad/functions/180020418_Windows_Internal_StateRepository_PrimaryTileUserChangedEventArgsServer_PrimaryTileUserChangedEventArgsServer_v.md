# Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::~PrimaryTileUserChangedEventArgsServer(void)

- ea: `0x180020418`
- end: `0x180020460`
- name: `??1PrimaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@UEAA@XZ`
- size: `72`
- prototype: `void __fastcall(Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020470`

## callees

- `0x18001e5dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020445`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020445`

## pseudocode

```c
void __fastcall Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::~PrimaryTileUserChangedEventArgsServer(
        Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer *this)
{
  *(_QWORD *)this = &Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180020418  push    rbx
0x18002041a  sub     rsp, 20h
0x18002041e  lea     rax, ??_7PrimaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6B@; const Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable'
0x180020425  mov     rbx, rcx
0x180020428  mov     [rcx], rax
0x18002042b  lea     rax, ??_7PrimaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable'{for `IWeakReferenceSource'}
0x180020432  mov     [rcx+8], rax
0x180020436  lea     rax, ??_7PrimaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002043d  mov     [rcx+10h], rax
0x180020441  mov     rcx, [rcx+40h]; string
0x180020445  call    cs:__imp_WindowsDeleteString
0x18002044b  mov     rcx, rbx
0x18002044e  mov     qword ptr [rbx+40h], 0
0x180020456  add     rsp, 20h
0x18002045a  pop     rbx
0x18002045b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserChangedEventArgs@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(void)
```
