# _TryDeleteRecallData_::_1_::catch$85

- ea: `0x18003195e`
- end: `0x180031997`
- name: `_TryDeleteRecallData_::_1_::catch$85`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18001e298`

## string_xrefs

- `0x180031972`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall TryDeleteRecallData_::_1_::catch_85(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 360),
                           (void *)0x2BE,
                           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003195e  mov     [rsp+arg_8], rdx
0x180031963  push    rbp
0x180031964  sub     rsp, 20h
0x180031968  mov     rbp, rdx
0x18003196b  mov     rcx, [rbp+168h]; this
0x180031972  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180031979  mov     edx, 2BEh; void *
0x18003197e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180031983  mov     [rbp+38h], eax
0x180031986  mov     rax, 0
0x180031990  add     rsp, 20h
0x180031994  pop     rbp
0x180031995  retn
```
