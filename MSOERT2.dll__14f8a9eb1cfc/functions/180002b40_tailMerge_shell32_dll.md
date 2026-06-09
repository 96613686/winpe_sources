# __tailMerge_shell32_dll

- ea: `0x180002b40`
- end: `0x180002bb9`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002bbf`
- `0x180002bd1`
- `0x180002be3`
- `0x180002bf5`
- `0x180002c07`
- `0x180002c19`
- `0x180002c2b`
- `0x180002c3d`
- `0x180002c4f`
- `0x180002c61`

## callees

- `0x180002b40`
- `0x180012ea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_shell32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_shell32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002b40  mov     [rsp+arg_0], rcx
0x180002b45  mov     [rsp+arg_8], rdx
0x180002b4a  mov     [rsp+arg_10], r8
0x180002b4f  mov     [rsp+arg_18], r9
0x180002b54  sub     rsp, 68h
0x180002b58  movdqa  [rsp+68h+var_48], xmm0
0x180002b5e  movdqa  [rsp+68h+var_38], xmm1
0x180002b64  movdqa  [rsp+68h+var_28], xmm2
0x180002b6a  movdqa  [rsp+68h+var_18], xmm3
0x180002b70  mov     rdx, rax
0x180002b73  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x180002b7a  call    __delayLoadHelper2
0x180002b7f  movdqa  xmm0, [rsp+68h+var_48]
0x180002b85  movdqa  xmm1, [rsp+68h+var_38]
0x180002b8b  movdqa  xmm2, [rsp+68h+var_28]
0x180002b91  movdqa  xmm3, [rsp+68h+var_18]
0x180002b97  mov     rcx, [rsp+68h+arg_0]
0x180002b9c  mov     rdx, [rsp+68h+arg_8]
0x180002ba1  mov     r8, [rsp+68h+arg_10]
0x180002ba9  mov     r9, [rsp+68h+arg_18]
0x180002bb1  add     rsp, 68h
0x180002bb5  jmp     short $+2
0x180002bb7  jmp     rax
```
