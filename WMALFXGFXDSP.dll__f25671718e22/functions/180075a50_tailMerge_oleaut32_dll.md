# __tailMerge_oleaut32_dll

- ea: `0x180075a50`
- end: `0x180075ac9`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180075acf`
- `0x180075ae1`

## callees

- `0x1800131d0`
- `0x180075a50`

## pseudocode

```c
__int64 __fastcall _tailMerge_oleaut32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_oleaut32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180075a50  mov     [rsp+arg_0], rcx
0x180075a55  mov     [rsp+arg_8], rdx
0x180075a5a  mov     [rsp+arg_10], r8
0x180075a5f  mov     [rsp+arg_18], r9
0x180075a64  sub     rsp, 68h
0x180075a68  movdqa  [rsp+68h+var_48], xmm0
0x180075a6e  movdqa  [rsp+68h+var_38], xmm1
0x180075a74  movdqa  [rsp+68h+var_28], xmm2
0x180075a7a  movdqa  [rsp+68h+var_18], xmm3
0x180075a80  mov     rdx, rax
0x180075a83  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180075a8a  call    __delayLoadHelper2
0x180075a8f  movdqa  xmm0, [rsp+68h+var_48]
0x180075a95  movdqa  xmm1, [rsp+68h+var_38]
0x180075a9b  movdqa  xmm2, [rsp+68h+var_28]
0x180075aa1  movdqa  xmm3, [rsp+68h+var_18]
0x180075aa7  mov     rcx, [rsp+68h+arg_0]
0x180075aac  mov     rdx, [rsp+68h+arg_8]
0x180075ab1  mov     r8, [rsp+68h+arg_10]
0x180075ab9  mov     r9, [rsp+68h+arg_18]
0x180075ac1  add     rsp, 68h
0x180075ac5  jmp     short $+2
0x180075ac7  jmp     rax
```
