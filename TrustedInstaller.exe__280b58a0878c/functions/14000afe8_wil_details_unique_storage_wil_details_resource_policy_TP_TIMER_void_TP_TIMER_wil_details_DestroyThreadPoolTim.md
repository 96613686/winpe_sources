# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000afe8`
- end: `0x14000b034`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000618c`
- `0x140006208`
- `0x1400067d8`
- `0x140006888`
- `0x140008184`
- `0x14001191c`

## callees

- `0x140003b94`
- `0x140003e04`
- `0x1400070d0`
- `0x14000afe8`

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
0x14000afe8  mov     [rsp+arg_8], rbx
0x14000afed  mov     [rsp+arg_10], rsi
0x14000aff2  push    rdi
0x14000aff3  sub     rsp, 20h
0x14000aff7  mov     rdi, [rcx]
0x14000affa  mov     rsi, rdx
0x14000affd  mov     rbx, rcx
0x14000b000  test    rdi, rdi
0x14000b003  jz      short loc_14000B021
0x14000b005  lea     rcx, [rsp+28h+arg_0]; this
0x14000b00a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000b00f  mov     rcx, rdi; pti
0x14000b012  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000b017  lea     rcx, [rsp+28h+arg_0]; this
0x14000b01c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000b021  mov     [rbx], rsi
0x14000b024  mov     rbx, [rsp+28h+arg_8]
0x14000b029  mov     rsi, [rsp+28h+arg_10]
0x14000b02e  add     rsp, 20h
0x14000b032  pop     rdi
0x14000b033  retn
```
