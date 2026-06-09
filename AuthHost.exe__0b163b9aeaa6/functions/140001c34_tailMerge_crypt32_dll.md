# __tailMerge_crypt32_dll

- ea: `0x140001c34`
- end: `0x140001cad`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001cb3`

## callees

- `0x140001c34`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001c34  mov     [rsp+arg_0], rcx
0x140001c39  mov     [rsp+arg_8], rdx
0x140001c3e  mov     [rsp+arg_10], r8
0x140001c43  mov     [rsp+arg_18], r9
0x140001c48  sub     rsp, 68h
0x140001c4c  movdqa  [rsp+68h+var_48], xmm0
0x140001c52  movdqa  [rsp+68h+var_38], xmm1
0x140001c58  movdqa  [rsp+68h+var_28], xmm2
0x140001c5e  movdqa  [rsp+68h+var_18], xmm3
0x140001c64  mov     rdx, rax
0x140001c67  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x140001c6e  call    __delayLoadHelper2
0x140001c73  movdqa  xmm0, [rsp+68h+var_48]
0x140001c79  movdqa  xmm1, [rsp+68h+var_38]
0x140001c7f  movdqa  xmm2, [rsp+68h+var_28]
0x140001c85  movdqa  xmm3, [rsp+68h+var_18]
0x140001c8b  mov     rcx, [rsp+68h+arg_0]
0x140001c90  mov     rdx, [rsp+68h+arg_8]
0x140001c95  mov     r8, [rsp+68h+arg_10]
0x140001c9d  mov     r9, [rsp+68h+arg_18]
0x140001ca5  add     rsp, 68h
0x140001ca9  jmp     short $+2
0x140001cab  jmp     rax
```
