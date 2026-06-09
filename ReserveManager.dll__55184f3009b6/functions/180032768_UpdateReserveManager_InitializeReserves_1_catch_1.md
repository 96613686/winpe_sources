# _UpdateReserveManager::InitializeReserves_::_1_::catch$1

- ea: `0x180032768`
- end: `0x18003279b`
- name: `_UpdateReserveManager::InitializeReserves_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x1800191f0`

## string_xrefs

- `0x180032779`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::InitializeReserves_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x1AD,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_1800192C5;
}

```

## disassembly

```asm
0x180032768  mov     [rsp+arg_8], rdx
0x18003276d  push    rbp
0x18003276e  sub     rsp, 20h
0x180032772  mov     rbp, rdx
0x180032775  mov     rcx, [rbp+48h]; this
0x180032779  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032780  mov     edx, 1ADh; void *
0x180032785  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003278a  mov     [rbp+30h], eax
0x18003278d  lea     rax, loc_1800192C5
0x180032794  add     rsp, 20h
0x180032798  pop     rbp
0x180032799  retn
```
