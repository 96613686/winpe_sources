# __tailMerge_dmcmnutils_dll

- ea: `0x140002550`
- end: `0x1400025c9`
- name: `__tailMerge_dmcmnutils_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400025cf`
- `0x1400025e1`
- `0x1400025f3`
- `0x140002605`

## callees

- `0x140002550`
- `0x14001a700`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmcmnutils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002550  mov     [rsp+arg_0], rcx
0x140002555  mov     [rsp+arg_8], rdx
0x14000255a  mov     [rsp+arg_10], r8
0x14000255f  mov     [rsp+arg_18], r9
0x140002564  sub     rsp, 68h
0x140002568  movdqa  [rsp+68h+var_48], xmm0
0x14000256e  movdqa  [rsp+68h+var_38], xmm1
0x140002574  movdqa  [rsp+68h+var_28], xmm2
0x14000257a  movdqa  [rsp+68h+var_18], xmm3
0x140002580  mov     rdx, rax
0x140002583  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmcmnutils_dll
0x14000258a  call    __delayLoadHelper2
0x14000258f  movdqa  xmm0, [rsp+68h+var_48]
0x140002595  movdqa  xmm1, [rsp+68h+var_38]
0x14000259b  movdqa  xmm2, [rsp+68h+var_28]
0x1400025a1  movdqa  xmm3, [rsp+68h+var_18]
0x1400025a7  mov     rcx, [rsp+68h+arg_0]
0x1400025ac  mov     rdx, [rsp+68h+arg_8]
0x1400025b1  mov     r8, [rsp+68h+arg_10]
0x1400025b9  mov     r9, [rsp+68h+arg_18]
0x1400025c1  add     rsp, 68h
0x1400025c5  jmp     short $+2
0x1400025c7  jmp     rax
```
