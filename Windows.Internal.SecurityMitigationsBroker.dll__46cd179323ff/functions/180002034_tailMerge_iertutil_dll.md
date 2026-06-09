# __tailMerge_iertutil_dll

- ea: `0x180002034`
- end: `0x1800020ad`
- name: `__tailMerge_iertutil_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020b3`
- `0x1800021e6`
- `0x1800021f8`
- `0x18000220a`
- `0x18000221c`
- `0x18000222e`
- `0x180002240`
- `0x180002252`
- `0x180002264`
- `0x180002276`

## callees

- `0x180002034`
- `0x180006880`

## pseudocode

```c
__int64 __fastcall _tailMerge_iertutil_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_iertutil_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002034  mov     [rsp+arg_0], rcx
0x180002039  mov     [rsp+arg_8], rdx
0x18000203e  mov     [rsp+arg_10], r8
0x180002043  mov     [rsp+arg_18], r9
0x180002048  sub     rsp, 68h
0x18000204c  movdqa  [rsp+68h+var_48], xmm0
0x180002052  movdqa  [rsp+68h+var_38], xmm1
0x180002058  movdqa  [rsp+68h+var_28], xmm2
0x18000205e  movdqa  [rsp+68h+var_18], xmm3
0x180002064  mov     rdx, rax
0x180002067  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_iertutil_dll
0x18000206e  call    __delayLoadHelper2
0x180002073  movdqa  xmm0, [rsp+68h+var_48]
0x180002079  movdqa  xmm1, [rsp+68h+var_38]
0x18000207f  movdqa  xmm2, [rsp+68h+var_28]
0x180002085  movdqa  xmm3, [rsp+68h+var_18]
0x18000208b  mov     rcx, [rsp+68h+arg_0]
0x180002090  mov     rdx, [rsp+68h+arg_8]
0x180002095  mov     r8, [rsp+68h+arg_10]
0x18000209d  mov     r9, [rsp+68h+arg_18]
0x1800020a5  add     rsp, 68h
0x1800020a9  jmp     short $+2
0x1800020ab  jmp     rax
```
