# _UpdateReserveManager::UntagSnapshots_::_1_::catch$1

- ea: `0x180032c18`
- end: `0x180032c4b`
- name: `_UpdateReserveManager::UntagSnapshots_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180020c70`

## string_xrefs

- `0x180032c29`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::UntagSnapshots_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x6C6,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180020DB8;
}

```

## disassembly

```asm
0x180032c18  mov     [rsp+arg_8], rdx
0x180032c1d  push    rbp
0x180032c1e  sub     rsp, 40h
0x180032c22  mov     rbp, rdx
0x180032c25  mov     rcx, [rbp+78h]; this
0x180032c29  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032c30  mov     edx, 6C6h; void *
0x180032c35  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032c3a  mov     [rbp+58h], eax
0x180032c3d  lea     rax, loc_180020DB8
0x180032c44  add     rsp, 40h
0x180032c48  pop     rbp
0x180032c49  retn
```
