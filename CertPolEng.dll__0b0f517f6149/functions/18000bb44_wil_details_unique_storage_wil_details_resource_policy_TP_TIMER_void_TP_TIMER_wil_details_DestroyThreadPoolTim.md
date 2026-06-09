# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000bb44`
- end: `0x18000bb90`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b664`
- `0x18000b6cc`
- `0x18000b8bc`
- `0x18000b9b0`
- `0x180018a84`

## callees

- `0x18000bb00`
- `0x18000bb20`
- `0x18000bb44`
- `0x18000f910`

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
0x18000bb44  mov     [rsp+arg_8], rbx
0x18000bb49  mov     [rsp+arg_10], rsi
0x18000bb4e  push    rdi
0x18000bb4f  sub     rsp, 20h
0x18000bb53  mov     rdi, [rcx]
0x18000bb56  mov     rsi, rdx
0x18000bb59  mov     rbx, rcx
0x18000bb5c  test    rdi, rdi
0x18000bb5f  jz      short loc_18000BB7D
0x18000bb61  lea     rcx, [rsp+28h+arg_0]; this
0x18000bb66  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000bb6b  mov     rcx, rdi; pti
0x18000bb6e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000bb73  lea     rcx, [rsp+28h+arg_0]; this
0x18000bb78  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000bb7d  mov     [rbx], rsi
0x18000bb80  mov     rbx, [rsp+28h+arg_8]
0x18000bb85  mov     rsi, [rsp+28h+arg_10]
0x18000bb8a  add     rsp, 20h
0x18000bb8e  pop     rdi
0x18000bb8f  retn
```
