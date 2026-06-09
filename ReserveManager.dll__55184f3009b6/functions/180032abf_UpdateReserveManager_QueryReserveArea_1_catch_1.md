# _UpdateReserveManager::QueryReserveArea_::_1_::catch$1

- ea: `0x180032abf`
- end: `0x180032af2`
- name: `_UpdateReserveManager::QueryReserveArea_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001c9e0`

## string_xrefs

- `0x180032ad0`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::QueryReserveArea_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x2AA,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001CB07;
}

```

## disassembly

```asm
0x180032abf  mov     [rsp+arg_8], rdx
0x180032ac4  push    rbp
0x180032ac5  sub     rsp, 20h
0x180032ac9  mov     rbp, rdx
0x180032acc  mov     rcx, [rbp+58h]; this
0x180032ad0  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032ad7  mov     edx, 2AAh; void *
0x180032adc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032ae1  mov     [rbp+20h], eax
0x180032ae4  lea     rax, loc_18001CB07
0x180032aeb  add     rsp, 20h
0x180032aef  pop     rbp
0x180032af0  retn
```
