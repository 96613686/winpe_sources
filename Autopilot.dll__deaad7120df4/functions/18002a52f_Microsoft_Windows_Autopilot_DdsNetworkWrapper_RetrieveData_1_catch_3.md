# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData_::_1_::catch$3

- ea: `0x18002a52f`
- end: `0x18002a56b`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData_::_1_::catch$3`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a543`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 144) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x2E1,
                            (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002a52f  mov     [rsp+arg_8], rdx
0x18002a534  push    rbp
0x18002a535  sub     rsp, 20h
0x18002a539  mov     rbp, rdx
0x18002a53c  mov     rcx, [rbp+88h]; this
0x18002a543  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a54a  mov     edx, 2E1h; void *
0x18002a54f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a554  mov     [rbp+90h], eax
0x18002a55a  mov     rax, 0
0x18002a564  add     rsp, 20h
0x18002a568  pop     rbp
0x18002a569  retn
```
