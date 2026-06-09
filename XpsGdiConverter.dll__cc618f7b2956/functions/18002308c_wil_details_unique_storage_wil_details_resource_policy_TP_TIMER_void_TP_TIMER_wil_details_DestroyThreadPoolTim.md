# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18002308c`
- end: `0x1800230d8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001db0c`
- `0x18001dbbc`
- `0x18001fdb4`
- `0x18001fe6c`
- `0x18001ff58`
- `0x1800204ac`

## callees

- `0x18000a894`
- `0x18000ab7c`
- `0x18001e5ec`
- `0x18002308c`

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
0x18002308c  mov     [rsp+arg_8], rbx
0x180023091  mov     [rsp+arg_10], rsi
0x180023096  push    rdi
0x180023097  sub     rsp, 20h
0x18002309b  mov     rdi, [rcx]
0x18002309e  mov     rsi, rdx
0x1800230a1  mov     rbx, rcx
0x1800230a4  test    rdi, rdi
0x1800230a7  jz      short loc_1800230C5
0x1800230a9  lea     rcx, [rsp+28h+arg_0]; this
0x1800230ae  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800230b3  mov     rcx, rdi; pti
0x1800230b6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800230bb  lea     rcx, [rsp+28h+arg_0]; this
0x1800230c0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800230c5  mov     [rbx], rsi
0x1800230c8  mov     rbx, [rsp+28h+arg_8]
0x1800230cd  mov     rsi, [rsp+28h+arg_10]
0x1800230d2  add     rsp, 20h
0x1800230d6  pop     rdi
0x1800230d7  retn
```
