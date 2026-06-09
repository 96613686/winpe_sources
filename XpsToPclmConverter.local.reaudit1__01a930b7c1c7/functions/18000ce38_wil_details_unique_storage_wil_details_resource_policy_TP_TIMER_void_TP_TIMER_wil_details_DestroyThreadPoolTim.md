# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000ce38`
- end: `0x18000ce84`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000880c`
- `0x18000aad0`
- `0x18000aedc`

## callees

- `0x180008418`
- `0x1800089f0`
- `0x180009020`
- `0x18000ce38`

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
0x18000ce38  mov     [rsp+arg_8], rbx
0x18000ce3d  mov     [rsp+arg_10], rsi
0x18000ce42  push    rdi
0x18000ce43  sub     rsp, 20h
0x18000ce47  mov     rdi, [rcx]
0x18000ce4a  mov     rsi, rdx
0x18000ce4d  mov     rbx, rcx
0x18000ce50  test    rdi, rdi
0x18000ce53  jz      short loc_18000CE71
0x18000ce55  lea     rcx, [rsp+28h+arg_0]; this
0x18000ce5a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ce5f  mov     rcx, rdi; pti
0x18000ce62  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000ce67  lea     rcx, [rsp+28h+arg_0]; this
0x18000ce6c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ce71  mov     [rbx], rsi
0x18000ce74  mov     rbx, [rsp+28h+arg_8]
0x18000ce79  mov     rsi, [rsp+28h+arg_10]
0x18000ce7e  add     rsp, 20h
0x18000ce82  pop     rdi
0x18000ce83  retn
```
