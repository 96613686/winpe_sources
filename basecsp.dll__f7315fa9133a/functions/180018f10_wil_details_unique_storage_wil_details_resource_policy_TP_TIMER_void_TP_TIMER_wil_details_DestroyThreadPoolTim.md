# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180018f10`
- end: `0x180018f5c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bd98`
- `0x18000be48`
- `0x180014c74`
- `0x180014d60`
- `0x180014e58`
- `0x1800152cc`

## callees

- `0x18000b810`
- `0x18000c020`
- `0x18000d55c`
- `0x180018f10`

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
0x180018f10  mov     [rsp+arg_8], rbx
0x180018f15  mov     [rsp+arg_10], rsi
0x180018f1a  push    rdi
0x180018f1b  sub     rsp, 20h
0x180018f1f  mov     rdi, [rcx]
0x180018f22  mov     rsi, rdx
0x180018f25  mov     rbx, rcx
0x180018f28  test    rdi, rdi
0x180018f2b  jz      short loc_180018F49
0x180018f2d  lea     rcx, [rsp+28h+arg_0]; this
0x180018f32  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018f37  mov     rcx, rdi; pti
0x180018f3a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180018f3f  lea     rcx, [rsp+28h+arg_0]; this
0x180018f44  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018f49  mov     [rbx], rsi
0x180018f4c  mov     rbx, [rsp+28h+arg_8]
0x180018f51  mov     rsi, [rsp+28h+arg_10]
0x180018f56  add     rsp, 20h
0x180018f5a  pop     rdi
0x180018f5b  retn
```
