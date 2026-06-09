# __tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll

- ea: `0x18000a9ec`
- end: `0x18000aa65`
- name: `__tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000aa6b`
- `0x18000aa7d`
- `0x18000aa8f`

## callees

- `0x180001530`
- `0x18000a9ec`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventing_consumer_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_consumer_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a9ec  mov     [rsp+arg_0], rcx
0x18000a9f1  mov     [rsp+arg_8], rdx
0x18000a9f6  mov     [rsp+arg_10], r8
0x18000a9fb  mov     [rsp+arg_18], r9
0x18000aa00  sub     rsp, 68h
0x18000aa04  movdqa  [rsp+68h+var_48], xmm0
0x18000aa0a  movdqa  [rsp+68h+var_38], xmm1
0x18000aa10  movdqa  [rsp+68h+var_28], xmm2
0x18000aa16  movdqa  [rsp+68h+var_18], xmm3
0x18000aa1c  mov     rdx, rax
0x18000aa1f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_consumer_l1_1_0_dll
0x18000aa26  call    __delayLoadHelper2
0x18000aa2b  movdqa  xmm0, [rsp+68h+var_48]
0x18000aa31  movdqa  xmm1, [rsp+68h+var_38]
0x18000aa37  movdqa  xmm2, [rsp+68h+var_28]
0x18000aa3d  movdqa  xmm3, [rsp+68h+var_18]
0x18000aa43  mov     rcx, [rsp+68h+arg_0]
0x18000aa48  mov     rdx, [rsp+68h+arg_8]
0x18000aa4d  mov     r8, [rsp+68h+arg_10]
0x18000aa55  mov     r9, [rsp+68h+arg_18]
0x18000aa5d  add     rsp, 68h
0x18000aa61  jmp     short $+2
0x18000aa63  jmp     rax
```
