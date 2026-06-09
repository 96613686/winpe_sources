# _Windows::Settings::RebootRequiredForCloudSettings_::_1_::catch$1

- ea: `0x1800606ed`
- end: `0x180060721`
- name: `_Windows::Settings::RebootRequiredForCloudSettings_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180034148`

## string_xrefs

- `0x1800606fe`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::RebootRequiredForCloudSettings_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x148,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800606ed  mov     [rsp+arg_8], rdx
0x1800606f2  push    rbp
0x1800606f3  sub     rsp, 20h
0x1800606f7  mov     rbp, rdx
0x1800606fa  mov     rcx, [rbp+48h]; this
0x1800606fe  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180060705  mov     edx, 148h; void *
0x18006070a  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18006070f  nop
0x180060710  mov     rax, 0
0x18006071a  add     rsp, 20h
0x18006071e  pop     rbp
0x18006071f  retn
```
