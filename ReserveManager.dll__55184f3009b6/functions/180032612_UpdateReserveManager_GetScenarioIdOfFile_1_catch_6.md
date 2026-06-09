# _UpdateReserveManager::GetScenarioIdOfFile_::_1_::catch$6

- ea: `0x180032612`
- end: `0x18003264b`
- name: `_UpdateReserveManager::GetScenarioIdOfFile_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180017380`

## string_xrefs

- `0x180032626`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::GetScenarioIdOfFile_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 200),
                            (void *)0x34D,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_180017664;
}

```

## disassembly

```asm
0x180032612  mov     [rsp+arg_8], rdx
0x180032617  push    rbp
0x180032618  sub     rsp, 40h
0x18003261c  mov     rbp, rdx
0x18003261f  mov     rcx, [rbp+0C8h]; this
0x180032626  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18003262d  mov     edx, 34Dh; void *
0x180032632  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032637  mov     [rbp+80h], eax
0x18003263d  lea     rax, loc_180017664
0x180032644  add     rsp, 40h
0x180032648  pop     rbp
0x180032649  retn
```
