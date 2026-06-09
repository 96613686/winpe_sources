# _QueryPerUserIsA9DataAnalysisDisabledByPolicy_::_1_::catch$26

- ea: `0x1800317b0`
- end: `0x1800317e7`
- name: `_QueryPerUserIsA9DataAnalysisDisabledByPolicy_::_1_::catch$26`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001d368`

## string_xrefs

- `0x1800317c4`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
__int64 __fastcall QueryPerUserIsA9DataAnalysisDisabledByPolicy_::_1_::catch_26(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x24F,
    (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800317b0  mov     [rsp+arg_8], rdx
0x1800317b5  push    rbp
0x1800317b6  sub     rsp, 30h
0x1800317ba  mov     rbp, rdx
0x1800317bd  mov     rcx, [rbp+0B8h]; this
0x1800317c4  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800317cb  mov     edx, 24Fh; void *
0x1800317d0  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800317d5  nop
0x1800317d6  mov     rax, 0
0x1800317e0  add     rsp, 30h
0x1800317e4  pop     rbp
0x1800317e5  retn
```
