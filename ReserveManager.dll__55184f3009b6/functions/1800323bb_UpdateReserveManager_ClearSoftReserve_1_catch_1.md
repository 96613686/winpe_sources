# _UpdateReserveManager::ClearSoftReserve_::_1_::catch$1

- ea: `0x1800323bb`
- end: `0x1800323ee`
- name: `_UpdateReserveManager::ClearSoftReserve_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180013600`

## string_xrefs

- `0x1800323cc`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::ClearSoftReserve_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x483,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180013759;
}

```

## disassembly

```asm
0x1800323bb  mov     [rsp+arg_8], rdx
0x1800323c0  push    rbp
0x1800323c1  sub     rsp, 20h
0x1800323c5  mov     rbp, rdx
0x1800323c8  mov     rcx, [rbp+58h]; this
0x1800323cc  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800323d3  mov     edx, 483h; void *
0x1800323d8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800323dd  mov     [rbp+38h], eax
0x1800323e0  lea     rax, loc_180013759
0x1800323e7  add     rsp, 20h
0x1800323eb  pop     rbp
0x1800323ec  retn
```
