# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000ae20`
- end: `0x18000ae6c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002dcc`
- `0x180002e48`
- `0x180003e88`
- `0x180003f38`
- `0x180007bec`
- `0x180007d50`

## callees

- `0x180003a24`
- `0x180004128`
- `0x180004820`
- `0x18000ae20`

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
0x18000ae20  mov     [rsp+arg_8], rbx
0x18000ae25  mov     [rsp+arg_10], rsi
0x18000ae2a  push    rdi
0x18000ae2b  sub     rsp, 20h
0x18000ae2f  mov     rdi, [rcx]
0x18000ae32  mov     rsi, rdx
0x18000ae35  mov     rbx, rcx
0x18000ae38  test    rdi, rdi
0x18000ae3b  jz      short loc_18000AE59
0x18000ae3d  lea     rcx, [rsp+28h+arg_0]; this
0x18000ae42  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ae47  mov     rcx, rdi; pti
0x18000ae4a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000ae4f  lea     rcx, [rsp+28h+arg_0]; this
0x18000ae54  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ae59  mov     [rbx], rsi
0x18000ae5c  mov     rbx, [rsp+28h+arg_8]
0x18000ae61  mov     rsi, [rsp+28h+arg_10]
0x18000ae66  add     rsp, 20h
0x18000ae6a  pop     rdi
0x18000ae6b  retn
```
