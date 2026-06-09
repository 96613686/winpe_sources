# __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll

- ea: `0x1800024d6`
- end: `0x18000254f`
- name: `__tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002555`

## callees

- `0x1800024d6`
- `0x180011cc0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800024d6  mov     [rsp+arg_0], rcx
0x1800024db  mov     [rsp+arg_8], rdx
0x1800024e0  mov     [rsp+arg_10], r8
0x1800024e5  mov     [rsp+arg_18], r9
0x1800024ea  sub     rsp, 68h
0x1800024ee  movdqa  [rsp+68h+var_48], xmm0
0x1800024f4  movdqa  [rsp+68h+var_38], xmm1
0x1800024fa  movdqa  [rsp+68h+var_28], xmm2
0x180002500  movdqa  [rsp+68h+var_18], xmm3
0x180002506  mov     rdx, rax
0x180002509  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_session_wtsapi32_l1_1_0_dll
0x180002510  call    __delayLoadHelper2
0x180002515  movdqa  xmm0, [rsp+68h+var_48]
0x18000251b  movdqa  xmm1, [rsp+68h+var_38]
0x180002521  movdqa  xmm2, [rsp+68h+var_28]
0x180002527  movdqa  xmm3, [rsp+68h+var_18]
0x18000252d  mov     rcx, [rsp+68h+arg_0]
0x180002532  mov     rdx, [rsp+68h+arg_8]
0x180002537  mov     r8, [rsp+68h+arg_10]
0x18000253f  mov     r9, [rsp+68h+arg_18]
0x180002547  add     rsp, 68h
0x18000254b  jmp     short $+2
0x18000254d  jmp     rax
```
