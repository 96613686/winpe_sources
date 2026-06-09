# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001ec20`
- end: `0x18001ec6c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009f9c`
- `0x18000a018`
- `0x1800116f0`
- `0x1800117f4`
- `0x180016f08`
- `0x180017130`

## callees

- `0x180006594`
- `0x180006860`
- `0x180014370`
- `0x18001ec20`

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
0x18001ec20  mov     [rsp+arg_8], rbx
0x18001ec25  mov     [rsp+arg_10], rsi
0x18001ec2a  push    rdi
0x18001ec2b  sub     rsp, 20h
0x18001ec2f  mov     rdi, [rcx]
0x18001ec32  mov     rsi, rdx
0x18001ec35  mov     rbx, rcx
0x18001ec38  test    rdi, rdi
0x18001ec3b  jz      short loc_18001EC59
0x18001ec3d  lea     rcx, [rsp+28h+arg_0]; this
0x18001ec42  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ec47  mov     rcx, rdi; pti
0x18001ec4a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001ec4f  lea     rcx, [rsp+28h+arg_0]; this
0x18001ec54  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ec59  mov     [rbx], rsi
0x18001ec5c  mov     rbx, [rsp+28h+arg_8]
0x18001ec61  mov     rsi, [rsp+28h+arg_10]
0x18001ec66  add     rsp, 20h
0x18001ec6a  pop     rdi
0x18001ec6b  retn
```
