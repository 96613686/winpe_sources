# __tailMerge_mscms_dll

- ea: `0x14000287a`
- end: `0x1400028f3`
- name: `__tailMerge_mscms_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400028f9`

## callees

- `0x14000287a`
- `0x140015a10`

## pseudocode

```c
__int64 __fastcall _tailMerge_mscms_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_mscms_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x14000287a  mov     [rsp+arg_0], rcx
0x14000287f  mov     [rsp+arg_8], rdx
0x140002884  mov     [rsp+arg_10], r8
0x140002889  mov     [rsp+arg_18], r9
0x14000288e  sub     rsp, 68h
0x140002892  movdqa  [rsp+68h+var_48], xmm0
0x140002898  movdqa  [rsp+68h+var_38], xmm1
0x14000289e  movdqa  [rsp+68h+var_28], xmm2
0x1400028a4  movdqa  [rsp+68h+var_18], xmm3
0x1400028aa  mov     rdx, rax
0x1400028ad  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_mscms_dll
0x1400028b4  call    __delayLoadHelper2
0x1400028b9  movdqa  xmm0, [rsp+68h+var_48]
0x1400028bf  movdqa  xmm1, [rsp+68h+var_38]
0x1400028c5  movdqa  xmm2, [rsp+68h+var_28]
0x1400028cb  movdqa  xmm3, [rsp+68h+var_18]
0x1400028d1  mov     rcx, [rsp+68h+arg_0]
0x1400028d6  mov     rdx, [rsp+68h+arg_8]
0x1400028db  mov     r8, [rsp+68h+arg_10]
0x1400028e3  mov     r9, [rsp+68h+arg_18]
0x1400028eb  add     rsp, 68h
0x1400028ef  jmp     short $+2
0x1400028f1  jmp     rax
```
