# _UpdateReserveManager::PrepareForReset_::_1_::catch$1

- ea: `0x180032954`
- end: `0x180032987`
- name: `_UpdateReserveManager::PrepareForReset_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001b560`

## string_xrefs

- `0x180032965`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::PrepareForReset_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x4DC,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001B73E;
}

```

## disassembly

```asm
0x180032954  mov     [rsp+arg_8], rdx
0x180032959  push    rbp
0x18003295a  sub     rsp, 20h
0x18003295e  mov     rbp, rdx
0x180032961  mov     rcx, [rbp+68h]; this
0x180032965  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18003296c  mov     edx, 4DCh; void *
0x180032971  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032976  mov     [rbp+30h], eax
0x180032979  lea     rax, loc_18001B73E
0x180032980  add     rsp, 20h
0x180032984  pop     rbp
0x180032985  retn
```
