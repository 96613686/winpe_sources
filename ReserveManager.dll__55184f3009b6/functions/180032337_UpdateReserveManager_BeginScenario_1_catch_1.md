# _UpdateReserveManager::BeginScenario_::_1_::catch$1

- ea: `0x180032337`
- end: `0x18003236d`
- name: `_UpdateReserveManager::BeginScenario_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180012340`

## string_xrefs

- `0x18003234b`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::BeginScenario_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 264),
                           (void *)0x217,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180012797;
}

```

## disassembly

```asm
0x180032337  mov     [rsp+arg_8], rdx
0x18003233c  push    rbp
0x18003233d  sub     rsp, 50h
0x180032341  mov     rbp, rdx
0x180032344  mov     rcx, [rbp+108h]; this
0x18003234b  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032352  mov     edx, 217h; void *
0x180032357  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003235c  mov     [rbp+60h], eax
0x18003235f  lea     rax, loc_180012797
0x180032366  add     rsp, 50h
0x18003236a  pop     rbp
0x18003236b  retn
```
