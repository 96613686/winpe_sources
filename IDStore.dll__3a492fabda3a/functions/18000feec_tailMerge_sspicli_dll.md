# __tailMerge_sspicli_dll

- ea: `0x18000feec`
- end: `0x18000ff65`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ff6b`
- `0x18000ff7d`
- `0x18000ff8f`
- `0x18000ffa1`
- `0x18000ffb3`
- `0x18000ffc5`
- `0x18000ffd7`
- `0x18000ffe9`

## callees

- `0x18000e230`
- `0x18000feec`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000feec  mov     [rsp+arg_0], rcx
0x18000fef1  mov     [rsp+arg_8], rdx
0x18000fef6  mov     [rsp+arg_10], r8
0x18000fefb  mov     [rsp+arg_18], r9
0x18000ff00  sub     rsp, 68h
0x18000ff04  movdqa  [rsp+68h+var_48], xmm0
0x18000ff0a  movdqa  [rsp+68h+var_38], xmm1
0x18000ff10  movdqa  [rsp+68h+var_28], xmm2
0x18000ff16  movdqa  [rsp+68h+var_18], xmm3
0x18000ff1c  mov     rdx, rax
0x18000ff1f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x18000ff26  call    __delayLoadHelper2
0x18000ff2b  movdqa  xmm0, [rsp+68h+var_48]
0x18000ff31  movdqa  xmm1, [rsp+68h+var_38]
0x18000ff37  movdqa  xmm2, [rsp+68h+var_28]
0x18000ff3d  movdqa  xmm3, [rsp+68h+var_18]
0x18000ff43  mov     rcx, [rsp+68h+arg_0]
0x18000ff48  mov     rdx, [rsp+68h+arg_8]
0x18000ff4d  mov     r8, [rsp+68h+arg_10]
0x18000ff55  mov     r9, [rsp+68h+arg_18]
0x18000ff5d  add     rsp, 68h
0x18000ff61  jmp     short $+2
0x18000ff63  jmp     rax
```
