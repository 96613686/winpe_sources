# __tailMerge_samlib_dll

- ea: `0x180010184`
- end: `0x1800101fd`
- name: `__tailMerge_samlib_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010203`
- `0x180010215`
- `0x180010227`
- `0x180010239`
- `0x18001024b`
- `0x18001025d`
- `0x18001026f`
- `0x180010281`
- `0x180010293`
- `0x1800102a5`

## callees

- `0x18000e230`
- `0x180010184`

## pseudocode

```c
__int64 __fastcall _tailMerge_samlib_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_samlib_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010184  mov     [rsp+arg_0], rcx
0x180010189  mov     [rsp+arg_8], rdx
0x18001018e  mov     [rsp+arg_10], r8
0x180010193  mov     [rsp+arg_18], r9
0x180010198  sub     rsp, 68h
0x18001019c  movdqa  [rsp+68h+var_48], xmm0
0x1800101a2  movdqa  [rsp+68h+var_38], xmm1
0x1800101a8  movdqa  [rsp+68h+var_28], xmm2
0x1800101ae  movdqa  [rsp+68h+var_18], xmm3
0x1800101b4  mov     rdx, rax
0x1800101b7  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_samlib_dll
0x1800101be  call    __delayLoadHelper2
0x1800101c3  movdqa  xmm0, [rsp+68h+var_48]
0x1800101c9  movdqa  xmm1, [rsp+68h+var_38]
0x1800101cf  movdqa  xmm2, [rsp+68h+var_28]
0x1800101d5  movdqa  xmm3, [rsp+68h+var_18]
0x1800101db  mov     rcx, [rsp+68h+arg_0]
0x1800101e0  mov     rdx, [rsp+68h+arg_8]
0x1800101e5  mov     r8, [rsp+68h+arg_10]
0x1800101ed  mov     r9, [rsp+68h+arg_18]
0x1800101f5  add     rsp, 68h
0x1800101f9  jmp     short $+2
0x1800101fb  jmp     rax
```
