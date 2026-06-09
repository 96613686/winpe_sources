# DisableReserves$catch$7

- ea: `0x1800320ac`
- end: `0x1800320df`
- name: `DisableReserves$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c520`

## string_xrefs

- `0x1800320bd`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall DisableReserves_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x101,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C5A8;
}

```

## disassembly

```asm
0x1800320ac  mov     [rsp+arg_8], rdx
0x1800320b1  push    rbp
0x1800320b2  sub     rsp, 20h
0x1800320b6  mov     rbp, rdx
0x1800320b9  mov     rcx, [rbp+38h]; this
0x1800320bd  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x1800320c4  mov     edx, 101h; void *
0x1800320c9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800320ce  mov     [rbp+20h], eax
0x1800320d1  lea     rax, loc_18000C5A8
0x1800320d8  add     rsp, 20h
0x1800320dc  pop     rbp
0x1800320dd  retn
```
