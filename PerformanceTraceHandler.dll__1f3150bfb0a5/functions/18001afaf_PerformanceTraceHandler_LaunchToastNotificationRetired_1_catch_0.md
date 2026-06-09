# _PerformanceTraceHandler::LaunchToastNotificationRetired_::_1_::catch$0

- ea: `0x18001afaf`
- end: `0x18001afe5`
- name: `_PerformanceTraceHandler::LaunchToastNotificationRetired_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012790`

## string_xrefs

- `0x18001afc0`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::LaunchToastNotificationRetired_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x13B,
                           (int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001afaf  mov     [rsp+arg_8], rdx
0x18001afb4  push    rbp
0x18001afb5  sub     rsp, 20h
0x18001afb9  mov     rbp, rdx
0x18001afbc  mov     rcx, [rbp+28h]; this
0x18001afc0  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001afc7  mov     edx, 13Bh; void *
0x18001afcc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001afd1  mov     [rbp+30h], eax
0x18001afd4  mov     rax, 0
0x18001afde  add     rsp, 20h
0x18001afe2  pop     rbp
0x18001afe3  retn
```
