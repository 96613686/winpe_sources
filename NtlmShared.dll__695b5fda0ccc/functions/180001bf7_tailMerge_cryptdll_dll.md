# __tailMerge_cryptdll_dll

- ea: `0x180001bf7`
- end: `0x180001c70`
- name: `__tailMerge_cryptdll_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c76`

## callees

- `0x180001bf7`
- `0x18000c450`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptdll_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptdll_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001bf7  mov     [rsp+arg_0], rcx
0x180001bfc  mov     [rsp+arg_8], rdx
0x180001c01  mov     [rsp+arg_10], r8
0x180001c06  mov     [rsp+arg_18], r9
0x180001c0b  sub     rsp, 68h
0x180001c0f  movdqa  [rsp+68h+var_48], xmm0
0x180001c15  movdqa  [rsp+68h+var_38], xmm1
0x180001c1b  movdqa  [rsp+68h+var_28], xmm2
0x180001c21  movdqa  [rsp+68h+var_18], xmm3
0x180001c27  mov     rdx, rax
0x180001c2a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptdll_dll
0x180001c31  call    __delayLoadHelper2
0x180001c36  movdqa  xmm0, [rsp+68h+var_48]
0x180001c3c  movdqa  xmm1, [rsp+68h+var_38]
0x180001c42  movdqa  xmm2, [rsp+68h+var_28]
0x180001c48  movdqa  xmm3, [rsp+68h+var_18]
0x180001c4e  mov     rcx, [rsp+68h+arg_0]
0x180001c53  mov     rdx, [rsp+68h+arg_8]
0x180001c58  mov     r8, [rsp+68h+arg_10]
0x180001c60  mov     r9, [rsp+68h+arg_18]
0x180001c68  add     rsp, 68h
0x180001c6c  jmp     short $+2
0x180001c6e  jmp     rax
```
