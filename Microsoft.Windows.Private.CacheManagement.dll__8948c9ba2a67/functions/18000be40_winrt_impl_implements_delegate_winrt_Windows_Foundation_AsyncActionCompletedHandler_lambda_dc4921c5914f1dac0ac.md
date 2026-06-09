# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::QueryInterface(winrt::guid const &,void * *)

- ea: `0x18000be40`
- end: `0x18000be61`
- name: `?QueryInterface@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e750`

## pseudocode

```c
__int64 __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::QueryInterface(
        int a1,
        int a2,
        int a3)
{
  return winrt::impl::implements_delegate_base::query_interface(
           a1 + 8,
           a2,
           a3,
           a1,
           (__int64)&winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>);
}

```

## disassembly

```asm
0x18000be40  sub     rsp, 38h
0x18000be44  mov     r9, rcx
0x18000be47  lea     rax, ??$guid_v@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>
0x18000be4e  add     rcx, 8
0x18000be52  mov     [rsp+38h+var_18], rax
0x18000be57  call    ?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z; winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)
0x18000be5c  add     rsp, 38h
0x18000be60  retn
```
