# __tailMerge_bcrypt_dll

- ea: `0x18000acb6`
- end: `0x18000ad2f`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ad35`
- `0x18000ad47`
- `0x18000ad59`
- `0x18000ad6b`
- `0x18000ad7d`
- `0x18000ad8f`
- `0x18000ada1`

## callees

- `0x180007cd0`
- `0x18000acb6`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000acb6  mov     [rsp+arg_0], rcx
0x18000acbb  mov     [rsp+arg_8], rdx
0x18000acc0  mov     [rsp+arg_10], r8
0x18000acc5  mov     [rsp+arg_18], r9
0x18000acca  sub     rsp, 68h
0x18000acce  movdqa  [rsp+68h+var_48], xmm0
0x18000acd4  movdqa  [rsp+68h+var_38], xmm1
0x18000acda  movdqa  [rsp+68h+var_28], xmm2
0x18000ace0  movdqa  [rsp+68h+var_18], xmm3
0x18000ace6  mov     rdx, rax
0x18000ace9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18000acf0  call    __delayLoadHelper2
0x18000acf5  movdqa  xmm0, [rsp+68h+var_48]
0x18000acfb  movdqa  xmm1, [rsp+68h+var_38]
0x18000ad01  movdqa  xmm2, [rsp+68h+var_28]
0x18000ad07  movdqa  xmm3, [rsp+68h+var_18]
0x18000ad0d  mov     rcx, [rsp+68h+arg_0]
0x18000ad12  mov     rdx, [rsp+68h+arg_8]
0x18000ad17  mov     r8, [rsp+68h+arg_10]
0x18000ad1f  mov     r9, [rsp+68h+arg_18]
0x18000ad27  add     rsp, 68h
0x18000ad2b  jmp     short $+2
0x18000ad2d  jmp     rax
```
