# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x18000f326`
- end: `0x18000f39f`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000f3a5`
- `0x18000f3b7`

## callees

- `0x18000a5e0`
- `0x18000f326`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f326  mov     [rsp+arg_0], rcx
0x18000f32b  mov     [rsp+arg_8], rdx
0x18000f330  mov     [rsp+arg_10], r8
0x18000f335  mov     [rsp+arg_18], r9
0x18000f33a  sub     rsp, 68h
0x18000f33e  movdqa  [rsp+68h+var_48], xmm0
0x18000f344  movdqa  [rsp+68h+var_38], xmm1
0x18000f34a  movdqa  [rsp+68h+var_28], xmm2
0x18000f350  movdqa  [rsp+68h+var_18], xmm3
0x18000f356  mov     rdx, rax
0x18000f359  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x18000f360  call    __delayLoadHelper2
0x18000f365  movdqa  xmm0, [rsp+68h+var_48]
0x18000f36b  movdqa  xmm1, [rsp+68h+var_38]
0x18000f371  movdqa  xmm2, [rsp+68h+var_28]
0x18000f377  movdqa  xmm3, [rsp+68h+var_18]
0x18000f37d  mov     rcx, [rsp+68h+arg_0]
0x18000f382  mov     rdx, [rsp+68h+arg_8]
0x18000f387  mov     r8, [rsp+68h+arg_10]
0x18000f38f  mov     r9, [rsp+68h+arg_18]
0x18000f397  add     rsp, 68h
0x18000f39b  jmp     short $+2
0x18000f39d  jmp     rax
```
