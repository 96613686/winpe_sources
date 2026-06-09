# _Microsoft::Windows::Autopilot::GetJsonFromRegistry_::_1_::catch$18

- ea: `0x180029b62`
- end: `0x180029b9b`
- name: `_Microsoft::Windows::Autopilot::GetJsonFromRegistry_::_1_::catch$18`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x180029b76`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::GetJsonFromRegistry_::_1_::catch_18(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x3D,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029b62  mov     [rsp+arg_8], rdx
0x180029b67  push    rbp
0x180029b68  sub     rsp, 40h
0x180029b6c  mov     rbp, rdx
0x180029b6f  mov     rcx, [rbp+0A8h]; this
0x180029b76  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029b7d  mov     edx, 3Dh ; '='; void *
0x180029b82  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029b87  mov     [rbp+40h], eax
0x180029b8a  mov     rax, 0
0x180029b94  add     rsp, 40h
0x180029b98  pop     rbp
0x180029b99  retn
```
