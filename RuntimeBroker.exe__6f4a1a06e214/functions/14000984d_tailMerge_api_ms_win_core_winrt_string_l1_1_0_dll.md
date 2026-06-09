# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x14000984d`
- end: `0x1400098c6`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400098cc`
- `0x1400099b1`
- `0x140009b14`
- `0x140009b38`

## callees

- `0x140006ad0`
- `0x14000984d`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000984d  mov     [rsp+arg_0], rcx
0x140009852  mov     [rsp+arg_8], rdx
0x140009857  mov     [rsp+arg_10], r8
0x14000985c  mov     [rsp+arg_18], r9
0x140009861  sub     rsp, 68h
0x140009865  movdqa  [rsp+68h+var_48], xmm0
0x14000986b  movdqa  [rsp+68h+var_38], xmm1
0x140009871  movdqa  [rsp+68h+var_28], xmm2
0x140009877  movdqa  [rsp+68h+var_18], xmm3
0x14000987d  mov     rdx, rax
0x140009880  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x140009887  call    __delayLoadHelper2
0x14000988c  movdqa  xmm0, [rsp+68h+var_48]
0x140009892  movdqa  xmm1, [rsp+68h+var_38]
0x140009898  movdqa  xmm2, [rsp+68h+var_28]
0x14000989e  movdqa  xmm3, [rsp+68h+var_18]
0x1400098a4  mov     rcx, [rsp+68h+arg_0]
0x1400098a9  mov     rdx, [rsp+68h+arg_8]
0x1400098ae  mov     r8, [rsp+68h+arg_10]
0x1400098b6  mov     r9, [rsp+68h+arg_18]
0x1400098be  add     rsp, 68h
0x1400098c2  jmp     short $+2
0x1400098c4  jmp     rax
```
