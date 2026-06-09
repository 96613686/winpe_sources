# __tailMerge_bcrypt_dll

- ea: `0x180002300`
- end: `0x180002379`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000237f`
- `0x180002391`
- `0x1800023a3`
- `0x1800023b5`
- `0x1800023c7`
- `0x1800023d9`
- `0x1800023eb`

## callees

- `0x180002300`
- `0x18001bb20`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002300  mov     [rsp+arg_0], rcx
0x180002305  mov     [rsp+arg_8], rdx
0x18000230a  mov     [rsp+arg_10], r8
0x18000230f  mov     [rsp+arg_18], r9
0x180002314  sub     rsp, 68h
0x180002318  movdqa  [rsp+68h+var_48], xmm0
0x18000231e  movdqa  [rsp+68h+var_38], xmm1
0x180002324  movdqa  [rsp+68h+var_28], xmm2
0x18000232a  movdqa  [rsp+68h+var_18], xmm3
0x180002330  mov     rdx, rax
0x180002333  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18000233a  call    __delayLoadHelper2
0x18000233f  movdqa  xmm0, [rsp+68h+var_48]
0x180002345  movdqa  xmm1, [rsp+68h+var_38]
0x18000234b  movdqa  xmm2, [rsp+68h+var_28]
0x180002351  movdqa  xmm3, [rsp+68h+var_18]
0x180002357  mov     rcx, [rsp+68h+arg_0]
0x18000235c  mov     rdx, [rsp+68h+arg_8]
0x180002361  mov     r8, [rsp+68h+arg_10]
0x180002369  mov     r9, [rsp+68h+arg_18]
0x180002371  add     rsp, 68h
0x180002375  jmp     short $+2
0x180002377  jmp     rax
```
