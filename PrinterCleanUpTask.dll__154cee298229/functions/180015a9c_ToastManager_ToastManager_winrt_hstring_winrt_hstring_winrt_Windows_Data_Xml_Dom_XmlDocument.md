# ToastManager::ToastManager(winrt::hstring,winrt::hstring,winrt::Windows::Data::Xml::Dom::XmlDocument)

- ea: `0x180015a9c`
- end: `0x180015b5a`
- name: `??0ToastManager@@QEAA@Uhstring@winrt@@0UXmlDocument@Dom@Xml@Data@Windows@2@@Z`
- size: `190`
- prototype: `__int64 *__fastcall(__int64 *, _QWORD *, _QWORD *, const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d424`
- `0x180012f8c`

## callees

- `0x180007118`
- `0x18000750c`
- `0x18000a360`
- `0x180011464`
- `0x180012bf0`
- `0x180014638`
- `0x180015a9c`

## pseudocode

```c
__int64 *__fastcall ToastManager::ToastManager(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        const struct winrt::Windows::Data::Xml::Dom::XmlDocument *a4)
{
  __int64 *v8; // rdi
  __int64 v9; // rcx
  _BYTE v11[8]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v12[10]; // [rsp+28h] [rbp-50h] BYREF

  *a1 = 0;
  v8 = (__int64 *)winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
                    (winrt::Windows::UI::Notifications::ToastNotification *)v11,
                    a4);
  if ( a1 != v8 )
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
    v9 = *v8;
    *v8 = 0;
    *a1 = v9;
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v11);
  v12[0] = *a2;
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification2<winrt::Windows::UI::Notifications::ToastNotification>::Tag(
    a1,
    v12);
  v12[0] = *a3;
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification2<winrt::Windows::UI::Notifications::ToastNotification>::Group(
    a1,
    v12);
  winrt::handle_type<winrt::impl::hstring_traits>::close(a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(a3);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(a4);
  return a1;
}

```

## disassembly

```asm
0x180015a9c  mov     rax, rsp
0x180015a9f  mov     [rax+20h], r9
0x180015aa3  mov     [rax+18h], r8
0x180015aa7  mov     [rax+10h], rdx
0x180015aab  mov     [rax+8], rcx
0x180015aaf  push    rbx
0x180015ab0  push    rsi
0x180015ab1  push    rdi
0x180015ab2  push    r14
0x180015ab4  push    r15
0x180015ab6  sub     rsp, 50h
0x180015aba  mov     rsi, r9
0x180015abd  mov     r14, r8
0x180015ac0  mov     r15, rdx
0x180015ac3  mov     rbx, rcx
0x180015ac6  mov     qword ptr [rcx], 0
0x180015acd  mov     rdx, r9; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x180015ad0  lea     rcx, [rax-58h]; this
0x180015ad4  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x180015ad9  mov     rdi, rax
0x180015adc  cmp     rbx, rax
0x180015adf  jz      short loc_180015AFC
0x180015ae1  cmp     qword ptr [rbx], 0
0x180015ae5  jz      short loc_180015AEF
0x180015ae7  mov     rcx, rbx
0x180015aea  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015aef  mov     rcx, [rdi]
0x180015af2  mov     qword ptr [rdi], 0
0x180015af9  mov     [rbx], rcx
0x180015afc  lea     rcx, [rsp+78h+var_58]; this
0x180015b01  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015b06  mov     rax, [r15]
0x180015b09  mov     [rsp+78h+var_50], rax
0x180015b0e  lea     rdx, [rsp+78h+var_50]
0x180015b13  mov     rcx, rbx
0x180015b16  call    ?Tag@?$consume_Windows_UI_Notifications_IToastNotification2@UToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification2<winrt::Windows::UI::Notifications::ToastNotification>::Tag(winrt::param::hstring const &)
0x180015b1b  mov     rax, [r14]
0x180015b1e  mov     [rsp+78h+var_50], rax
0x180015b23  lea     rdx, [rsp+78h+var_50]
0x180015b28  mov     rcx, rbx
0x180015b2b  call    ?Group@?$consume_Windows_UI_Notifications_IToastNotification2@UToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification2<winrt::Windows::UI::Notifications::ToastNotification>::Group(winrt::param::hstring const &)
0x180015b30  nop
0x180015b31  mov     rcx, r15
0x180015b34  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180015b39  nop
0x180015b3a  mov     rcx, r14
0x180015b3d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180015b42  nop
0x180015b43  mov     rcx, rsi; this
0x180015b46  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015b4b  mov     rax, rbx
0x180015b4e  add     rsp, 50h
0x180015b52  pop     r15
0x180015b54  pop     r14
0x180015b56  pop     rdi
0x180015b57  pop     rsi
0x180015b58  pop     rbx
0x180015b59  retn
```
