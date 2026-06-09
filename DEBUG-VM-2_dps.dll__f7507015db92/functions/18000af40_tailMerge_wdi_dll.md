# __tailMerge_wdi_dll

- ea: `0x18000af40`
- end: `0x18000afb9`
- name: `__tailMerge_wdi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000afc0`

## callees

- `0x180001530`
- `0x18000af40`

## pseudocode

```c
__int64 __fastcall _tailMerge_wdi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wdi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000af40  mov     [rsp+arg_0], rcx
0x18000af45  mov     [rsp+arg_8], rdx
0x18000af4a  mov     [rsp+arg_10], r8
0x18000af4f  mov     [rsp+arg_18], r9
0x18000af54  sub     rsp, 68h
0x18000af58  movdqa  [rsp+68h+var_48], xmm0
0x18000af5e  movdqa  [rsp+68h+var_38], xmm1
0x18000af64  movdqa  [rsp+68h+var_28], xmm2
0x18000af6a  movdqa  [rsp+68h+var_18], xmm3
0x18000af70  mov     rdx, rax
0x18000af73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wdi_dll
0x18000af7a  call    __delayLoadHelper2
0x18000af7f  movdqa  xmm0, [rsp+68h+var_48]
0x18000af85  movdqa  xmm1, [rsp+68h+var_38]
0x18000af8b  movdqa  xmm2, [rsp+68h+var_28]
0x18000af91  movdqa  xmm3, [rsp+68h+var_18]
0x18000af97  mov     rcx, [rsp+68h+arg_0]
0x18000af9c  mov     rdx, [rsp+68h+arg_8]
0x18000afa1  mov     r8, [rsp+68h+arg_10]
0x18000afa9  mov     r9, [rsp+68h+arg_18]
0x18000afb1  add     rsp, 68h
0x18000afb5  jmp     short $+2
0x18000afb7  jmp     rax
```
