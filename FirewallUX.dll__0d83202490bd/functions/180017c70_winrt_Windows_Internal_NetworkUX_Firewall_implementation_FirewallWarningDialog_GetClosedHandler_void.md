# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::GetClosedHandler(void)

- ea: `0x180017c70`
- end: `0x180017da7`
- name: `?GetClosedHandler@FirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA?AU?$delegate@PEAUIPopupWindow@@PEAUIPopupCommand@@@7@XZ`
- size: `311`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021e4`
- `0x180002c10`
- `0x180004fd0`
- `0x18000ac34`
- `0x18000b24c`
- `0x18000b5d0`
- `0x180017c70`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog::GetClosedHandler(
        __int64 a1,
        _QWORD *a2)
{
  __int64 weak_ref; // rax
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  _DWORD *v8; // [rsp+30h] [rbp-20h]
  int pExceptionObject; // [rsp+38h] [rbp-18h] BYREF
  __int128 v10; // [rsp+40h] [rbp-10h]
  __int64 v11; // [rsp+60h] [rbp+10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF
  __int64 v13; // [rsp+78h] [rbp+28h] BYREF

  weak_ref = winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,IClassFactory>::make_weak_ref(a1 + 8);
  if ( !weak_ref )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v11 = weak_ref;
  v12 = 0;
  pExceptionObject = 0;
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)weak_ref + 24LL))(weak_ref, &v12);
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &pExceptionObject);
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  v5 = v12;
  v12 = 0;
  v13 = 0;
  v11 = v5;
  v8 = operator new(0x18u);
  v8[2] = 1;
  v6 = v11;
  v11 = 0;
  *((_QWORD *)v8 + 2) = v6;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v8 = off_18002E5A8;
  *a2 = v8;
  if ( v11 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  if ( v13 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v13);
  if ( v12 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x180017c70  mov     [rsp-8+arg_8], rbx
0x180017c75  push    rbp
0x180017c76  mov     rbp, rsp
0x180017c79  sub     rsp, 50h
0x180017c7d  mov     rbx, rdx
0x180017c80  mov     [rbp+var_30], 0
0x180017c87  add     rcx, 8
0x180017c8b  call    ?make_weak_ref@?$root_implements@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIClassFactory@@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ; winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,IClassFactory>::make_weak_ref(void)
0x180017c90  mov     rcx, rax
0x180017c93  test    rax, rax
0x180017c96  jz      loc_180017D8D
0x180017c9c  mov     [rbp+arg_0], rax
0x180017ca0  mov     [rbp+arg_10], 0
0x180017ca8  mov     [rbp+var_30], 4
0x180017caf  mov     [rbp+pExceptionObject], 0
0x180017cb6  xorps   xmm0, xmm0
0x180017cb9  movdqu  [rbp+var_10], xmm0
0x180017cbe  mov     rax, [rax]
0x180017cc1  lea     rdx, [rbp+arg_10]
0x180017cc5  mov     rax, [rax+18h]
0x180017cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cce  test    eax, eax
0x180017cd0  js      loc_180017D81
0x180017cd6  lea     rcx, [rbp+arg_0]
0x180017cda  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180017cdf  nop
0x180017ce0  mov     rax, [rbp+arg_10]
0x180017ce4  mov     [rbp+arg_10], 0
0x180017cec  lea     rcx, [rbp+arg_18]
0x180017cf0  mov     [rbp+var_28], rcx
0x180017cf4  mov     [rbp+arg_18], 0
0x180017cfc  mov     [rbp+arg_0], rax
0x180017d00  lea     rax, [rbp+arg_0]
0x180017d04  mov     [rbp+var_20], rax
0x180017d08  mov     ecx, 18h; Size
0x180017d0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017d12  mov     [rbp+var_20], rax
0x180017d16  mov     dword ptr [rax+8], 1
0x180017d1d  mov     rcx, [rbp+arg_0]
0x180017d21  mov     [rbp+arg_0], 0
0x180017d29  mov     [rax+10h], rcx
0x180017d2d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180017d34  lea     rcx, off_18002E5A8
0x180017d3b  mov     [rax], rcx
0x180017d3e  mov     [rbx], rax
0x180017d41  cmp     [rbp+arg_0], 0
0x180017d46  jz      short loc_180017D52
0x180017d48  lea     rcx, [rbp+arg_0]
0x180017d4c  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180017d51  nop
0x180017d52  cmp     [rbp+arg_18], 0
0x180017d57  jz      short loc_180017D63
0x180017d59  lea     rcx, [rbp+arg_18]
0x180017d5d  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180017d62  nop
0x180017d63  cmp     [rbp+arg_10], 0
0x180017d68  jz      short loc_180017D73
0x180017d6a  lea     rcx, [rbp+arg_10]
0x180017d6e  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180017d73  mov     rax, rbx
0x180017d76  mov     rbx, [rsp+50h+arg_8]
0x180017d7b  add     rsp, 50h
0x180017d7f  pop     rbp
0x180017d80  retn
0x180017d81  lea     rdx, [rbp+pExceptionObject]
0x180017d85  mov     ecx, eax
0x180017d87  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180017d8d  lea     rcx, [rbp+pExceptionObject]; this
0x180017d91  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180017d96  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180017d9d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017da1  call    _CxxThrowException_0
```
