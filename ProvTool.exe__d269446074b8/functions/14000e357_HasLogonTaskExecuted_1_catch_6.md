# _HasLogonTaskExecuted_::_1_::catch$6

- ea: `0x14000e357`
- end: `0x14000e38d`
- name: `_HasLogonTaskExecuted_::_1_::catch$6`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400076f4`

## pseudocode

```c
__int64 __fastcall HasLogonTaskExecuted_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x88,
                           (int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x14000e357  mov     [rsp+arg_8], rdx
0x14000e35c  push    rbp
0x14000e35d  sub     rsp, 30h
0x14000e361  mov     rbp, rdx
0x14000e364  mov     rcx, [rbp+38h]; this
0x14000e368  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\provtool\\prov"...
0x14000e36f  mov     edx, 88h; void *
0x14000e374  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14000e379  mov     [rbp+40h], eax
0x14000e37c  mov     rax, 0
0x14000e386  add     rsp, 30h
0x14000e38a  pop     rbp
0x14000e38b  retn
```
