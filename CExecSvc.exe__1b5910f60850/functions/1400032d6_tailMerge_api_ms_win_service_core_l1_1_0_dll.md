# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x1400032d6`
- end: `0x14000334f`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x140003355`
- `0x140003367`
- `0x140003379`

## callees

- `0x1400032d6`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400032d6  mov     [rsp+arg_0], rcx
0x1400032db  mov     [rsp+arg_8], rdx
0x1400032e0  mov     [rsp+arg_10], r8
0x1400032e5  mov     [rsp+arg_18], r9
0x1400032ea  sub     rsp, 68h
0x1400032ee  movdqa  [rsp+68h+var_48], xmm0
0x1400032f4  movdqa  [rsp+68h+var_38], xmm1
0x1400032fa  movdqa  [rsp+68h+var_28], xmm2
0x140003300  movdqa  [rsp+68h+var_18], xmm3
0x140003306  mov     rdx, rax
0x140003309  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x140003310  call    __delayLoadHelper2
0x140003315  movdqa  xmm0, [rsp+68h+var_48]
0x14000331b  movdqa  xmm1, [rsp+68h+var_38]
0x140003321  movdqa  xmm2, [rsp+68h+var_28]
0x140003327  movdqa  xmm3, [rsp+68h+var_18]
0x14000332d  mov     rcx, [rsp+68h+arg_0]
0x140003332  mov     rdx, [rsp+68h+arg_8]
0x140003337  mov     r8, [rsp+68h+arg_10]
0x14000333f  mov     r9, [rsp+68h+arg_18]
0x140003347  add     rsp, 68h
0x14000334b  jmp     short $+2
0x14000334d  jmp     rax
```
