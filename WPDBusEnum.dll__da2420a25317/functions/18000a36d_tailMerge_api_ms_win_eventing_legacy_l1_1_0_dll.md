# __tailMerge_api_ms_win_eventing_legacy_l1_1_0_dll

- ea: `0x18000a36d`
- end: `0x18000a3e6`
- name: `__tailMerge_api_ms_win_eventing_legacy_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a3ec`

## callees

- `0x180006050`
- `0x18000a36d`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_eventing_legacy_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_legacy_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000a36d  mov     [rsp+arg_0], rcx
0x18000a372  mov     [rsp+arg_8], rdx
0x18000a377  mov     [rsp+arg_10], r8
0x18000a37c  mov     [rsp+arg_18], r9
0x18000a381  sub     rsp, 68h
0x18000a385  movdqa  [rsp+68h+var_48], xmm0
0x18000a38b  movdqa  [rsp+68h+var_38], xmm1
0x18000a391  movdqa  [rsp+68h+var_28], xmm2
0x18000a397  movdqa  [rsp+68h+var_18], xmm3
0x18000a39d  mov     rdx, rax
0x18000a3a0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_eventing_legacy_l1_1_0_dll
0x18000a3a7  call    __delayLoadHelper2
0x18000a3ac  movdqa  xmm0, [rsp+68h+var_48]
0x18000a3b2  movdqa  xmm1, [rsp+68h+var_38]
0x18000a3b8  movdqa  xmm2, [rsp+68h+var_28]
0x18000a3be  movdqa  xmm3, [rsp+68h+var_18]
0x18000a3c4  mov     rcx, [rsp+68h+arg_0]
0x18000a3c9  mov     rdx, [rsp+68h+arg_8]
0x18000a3ce  mov     r8, [rsp+68h+arg_10]
0x18000a3d6  mov     r9, [rsp+68h+arg_18]
0x18000a3de  add     rsp, 68h
0x18000a3e2  jmp     short $+2
0x18000a3e4  jmp     rax
```
