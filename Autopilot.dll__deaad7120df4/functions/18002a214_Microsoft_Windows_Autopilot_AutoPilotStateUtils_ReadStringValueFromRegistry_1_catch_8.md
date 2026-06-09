# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry_::_1_::catch$8

- ea: `0x18002a214`
- end: `0x18002a24d`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a228`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry_::_1_::catch_8(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x19B,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a214  mov     [rsp+arg_8], rdx
0x18002a219  push    rbp
0x18002a21a  sub     rsp, 40h
0x18002a21e  mov     rbp, rdx
0x18002a221  mov     rcx, [rbp+88h]; this
0x18002a228  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a22f  mov     edx, 19Bh; void *
0x18002a234  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a239  mov     [rbp+40h], eax
0x18002a23c  mov     rax, 0
0x18002a246  add     rsp, 40h
0x18002a24a  pop     rbp
0x18002a24b  retn
```
