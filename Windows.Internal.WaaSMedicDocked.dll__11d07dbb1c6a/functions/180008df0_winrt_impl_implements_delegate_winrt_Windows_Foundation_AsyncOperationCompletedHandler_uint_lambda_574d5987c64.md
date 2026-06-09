# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::Release(void)

- ea: `0x180008df0`
- end: `0x180008e56`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@V_lambda_574d5987c64a6b3f18218f4a51f47ca3_@@@impl@winrt@@UEAAIXZ`
- size: `102`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001940`
- `0x180008df0`
- `0x180009274`
- `0x18000a014`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180008e4f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180008e4f`

## pseudocode

```c
__int64 __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::Release(
        __int64 *a1)
{
  unsigned int v2; // edi

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 1));
  if ( !v2 && a1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    if ( a1[2] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 2);
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180008df0  mov     [rsp+arg_0], rbx
0x180008df5  push    rdi
0x180008df6  sub     rsp, 20h
0x180008dfa  mov     rbx, rcx
0x180008dfd  add     rcx, 8; this
0x180008e01  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x180008e06  mov     edi, eax
0x180008e08  test    eax, eax
0x180008e0a  jnz     short loc_180008E3E
0x180008e0c  test    rbx, rbx
0x180008e0f  jz      short loc_180008E3E
0x180008e11  or      edx, 0FFFFFFFFh
0x180008e14  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008e1c  sub     edx, 1
0x180008e1f  jnz     short loc_180008E4B
0x180008e21  nop
0x180008e22  lea     rcx, [rbx+10h]
0x180008e26  cmp     qword ptr [rcx], 0
0x180008e2a  jz      short loc_180008E31
0x180008e2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180008e31  mov     edx, 28h ; '('; unsigned __int64
0x180008e36  mov     rcx, rbx; void *
0x180008e39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008e3e  mov     rbx, [rsp+28h+arg_0]
0x180008e43  mov     eax, edi
0x180008e45  add     rsp, 20h
0x180008e49  pop     rdi
0x180008e4a  retn
0x180008e4b  test    edx, edx
0x180008e4d  jns     short loc_180008E22
0x180008e4f  call    cs:__imp_abort
```
