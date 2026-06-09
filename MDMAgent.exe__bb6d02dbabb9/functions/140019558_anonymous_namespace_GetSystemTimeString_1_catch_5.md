# __anonymous_namespace_::GetSystemTimeString_::_1_::catch$5

- ea: `0x140019558`
- end: `0x14001958e`
- name: `__anonymous_namespace_::GetSystemTimeString_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140006bb4`

## string_xrefs

- `0x140019569`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::GetSystemTimeString_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x90,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140019558  mov     [rsp+arg_8], rdx
0x14001955d  push    rbp
0x14001955e  sub     rsp, 50h
0x140019562  mov     rbp, rdx
0x140019565  mov     rcx, [rbp+78h]; this
0x140019569  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140019570  mov     edx, 90h; void *
0x140019575  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14001957a  mov     [rbp+50h], eax
0x14001957d  mov     rax, 0
0x140019587  add     rsp, 50h
0x14001958b  pop     rbp
0x14001958c  retn
```
