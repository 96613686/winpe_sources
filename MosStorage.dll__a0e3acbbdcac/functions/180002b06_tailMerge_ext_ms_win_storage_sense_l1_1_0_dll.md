# __tailMerge_ext_ms_win_storage_sense_l1_1_0_dll

- ea: `0x180002b06`
- end: `0x180002b7f`
- name: `__tailMerge_ext_ms_win_storage_sense_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b85`
- `0x180002b97`
- `0x180002ba9`
- `0x180002bbb`
- `0x180002bcd`
- `0x180002bdf`
- `0x180002bf1`

## callees

- `0x180002b06`
- `0x18000e1a0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_storage_sense_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b06  mov     [rsp+arg_0], rcx
0x180002b0b  mov     [rsp+arg_8], rdx
0x180002b10  mov     [rsp+arg_10], r8
0x180002b15  mov     [rsp+arg_18], r9
0x180002b1a  sub     rsp, 68h
0x180002b1e  movdqa  [rsp+68h+var_48], xmm0
0x180002b24  movdqa  [rsp+68h+var_38], xmm1
0x180002b2a  movdqa  [rsp+68h+var_28], xmm2
0x180002b30  movdqa  [rsp+68h+var_18], xmm3
0x180002b36  mov     rdx, rax
0x180002b39  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_storage_sense_l1_1_0_dll
0x180002b40  call    __delayLoadHelper2
0x180002b45  movdqa  xmm0, [rsp+68h+var_48]
0x180002b4b  movdqa  xmm1, [rsp+68h+var_38]
0x180002b51  movdqa  xmm2, [rsp+68h+var_28]
0x180002b57  movdqa  xmm3, [rsp+68h+var_18]
0x180002b5d  mov     rcx, [rsp+68h+arg_0]
0x180002b62  mov     rdx, [rsp+68h+arg_8]
0x180002b67  mov     r8, [rsp+68h+arg_10]
0x180002b6f  mov     r9, [rsp+68h+arg_18]
0x180002b77  add     rsp, 68h
0x180002b7b  jmp     short $+2
0x180002b7d  jmp     rax
```
