# _GetUserWorkingDirectories_::_1_::catch$26

- ea: `0x18003167d`
- end: `0x1800316b6`
- name: `_GetUserWorkingDirectories_::_1_::catch$26`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18001e298`

## string_xrefs

- `0x180031691`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall GetUserWorkingDirectories_::_1_::catch_26(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 744),
                           (void *)0x251,
                           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003167d  mov     [rsp+arg_8], rdx
0x180031682  push    rbp
0x180031683  sub     rsp, 30h
0x180031687  mov     rbp, rdx
0x18003168a  mov     rcx, [rbp+2E8h]; this
0x180031691  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180031698  mov     edx, 251h; void *
0x18003169d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800316a2  mov     [rbp+30h], eax
0x1800316a5  mov     rax, 0
0x1800316af  add     rsp, 30h
0x1800316b3  pop     rbp
0x1800316b4  retn
```
