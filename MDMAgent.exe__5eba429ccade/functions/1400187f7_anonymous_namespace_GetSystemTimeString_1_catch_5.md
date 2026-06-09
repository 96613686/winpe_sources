# __anonymous_namespace_::GetSystemTimeString_::_1_::catch$5

- ea: `0x1400187f7`
- end: `0x14001882d`
- name: `__anonymous_namespace_::GetSystemTimeString_::_1_::catch$5`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140006944`

## string_xrefs

- `0x140018808`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

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
                           (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1400187f7  mov     [rsp+arg_8], rdx
0x1400187fc  push    rbp
0x1400187fd  sub     rsp, 50h
0x140018801  mov     rbp, rdx
0x140018804  mov     rcx, [rbp+78h]; this
0x140018808  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x14001880f  mov     edx, 90h; void *
0x140018814  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140018819  mov     [rbp+50h], eax
0x14001881c  mov     rax, 0
0x140018826  add     rsp, 50h
0x14001882a  pop     rbp
0x14001882b  retn
```
