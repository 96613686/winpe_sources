# _UpdateReserveManager::UpdatePendingHardReserveAdjustment_::_1_::catch$2

- ea: `0x180032c51`
- end: `0x180032c8a`
- name: `_UpdateReserveManager::UpdatePendingHardReserveAdjustment_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180020e00`

## string_xrefs

- `0x180032c65`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::UpdatePendingHardReserveAdjustment_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 140) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 264),
                            (void *)0x3E9,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_18002180D;
}

```

## disassembly

```asm
0x180032c51  mov     [rsp+arg_8], rdx
0x180032c56  push    rbp
0x180032c57  sub     rsp, 40h
0x180032c5b  mov     rbp, rdx
0x180032c5e  mov     rcx, [rbp+108h]; this
0x180032c65  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032c6c  mov     edx, 3E9h; void *
0x180032c71  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032c76  mov     [rbp+8Ch], eax
0x180032c7c  lea     rax, loc_18002180D
0x180032c83  add     rsp, 40h
0x180032c87  pop     rbp
0x180032c88  retn
```
