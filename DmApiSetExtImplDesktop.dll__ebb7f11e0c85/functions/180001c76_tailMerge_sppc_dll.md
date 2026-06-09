# __tailMerge_sppc_dll

- ea: `0x180001c76`
- end: `0x180001cef`
- name: `__tailMerge_sppc_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001cf5`
- `0x180001d07`
- `0x180001d19`
- `0x180001d2b`
- `0x180001d3d`
- `0x180001d4f`

## callees

- `0x180001c76`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_sppc_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_sppc_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c76  mov     [rsp+arg_0], rcx
0x180001c7b  mov     [rsp+arg_8], rdx
0x180001c80  mov     [rsp+arg_10], r8
0x180001c85  mov     [rsp+arg_18], r9
0x180001c8a  sub     rsp, 68h
0x180001c8e  movdqa  [rsp+68h+var_48], xmm0
0x180001c94  movdqa  [rsp+68h+var_38], xmm1
0x180001c9a  movdqa  [rsp+68h+var_28], xmm2
0x180001ca0  movdqa  [rsp+68h+var_18], xmm3
0x180001ca6  mov     rdx, rax
0x180001ca9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sppc_dll
0x180001cb0  call    __delayLoadHelper2
0x180001cb5  movdqa  xmm0, [rsp+68h+var_48]
0x180001cbb  movdqa  xmm1, [rsp+68h+var_38]
0x180001cc1  movdqa  xmm2, [rsp+68h+var_28]
0x180001cc7  movdqa  xmm3, [rsp+68h+var_18]
0x180001ccd  mov     rcx, [rsp+68h+arg_0]
0x180001cd2  mov     rdx, [rsp+68h+arg_8]
0x180001cd7  mov     r8, [rsp+68h+arg_10]
0x180001cdf  mov     r9, [rsp+68h+arg_18]
0x180001ce7  add     rsp, 68h
0x180001ceb  jmp     short $+2
0x180001ced  jmp     rax
```
