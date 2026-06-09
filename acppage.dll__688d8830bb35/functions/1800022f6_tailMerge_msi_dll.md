# __tailMerge_msi_dll

- ea: `0x1800022f6`
- end: `0x18000236f`
- name: `__tailMerge_msi_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180002375`
- `0x180002387`

## callees

- `0x1800022f6`
- `0x180016160`

## pseudocode

```c
__int64 __fastcall _tailMerge_msi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_msi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022f6  mov     [rsp+arg_0], rcx
0x1800022fb  mov     [rsp+arg_8], rdx
0x180002300  mov     [rsp+arg_10], r8
0x180002305  mov     [rsp+arg_18], r9
0x18000230a  sub     rsp, 68h
0x18000230e  movdqa  [rsp+68h+var_48], xmm0
0x180002314  movdqa  [rsp+68h+var_38], xmm1
0x18000231a  movdqa  [rsp+68h+var_28], xmm2
0x180002320  movdqa  [rsp+68h+var_18], xmm3
0x180002326  mov     rdx, rax
0x180002329  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_msi_dll
0x180002330  call    __delayLoadHelper2
0x180002335  movdqa  xmm0, [rsp+68h+var_48]
0x18000233b  movdqa  xmm1, [rsp+68h+var_38]
0x180002341  movdqa  xmm2, [rsp+68h+var_28]
0x180002347  movdqa  xmm3, [rsp+68h+var_18]
0x18000234d  mov     rcx, [rsp+68h+arg_0]
0x180002352  mov     rdx, [rsp+68h+arg_8]
0x180002357  mov     r8, [rsp+68h+arg_10]
0x18000235f  mov     r9, [rsp+68h+arg_18]
0x180002367  add     rsp, 68h
0x18000236b  jmp     short $+2
0x18000236d  jmp     rax
```
