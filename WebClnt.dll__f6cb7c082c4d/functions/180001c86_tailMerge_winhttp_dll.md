# __tailMerge_winhttp_dll

- ea: `0x180001c86`
- end: `0x180001cff`
- name: `__tailMerge_winhttp_dll`
- size: `121`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001d05`
- `0x180001d17`
- `0x180001d29`
- `0x180001d3b`
- `0x180001d4d`
- `0x180001d5f`
- `0x180001d71`
- `0x180001d83`
- `0x180001d95`
- `0x180001da7`
- `0x180001db9`
- `0x180001dcb`
- `0x180001ddd`
- `0x180001def`
- `0x180001e01`
- `0x180001e13`
- `0x180001e25`
- `0x1800022ab`
- `0x1800022bd`
- `0x1800022cf`

## callees

- `0x180001c86`
- `0x18002ce10`

## pseudocode

```c
__int64 __fastcall _tailMerge_winhttp_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winhttp_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001c86  mov     [rsp+arg_0], rcx
0x180001c8b  mov     [rsp+arg_8], rdx
0x180001c90  mov     [rsp+arg_10], r8
0x180001c95  mov     [rsp+arg_18], r9
0x180001c9a  sub     rsp, 68h
0x180001c9e  movdqa  [rsp+68h+var_48], xmm0
0x180001ca4  movdqa  [rsp+68h+var_38], xmm1
0x180001caa  movdqa  [rsp+68h+var_28], xmm2
0x180001cb0  movdqa  [rsp+68h+var_18], xmm3
0x180001cb6  mov     rdx, rax
0x180001cb9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winhttp_dll
0x180001cc0  call    __delayLoadHelper2
0x180001cc5  movdqa  xmm0, [rsp+68h+var_48]
0x180001ccb  movdqa  xmm1, [rsp+68h+var_38]
0x180001cd1  movdqa  xmm2, [rsp+68h+var_28]
0x180001cd7  movdqa  xmm3, [rsp+68h+var_18]
0x180001cdd  mov     rcx, [rsp+68h+arg_0]
0x180001ce2  mov     rdx, [rsp+68h+arg_8]
0x180001ce7  mov     r8, [rsp+68h+arg_10]
0x180001cef  mov     r9, [rsp+68h+arg_18]
0x180001cf7  add     rsp, 68h
0x180001cfb  jmp     short $+2
0x180001cfd  jmp     rax
```
