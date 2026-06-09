# __tailMerge_profapi_dll

- ea: `0x18000241b`
- end: `0x180002494`
- name: `__tailMerge_profapi_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000249a`

## callees

- `0x18000241b`
- `0x180010df0`

## pseudocode

```c
__int64 __fastcall _tailMerge_profapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_profapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000241b  mov     [rsp+arg_0], rcx
0x180002420  mov     [rsp+arg_8], rdx
0x180002425  mov     [rsp+arg_10], r8
0x18000242a  mov     [rsp+arg_18], r9
0x18000242f  sub     rsp, 68h
0x180002433  movdqa  [rsp+68h+var_48], xmm0
0x180002439  movdqa  [rsp+68h+var_38], xmm1
0x18000243f  movdqa  [rsp+68h+var_28], xmm2
0x180002445  movdqa  [rsp+68h+var_18], xmm3
0x18000244b  mov     rdx, rax
0x18000244e  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_profapi_dll
0x180002455  call    __delayLoadHelper2
0x18000245a  movdqa  xmm0, [rsp+68h+var_48]
0x180002460  movdqa  xmm1, [rsp+68h+var_38]
0x180002466  movdqa  xmm2, [rsp+68h+var_28]
0x18000246c  movdqa  xmm3, [rsp+68h+var_18]
0x180002472  mov     rcx, [rsp+68h+arg_0]
0x180002477  mov     rdx, [rsp+68h+arg_8]
0x18000247c  mov     r8, [rsp+68h+arg_10]
0x180002484  mov     r9, [rsp+68h+arg_18]
0x18000248c  add     rsp, 68h
0x180002490  jmp     short $+2
0x180002492  jmp     rax
```
