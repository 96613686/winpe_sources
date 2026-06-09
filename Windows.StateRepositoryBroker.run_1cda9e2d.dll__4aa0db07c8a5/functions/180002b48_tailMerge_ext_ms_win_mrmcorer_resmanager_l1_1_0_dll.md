# __tailMerge_ext_ms_win_mrmcorer_resmanager_l1_1_0_dll

- ea: `0x180002b48`
- end: `0x180002bc1`
- name: `__tailMerge_ext_ms_win_mrmcorer_resmanager_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002bc7`

## callees

- `0x180002b48`
- `0x18000a6d0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_mrmcorer_resmanager_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_mrmcorer_resmanager_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b48  mov     [rsp+arg_0], rcx
0x180002b4d  mov     [rsp+arg_8], rdx
0x180002b52  mov     [rsp+arg_10], r8
0x180002b57  mov     [rsp+arg_18], r9
0x180002b5c  sub     rsp, 68h
0x180002b60  movdqa  [rsp+68h+var_48], xmm0
0x180002b66  movdqa  [rsp+68h+var_38], xmm1
0x180002b6c  movdqa  [rsp+68h+var_28], xmm2
0x180002b72  movdqa  [rsp+68h+var_18], xmm3
0x180002b78  mov     rdx, rax
0x180002b7b  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_mrmcorer_resmanager_l1_1_0_dll
0x180002b82  call    __delayLoadHelper2
0x180002b87  movdqa  xmm0, [rsp+68h+var_48]
0x180002b8d  movdqa  xmm1, [rsp+68h+var_38]
0x180002b93  movdqa  xmm2, [rsp+68h+var_28]
0x180002b99  movdqa  xmm3, [rsp+68h+var_18]
0x180002b9f  mov     rcx, [rsp+68h+arg_0]
0x180002ba4  mov     rdx, [rsp+68h+arg_8]
0x180002ba9  mov     r8, [rsp+68h+arg_10]
0x180002bb1  mov     r9, [rsp+68h+arg_18]
0x180002bb9  add     rsp, 68h
0x180002bbd  jmp     short $+2
0x180002bbf  jmp     rax
```
