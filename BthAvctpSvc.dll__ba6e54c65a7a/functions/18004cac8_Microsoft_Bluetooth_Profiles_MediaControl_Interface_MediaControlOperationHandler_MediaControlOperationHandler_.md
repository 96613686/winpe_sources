# Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::~MediaControlOperationHandler(void)

- ea: `0x18004cac8`
- end: `0x18004cbe1`
- name: `??1MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@UEAA@XZ`
- size: `281`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d620`

## callees

- `0x18000d0c0`
- `0x1800235bc`
- `0x18002cf50`
- `0x18004cac8`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cb49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cb49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::~MediaControlOperationHandler(
        Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *this)
{
  PVOID *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rcx

  *(_QWORD *)this = &Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler'};
  *((_QWORD *)this + 1) = &Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `IBthAvMediaEventHandler'};
  *((_QWORD *)this + 3) = &Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f26752851b2d3f90d31187047271b4d2_Traceguids, this);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 13) )
  {
    WindowsDeleteString(*((HSTRING *)this + 13));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *((_QWORD *)this + 9);
  if ( v3 && *((_QWORD *)this + 12) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 104LL))(*((_QWORD *)this + 9));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_q(v2[2], 12, &WPP_f26752851b2d3f90d31187047271b4d2_Traceguids, this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18004cac8  mov     [rsp+arg_0], rbx
0x18004cacd  push    rdi
0x18004cace  sub     rsp, 20h
0x18004cad2  mov     rbx, rcx
0x18004cad5  lea     rax, ??_7MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@6BIMediaControlOperationHandler@12345@@; const Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler'}
0x18004cadc  mov     [rcx], rax
0x18004cadf  lea     rax, ??_7MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIBthAvMediaEventHandler@@VFtmBase@23@@Details@WRL@5@@; const Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>'}
0x18004cae6  mov     [rcx+8], rax
0x18004caea  lea     rax, ??_7MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@6BIBthAvMediaEventHandler@@@; const Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `IBthAvMediaEventHandler'}
0x18004caf1  mov     [rcx+10h], rax
0x18004caf5  lea     rax, ??_7MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@5@@; const Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004cafc  mov     [rcx+18h], rax
0x18004cb00  lea     rdi, WPP_GLOBAL_Control
0x18004cb07  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb0e  cmp     rcx, rdi
0x18004cb11  jz      short loc_18004CB3E
0x18004cb13  test    byte ptr [rcx+1Ch], 1
0x18004cb17  jz      short loc_18004CB3E
0x18004cb19  cmp     byte ptr [rcx+19h], 5
0x18004cb1d  jb      short loc_18004CB3E
0x18004cb1f  mov     edx, 0Bh
0x18004cb24  mov     r9, rbx
0x18004cb27  lea     r8, WPP_f26752851b2d3f90d31187047271b4d2_Traceguids
0x18004cb2e  mov     rcx, [rcx+10h]
0x18004cb32  call    WPP_SF_q
0x18004cb37  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb3e  cmp     qword ptr [rbx+68h], 0
0x18004cb43  jz      short loc_18004CB56
0x18004cb45  mov     rcx, [rbx+68h]; string
0x18004cb49  call    cs:__imp_WindowsDeleteString
0x18004cb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb56  mov     r8, [rbx+48h]
0x18004cb5a  test    r8, r8
0x18004cb5d  jz      short loc_18004CB7E
0x18004cb5f  mov     rdx, [rbx+60h]
0x18004cb63  test    rdx, rdx
0x18004cb66  jz      short loc_18004CB7E
0x18004cb68  mov     rax, [r8]
0x18004cb6b  mov     rcx, r8
0x18004cb6e  mov     rax, [rax+68h]
0x18004cb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb77  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb7e  cmp     rcx, rdi
0x18004cb81  jz      short loc_18004CBA7
0x18004cb83  test    byte ptr [rcx+1Ch], 1
0x18004cb87  jz      short loc_18004CBA7
0x18004cb89  cmp     byte ptr [rcx+19h], 5
0x18004cb8d  jb      short loc_18004CBA7
0x18004cb8f  mov     edx, 0Ch
0x18004cb94  mov     r9, rbx
0x18004cb97  lea     r8, WPP_f26752851b2d3f90d31187047271b4d2_Traceguids
0x18004cb9e  mov     rcx, [rcx+10h]
0x18004cba2  call    WPP_SF_q
0x18004cba7  lea     rcx, [rbx+50h]
0x18004cbab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cbb0  nop
0x18004cbb1  mov     rcx, [rbx+48h]
0x18004cbb5  test    rcx, rcx
0x18004cbb8  jz      short loc_18004CBCF
0x18004cbba  mov     qword ptr [rbx+48h], 0
0x18004cbc2  mov     rax, [rcx]
0x18004cbc5  mov     rax, [rax+10h]
0x18004cbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbce  nop
0x18004cbcf  mov     rcx, rbx
0x18004cbd2  mov     rbx, [rsp+28h+arg_0]
0x18004cbd7  add     rsp, 20h
0x18004cbdb  pop     rdi
0x18004cbdc  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIMediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@3@UIBthAvMediaEventHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>(void)
```
