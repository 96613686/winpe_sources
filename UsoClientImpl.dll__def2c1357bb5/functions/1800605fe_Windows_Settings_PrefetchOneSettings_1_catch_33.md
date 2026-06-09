# _Windows::Settings::PrefetchOneSettings_::_1_::catch$33

- ea: `0x1800605fe`
- end: `0x180060635`
- name: `_Windows::Settings::PrefetchOneSettings_::_1_::catch$33`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180034148`

## string_xrefs

- `0x180060612`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::PrefetchOneSettings_::_1_::catch_33(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 168),
    (void *)0x12D,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800605fe  mov     [rsp+arg_8], rdx
0x180060603  push    rbp
0x180060604  sub     rsp, 30h
0x180060608  mov     rbp, rdx
0x18006060b  mov     rcx, [rbp+0A8h]; this
0x180060612  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180060619  mov     edx, 12Dh; void *
0x18006061e  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180060623  nop
0x180060624  mov     rax, 0
0x18006062e  add     rsp, 30h
0x180060632  pop     rbp
0x180060633  retn
```
