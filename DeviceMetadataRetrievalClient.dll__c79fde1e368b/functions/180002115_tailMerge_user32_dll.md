# __tailMerge_user32_dll

- ea: `0x180002115`
- end: `0x18000218e`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002194`

## callees

- `0x180002115`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002115  mov     [rsp+arg_0], rcx
0x18000211a  mov     [rsp+arg_8], rdx
0x18000211f  mov     [rsp+arg_10], r8
0x180002124  mov     [rsp+arg_18], r9
0x180002129  sub     rsp, 68h
0x18000212d  movdqa  [rsp+68h+var_48], xmm0
0x180002133  movdqa  [rsp+68h+var_38], xmm1
0x180002139  movdqa  [rsp+68h+var_28], xmm2
0x18000213f  movdqa  [rsp+68h+var_18], xmm3
0x180002145  mov     rdx, rax
0x180002148  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x18000214f  call    __delayLoadHelper2
0x180002154  movdqa  xmm0, [rsp+68h+var_48]
0x18000215a  movdqa  xmm1, [rsp+68h+var_38]
0x180002160  movdqa  xmm2, [rsp+68h+var_28]
0x180002166  movdqa  xmm3, [rsp+68h+var_18]
0x18000216c  mov     rcx, [rsp+68h+arg_0]
0x180002171  mov     rdx, [rsp+68h+arg_8]
0x180002176  mov     r8, [rsp+68h+arg_10]
0x18000217e  mov     r9, [rsp+68h+arg_18]
0x180002186  add     rsp, 68h
0x18000218a  jmp     short $+2
0x18000218c  jmp     rax
```
