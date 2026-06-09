# _winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::catch$20

- ea: `0x18000b917`
- end: `0x18000b943`
- name: `_winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::catch$20`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009f70`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::PerformCorruptionRepair_::_1_::catch_20(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 80) = *(_DWORD *)winrt::to_hresult(a2 + 80);
  return 0;
}

```

## disassembly

```asm
0x18000b917  mov     [rsp+arg_8], rdx
0x18000b91c  push    rbp
0x18000b91d  sub     rsp, 20h
0x18000b921  mov     rbp, rdx
0x18000b924  lea     rcx, [rbp+50h]
0x18000b928  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000b92d  mov     ecx, [rax]
0x18000b92f  mov     [rbp+50h], ecx
0x18000b932  mov     rax, 0
0x18000b93c  add     rsp, 20h
0x18000b940  pop     rbp
0x18000b941  retn
```
