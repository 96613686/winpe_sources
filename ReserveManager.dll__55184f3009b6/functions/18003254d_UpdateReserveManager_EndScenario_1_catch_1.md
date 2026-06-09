# _UpdateReserveManager::EndScenario_::_1_::catch$1

- ea: `0x18003254d`
- end: `0x180032583`
- name: `_UpdateReserveManager::EndScenario_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x1800155e0`

## string_xrefs

- `0x180032561`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::EndScenario_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 264),
                           (void *)0x294,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180015AA3;
}

```

## disassembly

```asm
0x18003254d  mov     [rsp+arg_8], rdx
0x180032552  push    rbp
0x180032553  sub     rsp, 50h
0x180032557  mov     rbp, rdx
0x18003255a  mov     rcx, [rbp+108h]; this
0x180032561  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032568  mov     edx, 294h; void *
0x18003256d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032572  mov     [rbp+50h], eax
0x180032575  lea     rax, loc_180015AA3
0x18003257c  add     rsp, 50h
0x180032580  pop     rbp
0x180032581  retn
```
