# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled(void)

- ea: `0x180022de4`
- end: `0x180022ec6`
- name: `?_TryFindAndUpdateAllowCommandEnabled@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAXXZ`
- size: `226`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d568`
- `0x18001f9d4`

## callees

- `0x18000b24c`
- `0x18000b5d0`
- `0x18001aaf0`
- `0x180022de4`
- `0x18002d010`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this,
        __int64 a2)
{
  bool v2; // bl
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  const char *v6; // r9
  __int64 *v7; // rdx
  __int64 v8; // [rsp+0h] [rbp-48h] BYREF
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = (*((_BYTE *)this + 592) || *((_BYTE *)this + 593) || *((_BYTE *)this + 594)) && *((_BYTE *)this + 525) != 0;
  v3 = *((_QWORD *)this + 58);
  if ( v3 )
  {
    v11 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, void *, __int64 *))v3)(
           v3,
           &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>,
           &v11);
    v3 = v11;
  }
  else
  {
    v4 = 0;
    v11 = 0;
  }
  v9 = 0;
  v10 = 0;
  if ( v4 < 0 )
  {
    try
    {
      winrt::throw_hresult((unsigned int)v4, &v9);
    }
    catch ( ... )
    {
      v7 = &v8;
      wil::details::in1diag3::Log_CaughtException(
        (wil::details::in1diag3 *)v7[9],
        (void *)0x249,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\firewallnotificationdialog.cpp",
        v6);
      return;
    }
  }
  v9 = 0;
  v10 = 0;
  LOBYTE(a2) = v2;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 184LL))(v3, a2);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v9);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  LOBYTE(v11) = v2;
  FirewallUxTelemetry::AllowButtonEnabled<bool>(&v11);
}

```

## disassembly

```asm
0x180022de4  push    rbx
0x180022de6  sub     rsp, 40h
0x180022dea  cmp     byte ptr [rcx+250h], 0
0x180022df1  jnz     short loc_180022E09
0x180022df3  cmp     byte ptr [rcx+251h], 0
0x180022dfa  jnz     short loc_180022E09
0x180022dfc  cmp     byte ptr [rcx+252h], 0
0x180022e03  jnz     short loc_180022E09
0x180022e05  xor     bl, bl
0x180022e07  jmp     short loc_180022E16
0x180022e09  mov     al, [rcx+20Dh]
0x180022e0f  neg     al
0x180022e11  sbb     bl, bl
0x180022e13  and     bl, 1
0x180022e16  mov     rcx, [rcx+1D0h]
0x180022e1d  test    rcx, rcx
0x180022e20  jnz     short loc_180022E2B
0x180022e22  xor     eax, eax
0x180022e24  mov     [rsp+48h+arg_0], rax
0x180022e29  jmp     short loc_180022E55
0x180022e2b  mov     [rsp+48h+arg_0], 0
0x180022e34  mov     rax, [rcx]
0x180022e37  lea     r8, [rsp+48h+arg_0]
0x180022e3c  lea     rdx, ??$guid_v@UIControl@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IControl>
0x180022e43  mov     rax, [rax]
0x180022e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e4b  mov     rcx, [rsp+48h+arg_0]
0x180022e50  mov     [rsp+48h+arg_0], rcx
0x180022e55  mov     [rsp+48h+var_28], 0
0x180022e5d  xorps   xmm0, xmm0
0x180022e60  movdqu  [rsp+48h+var_20], xmm0
0x180022e66  test    eax, eax
0x180022e68  js      short loc_180022EAC
0x180022e6a  mov     [rsp+48h+var_28], 0
0x180022e72  movdqu  [rsp+48h+var_20], xmm0
0x180022e78  mov     rax, [rcx]
0x180022e7b  mov     dl, bl
0x180022e7d  mov     rax, [rax+0B8h]
0x180022e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e89  test    eax, eax
0x180022e8b  js      short loc_180022EB8
0x180022e8d  lea     rcx, [rsp+48h+arg_0]
0x180022e92  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180022e97  mov     byte ptr [rsp+48h+arg_0], bl
0x180022e9b  lea     rcx, [rsp+48h+arg_0]
0x180022ea0  call    ??$AllowButtonEnabled@_N@FirewallUxTelemetry@@SAX$$QEA_N@Z; FirewallUxTelemetry::AllowButtonEnabled<bool>(bool &&)
0x180022ea5  nop
0x180022ea6  add     rsp, 40h
0x180022eaa  pop     rbx
0x180022eab  retn
0x180022eac  lea     rdx, [rsp+48h+var_28]
0x180022eb1  mov     ecx, eax
0x180022eb3  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180022eb8  lea     rdx, [rsp+48h+var_28]
0x180022ebd  mov     ecx, eax
0x180022ebf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
