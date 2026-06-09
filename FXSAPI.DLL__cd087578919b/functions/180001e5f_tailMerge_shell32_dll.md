# __tailMerge_shell32_dll

- ea: `0x180001e5f`
- end: `0x180001ed8`
- name: `__tailMerge_shell32_dll`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ede`
- `0x180001ef0`
- `0x180001f02`
- `0x180001f14`
- `0x180001f26`
- `0x180001f38`
- `0x180001f4a`

## callees

- `0x180001e5f`
- `0x18003cfd0`

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
0x180001e5f  mov     [rsp+arg_0], rcx
0x180001e64  mov     [rsp+arg_8], rdx
0x180001e69  mov     [rsp+arg_10], r8
0x180001e6e  mov     [rsp+arg_18], r9
0x180001e73  sub     rsp, 68h
0x180001e77  movdqa  [rsp+68h+var_48], xmm0
0x180001e7d  movdqa  [rsp+68h+var_38], xmm1
0x180001e83  movdqa  [rsp+68h+var_28], xmm2
0x180001e89  movdqa  [rsp+68h+var_18], xmm3
0x180001e8f  mov     rdx, rax
0x180001e92  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_shell32_dll
0x180001e99  call    __delayLoadHelper2
0x180001e9e  movdqa  xmm0, [rsp+68h+var_48]
0x180001ea4  movdqa  xmm1, [rsp+68h+var_38]
0x180001eaa  movdqa  xmm2, [rsp+68h+var_28]
0x180001eb0  movdqa  xmm3, [rsp+68h+var_18]
0x180001eb6  mov     rcx, [rsp+68h+arg_0]
0x180001ebb  mov     rdx, [rsp+68h+arg_8]
0x180001ec0  mov     r8, [rsp+68h+arg_10]
0x180001ec8  mov     r9, [rsp+68h+arg_18]
0x180001ed0  add     rsp, 68h
0x180001ed4  jmp     short $+2
0x180001ed6  jmp     rax
```
