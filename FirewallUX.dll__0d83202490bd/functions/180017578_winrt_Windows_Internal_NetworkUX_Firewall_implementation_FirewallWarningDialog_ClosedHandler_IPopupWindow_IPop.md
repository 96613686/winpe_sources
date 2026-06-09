# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::ClosedHandler(IPopupWindow *,IPopupCommand *)

- ea: `0x180017578`
- end: `0x1800175b7`
- name: `?ClosedHandler@FirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAXPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `63`
- prototype: `void __fastcall __noreturn(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x18000ed74`
- `0x180018568`
- `0x180028a94`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::ClosedHandler(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog *this,
        struct IPopupWindow *a2,
        struct IPopupCommand *a3)
{
  struct IPopupCommand *v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = a3;
  NetworkingTriageScenario::FirewallUX::RequiredFields::RequiredFields(&v4, a2, 1);
  NetworkingTriageScenario::FirewallUX::WarningDialogClosed((const struct NetworkingTriageScenario::FirewallUX::RequiredFields *)&v4);
  (*(void (__fastcall **)(struct IPopupWindow *))(*(_QWORD *)a2 + 296LL))(a2);
  ExitComServerProcess();
}

```

## disassembly

```asm
0x180017578  mov     [rsp+arg_10], r8
0x18001757d  push    rbx
0x18001757e  sub     rsp, 20h
0x180017582  mov     r8d, 1
0x180017588  lea     rcx, [rsp+28h+arg_10]
0x18001758d  mov     rbx, rdx
0x180017590  call    ??0RequiredFields@FirewallUX@NetworkingTriageScenario@@QEAA@W4EventSources@2@W4DialogType@12@@Z; NetworkingTriageScenario::FirewallUX::RequiredFields::RequiredFields(NetworkingTriageScenario::EventSources,NetworkingTriageScenario::FirewallUX::DialogType)
0x180017595  lea     rcx, [rsp+28h+arg_10]; struct NetworkingTriageScenario::FirewallUX::RequiredFields *
0x18001759a  call    ?WarningDialogClosed@FirewallUX@NetworkingTriageScenario@@SAXAEBURequiredFields@12@@Z; NetworkingTriageScenario::FirewallUX::WarningDialogClosed(NetworkingTriageScenario::FirewallUX::RequiredFields const &)
0x18001759f  mov     rax, [rbx]
0x1800175a2  mov     rcx, rbx
0x1800175a5  mov     rax, [rax+128h]
0x1800175ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175b1  call    ?ExitComServerProcess@@YAXXZ; ExitComServerProcess(void)
```
