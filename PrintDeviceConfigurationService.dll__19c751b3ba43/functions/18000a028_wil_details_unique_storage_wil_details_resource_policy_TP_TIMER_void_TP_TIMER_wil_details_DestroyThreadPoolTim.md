# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000a028`
- end: `0x18000a074`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004fa0`
- `0x180005050`
- `0x18000762c`
- `0x180007718`
- `0x180007b8c`
- `0x18000bac8`
- `0x18000f5e4`

## callees

- `0x180004af8`
- `0x180005240`
- `0x180005910`
- `0x18000a028`

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
0x18000a028  mov     [rsp+arg_8], rbx
0x18000a02d  mov     [rsp+arg_10], rsi
0x18000a032  push    rdi
0x18000a033  sub     rsp, 20h
0x18000a037  mov     rdi, [rcx]
0x18000a03a  mov     rsi, rdx
0x18000a03d  mov     rbx, rcx
0x18000a040  test    rdi, rdi
0x18000a043  jz      short loc_18000A061
0x18000a045  lea     rcx, [rsp+28h+arg_0]; this
0x18000a04a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a04f  mov     rcx, rdi; pti
0x18000a052  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000a057  lea     rcx, [rsp+28h+arg_0]; this
0x18000a05c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a061  mov     [rbx], rsi
0x18000a064  mov     rbx, [rsp+28h+arg_8]
0x18000a069  mov     rsi, [rsp+28h+arg_10]
0x18000a06e  add     rsp, 20h
0x18000a072  pop     rdi
0x18000a073  retn
```
