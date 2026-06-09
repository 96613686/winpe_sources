# _UpdateReserveManager::ValidateForSysprep_::_1_::catch$1

- ea: `0x180032ca2`
- end: `0x180032cd5`
- name: `_UpdateReserveManager::ValidateForSysprep_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180021850`

## string_xrefs

- `0x180032cb3`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::ValidateForSysprep_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x5E3,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180021A0F;
}

```

## disassembly

```asm
0x180032ca2  mov     [rsp+arg_8], rdx
0x180032ca7  push    rbp
0x180032ca8  sub     rsp, 20h
0x180032cac  mov     rbp, rdx
0x180032caf  mov     rcx, [rbp+68h]; this
0x180032cb3  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032cba  mov     edx, 5E3h; void *
0x180032cbf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032cc4  mov     [rbp+20h], eax
0x180032cc7  lea     rax, loc_180021A0F
0x180032cce  add     rsp, 20h
0x180032cd2  pop     rbp
0x180032cd3  retn
```
