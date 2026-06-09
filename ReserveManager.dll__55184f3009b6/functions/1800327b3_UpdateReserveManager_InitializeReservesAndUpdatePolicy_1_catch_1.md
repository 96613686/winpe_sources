# _UpdateReserveManager::InitializeReservesAndUpdatePolicy_::_1_::catch$1

- ea: `0x1800327b3`
- end: `0x1800327e9`
- name: `_UpdateReserveManager::InitializeReservesAndUpdatePolicy_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x18000a0a4`
- `0x1800192e0`

## string_xrefs

- `0x1800327c7`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::InitializeReservesAndUpdatePolicy_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 184),
                            (void *)0x55D,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_18001960C;
}

```

## disassembly

```asm
0x1800327b3  mov     [rsp+arg_8], rdx
0x1800327b8  push    rbp
0x1800327b9  sub     rsp, 30h
0x1800327bd  mov     rbp, rdx
0x1800327c0  mov     rcx, [rbp+0B8h]; this
0x1800327c7  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800327ce  mov     edx, 55Dh; void *
0x1800327d3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800327d8  mov     [rbp+78h], eax
0x1800327db  lea     rax, loc_18001960C
0x1800327e2  add     rsp, 30h
0x1800327e6  pop     rbp
0x1800327e7  retn
```
