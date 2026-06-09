# _UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch$10

- ea: `0x1800328a9`
- end: `0x1800328df`
- name: `_UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x18000a0a4`
- `0x18001aff0`

## string_xrefs

- `0x1800328bd`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::MoveFileBetweenReserveAreas_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 296),
                           (void *)0x324,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001B384;
}

```

## disassembly

```asm
0x1800328a9  mov     [rsp+arg_8], rdx
0x1800328ae  push    rbp
0x1800328af  sub     rsp, 40h
0x1800328b3  mov     rbp, rdx
0x1800328b6  mov     rcx, [rbp+128h]; this
0x1800328bd  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800328c4  mov     edx, 324h; void *
0x1800328c9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800328ce  mov     [rbp+50h], eax
0x1800328d1  lea     rax, loc_18001B384
0x1800328d8  add     rsp, 40h
0x1800328dc  pop     rbp
0x1800328dd  retn
```
