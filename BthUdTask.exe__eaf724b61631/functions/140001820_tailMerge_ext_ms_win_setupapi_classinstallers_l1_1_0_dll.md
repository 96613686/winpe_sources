# __tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_0_dll

- ea: `0x140001820`
- end: `0x140001899`
- name: `__tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x14000189f`

## callees

- `0x140001820`
- `0x140001eb0`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_setupapi_classinstallers_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_setupapi_classinstallers_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001820  mov     [rsp+arg_0], rcx
0x140001825  mov     [rsp+arg_8], rdx
0x14000182a  mov     [rsp+arg_10], r8
0x14000182f  mov     [rsp+arg_18], r9
0x140001834  sub     rsp, 68h
0x140001838  movdqa  [rsp+68h+var_48], xmm0
0x14000183e  movdqa  [rsp+68h+var_38], xmm1
0x140001844  movdqa  [rsp+68h+var_28], xmm2
0x14000184a  movdqa  [rsp+68h+var_18], xmm3
0x140001850  mov     rdx, rax
0x140001853  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_setupapi_classinstallers_l1_1_0_dll
0x14000185a  call    __delayLoadHelper2
0x14000185f  movdqa  xmm0, [rsp+68h+var_48]
0x140001865  movdqa  xmm1, [rsp+68h+var_38]
0x14000186b  movdqa  xmm2, [rsp+68h+var_28]
0x140001871  movdqa  xmm3, [rsp+68h+var_18]
0x140001877  mov     rcx, [rsp+68h+arg_0]
0x14000187c  mov     rdx, [rsp+68h+arg_8]
0x140001881  mov     r8, [rsp+68h+arg_10]
0x140001889  mov     r9, [rsp+68h+arg_18]
0x140001891  add     rsp, 68h
0x140001895  jmp     short $+2
0x140001897  jmp     rax
```
