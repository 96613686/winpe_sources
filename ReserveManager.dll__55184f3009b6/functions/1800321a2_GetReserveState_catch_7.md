# GetReserveState$catch$7

- ea: `0x1800321a2`
- end: `0x1800321d5`
- name: `GetReserveState$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c820`

## string_xrefs

- `0x1800321b3`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall GetReserveState_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x12C,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C8AC;
}

```

## disassembly

```asm
0x1800321a2  mov     [rsp+arg_8], rdx
0x1800321a7  push    rbp
0x1800321a8  sub     rsp, 20h
0x1800321ac  mov     rbp, rdx
0x1800321af  mov     rcx, [rbp+48h]; this
0x1800321b3  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x1800321ba  mov     edx, 12Ch; void *
0x1800321bf  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800321c4  mov     [rbp+20h], eax
0x1800321c7  lea     rax, loc_18000C8AC
0x1800321ce  add     rsp, 20h
0x1800321d2  pop     rbp
0x1800321d3  retn
```
