# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetClosedHandler(void)

- ea: `0x18001e940`
- end: `0x18001e9fe`
- name: `?GetClosedHandler@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA?AU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@7@XZ`
- size: `190`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e4`
- `0x18000b5d0`
- `0x18001e940`
- `0x180023264`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetClosedHandler(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *weak; // rax
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  _DWORD *v7; // [rsp+30h] [rbp-10h]
  _QWORD *v8; // [rsp+58h] [rbp+18h] BYREF
  __int64 v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 v10; // [rsp+68h] [rbp+28h] BYREF

  v8 = a2;
  weak = (_QWORD *)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                     a1,
                     &v10);
  v4 = (_QWORD *)*weak;
  *weak = 0;
  v9 = 0;
  v8 = v4;
  v7 = operator new(0x18u);
  v7[2] = 1;
  v5 = v8;
  v8 = 0;
  *((_QWORD *)v7 + 2) = v5;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v7 = off_18002E8E0;
  *a2 = v7;
  if ( v8 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v8);
  if ( v9 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v9);
  if ( v10 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v10);
  return a2;
}

```

## disassembly

```asm
0x18001e940  mov     [rsp-8+arg_0], rbx
0x18001e945  mov     [rsp-8+arg_8], rdx
0x18001e94a  push    rbp
0x18001e94b  mov     rbp, rsp
0x18001e94e  sub     rsp, 40h
0x18001e952  mov     rbx, rdx
0x18001e955  lea     rdx, [rbp+arg_18]
0x18001e959  call    ?get_weak@?$implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@UFirewallDialogBase@234567@@winrt@@QEAA?AU?$weak_ref@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(void)
0x18001e95e  nop
0x18001e95f  mov     rcx, [rax]
0x18001e962  mov     qword ptr [rax], 0
0x18001e969  lea     rax, [rbp+arg_10]
0x18001e96d  mov     [rbp+var_18], rax
0x18001e971  mov     [rbp+arg_10], 0
0x18001e979  mov     [rbp+arg_8], rcx
0x18001e97d  lea     rax, [rbp+arg_8]
0x18001e981  mov     [rbp+var_10], rax
0x18001e985  mov     ecx, 18h; Size
0x18001e98a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e98f  mov     [rbp+var_10], rax
0x18001e993  mov     dword ptr [rax+8], 1
0x18001e99a  mov     rcx, [rbp+arg_8]
0x18001e99e  mov     [rbp+arg_8], 0
0x18001e9a6  mov     [rax+10h], rcx
0x18001e9aa  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001e9b1  lea     rcx, off_18002E8E0
0x18001e9b8  mov     [rax], rcx
0x18001e9bb  mov     [rbx], rax
0x18001e9be  cmp     [rbp+arg_8], 0
0x18001e9c3  jz      short loc_18001E9CF
0x18001e9c5  lea     rcx, [rbp+arg_8]
0x18001e9c9  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e9ce  nop
0x18001e9cf  cmp     [rbp+arg_10], 0
0x18001e9d4  jz      short loc_18001E9E0
0x18001e9d6  lea     rcx, [rbp+arg_10]
0x18001e9da  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e9df  nop
0x18001e9e0  cmp     [rbp+arg_18], 0
0x18001e9e5  jz      short loc_18001E9F0
0x18001e9e7  lea     rcx, [rbp+arg_18]
0x18001e9eb  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e9f0  mov     rax, rbx
0x18001e9f3  mov     rbx, [rsp+40h+arg_0]
0x18001e9f8  add     rsp, 40h
0x18001e9fc  pop     rbp
0x18001e9fd  retn
```
