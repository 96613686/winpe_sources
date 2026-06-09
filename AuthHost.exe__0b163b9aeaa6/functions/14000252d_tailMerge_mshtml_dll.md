# __tailMerge_mshtml_dll

- ea: `0x14000252d`
- end: `0x1400025a6`
- name: `__tailMerge_mshtml_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400025ac`

## callees

- `0x14000252d`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_mshtml_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mshtml_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000252d  mov     [rsp+arg_0], rcx
0x140002532  mov     [rsp+arg_8], rdx
0x140002537  mov     [rsp+arg_10], r8
0x14000253c  mov     [rsp+arg_18], r9
0x140002541  sub     rsp, 68h
0x140002545  movdqa  [rsp+68h+var_48], xmm0
0x14000254b  movdqa  [rsp+68h+var_38], xmm1
0x140002551  movdqa  [rsp+68h+var_28], xmm2
0x140002557  movdqa  [rsp+68h+var_18], xmm3
0x14000255d  mov     rdx, rax
0x140002560  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mshtml_dll
0x140002567  call    __delayLoadHelper2
0x14000256c  movdqa  xmm0, [rsp+68h+var_48]
0x140002572  movdqa  xmm1, [rsp+68h+var_38]
0x140002578  movdqa  xmm2, [rsp+68h+var_28]
0x14000257e  movdqa  xmm3, [rsp+68h+var_18]
0x140002584  mov     rcx, [rsp+68h+arg_0]
0x140002589  mov     rdx, [rsp+68h+arg_8]
0x14000258e  mov     r8, [rsp+68h+arg_10]
0x140002596  mov     r9, [rsp+68h+arg_18]
0x14000259e  add     rsp, 68h
0x1400025a2  jmp     short $+2
0x1400025a4  jmp     rax
```
