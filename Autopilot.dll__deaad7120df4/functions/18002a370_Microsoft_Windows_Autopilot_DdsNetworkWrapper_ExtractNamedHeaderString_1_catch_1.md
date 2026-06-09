# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString_::_1_::catch$1

- ea: `0x18002a370`
- end: `0x18002a3a6`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800190cc`

## string_xrefs

- `0x18002a381`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x28D,
                           (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a370  mov     [rsp+arg_8], rdx
0x18002a375  push    rbp
0x18002a376  sub     rsp, 30h
0x18002a37a  mov     rbp, rdx
0x18002a37d  mov     rcx, [rbp+58h]; this
0x18002a381  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002a388  mov     edx, 28Dh; void *
0x18002a38d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a392  mov     [rbp+60h], eax
0x18002a395  mov     rax, 0
0x18002a39f  add     rsp, 30h
0x18002a3a3  pop     rbp
0x18002a3a4  retn
```
