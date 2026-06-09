# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::catch$50

- ea: `0x140018e8d`
- end: `0x140018ec6`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::catch$50`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006944`

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
                            (int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x140018e8d  mov     [rsp+arg_8], rdx
0x140018e92  push    rbp
0x140018e93  sub     rsp, 50h
0x140018e97  mov     rbp, rdx
0x140018e9a  mov     rcx, [rbp+5A8h]; this
0x140018ea1  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x140018ea8  mov     edx, 603h; void *
0x140018ead  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140018eb2  mov     [rbp+78h], eax
0x140018eb5  mov     rax, 0
0x140018ebf  add     rsp, 50h
0x140018ec3  pop     rbp
0x140018ec4  retn
```
