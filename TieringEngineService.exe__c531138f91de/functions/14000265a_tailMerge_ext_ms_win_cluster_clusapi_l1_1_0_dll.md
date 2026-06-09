# __tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll

- ea: `0x14000265a`
- end: `0x1400026d3`
- name: `__tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400026d9`
- `0x1400026eb`
- `0x1400026fd`

## callees

- `0x14000265a`
- `0x14003c720`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_cluster_clusapi_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000265a  mov     [rsp+arg_0], rcx
0x14000265f  mov     [rsp+arg_8], rdx
0x140002664  mov     [rsp+arg_10], r8
0x140002669  mov     [rsp+arg_18], r9
0x14000266e  sub     rsp, 68h
0x140002672  movdqa  [rsp+68h+var_48], xmm0
0x140002678  movdqa  [rsp+68h+var_38], xmm1
0x14000267e  movdqa  [rsp+68h+var_28], xmm2
0x140002684  movdqa  [rsp+68h+var_18], xmm3
0x14000268a  mov     rdx, rax
0x14000268d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_cluster_clusapi_l1_1_0_dll
0x140002694  call    __delayLoadHelper2
0x140002699  movdqa  xmm0, [rsp+68h+var_48]
0x14000269f  movdqa  xmm1, [rsp+68h+var_38]
0x1400026a5  movdqa  xmm2, [rsp+68h+var_28]
0x1400026ab  movdqa  xmm3, [rsp+68h+var_18]
0x1400026b1  mov     rcx, [rsp+68h+arg_0]
0x1400026b6  mov     rdx, [rsp+68h+arg_8]
0x1400026bb  mov     r8, [rsp+68h+arg_10]
0x1400026c3  mov     r9, [rsp+68h+arg_18]
0x1400026cb  add     rsp, 68h
0x1400026cf  jmp     short $+2
0x1400026d1  jmp     rax
```
