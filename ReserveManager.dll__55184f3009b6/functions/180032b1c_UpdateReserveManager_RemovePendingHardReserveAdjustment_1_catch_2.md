# _UpdateReserveManager::RemovePendingHardReserveAdjustment_::_1_::catch$2

- ea: `0x180032b1c`
- end: `0x180032b55`
- name: `_UpdateReserveManager::RemovePendingHardReserveAdjustment_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001d140`

## string_xrefs

- `0x180032b30`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::RemovePendingHardReserveAdjustment_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 216),
                            (void *)0x465,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_18001D40A;
}

```

## disassembly

```asm
0x180032b1c  mov     [rsp+arg_8], rdx
0x180032b21  push    rbp
0x180032b22  sub     rsp, 40h
0x180032b26  mov     rbp, rdx
0x180032b29  mov     rcx, [rbp+0D8h]; this
0x180032b30  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032b37  mov     edx, 465h; void *
0x180032b3c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032b41  mov     [rbp+80h], eax
0x180032b47  lea     rax, loc_18001D40A
0x180032b4e  add     rsp, 40h
0x180032b52  pop     rbp
0x180032b53  retn
```
