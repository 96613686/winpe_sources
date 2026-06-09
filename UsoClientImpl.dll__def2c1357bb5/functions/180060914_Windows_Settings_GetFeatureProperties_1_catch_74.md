# _Windows::Settings::GetFeatureProperties_::_1_::catch$74

- ea: `0x180060914`
- end: `0x180060952`
- name: `_Windows::Settings::GetFeatureProperties_::_1_::catch$74`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180034148`

## string_xrefs

- `0x180060928`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Settings.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Settings::GetFeatureProperties_::_1_::catch_74(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x174,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
    a4);
  *(_BYTE *)(*(_QWORD *)(a2 + 72) + 16LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180060914  mov     [rsp+arg_8], rdx
0x180060919  push    rbp
0x18006091a  sub     rsp, 20h
0x18006091e  mov     rbp, rdx
0x180060921  mov     rcx, [rbp+0B8h]; this
0x180060928  lea     r8, aCW1SSrcOrchest_5; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006092f  mov     edx, 174h; void *
0x180060934  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180060939  mov     rax, [rbp+48h]
0x18006093d  mov     byte ptr [rax+10h], 0
0x180060941  mov     rax, 0
0x18006094b  add     rsp, 20h
0x18006094f  pop     rbp
0x180060950  retn
```
