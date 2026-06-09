# _Windows::Settings::RegisterDynamicInstalledProducts_::_1_::catch$66

- ea: `0x180060481`
- end: `0x1800604b8`
- name: `_Windows::Settings::RegisterDynamicInstalledProducts_::_1_::catch$66`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180034148`

## string_xrefs

- `0x180060495`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::RegisterDynamicInstalledProducts_::_1_::catch_66(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0xD2,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180060481  mov     [rsp+arg_8], rdx
0x180060486  push    rbp
0x180060487  sub     rsp, 40h
0x18006048b  mov     rbp, rdx
0x18006048e  mov     rcx, [rbp+1E8h]; this
0x180060495  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006049c  mov     edx, 0D2h; void *
0x1800604a1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800604a6  nop
0x1800604a7  mov     rax, 0
0x1800604b1  add     rsp, 40h
0x1800604b5  pop     rbp
0x1800604b6  retn
```
