# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize_::_1_::catch$11

- ea: `0x1800293ec`
- end: `0x180029422`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize_::_1_::catch$11`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x1800293fd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize_::_1_::catch_11(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800293ec  mov     [rsp+arg_8], rdx
0x1800293f1  push    rbp
0x1800293f2  sub     rsp, 20h
0x1800293f6  mov     rbp, rdx
0x1800293f9  mov     rcx, [rbp+58h]; this
0x1800293fd  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029404  mov     edx, 6Ch ; 'l'; void *
0x180029409  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002940e  mov     [rbp+20h], eax
0x180029411  mov     rax, 0
0x18002941b  add     rsp, 20h
0x18002941f  pop     rbp
0x180029420  retn
```
