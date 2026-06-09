# _UpdateReserveManager::PrepareForAuditMode_::_1_::catch$1

- ea: `0x18003291b`
- end: `0x18003294e`
- name: `_UpdateReserveManager::PrepareForAuditMode_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x18001b3d0`

## string_xrefs

- `0x18003292c`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::PrepareForAuditMode_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x5FA,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_18001B54A;
}

```

## disassembly

```asm
0x18003291b  mov     [rsp+arg_8], rdx
0x180032920  push    rbp
0x180032921  sub     rsp, 20h
0x180032925  mov     rbp, rdx
0x180032928  mov     rcx, [rbp+68h]; this
0x18003292c  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032933  mov     edx, 5FAh; void *
0x180032938  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003293d  mov     [rbp+30h], eax
0x180032940  lea     rax, loc_18001B54A
0x180032947  add     rsp, 20h
0x18003294b  pop     rbp
0x18003294c  retn
```
