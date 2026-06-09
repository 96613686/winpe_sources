# winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vector deleting destructor'(uint)

- ea: `0x1800294f0`
- end: `0x180029538`
- name: `??_E?$heap_implements@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@UEAAPEAXI@Z`
- size: `72`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800294e0`

## callees

- `0x1800025f8`
- `0x1800058ec`
- `0x18000b5d0`
- `0x1800294f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vector deleting destructor'(
        char *a1,
        char a2)
{
  _QWORD *v4; // rcx

  v4 = a1 + 24;
  if ( *v4 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v4);
  winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>::~root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>(a1 + 8);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800294f0  mov     [rsp+arg_0], rbx
0x1800294f5  push    rdi
0x1800294f6  sub     rsp, 20h
0x1800294fa  mov     rbx, rcx
0x1800294fd  mov     edi, edx
0x1800294ff  add     rcx, 18h
0x180029503  cmp     qword ptr [rcx], 0
0x180029507  jz      short loc_18002950E
0x180029509  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18002950e  lea     rcx, [rbx+8]
0x180029512  call    ??1?$root_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIClassFactory@@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>::~root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>(void)
0x180029517  test    dil, 1
0x18002951b  jz      short loc_18002952A
0x18002951d  mov     edx, 20h ; ' '; unsigned __int64
0x180029522  mov     rcx, rbx; void *
0x180029525  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002952a  mov     rax, rbx
0x18002952d  mov     rbx, [rsp+28h+arg_0]
0x180029532  add     rsp, 20h
0x180029536  pop     rdi
0x180029537  retn
```
