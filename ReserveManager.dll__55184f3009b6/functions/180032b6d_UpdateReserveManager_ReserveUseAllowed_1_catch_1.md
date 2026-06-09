# _UpdateReserveManager::ReserveUseAllowed_::_1_::catch$1

- ea: `0x180032b6d`
- end: `0x180032ba0`
- name: `_UpdateReserveManager::ReserveUseAllowed_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a0a4`

## string_xrefs

- `0x180032b7e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
void *__fastcall UpdateReserveManager::ReserveUseAllowed_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x19C,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001EE6C;
}

```

## disassembly

```asm
0x180032b6d  mov     [rsp+arg_8], rdx
0x180032b72  push    rbp
0x180032b73  sub     rsp, 20h
0x180032b77  mov     rbp, rdx
0x180032b7a  mov     rcx, [rbp+48h]; this
0x180032b7e  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032b85  mov     edx, 19Ch; void *
0x180032b8a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032b8f  mov     [rbp+20h], eax
0x180032b92  lea     rax, loc_18001EE6C
0x180032b99  add     rsp, 20h
0x180032b9d  pop     rbp
0x180032b9e  retn
```
