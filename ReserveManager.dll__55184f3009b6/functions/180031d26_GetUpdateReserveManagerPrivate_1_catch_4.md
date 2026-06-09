# _GetUpdateReserveManagerPrivate_::_1_::catch$4

- ea: `0x180031d26`
- end: `0x180031d5c`
- name: `_GetUpdateReserveManagerPrivate_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180007d08`
- `0x18000a0a4`

## string_xrefs

- `0x180031d3a`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall GetUpdateReserveManagerPrivate_::_1_::catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x6D,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_180007DF2;
}

```

## disassembly

```asm
0x180031d26  mov     [rsp+arg_8], rdx
0x180031d2b  push    rbp
0x180031d2c  sub     rsp, 30h
0x180031d30  mov     rbp, rdx
0x180031d33  mov     rcx, [rbp+88h]; this
0x180031d3a  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180031d41  mov     edx, 6Dh ; 'm'; void *
0x180031d46  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180031d4b  mov     [rbp+30h], eax
0x180031d4e  lea     rax, loc_180007DF2
0x180031d55  add     rsp, 30h
0x180031d59  pop     rbp
0x180031d5a  retn
```
