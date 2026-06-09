# __tailMerge_bcrypt_dll

- ea: `0x180001990`
- end: `0x180001a09`
- name: `__tailMerge_bcrypt_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a0f`
- `0x180001a21`
- `0x180001abe`
- `0x180001ad0`
- `0x180001ae2`
- `0x180001af4`
- `0x180001b06`
- `0x180001b18`
- `0x180001c88`
- `0x180001c9a`
- `0x180001cac`
- `0x180001cbe`

## callees

- `0x180001990`
- `0x18000c450`

## pseudocode

```c
__int64 __fastcall _tailMerge_bcrypt_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_bcrypt_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001990  mov     [rsp+arg_0], rcx
0x180001995  mov     [rsp+arg_8], rdx
0x18000199a  mov     [rsp+arg_10], r8
0x18000199f  mov     [rsp+arg_18], r9
0x1800019a4  sub     rsp, 68h
0x1800019a8  movdqa  [rsp+68h+var_48], xmm0
0x1800019ae  movdqa  [rsp+68h+var_38], xmm1
0x1800019b4  movdqa  [rsp+68h+var_28], xmm2
0x1800019ba  movdqa  [rsp+68h+var_18], xmm3
0x1800019c0  mov     rdx, rax
0x1800019c3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_bcrypt_dll
0x1800019ca  call    __delayLoadHelper2
0x1800019cf  movdqa  xmm0, [rsp+68h+var_48]
0x1800019d5  movdqa  xmm1, [rsp+68h+var_38]
0x1800019db  movdqa  xmm2, [rsp+68h+var_28]
0x1800019e1  movdqa  xmm3, [rsp+68h+var_18]
0x1800019e7  mov     rcx, [rsp+68h+arg_0]
0x1800019ec  mov     rdx, [rsp+68h+arg_8]
0x1800019f1  mov     r8, [rsp+68h+arg_10]
0x1800019f9  mov     r9, [rsp+68h+arg_18]
0x180001a01  add     rsp, 68h
0x180001a05  jmp     short $+2
0x180001a07  jmp     rax
```
