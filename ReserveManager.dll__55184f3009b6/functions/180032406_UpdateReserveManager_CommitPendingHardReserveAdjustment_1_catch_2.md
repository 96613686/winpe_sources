# _UpdateReserveManager::CommitPendingHardReserveAdjustment_::_1_::catch$2

- ea: `0x180032406`
- end: `0x18003243f`
- name: `_UpdateReserveManager::CommitPendingHardReserveAdjustment_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a0a4`
- `0x180013850`

## string_xrefs

- `0x18003241a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::CommitPendingHardReserveAdjustment_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 216),
                            (void *)0x42B,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_180013C0A;
}

```

## disassembly

```asm
0x180032406  mov     [rsp+arg_8], rdx
0x18003240b  push    rbp
0x18003240c  sub     rsp, 40h
0x180032410  mov     rbp, rdx
0x180032413  mov     rcx, [rbp+0D8h]; this
0x18003241a  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032421  mov     edx, 42Bh; void *
0x180032426  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003242b  mov     [rbp+80h], eax
0x180032431  lea     rax, loc_180013C0A
0x180032438  add     rsp, 40h
0x18003243c  pop     rbp
0x18003243d  retn
```
