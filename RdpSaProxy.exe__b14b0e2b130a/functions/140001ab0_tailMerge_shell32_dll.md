# __tailMerge_shell32_dll

- ea: `0x140001ab0`
- end: `0x140001b29`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001b2f`
- `0x140002566`

## callees

- `0x140001ab0`
- `0x140005600`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001ab0  mov     [rsp+arg_0], rcx
0x140001ab5  mov     [rsp+arg_8], rdx
0x140001aba  mov     [rsp+arg_10], r8
0x140001abf  mov     [rsp+arg_18], r9
0x140001ac4  sub     rsp, 68h
0x140001ac8  movdqa  [rsp+68h+var_48], xmm0
0x140001ace  movdqa  [rsp+68h+var_38], xmm1
0x140001ad4  movdqa  [rsp+68h+var_28], xmm2
0x140001ada  movdqa  [rsp+68h+var_18], xmm3
0x140001ae0  mov     rdx, rax
0x140001ae3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x140001aea  call    __delayLoadHelper2
0x140001aef  movdqa  xmm0, [rsp+68h+var_48]
0x140001af5  movdqa  xmm1, [rsp+68h+var_38]
0x140001afb  movdqa  xmm2, [rsp+68h+var_28]
0x140001b01  movdqa  xmm3, [rsp+68h+var_18]
0x140001b07  mov     rcx, [rsp+68h+arg_0]
0x140001b0c  mov     rdx, [rsp+68h+arg_8]
0x140001b11  mov     r8, [rsp+68h+arg_10]
0x140001b19  mov     r9, [rsp+68h+arg_18]
0x140001b21  add     rsp, 68h
0x140001b25  jmp     short $+2
0x140001b27  jmp     rax
```
