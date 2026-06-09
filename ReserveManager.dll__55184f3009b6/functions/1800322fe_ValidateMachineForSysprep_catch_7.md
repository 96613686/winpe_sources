# ValidateMachineForSysprep$catch$7

- ea: `0x1800322fe`
- end: `0x180032331`
- name: `ValidateMachineForSysprep$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000ccd0`

## string_xrefs

- `0x18003230f`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall ValidateMachineForSysprep_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xD7,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000CD5F;
}

```

## disassembly

```asm
0x1800322fe  mov     [rsp+arg_8], rdx
0x180032303  push    rbp
0x180032304  sub     rsp, 20h
0x180032308  mov     rbp, rdx
0x18003230b  mov     rcx, [rbp+38h]; this
0x18003230f  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x180032316  mov     edx, 0D7h; void *
0x18003231b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032320  mov     [rbp+20h], eax
0x180032323  lea     rax, loc_18000CD5F
0x18003232a  add     rsp, 20h
0x18003232e  pop     rbp
0x18003232f  retn
```
