# __tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll

- ea: `0x14000449a`
- end: `0x140004513`
- name: `__tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004519`

## callees

- `0x14000449a`
- `0x14000ea00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_appmodel_shellexecute_l1_1_0_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_appmodel_shellexecute_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000449a  mov     [rsp+arg_0], rcx
0x14000449f  mov     [rsp+arg_8], rdx
0x1400044a4  mov     [rsp+arg_10], r8
0x1400044a9  mov     [rsp+arg_18], r9
0x1400044ae  sub     rsp, 68h
0x1400044b2  movdqa  [rsp+68h+var_48], xmm0
0x1400044b8  movdqa  [rsp+68h+var_38], xmm1
0x1400044be  movdqa  [rsp+68h+var_28], xmm2
0x1400044c4  movdqa  [rsp+68h+var_18], xmm3
0x1400044ca  mov     rdx, rax
0x1400044cd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_appmodel_shellexecute_l1_1_0_dll
0x1400044d4  call    __delayLoadHelper2
0x1400044d9  movdqa  xmm0, [rsp+68h+var_48]
0x1400044df  movdqa  xmm1, [rsp+68h+var_38]
0x1400044e5  movdqa  xmm2, [rsp+68h+var_28]
0x1400044eb  movdqa  xmm3, [rsp+68h+var_18]
0x1400044f1  mov     rcx, [rsp+68h+arg_0]
0x1400044f6  mov     rdx, [rsp+68h+arg_8]
0x1400044fb  mov     r8, [rsp+68h+arg_10]
0x140004503  mov     r9, [rsp+68h+arg_18]
0x14000450b  add     rsp, 68h
0x14000450f  jmp     short $+2
0x140004511  jmp     rax
```
