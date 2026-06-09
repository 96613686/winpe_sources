# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000aa74`
- end: `0x18000aac0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004cec`
- `0x180004d68`
- `0x180005d3c`
- `0x180005dec`
- `0x180008378`
- `0x18000f720`
- `0x18000fa68`

## callees

- `0x180005920`
- `0x180005fc4`
- `0x180006610`
- `0x18000aa74`

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
0x18000aa74  mov     [rsp+arg_8], rbx
0x18000aa79  mov     [rsp+arg_10], rsi
0x18000aa7e  push    rdi
0x18000aa7f  sub     rsp, 20h
0x18000aa83  mov     rdi, [rcx]
0x18000aa86  mov     rsi, rdx
0x18000aa89  mov     rbx, rcx
0x18000aa8c  test    rdi, rdi
0x18000aa8f  jz      short loc_18000AAAD
0x18000aa91  lea     rcx, [rsp+28h+arg_0]; this
0x18000aa96  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000aa9b  mov     rcx, rdi; pti
0x18000aa9e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000aaa3  lea     rcx, [rsp+28h+arg_0]; this
0x18000aaa8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000aaad  mov     [rbx], rsi
0x18000aab0  mov     rbx, [rsp+28h+arg_8]
0x18000aab5  mov     rsi, [rsp+28h+arg_10]
0x18000aaba  add     rsp, 20h
0x18000aabe  pop     rdi
0x18000aabf  retn
```
