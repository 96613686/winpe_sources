# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180011884`
- end: `0x1800118d1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800066f0`
- `0x180006774`
- `0x1800076f8`
- `0x180007804`
- `0x18000b974`
- `0x18000bb0c`

## callees

- `0x18000383c`
- `0x180003990`
- `0x180009e74`
- `0x180011884`

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
0x180011884  mov     [rsp+arg_8], rbx
0x180011889  mov     [rsp+arg_10], rsi
0x18001188e  push    rdi
0x18001188f  sub     rsp, 20h
0x180011893  mov     rdi, [rcx]
0x180011896  mov     rsi, rdx
0x180011899  mov     rbx, rcx
0x18001189c  test    rdi, rdi
0x18001189f  jz      short loc_1800118BD
0x1800118a1  lea     rcx, [rsp+28h+arg_0]; this
0x1800118a6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800118ab  mov     rcx, rdi; pti
0x1800118ae  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800118b3  lea     rcx, [rsp+28h+arg_0]; this
0x1800118b8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800118bd  mov     [rbx], rsi
0x1800118c0  mov     rbx, [rsp+28h+arg_8]
0x1800118c5  mov     rsi, [rsp+28h+arg_10]
0x1800118ca  add     rsp, 20h
0x1800118ce  pop     rdi
0x1800118cf  retn
```
