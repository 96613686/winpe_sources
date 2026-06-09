# __tailMerge_omadmapi_dll

- ea: `0x180001e83`
- end: `0x180001efc`
- name: `__tailMerge_omadmapi_dll`
- size: `121`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f02`
- `0x180001f14`
- `0x180001f26`
- `0x180001f38`
- `0x180001f4a`

## callees

- `0x180001e83`
- `0x180009a60`

## pseudocode

```c
__int64 __fastcall _tailMerge_omadmapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_omadmapi_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e83  mov     [rsp+arg_0], rcx
0x180001e88  mov     [rsp+arg_8], rdx
0x180001e8d  mov     [rsp+arg_10], r8
0x180001e92  mov     [rsp+arg_18], r9
0x180001e97  sub     rsp, 68h
0x180001e9b  movdqa  [rsp+68h+var_48], xmm0
0x180001ea1  movdqa  [rsp+68h+var_38], xmm1
0x180001ea7  movdqa  [rsp+68h+var_28], xmm2
0x180001ead  movdqa  [rsp+68h+var_18], xmm3
0x180001eb3  mov     rdx, rax
0x180001eb6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_omadmapi_dll
0x180001ebd  call    __delayLoadHelper2
0x180001ec2  movdqa  xmm0, [rsp+68h+var_48]
0x180001ec8  movdqa  xmm1, [rsp+68h+var_38]
0x180001ece  movdqa  xmm2, [rsp+68h+var_28]
0x180001ed4  movdqa  xmm3, [rsp+68h+var_18]
0x180001eda  mov     rcx, [rsp+68h+arg_0]
0x180001edf  mov     rdx, [rsp+68h+arg_8]
0x180001ee4  mov     r8, [rsp+68h+arg_10]
0x180001eec  mov     r9, [rsp+68h+arg_18]
0x180001ef4  add     rsp, 68h
0x180001ef8  jmp     short $+2
0x180001efa  jmp     rax
```
