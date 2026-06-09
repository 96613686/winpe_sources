# _UpdateReserveManager::TurnOffReserves_::_1_::catch$1

- ea: `0x180032bb8`
- end: `0x180032bee`
- name: `_UpdateReserveManager::TurnOffReserves_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x1800204d0`

## string_xrefs

- `0x180032bcc`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::TurnOffReserves_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x4C0,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180020758;
}

```

## disassembly

```asm
0x180032bb8  mov     [rsp+arg_8], rdx
0x180032bbd  push    rbp
0x180032bbe  sub     rsp, 40h
0x180032bc2  mov     rbp, rdx
0x180032bc5  mov     rcx, [rbp+0C8h]; this
0x180032bcc  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032bd3  mov     edx, 4C0h; void *
0x180032bd8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032bdd  mov     [rbp+50h], eax
0x180032be0  lea     rax, loc_180020758
0x180032be7  add     rsp, 40h
0x180032beb  pop     rbp
0x180032bec  retn
```
