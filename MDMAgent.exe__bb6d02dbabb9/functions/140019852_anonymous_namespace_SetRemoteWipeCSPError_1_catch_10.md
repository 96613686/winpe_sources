# __anonymous_namespace_::SetRemoteWipeCSPError_::_1_::catch$10

- ea: `0x140019852`
- end: `0x14001988b`
- name: `__anonymous_namespace_::SetRemoteWipeCSPError_::_1_::catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140006bb4`

## string_xrefs

- `0x140019866`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::SetRemoteWipeCSPError_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0xBB,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140019852  mov     [rsp+arg_8], rdx
0x140019857  push    rbp
0x140019858  sub     rsp, 50h
0x14001985c  mov     rbp, rdx
0x14001985f  mov     rcx, [rbp+0A8h]; this
0x140019866  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x14001986d  mov     edx, 0BBh; void *
0x140019872  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140019877  mov     [rbp+60h], eax
0x14001987a  mov     rax, 0
0x140019884  add     rsp, 50h
0x140019888  pop     rbp
0x140019889  retn
```
