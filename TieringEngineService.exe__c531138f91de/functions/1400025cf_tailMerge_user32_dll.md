# __tailMerge_user32_dll

- ea: `0x1400025cf`
- end: `0x140002648`
- name: `__tailMerge_user32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000264e`

## callees

- `0x1400025cf`
- `0x14003c720`

## pseudocode

```c
__int64 __fastcall _tailMerge_user32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_user32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400025cf  mov     [rsp+arg_0], rcx
0x1400025d4  mov     [rsp+arg_8], rdx
0x1400025d9  mov     [rsp+arg_10], r8
0x1400025de  mov     [rsp+arg_18], r9
0x1400025e3  sub     rsp, 68h
0x1400025e7  movdqa  [rsp+68h+var_48], xmm0
0x1400025ed  movdqa  [rsp+68h+var_38], xmm1
0x1400025f3  movdqa  [rsp+68h+var_28], xmm2
0x1400025f9  movdqa  [rsp+68h+var_18], xmm3
0x1400025ff  mov     rdx, rax
0x140002602  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_user32_dll
0x140002609  call    __delayLoadHelper2
0x14000260e  movdqa  xmm0, [rsp+68h+var_48]
0x140002614  movdqa  xmm1, [rsp+68h+var_38]
0x14000261a  movdqa  xmm2, [rsp+68h+var_28]
0x140002620  movdqa  xmm3, [rsp+68h+var_18]
0x140002626  mov     rcx, [rsp+68h+arg_0]
0x14000262b  mov     rdx, [rsp+68h+arg_8]
0x140002630  mov     r8, [rsp+68h+arg_10]
0x140002638  mov     r9, [rsp+68h+arg_18]
0x140002640  add     rsp, 68h
0x140002644  jmp     short $+2
0x140002646  jmp     rax
```
