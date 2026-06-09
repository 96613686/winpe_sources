# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180016f34`
- end: `0x180016f80`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015790`
- `0x180016e40`
- `0x180016fe0`
- `0x180017060`
- `0x18002343c`
- `0x1800234b8`

## callees

- `0x180016f34`
- `0x180023f24`
- `0x18002426c`
- `0x180024cb0`

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
0x180016f34  mov     [rsp+arg_8], rbx
0x180016f39  mov     [rsp+arg_10], rsi
0x180016f3e  push    rdi
0x180016f3f  sub     rsp, 20h
0x180016f43  mov     rdi, [rcx]
0x180016f46  mov     rsi, rdx
0x180016f49  mov     rbx, rcx
0x180016f4c  test    rdi, rdi
0x180016f4f  jz      short loc_180016F6D
0x180016f51  lea     rcx, [rsp+28h+arg_0]; this
0x180016f56  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016f5b  mov     rcx, rdi; pti
0x180016f5e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180016f63  lea     rcx, [rsp+28h+arg_0]; this
0x180016f68  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180016f6d  mov     [rbx], rsi
0x180016f70  mov     rbx, [rsp+28h+arg_8]
0x180016f75  mov     rsi, [rsp+28h+arg_10]
0x180016f7a  add     rsp, 20h
0x180016f7e  pop     rdi
0x180016f7f  retn
```
