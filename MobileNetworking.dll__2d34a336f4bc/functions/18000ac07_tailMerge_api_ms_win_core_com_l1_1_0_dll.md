# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x18000ac07`
- end: `0x18000ac80`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac86`
- `0x18000ac98`
- `0x18000acaa`
- `0x18000adb3`

## callees

- `0x180007cd0`
- `0x18000ac07`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ac07  mov     [rsp+arg_0], rcx
0x18000ac0c  mov     [rsp+arg_8], rdx
0x18000ac11  mov     [rsp+arg_10], r8
0x18000ac16  mov     [rsp+arg_18], r9
0x18000ac1b  sub     rsp, 68h
0x18000ac1f  movdqa  [rsp+68h+var_48], xmm0
0x18000ac25  movdqa  [rsp+68h+var_38], xmm1
0x18000ac2b  movdqa  [rsp+68h+var_28], xmm2
0x18000ac31  movdqa  [rsp+68h+var_18], xmm3
0x18000ac37  mov     rdx, rax
0x18000ac3a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x18000ac41  call    __delayLoadHelper2
0x18000ac46  movdqa  xmm0, [rsp+68h+var_48]
0x18000ac4c  movdqa  xmm1, [rsp+68h+var_38]
0x18000ac52  movdqa  xmm2, [rsp+68h+var_28]
0x18000ac58  movdqa  xmm3, [rsp+68h+var_18]
0x18000ac5e  mov     rcx, [rsp+68h+arg_0]
0x18000ac63  mov     rdx, [rsp+68h+arg_8]
0x18000ac68  mov     r8, [rsp+68h+arg_10]
0x18000ac70  mov     r9, [rsp+68h+arg_18]
0x18000ac78  add     rsp, 68h
0x18000ac7c  jmp     short $+2
0x18000ac7e  jmp     rax
```
