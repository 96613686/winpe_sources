# PrepareMachineForAuditMode$catch$7

- ea: `0x18003228c`
- end: `0x1800322bf`
- name: `PrepareMachineForAuditMode$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000cb70`

## string_xrefs

- `0x18003229d`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall PrepareMachineForAuditMode_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xEC,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000CBFF;
}

```

## disassembly

```asm
0x18003228c  mov     [rsp+arg_8], rdx
0x180032291  push    rbp
0x180032292  sub     rsp, 20h
0x180032296  mov     rbp, rdx
0x180032299  mov     rcx, [rbp+38h]; this
0x18003229d  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x1800322a4  mov     edx, 0ECh; void *
0x1800322a9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800322ae  mov     [rbp+20h], eax
0x1800322b1  lea     rax, loc_18000CBFF
0x1800322b8  add     rsp, 20h
0x1800322bc  pop     rbp
0x1800322bd  retn
```
