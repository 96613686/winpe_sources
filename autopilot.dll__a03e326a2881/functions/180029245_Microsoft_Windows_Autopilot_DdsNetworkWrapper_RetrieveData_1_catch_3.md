# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData_::_1_::catch$3

- ea: `0x180029245`
- end: `0x180029281`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData_::_1_::catch$3`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180029259`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029245  mov     [rsp+arg_8], rdx
0x18002924a  push    rbp
0x18002924b  sub     rsp, 20h
0x18002924f  mov     rbp, rdx
0x180029252  mov     rcx, [rbp+88h]; this
0x180029259  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180029260  mov     edx, 2E1h; void *
0x180029265  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002926a  mov     [rbp+90h], eax
0x180029270  mov     rax, 0
0x18002927a  add     rsp, 20h
0x18002927e  pop     rbp
0x18002927f  retn
```
