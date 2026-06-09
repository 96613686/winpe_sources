# winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>(uint,winrt::hstring const &,winrt::delegate<IPopupWindow *,IPopupCommand *>)

- ea: `0x18000eaa8`
- end: `0x18000ec04`
- name: `??0?$heap_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@QEAA@IAEBUhstring@2@U?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@2@@Z`
- size: `348`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e9d4`

## callees

- `0x1800021e4`
- `0x18000b5d0`
- `0x18000eaa8`
- `0x180016dbc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rsi
  _QWORD *v9; // rbx
  __int64 v10; // r14
  __int64 v12; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+28h] [rbp-18h] BYREF

  v6 = *a4;
  *a4 = 0;
  v12 = v6;
  v13[1] = &v12;
  *(_QWORD *)a1 = &winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 16) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>'};
  *(_QWORD *)(a1 + 8) = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,IPopupCommand>'};
  v7 = (_QWORD *)(a1 + 32);
  *v7 = 0;
  v8 = (_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 24) = a2;
  winrt::hstring::operator=(v7, a3);
  v9 = operator new(0x20u);
  v10 = v12;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  *v9 = &winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,std::tuple<IPopupCommandHandler>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v9[2] = 1;
  v9[3] = v10;
  *v9 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,std::tuple<IPopupCommandHandler>>'};
  v9[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,IPopupCommandHandler>'};
  v13[0] = v9;
  if ( v8 == v13 )
  {
    if ( v9 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v13);
  }
  else
  {
    if ( *v8 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1 + 40);
    *v8 = v9;
  }
  if ( v12 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>'};
  *(_QWORD *)(a1 + 8) = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,IPopupCommand>'};
  if ( *a4 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a4);
  return a1;
}

```

## disassembly

```asm
0x18000eaa8  mov     [rsp-28h+arg_10], rbx
0x18000eaad  mov     [rsp-28h+arg_18], r9
0x18000eab2  mov     [rsp-28h+arg_0], rcx
0x18000eab7  push    rbp
0x18000eab8  push    rsi
0x18000eab9  push    rdi
0x18000eaba  push    r14
0x18000eabc  push    r15
0x18000eabe  mov     rbp, rsp
0x18000eac1  sub     rsp, 40h
0x18000eac5  mov     r15, r9
0x18000eac8  mov     rdi, rcx
0x18000eacb  mov     rax, [r9]
0x18000eace  mov     qword ptr [r9], 0
0x18000ead5  mov     [rbp+var_20], rax
0x18000ead9  lea     rax, [rbp+var_20]
0x18000eadd  mov     [rbp+var_10], rax
0x18000eae1  lea     rax, ??_7?$producers_base@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupCommand@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>::`vftable'
0x18000eae8  mov     [rcx], rax
0x18000eaeb  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000eaf2  mov     qword ptr [rcx+10h], 1
0x18000eafa  lea     rax, ??_7?$heap_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupCommand@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>'}
0x18000eb01  mov     [rcx], rax
0x18000eb04  lea     rax, ??_7?$heap_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupCommand@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,IPopupCommand>'}
0x18000eb0b  mov     [rcx+8], rax
0x18000eb0f  add     rcx, 20h ; ' '
0x18000eb13  mov     qword ptr [rcx], 0
0x18000eb1a  lea     rsi, [rdi+28h]
0x18000eb1e  mov     qword ptr [rsi], 0
0x18000eb25  mov     [rdi+18h], edx
0x18000eb28  mov     rdx, r8
0x18000eb2b  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18000eb30  mov     ecx, 20h ; ' '; Size
0x18000eb35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eb3a  mov     rbx, rax
0x18000eb3d  mov     [rbp+arg_18], rax
0x18000eb41  mov     r14, [rbp+var_20]
0x18000eb45  test    r14, r14
0x18000eb48  jz      short loc_18000EB59
0x18000eb4a  mov     rcx, [r14]
0x18000eb4d  mov     rax, [rcx+8]
0x18000eb51  mov     rcx, r14
0x18000eb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb59  lea     rax, ??_7?$producers_base@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupCommandHandler@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,std::tuple<IPopupCommandHandler>>::`vftable'
0x18000eb60  mov     [rbx], rax
0x18000eb63  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000eb6a  mov     qword ptr [rbx+10h], 1
0x18000eb72  mov     [rbx+18h], r14
0x18000eb76  lea     rax, ??_7?$heap_implements@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupCommandHandler@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,std::tuple<IPopupCommandHandler>>'}
0x18000eb7d  mov     [rbx], rax
0x18000eb80  lea     rax, ??_7?$heap_implements@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UPopupCommandHandler@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupCommandHandler@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommandHandler,IPopupCommandHandler>'}
0x18000eb87  mov     [rbx+8], rax
0x18000eb8b  mov     [rbp+var_18], rbx
0x18000eb8f  lea     rax, [rbp+var_18]
0x18000eb93  cmp     rsi, rax
0x18000eb96  jz      short loc_18000EBAB
0x18000eb98  cmp     qword ptr [rsi], 0
0x18000eb9c  jz      short loc_18000EBA6
0x18000eb9e  mov     rcx, rsi
0x18000eba1  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000eba6  mov     [rsi], rbx
0x18000eba9  jmp     short loc_18000EBBA
0x18000ebab  test    rbx, rbx
0x18000ebae  jz      short loc_18000EBBA
0x18000ebb0  lea     rcx, [rbp+var_18]
0x18000ebb4  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000ebb9  nop
0x18000ebba  cmp     [rbp+var_20], 0
0x18000ebbf  jz      short loc_18000EBCA
0x18000ebc1  lea     rcx, [rbp+var_20]
0x18000ebc5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000ebca  lea     rax, ??_7?$heap_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupCommand@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,std::tuple<IPopupCommand>>'}
0x18000ebd1  mov     [rdi], rax
0x18000ebd4  lea     rax, ??_7?$heap_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UPopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupCommand@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand,IPopupCommand>'}
0x18000ebdb  mov     [rdi+8], rax
0x18000ebdf  cmp     qword ptr [r15], 0
0x18000ebe3  jz      short loc_18000EBED
0x18000ebe5  mov     rcx, r15
0x18000ebe8  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000ebed  mov     rax, rdi
0x18000ebf0  mov     rbx, [rsp+40h+arg_10]
0x18000ebf8  add     rsp, 40h
0x18000ebfc  pop     r15
0x18000ebfe  pop     r14
0x18000ec00  pop     rdi
0x18000ec01  pop     rsi
0x18000ec02  pop     rbp
0x18000ec03  retn
```
