# _winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$0

- ea: `0x18000b97b`
- end: `0x18000b9a9`
- name: `_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000689c`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)(a2 + 144) = *(_QWORD *)(a2 + 240) + 16LL;
  return wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(*(__int64 **)(a2 + 144));
}

```

## disassembly

```asm
0x18000b97b  push    rbp
0x18000b97d  sub     rsp, 20h
0x18000b981  mov     rbp, rdx
0x18000b984  mov     eax, 10h
0x18000b989  add     rax, [rbp+0F0h]
0x18000b990  mov     [rbp+90h], rax
0x18000b997  mov     rcx, [rbp+90h]
0x18000b99e  call    ??1?$com_ptr_t@UICbsSession7@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(void)
0x18000b9a3  add     rsp, 20h
0x18000b9a7  pop     rbp
0x18000b9a8  retn
```
