# _UpdateReserveManager::DisableReserves_::_1_::catch$1

- ea: `0x18003249f`
- end: `0x1800324d5`
- name: `_UpdateReserveManager::DisableReserves_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x180014960`

## string_xrefs

- `0x1800324b3`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::DisableReserves_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 152),
                            (void *)0x645,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_180014E02;
}

```

## disassembly

```asm
0x18003249f  mov     [rsp+arg_8], rdx
0x1800324a4  push    rbp
0x1800324a5  sub     rsp, 30h
0x1800324a9  mov     rbp, rdx
0x1800324ac  mov     rcx, [rbp+98h]; this
0x1800324b3  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800324ba  mov     edx, 645h; void *
0x1800324bf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800324c4  mov     [rbp+78h], eax
0x1800324c7  lea     rax, loc_180014E02
0x1800324ce  add     rsp, 30h
0x1800324d2  pop     rbp
0x1800324d3  retn
```
