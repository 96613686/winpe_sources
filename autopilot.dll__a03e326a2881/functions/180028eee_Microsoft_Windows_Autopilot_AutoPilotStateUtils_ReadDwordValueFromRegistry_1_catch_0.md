# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry_::_1_::catch$0

- ea: `0x180028eee`
- end: `0x180028f24`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028eff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x1AA,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028eee  mov     [rsp+arg_8], rdx
0x180028ef3  push    rbp
0x180028ef4  sub     rsp, 40h
0x180028ef8  mov     rbp, rdx
0x180028efb  mov     rcx, [rbp+58h]; this
0x180028eff  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028f06  mov     edx, 1AAh; void *
0x180028f0b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028f10  mov     [rbp+60h], eax
0x180028f13  mov     rax, 0
0x180028f1d  add     rsp, 40h
0x180028f21  pop     rbp
0x180028f22  retn
```
