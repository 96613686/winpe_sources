# wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)

- ea: `0x18000ddb0`
- end: `0x18000ddfc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c4a0`
- `0x18000d34c`

## callees

- `0x180004af8`
- `0x180005240`
- `0x18000c678`
- `0x18000ddb0`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  struct wil::details::wnf_subscription_state_base *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::delete_wnf_subscription_state(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000ddb0  mov     [rsp+arg_8], rbx
0x18000ddb5  mov     [rsp+arg_10], rsi
0x18000ddba  push    rdi
0x18000ddbb  sub     rsp, 20h
0x18000ddbf  mov     rdi, [rcx]
0x18000ddc2  mov     rsi, rdx
0x18000ddc5  mov     rbx, rcx
0x18000ddc8  test    rdi, rdi
0x18000ddcb  jz      short loc_18000DDE9
0x18000ddcd  lea     rcx, [rsp+28h+arg_0]; this
0x18000ddd2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ddd7  mov     rcx, rdi; this
0x18000ddda  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x18000dddf  lea     rcx, [rsp+28h+arg_0]; this
0x18000dde4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dde9  mov     [rbx], rsi
0x18000ddec  mov     rbx, [rsp+28h+arg_8]
0x18000ddf1  mov     rsi, [rsp+28h+arg_10]
0x18000ddf6  add     rsp, 20h
0x18000ddfa  pop     rdi
0x18000ddfb  retn
```
