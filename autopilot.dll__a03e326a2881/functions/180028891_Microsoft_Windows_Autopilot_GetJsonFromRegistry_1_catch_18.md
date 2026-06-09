# _Microsoft::Windows::Autopilot::GetJsonFromRegistry_::_1_::catch$18

- ea: `0x180028891`
- end: `0x1800288ca`
- name: `_Microsoft::Windows::Autopilot::GetJsonFromRegistry_::_1_::catch$18`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x1800288a5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028891  mov     [rsp+arg_8], rdx
0x180028896  push    rbp
0x180028897  sub     rsp, 40h
0x18002889b  mov     rbp, rdx
0x18002889e  mov     rcx, [rbp+0A8h]; this
0x1800288a5  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800288ac  mov     edx, 3Dh ; '='; void *
0x1800288b1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800288b6  mov     [rbp+40h], eax
0x1800288b9  mov     rax, 0
0x1800288c3  add     rsp, 40h
0x1800288c7  pop     rbp
0x1800288c8  retn
```
