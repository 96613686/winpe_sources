# __tailMerge_wkscli_dll

- ea: `0x18000ec16`
- end: `0x18000ec8f`
- name: `__tailMerge_wkscli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ec95`

## callees

- `0x180008870`
- `0x18000ec16`

## pseudocode

```c
__int64 __fastcall _tailMerge_wkscli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_wkscli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000ec16  mov     [rsp+arg_0], rcx
0x18000ec1b  mov     [rsp+arg_8], rdx
0x18000ec20  mov     [rsp+arg_10], r8
0x18000ec25  mov     [rsp+arg_18], r9
0x18000ec2a  sub     rsp, 68h
0x18000ec2e  movdqa  [rsp+68h+var_48], xmm0
0x18000ec34  movdqa  [rsp+68h+var_38], xmm1
0x18000ec3a  movdqa  [rsp+68h+var_28], xmm2
0x18000ec40  movdqa  [rsp+68h+var_18], xmm3
0x18000ec46  mov     rdx, rax
0x18000ec49  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wkscli_dll
0x18000ec50  call    __delayLoadHelper2
0x18000ec55  movdqa  xmm0, [rsp+68h+var_48]
0x18000ec5b  movdqa  xmm1, [rsp+68h+var_38]
0x18000ec61  movdqa  xmm2, [rsp+68h+var_28]
0x18000ec67  movdqa  xmm3, [rsp+68h+var_18]
0x18000ec6d  mov     rcx, [rsp+68h+arg_0]
0x18000ec72  mov     rdx, [rsp+68h+arg_8]
0x18000ec77  mov     r8, [rsp+68h+arg_10]
0x18000ec7f  mov     r9, [rsp+68h+arg_18]
0x18000ec87  add     rsp, 68h
0x18000ec8b  jmp     short $+2
0x18000ec8d  jmp     rax
```
