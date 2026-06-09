# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000c300`
- end: `0x18000c34d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009118`
- `0x18000abb0`
- `0x18000f22c`
- `0x1800364e8`
- `0x18003656c`
- `0x1800368d8`

## callees

- `0x180008de0`
- `0x180009258`
- `0x180009714`
- `0x18000c300`

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
0x18000c300  mov     [rsp+arg_8], rbx
0x18000c305  mov     [rsp+arg_10], rsi
0x18000c30a  push    rdi
0x18000c30b  sub     rsp, 20h
0x18000c30f  mov     rdi, [rcx]
0x18000c312  mov     rsi, rdx
0x18000c315  mov     rbx, rcx
0x18000c318  test    rdi, rdi
0x18000c31b  jz      short loc_18000C339
0x18000c31d  lea     rcx, [rsp+28h+arg_0]; this
0x18000c322  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c327  mov     rcx, rdi; pti
0x18000c32a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000c32f  lea     rcx, [rsp+28h+arg_0]; this
0x18000c334  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c339  mov     [rbx], rsi
0x18000c33c  mov     rbx, [rsp+28h+arg_8]
0x18000c341  mov     rsi, [rsp+28h+arg_10]
0x18000c346  add     rsp, 20h
0x18000c34a  pop     rdi
0x18000c34b  retn
```
