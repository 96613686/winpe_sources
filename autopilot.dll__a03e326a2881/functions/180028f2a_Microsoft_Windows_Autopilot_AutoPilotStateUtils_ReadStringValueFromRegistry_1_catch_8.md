# _Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry_::_1_::catch$8

- ea: `0x180028f2a`
- end: `0x180028f63`
- name: `_Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry_::_1_::catch$8`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028f3e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028f2a  mov     [rsp+arg_8], rdx
0x180028f2f  push    rbp
0x180028f30  sub     rsp, 40h
0x180028f34  mov     rbp, rdx
0x180028f37  mov     rcx, [rbp+88h]; this
0x180028f3e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028f45  mov     edx, 19Bh; void *
0x180028f4a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028f4f  mov     [rbp+40h], eax
0x180028f52  mov     rax, 0
0x180028f5c  add     rsp, 40h
0x180028f60  pop     rbp
0x180028f61  retn
```
