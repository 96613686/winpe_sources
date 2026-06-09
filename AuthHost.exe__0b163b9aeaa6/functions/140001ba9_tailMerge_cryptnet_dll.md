# __tailMerge_cryptnet_dll

- ea: `0x140001ba9`
- end: `0x140001c22`
- name: `__tailMerge_cryptnet_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001c28`

## callees

- `0x140001ba9`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptnet_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptnet_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001ba9  mov     [rsp+arg_0], rcx
0x140001bae  mov     [rsp+arg_8], rdx
0x140001bb3  mov     [rsp+arg_10], r8
0x140001bb8  mov     [rsp+arg_18], r9
0x140001bbd  sub     rsp, 68h
0x140001bc1  movdqa  [rsp+68h+var_48], xmm0
0x140001bc7  movdqa  [rsp+68h+var_38], xmm1
0x140001bcd  movdqa  [rsp+68h+var_28], xmm2
0x140001bd3  movdqa  [rsp+68h+var_18], xmm3
0x140001bd9  mov     rdx, rax
0x140001bdc  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptnet_dll
0x140001be3  call    __delayLoadHelper2
0x140001be8  movdqa  xmm0, [rsp+68h+var_48]
0x140001bee  movdqa  xmm1, [rsp+68h+var_38]
0x140001bf4  movdqa  xmm2, [rsp+68h+var_28]
0x140001bfa  movdqa  xmm3, [rsp+68h+var_18]
0x140001c00  mov     rcx, [rsp+68h+arg_0]
0x140001c05  mov     rdx, [rsp+68h+arg_8]
0x140001c0a  mov     r8, [rsp+68h+arg_10]
0x140001c12  mov     r9, [rsp+68h+arg_18]
0x140001c1a  add     rsp, 68h
0x140001c1e  jmp     short $+2
0x140001c20  jmp     rax
```
