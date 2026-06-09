# GetUpdateReserveManager$catch$4

- ea: `0x1800321db`
- end: `0x180032211`
- name: `GetUpdateReserveManager$catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c8c0`

## string_xrefs

- `0x1800321ef`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall GetUpdateReserveManager_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x38,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C9A7;
}

```

## disassembly

```asm
0x1800321db  mov     [rsp+arg_8], rdx
0x1800321e0  push    rbp
0x1800321e1  sub     rsp, 30h
0x1800321e5  mov     rbp, rdx
0x1800321e8  mov     rcx, [rbp+88h]; this
0x1800321ef  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x1800321f6  mov     edx, 38h ; '8'; void *
0x1800321fb  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032200  mov     [rbp+30h], eax
0x180032203  lea     rax, loc_18000C9A7
0x18003220a  add     rsp, 30h
0x18003220e  pop     rbp
0x18003220f  retn
```
