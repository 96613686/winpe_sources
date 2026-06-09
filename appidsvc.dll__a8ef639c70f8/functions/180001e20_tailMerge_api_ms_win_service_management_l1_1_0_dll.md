# __tailMerge_api_ms_win_service_management_l1_1_0_dll

- ea: `0x180001e20`
- end: `0x180001e99`
- name: `__tailMerge_api_ms_win_service_management_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001ea0`
- `0x180001ec0`
- `0x180001ee0`
- `0x180001f00`

## callees

- `0x180001e20`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_management_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001e20  mov     [rsp+arg_0], rcx
0x180001e25  mov     [rsp+arg_8], rdx
0x180001e2a  mov     [rsp+arg_10], r8
0x180001e2f  mov     [rsp+arg_18], r9
0x180001e34  sub     rsp, 68h
0x180001e38  movdqa  [rsp+68h+var_48], xmm0
0x180001e3e  movdqa  [rsp+68h+var_38], xmm1
0x180001e44  movdqa  [rsp+68h+var_28], xmm2
0x180001e4a  movdqa  [rsp+68h+var_18], xmm3
0x180001e50  mov     rdx, rax
0x180001e53  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_management_l1_1_0_dll
0x180001e5a  call    __delayLoadHelper2
0x180001e5f  movdqa  xmm0, [rsp+68h+var_48]
0x180001e65  movdqa  xmm1, [rsp+68h+var_38]
0x180001e6b  movdqa  xmm2, [rsp+68h+var_28]
0x180001e71  movdqa  xmm3, [rsp+68h+var_18]
0x180001e77  mov     rcx, [rsp+68h+arg_0]
0x180001e7c  mov     rdx, [rsp+68h+arg_8]
0x180001e81  mov     r8, [rsp+68h+arg_10]
0x180001e89  mov     r9, [rsp+68h+arg_18]
0x180001e91  add     rsp, 68h
0x180001e95  jmp     short $+2
0x180001e97  jmp     rax
```
