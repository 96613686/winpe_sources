# winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)

- ea: `0x18000a9dc`
- end: `0x18000aa17`
- name: `??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z`
- size: `59`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f40`
- `0x18000fa50`

## callees

- `0x18000750c`
- `0x18000a9dc`

## pseudocode

```c
__int64 *__fastcall winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rax

  if ( a1 != a2 )
  {
    if ( *a1 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
    v4 = *a2;
    *a2 = 0;
    *a1 = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a9dc  mov     [rsp+arg_0], rbx
0x18000a9e1  push    rdi
0x18000a9e2  sub     rsp, 20h
0x18000a9e6  mov     rdi, rdx
0x18000a9e9  mov     rbx, rcx
0x18000a9ec  cmp     rcx, rdx
0x18000a9ef  jz      short loc_18000AA09
0x18000a9f1  cmp     qword ptr [rcx], 0
0x18000a9f5  jz      short loc_18000A9FC
0x18000a9f7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a9fc  mov     rax, [rdi]
0x18000a9ff  mov     qword ptr [rdi], 0
0x18000aa06  mov     [rbx], rax
0x18000aa09  mov     rax, rbx
0x18000aa0c  mov     rbx, [rsp+28h+arg_0]
0x18000aa11  add     rsp, 20h
0x18000aa15  pop     rdi
0x18000aa16  retn
```
