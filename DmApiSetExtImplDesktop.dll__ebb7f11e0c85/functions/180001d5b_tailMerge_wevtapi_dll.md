# __tailMerge_wevtapi_dll

- ea: `0x180001d5b`
- end: `0x180001dd4`
- name: `__tailMerge_wevtapi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001dda`
- `0x180001dec`

## callees

- `0x180001d5b`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_wevtapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_wevtapi_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001d5b  mov     [rsp+arg_0], rcx
0x180001d60  mov     [rsp+arg_8], rdx
0x180001d65  mov     [rsp+arg_10], r8
0x180001d6a  mov     [rsp+arg_18], r9
0x180001d6f  sub     rsp, 68h
0x180001d73  movdqa  [rsp+68h+var_48], xmm0
0x180001d79  movdqa  [rsp+68h+var_38], xmm1
0x180001d7f  movdqa  [rsp+68h+var_28], xmm2
0x180001d85  movdqa  [rsp+68h+var_18], xmm3
0x180001d8b  mov     rdx, rax
0x180001d8e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wevtapi_dll
0x180001d95  call    __delayLoadHelper2
0x180001d9a  movdqa  xmm0, [rsp+68h+var_48]
0x180001da0  movdqa  xmm1, [rsp+68h+var_38]
0x180001da6  movdqa  xmm2, [rsp+68h+var_28]
0x180001dac  movdqa  xmm3, [rsp+68h+var_18]
0x180001db2  mov     rcx, [rsp+68h+arg_0]
0x180001db7  mov     rdx, [rsp+68h+arg_8]
0x180001dbc  mov     r8, [rsp+68h+arg_10]
0x180001dc4  mov     r9, [rsp+68h+arg_18]
0x180001dcc  add     rsp, 68h
0x180001dd0  jmp     short $+2
0x180001dd2  jmp     rax
```
