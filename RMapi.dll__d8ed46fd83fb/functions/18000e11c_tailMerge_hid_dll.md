# __tailMerge_hid_dll

- ea: `0x18000e11c`
- end: `0x18000e195`
- name: `__tailMerge_hid_dll`
- size: `121`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e19b`
- `0x18000e1ad`
- `0x18000e1bf`
- `0x18000e25c`
- `0x18000e26e`
- `0x18000e280`
- `0x18000e292`
- `0x18000e2a4`
- `0x18000e2fe`
- `0x18000e310`
- `0x18000e322`

## callees

- `0x180008130`
- `0x18000e11c`

## pseudocode

```c
__int64 __fastcall _tailMerge_hid_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_hid_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e11c  mov     [rsp+arg_0], rcx
0x18000e121  mov     [rsp+arg_8], rdx
0x18000e126  mov     [rsp+arg_10], r8
0x18000e12b  mov     [rsp+arg_18], r9
0x18000e130  sub     rsp, 68h
0x18000e134  movdqa  [rsp+68h+var_48], xmm0
0x18000e13a  movdqa  [rsp+68h+var_38], xmm1
0x18000e140  movdqa  [rsp+68h+var_28], xmm2
0x18000e146  movdqa  [rsp+68h+var_18], xmm3
0x18000e14c  mov     rdx, rax
0x18000e14f  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_hid_dll
0x18000e156  call    __delayLoadHelper2
0x18000e15b  movdqa  xmm0, [rsp+68h+var_48]
0x18000e161  movdqa  xmm1, [rsp+68h+var_38]
0x18000e167  movdqa  xmm2, [rsp+68h+var_28]
0x18000e16d  movdqa  xmm3, [rsp+68h+var_18]
0x18000e173  mov     rcx, [rsp+68h+arg_0]
0x18000e178  mov     rdx, [rsp+68h+arg_8]
0x18000e17d  mov     r8, [rsp+68h+arg_10]
0x18000e185  mov     r9, [rsp+68h+arg_18]
0x18000e18d  add     rsp, 68h
0x18000e191  jmp     short $+2
0x18000e193  jmp     rax
```
