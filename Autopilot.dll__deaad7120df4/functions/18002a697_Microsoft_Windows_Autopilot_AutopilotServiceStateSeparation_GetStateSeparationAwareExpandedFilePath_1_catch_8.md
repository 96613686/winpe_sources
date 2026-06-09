# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch$8

- ea: `0x18002a697`
- end: `0x18002a6d0`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a6ab`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0xB4,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a697  mov     [rsp+arg_8], rdx
0x18002a69c  push    rbp
0x18002a69d  sub     rsp, 20h
0x18002a6a1  mov     rbp, rdx
0x18002a6a4  mov     rcx, [rbp+88h]; this
0x18002a6ab  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a6b2  mov     edx, 0B4h; void *
0x18002a6b7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a6bc  mov     [rbp+20h], eax
0x18002a6bf  mov     rax, 0
0x18002a6c9  add     rsp, 20h
0x18002a6cd  pop     rbp
0x18002a6ce  retn
```
