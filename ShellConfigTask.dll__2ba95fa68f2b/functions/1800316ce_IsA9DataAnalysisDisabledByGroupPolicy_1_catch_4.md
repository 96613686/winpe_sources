# _IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch$4

- ea: `0x1800316ce`
- end: `0x180031705`
- name: `_IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch$4`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001d368`

## string_xrefs

- `0x1800316e2`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
__int64 __fastcall IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0x269,
    (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800316ce  mov     [rsp+arg_8], rdx
0x1800316d3  push    rbp
0x1800316d4  sub     rsp, 30h
0x1800316d8  mov     rbp, rdx
0x1800316db  mov     rcx, [rbp+98h]; this
0x1800316e2  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800316e9  mov     edx, 269h; void *
0x1800316ee  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800316f3  nop
0x1800316f4  mov     rax, 0
0x1800316fe  add     rsp, 30h
0x180031702  pop     rbp
0x180031703  retn
```
