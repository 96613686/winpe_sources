# InitializeReservesAndUpdatePolicy$catch$7

- ea: `0x180032253`
- end: `0x180032286`
- name: `InitializeReservesAndUpdatePolicy$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000cad0`

## string_xrefs

- `0x180032264`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall InitializeReservesAndUpdatePolicy_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x98,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000CB58;
}

```

## disassembly

```asm
0x180032253  mov     [rsp+arg_8], rdx
0x180032258  push    rbp
0x180032259  sub     rsp, 20h
0x18003225d  mov     rbp, rdx
0x180032260  mov     rcx, [rbp+38h]; this
0x180032264  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x18003226b  mov     edx, 98h; void *
0x180032270  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032275  mov     [rbp+20h], eax
0x180032278  lea     rax, loc_18000CB58
0x18003227f  add     rsp, 20h
0x180032283  pop     rbp
0x180032284  retn
```
