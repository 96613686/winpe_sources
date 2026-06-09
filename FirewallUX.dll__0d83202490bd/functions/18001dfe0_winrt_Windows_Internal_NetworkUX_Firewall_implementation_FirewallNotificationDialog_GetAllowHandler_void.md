# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetAllowHandler(void)

- ea: `0x18001dfe0`
- end: `0x18001e0a9`
- name: `?GetAllowHandler@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA?AV?$optional@U?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@winrt@@@std@@XZ`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e4`
- `0x18000b5d0`
- `0x18001dfe0`
- `0x180023264`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetAllowHandler(
        __int64 a1,
        __int64 a2)
{
  __int64 *weak; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  _DWORD *v7; // [rsp+38h] [rbp-8h]
  __int64 v8; // [rsp+58h] [rbp+18h] BYREF
  __int64 v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 v10; // [rsp+68h] [rbp+28h] BYREF

  v8 = a2;
  weak = (__int64 *)winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(
                      a1,
                      &v10);
  v4 = *weak;
  *weak = 0;
  v9 = 0;
  v8 = v4;
  v7 = operator new(0x18u);
  v7[2] = 1;
  v5 = v8;
  v8 = 0;
  *((_QWORD *)v7 + 2) = v5;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v7 = off_18002E8C0;
  *(_QWORD *)a2 = v7;
  if ( v8 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v8);
  if ( v9 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v9);
  *(_BYTE *)(a2 + 8) = 1;
  if ( v10 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v10);
  return a2;
}

```

## disassembly

```asm
0x18001dfe0  mov     [rsp-8+arg_0], rbx
0x18001dfe5  mov     [rsp-8+arg_8], rdx
0x18001dfea  push    rbp
0x18001dfeb  mov     rbp, rsp
0x18001dfee  sub     rsp, 40h
0x18001dff2  mov     rbx, rdx
0x18001dff5  lea     rdx, [rbp+arg_18]
0x18001dff9  call    ?get_weak@?$implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@UFirewallDialogBase@234567@@winrt@@QEAA?AU?$weak_ref@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase>::get_weak(void)
0x18001dffe  nop
0x18001dfff  mov     rcx, [rax]
0x18001e002  mov     qword ptr [rax], 0
0x18001e009  mov     [rbp+var_18], 0
0x18001e011  lea     rax, [rbp+arg_10]
0x18001e015  mov     [rbp+var_10], rax
0x18001e019  mov     [rbp+arg_10], 0
0x18001e021  mov     [rbp+arg_8], rcx
0x18001e025  lea     rax, [rbp+arg_8]
0x18001e029  mov     [rbp+var_8], rax
0x18001e02d  mov     ecx, 18h; Size
0x18001e032  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e037  mov     [rbp+var_8], rax
0x18001e03b  mov     dword ptr [rax+8], 1
0x18001e042  mov     rcx, [rbp+arg_8]
0x18001e046  mov     [rbp+arg_8], 0
0x18001e04e  mov     [rax+10h], rcx
0x18001e052  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001e059  lea     rcx, off_18002E8C0
0x18001e060  mov     [rax], rcx
0x18001e063  mov     [rbx], rax
0x18001e066  cmp     [rbp+arg_8], 0
0x18001e06b  jz      short loc_18001E077
0x18001e06d  lea     rcx, [rbp+arg_8]
0x18001e071  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e076  nop
0x18001e077  cmp     [rbp+arg_10], 0
0x18001e07c  jz      short loc_18001E087
0x18001e07e  lea     rcx, [rbp+arg_10]
0x18001e082  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e087  mov     byte ptr [rbx+8], 1
0x18001e08b  cmp     [rbp+arg_18], 0
0x18001e090  jz      short loc_18001E09B
0x18001e092  lea     rcx, [rbp+arg_18]
0x18001e096  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001e09b  mov     rax, rbx
0x18001e09e  mov     rbx, [rsp+40h+arg_0]
0x18001e0a3  add     rsp, 40h
0x18001e0a7  pop     rbp
0x18001e0a8  retn
```
