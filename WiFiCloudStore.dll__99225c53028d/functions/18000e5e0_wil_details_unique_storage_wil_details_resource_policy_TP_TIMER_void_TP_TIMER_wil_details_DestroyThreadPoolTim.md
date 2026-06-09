# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000e5e0`
- end: `0x18000e62c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e634`
- `0x18000f450`
- `0x180027ed4`
- `0x180028670`
- `0x18002d760`
- `0x180031280`

## callees

- `0x18000e17c`
- `0x18000e19c`
- `0x18000e5e0`
- `0x18002d290`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000e5e0  mov     [rsp+arg_8], rbx
0x18000e5e5  mov     [rsp+arg_10], rsi
0x18000e5ea  push    rdi
0x18000e5eb  sub     rsp, 20h
0x18000e5ef  mov     rdi, [rcx]
0x18000e5f2  mov     rsi, rdx
0x18000e5f5  mov     rbx, rcx
0x18000e5f8  test    rdi, rdi
0x18000e5fb  jz      short loc_18000E619
0x18000e5fd  lea     rcx, [rsp+28h+arg_0]; this
0x18000e602  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e607  mov     rcx, rdi; pti
0x18000e60a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000e60f  lea     rcx, [rsp+28h+arg_0]; this
0x18000e614  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e619  mov     [rbx], rsi
0x18000e61c  mov     rbx, [rsp+28h+arg_8]
0x18000e621  mov     rsi, [rsp+28h+arg_10]
0x18000e626  add     rsp, 20h
0x18000e62a  pop     rdi
0x18000e62b  retn
```
