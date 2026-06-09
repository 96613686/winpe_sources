# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ClosedHandler(IPopupWindow *,IPopupCommand *)

- ea: `0x18001dbf0`
- end: `0x18001dc34`
- name: `?ClosedHandler@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `68`
- prototype: `void __fastcall __noreturn(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800233e0`

## callees

- `0x18000ed74`
- `0x180012398`
- `0x18001f45c`
- `0x180028a94`
- `0x18002d010`

## pseudocode

```c
void __fastcall __noreturn winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::ClosedHandler(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this,
        struct IPopupWindow *a2,
        struct IPopupCommand *a3)
{
  unsigned int TriageDialogType; // eax
  __int64 v5; // rdx
  struct IPopupCommand *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = a3;
  TriageDialogType = GetTriageDialogType(*((unsigned int *)this + 20));
  NetworkingTriageScenario::FirewallUX::RequiredFields::RequiredFields(&v6, v5, TriageDialogType);
  NetworkingTriageScenario::FirewallUX::NotificationDialogCanceled((const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v6);
  (*(void (__fastcall **)(struct IPopupWindow *))(*(_QWORD *)a2 + 296LL))(a2);
  ExitComServerProcess();
}

```

## disassembly

```asm
0x18001dbf0  mov     [rsp+arg_10], r8
0x18001dbf5  push    rbx
0x18001dbf6  sub     rsp, 20h
0x18001dbfa  mov     ecx, [rcx+50h]
0x18001dbfd  mov     rbx, rdx
0x18001dc00  call    ?GetTriageDialogType@@YA?AW4DialogType@FirewallUX@NetworkingTriageScenario@@W41implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@Z; GetTriageDialogType(winrt::Windows::Internal::NetworkUX::Firewall::implementation::DialogType)
0x18001dc05  mov     r8d, eax
0x18001dc08  lea     rcx, [rsp+28h+arg_10]
0x18001dc0d  call    ??0RequiredFields@FirewallUX@NetworkingTriageScenario@@QEAA@W4EventSources@2@W4DialogType@12@@Z; NetworkingTriageScenario::FirewallUX::RequiredFields::RequiredFields(NetworkingTriageScenario::EventSources,NetworkingTriageScenario::FirewallUX::DialogType)
0x18001dc12  lea     rcx, [rsp+28h+arg_10]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18001dc17  call    ?NotificationDialogCanceled@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@@Z; NetworkingTriageScenario::FirewallUX::NotificationDialogCanceled(NetworkingTriageScenario::FirewallUX::RequiredFields const &)
0x18001dc1c  mov     rax, [rbx]
0x18001dc1f  mov     rcx, rbx
0x18001dc22  mov     rax, [rax+128h]
0x18001dc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc2e  call    ?ExitComServerProcess@@YAXXZ; ExitComServerProcess(void)
```
