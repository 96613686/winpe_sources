# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString_::_1_::catch$1

- ea: `0x180029086`
- end: `0x1800290bc`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::ExtractNamedHeaderString_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180029097`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029086  mov     [rsp+arg_8], rdx
0x18002908b  push    rbp
0x18002908c  sub     rsp, 30h
0x180029090  mov     rbp, rdx
0x180029093  mov     rcx, [rbp+58h]; this
0x180029097  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002909e  mov     edx, 28Dh; void *
0x1800290a3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800290a8  mov     [rbp+60h], eax
0x1800290ab  mov     rax, 0
0x1800290b5  add     rsp, 30h
0x1800290b9  pop     rbp
0x1800290ba  retn
```
