# __tailMerge_advapi32_dll

- ea: `0x1400015d0`
- end: `0x14000164a`
- name: `__tailMerge_advapi32_dll`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001000`
- `0x14000100c`
- `0x1400015c7`

## callees

- `0x1400015d0`
- `0x140001650`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400015d0  mov     [rsp+arg_0], rcx
0x1400015d5  mov     [rsp+arg_8], rdx
0x1400015da  mov     [rsp+arg_10], r8
0x1400015df  mov     [rsp+arg_18], r9
0x1400015e4  sub     rsp, 68h
0x1400015e8  movdqa  [rsp+68h+var_48], xmm0
0x1400015ee  movdqa  [rsp+68h+var_38], xmm1
0x1400015f4  movdqa  [rsp+68h+var_28], xmm2
0x1400015fa  movdqa  [rsp+68h+var_18], xmm3
0x140001600  mov     rdx, rax
0x140001603  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x14000160a  call    __delayLoadHelper2
0x14000160f  movdqa  xmm0, [rsp+68h+var_48]
0x140001615  movdqa  xmm1, [rsp+68h+var_38]
0x14000161b  movdqa  xmm2, [rsp+68h+var_28]
0x140001621  movdqa  xmm3, [rsp+68h+var_18]
0x140001627  mov     rcx, [rsp+68h+arg_0]
0x14000162c  mov     rdx, [rsp+68h+arg_8]
0x140001631  mov     r8, [rsp+68h+arg_10]
0x140001639  mov     r9, [rsp+68h+arg_18]
0x140001641  add     rsp, 68h
0x140001645  jmp     short loc_140001648
0x140001648  jmp     rax
```
