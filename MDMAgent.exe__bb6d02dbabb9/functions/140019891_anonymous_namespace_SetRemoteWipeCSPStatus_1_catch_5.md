# __anonymous_namespace_::SetRemoteWipeCSPStatus_::_1_::catch$5

- ea: `0x140019891`
- end: `0x1400198c7`
- name: `__anonymous_namespace_::SetRemoteWipeCSPStatus_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140006bb4`

## string_xrefs

- `0x1400198a2`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::SetRemoteWipeCSPStatus_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x75,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x140019891  mov     [rsp+arg_8], rdx
0x140019896  push    rbp
0x140019897  sub     rsp, 50h
0x14001989b  mov     rbp, rdx
0x14001989e  mov     rcx, [rbp+68h]; this
0x1400198a2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400198a9  mov     edx, 75h ; 'u'; void *
0x1400198ae  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1400198b3  mov     [rbp+70h], eax
0x1400198b6  mov     rax, 0
0x1400198c0  add     rsp, 50h
0x1400198c4  pop     rbp
0x1400198c5  retn
```
