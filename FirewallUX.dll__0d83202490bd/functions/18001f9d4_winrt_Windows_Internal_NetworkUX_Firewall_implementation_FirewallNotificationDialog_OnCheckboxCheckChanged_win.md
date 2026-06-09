# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::OnCheckboxCheckChanged(winrt::Windows::Internal::NetworkUX::Firewall::FirewallProfileTypes,bool)

- ea: `0x18001f9d4`
- end: `0x18001fabb`
- name: `?OnCheckboxCheckChanged@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXW4FirewallProfileTypes@34567@_N@Z`
- size: `231`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ec90`
- `0x18001ed10`
- `0x18001ed80`
- `0x18001ee00`
- `0x18001ee70`
- `0x18001eef0`

## callees

- `0x180010430`
- `0x18001aca4`
- `0x18001af58`
- `0x18001b08c`
- `0x18001f53c`
- `0x18001f9d4`
- `0x180022de4`
- `0x180029734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa26`

## string_xrefs

- `0x18001faa9`: `shellcommon\shell\networkux\firewallux\lib\Utils.h`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::OnCheckboxCheckChanged(
        __int64 a1,
        unsigned int a2,
        bool a3)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  const char *v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v12; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+44h] [rbp+Ch]
  bool v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = a3;
  if ( *(_DWORD *)(a1 + 80) )
  {
    if ( *(_DWORD *)(a1 + 80) != 1 )
      wil::details::in1diag3::FailFast_UnexpectedMsg(
        retaddr,
        (void *)0x3B,
        (unsigned int)"shellcommon\\shell\\networkux\\firewallux\\lib\\Utils.h",
        "Unexpected dialog type",
        v10);
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  v12 = 16;
  v13 = v6;
  NetworkingTriageScenario::FirewallUX::NotificationDialogCheckboxChanged(
    (const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v12,
    a2,
    a3);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 552));
  switch ( a2 )
  {
    case 4u:
      *(_BYTE *)(a1 + 592) = a3;
      FirewallUxTelemetry::PublicNetworksCheckboxToggled<bool &>(&v14);
LABEL_11:
      winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled(
        (winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *)a1,
        v9);
      goto LABEL_13;
    case 2u:
      *(_BYTE *)(a1 + 593) = a3;
      FirewallUxTelemetry::PrivateNetworksCheckboxToggled<bool &>(&v14);
      goto LABEL_11;
    case 1u:
      *(_BYTE *)(a1 + 594) = a3;
      FirewallUxTelemetry::DomainNetworksCheckboxToggled<bool &>(&v14);
      goto LABEL_11;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
LABEL_13:
  if ( a1 != -552 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 552));
}

```

## disassembly

```asm
0x18001f9d4  mov     [rsp+arg_8], rbx
0x18001f9d9  mov     [rsp+arg_10], r8b
0x18001f9de  push    rbp
0x18001f9df  push    rsi
0x18001f9e0  push    rdi; char *
0x18001f9e1  sub     rsp, 20h
0x18001f9e5  mov     sil, r8b
0x18001f9e8  mov     ebp, edx
0x18001f9ea  mov     rdi, rcx
0x18001f9ed  cmp     dword ptr [rcx+50h], 0
0x18001f9f1  jnz     short loc_18001F9F7
0x18001f9f3  xor     eax, eax
0x18001f9f5  jmp     short loc_18001FA06
0x18001f9f7  cmp     dword ptr [rcx+50h], 1
0x18001f9fb  jnz     loc_18001FA9D
0x18001fa01  mov     eax, 1
0x18001fa06  mov     [rsp+38h+arg_0], 10h
0x18001fa0e  mov     [rsp+38h+arg_4], eax
0x18001fa12  lea     rcx, [rsp+38h+arg_0]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18001fa17  call    ?NotificationDialogCheckboxChanged@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@I_N@Z; NetworkingTriageScenario::FirewallUX::NotificationDialogCheckboxChanged(NetworkingTriageScenario::FirewallUX::RequiredFields const &,uint,bool)
0x18001fa1c  lea     rbx, [rdi+228h]
0x18001fa23  mov     rcx, rbx; lpCriticalSection
0x18001fa26  call    cs:__imp_EnterCriticalSection
0x18001fa2c  cmp     ebp, 4
0x18001fa2f  jnz     short loc_18001FA44
0x18001fa31  mov     [rdi+250h], sil
0x18001fa38  lea     rcx, [rsp+38h+arg_10]
0x18001fa3d  call    ??$PublicNetworksCheckboxToggled@AEA_N@FirewallUxTelemetry@@SAXAEA_N@Z; FirewallUxTelemetry::PublicNetworksCheckboxToggled<bool &>(bool &)
0x18001fa42  jmp     short loc_18001FA72
0x18001fa44  cmp     ebp, 2
0x18001fa47  jnz     short loc_18001FA5C
0x18001fa49  mov     [rdi+251h], sil
0x18001fa50  lea     rcx, [rsp+38h+arg_10]
0x18001fa55  call    ??$PrivateNetworksCheckboxToggled@AEA_N@FirewallUxTelemetry@@SAXAEA_N@Z; FirewallUxTelemetry::PrivateNetworksCheckboxToggled<bool &>(bool &)
0x18001fa5a  jmp     short loc_18001FA72
0x18001fa5c  cmp     ebp, 1
0x18001fa5f  jnz     short loc_18001FA7C
0x18001fa61  mov     [rdi+252h], sil
0x18001fa68  lea     rcx, [rsp+38h+arg_10]
0x18001fa6d  call    ??$DomainNetworksCheckboxToggled@AEA_N@FirewallUxTelemetry@@SAXAEA_N@Z; FirewallUxTelemetry::DomainNetworksCheckboxToggled<bool &>(bool &)
0x18001fa72  mov     rcx, rdi; this
0x18001fa75  call    ?_TryFindAndUpdateAllowCommandEnabled@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::_TryFindAndUpdateAllowCommandEnabled(void)
0x18001fa7a  jmp     short loc_18001FA81
0x18001fa7c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fa81  test    rbx, rbx
0x18001fa84  jz      short loc_18001FA90
0x18001fa86  mov     rcx, rbx; lpCriticalSection
0x18001fa89  call    cs:__imp_LeaveCriticalSection
0x18001fa8f  nop
0x18001fa90  mov     rbx, [rsp+38h+arg_8]
0x18001fa95  add     rsp, 20h
0x18001fa99  pop     rdi
0x18001fa9a  pop     rsi
0x18001fa9b  pop     rbp
0x18001fa9c  retn
0x18001fa9d  mov     rcx, [rsp+38h]; this
0x18001faa2  lea     r9, aUnexpectedDial; "Unexpected dialog type"
0x18001faa9  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\networkux\\firewall"...
0x18001fab0  mov     edx, 3Bh ; ';'; void *
0x18001fab5  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
