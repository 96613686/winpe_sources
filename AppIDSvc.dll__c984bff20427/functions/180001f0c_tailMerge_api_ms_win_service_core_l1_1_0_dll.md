# __tailMerge_api_ms_win_service_core_l1_1_0_dll

- ea: `0x180001f0c`
- end: `0x180001f85`
- name: `__tailMerge_api_ms_win_service_core_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001f90`
- `0x180001fb0`

## callees

- `0x180001f0c`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_core_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001f0c  mov     [rsp+arg_0], rcx
0x180001f11  mov     [rsp+arg_8], rdx
0x180001f16  mov     [rsp+arg_10], r8
0x180001f1b  mov     [rsp+arg_18], r9
0x180001f20  sub     rsp, 68h
0x180001f24  movdqa  [rsp+68h+var_48], xmm0
0x180001f2a  movdqa  [rsp+68h+var_38], xmm1
0x180001f30  movdqa  [rsp+68h+var_28], xmm2
0x180001f36  movdqa  [rsp+68h+var_18], xmm3
0x180001f3c  mov     rdx, rax
0x180001f3f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_core_l1_1_0_dll
0x180001f46  call    __delayLoadHelper2
0x180001f4b  movdqa  xmm0, [rsp+68h+var_48]
0x180001f51  movdqa  xmm1, [rsp+68h+var_38]
0x180001f57  movdqa  xmm2, [rsp+68h+var_28]
0x180001f5d  movdqa  xmm3, [rsp+68h+var_18]
0x180001f63  mov     rcx, [rsp+68h+arg_0]
0x180001f68  mov     rdx, [rsp+68h+arg_8]
0x180001f6d  mov     r8, [rsp+68h+arg_10]
0x180001f75  mov     r9, [rsp+68h+arg_18]
0x180001f7d  add     rsp, 68h
0x180001f81  jmp     short $+2
0x180001f83  jmp     rax
```
