# __tailMerge_propsys_dll

- ea: `0x1800022e3`
- end: `0x18000235c`
- name: `__tailMerge_propsys_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002362`

## callees

- `0x1800022e3`
- `0x18001da40`

## pseudocode

```c
__int64 __fastcall _tailMerge_propsys_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_propsys_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022e3  mov     [rsp+arg_0], rcx
0x1800022e8  mov     [rsp+arg_8], rdx
0x1800022ed  mov     [rsp+arg_10], r8
0x1800022f2  mov     [rsp+arg_18], r9
0x1800022f7  sub     rsp, 68h
0x1800022fb  movdqa  [rsp+68h+var_48], xmm0
0x180002301  movdqa  [rsp+68h+var_38], xmm1
0x180002307  movdqa  [rsp+68h+var_28], xmm2
0x18000230d  movdqa  [rsp+68h+var_18], xmm3
0x180002313  mov     rdx, rax
0x180002316  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_propsys_dll
0x18000231d  call    __delayLoadHelper2
0x180002322  movdqa  xmm0, [rsp+68h+var_48]
0x180002328  movdqa  xmm1, [rsp+68h+var_38]
0x18000232e  movdqa  xmm2, [rsp+68h+var_28]
0x180002334  movdqa  xmm3, [rsp+68h+var_18]
0x18000233a  mov     rcx, [rsp+68h+arg_0]
0x18000233f  mov     rdx, [rsp+68h+arg_8]
0x180002344  mov     r8, [rsp+68h+arg_10]
0x18000234c  mov     r9, [rsp+68h+arg_18]
0x180002354  add     rsp, 68h
0x180002358  jmp     short $+2
0x18000235a  jmp     rax
```
