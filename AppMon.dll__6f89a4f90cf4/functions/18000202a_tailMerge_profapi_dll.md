# __tailMerge_profapi_dll

- ea: `0x18000202a`
- end: `0x1800020a3`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020a9`

## callees

- `0x18000202a`
- `0x18000edd0`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000202a  mov     [rsp+arg_0], rcx
0x18000202f  mov     [rsp+arg_8], rdx
0x180002034  mov     [rsp+arg_10], r8
0x180002039  mov     [rsp+arg_18], r9
0x18000203e  sub     rsp, 68h
0x180002042  movdqa  [rsp+68h+var_48], xmm0
0x180002048  movdqa  [rsp+68h+var_38], xmm1
0x18000204e  movdqa  [rsp+68h+var_28], xmm2
0x180002054  movdqa  [rsp+68h+var_18], xmm3
0x18000205a  mov     rdx, rax
0x18000205d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x180002064  call    __delayLoadHelper2
0x180002069  movdqa  xmm0, [rsp+68h+var_48]
0x18000206f  movdqa  xmm1, [rsp+68h+var_38]
0x180002075  movdqa  xmm2, [rsp+68h+var_28]
0x18000207b  movdqa  xmm3, [rsp+68h+var_18]
0x180002081  mov     rcx, [rsp+68h+arg_0]
0x180002086  mov     rdx, [rsp+68h+arg_8]
0x18000208b  mov     r8, [rsp+68h+arg_10]
0x180002093  mov     r9, [rsp+68h+arg_18]
0x18000209b  add     rsp, 68h
0x18000209f  jmp     short $+2
0x1800020a1  jmp     rax
```
