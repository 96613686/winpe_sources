# EnableReserves$catch$7

- ea: `0x1800320f7`
- end: `0x18003212a`
- name: `EnableReserves$catch$7`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a0a4`
- `0x18000c610`

## string_xrefs

- `0x180032108`: `onecore\base\servicing\updatereservemanager\dll\main.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall EnableReserves_catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x116,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\dll\\main.cpp",
                           a4);
  return &loc_18000C698;
}

```

## disassembly

```asm
0x1800320f7  mov     [rsp+arg_8], rdx
0x1800320fc  push    rbp
0x1800320fd  sub     rsp, 20h
0x180032101  mov     rbp, rdx
0x180032104  mov     rcx, [rbp+38h]; this
0x180032108  lea     r8, aOnecoreBaseSer_0; "onecore\\base\\servicing\\updatereserve"...
0x18003210f  mov     edx, 116h; void *
0x180032114  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032119  mov     [rbp+20h], eax
0x18003211c  lea     rax, loc_18000C698
0x180032123  add     rsp, 20h
0x180032127  pop     rbp
0x180032128  retn
```
