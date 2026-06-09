# _UpdateReserveManager::EnableReserves_::_1_::catch$1

- ea: `0x180032511`
- end: `0x180032547`
- name: `_UpdateReserveManager::EnableReserves_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180015240`

## string_xrefs

- `0x180032525`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::EnableReserves_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x67E,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_1800155A7;
}

```

## disassembly

```asm
0x180032511  mov     [rsp+arg_8], rdx
0x180032516  push    rbp
0x180032517  sub     rsp, 30h
0x18003251b  mov     rbp, rdx
0x18003251e  mov     rcx, [rbp+88h]; this
0x180032525  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18003252c  mov     edx, 67Eh; void *
0x180032531  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032536  mov     [rbp+70h], eax
0x180032539  lea     rax, loc_1800155A7
0x180032540  add     rsp, 30h
0x180032544  pop     rbp
0x180032545  retn
```
