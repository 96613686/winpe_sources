# Windows::System::ProcessLauncherOptionsImpl::~ProcessLauncherOptionsImpl(void)

- ea: `0x18000aff8`
- end: `0x18000b09a`
- name: `??1ProcessLauncherOptionsImpl@System@Windows@@UEAA@XZ`
- size: `162`
- prototype: `void __fastcall(Windows::System::ProcessLauncherOptionsImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b310`

## callees

- `0x18000aeec`
- `0x18000aff8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b025`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::System::ProcessLauncherOptionsImpl::~ProcessLauncherOptionsImpl(
        Windows::System::ProcessLauncherOptionsImpl *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &Windows::System::ProcessLauncherOptionsImpl::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::ProcessLauncherOptionsImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::System::ProcessLauncherOptionsImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    *((_QWORD *)this + 10) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    *((_QWORD *)this + 8) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18000aff8  push    rbx
0x18000affa  sub     rsp, 20h
0x18000affe  mov     rbx, rcx
0x18000b001  lea     rax, ??_7ProcessLauncherOptionsImpl@System@Windows@@6B@; const Windows::System::ProcessLauncherOptionsImpl::`vftable'
0x18000b008  mov     [rcx], rax
0x18000b00b  lea     rax, ??_7ProcessLauncherOptionsImpl@System@Windows@@6BIWeakReferenceSource@@@; const Windows::System::ProcessLauncherOptionsImpl::`vftable'{for `IWeakReferenceSource'}
0x18000b012  mov     [rcx+8], rax
0x18000b016  lea     rax, ??_7ProcessLauncherOptionsImpl@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::ProcessLauncherOptionsImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000b01d  mov     [rcx+10h], rax
0x18000b021  mov     rcx, [rcx+58h]; string
0x18000b025  call    cs:__imp_WindowsDeleteString
0x18000b02b  mov     qword ptr [rbx+58h], 0
0x18000b033  mov     rcx, [rbx+50h]
0x18000b037  test    rcx, rcx
0x18000b03a  jz      short loc_18000B051
0x18000b03c  mov     qword ptr [rbx+50h], 0
0x18000b044  mov     rax, [rcx]
0x18000b047  mov     rax, [rax+10h]
0x18000b04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b050  nop
0x18000b051  mov     rcx, [rbx+48h]
0x18000b055  test    rcx, rcx
0x18000b058  jz      short loc_18000B06F
0x18000b05a  mov     qword ptr [rbx+48h], 0
0x18000b062  mov     rax, [rcx]
0x18000b065  mov     rax, [rax+10h]
0x18000b069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06e  nop
0x18000b06f  mov     rcx, [rbx+40h]
0x18000b073  test    rcx, rcx
0x18000b076  jz      short loc_18000B08D
0x18000b078  mov     qword ptr [rbx+40h], 0
0x18000b080  mov     rax, [rcx]
0x18000b083  mov     rax, [rax+10h]
0x18000b087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08c  nop
0x18000b08d  mov     rcx, rbx
0x18000b090  add     rsp, 20h
0x18000b094  pop     rbx
0x18000b095  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIProcessLauncherOptions@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::IProcessLauncherOptions,Microsoft::WRL::FtmBase>(void)
```
