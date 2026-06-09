# __tailMerge_oleaut32_dll

- ea: `0x140001aa0`
- end: `0x140001b19`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001b1f`
- `0x140001b31`
- `0x140001b43`
- `0x140001b55`
- `0x140001b67`
- `0x140001b79`
- `0x140001b8b`
- `0x140001b9d`

## callees

- `0x140001aa0`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001aa0  mov     [rsp+arg_0], rcx
0x140001aa5  mov     [rsp+arg_8], rdx
0x140001aaa  mov     [rsp+arg_10], r8
0x140001aaf  mov     [rsp+arg_18], r9
0x140001ab4  sub     rsp, 68h
0x140001ab8  movdqa  [rsp+68h+var_48], xmm0
0x140001abe  movdqa  [rsp+68h+var_38], xmm1
0x140001ac4  movdqa  [rsp+68h+var_28], xmm2
0x140001aca  movdqa  [rsp+68h+var_18], xmm3
0x140001ad0  mov     rdx, rax
0x140001ad3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140001ada  call    __delayLoadHelper2
0x140001adf  movdqa  xmm0, [rsp+68h+var_48]
0x140001ae5  movdqa  xmm1, [rsp+68h+var_38]
0x140001aeb  movdqa  xmm2, [rsp+68h+var_28]
0x140001af1  movdqa  xmm3, [rsp+68h+var_18]
0x140001af7  mov     rcx, [rsp+68h+arg_0]
0x140001afc  mov     rdx, [rsp+68h+arg_8]
0x140001b01  mov     r8, [rsp+68h+arg_10]
0x140001b09  mov     r9, [rsp+68h+arg_18]
0x140001b11  add     rsp, 68h
0x140001b15  jmp     short $+2
0x140001b17  jmp     rax
```
