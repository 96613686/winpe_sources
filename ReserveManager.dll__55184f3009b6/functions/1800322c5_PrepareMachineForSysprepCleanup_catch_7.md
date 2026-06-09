# PrepareMachineForSysprepCleanup$catch$7

- ea: `0x1800322c5`
- end: `0x1800322f8`
- name: `PrepareMachineForSysprepCleanup$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000cc20`

## string_xrefs

- `0x1800322d6`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall PrepareMachineForSysprepCleanup_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xC2,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000CCAF;
}

```

## disassembly

```asm
0x1800322c5  mov     [rsp+arg_8], rdx
0x1800322ca  push    rbp
0x1800322cb  sub     rsp, 20h
0x1800322cf  mov     rbp, rdx
0x1800322d2  mov     rcx, [rbp+38h]; this
0x1800322d6  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x1800322dd  mov     edx, 0C2h; void *
0x1800322e2  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800322e7  mov     [rbp+20h], eax
0x1800322ea  lea     rax, loc_18000CCAF
0x1800322f1  add     rsp, 20h
0x1800322f5  pop     rbp
0x1800322f6  retn
```
