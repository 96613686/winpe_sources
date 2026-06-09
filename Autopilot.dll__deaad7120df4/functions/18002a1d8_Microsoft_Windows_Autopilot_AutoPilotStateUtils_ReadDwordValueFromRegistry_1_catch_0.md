# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry_::_1_::catch$0

- ea: `0x18002a1d8`
- end: `0x18002a20e`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a1e9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a1d8  mov     [rsp+arg_8], rdx
0x18002a1dd  push    rbp
0x18002a1de  sub     rsp, 40h
0x18002a1e2  mov     rbp, rdx
0x18002a1e5  mov     rcx, [rbp+58h]; this
0x18002a1e9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a1f0  mov     edx, 1AAh; void *
0x18002a1f5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a1fa  mov     [rbp+60h], eax
0x18002a1fd  mov     rax, 0
0x18002a207  add     rsp, 40h
0x18002a20b  pop     rbp
0x18002a20c  retn
```
