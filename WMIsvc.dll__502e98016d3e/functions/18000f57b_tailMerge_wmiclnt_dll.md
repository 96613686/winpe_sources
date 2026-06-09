# __tailMerge_wmiclnt_dll

- ea: `0x18000f57b`
- end: `0x18000f5f4`
- name: `__tailMerge_wmiclnt_dll`
- size: `121`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f5fa`
- `0x18000f60c`
- `0x18000f61e`
- `0x1800102c6`
- `0x1800102d8`
- `0x1800102ea`
- `0x1800102fc`
- `0x18001030e`

## callees

- `0x18000a5e0`
- `0x18000f57b`

## pseudocode

```c
__int64 __fastcall _tailMerge_wmiclnt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000f57b  mov     [rsp+arg_0], rcx
0x18000f580  mov     [rsp+arg_8], rdx
0x18000f585  mov     [rsp+arg_10], r8
0x18000f58a  mov     [rsp+arg_18], r9
0x18000f58f  sub     rsp, 68h
0x18000f593  movdqa  [rsp+68h+var_48], xmm0
0x18000f599  movdqa  [rsp+68h+var_38], xmm1
0x18000f59f  movdqa  [rsp+68h+var_28], xmm2
0x18000f5a5  movdqa  [rsp+68h+var_18], xmm3
0x18000f5ab  mov     rdx, rax
0x18000f5ae  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wmiclnt_dll
0x18000f5b5  call    __delayLoadHelper2
0x18000f5ba  movdqa  xmm0, [rsp+68h+var_48]
0x18000f5c0  movdqa  xmm1, [rsp+68h+var_38]
0x18000f5c6  movdqa  xmm2, [rsp+68h+var_28]
0x18000f5cc  movdqa  xmm3, [rsp+68h+var_18]
0x18000f5d2  mov     rcx, [rsp+68h+arg_0]
0x18000f5d7  mov     rdx, [rsp+68h+arg_8]
0x18000f5dc  mov     r8, [rsp+68h+arg_10]
0x18000f5e4  mov     r9, [rsp+68h+arg_18]
0x18000f5ec  add     rsp, 68h
0x18000f5f0  jmp     short $+2
0x18000f5f2  jmp     rax
```
