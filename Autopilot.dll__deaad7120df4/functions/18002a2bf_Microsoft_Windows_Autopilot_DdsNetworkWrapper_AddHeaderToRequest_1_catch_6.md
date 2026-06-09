# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest_::_1_::catch$6

- ea: `0x18002a2bf`
- end: `0x18002a2f5`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a2d0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x1BE,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a2bf  mov     [rsp+arg_8], rdx
0x18002a2c4  push    rbp
0x18002a2c5  sub     rsp, 20h
0x18002a2c9  mov     rbp, rdx
0x18002a2cc  mov     rcx, [rbp+78h]; this
0x18002a2d0  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a2d7  mov     edx, 1BEh; void *
0x18002a2dc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a2e1  mov     [rbp+40h], eax
0x18002a2e4  mov     rax, 0
0x18002a2ee  add     rsp, 20h
0x18002a2f2  pop     rbp
0x18002a2f3  retn
```
