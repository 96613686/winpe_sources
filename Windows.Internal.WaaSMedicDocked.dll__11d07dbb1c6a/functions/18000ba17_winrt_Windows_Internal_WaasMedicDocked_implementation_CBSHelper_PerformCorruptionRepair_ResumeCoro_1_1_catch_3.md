# _winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::catch$38

- ea: `0x18000ba17`
- end: `0x18000ba4d`
- name: `_winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair$_ResumeCoro$1_::_1_::catch$38`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a034`

## pseudocode

```c
void __fastcall __noreturn winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::PerformCorruptionRepair__ResumeCoro_1_::_1_::catch_38(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 240);
  *(_WORD *)(v2 + 8) = -1;
  winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<unsigned int>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<unsigned int>,void>::unhandled_exception(v2 - 112);
}

```

## disassembly

```asm
0x18000ba17  mov     [rsp+arg_8], rdx
0x18000ba1c  push    rbp
0x18000ba1d  sub     rsp, 50h
0x18000ba21  mov     rbp, rdx
0x18000ba24  or      eax, 0FFFFFFFFh
0x18000ba27  mov     rcx, [rbp+0F0h]
0x18000ba2e  mov     [rcx+8], ax
0x18000ba32  add     rcx, 0FFFFFFFFFFFFFF90h
0x18000ba36  call    ?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@I@Foundation@Windows@winrt@@PEAVCBSHelper@implementation@WaasMedicDocked@Internal@34@@experimental@std@@U?$IAsyncOperation@I@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<uint>,winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<uint>,void>::unhandled_exception(void)
0x18000ba3c  mov     rax, 0
0x18000ba46  add     rsp, 50h
0x18000ba4a  pop     rbp
0x18000ba4b  retn
```
