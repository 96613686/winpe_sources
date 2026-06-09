# std::thread::_Invoke_std::tuple__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog_::_2_::_lambda_1____0_

- ea: `0x18001ba40`
- end: `0x18001bab0`
- name: `std::thread::_Invoke_std::tuple__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog_::_2_::_lambda_1____0_`
- size: `112`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800021e4`
- `0x1800025f8`
- `0x18000b5d0`
- `0x18001ba40`
- `0x1800229a0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001ba82`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18001ba82`

## pseudocode

```c
__int64 __fastcall std::thread::_Invoke_std::tuple__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ShowDialog_::_2_::_lambda_1____0_(
        __int64 *a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax

  v2 = *a1;
  v3 = operator new(0x140u);
  v3[39] = v2;
  *v3 = winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_ShowDialogInternal__ResumeCoro_1;
  *((_DWORD *)v3 + 2) = 65538;
  *((_BYTE *)v3 + 304) = 0;
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_ShowDialogInternal__ResumeCoro_1(v3);
  _Cnd_do_broadcast_at_thread_exit();
  if ( *a1 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1);
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x18001ba40  mov     [rsp+arg_0], rbx
0x18001ba45  push    rdi
0x18001ba46  sub     rsp, 20h
0x18001ba4a  mov     rdi, rcx
0x18001ba4d  mov     rbx, [rcx]
0x18001ba50  mov     ecx, 140h; Size
0x18001ba55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba5a  mov     [rax+138h], rbx
0x18001ba61  lea     rcx, winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallNotificationDialog___ShowDialogInternal$_ResumeCoro$1
0x18001ba68  mov     [rax], rcx
0x18001ba6b  mov     dword ptr [rax+8], 10002h
0x18001ba72  xor     ecx, ecx
0x18001ba74  mov     [rax+130h], cl
0x18001ba7a  mov     rcx, rax; void *
0x18001ba7d  call    winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallNotificationDialog___ShowDialogInternal$_ResumeCoro$1
0x18001ba82  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x18001ba88  cmp     qword ptr [rdi], 0
0x18001ba8c  jz      short loc_18001BA96
0x18001ba8e  mov     rcx, rdi
0x18001ba91  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001ba96  mov     edx, 8; unsigned __int64
0x18001ba9b  mov     rcx, rdi; void *
0x18001ba9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001baa3  xor     eax, eax
0x18001baa5  mov     rbx, [rsp+28h+arg_0]
0x18001baaa  add     rsp, 20h
0x18001baae  pop     rdi
0x18001baaf  retn
```
