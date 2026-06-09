# Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::~SecondaryTileUserChangedEventArgsServer(void)

- ea: `0x180020188`
- end: `0x1800201d0`
- name: `??1SecondaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@UEAA@XZ`
- size: `72`
- prototype: `void __fastcall(Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800201e0`

## callees

- `0x18001e5dc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800201b5`

## pseudocode

```c
void __fastcall Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::~SecondaryTileUserChangedEventArgsServer(
        Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer *this)
{
  *(_QWORD *)this = &Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180020188  push    rbx
0x18002018a  sub     rsp, 20h
0x18002018e  lea     rax, ??_7SecondaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6B@; const Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable'
0x180020195  mov     rbx, rcx
0x180020198  mov     [rcx], rax
0x18002019b  lea     rax, ??_7SecondaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable'{for `IWeakReferenceSource'}
0x1800201a2  mov     [rcx+8], rax
0x1800201a6  lea     rax, ??_7SecondaryTileUserChangedEventArgsServer@StateRepository@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgsServer::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800201ad  mov     [rcx+10h], rax
0x1800201b1  mov     rcx, [rcx+40h]; string
0x1800201b5  call    cs:__imp_WindowsDeleteString
0x1800201bb  mov     rcx, rbx
0x1800201be  mov     qword ptr [rbx+40h], 0
0x1800201c6  add     rsp, 20h
0x1800201ca  pop     rbx
0x1800201cb  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserChangedEventArgs@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgs,Microsoft::WRL::FtmBase>(void)
```
