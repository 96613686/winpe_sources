# __tailMerge_wintrust_dll

- ea: `0x18000268f`
- end: `0x180002708`
- name: `__tailMerge_wintrust_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000270e`
- `0x180002720`
- `0x180002732`
- `0x180002744`

## callees

- `0x18000268f`
- `0x180014100`

## pseudocode

```c
__int64 __fastcall _tailMerge_wintrust_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wintrust_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000268f  mov     [rsp+arg_0], rcx
0x180002694  mov     [rsp+arg_8], rdx
0x180002699  mov     [rsp+arg_10], r8
0x18000269e  mov     [rsp+arg_18], r9
0x1800026a3  sub     rsp, 68h
0x1800026a7  movdqa  [rsp+68h+var_48], xmm0
0x1800026ad  movdqa  [rsp+68h+var_38], xmm1
0x1800026b3  movdqa  [rsp+68h+var_28], xmm2
0x1800026b9  movdqa  [rsp+68h+var_18], xmm3
0x1800026bf  mov     rdx, rax
0x1800026c2  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wintrust_dll
0x1800026c9  call    __delayLoadHelper2
0x1800026ce  movdqa  xmm0, [rsp+68h+var_48]
0x1800026d4  movdqa  xmm1, [rsp+68h+var_38]
0x1800026da  movdqa  xmm2, [rsp+68h+var_28]
0x1800026e0  movdqa  xmm3, [rsp+68h+var_18]
0x1800026e6  mov     rcx, [rsp+68h+arg_0]
0x1800026eb  mov     rdx, [rsp+68h+arg_8]
0x1800026f0  mov     r8, [rsp+68h+arg_10]
0x1800026f8  mov     r9, [rsp+68h+arg_18]
0x180002700  add     rsp, 68h
0x180002704  jmp     short $+2
0x180002706  jmp     rax
```
