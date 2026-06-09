# Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::~A2dpSinkPlaybackConnection(void)

- ea: `0x180024680`
- end: `0x180024741`
- name: `??1A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@EEAA@XZ`
- size: `193`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800248a0`

## callees

- `0x18000b3d4`
- `0x18000de78`
- `0x1800235bc`
- `0x180024634`
- `0x180024680`
- `0x1800249e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024721`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::~A2dpSinkPlaybackConnection(
        Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection'};
  *((_QWORD *)this + 1) = &Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IWeakReferenceSource,Windows::Foundation::IClosable,IFastRundown>'};
  *((_QWORD *)this + 2) = &Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Windows::Foundation::IClosable'};
  *((_QWORD *)this + 3) = &Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IFastRundown>'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_46c7da31cc553b94876790d5786b6424_Traceguids, this);
  }
  Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::Close((Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection *)((char *)this + 16));
  std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>((char *)this + 88);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>(this);
}

```

## disassembly

```asm
0x180024680  mov     [rsp+arg_0], rbx
0x180024685  push    rdi
0x180024686  sub     rsp, 20h
0x18002468a  lea     rax, ??_7A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@6BIA2dpSinkPlaybackConnection@12345@@; const Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection'}
0x180024691  mov     rbx, rcx
0x180024694  mov     [rcx], rax
0x180024697  lea     rax, ??_7A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@UIFastRundown@@@Details@WRL@5@@; const Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IWeakReferenceSource,Windows::Foundation::IClosable,IFastRundown>'}
0x18002469e  mov     [rcx+8], rax
0x1800246a2  lea     rax, ??_7A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@6BIClosable@Foundation@Windows@@@; const Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Windows::Foundation::IClosable'}
0x1800246a9  mov     [rcx+10h], rax
0x1800246ad  lea     rax, ??_7A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIFastRundown@@@Details@WRL@5@@; const Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IFastRundown>'}
0x1800246b4  mov     [rcx+18h], rax
0x1800246b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246bf  lea     rax, WPP_GLOBAL_Control
0x1800246c6  cmp     rcx, rax
0x1800246c9  jz      short loc_1800246EF
0x1800246cb  test    byte ptr [rcx+1Ch], 1
0x1800246cf  jz      short loc_1800246EF
0x1800246d1  cmp     byte ptr [rcx+19h], 4
0x1800246d5  jb      short loc_1800246EF
0x1800246d7  mov     rcx, [rcx+10h]
0x1800246db  lea     r8, WPP_46c7da31cc553b94876790d5786b6424_Traceguids
0x1800246e2  mov     edx, 0Fh
0x1800246e7  mov     r9, rbx
0x1800246ea  call    WPP_SF_q
0x1800246ef  lea     rcx, [rbx+10h]; this
0x1800246f3  call    ?Close@A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@UEAAJXZ; Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::Close(void)
0x1800246f8  lea     rcx, [rbx+58h]
0x1800246fc  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x180024701  mov     rcx, [rbx+50h]; this
0x180024705  test    rcx, rcx
0x180024708  jz      short loc_18002470F
0x18002470a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002470f  mov     rcx, [rbx+40h]; this
0x180024713  test    rcx, rcx
0x180024716  jz      short loc_18002471D
0x180024718  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002471d  mov     rcx, [rbx+30h]; string
0x180024721  call    cs:__imp_WindowsDeleteString
0x180024727  mov     rcx, rbx
0x18002472a  mov     qword ptr [rbx+30h], 0
0x180024732  mov     rbx, [rsp+28h+arg_0]
0x180024737  add     rsp, 20h
0x18002473b  pop     rdi
0x18002473c  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UIA2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@3@UIClosable@Foundation@Windows@@UIFastRundown@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,Microsoft::Bluetooth::Profiles::A2dp::Private::IA2dpSinkPlaybackConnection,Windows::Foundation::IClosable,IFastRundown>(void)
```
