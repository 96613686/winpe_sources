# _UpdateReserveManager::PrepareForUninstall_::_1_::catch$6

- ea: `0x1800329c6`
- end: `0x1800329fc`
- name: `_UpdateReserveManager::PrepareForUninstall_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001b8f0`

## string_xrefs

- `0x1800329da`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::PrepareForUninstall_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 232),
                           (void *)0x5B0,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001BCFA;
}

```

## disassembly

```asm
0x1800329c6  mov     [rsp+arg_8], rdx
0x1800329cb  push    rbp
0x1800329cc  sub     rsp, 50h
0x1800329d0  mov     rbp, rdx
0x1800329d3  mov     rcx, [rbp+0E8h]; this
0x1800329da  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800329e1  mov     edx, 5B0h; void *
0x1800329e6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800329eb  mov     [rbp+60h], eax
0x1800329ee  lea     rax, loc_18001BCFA
0x1800329f5  add     rsp, 50h
0x1800329f9  pop     rbp
0x1800329fa  retn
```
