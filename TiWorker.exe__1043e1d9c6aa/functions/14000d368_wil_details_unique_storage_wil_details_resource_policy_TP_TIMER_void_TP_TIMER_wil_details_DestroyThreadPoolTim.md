# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x14000d368`
- end: `0x14000d3b4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009b50`
- `0x140009bcc`
- `0x14000a1bc`

## callees

- `0x140003aa4`
- `0x140003d14`
- `0x14000aa30`
- `0x14000d368`

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
0x14000d368  mov     [rsp+arg_8], rbx
0x14000d36d  mov     [rsp+arg_10], rsi
0x14000d372  push    rdi
0x14000d373  sub     rsp, 20h
0x14000d377  mov     rdi, [rcx]
0x14000d37a  mov     rsi, rdx
0x14000d37d  mov     rbx, rcx
0x14000d380  test    rdi, rdi
0x14000d383  jz      short loc_14000D3A1
0x14000d385  lea     rcx, [rsp+28h+arg_0]; this
0x14000d38a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000d38f  mov     rcx, rdi; pti
0x14000d392  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000d397  lea     rcx, [rsp+28h+arg_0]; this
0x14000d39c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000d3a1  mov     [rbx], rsi
0x14000d3a4  mov     rbx, [rsp+28h+arg_8]
0x14000d3a9  mov     rsi, [rsp+28h+arg_10]
0x14000d3ae  add     rsp, 20h
0x14000d3b2  pop     rdi
0x14000d3b3  retn
```
