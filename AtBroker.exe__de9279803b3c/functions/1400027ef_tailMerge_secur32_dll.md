# __tailMerge_secur32_dll

- ea: `0x1400027ef`
- end: `0x140002868`
- name: `__tailMerge_secur32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000286e`

## callees

- `0x1400027ef`
- `0x140015a10`

## pseudocode

```c
__int64 __fastcall _tailMerge_secur32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_secur32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400027ef  mov     [rsp+arg_0], rcx
0x1400027f4  mov     [rsp+arg_8], rdx
0x1400027f9  mov     [rsp+arg_10], r8
0x1400027fe  mov     [rsp+arg_18], r9
0x140002803  sub     rsp, 68h
0x140002807  movdqa  [rsp+68h+var_48], xmm0
0x14000280d  movdqa  [rsp+68h+var_38], xmm1
0x140002813  movdqa  [rsp+68h+var_28], xmm2
0x140002819  movdqa  [rsp+68h+var_18], xmm3
0x14000281f  mov     rdx, rax
0x140002822  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_secur32_dll
0x140002829  call    __delayLoadHelper2
0x14000282e  movdqa  xmm0, [rsp+68h+var_48]
0x140002834  movdqa  xmm1, [rsp+68h+var_38]
0x14000283a  movdqa  xmm2, [rsp+68h+var_28]
0x140002840  movdqa  xmm3, [rsp+68h+var_18]
0x140002846  mov     rcx, [rsp+68h+arg_0]
0x14000284b  mov     rdx, [rsp+68h+arg_8]
0x140002850  mov     r8, [rsp+68h+arg_10]
0x140002858  mov     r9, [rsp+68h+arg_18]
0x140002860  add     rsp, 68h
0x140002864  jmp     short $+2
0x140002866  jmp     rax
```
