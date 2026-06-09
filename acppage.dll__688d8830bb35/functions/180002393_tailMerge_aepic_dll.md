# __tailMerge_aepic_dll

- ea: `0x180002393`
- end: `0x18000240c`
- name: `__tailMerge_aepic_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002412`
- `0x180002424`

## callees

- `0x180002393`
- `0x180016160`

## pseudocode

```c
__int64 __fastcall _tailMerge_aepic_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_aepic_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002393  mov     [rsp+arg_0], rcx
0x180002398  mov     [rsp+arg_8], rdx
0x18000239d  mov     [rsp+arg_10], r8
0x1800023a2  mov     [rsp+arg_18], r9
0x1800023a7  sub     rsp, 68h
0x1800023ab  movdqa  [rsp+68h+var_48], xmm0
0x1800023b1  movdqa  [rsp+68h+var_38], xmm1
0x1800023b7  movdqa  [rsp+68h+var_28], xmm2
0x1800023bd  movdqa  [rsp+68h+var_18], xmm3
0x1800023c3  mov     rdx, rax
0x1800023c6  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_aepic_dll
0x1800023cd  call    __delayLoadHelper2
0x1800023d2  movdqa  xmm0, [rsp+68h+var_48]
0x1800023d8  movdqa  xmm1, [rsp+68h+var_38]
0x1800023de  movdqa  xmm2, [rsp+68h+var_28]
0x1800023e4  movdqa  xmm3, [rsp+68h+var_18]
0x1800023ea  mov     rcx, [rsp+68h+arg_0]
0x1800023ef  mov     rdx, [rsp+68h+arg_8]
0x1800023f4  mov     r8, [rsp+68h+arg_10]
0x1800023fc  mov     r9, [rsp+68h+arg_18]
0x180002404  add     rsp, 68h
0x180002408  jmp     short $+2
0x18000240a  jmp     rax
```
