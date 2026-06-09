# _Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData_::_1_::catch$13

- ea: `0x180029d51`
- end: `0x180029d87`
- name: `_Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData_::_1_::catch$13`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x180029d62`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData_::_1_::catch_13(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x122,
                            (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029d51  mov     [rsp+arg_8], rdx
0x180029d56  push    rbp
0x180029d57  sub     rsp, 30h
0x180029d5b  mov     rbp, rdx
0x180029d5e  mov     rcx, [rbp+58h]; this
0x180029d62  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029d69  mov     edx, 122h; void *
0x180029d6e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029d73  mov     [rbp+68h], eax
0x180029d76  mov     rax, 0
0x180029d80  add     rsp, 30h
0x180029d84  pop     rbp
0x180029d85  retn
```
