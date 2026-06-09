# winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)

- ea: `0x180010c28`
- end: `0x180010c63`
- name: `??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z`
- size: `59`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010810`
- `0x1800130d0`

## callees

- `0x180009c74`
- `0x180010c28`

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
0x180010c28  mov     [rsp+arg_0], rbx
0x180010c2d  push    rdi
0x180010c2e  sub     rsp, 20h
0x180010c32  mov     rdi, rdx
0x180010c35  mov     rbx, rcx
0x180010c38  cmp     rcx, rdx
0x180010c3b  jz      short loc_180010C55
0x180010c3d  cmp     qword ptr [rcx], 0
0x180010c41  jz      short loc_180010C48
0x180010c43  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180010c48  mov     rax, [rdi]
0x180010c4b  mov     qword ptr [rdi], 0
0x180010c52  mov     [rbx], rax
0x180010c55  mov     rax, rbx
0x180010c58  mov     rbx, [rsp+28h+arg_0]
0x180010c5d  add     rsp, 20h
0x180010c61  pop     rdi
0x180010c62  retn
```
