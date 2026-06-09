# __tailMerge_crypt32_dll

- ea: `0x14000264c`
- end: `0x1400026c5`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400026cb`

## callees

- `0x14000264c`
- `0x140011350`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000264c  mov     [rsp+arg_0], rcx
0x140002651  mov     [rsp+arg_8], rdx
0x140002656  mov     [rsp+arg_10], r8
0x14000265b  mov     [rsp+arg_18], r9
0x140002660  sub     rsp, 68h
0x140002664  movdqa  [rsp+68h+var_48], xmm0
0x14000266a  movdqa  [rsp+68h+var_38], xmm1
0x140002670  movdqa  [rsp+68h+var_28], xmm2
0x140002676  movdqa  [rsp+68h+var_18], xmm3
0x14000267c  mov     rdx, rax
0x14000267f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x140002686  call    __delayLoadHelper2
0x14000268b  movdqa  xmm0, [rsp+68h+var_48]
0x140002691  movdqa  xmm1, [rsp+68h+var_38]
0x140002697  movdqa  xmm2, [rsp+68h+var_28]
0x14000269d  movdqa  xmm3, [rsp+68h+var_18]
0x1400026a3  mov     rcx, [rsp+68h+arg_0]
0x1400026a8  mov     rdx, [rsp+68h+arg_8]
0x1400026ad  mov     r8, [rsp+68h+arg_10]
0x1400026b5  mov     r9, [rsp+68h+arg_18]
0x1400026bd  add     rsp, 68h
0x1400026c1  jmp     short $+2
0x1400026c3  jmp     rax
```
