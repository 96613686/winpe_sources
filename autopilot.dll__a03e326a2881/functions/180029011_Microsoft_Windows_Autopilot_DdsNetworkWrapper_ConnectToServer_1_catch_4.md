# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer_::_1_::catch$4

- ea: `0x180029011`
- end: `0x18002904a`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer_::_1_::catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180029025`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029011  mov     [rsp+arg_8], rdx
0x180029016  push    rbp
0x180029017  sub     rsp, 40h
0x18002901b  mov     rbp, rdx
0x18002901e  mov     rcx, [rbp+158h]; this
0x180029025  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002902c  mov     edx, 1A6h; void *
0x180029031  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029036  mov     [rbp+40h], eax
0x180029039  mov     rax, 0
0x180029043  add     rsp, 40h
0x180029047  pop     rbp
0x180029048  retn
```
