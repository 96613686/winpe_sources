# __tailMerge_crypt32_dll

- ea: `0x1800028ec`
- end: `0x180002965`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000296b`

## callees

- `0x1800028ec`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_crypt32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_crypt32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028ec  mov     [rsp+arg_0], rcx
0x1800028f1  mov     [rsp+arg_8], rdx
0x1800028f6  mov     [rsp+arg_10], r8
0x1800028fb  mov     [rsp+arg_18], r9
0x180002900  sub     rsp, 68h
0x180002904  movdqa  [rsp+68h+var_48], xmm0
0x18000290a  movdqa  [rsp+68h+var_38], xmm1
0x180002910  movdqa  [rsp+68h+var_28], xmm2
0x180002916  movdqa  [rsp+68h+var_18], xmm3
0x18000291c  mov     rdx, rax
0x18000291f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180002926  call    __delayLoadHelper2
0x18000292b  movdqa  xmm0, [rsp+68h+var_48]
0x180002931  movdqa  xmm1, [rsp+68h+var_38]
0x180002937  movdqa  xmm2, [rsp+68h+var_28]
0x18000293d  movdqa  xmm3, [rsp+68h+var_18]
0x180002943  mov     rcx, [rsp+68h+arg_0]
0x180002948  mov     rdx, [rsp+68h+arg_8]
0x18000294d  mov     r8, [rsp+68h+arg_10]
0x180002955  mov     r9, [rsp+68h+arg_18]
0x18000295d  add     rsp, 68h
0x180002961  jmp     short $+2
0x180002963  jmp     rax
```
