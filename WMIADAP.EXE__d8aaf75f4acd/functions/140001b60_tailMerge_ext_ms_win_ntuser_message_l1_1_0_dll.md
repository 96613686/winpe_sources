# __tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll

- ea: `0x140001b60`
- end: `0x140001bd9`
- name: `__tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001bdf`
- `0x140001bf1`
- `0x140001c03`
- `0x140001c15`

## callees

- `0x140001b60`
- `0x14000fc40`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_ntuser_message_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001b60  mov     [rsp+arg_0], rcx
0x140001b65  mov     [rsp+arg_8], rdx
0x140001b6a  mov     [rsp+arg_10], r8
0x140001b6f  mov     [rsp+arg_18], r9
0x140001b74  sub     rsp, 68h
0x140001b78  movdqa  [rsp+68h+var_48], xmm0
0x140001b7e  movdqa  [rsp+68h+var_38], xmm1
0x140001b84  movdqa  [rsp+68h+var_28], xmm2
0x140001b8a  movdqa  [rsp+68h+var_18], xmm3
0x140001b90  mov     rdx, rax
0x140001b93  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_ntuser_message_l1_1_0_dll
0x140001b9a  call    __delayLoadHelper2
0x140001b9f  movdqa  xmm0, [rsp+68h+var_48]
0x140001ba5  movdqa  xmm1, [rsp+68h+var_38]
0x140001bab  movdqa  xmm2, [rsp+68h+var_28]
0x140001bb1  movdqa  xmm3, [rsp+68h+var_18]
0x140001bb7  mov     rcx, [rsp+68h+arg_0]
0x140001bbc  mov     rdx, [rsp+68h+arg_8]
0x140001bc1  mov     r8, [rsp+68h+arg_10]
0x140001bc9  mov     r9, [rsp+68h+arg_18]
0x140001bd1  add     rsp, 68h
0x140001bd5  jmp     short $+2
0x140001bd7  jmp     rax
```
