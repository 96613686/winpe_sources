# __tailMerge_shlwapi_dll

- ea: `0x1800022a9`
- end: `0x180002322`
- name: `__tailMerge_shlwapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002328`

## callees

- `0x1800022a9`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_shlwapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shlwapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022a9  mov     [rsp+arg_0], rcx
0x1800022ae  mov     [rsp+arg_8], rdx
0x1800022b3  mov     [rsp+arg_10], r8
0x1800022b8  mov     [rsp+arg_18], r9
0x1800022bd  sub     rsp, 68h
0x1800022c1  movdqa  [rsp+68h+var_48], xmm0
0x1800022c7  movdqa  [rsp+68h+var_38], xmm1
0x1800022cd  movdqa  [rsp+68h+var_28], xmm2
0x1800022d3  movdqa  [rsp+68h+var_18], xmm3
0x1800022d9  mov     rdx, rax
0x1800022dc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shlwapi_dll
0x1800022e3  call    __delayLoadHelper2
0x1800022e8  movdqa  xmm0, [rsp+68h+var_48]
0x1800022ee  movdqa  xmm1, [rsp+68h+var_38]
0x1800022f4  movdqa  xmm2, [rsp+68h+var_28]
0x1800022fa  movdqa  xmm3, [rsp+68h+var_18]
0x180002300  mov     rcx, [rsp+68h+arg_0]
0x180002305  mov     rdx, [rsp+68h+arg_8]
0x18000230a  mov     r8, [rsp+68h+arg_10]
0x180002312  mov     r9, [rsp+68h+arg_18]
0x18000231a  add     rsp, 68h
0x18000231e  jmp     short $+2
0x180002320  jmp     rax
```
