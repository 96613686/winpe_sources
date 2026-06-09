# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath_::_1_::catch$12

- ea: `0x18002a658`
- end: `0x18002a691`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath_::_1_::catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a66c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 632),
                           (void *)0xC6,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a658  mov     [rsp+arg_8], rdx
0x18002a65d  push    rbp
0x18002a65e  sub     rsp, 20h
0x18002a662  mov     rbp, rdx
0x18002a665  mov     rcx, [rbp+278h]; this
0x18002a66c  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a673  mov     edx, 0C6h; void *
0x18002a678  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a67d  mov     [rbp+20h], eax
0x18002a680  mov     rax, 0
0x18002a68a  add     rsp, 20h
0x18002a68e  pop     rbp
0x18002a68f  retn
```
