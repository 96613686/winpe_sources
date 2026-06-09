# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::catch$50

- ea: `0x140019bee`
- end: `0x140019c27`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::catch$50`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006bb4`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::catch_50(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 1448),
                            (void *)0x603,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x140019bee  mov     [rsp+arg_8], rdx
0x140019bf3  push    rbp
0x140019bf4  sub     rsp, 50h
0x140019bf8  mov     rbp, rdx
0x140019bfb  mov     rcx, [rbp+5A8h]; this
0x140019c02  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140019c09  mov     edx, 603h; void *
0x140019c0e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140019c13  mov     [rbp+78h], eax
0x140019c16  mov     rax, 0
0x140019c20  add     rsp, 50h
0x140019c24  pop     rbp
0x140019c25  retn
```
