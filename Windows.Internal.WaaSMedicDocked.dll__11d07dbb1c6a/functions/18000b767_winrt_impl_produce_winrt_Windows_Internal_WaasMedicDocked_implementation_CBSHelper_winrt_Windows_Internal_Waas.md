# _winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::CanUseWUAsRepairSource_::_1_::catch$0

- ea: `0x18000b767`
- end: `0x18000b793`
- name: `_winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::CanUseWUAsRepairSource_::_1_::catch$0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009f70`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper_winrt::Windows::Internal::WaasMedicDocked::ICBSHelper_::CanUseWUAsRepairSource_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  *(_DWORD *)(a2 + 80) = *(_DWORD *)winrt::to_hresult(a2 + 80);
  return 0;
}

```

## disassembly

```asm
0x18000b767  mov     [rsp+arg_8], rdx
0x18000b76c  push    rbp
0x18000b76d  sub     rsp, 40h
0x18000b771  mov     rbp, rdx
0x18000b774  lea     rcx, [rbp+50h]
0x18000b778  call    ?to_hresult@winrt@@YA?AUhresult@1@XZ; winrt::to_hresult(void)
0x18000b77d  mov     ecx, [rax]
0x18000b77f  mov     [rbp+50h], ecx
0x18000b782  mov     rax, 0
0x18000b78c  add     rsp, 40h
0x18000b790  pop     rbp
0x18000b791  retn
```
