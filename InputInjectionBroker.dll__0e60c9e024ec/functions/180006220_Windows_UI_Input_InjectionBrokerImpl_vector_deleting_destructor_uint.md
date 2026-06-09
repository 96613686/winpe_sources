# Windows::UI::Input::InjectionBrokerImpl::`vector deleting destructor'(uint)

- ea: `0x180006220`
- end: `0x180006270`
- name: `??_EInjectionBrokerImpl@Input@UI@Windows@@MEAAPEAXI@Z`
- size: `80`
- prototype: `Windows::UI::Input::InjectionBrokerImpl *__fastcall(Windows::UI::Input::InjectionBrokerImpl *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006168`
- `0x180006220`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000625c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000625c`

## pseudocode

```c
Windows::UI::Input::InjectionBrokerImpl *__fastcall Windows::UI::Input::InjectionBrokerImpl::`vector deleting destructor'(
        Windows::UI::Input::InjectionBrokerImpl *this,
        char a2)
{
  *(_QWORD *)this = &Windows::UI::Input::InjectionBrokerImpl::`vftable';
  *((_QWORD *)this + 1) = &Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>((__int64)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006220  mov     [rsp+arg_0], rbx
0x180006225  push    rdi
0x180006226  sub     rsp, 20h
0x18000622a  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6B@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'
0x180006231  mov     ebx, edx
0x180006233  mov     [rcx], rax
0x180006236  mov     rdi, rcx
0x180006239  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6BIWeakReferenceSource@@@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `IWeakReferenceSource'}
0x180006240  mov     [rcx+8], rax
0x180006244  lea     rax, ??_7InjectionBrokerImpl@Input@UI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::UI::Input::InjectionBrokerImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000624b  mov     [rcx+10h], rax
0x18000624f  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>(void)
0x180006254  test    bl, 1
0x180006257  jz      short loc_180006262
0x180006259  mov     rcx, rdi
0x18000625c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006262  mov     rbx, [rsp+28h+arg_0]
0x180006267  mov     rax, rdi
0x18000626a  add     rsp, 20h
0x18000626e  pop     rdi
0x18000626f  retn
```
