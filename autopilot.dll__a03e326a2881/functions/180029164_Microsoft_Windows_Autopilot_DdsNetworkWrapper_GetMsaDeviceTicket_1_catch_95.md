# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket_::_1_::catch$95

- ea: `0x180029164`
- end: `0x18002919d`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket_::_1_::catch$95`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180029178`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket_::_1_::catch_95(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x322,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029164  mov     [rsp+arg_8], rdx
0x180029169  push    rbp
0x18002916a  sub     rsp, 30h
0x18002916e  mov     rbp, rdx
0x180029171  mov     rcx, [rbp+0F8h]; this
0x180029178  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002917f  mov     edx, 322h; void *
0x180029184  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029189  mov     [rbp+30h], eax
0x18002918c  mov     rax, 0
0x180029196  add     rsp, 30h
0x18002919a  pop     rbp
0x18002919b  retn
```
