# __tailMerge_dmxmlhelputils_dll

- ea: `0x180002929`
- end: `0x1800029a2`
- name: `__tailMerge_dmxmlhelputils_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800029a8`

## callees

- `0x180002929`
- `0x180018700`

## pseudocode

```c
__int64 __fastcall _tailMerge_dmxmlhelputils_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dmxmlhelputils_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002929  mov     [rsp+arg_0], rcx
0x18000292e  mov     [rsp+arg_8], rdx
0x180002933  mov     [rsp+arg_10], r8
0x180002938  mov     [rsp+arg_18], r9
0x18000293d  sub     rsp, 68h
0x180002941  movdqa  [rsp+68h+var_48], xmm0
0x180002947  movdqa  [rsp+68h+var_38], xmm1
0x18000294d  movdqa  [rsp+68h+var_28], xmm2
0x180002953  movdqa  [rsp+68h+var_18], xmm3
0x180002959  mov     rdx, rax
0x18000295c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dmxmlhelputils_dll
0x180002963  call    __delayLoadHelper2
0x180002968  movdqa  xmm0, [rsp+68h+var_48]
0x18000296e  movdqa  xmm1, [rsp+68h+var_38]
0x180002974  movdqa  xmm2, [rsp+68h+var_28]
0x18000297a  movdqa  xmm3, [rsp+68h+var_18]
0x180002980  mov     rcx, [rsp+68h+arg_0]
0x180002985  mov     rdx, [rsp+68h+arg_8]
0x18000298a  mov     r8, [rsp+68h+arg_10]
0x180002992  mov     r9, [rsp+68h+arg_18]
0x18000299a  add     rsp, 68h
0x18000299e  jmp     short $+2
0x1800029a0  jmp     rax
```
