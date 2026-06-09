# __tailMerge_ext_ms_win_provisioning_platform_l1_1_1_dll

- ea: `0x1400021f6`
- end: `0x14000226f`
- name: `__tailMerge_ext_ms_win_provisioning_platform_l1_1_1_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002275`

## callees

- `0x1400021f6`
- `0x14000dd40`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_provisioning_platform_l1_1_1_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_provisioning_platform_l1_1_1_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400021f6  mov     [rsp+arg_0], rcx
0x1400021fb  mov     [rsp+arg_8], rdx
0x140002200  mov     [rsp+arg_10], r8
0x140002205  mov     [rsp+arg_18], r9
0x14000220a  sub     rsp, 68h
0x14000220e  movdqa  [rsp+68h+var_48], xmm0
0x140002214  movdqa  [rsp+68h+var_38], xmm1
0x14000221a  movdqa  [rsp+68h+var_28], xmm2
0x140002220  movdqa  [rsp+68h+var_18], xmm3
0x140002226  mov     rdx, rax
0x140002229  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_provisioning_platform_l1_1_1_dll
0x140002230  call    __delayLoadHelper2
0x140002235  movdqa  xmm0, [rsp+68h+var_48]
0x14000223b  movdqa  xmm1, [rsp+68h+var_38]
0x140002241  movdqa  xmm2, [rsp+68h+var_28]
0x140002247  movdqa  xmm3, [rsp+68h+var_18]
0x14000224d  mov     rcx, [rsp+68h+arg_0]
0x140002252  mov     rdx, [rsp+68h+arg_8]
0x140002257  mov     r8, [rsp+68h+arg_10]
0x14000225f  mov     r9, [rsp+68h+arg_18]
0x140002267  add     rsp, 68h
0x14000226b  jmp     short $+2
0x14000226d  jmp     rax
```
