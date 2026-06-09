# __tailMerge_cryptbase_dll

- ea: `0x180002555`
- end: `0x1800025ce`
- name: `__tailMerge_cryptbase_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800025d4`
- `0x1800025e6`

## callees

- `0x180002555`
- `0x18002cea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptbase_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptbase_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002555  mov     [rsp+arg_0], rcx
0x18000255a  mov     [rsp+arg_8], rdx
0x18000255f  mov     [rsp+arg_10], r8
0x180002564  mov     [rsp+arg_18], r9
0x180002569  sub     rsp, 68h
0x18000256d  movdqa  [rsp+68h+var_48], xmm0
0x180002573  movdqa  [rsp+68h+var_38], xmm1
0x180002579  movdqa  [rsp+68h+var_28], xmm2
0x18000257f  movdqa  [rsp+68h+var_18], xmm3
0x180002585  mov     rdx, rax
0x180002588  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptbase_dll
0x18000258f  call    __delayLoadHelper2
0x180002594  movdqa  xmm0, [rsp+68h+var_48]
0x18000259a  movdqa  xmm1, [rsp+68h+var_38]
0x1800025a0  movdqa  xmm2, [rsp+68h+var_28]
0x1800025a6  movdqa  xmm3, [rsp+68h+var_18]
0x1800025ac  mov     rcx, [rsp+68h+arg_0]
0x1800025b1  mov     rdx, [rsp+68h+arg_8]
0x1800025b6  mov     r8, [rsp+68h+arg_10]
0x1800025be  mov     r9, [rsp+68h+arg_18]
0x1800025c6  add     rsp, 68h
0x1800025ca  jmp     short $+2
0x1800025cc  jmp     rax
```
