# __tailMerge_profapi_dll

- ea: `0x14000421b`
- end: `0x140004294`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000429a`
- `0x1400042ac`
- `0x140004349`
- `0x140004471`

## callees

- `0x14000421b`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000421b  mov     [rsp+arg_0], rcx
0x140004220  mov     [rsp+arg_8], rdx
0x140004225  mov     [rsp+arg_10], r8
0x14000422a  mov     [rsp+arg_18], r9
0x14000422f  sub     rsp, 68h
0x140004233  movdqa  [rsp+68h+var_48], xmm0
0x140004239  movdqa  [rsp+68h+var_38], xmm1
0x14000423f  movdqa  [rsp+68h+var_28], xmm2
0x140004245  movdqa  [rsp+68h+var_18], xmm3
0x14000424b  mov     rdx, rax
0x14000424e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x140004255  call    __delayLoadHelper2
0x14000425a  movdqa  xmm0, [rsp+68h+var_48]
0x140004260  movdqa  xmm1, [rsp+68h+var_38]
0x140004266  movdqa  xmm2, [rsp+68h+var_28]
0x14000426c  movdqa  xmm3, [rsp+68h+var_18]
0x140004272  mov     rcx, [rsp+68h+arg_0]
0x140004277  mov     rdx, [rsp+68h+arg_8]
0x14000427c  mov     r8, [rsp+68h+arg_10]
0x140004284  mov     r9, [rsp+68h+arg_18]
0x14000428c  add     rsp, 68h
0x140004290  jmp     short $+2
0x140004292  jmp     rax
```
