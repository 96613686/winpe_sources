# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::catch$57

- ea: `0x140018dd0`
- end: `0x140018e09`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::catch$57`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006944`

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
                           (int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x140018dd0  mov     [rsp+arg_8], rdx
0x140018dd5  push    rbp
0x140018dd6  sub     rsp, 50h
0x140018dda  mov     rbp, rdx
0x140018ddd  mov     rcx, [rbp+5A8h]; this
0x140018de4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140018deb  mov     edx, 4ECh; void *
0x140018df0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140018df5  mov     [rbp+58h], eax
0x140018df8  mov     rax, 0
0x140018e02  add     rsp, 50h
0x140018e06  pop     rbp
0x140018e07  retn
```
