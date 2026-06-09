# CAccountsSettingsPaneCommandsRequestedEventArgs::~CAccountsSettingsPaneCommandsRequestedEventArgs(void)

- ea: `0x1800369e8`
- end: `0x180036aa9`
- name: `??1CAccountsSettingsPaneCommandsRequestedEventArgs@@UEAA@XZ`
- size: `193`
- prototype: `void __fastcall(CAccountsSettingsPaneCommandsRequestedEventArgs *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025530`

## callees

- `0x180011ffc`
- `0x180024198`
- `0x18002b130`
- `0x1800369e8`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036a29`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036a29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036a89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAccountsSettingsPaneCommandsRequestedEventArgs::~CAccountsSettingsPaneCommandsRequestedEventArgs(
        CAccountsSettingsPaneCommandsRequestedEventArgs *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs'};
  *((_QWORD *)this + 1) = &CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>'};
  *((_QWORD *)this + 2) = &CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs2'};
  *((_QWORD *)this + 3) = &CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<INoMarshal>>'};
  v2 = (void *)*((_QWORD *)this + 13);
  if ( v2 )
    SetEvent(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 120);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release((char *)this + 104);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 88);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::ICredentialCommand,Microsoft::WRL::CloakedIid<ICredentialHelper>,Microsoft::WRL::CloakedIid<INoMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::ICredentialCommand,Microsoft::WRL::CloakedIid<ICredentialHelper>,Microsoft::WRL::CloakedIid<INoMarshal>>(this);
}

```

## disassembly

```asm
0x1800369e8  mov     [rsp+arg_0], rbx
0x1800369ed  push    rdi
0x1800369ee  sub     rsp, 20h
0x1800369f2  mov     rbx, rcx
0x1800369f5  lea     rax, ??_7CAccountsSettingsPaneCommandsRequestedEventArgs@@6BIAccountsSettingsPaneCommandsRequestedEventArgs@ApplicationSettings@UI@Windows@@@; const CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs'}
0x1800369fc  mov     [rcx], rax
0x1800369ff  lea     rax, ??_7CAccountsSettingsPaneCommandsRequestedEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAccountsSettingsPaneCommandsRequestedEventArgs2@ApplicationSettings@UI@Windows@@U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@@; const CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs2,Microsoft::WRL::CloakedIid<INoMarshal>>'}
0x180036a06  mov     [rcx+8], rax
0x180036a0a  lea     rax, ??_7CAccountsSettingsPaneCommandsRequestedEventArgs@@6BIAccountsSettingsPaneCommandsRequestedEventArgs2@ApplicationSettings@UI@Windows@@@; const CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Windows::UI::ApplicationSettings::IAccountsSettingsPaneCommandsRequestedEventArgs2'}
0x180036a11  mov     [rcx+10h], rax
0x180036a15  lea     rax, ??_7CAccountsSettingsPaneCommandsRequestedEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@@; const CAccountsSettingsPaneCommandsRequestedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<INoMarshal>>'}
0x180036a1c  mov     [rcx+18h], rax
0x180036a20  mov     rcx, [rcx+68h]; hEvent
0x180036a24  test    rcx, rcx
0x180036a27  jz      short loc_180036A2F
0x180036a29  call    cs:__imp_SetEvent
0x180036a2f  lea     rcx, [rbx+78h]
0x180036a33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036a38  nop
0x180036a39  mov     rcx, [rbx+70h]
0x180036a3d  test    rcx, rcx
0x180036a40  jz      short loc_180036A57
0x180036a42  mov     qword ptr [rbx+70h], 0
0x180036a4a  mov     rax, [rcx]
0x180036a4d  mov     rax, [rax+10h]
0x180036a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a56  nop
0x180036a57  lea     rcx, [rbx+68h]
0x180036a5b  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180036a60  nop
0x180036a61  lea     rcx, [rbx+58h]
0x180036a65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036a6a  lea     rcx, [rbx+50h]
0x180036a6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036a73  lea     rcx, [rbx+48h]
0x180036a77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036a7c  lea     rcx, [rbx+40h]
0x180036a80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180036a85  mov     rcx, [rbx+38h]; string
0x180036a89  call    cs:__imp_WindowsDeleteString
0x180036a8f  mov     qword ptr [rbx+38h], 0
0x180036a97  mov     rcx, rbx
0x180036a9a  mov     rbx, [rsp+28h+arg_0]
0x180036a9f  add     rsp, 20h
0x180036aa3  pop     rdi
0x180036aa4  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICredentialCommand@ApplicationSettings@UI@Windows@@U?$CloakedIid@UICredentialHelper@@@23@U?$CloakedIid@UINoMarshal@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::ICredentialCommand,Microsoft::WRL::CloakedIid<ICredentialHelper>,Microsoft::WRL::CloakedIid<INoMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::ApplicationSettings::ICredentialCommand,Microsoft::WRL::CloakedIid<ICredentialHelper>,Microsoft::WRL::CloakedIid<INoMarshal>>(void)
```
