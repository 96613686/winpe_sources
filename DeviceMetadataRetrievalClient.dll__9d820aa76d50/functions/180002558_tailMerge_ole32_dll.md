# __tailMerge_ole32_dll

- ea: `0x180002558`
- end: `0x1800025d1`
- name: `__tailMerge_ole32_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025d7`
- `0x1800025e9`
- `0x1800025fb`
- `0x18000260d`
- `0x1800026af`

## callees

- `0x180002558`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_ole32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ole32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002558  mov     [rsp+arg_0], rcx
0x18000255d  mov     [rsp+arg_8], rdx
0x180002562  mov     [rsp+arg_10], r8
0x180002567  mov     [rsp+arg_18], r9
0x18000256c  sub     rsp, 68h
0x180002570  movdqa  [rsp+68h+var_48], xmm0
0x180002576  movdqa  [rsp+68h+var_38], xmm1
0x18000257c  movdqa  [rsp+68h+var_28], xmm2
0x180002582  movdqa  [rsp+68h+var_18], xmm3
0x180002588  mov     rdx, rax
0x18000258b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ole32_dll
0x180002592  call    __delayLoadHelper2
0x180002597  movdqa  xmm0, [rsp+68h+var_48]
0x18000259d  movdqa  xmm1, [rsp+68h+var_38]
0x1800025a3  movdqa  xmm2, [rsp+68h+var_28]
0x1800025a9  movdqa  xmm3, [rsp+68h+var_18]
0x1800025af  mov     rcx, [rsp+68h+arg_0]
0x1800025b4  mov     rdx, [rsp+68h+arg_8]
0x1800025b9  mov     r8, [rsp+68h+arg_10]
0x1800025c1  mov     r9, [rsp+68h+arg_18]
0x1800025c9  add     rsp, 68h
0x1800025cd  jmp     short $+2
0x1800025cf  jmp     rax
```
