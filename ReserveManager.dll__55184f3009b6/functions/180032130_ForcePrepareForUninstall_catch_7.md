# ForcePrepareForUninstall$catch$7

- ea: `0x180032130`
- end: `0x180032163`
- name: `ForcePrepareForUninstall$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c6b0`

## string_xrefs

- `0x180032141`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall ForcePrepareForUninstall_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xAD,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C73F;
}

```

## disassembly

```asm
0x180032130  mov     [rsp+arg_8], rdx
0x180032135  push    rbp
0x180032136  sub     rsp, 20h
0x18003213a  mov     rbp, rdx
0x18003213d  mov     rcx, [rbp+38h]; this
0x180032141  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180032148  mov     edx, 0ADh; void *
0x18003214d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032152  mov     [rbp+20h], eax
0x180032155  lea     rax, loc_18000C73F
0x18003215c  add     rsp, 20h
0x180032160  pop     rbp
0x180032161  retn
```
