# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)

- ea: `0x18000bb08`
- end: `0x18000bb54`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z`
- size: `76`
- prototype: `void __fastcall(struct _TP_WORK **, struct _TP_WORK *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b7d8`
- `0x18000b910`
- `0x18000ce84`

## callees

- `0x180005318`
- `0x180005a38`
- `0x18000b63c`
- `0x18000bb08`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        struct _TP_WORK **a1,
        struct _TP_WORK *a2)
{
  struct _TP_WORK *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    wil::details::DestroyThreadPoolWork<0>::Destroy(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000bb08  mov     [rsp+arg_8], rbx
0x18000bb0d  mov     [rsp+arg_10], rsi
0x18000bb12  push    rdi
0x18000bb13  sub     rsp, 20h
0x18000bb17  mov     rdi, [rcx]
0x18000bb1a  mov     rsi, rdx
0x18000bb1d  mov     rbx, rcx
0x18000bb20  test    rdi, rdi
0x18000bb23  jz      short loc_18000BB41
0x18000bb25  lea     rcx, [rsp+28h+arg_0]; this
0x18000bb2a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000bb2f  mov     rcx, rdi
0x18000bb32  call    ?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAXPEAU_TP_WORK@@@Z; wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *)
0x18000bb37  lea     rcx, [rsp+28h+arg_0]; this
0x18000bb3c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000bb41  mov     [rbx], rsi
0x18000bb44  mov     rbx, [rsp+28h+arg_8]
0x18000bb49  mov     rsi, [rsp+28h+arg_10]
0x18000bb4e  add     rsp, 20h
0x18000bb52  pop     rdi
0x18000bb53  retn
```
