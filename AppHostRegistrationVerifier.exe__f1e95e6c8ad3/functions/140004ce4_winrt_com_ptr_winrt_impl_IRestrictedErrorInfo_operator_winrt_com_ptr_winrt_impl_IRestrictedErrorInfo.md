# winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)

- ea: `0x140004ce4`
- end: `0x140004d1f`
- name: `??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z`
- size: `59`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004648`
- `0x140007964`

## callees

- `0x140004ce4`
- `0x140007eec`

## pseudocode

```c
__int64 *__fastcall winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rax

  if ( a1 != a2 )
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a1);
    v4 = *a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x140004ce4  mov     [rsp+arg_0], rbx
0x140004ce9  push    rdi
0x140004cea  sub     rsp, 20h
0x140004cee  mov     rdi, rdx
0x140004cf1  mov     rbx, rcx
0x140004cf4  cmp     rcx, rdx
0x140004cf7  jz      short loc_140004D11
0x140004cf9  cmp     qword ptr [rcx], 0
0x140004cfd  jz      short loc_140004D04
0x140004cff  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140004d04  mov     rax, [rdi]
0x140004d07  mov     qword ptr [rdi], 0
0x140004d0e  mov     [rbx], rax
0x140004d11  mov     rax, rbx
0x140004d14  mov     rbx, [rsp+28h+arg_0]
0x140004d19  add     rsp, 20h
0x140004d1d  pop     rdi
0x140004d1e  retn
```
