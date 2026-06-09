# ?QueryInterface@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z

- ea: `0x180009f40`
- end: `0x180009f61`
- name: `?QueryInterface@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@UEAAHAEBUguid@3@PEAPEAX@Z`
- size: `33`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f144`

## pseudocode

```c
__int64 __fastcall _QueryInterface___implements_delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__UEAAHAEBUguid_3_PEAPEAX_Z(
        int a1,
        int a2,
        int a3)
{
  return winrt::impl::implements_delegate_base::query_interface(
           a1 + 8,
           a2,
           a3,
           a1,
           (__int64)winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>);
}

```

## disassembly

```asm
0x180009f40  sub     rsp, 38h
0x180009f44  mov     r9, rcx
0x180009f47  lea     rax, ??$guid_v@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>
0x180009f4e  add     rcx, 8
0x180009f52  mov     [rsp+38h+var_18], rax
0x180009f57  call    ?query_interface@implements_delegate_base@impl@winrt@@QEAAIAEBUguid@3@PEAPEAXPEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@23@0@Z; winrt::impl::implements_delegate_base::query_interface(winrt::guid const &,void * *,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *,winrt::guid const &)
0x180009f5c  add     rsp, 38h
0x180009f60  retn
```
