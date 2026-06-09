# __tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll

- ea: `0x180013a16`
- end: `0x180013a8f`
- name: `__tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013a95`

## callees

- `0x180010e10`
- `0x180013a16`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_bicltapi_l1_1_6_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_bicltapi_l1_1_6_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013a16  mov     [rsp+arg_0], rcx
0x180013a1b  mov     [rsp+arg_8], rdx
0x180013a20  mov     [rsp+arg_10], r8
0x180013a25  mov     [rsp+arg_18], r9
0x180013a2a  sub     rsp, 68h
0x180013a2e  movdqa  [rsp+68h+var_48], xmm0
0x180013a34  movdqa  [rsp+68h+var_38], xmm1
0x180013a3a  movdqa  [rsp+68h+var_28], xmm2
0x180013a40  movdqa  [rsp+68h+var_18], xmm3
0x180013a46  mov     rdx, rax
0x180013a49  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_bicltapi_l1_1_6_dll
0x180013a50  call    __delayLoadHelper2
0x180013a55  movdqa  xmm0, [rsp+68h+var_48]
0x180013a5b  movdqa  xmm1, [rsp+68h+var_38]
0x180013a61  movdqa  xmm2, [rsp+68h+var_28]
0x180013a67  movdqa  xmm3, [rsp+68h+var_18]
0x180013a6d  mov     rcx, [rsp+68h+arg_0]
0x180013a72  mov     rdx, [rsp+68h+arg_8]
0x180013a77  mov     r8, [rsp+68h+arg_10]
0x180013a7f  mov     r9, [rsp+68h+arg_18]
0x180013a87  add     rsp, 68h
0x180013a8b  jmp     short $+2
0x180013a8d  jmp     rax
```
