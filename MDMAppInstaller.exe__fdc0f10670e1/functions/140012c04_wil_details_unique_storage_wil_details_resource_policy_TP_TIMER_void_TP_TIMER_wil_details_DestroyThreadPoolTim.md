# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140012c04`
- end: `0x140012c50`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007e1c`
- `0x140007e98`
- `0x140009388`
- `0x140009438`
- `0x14000edec`
- `0x14000f0b8`

## callees

- `0x1400039f0`
- `0x140003dd0`
- `0x14000a360`
- `0x140012c04`

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
0x140012c04  mov     [rsp+arg_8], rbx
0x140012c09  mov     [rsp+arg_10], rsi
0x140012c0e  push    rdi
0x140012c0f  sub     rsp, 20h
0x140012c13  mov     rdi, [rcx]
0x140012c16  mov     rsi, rdx
0x140012c19  mov     rbx, rcx
0x140012c1c  test    rdi, rdi
0x140012c1f  jz      short loc_140012C3D
0x140012c21  lea     rcx, [rsp+28h+arg_0]; this
0x140012c26  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140012c2b  mov     rcx, rdi; pti
0x140012c2e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140012c33  lea     rcx, [rsp+28h+arg_0]; this
0x140012c38  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140012c3d  mov     [rbx], rsi
0x140012c40  mov     rbx, [rsp+28h+arg_8]
0x140012c45  mov     rsi, [rsp+28h+arg_10]
0x140012c4a  add     rsp, 20h
0x140012c4e  pop     rdi
0x140012c4f  retn
```
