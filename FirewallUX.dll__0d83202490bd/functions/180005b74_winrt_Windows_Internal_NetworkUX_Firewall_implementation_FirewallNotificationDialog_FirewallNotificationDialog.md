# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::~FirewallNotificationDialog(void)

- ea: `0x180005b74`
- end: `0x180005be5`
- name: `??1FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x180005974`
- `0x180005a4c`
- `0x180005b74`
- `0x18000b5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b84`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b84`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::~FirewallNotificationDialog(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::~vector<winrt::Windows::UI::Xaml::Controls::CheckBox>((char *)this + 528);
  if ( *((_QWORD *)this + 62) )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref((char *)this + 496);
  std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::~vector<winrt::Windows::UI::Xaml::Controls::CheckBox>((char *)this + 472);
  if ( *((_QWORD *)this + 58) )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref((char *)this + 464);
  if ( *((_QWORD *)this + 57) )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref((char *)this + 456);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::~FirewallDialogBase(this);
}

```

## disassembly

```asm
0x180005b74  push    rbx
0x180005b76  sub     rsp, 20h
0x180005b7a  mov     rbx, rcx
0x180005b7d  add     rcx, 228h; lpCriticalSection
0x180005b84  call    cs:__imp_DeleteCriticalSection
0x180005b8a  lea     rcx, [rbx+210h]
0x180005b91  call    ??1?$vector@UCheckBox@Controls@Xaml@UI@Windows@winrt@@V?$allocator@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::~vector<winrt::Windows::UI::Xaml::Controls::CheckBox>(void)
0x180005b96  lea     rcx, [rbx+1F0h]
0x180005b9d  cmp     qword ptr [rcx], 0
0x180005ba1  jz      short loc_180005BA8
0x180005ba3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180005ba8  lea     rcx, [rbx+1D8h]
0x180005baf  call    ??1?$vector@UCheckBox@Controls@Xaml@UI@Windows@winrt@@V?$allocator@UCheckBox@Controls@Xaml@UI@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::UI::Xaml::Controls::CheckBox>::~vector<winrt::Windows::UI::Xaml::Controls::CheckBox>(void)
0x180005bb4  lea     rcx, [rbx+1D0h]
0x180005bbb  cmp     qword ptr [rcx], 0
0x180005bbf  jz      short loc_180005BC6
0x180005bc1  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180005bc6  lea     rcx, [rbx+1C8h]
0x180005bcd  cmp     qword ptr [rcx], 0
0x180005bd1  jz      short loc_180005BD8
0x180005bd3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180005bd8  mov     rcx, rbx; this
0x180005bdb  add     rsp, 20h
0x180005bdf  pop     rbx
0x180005be0  jmp     ??1FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA@XZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::~FirewallDialogBase(void)
```
