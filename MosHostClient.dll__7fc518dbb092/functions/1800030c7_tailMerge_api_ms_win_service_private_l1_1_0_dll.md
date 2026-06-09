# __tailMerge_api_ms_win_service_private_l1_1_0_dll

- ea: `0x1800030c7`
- end: `0x180003140`
- name: `__tailMerge_api_ms_win_service_private_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003146`

## callees

- `0x1800030c7`
- `0x180010f00`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_private_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800030c7  mov     [rsp+arg_0], rcx
0x1800030cc  mov     [rsp+arg_8], rdx
0x1800030d1  mov     [rsp+arg_10], r8
0x1800030d6  mov     [rsp+arg_18], r9
0x1800030db  sub     rsp, 68h
0x1800030df  movdqa  [rsp+68h+var_48], xmm0
0x1800030e5  movdqa  [rsp+68h+var_38], xmm1
0x1800030eb  movdqa  [rsp+68h+var_28], xmm2
0x1800030f1  movdqa  [rsp+68h+var_18], xmm3
0x1800030f7  mov     rdx, rax
0x1800030fa  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_private_l1_1_0_dll
0x180003101  call    __delayLoadHelper2
0x180003106  movdqa  xmm0, [rsp+68h+var_48]
0x18000310c  movdqa  xmm1, [rsp+68h+var_38]
0x180003112  movdqa  xmm2, [rsp+68h+var_28]
0x180003118  movdqa  xmm3, [rsp+68h+var_18]
0x18000311e  mov     rcx, [rsp+68h+arg_0]
0x180003123  mov     rdx, [rsp+68h+arg_8]
0x180003128  mov     r8, [rsp+68h+arg_10]
0x180003130  mov     r9, [rsp+68h+arg_18]
0x180003138  add     rsp, 68h
0x18000313c  jmp     short $+2
0x18000313e  jmp     rax
```
