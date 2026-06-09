# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket_::_1_::catch$95

- ea: `0x18002a44e`
- end: `0x18002a487`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket_::_1_::catch$95`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a462`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a44e  mov     [rsp+arg_8], rdx
0x18002a453  push    rbp
0x18002a454  sub     rsp, 30h
0x18002a458  mov     rbp, rdx
0x18002a45b  mov     rcx, [rbp+0F8h]; this
0x18002a462  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a469  mov     edx, 322h; void *
0x18002a46e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a473  mov     [rbp+30h], eax
0x18002a476  mov     rax, 0
0x18002a480  add     rsp, 30h
0x18002a484  pop     rbp
0x18002a485  retn
```
