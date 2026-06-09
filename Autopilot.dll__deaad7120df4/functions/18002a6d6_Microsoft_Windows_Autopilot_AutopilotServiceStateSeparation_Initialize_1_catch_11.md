# _Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize_::_1_::catch$11

- ea: `0x18002a6d6`
- end: `0x18002a70c`
- name: `_Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize_::_1_::catch$11`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a6e7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

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
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a6d6  mov     [rsp+arg_8], rdx
0x18002a6db  push    rbp
0x18002a6dc  sub     rsp, 20h
0x18002a6e0  mov     rbp, rdx
0x18002a6e3  mov     rcx, [rbp+58h]; this
0x18002a6e7  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a6ee  mov     edx, 6Ch ; 'l'; void *
0x18002a6f3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a6f8  mov     [rbp+20h], eax
0x18002a6fb  mov     rax, 0
0x18002a705  add     rsp, 20h
0x18002a709  pop     rbp
0x18002a70a  retn
```
