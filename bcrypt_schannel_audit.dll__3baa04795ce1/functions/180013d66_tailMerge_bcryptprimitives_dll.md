# __tailMerge_bcryptprimitives_dll

- ea: `0x180013d66`
- end: `0x180013ddf`
- name: `__tailMerge_bcryptprimitives_dll`
- size: `121`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013de5`
- `0x180013e00`
- `0x180013e20`
- `0x180013e40`
- `0x180013e60`
- `0x180013e80`
- `0x180013ea0`
- `0x180013ec0`
- `0x180013ee0`

## callees

- `0x180013d66`
- `0x18001b380`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcryptprimitives_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcryptprimitives_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180013d66  mov     [rsp+arg_0], rcx
0x180013d6b  mov     [rsp+arg_8], rdx
0x180013d70  mov     [rsp+arg_10], r8
0x180013d75  mov     [rsp+arg_18], r9
0x180013d7a  sub     rsp, 68h
0x180013d7e  movdqa  [rsp+68h+var_48], xmm0
0x180013d84  movdqa  [rsp+68h+var_38], xmm1
0x180013d8a  movdqa  [rsp+68h+var_28], xmm2
0x180013d90  movdqa  [rsp+68h+var_18], xmm3
0x180013d96  mov     rdx, rax
0x180013d99  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcryptprimitives_dll
0x180013da0  call    __delayLoadHelper2
0x180013da5  movdqa  xmm0, [rsp+68h+var_48]
0x180013dab  movdqa  xmm1, [rsp+68h+var_38]
0x180013db1  movdqa  xmm2, [rsp+68h+var_28]
0x180013db7  movdqa  xmm3, [rsp+68h+var_18]
0x180013dbd  mov     rcx, [rsp+68h+arg_0]
0x180013dc2  mov     rdx, [rsp+68h+arg_8]
0x180013dc7  mov     r8, [rsp+68h+arg_10]
0x180013dcf  mov     r9, [rsp+68h+arg_18]
0x180013dd7  add     rsp, 68h
0x180013ddb  jmp     short $+2
0x180013ddd  jmp     rax
```
