# __tailMerge_crypt32_dll

- ea: `0x180001fbc`
- end: `0x180002035`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002040`
- `0x180002060`
- `0x180002080`
- `0x180002270`
- `0x180002320`
- `0x180002340`
- `0x180002360`
- `0x180002380`
- `0x1800023a0`
- `0x1800023c0`

## callees

- `0x180001fbc`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001fbc  mov     [rsp+arg_0], rcx
0x180001fc1  mov     [rsp+arg_8], rdx
0x180001fc6  mov     [rsp+arg_10], r8
0x180001fcb  mov     [rsp+arg_18], r9
0x180001fd0  sub     rsp, 68h
0x180001fd4  movdqa  [rsp+68h+var_48], xmm0
0x180001fda  movdqa  [rsp+68h+var_38], xmm1
0x180001fe0  movdqa  [rsp+68h+var_28], xmm2
0x180001fe6  movdqa  [rsp+68h+var_18], xmm3
0x180001fec  mov     rdx, rax
0x180001fef  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180001ff6  call    __delayLoadHelper2
0x180001ffb  movdqa  xmm0, [rsp+68h+var_48]
0x180002001  movdqa  xmm1, [rsp+68h+var_38]
0x180002007  movdqa  xmm2, [rsp+68h+var_28]
0x18000200d  movdqa  xmm3, [rsp+68h+var_18]
0x180002013  mov     rcx, [rsp+68h+arg_0]
0x180002018  mov     rdx, [rsp+68h+arg_8]
0x18000201d  mov     r8, [rsp+68h+arg_10]
0x180002025  mov     r9, [rsp+68h+arg_18]
0x18000202d  add     rsp, 68h
0x180002031  jmp     short $+2
0x180002033  jmp     rax
```
