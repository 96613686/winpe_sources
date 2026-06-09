# _Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask_::_1_::catch$4

- ea: `0x180028b76`
- end: `0x180028bac`
- name: `_Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028b87`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x78,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028b76  mov     [rsp+arg_8], rdx
0x180028b7b  push    rbp
0x180028b7c  sub     rsp, 20h
0x180028b80  mov     rbp, rdx
0x180028b83  mov     rcx, [rbp+28h]; this
0x180028b87  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028b8e  mov     edx, 78h ; 'x'; void *
0x180028b93  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028b98  mov     [rbp+38h], eax
0x180028b9b  mov     rax, 0
0x180028ba5  add     rsp, 20h
0x180028ba9  pop     rbp
0x180028baa  retn
```
