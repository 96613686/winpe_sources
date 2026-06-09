# _UpdateReserveManager::Initialize_::_1_::catch$39

- ea: `0x180032675`
- end: `0x1800326ae`
- name: `_UpdateReserveManager::Initialize_::_1_::catch$39`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a0a4`
- `0x1800177f8`

## string_xrefs

- `0x180032689`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UpdateReserveManager::Initialize_::_1_::catch_39(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 552) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 680),
                            (void *)0x17B,
                            (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                            a4);
  return &loc_180019176;
}

```

## disassembly

```asm
0x180032675  mov     [rsp+arg_8], rdx
0x18003267a  push    rbp
0x18003267b  sub     rsp, 40h
0x18003267f  mov     rbp, rdx
0x180032682  mov     rcx, [rbp+2A8h]; this
0x180032689  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180032690  mov     edx, 17Bh; void *
0x180032695  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003269a  mov     [rbp+228h], eax
0x1800326a0  lea     rax, loc_180019176
0x1800326a7  add     rsp, 40h
0x1800326ab  pop     rbp
0x1800326ac  retn
```
