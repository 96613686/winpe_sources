# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime_::_1_::catch$6

- ea: `0x180028eaf`
- end: `0x180028ee8`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028ec3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 440),
                           (void *)0xCF,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028eaf  mov     [rsp+arg_8], rdx
0x180028eb4  push    rbp
0x180028eb5  sub     rsp, 20h
0x180028eb9  mov     rbp, rdx
0x180028ebc  mov     rcx, [rbp+1B8h]; this
0x180028ec3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028eca  mov     edx, 0CFh; void *
0x180028ecf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028ed4  mov     [rbp+20h], eax
0x180028ed7  mov     rax, 0
0x180028ee1  add     rsp, 20h
0x180028ee5  pop     rbp
0x180028ee6  retn
```
