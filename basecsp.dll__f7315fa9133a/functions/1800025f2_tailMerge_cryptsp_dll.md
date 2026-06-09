# __tailMerge_cryptsp_dll

- ea: `0x1800025f2`
- end: `0x18000266b`
- name: `__tailMerge_cryptsp_dll`
- size: `121`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002671`
- `0x180002683`
- `0x180002695`
- `0x1800026a7`
- `0x1800026b9`
- `0x1800026cb`
- `0x1800026dd`
- `0x1800026ef`
- `0x180002701`
- `0x180002713`
- `0x180002725`
- `0x180002737`
- `0x180002749`
- `0x18000275b`
- `0x18000276d`
- `0x18000277f`
- `0x180002791`
- `0x1800027a3`
- `0x1800027b5`
- `0x1800027c7`
- `0x1800027d9`
- `0x1800027eb`
- `0x1800027fd`
- `0x18000280f`
- `0x180002821`
- `0x180002833`

## callees

- `0x1800025f2`
- `0x18002cea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_cryptsp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_cryptsp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025f2  mov     [rsp+arg_0], rcx
0x1800025f7  mov     [rsp+arg_8], rdx
0x1800025fc  mov     [rsp+arg_10], r8
0x180002601  mov     [rsp+arg_18], r9
0x180002606  sub     rsp, 68h
0x18000260a  movdqa  [rsp+68h+var_48], xmm0
0x180002610  movdqa  [rsp+68h+var_38], xmm1
0x180002616  movdqa  [rsp+68h+var_28], xmm2
0x18000261c  movdqa  [rsp+68h+var_18], xmm3
0x180002622  mov     rdx, rax
0x180002625  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_cryptsp_dll
0x18000262c  call    __delayLoadHelper2
0x180002631  movdqa  xmm0, [rsp+68h+var_48]
0x180002637  movdqa  xmm1, [rsp+68h+var_38]
0x18000263d  movdqa  xmm2, [rsp+68h+var_28]
0x180002643  movdqa  xmm3, [rsp+68h+var_18]
0x180002649  mov     rcx, [rsp+68h+arg_0]
0x18000264e  mov     rdx, [rsp+68h+arg_8]
0x180002653  mov     r8, [rsp+68h+arg_10]
0x18000265b  mov     r9, [rsp+68h+arg_18]
0x180002663  add     rsp, 68h
0x180002667  jmp     short $+2
0x180002669  jmp     rax
```
