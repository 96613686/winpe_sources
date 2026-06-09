# __tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll

- ea: `0x1800136e0`
- end: `0x180013759`
- name: `__tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001375f`
- `0x180013771`
- `0x180013783`
- `0x180013795`
- `0x1800137a7`
- `0x1800137b9`

## callees

- `0x18000af70`
- `0x1800136e0`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_winrt_string_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2(
              (const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll,
              v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800136e0  mov     [rsp+arg_0], rcx
0x1800136e5  mov     [rsp+arg_8], rdx
0x1800136ea  mov     [rsp+arg_10], r8
0x1800136ef  mov     [rsp+arg_18], r9
0x1800136f4  sub     rsp, 68h
0x1800136f8  movdqa  [rsp+68h+var_48], xmm0
0x1800136fe  movdqa  [rsp+68h+var_38], xmm1
0x180013704  movdqa  [rsp+68h+var_28], xmm2
0x18001370a  movdqa  [rsp+68h+var_18], xmm3
0x180013710  mov     rdx, rax
0x180013713  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_winrt_string_l1_1_0_dll
0x18001371a  call    __delayLoadHelper2
0x18001371f  movdqa  xmm0, [rsp+68h+var_48]
0x180013725  movdqa  xmm1, [rsp+68h+var_38]
0x18001372b  movdqa  xmm2, [rsp+68h+var_28]
0x180013731  movdqa  xmm3, [rsp+68h+var_18]
0x180013737  mov     rcx, [rsp+68h+arg_0]
0x18001373c  mov     rdx, [rsp+68h+arg_8]
0x180013741  mov     r8, [rsp+68h+arg_10]
0x180013749  mov     r9, [rsp+68h+arg_18]
0x180013751  add     rsp, 68h
0x180013755  jmp     short $+2
0x180013757  jmp     rax
```
