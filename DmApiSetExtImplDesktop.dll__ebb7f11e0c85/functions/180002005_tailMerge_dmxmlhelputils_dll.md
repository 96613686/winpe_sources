# __tailMerge_dmxmlhelputils_dll

- ea: `0x180002005`
- end: `0x18000207e`
- name: `__tailMerge_dmxmlhelputils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002084`

## callees

- `0x180002005`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmxmlhelputils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_dmxmlhelputils_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002005  mov     [rsp+arg_0], rcx
0x18000200a  mov     [rsp+arg_8], rdx
0x18000200f  mov     [rsp+arg_10], r8
0x180002014  mov     [rsp+arg_18], r9
0x180002019  sub     rsp, 68h
0x18000201d  movdqa  [rsp+68h+var_48], xmm0
0x180002023  movdqa  [rsp+68h+var_38], xmm1
0x180002029  movdqa  [rsp+68h+var_28], xmm2
0x18000202f  movdqa  [rsp+68h+var_18], xmm3
0x180002035  mov     rdx, rax
0x180002038  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmxmlhelputils_dll
0x18000203f  call    __delayLoadHelper2
0x180002044  movdqa  xmm0, [rsp+68h+var_48]
0x18000204a  movdqa  xmm1, [rsp+68h+var_38]
0x180002050  movdqa  xmm2, [rsp+68h+var_28]
0x180002056  movdqa  xmm3, [rsp+68h+var_18]
0x18000205c  mov     rcx, [rsp+68h+arg_0]
0x180002061  mov     rdx, [rsp+68h+arg_8]
0x180002066  mov     r8, [rsp+68h+arg_10]
0x18000206e  mov     r9, [rsp+68h+arg_18]
0x180002076  add     rsp, 68h
0x18000207a  jmp     short $+2
0x18000207c  jmp     rax
```
