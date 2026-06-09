# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1400082f4`
- end: `0x140008340`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007474`
- `0x140007894`
- `0x1400081e4`
- `0x140008264`
- `0x14000850c`
- `0x14000a1ac`

## callees

- `0x1400082f4`
- `0x14000ab14`
- `0x14000ad60`
- `0x14000b370`

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
0x1400082f4  mov     [rsp+arg_8], rbx
0x1400082f9  mov     [rsp+arg_10], rsi
0x1400082fe  push    rdi
0x1400082ff  sub     rsp, 20h
0x140008303  mov     rdi, [rcx]
0x140008306  mov     rsi, rdx
0x140008309  mov     rbx, rcx
0x14000830c  test    rdi, rdi
0x14000830f  jz      short loc_14000832D
0x140008311  lea     rcx, [rsp+28h+arg_0]; this
0x140008316  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000831b  mov     rcx, rdi; pti
0x14000831e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140008323  lea     rcx, [rsp+28h+arg_0]; this
0x140008328  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000832d  mov     [rbx], rsi
0x140008330  mov     rbx, [rsp+28h+arg_8]
0x140008335  mov     rsi, [rsp+28h+arg_10]
0x14000833a  add     rsp, 20h
0x14000833e  pop     rdi
0x14000833f  retn
```
