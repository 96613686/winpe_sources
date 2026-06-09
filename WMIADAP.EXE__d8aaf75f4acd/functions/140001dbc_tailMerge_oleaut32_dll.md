# __tailMerge_oleaut32_dll

- ea: `0x140001dbc`
- end: `0x140001e35`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001e3b`
- `0x140001e4d`
- `0x140001e5f`
- `0x140001e71`
- `0x140001e83`
- `0x1400029b2`
- `0x140002a4f`
- `0x140002a61`
- `0x140002a73`
- `0x140002a85`
- `0x140002a97`
- `0x140002aa9`

## callees

- `0x140001dbc`
- `0x14000fc40`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140001dbc  mov     [rsp+arg_0], rcx
0x140001dc1  mov     [rsp+arg_8], rdx
0x140001dc6  mov     [rsp+arg_10], r8
0x140001dcb  mov     [rsp+arg_18], r9
0x140001dd0  sub     rsp, 68h
0x140001dd4  movdqa  [rsp+68h+var_48], xmm0
0x140001dda  movdqa  [rsp+68h+var_38], xmm1
0x140001de0  movdqa  [rsp+68h+var_28], xmm2
0x140001de6  movdqa  [rsp+68h+var_18], xmm3
0x140001dec  mov     rdx, rax
0x140001def  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x140001df6  call    __delayLoadHelper2
0x140001dfb  movdqa  xmm0, [rsp+68h+var_48]
0x140001e01  movdqa  xmm1, [rsp+68h+var_38]
0x140001e07  movdqa  xmm2, [rsp+68h+var_28]
0x140001e0d  movdqa  xmm3, [rsp+68h+var_18]
0x140001e13  mov     rcx, [rsp+68h+arg_0]
0x140001e18  mov     rdx, [rsp+68h+arg_8]
0x140001e1d  mov     r8, [rsp+68h+arg_10]
0x140001e25  mov     r9, [rsp+68h+arg_18]
0x140001e2d  add     rsp, 68h
0x140001e31  jmp     short $+2
0x140001e33  jmp     rax
```
