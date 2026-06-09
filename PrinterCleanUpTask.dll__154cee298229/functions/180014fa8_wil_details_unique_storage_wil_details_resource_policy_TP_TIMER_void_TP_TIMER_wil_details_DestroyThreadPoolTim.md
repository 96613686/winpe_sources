# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180014fa8`
- end: `0x180014ff4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010988`
- `0x180010a04`
- `0x180011798`

## callees

- `0x18000a33c`
- `0x18000a95c`
- `0x180012440`
- `0x180014fa8`

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
0x180014fa8  mov     [rsp+arg_8], rbx
0x180014fad  mov     [rsp+arg_10], rsi
0x180014fb2  push    rdi
0x180014fb3  sub     rsp, 20h
0x180014fb7  mov     rdi, [rcx]
0x180014fba  mov     rsi, rdx
0x180014fbd  mov     rbx, rcx
0x180014fc0  test    rdi, rdi
0x180014fc3  jz      short loc_180014FE1
0x180014fc5  lea     rcx, [rsp+28h+arg_0]; this
0x180014fca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180014fcf  mov     rcx, rdi; pti
0x180014fd2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180014fd7  lea     rcx, [rsp+28h+arg_0]; this
0x180014fdc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014fe1  mov     [rbx], rsi
0x180014fe4  mov     rbx, [rsp+28h+arg_8]
0x180014fe9  mov     rsi, [rsp+28h+arg_10]
0x180014fee  add     rsp, 20h
0x180014ff2  pop     rdi
0x180014ff3  retn
```
