# __tailMerge_bcrypt_dll

- ea: `0x18000218a`
- end: `0x180002203`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002209`
- `0x18000236c`
- `0x180002390`
- `0x1800023a2`
- `0x1800023b4`
- `0x180002451`
- `0x180002463`
- `0x180002499`
- `0x1800024ab`
- `0x1800024bd`
- `0x1800024cf`
- `0x1800024e1`
- `0x1800024f3`
- `0x180002505`
- `0x180002517`
- `0x180002529`
- `0x18000253b`
- `0x1800026e1`
- `0x1800026f3`
- `0x180002705`

## callees

- `0x18000218a`
- `0x18001a560`

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
0x18000218a  mov     [rsp+arg_0], rcx
0x18000218f  mov     [rsp+arg_8], rdx
0x180002194  mov     [rsp+arg_10], r8
0x180002199  mov     [rsp+arg_18], r9
0x18000219e  sub     rsp, 68h
0x1800021a2  movdqa  [rsp+68h+var_48], xmm0
0x1800021a8  movdqa  [rsp+68h+var_38], xmm1
0x1800021ae  movdqa  [rsp+68h+var_28], xmm2
0x1800021b4  movdqa  [rsp+68h+var_18], xmm3
0x1800021ba  mov     rdx, rax
0x1800021bd  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800021c4  call    __delayLoadHelper2
0x1800021c9  movdqa  xmm0, [rsp+68h+var_48]
0x1800021cf  movdqa  xmm1, [rsp+68h+var_38]
0x1800021d5  movdqa  xmm2, [rsp+68h+var_28]
0x1800021db  movdqa  xmm3, [rsp+68h+var_18]
0x1800021e1  mov     rcx, [rsp+68h+arg_0]
0x1800021e6  mov     rdx, [rsp+68h+arg_8]
0x1800021eb  mov     r8, [rsp+68h+arg_10]
0x1800021f3  mov     r9, [rsp+68h+arg_18]
0x1800021fb  add     rsp, 68h
0x1800021ff  jmp     short $+2
0x180002201  jmp     rax
```
