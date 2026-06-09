# __tailMerge_rpcrt4_dll

- ea: `0x180002215`
- end: `0x18000228e`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002294`
- `0x1800022a6`
- `0x18000237e`
- `0x18000254d`
- `0x180002675`
- `0x180002687`
- `0x180002699`
- `0x1800026ab`
- `0x1800026bd`
- `0x1800026cf`
- `0x180002717`

## callees

- `0x180002215`
- `0x18001a560`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002215  mov     [rsp+arg_0], rcx
0x18000221a  mov     [rsp+arg_8], rdx
0x18000221f  mov     [rsp+arg_10], r8
0x180002224  mov     [rsp+arg_18], r9
0x180002229  sub     rsp, 68h
0x18000222d  movdqa  [rsp+68h+var_48], xmm0
0x180002233  movdqa  [rsp+68h+var_38], xmm1
0x180002239  movdqa  [rsp+68h+var_28], xmm2
0x18000223f  movdqa  [rsp+68h+var_18], xmm3
0x180002245  mov     rdx, rax
0x180002248  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x18000224f  call    __delayLoadHelper2
0x180002254  movdqa  xmm0, [rsp+68h+var_48]
0x18000225a  movdqa  xmm1, [rsp+68h+var_38]
0x180002260  movdqa  xmm2, [rsp+68h+var_28]
0x180002266  movdqa  xmm3, [rsp+68h+var_18]
0x18000226c  mov     rcx, [rsp+68h+arg_0]
0x180002271  mov     rdx, [rsp+68h+arg_8]
0x180002276  mov     r8, [rsp+68h+arg_10]
0x18000227e  mov     r9, [rsp+68h+arg_18]
0x180002286  add     rsp, 68h
0x18000228a  jmp     short $+2
0x18000228c  jmp     rax
```
