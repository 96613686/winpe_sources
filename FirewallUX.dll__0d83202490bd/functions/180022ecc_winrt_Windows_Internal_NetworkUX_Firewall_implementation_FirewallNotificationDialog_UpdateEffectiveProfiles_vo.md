# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_UpdateEffectiveProfiles(void)

- ea: `0x180022ecc`
- end: `0x180022fca`
- name: `?_UpdateEffectiveProfiles@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAXXZ`
- size: `254`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800229a0`

## callees

- `0x1800021c0`
- `0x18001ada4`
- `0x18001b764`
- `0x18001c870`
- `0x18001ccd4`
- `0x180022ecc`
- `0x180027498`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_UpdateEffectiveProfiles(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this)
{
  int v2; // edi
  unsigned int *v3; // rsi
  unsigned int *v4; // r15
  unsigned int v5; // r14d
  char v6[4]; // [rsp+20h] [rbp-58h] BYREF
  int v7[3]; // [rsp+24h] [rbp-54h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int *v9; // [rsp+40h] [rbp-38h] BYREF
  unsigned int *v10; // [rsp+48h] [rbp-30h]
  _DWORD v11[3]; // [rsp+58h] [rbp-20h] BYREF
  char v12; // [rsp+64h] [rbp-14h] BYREF

  if ( *((_BYTE *)this + 525) )
  {
    v2 = *((_DWORD *)this + 126);
    v7[0] = v2;
    v11[0] = 1;
    v11[1] = 2;
    v11[2] = 4;
    v8[0] = v11;
    v8[1] = &v12;
    std::vector<enum winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>::vector<enum winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>(
      &v9,
      v8);
    v3 = v9;
    v4 = v10;
    if ( v9 != v10 )
    {
      do
      {
        v5 = *v3;
        if ( (*v3 & v2) != 0 && !(unsigned __int8)CheckUserPrefMergeForProfileType(v5) )
        {
          v2 &= ~v5;
          *((_DWORD *)this + 151) |= v5;
        }
        ++v3;
      }
      while ( v3 != v4 );
      v7[0] = v2;
    }
    if ( v2 && (v2 & *((_DWORD *)this + 150)) == *((_DWORD *)this + 150) )
    {
      *((_DWORD *)this + 126) = v2;
      FirewallUxTelemetry::DialogInitialize::UpdatedNotificationEffectiveProfiles<enum winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes &>(v7);
    }
    else
    {
      *((_BYTE *)this + 525) = 0;
      v6[0] = 0;
      FirewallUxTelemetry::OverrideShouldConfigureForGroupPolicy<bool>(v6);
    }
    std::vector<enum winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>::~vector<enum winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>(&v9);
  }
}

```

## disassembly

```asm
0x180022ecc  push    rbp
0x180022ece  push    rbx
0x180022ecf  push    rsi
0x180022ed0  push    rdi
0x180022ed1  push    r14
0x180022ed3  push    r15
0x180022ed5  mov     rbp, rsp
0x180022ed8  sub     rsp, 78h
0x180022edc  mov     rax, cs:__security_cookie
0x180022ee3  xor     rax, rsp
0x180022ee6  mov     [rbp+var_10], rax
0x180022eea  mov     rbx, rcx
0x180022eed  cmp     byte ptr [rcx+20Dh], 0
0x180022ef4  jz      loc_180022FB1
0x180022efa  mov     edi, [rcx+1F8h]
0x180022f00  mov     [rbp+var_54], edi
0x180022f03  mov     [rbp+var_20], 1
0x180022f0a  mov     [rbp+var_1C], 2
0x180022f11  mov     [rbp+var_18], 4
0x180022f18  lea     rax, [rbp+var_20]
0x180022f1c  mov     [rbp+var_48], rax
0x180022f20  lea     rax, [rbp+var_14]
0x180022f24  mov     [rbp+var_40], rax
0x180022f28  lea     rdx, [rbp+var_48]
0x180022f2c  lea     rcx, [rbp+var_38]
0x180022f30  call    ??0?$vector@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@V?$allocator@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@std@@@std@@QEAA@V?$initializer_list@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@1@AEBV?$allocator@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@1@@Z; std::vector<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>::vector<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>(std::initializer_list<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>,std::allocator<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes> const &)
0x180022f35  mov     rsi, [rbp+var_38]
0x180022f39  mov     r15, [rbp+var_30]
0x180022f3d  cmp     rsi, r15
0x180022f40  jz      short loc_180022F70
0x180022f42  mov     r14d, [rsi]
0x180022f45  test    edi, r14d
0x180022f48  jz      short loc_180022F64
0x180022f4a  mov     ecx, r14d
0x180022f4d  call    ?CheckUserPrefMergeForProfileType@@YA_NW4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@Z; CheckUserPrefMergeForProfileType(winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes)
0x180022f52  test    al, al
0x180022f54  jnz     short loc_180022F64
0x180022f56  mov     eax, r14d
0x180022f59  not     eax
0x180022f5b  and     edi, eax
0x180022f5d  or      [rbx+25Ch], r14d
0x180022f64  add     rsi, 4
0x180022f68  cmp     rsi, r15
0x180022f6b  jnz     short loc_180022F42
0x180022f6d  mov     [rbp+var_54], edi
0x180022f70  test    edi, edi
0x180022f72  jz      short loc_180022F93
0x180022f74  mov     ecx, [rbx+258h]
0x180022f7a  mov     eax, ecx
0x180022f7c  and     eax, edi
0x180022f7e  cmp     eax, ecx
0x180022f80  jnz     short loc_180022F93
0x180022f82  mov     [rbx+1F8h], edi
0x180022f88  lea     rcx, [rbp+var_54]
0x180022f8c  call    ??$UpdatedNotificationEffectiveProfiles@AEAW4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@DialogInitialize@FirewallUxTelemetry@@SAXAEAW4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@Z; FirewallUxTelemetry::DialogInitialize::UpdatedNotificationEffectiveProfiles<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes &>(winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes &)
0x180022f91  jmp     short loc_180022FA7
0x180022f93  mov     byte ptr [rbx+20Dh], 0
0x180022f9a  mov     [rbp+var_58], 0
0x180022f9e  lea     rcx, [rbp+var_58]
0x180022fa2  call    ??$OverrideShouldConfigureForGroupPolicy@_N@FirewallUxTelemetry@@SAX$$QEA_N@Z; FirewallUxTelemetry::OverrideShouldConfigureForGroupPolicy<bool>(bool &&)
0x180022fa7  lea     rcx, [rbp+var_38]
0x180022fab  call    ??1?$vector@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@V?$allocator@W4FirewallProfileTypes@Firewall@NetworkUX@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>::~vector<winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes>(void)
0x180022fb0  nop
0x180022fb1  mov     rcx, [rbp+var_10]
0x180022fb5  xor     rcx, rsp; StackCookie
0x180022fb8  call    __security_check_cookie
0x180022fbd  add     rsp, 78h
0x180022fc1  pop     r15
0x180022fc3  pop     r14
0x180022fc5  pop     rdi
0x180022fc6  pop     rsi
0x180022fc7  pop     rbx
0x180022fc8  pop     rbp
0x180022fc9  retn
```
