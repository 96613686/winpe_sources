# winrt::impl::variadic_delegate__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetAllowHandler_::_2_::_lambda_1__void_IPopupWindow___IPopupCommand___::invoke

- ea: `0x180023310`
- end: `0x1800233d1`
- name: `winrt::impl::variadic_delegate__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetAllowHandler_::_2_::_lambda_1__void_IPopupWindow___IPopupCommand___::invoke`
- size: `193`
- prototype: `void __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e4`
- `0x18000b5d0`
- `0x18001cdc0`
- `0x180023310`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::variadic_delegate__winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetAllowHandler_::_2_::_lambda_1__void_IPopupWindow___IPopupCommand___::invoke(
        __int64 a1,
        void (__fastcall **a2)(char *a1),
        void (__fastcall **a3)(char *a1))
{
  void (__fastcall *v3)(char *); // rsi
  void (__fastcall *v4)(char *); // rbp
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdi
  void (__fastcall **v8)(char *); // rax
  __int64 v9[9]; // [rsp+20h] [rbp-48h] BYREF

  v3 = *a3;
  v4 = *a2;
  v5 = *(_QWORD *)(a1 + 16);
  v9[0] = 0;
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v5 + 24LL))(
      v5,
      &winrt::impl::guid_v<winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>,
      v9);
    if ( v9[0] )
    {
      v6 = v9[0] - 448;
      v7 = v9[0] - 448;
    }
    else
    {
      v6 = 0;
      v7 = 0;
    }
    v9[0] = v6;
  }
  else
  {
    v6 = 0;
    v7 = 0;
  }
  if ( v6 )
  {
    v8 = (void (__fastcall **)(char *))operator new(0x310u);
    v9[1] = (__int64)v8;
    v8[95] = (void (__fastcall *)(char *))v6;
    v8[96] = v4;
    v8[97] = v3;
    *v8 = winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::AllowHandler__ResumeCoro_1;
    *((_DWORD *)v8 + 2) = 65538;
    *((_BYTE *)v8 + 752) = 0;
    winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::AllowHandler__ResumeCoro_1((char *)v8);
  }
  if ( v7 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v9);
}

```

## disassembly

```asm
0x180023310  push    rbx
0x180023312  push    rbp
0x180023313  push    rsi
0x180023314  push    rdi
0x180023315  sub     rsp, 48h
0x180023319  mov     rsi, [r8]
0x18002331c  mov     rbp, [rdx]
0x18002331f  mov     rcx, [rcx+10h]
0x180023323  mov     [rsp+68h+var_48], 0
0x18002332c  test    rcx, rcx
0x18002332f  jnz     short loc_180023337
0x180023331  xor     ebx, ebx
0x180023333  xor     edi, edi
0x180023335  jmp     short loc_18002336E
0x180023337  mov     rax, [rcx]
0x18002333a  lea     r8, [rsp+68h+var_48]
0x18002333f  lea     rdx, ??$guid_v@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>
0x180023346  mov     rax, [rax+18h]
0x18002334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002334f  mov     rax, [rsp+68h+var_48]
0x180023354  test    rax, rax
0x180023357  jnz     short loc_18002335F
0x180023359  xor     ebx, ebx
0x18002335b  xor     edi, edi
0x18002335d  jmp     short loc_180023369
0x18002335f  lea     rbx, [rax-1C0h]
0x180023366  mov     rdi, rbx
0x180023369  mov     [rsp+68h+var_48], rbx
0x18002336e  test    rbx, rbx
0x180023371  jz      short loc_1800233B9
0x180023373  mov     ecx, 310h; Size
0x180023378  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002337d  mov     [rsp+68h+var_40], rax
0x180023382  mov     [rax+2F8h], rbx
0x180023389  mov     [rax+300h], rbp
0x180023390  mov     [rax+308h], rsi
0x180023397  lea     rcx, winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallNotificationDialog__AllowHandler$_ResumeCoro$1
0x18002339e  mov     [rax], rcx
0x1800233a1  mov     dword ptr [rax+8], 10002h
0x1800233a8  xor     ecx, ecx
0x1800233aa  mov     [rax+2F0h], cl
0x1800233b0  mov     rcx, rax; void *
0x1800233b3  call    winrt__Windows__Internal__NetworkUX__Firewall__implementation__FirewallNotificationDialog__AllowHandler$_ResumeCoro$1
0x1800233b8  nop
0x1800233b9  test    rdi, rdi
0x1800233bc  jz      short loc_1800233C8
0x1800233be  lea     rcx, [rsp+68h+var_48]
0x1800233c3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800233c8  add     rsp, 48h
0x1800233cc  pop     rdi
0x1800233cd  pop     rsi
0x1800233ce  pop     rbp
0x1800233cf  pop     rbx
0x1800233d0  retn
```
