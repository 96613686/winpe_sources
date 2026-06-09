# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x180008a00`
- end: `0x180008a21`
- name: `?QueryInterface@?$implements_delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@V_lambda_574d5987c64a6b3f18218f4a51f47ca3_@@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800098e8`

## pseudocode

```c
__int64 __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::QueryInterface(
        int a1,
        int a2,
        int a3)
{
  return winrt::impl::implements_delegate_base::query_interface(
           a1 + 8,
           a2,
           a3,
           a1,
           (__int64)&winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>>);
}

```

## disassembly

```asm
0x180008a00  sub     rsp, 38h
0x180008a04  mov     r9, rcx
0x180008a07  lea     rax, ??$guid_v@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>>
0x180008a0e  add     rcx, 8
0x180008a12  mov     [rsp+38h+var_18], rax
0x180008a17  call    ?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z; winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)
0x180008a1c  add     rsp, 38h
0x180008a20  retn
```
