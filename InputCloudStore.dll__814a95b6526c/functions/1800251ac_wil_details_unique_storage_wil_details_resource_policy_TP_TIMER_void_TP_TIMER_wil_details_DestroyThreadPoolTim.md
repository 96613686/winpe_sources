# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x1800251ac`
- end: `0x1800251f8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001b648`
- `0x180020510`
- `0x1800206a0`
- `0x180028970`
- `0x1800289ec`
- `0x180028d68`

## callees

- `0x180004dc8`
- `0x180005094`
- `0x18001f364`
- `0x1800251ac`

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
0x1800251ac  mov     [rsp+arg_8], rbx
0x1800251b1  mov     [rsp+arg_10], rsi
0x1800251b6  push    rdi
0x1800251b7  sub     rsp, 20h
0x1800251bb  mov     rdi, [rcx]
0x1800251be  mov     rsi, rdx
0x1800251c1  mov     rbx, rcx
0x1800251c4  test    rdi, rdi
0x1800251c7  jz      short loc_1800251E5
0x1800251c9  lea     rcx, [rsp+28h+arg_0]; this
0x1800251ce  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800251d3  mov     rcx, rdi; pti
0x1800251d6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800251db  lea     rcx, [rsp+28h+arg_0]; this
0x1800251e0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800251e5  mov     [rbx], rsi
0x1800251e8  mov     rbx, [rsp+28h+arg_8]
0x1800251ed  mov     rsi, [rsp+28h+arg_10]
0x1800251f2  add     rsp, 20h
0x1800251f6  pop     rdi
0x1800251f7  retn
```
