# __tailMerge_combase_dll

- ea: `0x140003fbe`
- end: `0x140004037`
- name: `__tailMerge_combase_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000403d`

## callees

- `0x1400023e0`
- `0x140003fbe`

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
0x140003fbe  mov     [rsp+arg_0], rcx
0x140003fc3  mov     [rsp+arg_8], rdx
0x140003fc8  mov     [rsp+arg_10], r8
0x140003fcd  mov     [rsp+arg_18], r9
0x140003fd2  sub     rsp, 68h
0x140003fd6  movdqa  [rsp+68h+var_48], xmm0
0x140003fdc  movdqa  [rsp+68h+var_38], xmm1
0x140003fe2  movdqa  [rsp+68h+var_28], xmm2
0x140003fe8  movdqa  [rsp+68h+var_18], xmm3
0x140003fee  mov     rdx, rax
0x140003ff1  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_combase_dll
0x140003ff8  call    __delayLoadHelper2
0x140003ffd  movdqa  xmm0, [rsp+68h+var_48]
0x140004003  movdqa  xmm1, [rsp+68h+var_38]
0x140004009  movdqa  xmm2, [rsp+68h+var_28]
0x14000400f  movdqa  xmm3, [rsp+68h+var_18]
0x140004015  mov     rcx, [rsp+68h+arg_0]
0x14000401a  mov     rdx, [rsp+68h+arg_8]
0x14000401f  mov     r8, [rsp+68h+arg_10]
0x140004027  mov     r9, [rsp+68h+arg_18]
0x14000402f  add     rsp, 68h
0x140004033  jmp     short $+2
0x140004035  jmp     rax
```
