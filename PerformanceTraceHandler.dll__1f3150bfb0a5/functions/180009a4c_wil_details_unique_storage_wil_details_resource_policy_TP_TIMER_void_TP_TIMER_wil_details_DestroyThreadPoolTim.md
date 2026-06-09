# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180009a4c`
- end: `0x180009a98`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800049e8`
- `0x180004a98`
- `0x180007000`
- `0x1800070ec`
- `0x18000755c`
- `0x18000c848`

## callees

- `0x1800045b8`
- `0x180004c88`
- `0x1800052d0`
- `0x180009a4c`

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
0x180009a4c  mov     [rsp+arg_8], rbx
0x180009a51  mov     [rsp+arg_10], rsi
0x180009a56  push    rdi
0x180009a57  sub     rsp, 20h
0x180009a5b  mov     rdi, [rcx]
0x180009a5e  mov     rsi, rdx
0x180009a61  mov     rbx, rcx
0x180009a64  test    rdi, rdi
0x180009a67  jz      short loc_180009A85
0x180009a69  lea     rcx, [rsp+28h+arg_0]; this
0x180009a6e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009a73  mov     rcx, rdi; pti
0x180009a76  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180009a7b  lea     rcx, [rsp+28h+arg_0]; this
0x180009a80  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009a85  mov     [rbx], rsi
0x180009a88  mov     rbx, [rsp+28h+arg_8]
0x180009a8d  mov     rsi, [rsp+28h+arg_10]
0x180009a92  add     rsp, 20h
0x180009a96  pop     rdi
0x180009a97  retn
```
