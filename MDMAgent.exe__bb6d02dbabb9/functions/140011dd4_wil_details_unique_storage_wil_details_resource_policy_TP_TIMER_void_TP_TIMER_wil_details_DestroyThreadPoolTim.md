# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140011dd4`
- end: `0x140011e21`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008e44`
- `0x140008ec8`
- `0x140009548`

## callees

- `0x1400048c8`
- `0x140004d00`
- `0x14000b7f4`
- `0x140011dd4`

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
0x140011dd4  mov     [rsp+arg_8], rbx
0x140011dd9  mov     [rsp+arg_10], rsi
0x140011dde  push    rdi
0x140011ddf  sub     rsp, 20h
0x140011de3  mov     rdi, [rcx]
0x140011de6  mov     rsi, rdx
0x140011de9  mov     rbx, rcx
0x140011dec  test    rdi, rdi
0x140011def  jz      short loc_140011E0D
0x140011df1  lea     rcx, [rsp+28h+arg_0]; this
0x140011df6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140011dfb  mov     rcx, rdi; pti
0x140011dfe  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140011e03  lea     rcx, [rsp+28h+arg_0]; this
0x140011e08  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140011e0d  mov     [rbx], rsi
0x140011e10  mov     rbx, [rsp+28h+arg_8]
0x140011e15  mov     rsi, [rsp+28h+arg_10]
0x140011e1a  add     rsp, 20h
0x140011e1e  pop     rdi
0x140011e1f  retn
```
