# _RecursiveDelete_::_1_::catch$27

- ea: `0x180031859`
- end: `0x180031892`
- name: `_RecursiveDelete_::_1_::catch$27`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18001e298`

## string_xrefs

- `0x18003186d`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall RecursiveDelete_::_1_::catch_27(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 100) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 296),
                            (void *)0xD8,
                            (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180031859  mov     [rsp+arg_8], rdx
0x18003185e  push    rbp
0x18003185f  sub     rsp, 60h
0x180031863  mov     rbp, rdx
0x180031866  mov     rcx, [rbp+128h]; this
0x18003186d  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180031874  mov     edx, 0D8h; void *
0x180031879  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003187e  mov     [rbp+64h], eax
0x180031881  mov     rax, 0
0x18003188b  add     rsp, 60h
0x18003188f  pop     rbp
0x180031890  retn
```
