# __tailMerge_dxgi_dll

- ea: `0x140004049`
- end: `0x1400040c2`
- name: `__tailMerge_dxgi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400040c8`

## callees

- `0x1400023e0`
- `0x140004049`

## pseudocode

```c
__int64 __fastcall _tailMerge_dxgi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_dxgi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004049  mov     [rsp+arg_0], rcx
0x14000404e  mov     [rsp+arg_8], rdx
0x140004053  mov     [rsp+arg_10], r8
0x140004058  mov     [rsp+arg_18], r9
0x14000405d  sub     rsp, 68h
0x140004061  movdqa  [rsp+68h+var_48], xmm0
0x140004067  movdqa  [rsp+68h+var_38], xmm1
0x14000406d  movdqa  [rsp+68h+var_28], xmm2
0x140004073  movdqa  [rsp+68h+var_18], xmm3
0x140004079  mov     rdx, rax
0x14000407c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_dxgi_dll
0x140004083  call    __delayLoadHelper2
0x140004088  movdqa  xmm0, [rsp+68h+var_48]
0x14000408e  movdqa  xmm1, [rsp+68h+var_38]
0x140004094  movdqa  xmm2, [rsp+68h+var_28]
0x14000409a  movdqa  xmm3, [rsp+68h+var_18]
0x1400040a0  mov     rcx, [rsp+68h+arg_0]
0x1400040a5  mov     rdx, [rsp+68h+arg_8]
0x1400040aa  mov     r8, [rsp+68h+arg_10]
0x1400040b2  mov     r9, [rsp+68h+arg_18]
0x1400040ba  add     rsp, 68h
0x1400040be  jmp     short $+2
0x1400040c0  jmp     rax
```
