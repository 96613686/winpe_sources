# __tailMerge_dismapi_dll

- ea: `0x180002b8e`
- end: `0x180002c07`
- name: `__tailMerge_dismapi_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c0d`
- `0x180002c1f`
- `0x180002c31`
- `0x180002c43`
- `0x180002c55`
- `0x180002c67`

## callees

- `0x180002b8e`
- `0x180016410`

## pseudocode

```c
__int64 __fastcall _tailMerge_dismapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_dismapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b8e  mov     [rsp+arg_0], rcx
0x180002b93  mov     [rsp+arg_8], rdx
0x180002b98  mov     [rsp+arg_10], r8
0x180002b9d  mov     [rsp+arg_18], r9
0x180002ba2  sub     rsp, 68h
0x180002ba6  movdqa  [rsp+68h+var_48], xmm0
0x180002bac  movdqa  [rsp+68h+var_38], xmm1
0x180002bb2  movdqa  [rsp+68h+var_28], xmm2
0x180002bb8  movdqa  [rsp+68h+var_18], xmm3
0x180002bbe  mov     rdx, rax
0x180002bc1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dismapi_dll
0x180002bc8  call    __delayLoadHelper2
0x180002bcd  movdqa  xmm0, [rsp+68h+var_48]
0x180002bd3  movdqa  xmm1, [rsp+68h+var_38]
0x180002bd9  movdqa  xmm2, [rsp+68h+var_28]
0x180002bdf  movdqa  xmm3, [rsp+68h+var_18]
0x180002be5  mov     rcx, [rsp+68h+arg_0]
0x180002bea  mov     rdx, [rsp+68h+arg_8]
0x180002bef  mov     r8, [rsp+68h+arg_10]
0x180002bf7  mov     r9, [rsp+68h+arg_18]
0x180002bff  add     rsp, 68h
0x180002c03  jmp     short $+2
0x180002c05  jmp     rax
```
