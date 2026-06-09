# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000adb8`
- end: `0x18000ae04`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007e24`
- `0x18000931c`
- `0x1800096a8`

## callees

- `0x180004d14`
- `0x180005010`
- `0x180008384`
- `0x18000adb8`

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
0x18000adb8  mov     [rsp+arg_8], rbx
0x18000adbd  mov     [rsp+arg_10], rsi
0x18000adc2  push    rdi
0x18000adc3  sub     rsp, 20h
0x18000adc7  mov     rdi, [rcx]
0x18000adca  mov     rsi, rdx
0x18000adcd  mov     rbx, rcx
0x18000add0  test    rdi, rdi
0x18000add3  jz      short loc_18000ADF1
0x18000add5  lea     rcx, [rsp+28h+arg_0]; this
0x18000adda  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000addf  mov     rcx, rdi; pti
0x18000ade2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000ade7  lea     rcx, [rsp+28h+arg_0]; this
0x18000adec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000adf1  mov     [rbx], rsi
0x18000adf4  mov     rbx, [rsp+28h+arg_8]
0x18000adf9  mov     rsi, [rsp+28h+arg_10]
0x18000adfe  add     rsp, 20h
0x18000ae02  pop     rdi
0x18000ae03  retn
```
