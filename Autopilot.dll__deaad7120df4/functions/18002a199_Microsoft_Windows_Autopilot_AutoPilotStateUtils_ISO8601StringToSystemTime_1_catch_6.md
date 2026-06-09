# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime_::_1_::catch$6

- ea: `0x18002a199`
- end: `0x18002a1d2`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ISO8601StringToSystemTime_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a1ad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a199  mov     [rsp+arg_8], rdx
0x18002a19e  push    rbp
0x18002a19f  sub     rsp, 20h
0x18002a1a3  mov     rbp, rdx
0x18002a1a6  mov     rcx, [rbp+1B8h]; this
0x18002a1ad  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a1b4  mov     edx, 0CFh; void *
0x18002a1b9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a1be  mov     [rbp+20h], eax
0x18002a1c1  mov     rax, 0
0x18002a1cb  add     rsp, 20h
0x18002a1cf  pop     rbp
0x18002a1d0  retn
```
