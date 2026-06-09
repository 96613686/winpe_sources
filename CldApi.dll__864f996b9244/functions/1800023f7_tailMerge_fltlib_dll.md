# __tailMerge_fltlib_dll

- ea: `0x1800023f7`
- end: `0x180002470`
- name: `__tailMerge_fltlib_dll`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002476`
- `0x180002488`
- `0x18000249a`

## callees

- `0x1800023f7`
- `0x18001bb20`

## pseudocode

```c
__int64 __fastcall _tailMerge_fltlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_fltlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800023f7  mov     [rsp+arg_0], rcx
0x1800023fc  mov     [rsp+arg_8], rdx
0x180002401  mov     [rsp+arg_10], r8
0x180002406  mov     [rsp+arg_18], r9
0x18000240b  sub     rsp, 68h
0x18000240f  movdqa  [rsp+68h+var_48], xmm0
0x180002415  movdqa  [rsp+68h+var_38], xmm1
0x18000241b  movdqa  [rsp+68h+var_28], xmm2
0x180002421  movdqa  [rsp+68h+var_18], xmm3
0x180002427  mov     rdx, rax
0x18000242a  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_fltlib_dll
0x180002431  call    __delayLoadHelper2
0x180002436  movdqa  xmm0, [rsp+68h+var_48]
0x18000243c  movdqa  xmm1, [rsp+68h+var_38]
0x180002442  movdqa  xmm2, [rsp+68h+var_28]
0x180002448  movdqa  xmm3, [rsp+68h+var_18]
0x18000244e  mov     rcx, [rsp+68h+arg_0]
0x180002453  mov     rdx, [rsp+68h+arg_8]
0x180002458  mov     r8, [rsp+68h+arg_10]
0x180002460  mov     r9, [rsp+68h+arg_18]
0x180002468  add     rsp, 68h
0x18000246c  jmp     short $+2
0x18000246e  jmp     rax
```
