# _PerformanceTraceHandler::LaunchToastNotification_::_1_::catch$12

- ea: `0x18001ae9e`
- end: `0x18001aed7`
- name: `_PerformanceTraceHandler::LaunchToastNotification_::_1_::catch$12`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001aeb2`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::LaunchToastNotification_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0xFA,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001ae9e  mov     [rsp+arg_8], rdx
0x18001aea3  push    rbp
0x18001aea4  sub     rsp, 20h
0x18001aea8  mov     rbp, rdx
0x18001aeab  mov     rcx, [rbp+0A8h]; this
0x18001aeb2  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001aeb9  mov     edx, 0FAh; void *
0x18001aebe  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001aec3  mov     [rbp+20h], eax
0x18001aec6  mov     rax, 0
0x18001aed0  add     rsp, 20h
0x18001aed4  pop     rbp
0x18001aed5  retn
```
