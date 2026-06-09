# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1400095a8`
- end: `0x1400095f4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400046e0`
- `0x140004790`
- `0x140006cfc`
- `0x140006de8`
- `0x14000721c`
- `0x14000a174`

## callees

- `0x140004238`
- `0x14000494c`
- `0x140005030`
- `0x1400095a8`

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
0x1400095a8  mov     [rsp+arg_8], rbx
0x1400095ad  mov     [rsp+arg_10], rsi
0x1400095b2  push    rdi
0x1400095b3  sub     rsp, 20h
0x1400095b7  mov     rdi, [rcx]
0x1400095ba  mov     rsi, rdx
0x1400095bd  mov     rbx, rcx
0x1400095c0  test    rdi, rdi
0x1400095c3  jz      short loc_1400095E1
0x1400095c5  lea     rcx, [rsp+28h+arg_0]; this
0x1400095ca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400095cf  mov     rcx, rdi; pti
0x1400095d2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400095d7  lea     rcx, [rsp+28h+arg_0]; this
0x1400095dc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400095e1  mov     [rbx], rsi
0x1400095e4  mov     rbx, [rsp+28h+arg_8]
0x1400095e9  mov     rsi, [rsp+28h+arg_10]
0x1400095ee  add     rsp, 20h
0x1400095f2  pop     rdi
0x1400095f3  retn
```
