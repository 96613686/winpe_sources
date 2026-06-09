# __tailMerge_crypt32_dll

- ea: `0x1800021da`
- end: `0x180002253`
- name: `__tailMerge_crypt32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002259`

## callees

- `0x1800021da`
- `0x18001d370`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800021da  mov     [rsp+arg_0], rcx
0x1800021df  mov     [rsp+arg_8], rdx
0x1800021e4  mov     [rsp+arg_10], r8
0x1800021e9  mov     [rsp+arg_18], r9
0x1800021ee  sub     rsp, 68h
0x1800021f2  movdqa  [rsp+68h+var_48], xmm0
0x1800021f8  movdqa  [rsp+68h+var_38], xmm1
0x1800021fe  movdqa  [rsp+68h+var_28], xmm2
0x180002204  movdqa  [rsp+68h+var_18], xmm3
0x18000220a  mov     rdx, rax
0x18000220d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_crypt32_dll
0x180002214  call    __delayLoadHelper2
0x180002219  movdqa  xmm0, [rsp+68h+var_48]
0x18000221f  movdqa  xmm1, [rsp+68h+var_38]
0x180002225  movdqa  xmm2, [rsp+68h+var_28]
0x18000222b  movdqa  xmm3, [rsp+68h+var_18]
0x180002231  mov     rcx, [rsp+68h+arg_0]
0x180002236  mov     rdx, [rsp+68h+arg_8]
0x18000223b  mov     r8, [rsp+68h+arg_10]
0x180002243  mov     r9, [rsp+68h+arg_18]
0x18000224b  add     rsp, 68h
0x18000224f  jmp     short $+2
0x180002251  jmp     rax
```
