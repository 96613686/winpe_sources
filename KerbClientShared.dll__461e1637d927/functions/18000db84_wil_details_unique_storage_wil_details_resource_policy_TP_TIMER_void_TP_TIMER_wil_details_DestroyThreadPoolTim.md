# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000db84`
- end: `0x18000dbd0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d29c`
- `0x18000d31c`
- `0x18000d92c`
- `0x18000da14`

## callees

- `0x18000dadc`
- `0x18000db60`
- `0x18000db84`
- `0x180010b80`

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
0x18000db84  mov     [rsp+arg_8], rbx
0x18000db89  mov     [rsp+arg_10], rsi
0x18000db8e  push    rdi
0x18000db8f  sub     rsp, 20h
0x18000db93  mov     rdi, [rcx]
0x18000db96  mov     rsi, rdx
0x18000db99  mov     rbx, rcx
0x18000db9c  test    rdi, rdi
0x18000db9f  jz      short loc_18000DBBD
0x18000dba1  lea     rcx, [rsp+28h+arg_0]; this
0x18000dba6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dbab  mov     rcx, rdi; pti
0x18000dbae  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000dbb3  lea     rcx, [rsp+28h+arg_0]; this
0x18000dbb8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dbbd  mov     [rbx], rsi
0x18000dbc0  mov     rbx, [rsp+28h+arg_8]
0x18000dbc5  mov     rsi, [rsp+28h+arg_10]
0x18000dbca  add     rsp, 20h
0x18000dbce  pop     rdi
0x18000dbcf  retn
```
