# __tailMerge_advapi32_dll

- ea: `0x180001fff`
- end: `0x180002078`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000207e`
- `0x1800021a6`
- `0x1800021b8`
- `0x1800021ca`
- `0x1800021dc`
- `0x18000229d`
- `0x18000233a`
- `0x18000234c`
- `0x18000235e`
- `0x180002370`
- `0x180002382`
- `0x180002394`
- `0x1800023a6`
- `0x1800023b8`
- `0x1800023ca`
- `0x1800023dc`
- `0x1800023ee`
- `0x180002400`
- `0x180002412`
- `0x180002424`
- `0x180002436`
- `0x18000261f`
- `0x180002631`
- `0x180002643`
- `0x180002655`
- `0x180002667`
- `0x180002679`
- `0x18000268b`
- `0x18000269d`

## callees

- `0x180001fff`
- `0x180013680`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_advapi32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001fff  mov     [rsp+arg_0], rcx
0x180002004  mov     [rsp+arg_8], rdx
0x180002009  mov     [rsp+arg_10], r8
0x18000200e  mov     [rsp+arg_18], r9
0x180002013  sub     rsp, 68h
0x180002017  movdqa  [rsp+68h+var_48], xmm0
0x18000201d  movdqa  [rsp+68h+var_38], xmm1
0x180002023  movdqa  [rsp+68h+var_28], xmm2
0x180002029  movdqa  [rsp+68h+var_18], xmm3
0x18000202f  mov     rdx, rax
0x180002032  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x180002039  call    __delayLoadHelper2
0x18000203e  movdqa  xmm0, [rsp+68h+var_48]
0x180002044  movdqa  xmm1, [rsp+68h+var_38]
0x18000204a  movdqa  xmm2, [rsp+68h+var_28]
0x180002050  movdqa  xmm3, [rsp+68h+var_18]
0x180002056  mov     rcx, [rsp+68h+arg_0]
0x18000205b  mov     rdx, [rsp+68h+arg_8]
0x180002060  mov     r8, [rsp+68h+arg_10]
0x180002068  mov     r9, [rsp+68h+arg_18]
0x180002070  add     rsp, 68h
0x180002074  jmp     short $+2
0x180002076  jmp     rax
```
