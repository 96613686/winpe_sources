# __tailMerge_xmllite_dll

- ea: `0x1800024cd`
- end: `0x180002546`
- name: `__tailMerge_xmllite_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000254c`

## callees

- `0x1800024cd`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_xmllite_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_xmllite_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024cd  mov     [rsp+arg_0], rcx
0x1800024d2  mov     [rsp+arg_8], rdx
0x1800024d7  mov     [rsp+arg_10], r8
0x1800024dc  mov     [rsp+arg_18], r9
0x1800024e1  sub     rsp, 68h
0x1800024e5  movdqa  [rsp+68h+var_48], xmm0
0x1800024eb  movdqa  [rsp+68h+var_38], xmm1
0x1800024f1  movdqa  [rsp+68h+var_28], xmm2
0x1800024f7  movdqa  [rsp+68h+var_18], xmm3
0x1800024fd  mov     rdx, rax
0x180002500  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_xmllite_dll
0x180002507  call    __delayLoadHelper2
0x18000250c  movdqa  xmm0, [rsp+68h+var_48]
0x180002512  movdqa  xmm1, [rsp+68h+var_38]
0x180002518  movdqa  xmm2, [rsp+68h+var_28]
0x18000251e  movdqa  xmm3, [rsp+68h+var_18]
0x180002524  mov     rcx, [rsp+68h+arg_0]
0x180002529  mov     rdx, [rsp+68h+arg_8]
0x18000252e  mov     r8, [rsp+68h+arg_10]
0x180002536  mov     r9, [rsp+68h+arg_18]
0x18000253e  add     rsp, 68h
0x180002542  jmp     short $+2
0x180002544  jmp     rax
```
