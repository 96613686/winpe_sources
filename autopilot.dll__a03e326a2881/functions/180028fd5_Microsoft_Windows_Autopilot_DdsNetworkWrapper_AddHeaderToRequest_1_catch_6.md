# _Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest_::_1_::catch$6

- ea: `0x180028fd5`
- end: `0x18002900b`
- name: `_Microsoft::Windows::Autopilot::DdsNetworkWrapper::AddHeaderToRequest_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018b10`

## string_xrefs

- `0x180028fe6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

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
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028fd5  mov     [rsp+arg_8], rdx
0x180028fda  push    rbp
0x180028fdb  sub     rsp, 20h
0x180028fdf  mov     rbp, rdx
0x180028fe2  mov     rcx, [rbp+78h]; this
0x180028fe6  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028fed  mov     edx, 1BEh; void *
0x180028ff2  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180028ff7  mov     [rbp+40h], eax
0x180028ffa  mov     rax, 0
0x180029004  add     rsp, 20h
0x180029008  pop     rbp
0x180029009  retn
```
