# _winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$2

- ea: `0x18000b9e3`
- end: `0x18000ba11`
- name: `_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::dtor$2`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000689c`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)(a2 + 160) = *(_QWORD *)(a2 + 240) + 72LL;
  return wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(*(__int64 **)(a2 + 160));
}

```

## disassembly

```asm
0x18000b9e3  push    rbp
0x18000b9e5  sub     rsp, 20h
0x18000b9e9  mov     rbp, rdx
0x18000b9ec  mov     eax, 48h ; 'H'
0x18000b9f1  add     rax, [rbp+0F0h]
0x18000b9f8  mov     [rbp+0A0h], rax
0x18000b9ff  mov     rcx, [rbp+0A0h]
0x18000ba06  call    ??1?$com_ptr_t@UICbsSession7@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICbsSession7,wil::err_returncode_policy>::~com_ptr_t<ICbsSession7,wil::err_returncode_policy>(void)
0x18000ba0b  add     rsp, 20h
0x18000ba0f  pop     rbp
0x18000ba10  retn
```
