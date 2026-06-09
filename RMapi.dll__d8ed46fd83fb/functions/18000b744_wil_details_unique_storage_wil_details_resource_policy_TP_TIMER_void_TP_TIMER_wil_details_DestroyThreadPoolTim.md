# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000b744`
- end: `0x18000b790`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800119a8`
- `0x180011a58`
- `0x180014148`
- `0x180014250`
- `0x18001432c`
- `0x18001473c`
- `0x18001eea8`
- `0x18002056c`
- `0x1800228dc`
- `0x1800233a4`

## callees

- `0x180006630`
- `0x180009098`
- `0x18000b744`
- `0x180011f64`

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
0x18000b744  mov     [rsp+arg_8], rbx
0x18000b749  mov     [rsp+arg_10], rsi
0x18000b74e  push    rdi
0x18000b74f  sub     rsp, 20h
0x18000b753  mov     rdi, [rcx]
0x18000b756  mov     rsi, rdx
0x18000b759  mov     rbx, rcx
0x18000b75c  test    rdi, rdi
0x18000b75f  jz      short loc_18000B77D
0x18000b761  lea     rcx, [rsp+28h+arg_0]; this
0x18000b766  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000b76b  mov     rcx, rdi; pti
0x18000b76e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000b773  lea     rcx, [rsp+28h+arg_0]; this
0x18000b778  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b77d  mov     [rbx], rsi
0x18000b780  mov     rbx, [rsp+28h+arg_8]
0x18000b785  mov     rsi, [rsp+28h+arg_10]
0x18000b78a  add     rsp, 20h
0x18000b78e  pop     rdi
0x18000b78f  retn
```
