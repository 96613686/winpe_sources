# __tailMerge_api_ms_win_service_winsvc_l1_1_0_dll

- ea: `0x1800021cc`
- end: `0x180002245`
- name: `__tailMerge_api_ms_win_service_winsvc_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002250`

## callees

- `0x1800021cc`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_service_winsvc_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800021cc  mov     [rsp+arg_0], rcx
0x1800021d1  mov     [rsp+arg_8], rdx
0x1800021d6  mov     [rsp+arg_10], r8
0x1800021db  mov     [rsp+arg_18], r9
0x1800021e0  sub     rsp, 68h
0x1800021e4  movdqa  [rsp+68h+var_48], xmm0
0x1800021ea  movdqa  [rsp+68h+var_38], xmm1
0x1800021f0  movdqa  [rsp+68h+var_28], xmm2
0x1800021f6  movdqa  [rsp+68h+var_18], xmm3
0x1800021fc  mov     rdx, rax
0x1800021ff  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_service_winsvc_l1_1_0_dll
0x180002206  call    __delayLoadHelper2
0x18000220b  movdqa  xmm0, [rsp+68h+var_48]
0x180002211  movdqa  xmm1, [rsp+68h+var_38]
0x180002217  movdqa  xmm2, [rsp+68h+var_28]
0x18000221d  movdqa  xmm3, [rsp+68h+var_18]
0x180002223  mov     rcx, [rsp+68h+arg_0]
0x180002228  mov     rdx, [rsp+68h+arg_8]
0x18000222d  mov     r8, [rsp+68h+arg_10]
0x180002235  mov     r9, [rsp+68h+arg_18]
0x18000223d  add     rsp, 68h
0x180002241  jmp     short $+2
0x180002243  jmp     rax
```
