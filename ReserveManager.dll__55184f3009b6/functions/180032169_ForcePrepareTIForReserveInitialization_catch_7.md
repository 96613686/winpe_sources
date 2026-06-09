# ForcePrepareTIForReserveInitialization$catch$7

- ea: `0x180032169`
- end: `0x18003219c`
- name: `ForcePrepareTIForReserveInitialization$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c760`

## string_xrefs

- `0x18003217a`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall ForcePrepareTIForReserveInitialization_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x83,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C803;
}

```

## disassembly

```asm
0x180032169  mov     [rsp+arg_8], rdx
0x18003216e  push    rbp
0x18003216f  sub     rsp, 20h
0x180032173  mov     rbp, rdx
0x180032176  mov     rcx, [rbp+48h]; this
0x18003217a  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180032181  mov     edx, 83h; void *
0x180032186  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003218b  mov     [rbp+20h], eax
0x18003218e  lea     rax, loc_18000C803
0x180032195  add     rsp, 20h
0x180032199  pop     rbp
0x18003219a  retn
```
