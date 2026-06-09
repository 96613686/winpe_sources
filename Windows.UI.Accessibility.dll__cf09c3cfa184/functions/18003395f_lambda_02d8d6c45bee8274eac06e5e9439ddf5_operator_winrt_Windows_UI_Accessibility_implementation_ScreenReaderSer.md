# __lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const___::_1_::catch$3

- ea: `0x18003395f`
- end: `0x180033993`
- name: `__lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const___::_1_::catch$3`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800150c0`

## string_xrefs

- `0x180033970`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\screenreaderservice.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_02d8d6c45bee8274eac06e5e9439ddf5_::operator()_winrt::Windows::UI::Accessibility::implementation::ScreenReaderService::ScreenReaderPositionChangedEventPayload_const___::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 104),
    (void *)0x1A,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\screenreaderservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003395f  mov     [rsp+arg_8], rdx
0x180033964  push    rbp
0x180033965  sub     rsp, 30h
0x180033969  mov     rbp, rdx
0x18003396c  mov     rcx, [rbp+68h]; this
0x180033970  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\accessibletech\\ex"...
0x180033977  mov     edx, 1Ah; void *
0x18003397c  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180033981  nop
0x180033982  mov     rax, 0
0x18003398c  add     rsp, 30h
0x180033990  pop     rbp
0x180033991  retn
```
