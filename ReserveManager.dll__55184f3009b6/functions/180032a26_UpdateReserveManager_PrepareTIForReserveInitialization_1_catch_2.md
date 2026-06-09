# _UpdateReserveManager::PrepareTIForReserveInitialization_::_1_::catch$2

- ea: `0x180032a26`
- end: `0x180032a5f`
- name: `_UpdateReserveManager::PrepareTIForReserveInitialization_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001bd30`

## string_xrefs

- `0x180032a3a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::PrepareTIForReserveInitialization_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 160) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 200),
                            (void *)0x527,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_18001C1F7;
}

```

## disassembly

```asm
0x180032a26  mov     [rsp+arg_8], rdx
0x180032a2b  push    rbp
0x180032a2c  sub     rsp, 30h
0x180032a30  mov     rbp, rdx
0x180032a33  mov     rcx, [rbp+0C8h]; this
0x180032a3a  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032a41  mov     edx, 527h; void *
0x180032a46  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032a4b  mov     [rbp+0A0h], eax
0x180032a51  lea     rax, loc_18001C1F7
0x180032a58  add     rsp, 30h
0x180032a5c  pop     rbp
0x180032a5d  retn
```
