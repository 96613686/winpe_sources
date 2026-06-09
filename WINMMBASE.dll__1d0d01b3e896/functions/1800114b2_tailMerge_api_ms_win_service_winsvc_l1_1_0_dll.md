# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x1800114b2`
- end: `0x18001152b`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180011531`

## callees

- `0x18000f240`
- `0x1800114b2`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800114b2  mov     [rsp+arg_0], rcx
0x1800114b7  mov     [rsp+arg_8], rdx
0x1800114bc  mov     [rsp+arg_10], r8
0x1800114c1  mov     [rsp+arg_18], r9
0x1800114c6  sub     rsp, 68h
0x1800114ca  movdqa  [rsp+68h+var_48], xmm0
0x1800114d0  movdqa  [rsp+68h+var_38], xmm1
0x1800114d6  movdqa  [rsp+68h+var_28], xmm2
0x1800114dc  movdqa  [rsp+68h+var_18], xmm3
0x1800114e2  mov     rdx, rax
0x1800114e5  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x1800114ec  call    __delayLoadHelper2
0x1800114f1  movdqa  xmm0, [rsp+68h+var_48]
0x1800114f7  movdqa  xmm1, [rsp+68h+var_38]
0x1800114fd  movdqa  xmm2, [rsp+68h+var_28]
0x180011503  movdqa  xmm3, [rsp+68h+var_18]
0x180011509  mov     rcx, [rsp+68h+arg_0]
0x18001150e  mov     rdx, [rsp+68h+arg_8]
0x180011513  mov     r8, [rsp+68h+arg_10]
0x18001151b  mov     r9, [rsp+68h+arg_18]
0x180011523  add     rsp, 68h
0x180011527  jmp     short $+2
0x180011529  jmp     rax
```
