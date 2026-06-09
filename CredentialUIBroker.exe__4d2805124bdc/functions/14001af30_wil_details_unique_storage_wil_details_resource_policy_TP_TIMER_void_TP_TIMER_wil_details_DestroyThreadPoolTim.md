# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14001af30`
- end: `0x14001af7c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005218`
- `0x140005294`
- `0x1400094ac`
- `0x1400095f0`
- `0x140010880`
- `0x140011e9c`

## callees

- `0x1400085ac`
- `0x1400097ec`
- `0x14000b89c`
- `0x14001af30`

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
0x14001af30  mov     [rsp+arg_8], rbx
0x14001af35  mov     [rsp+arg_10], rsi
0x14001af3a  push    rdi
0x14001af3b  sub     rsp, 20h
0x14001af3f  mov     rdi, [rcx]
0x14001af42  mov     rsi, rdx
0x14001af45  mov     rbx, rcx
0x14001af48  test    rdi, rdi
0x14001af4b  jz      short loc_14001AF69
0x14001af4d  lea     rcx, [rsp+28h+arg_0]; this
0x14001af52  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001af57  mov     rcx, rdi; pti
0x14001af5a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14001af5f  lea     rcx, [rsp+28h+arg_0]; this
0x14001af64  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001af69  mov     [rbx], rsi
0x14001af6c  mov     rbx, [rsp+28h+arg_8]
0x14001af71  mov     rsi, [rsp+28h+arg_10]
0x14001af76  add     rsp, 20h
0x14001af7a  pop     rdi
0x14001af7b  retn
```
