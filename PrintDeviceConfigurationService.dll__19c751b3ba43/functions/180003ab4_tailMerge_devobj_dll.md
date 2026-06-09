# __tailMerge_devobj_dll

- ea: `0x180003ab4`
- end: `0x180003b2d`
- name: `__tailMerge_devobj_dll`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003b33`
- `0x180003b45`
- `0x180003b57`
- `0x180003b69`

## callees

- `0x180003ab4`
- `0x180016410`

## pseudocode

```c
__int64 __fastcall _tailMerge_devobj_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_devobj_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003ab4  mov     [rsp+arg_0], rcx
0x180003ab9  mov     [rsp+arg_8], rdx
0x180003abe  mov     [rsp+arg_10], r8
0x180003ac3  mov     [rsp+arg_18], r9
0x180003ac8  sub     rsp, 68h
0x180003acc  movdqa  [rsp+68h+var_48], xmm0
0x180003ad2  movdqa  [rsp+68h+var_38], xmm1
0x180003ad8  movdqa  [rsp+68h+var_28], xmm2
0x180003ade  movdqa  [rsp+68h+var_18], xmm3
0x180003ae4  mov     rdx, rax
0x180003ae7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_devobj_dll
0x180003aee  call    __delayLoadHelper2
0x180003af3  movdqa  xmm0, [rsp+68h+var_48]
0x180003af9  movdqa  xmm1, [rsp+68h+var_38]
0x180003aff  movdqa  xmm2, [rsp+68h+var_28]
0x180003b05  movdqa  xmm3, [rsp+68h+var_18]
0x180003b0b  mov     rcx, [rsp+68h+arg_0]
0x180003b10  mov     rdx, [rsp+68h+arg_8]
0x180003b15  mov     r8, [rsp+68h+arg_10]
0x180003b1d  mov     r9, [rsp+68h+arg_18]
0x180003b25  add     rsp, 68h
0x180003b29  jmp     short $+2
0x180003b2b  jmp     rax
```
