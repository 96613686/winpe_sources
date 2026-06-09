# _WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton_::_1_::catch$21

- ea: `0x18001b2ad`
- end: `0x18001b2e6`
- name: `_WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton_::_1_::catch$21`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001b2c1`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton_::_1_::catch_21(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0xEF,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001b2ad  mov     [rsp+arg_8], rdx
0x18001b2b2  push    rbp
0x18001b2b3  sub     rsp, 40h
0x18001b2b7  mov     rbp, rdx
0x18001b2ba  mov     rcx, [rbp+0D8h]; this
0x18001b2c1  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x18001b2c8  mov     edx, 0EFh; void *
0x18001b2cd  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001b2d2  mov     [rbp+50h], eax
0x18001b2d5  mov     rax, 0
0x18001b2df  add     rsp, 40h
0x18001b2e3  pop     rbp
0x18001b2e4  retn
```
