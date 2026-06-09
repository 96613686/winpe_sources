# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180020888`
- end: `0x1800208d4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180020348`
- `0x1800204d0`
- `0x180020674`
- `0x180020794`

## callees

- `0x180020598`
- `0x18002061c`
- `0x180020888`
- `0x18002a360`

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
0x180020888  mov     [rsp+arg_8], rbx
0x18002088d  mov     [rsp+arg_10], rsi
0x180020892  push    rdi
0x180020893  sub     rsp, 20h
0x180020897  mov     rdi, [rcx]
0x18002089a  mov     rsi, rdx
0x18002089d  mov     rbx, rcx
0x1800208a0  test    rdi, rdi
0x1800208a3  jz      short loc_1800208C1
0x1800208a5  lea     rcx, [rsp+28h+arg_0]; this
0x1800208aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800208af  mov     rcx, rdi; pti
0x1800208b2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800208b7  lea     rcx, [rsp+28h+arg_0]; this
0x1800208bc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800208c1  mov     [rbx], rsi
0x1800208c4  mov     rbx, [rsp+28h+arg_8]
0x1800208c9  mov     rsi, [rsp+28h+arg_10]
0x1800208ce  add     rsp, 20h
0x1800208d2  pop     rdi
0x1800208d3  retn
```
