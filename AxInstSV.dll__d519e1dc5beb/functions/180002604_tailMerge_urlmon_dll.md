# __tailMerge_urlmon_dll

- ea: `0x180002604`
- end: `0x18000267d`
- name: `__tailMerge_urlmon_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002683`

## callees

- `0x180002604`
- `0x180014100`

## pseudocode

```c
__int64 __fastcall _tailMerge_urlmon_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_urlmon_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002604  mov     [rsp+arg_0], rcx
0x180002609  mov     [rsp+arg_8], rdx
0x18000260e  mov     [rsp+arg_10], r8
0x180002613  mov     [rsp+arg_18], r9
0x180002618  sub     rsp, 68h
0x18000261c  movdqa  [rsp+68h+var_48], xmm0
0x180002622  movdqa  [rsp+68h+var_38], xmm1
0x180002628  movdqa  [rsp+68h+var_28], xmm2
0x18000262e  movdqa  [rsp+68h+var_18], xmm3
0x180002634  mov     rdx, rax
0x180002637  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_urlmon_dll
0x18000263e  call    __delayLoadHelper2
0x180002643  movdqa  xmm0, [rsp+68h+var_48]
0x180002649  movdqa  xmm1, [rsp+68h+var_38]
0x18000264f  movdqa  xmm2, [rsp+68h+var_28]
0x180002655  movdqa  xmm3, [rsp+68h+var_18]
0x18000265b  mov     rcx, [rsp+68h+arg_0]
0x180002660  mov     rdx, [rsp+68h+arg_8]
0x180002665  mov     r8, [rsp+68h+arg_10]
0x18000266d  mov     r9, [rsp+68h+arg_18]
0x180002675  add     rsp, 68h
0x180002679  jmp     short $+2
0x18000267b  jmp     rax
```
