# GetUpdateReserveManagerCBS$catch$4

- ea: `0x180032217`
- end: `0x18003224d`
- name: `GetUpdateReserveManagerCBS$catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c9c0`

## string_xrefs

- `0x18003222b`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall GetUpdateReserveManagerCBS_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x57,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000CAB8;
}

```

## disassembly

```asm
0x180032217  mov     [rsp+arg_8], rdx
0x18003221c  push    rbp
0x18003221d  sub     rsp, 30h
0x180032221  mov     rbp, rdx
0x180032224  mov     rcx, [rbp+88h]; this
0x18003222b  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180032232  mov     edx, 57h ; 'W'; void *
0x180032237  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003223c  mov     [rbp+30h], eax
0x18003223f  lea     rax, loc_18000CAB8
0x180032246  add     rsp, 30h
0x18003224a  pop     rbp
0x18003224b  retn
```
