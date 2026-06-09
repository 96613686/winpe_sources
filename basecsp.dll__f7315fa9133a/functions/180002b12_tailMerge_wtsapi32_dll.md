# __tailMerge_wtsapi32_dll

- ea: `0x180002b12`
- end: `0x180002b8b`
- name: `__tailMerge_wtsapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b91`
- `0x180002ba3`

## callees

- `0x180002b12`
- `0x18002cea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_wtsapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b12  mov     [rsp+arg_0], rcx
0x180002b17  mov     [rsp+arg_8], rdx
0x180002b1c  mov     [rsp+arg_10], r8
0x180002b21  mov     [rsp+arg_18], r9
0x180002b26  sub     rsp, 68h
0x180002b2a  movdqa  [rsp+68h+var_48], xmm0
0x180002b30  movdqa  [rsp+68h+var_38], xmm1
0x180002b36  movdqa  [rsp+68h+var_28], xmm2
0x180002b3c  movdqa  [rsp+68h+var_18], xmm3
0x180002b42  mov     rdx, rax
0x180002b45  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wtsapi32_dll
0x180002b4c  call    __delayLoadHelper2
0x180002b51  movdqa  xmm0, [rsp+68h+var_48]
0x180002b57  movdqa  xmm1, [rsp+68h+var_38]
0x180002b5d  movdqa  xmm2, [rsp+68h+var_28]
0x180002b63  movdqa  xmm3, [rsp+68h+var_18]
0x180002b69  mov     rcx, [rsp+68h+arg_0]
0x180002b6e  mov     rdx, [rsp+68h+arg_8]
0x180002b73  mov     r8, [rsp+68h+arg_10]
0x180002b7b  mov     r9, [rsp+68h+arg_18]
0x180002b83  add     rsp, 68h
0x180002b87  jmp     short $+2
0x180002b89  jmp     rax
```
