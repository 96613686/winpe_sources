# _Windows::Settings::RefreshSettings_::_1_::catch$104

- ea: `0x1800603d8`
- end: `0x18006040f`
- name: `_Windows::Settings::RefreshSettings_::_1_::catch$104`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180034148`

## string_xrefs

- `0x1800603ec`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::RefreshSettings_::_1_::catch_104(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 712),
    (void *)0xAD,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800603d8  mov     [rsp+arg_8], rdx
0x1800603dd  push    rbp
0x1800603de  sub     rsp, 30h
0x1800603e2  mov     rbp, rdx
0x1800603e5  mov     rcx, [rbp+2C8h]; this
0x1800603ec  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800603f3  mov     edx, 0ADh; void *
0x1800603f8  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800603fd  nop
0x1800603fe  mov     rax, 0
0x180060408  add     rsp, 30h
0x18006040c  pop     rbp
0x18006040d  retn
```
