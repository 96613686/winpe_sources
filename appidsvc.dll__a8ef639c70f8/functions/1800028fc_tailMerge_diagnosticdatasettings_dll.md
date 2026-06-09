# __tailMerge_diagnosticdatasettings_dll

- ea: `0x1800028fc`
- end: `0x180002975`
- name: `__tailMerge_diagnosticdatasettings_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002980`

## callees

- `0x1800028fc`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_diagnosticdatasettings_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_diagnosticdatasettings_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028fc  mov     [rsp+arg_0], rcx
0x180002901  mov     [rsp+arg_8], rdx
0x180002906  mov     [rsp+arg_10], r8
0x18000290b  mov     [rsp+arg_18], r9
0x180002910  sub     rsp, 68h
0x180002914  movdqa  [rsp+68h+var_48], xmm0
0x18000291a  movdqa  [rsp+68h+var_38], xmm1
0x180002920  movdqa  [rsp+68h+var_28], xmm2
0x180002926  movdqa  [rsp+68h+var_18], xmm3
0x18000292c  mov     rdx, rax
0x18000292f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_diagnosticdatasettings_dll
0x180002936  call    __delayLoadHelper2
0x18000293b  movdqa  xmm0, [rsp+68h+var_48]
0x180002941  movdqa  xmm1, [rsp+68h+var_38]
0x180002947  movdqa  xmm2, [rsp+68h+var_28]
0x18000294d  movdqa  xmm3, [rsp+68h+var_18]
0x180002953  mov     rcx, [rsp+68h+arg_0]
0x180002958  mov     rdx, [rsp+68h+arg_8]
0x18000295d  mov     r8, [rsp+68h+arg_10]
0x180002965  mov     r9, [rsp+68h+arg_18]
0x18000296d  add     rsp, 68h
0x180002971  jmp     short $+2
0x180002973  jmp     rax
```
