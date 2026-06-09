# _PerformanceTraceHandler::LaunchToastNotificationBeginning_::_1_::catch$1

- ea: `0x18001aedd`
- end: `0x18001af13`
- name: `_PerformanceTraceHandler::LaunchToastNotificationBeginning_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001aeee`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::LaunchToastNotificationBeginning_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x12C,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001aedd  mov     [rsp+arg_8], rdx
0x18001aee2  push    rbp
0x18001aee3  sub     rsp, 20h
0x18001aee7  mov     rbp, rdx
0x18001aeea  mov     rcx, [rbp+28h]; this
0x18001aeee  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001aef5  mov     edx, 12Ch; void *
0x18001aefa  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001aeff  mov     [rbp+38h], eax
0x18001af02  mov     rax, 0
0x18001af0c  add     rsp, 20h
0x18001af10  pop     rbp
0x18001af11  retn
```
