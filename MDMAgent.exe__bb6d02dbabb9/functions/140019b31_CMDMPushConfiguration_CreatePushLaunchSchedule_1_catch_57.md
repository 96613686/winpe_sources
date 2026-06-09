# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::catch$57

- ea: `0x140019b31`
- end: `0x140019b6a`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::catch$57`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006bb4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::catch_57(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 1448),
                           (void *)0x4EC,
                           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140019b31  mov     [rsp+arg_8], rdx
0x140019b36  push    rbp
0x140019b37  sub     rsp, 50h
0x140019b3b  mov     rbp, rdx
0x140019b3e  mov     rcx, [rbp+5A8h]; this
0x140019b45  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140019b4c  mov     edx, 4ECh; void *
0x140019b51  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140019b56  mov     [rbp+58h], eax
0x140019b59  mov     rax, 0
0x140019b63  add     rsp, 50h
0x140019b67  pop     rbp
0x140019b68  retn
```
