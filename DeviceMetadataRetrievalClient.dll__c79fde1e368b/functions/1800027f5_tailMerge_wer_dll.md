# __tailMerge_wer_dll

- ea: `0x1800027f5`
- end: `0x18000286e`
- name: `__tailMerge_wer_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002874`
- `0x180002886`
- `0x180002898`
- `0x1800028aa`
- `0x1800028bc`

## callees

- `0x1800027f5`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_wer_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wer_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027f5  mov     [rsp+arg_0], rcx
0x1800027fa  mov     [rsp+arg_8], rdx
0x1800027ff  mov     [rsp+arg_10], r8
0x180002804  mov     [rsp+arg_18], r9
0x180002809  sub     rsp, 68h
0x18000280d  movdqa  [rsp+68h+var_48], xmm0
0x180002813  movdqa  [rsp+68h+var_38], xmm1
0x180002819  movdqa  [rsp+68h+var_28], xmm2
0x18000281f  movdqa  [rsp+68h+var_18], xmm3
0x180002825  mov     rdx, rax
0x180002828  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wer_dll
0x18000282f  call    __delayLoadHelper2
0x180002834  movdqa  xmm0, [rsp+68h+var_48]
0x18000283a  movdqa  xmm1, [rsp+68h+var_38]
0x180002840  movdqa  xmm2, [rsp+68h+var_28]
0x180002846  movdqa  xmm3, [rsp+68h+var_18]
0x18000284c  mov     rcx, [rsp+68h+arg_0]
0x180002851  mov     rdx, [rsp+68h+arg_8]
0x180002856  mov     r8, [rsp+68h+arg_10]
0x18000285e  mov     r9, [rsp+68h+arg_18]
0x180002866  add     rsp, 68h
0x18000286a  jmp     short $+2
0x18000286c  jmp     rax
```
