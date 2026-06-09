# _Windows::Settings::GetAllFeatureProperties_::_1_::catch$92

- ea: `0x180060837`
- end: `0x180060875`
- name: `_Windows::Settings::GetAllFeatureProperties_::_1_::catch$92`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180034148`

## string_xrefs

- `0x18006084b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::GetAllFeatureProperties_::_1_::catch_92(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 296),
    (void *)0x15F,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  *(_BYTE *)(*(_QWORD *)(a2 + 80) + 16LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180060837  mov     [rsp+arg_8], rdx
0x18006083c  push    rbp
0x18006083d  sub     rsp, 20h
0x180060841  mov     rbp, rdx
0x180060844  mov     rcx, [rbp+128h]; this
0x18006084b  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180060852  mov     edx, 15Fh; void *
0x180060857  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18006085c  mov     rax, [rbp+50h]
0x180060860  mov     byte ptr [rax+10h], 0
0x180060864  mov     rax, 0
0x18006086e  add     rsp, 20h
0x180060872  pop     rbp
0x180060873  retn
```
