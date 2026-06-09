# _PerformanceTraceHandler::LaunchToastNotificationError_::_1_::catch$1

- ea: `0x18001af19`
- end: `0x18001af4f`
- name: `_PerformanceTraceHandler::LaunchToastNotificationError_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001af2a`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::LaunchToastNotificationError_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x134,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001af19  mov     [rsp+arg_8], rdx
0x18001af1e  push    rbp
0x18001af1f  sub     rsp, 20h
0x18001af23  mov     rbp, rdx
0x18001af26  mov     rcx, [rbp+28h]; this
0x18001af2a  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001af31  mov     edx, 134h; void *
0x18001af36  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001af3b  mov     [rbp+38h], eax
0x18001af3e  mov     rax, 0
0x18001af48  add     rsp, 20h
0x18001af4c  pop     rbp
0x18001af4d  retn
```
