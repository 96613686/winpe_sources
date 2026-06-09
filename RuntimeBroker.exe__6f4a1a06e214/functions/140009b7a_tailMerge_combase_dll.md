# __tailMerge_combase_dll

- ea: `0x140009b7a`
- end: `0x140009bf3`
- name: `__tailMerge_combase_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009bf9`
- `0x140009c0b`
- `0x140009c1d`
- `0x140009c2f`

## callees

- `0x140006ad0`
- `0x140009b7a`

## pseudocode

```c
__int64 __fastcall _tailMerge_combase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_combase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140009b7a  mov     [rsp+arg_0], rcx
0x140009b7f  mov     [rsp+arg_8], rdx
0x140009b84  mov     [rsp+arg_10], r8
0x140009b89  mov     [rsp+arg_18], r9
0x140009b8e  sub     rsp, 68h
0x140009b92  movdqa  [rsp+68h+var_48], xmm0
0x140009b98  movdqa  [rsp+68h+var_38], xmm1
0x140009b9e  movdqa  [rsp+68h+var_28], xmm2
0x140009ba4  movdqa  [rsp+68h+var_18], xmm3
0x140009baa  mov     rdx, rax
0x140009bad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_combase_dll
0x140009bb4  call    __delayLoadHelper2
0x140009bb9  movdqa  xmm0, [rsp+68h+var_48]
0x140009bbf  movdqa  xmm1, [rsp+68h+var_38]
0x140009bc5  movdqa  xmm2, [rsp+68h+var_28]
0x140009bcb  movdqa  xmm3, [rsp+68h+var_18]
0x140009bd1  mov     rcx, [rsp+68h+arg_0]
0x140009bd6  mov     rdx, [rsp+68h+arg_8]
0x140009bdb  mov     r8, [rsp+68h+arg_10]
0x140009be3  mov     r9, [rsp+68h+arg_18]
0x140009beb  add     rsp, 68h
0x140009bef  jmp     short $+2
0x140009bf1  jmp     rax
```
