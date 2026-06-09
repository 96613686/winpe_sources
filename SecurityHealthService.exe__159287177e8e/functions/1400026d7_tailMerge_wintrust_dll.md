# __tailMerge_wintrust_dll

- ea: `0x1400026d7`
- end: `0x140002750`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002756`
- `0x140002768`
- `0x14000277a`
- `0x14000278c`
- `0x14000279e`
- `0x1400027b0`
- `0x1400027c2`
- `0x1400027d4`
- `0x1400027e6`

## callees

- `0x1400026d7`
- `0x140011350`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400026d7  mov     [rsp+arg_0], rcx
0x1400026dc  mov     [rsp+arg_8], rdx
0x1400026e1  mov     [rsp+arg_10], r8
0x1400026e6  mov     [rsp+arg_18], r9
0x1400026eb  sub     rsp, 68h
0x1400026ef  movdqa  [rsp+68h+var_48], xmm0
0x1400026f5  movdqa  [rsp+68h+var_38], xmm1
0x1400026fb  movdqa  [rsp+68h+var_28], xmm2
0x140002701  movdqa  [rsp+68h+var_18], xmm3
0x140002707  mov     rdx, rax
0x14000270a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x140002711  call    __delayLoadHelper2
0x140002716  movdqa  xmm0, [rsp+68h+var_48]
0x14000271c  movdqa  xmm1, [rsp+68h+var_38]
0x140002722  movdqa  xmm2, [rsp+68h+var_28]
0x140002728  movdqa  xmm3, [rsp+68h+var_18]
0x14000272e  mov     rcx, [rsp+68h+arg_0]
0x140002733  mov     rdx, [rsp+68h+arg_8]
0x140002738  mov     r8, [rsp+68h+arg_10]
0x140002740  mov     r9, [rsp+68h+arg_18]
0x140002748  add     rsp, 68h
0x14000274c  jmp     short $+2
0x14000274e  jmp     rax
```
