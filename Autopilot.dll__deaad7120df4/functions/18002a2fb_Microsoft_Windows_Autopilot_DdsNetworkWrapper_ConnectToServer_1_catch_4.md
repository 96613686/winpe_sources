# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer_::_1_::catch$4

- ea: `0x18002a2fb`
- end: `0x18002a334`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer_::_1_::catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a30f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 344),
                           (void *)0x1A6,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a2fb  mov     [rsp+arg_8], rdx
0x18002a300  push    rbp
0x18002a301  sub     rsp, 40h
0x18002a305  mov     rbp, rdx
0x18002a308  mov     rcx, [rbp+158h]; this
0x18002a30f  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a316  mov     edx, 1A6h; void *
0x18002a31b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a320  mov     [rbp+40h], eax
0x18002a323  mov     rax, 0
0x18002a32d  add     rsp, 40h
0x18002a331  pop     rbp
0x18002a332  retn
```
