# __tailMerge_userenv_dll

- ea: `0x180001efa`
- end: `0x180001f73`
- name: `__tailMerge_userenv_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f79`

## callees

- `0x180001efa`
- `0x180006880`

## pseudocode

```c
__int64 __fastcall _tailMerge_userenv_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_userenv_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001efa  mov     [rsp+arg_0], rcx
0x180001eff  mov     [rsp+arg_8], rdx
0x180001f04  mov     [rsp+arg_10], r8
0x180001f09  mov     [rsp+arg_18], r9
0x180001f0e  sub     rsp, 68h
0x180001f12  movdqa  [rsp+68h+var_48], xmm0
0x180001f18  movdqa  [rsp+68h+var_38], xmm1
0x180001f1e  movdqa  [rsp+68h+var_28], xmm2
0x180001f24  movdqa  [rsp+68h+var_18], xmm3
0x180001f2a  mov     rdx, rax
0x180001f2d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_userenv_dll
0x180001f34  call    __delayLoadHelper2
0x180001f39  movdqa  xmm0, [rsp+68h+var_48]
0x180001f3f  movdqa  xmm1, [rsp+68h+var_38]
0x180001f45  movdqa  xmm2, [rsp+68h+var_28]
0x180001f4b  movdqa  xmm3, [rsp+68h+var_18]
0x180001f51  mov     rcx, [rsp+68h+arg_0]
0x180001f56  mov     rdx, [rsp+68h+arg_8]
0x180001f5b  mov     r8, [rsp+68h+arg_10]
0x180001f63  mov     r9, [rsp+68h+arg_18]
0x180001f6b  add     rsp, 68h
0x180001f6f  jmp     short $+2
0x180001f71  jmp     rax
```
