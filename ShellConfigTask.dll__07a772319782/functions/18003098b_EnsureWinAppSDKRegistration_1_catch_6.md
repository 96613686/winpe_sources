# _EnsureWinAppSDKRegistration_::_1_::catch$6

- ea: `0x18003098b`
- end: `0x1800309c1`
- name: `_EnsureWinAppSDKRegistration_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001e298`

## string_xrefs

- `0x18003099c`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall EnsureWinAppSDKRegistration_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xDA,
                           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003098b  mov     [rsp+arg_8], rdx
0x180030990  push    rbp
0x180030991  sub     rsp, 20h
0x180030995  mov     rbp, rdx
0x180030998  mov     rcx, [rbp+48h]; this
0x18003099c  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800309a3  mov     edx, 0DAh; void *
0x1800309a8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800309ad  mov     [rbp+50h], eax
0x1800309b0  mov     rax, 0
0x1800309ba  add     rsp, 20h
0x1800309be  pop     rbp
0x1800309bf  retn
```
