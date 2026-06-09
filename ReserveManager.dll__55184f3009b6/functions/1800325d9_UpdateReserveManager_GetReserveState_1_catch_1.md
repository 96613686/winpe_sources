# _UpdateReserveManager::GetReserveState_::_1_::catch$1

- ea: `0x1800325d9`
- end: `0x18003260c`
- name: `_UpdateReserveManager::GetReserveState_::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x1800170ec`

## string_xrefs

- `0x1800325ea`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::GetReserveState_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x6A2,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           a4);
  return &loc_180017288;
}

```

## disassembly

```asm
0x1800325d9  mov     [rsp+arg_8], rdx
0x1800325de  push    rbp
0x1800325df  sub     rsp, 20h
0x1800325e3  mov     rbp, rdx
0x1800325e6  mov     rcx, [rbp+68h]; this
0x1800325ea  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800325f1  mov     edx, 6A2h; void *
0x1800325f6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800325fb  mov     [rbp+20h], eax
0x1800325fe  lea     rax, loc_180017288
0x180032605  add     rsp, 20h
0x180032609  pop     rbp
0x18003260a  retn
```
