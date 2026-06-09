# __tailMerge_profapi_dll

- ea: `0x180002723`
- end: `0x18000279c`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027a2`

## callees

- `0x180002723`
- `0x18001a560`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002723  mov     [rsp+arg_0], rcx
0x180002728  mov     [rsp+arg_8], rdx
0x18000272d  mov     [rsp+arg_10], r8
0x180002732  mov     [rsp+arg_18], r9
0x180002737  sub     rsp, 68h
0x18000273b  movdqa  [rsp+68h+var_48], xmm0
0x180002741  movdqa  [rsp+68h+var_38], xmm1
0x180002747  movdqa  [rsp+68h+var_28], xmm2
0x18000274d  movdqa  [rsp+68h+var_18], xmm3
0x180002753  mov     rdx, rax
0x180002756  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x18000275d  call    __delayLoadHelper2
0x180002762  movdqa  xmm0, [rsp+68h+var_48]
0x180002768  movdqa  xmm1, [rsp+68h+var_38]
0x18000276e  movdqa  xmm2, [rsp+68h+var_28]
0x180002774  movdqa  xmm3, [rsp+68h+var_18]
0x18000277a  mov     rcx, [rsp+68h+arg_0]
0x18000277f  mov     rdx, [rsp+68h+arg_8]
0x180002784  mov     r8, [rsp+68h+arg_10]
0x18000278c  mov     r9, [rsp+68h+arg_18]
0x180002794  add     rsp, 68h
0x180002798  jmp     short $+2
0x18000279a  jmp     rax
```
