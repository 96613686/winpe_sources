# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch$8

- ea: `0x1800293ad`
- end: `0x1800293e6`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x1800293c1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0xB4,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800293ad  mov     [rsp+arg_8], rdx
0x1800293b2  push    rbp
0x1800293b3  sub     rsp, 20h
0x1800293b7  mov     rbp, rdx
0x1800293ba  mov     rcx, [rbp+88h]; this
0x1800293c1  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800293c8  mov     edx, 0B4h; void *
0x1800293cd  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800293d2  mov     [rbp+20h], eax
0x1800293d5  mov     rax, 0
0x1800293df  add     rsp, 20h
0x1800293e3  pop     rbp
0x1800293e4  retn
```
