# _WhesvcUXHandler::LaunchToastNotificationHelper_::_1_::catch$9

- ea: `0x18001b202`
- end: `0x18001b23b`
- name: `_WhesvcUXHandler::LaunchToastNotificationHelper_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001b213`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::LaunchToastNotificationHelper_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x114,
                            (int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18001b202  mov     [rsp+arg_8], rdx
0x18001b207  push    rbp
0x18001b208  sub     rsp, 20h
0x18001b20c  mov     rbp, rdx
0x18001b20f  mov     rcx, [rbp+78h]; this
0x18001b213  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x18001b21a  mov     edx, 114h; void *
0x18001b21f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001b224  mov     [rbp+80h], eax
0x18001b22a  mov     rax, 0
0x18001b234  add     rsp, 20h
0x18001b238  pop     rbp
0x18001b239  retn
```
