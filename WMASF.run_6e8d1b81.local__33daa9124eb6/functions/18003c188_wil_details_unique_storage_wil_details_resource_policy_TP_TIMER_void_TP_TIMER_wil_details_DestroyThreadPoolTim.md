# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18003c188`
- end: `0x18003c1d4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032c1c`
- `0x180033770`
- `0x1800396d4`

## callees

- `0x1800334c4`
- `0x1800338dc`
- `0x180035ce4`
- `0x18003c188`

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
0x18003c188  mov     [rsp+arg_8], rbx
0x18003c18d  mov     [rsp+arg_10], rsi
0x18003c192  push    rdi
0x18003c193  sub     rsp, 20h
0x18003c197  mov     rdi, [rcx]
0x18003c19a  mov     rsi, rdx
0x18003c19d  mov     rbx, rcx
0x18003c1a0  test    rdi, rdi
0x18003c1a3  jz      short loc_18003C1C1
0x18003c1a5  lea     rcx, [rsp+28h+arg_0]; this
0x18003c1aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003c1af  mov     rcx, rdi; pti
0x18003c1b2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18003c1b7  lea     rcx, [rsp+28h+arg_0]; this
0x18003c1bc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003c1c1  mov     [rbx], rsi
0x18003c1c4  mov     rbx, [rsp+28h+arg_8]
0x18003c1c9  mov     rsi, [rsp+28h+arg_10]
0x18003c1ce  add     rsp, 20h
0x18003c1d2  pop     rdi
0x18003c1d3  retn
```
