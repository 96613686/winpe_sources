# __tailMerge_ws2_32_dll

- ea: `0x180094e4e`
- end: `0x180094ec7`
- name: `__tailMerge_ws2_32_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180094ecd`
- `0x180094edf`
- `0x180094ef1`
- `0x180094f03`

## callees

- `0x180094e4e`
- `0x1800a3fe0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ws2_32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ws2_32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180094e4e  mov     [rsp+arg_0], rcx
0x180094e53  mov     [rsp+arg_8], rdx
0x180094e58  mov     [rsp+arg_10], r8
0x180094e5d  mov     [rsp+arg_18], r9
0x180094e62  sub     rsp, 68h
0x180094e66  movdqa  [rsp+68h+var_48], xmm0
0x180094e6c  movdqa  [rsp+68h+var_38], xmm1
0x180094e72  movdqa  [rsp+68h+var_28], xmm2
0x180094e78  movdqa  [rsp+68h+var_18], xmm3
0x180094e7e  mov     rdx, rax
0x180094e81  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ws2_32_dll
0x180094e88  call    __delayLoadHelper2
0x180094e8d  movdqa  xmm0, [rsp+68h+var_48]
0x180094e93  movdqa  xmm1, [rsp+68h+var_38]
0x180094e99  movdqa  xmm2, [rsp+68h+var_28]
0x180094e9f  movdqa  xmm3, [rsp+68h+var_18]
0x180094ea5  mov     rcx, [rsp+68h+arg_0]
0x180094eaa  mov     rdx, [rsp+68h+arg_8]
0x180094eaf  mov     r8, [rsp+68h+arg_10]
0x180094eb7  mov     r9, [rsp+68h+arg_18]
0x180094ebf  add     rsp, 68h
0x180094ec3  jmp     short $+2
0x180094ec5  jmp     rax
```
