# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180003152`
- end: `0x1800031cb`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800031d1`
- `0x1800031e3`
- `0x1800031f5`
- `0x180003207`

## callees

- `0x180003152`
- `0x180010f00`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180003152  mov     [rsp+arg_0], rcx
0x180003157  mov     [rsp+arg_8], rdx
0x18000315c  mov     [rsp+arg_10], r8
0x180003161  mov     [rsp+arg_18], r9
0x180003166  sub     rsp, 68h
0x18000316a  movdqa  [rsp+68h+var_48], xmm0
0x180003170  movdqa  [rsp+68h+var_38], xmm1
0x180003176  movdqa  [rsp+68h+var_28], xmm2
0x18000317c  movdqa  [rsp+68h+var_18], xmm3
0x180003182  mov     rdx, rax
0x180003185  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x18000318c  call    __delayLoadHelper2
0x180003191  movdqa  xmm0, [rsp+68h+var_48]
0x180003197  movdqa  xmm1, [rsp+68h+var_38]
0x18000319d  movdqa  xmm2, [rsp+68h+var_28]
0x1800031a3  movdqa  xmm3, [rsp+68h+var_18]
0x1800031a9  mov     rcx, [rsp+68h+arg_0]
0x1800031ae  mov     rdx, [rsp+68h+arg_8]
0x1800031b3  mov     r8, [rsp+68h+arg_10]
0x1800031bb  mov     r9, [rsp+68h+arg_18]
0x1800031c3  add     rsp, 68h
0x1800031c7  jmp     short $+2
0x1800031c9  jmp     rax
```
