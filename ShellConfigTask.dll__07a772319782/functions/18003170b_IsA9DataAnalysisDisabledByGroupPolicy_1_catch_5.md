# _IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch$5

- ea: `0x18003170b`
- end: `0x180031742`
- name: `_IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch$5`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001d368`

## string_xrefs

- `0x18003171f`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
__int64 __fastcall IsA9DataAnalysisDisabledByGroupPolicy_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0x271,
    (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18003170b  mov     [rsp+arg_8], rdx
0x180031710  push    rbp
0x180031711  sub     rsp, 30h
0x180031715  mov     rbp, rdx
0x180031718  mov     rcx, [rbp+98h]; this
0x18003171f  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180031726  mov     edx, 271h; void *
0x18003172b  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180031730  nop
0x180031731  mov     rax, 0
0x18003173b  add     rsp, 30h
0x18003173f  pop     rbp
0x180031740  retn
```
