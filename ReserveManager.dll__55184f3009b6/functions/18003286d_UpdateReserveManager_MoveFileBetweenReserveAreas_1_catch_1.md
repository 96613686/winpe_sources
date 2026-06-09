# _UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch$1

- ea: `0x18003286d`
- end: `0x1800328a3`
- name: `_UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x18000a0a4`
- `0x18001ac20`

## string_xrefs

- `0x180032881`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x2F2,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001AF9C;
}

```

## disassembly

```asm
0x18003286d  mov     [rsp+arg_8], rdx
0x180032872  push    rbp
0x180032873  sub     rsp, 30h
0x180032877  mov     rbp, rdx
0x18003287a  mov     rcx, [rbp+0F8h]; this
0x180032881  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032888  mov     edx, 2F2h; void *
0x18003288d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032892  mov     [rbp+48h], eax
0x180032895  lea     rax, loc_18001AF9C
0x18003289c  add     rsp, 30h
0x1800328a0  pop     rbp
0x1800328a1  retn
```
