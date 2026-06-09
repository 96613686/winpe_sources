# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180001aa0`
- end: `0x180001aec`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002b50`
- `0x180008010`
- `0x1800080c0`
- `0x1800096c8`
- `0x1800097e8`
- `0x1800098d4`
- `0x180009cc0`

## callees

- `0x180001aa0`
- `0x180002f20`
- `0x18000500c`
- `0x180005244`

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
0x180001aa0  mov     [rsp+arg_8], rbx
0x180001aa5  mov     [rsp+arg_10], rsi
0x180001aaa  push    rdi
0x180001aab  sub     rsp, 20h
0x180001aaf  mov     rdi, [rcx]
0x180001ab2  mov     rsi, rdx
0x180001ab5  mov     rbx, rcx
0x180001ab8  test    rdi, rdi
0x180001abb  jz      short loc_180001AD9
0x180001abd  lea     rcx, [rsp+28h+arg_0]; this
0x180001ac2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180001ac7  mov     rcx, rdi; pti
0x180001aca  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180001acf  lea     rcx, [rsp+28h+arg_0]; this
0x180001ad4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180001ad9  mov     [rbx], rsi
0x180001adc  mov     rbx, [rsp+28h+arg_8]
0x180001ae1  mov     rsi, [rsp+28h+arg_10]
0x180001ae6  add     rsp, 20h
0x180001aea  pop     rdi
0x180001aeb  retn
```
