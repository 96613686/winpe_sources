# _UpdateReserveManager::PrepareForSysprepCleanup_::_1_::catch$1

- ea: `0x18003298d`
- end: `0x1800329c0`
- name: `_UpdateReserveManager::PrepareForSysprepCleanup_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001b760`

## string_xrefs

- `0x18003299e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::PrepareForSysprepCleanup_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x5C7,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001B8D7;
}

```

## disassembly

```asm
0x18003298d  mov     [rsp+arg_8], rdx
0x180032992  push    rbp
0x180032993  sub     rsp, 20h
0x180032997  mov     rbp, rdx
0x18003299a  mov     rcx, [rbp+68h]; this
0x18003299e  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800329a5  mov     edx, 5C7h; void *
0x1800329aa  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800329af  mov     [rbp+30h], eax
0x1800329b2  lea     rax, loc_18001B8D7
0x1800329b9  add     rsp, 20h
0x1800329bd  pop     rbp
0x1800329be  retn
```
