# __tailMerge_rasapi32_dll

- ea: `0x180002ab5`
- end: `0x180002b2e`
- name: `__tailMerge_rasapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b34`

## callees

- `0x180002ab5`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_rasapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rasapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002ab5  mov     [rsp+arg_0], rcx
0x180002aba  mov     [rsp+arg_8], rdx
0x180002abf  mov     [rsp+arg_10], r8
0x180002ac4  mov     [rsp+arg_18], r9
0x180002ac9  sub     rsp, 68h
0x180002acd  movdqa  [rsp+68h+var_48], xmm0
0x180002ad3  movdqa  [rsp+68h+var_38], xmm1
0x180002ad9  movdqa  [rsp+68h+var_28], xmm2
0x180002adf  movdqa  [rsp+68h+var_18], xmm3
0x180002ae5  mov     rdx, rax
0x180002ae8  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rasapi32_dll
0x180002aef  call    __delayLoadHelper2
0x180002af4  movdqa  xmm0, [rsp+68h+var_48]
0x180002afa  movdqa  xmm1, [rsp+68h+var_38]
0x180002b00  movdqa  xmm2, [rsp+68h+var_28]
0x180002b06  movdqa  xmm3, [rsp+68h+var_18]
0x180002b0c  mov     rcx, [rsp+68h+arg_0]
0x180002b11  mov     rdx, [rsp+68h+arg_8]
0x180002b16  mov     r8, [rsp+68h+arg_10]
0x180002b1e  mov     r9, [rsp+68h+arg_18]
0x180002b26  add     rsp, 68h
0x180002b2a  jmp     short $+2
0x180002b2c  jmp     rax
```
