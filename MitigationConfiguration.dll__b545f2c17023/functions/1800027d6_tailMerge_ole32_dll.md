# __tailMerge_ole32_dll

- ea: `0x1800027d6`
- end: `0x18000284f`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002855`

## callees

- `0x1800027d6`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800027d6  mov     [rsp+arg_0], rcx
0x1800027db  mov     [rsp+arg_8], rdx
0x1800027e0  mov     [rsp+arg_10], r8
0x1800027e5  mov     [rsp+arg_18], r9
0x1800027ea  sub     rsp, 68h
0x1800027ee  movdqa  [rsp+68h+var_48], xmm0
0x1800027f4  movdqa  [rsp+68h+var_38], xmm1
0x1800027fa  movdqa  [rsp+68h+var_28], xmm2
0x180002800  movdqa  [rsp+68h+var_18], xmm3
0x180002806  mov     rdx, rax
0x180002809  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180002810  call    __delayLoadHelper2
0x180002815  movdqa  xmm0, [rsp+68h+var_48]
0x18000281b  movdqa  xmm1, [rsp+68h+var_38]
0x180002821  movdqa  xmm2, [rsp+68h+var_28]
0x180002827  movdqa  xmm3, [rsp+68h+var_18]
0x18000282d  mov     rcx, [rsp+68h+arg_0]
0x180002832  mov     rdx, [rsp+68h+arg_8]
0x180002837  mov     r8, [rsp+68h+arg_10]
0x18000283f  mov     r9, [rsp+68h+arg_18]
0x180002847  add     rsp, 68h
0x18000284b  jmp     short $+2
0x18000284d  jmp     rax
```
