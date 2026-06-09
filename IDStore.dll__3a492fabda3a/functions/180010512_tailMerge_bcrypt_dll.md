# __tailMerge_bcrypt_dll

- ea: `0x180010512`
- end: `0x18001058b`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010591`
- `0x1800105a3`
- `0x1800105b5`
- `0x1800105c7`

## callees

- `0x18000e230`
- `0x180010512`

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
0x180010512  mov     [rsp+arg_0], rcx
0x180010517  mov     [rsp+arg_8], rdx
0x18001051c  mov     [rsp+arg_10], r8
0x180010521  mov     [rsp+arg_18], r9
0x180010526  sub     rsp, 68h
0x18001052a  movdqa  [rsp+68h+var_48], xmm0
0x180010530  movdqa  [rsp+68h+var_38], xmm1
0x180010536  movdqa  [rsp+68h+var_28], xmm2
0x18001053c  movdqa  [rsp+68h+var_18], xmm3
0x180010542  mov     rdx, rax
0x180010545  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x18001054c  call    __delayLoadHelper2
0x180010551  movdqa  xmm0, [rsp+68h+var_48]
0x180010557  movdqa  xmm1, [rsp+68h+var_38]
0x18001055d  movdqa  xmm2, [rsp+68h+var_28]
0x180010563  movdqa  xmm3, [rsp+68h+var_18]
0x180010569  mov     rcx, [rsp+68h+arg_0]
0x18001056e  mov     rdx, [rsp+68h+arg_8]
0x180010573  mov     r8, [rsp+68h+arg_10]
0x18001057b  mov     r9, [rsp+68h+arg_18]
0x180010583  add     rsp, 68h
0x180010587  jmp     short $+2
0x180010589  jmp     rax
```
