# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180006fac`
- end: `0x180006ffa`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007334`
- `0x1800097c0`

## callees

- `0x180006fac`
- `0x1800073b0`
- `0x18000ac30`
- `0x18000aec0`

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
0x180006fac  mov     [rsp+arg_8], rbx
0x180006fb1  mov     [rsp+arg_10], rsi
0x180006fb6  push    rdi
0x180006fb7  sub     rsp, 20h
0x180006fbb  mov     rdi, [rcx]
0x180006fbe  mov     rsi, rdx
0x180006fc1  mov     rbx, rcx
0x180006fc4  test    rdi, rdi
0x180006fc7  jnz     short loc_180006FDC
0x180006fc9  mov     [rbx], rsi
0x180006fcc  mov     rbx, [rsp+28h+arg_8]
0x180006fd1  mov     rsi, [rsp+28h+arg_10]
0x180006fd6  add     rsp, 20h
0x180006fda  pop     rdi
0x180006fdb  retn
0x180006fdc  lea     rcx, [rsp+28h+arg_0]; this
0x180006fe1  call    ??0last_error_context@wil@@QEAA@XZ
0x180006fe6  mov     rcx, rdi; pti
0x180006fe9  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z
0x180006fee  lea     rcx, [rsp+28h+arg_0]; this
0x180006ff3  call    ??1last_error_context@wil@@QEAA@XZ
0x180006ff8  jmp     short loc_180006FC9
```
