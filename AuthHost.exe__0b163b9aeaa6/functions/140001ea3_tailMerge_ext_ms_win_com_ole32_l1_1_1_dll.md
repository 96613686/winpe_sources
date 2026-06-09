# __tailMerge_ext_ms_win_com_ole32_l1_1_1_dll

- ea: `0x140001ea3`
- end: `0x140001f1c`
- name: `__tailMerge_ext_ms_win_com_ole32_l1_1_1_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001f22`

## callees

- `0x140001ea3`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_com_ole32_l1_1_1_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_com_ole32_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001ea3  mov     [rsp+arg_0], rcx
0x140001ea8  mov     [rsp+arg_8], rdx
0x140001ead  mov     [rsp+arg_10], r8
0x140001eb2  mov     [rsp+arg_18], r9
0x140001eb7  sub     rsp, 68h
0x140001ebb  movdqa  [rsp+68h+var_48], xmm0
0x140001ec1  movdqa  [rsp+68h+var_38], xmm1
0x140001ec7  movdqa  [rsp+68h+var_28], xmm2
0x140001ecd  movdqa  [rsp+68h+var_18], xmm3
0x140001ed3  mov     rdx, rax
0x140001ed6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_com_ole32_l1_1_1_dll
0x140001edd  call    __delayLoadHelper2
0x140001ee2  movdqa  xmm0, [rsp+68h+var_48]
0x140001ee8  movdqa  xmm1, [rsp+68h+var_38]
0x140001eee  movdqa  xmm2, [rsp+68h+var_28]
0x140001ef4  movdqa  xmm3, [rsp+68h+var_18]
0x140001efa  mov     rcx, [rsp+68h+arg_0]
0x140001eff  mov     rdx, [rsp+68h+arg_8]
0x140001f04  mov     r8, [rsp+68h+arg_10]
0x140001f0c  mov     r9, [rsp+68h+arg_18]
0x140001f14  add     rsp, 68h
0x140001f18  jmp     short $+2
0x140001f1a  jmp     rax
```
