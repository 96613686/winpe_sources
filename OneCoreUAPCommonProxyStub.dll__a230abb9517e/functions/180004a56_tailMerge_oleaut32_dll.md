# __tailMerge_oleaut32_dll

- ea: `0x180004a56`
- end: `0x180004acf`
- name: `__tailMerge_oleaut32_dll`
- size: `121`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004ad5`
- `0x180004afc`
- `0x180004b1c`
- `0x180004b3c`
- `0x180004b5c`
- `0x180004b7c`
- `0x180004b9c`
- `0x180004bbc`
- `0x180004e8c`
- `0x180004eac`
- `0x180004ecc`
- `0x180004eec`
- `0x180004f0c`
- `0x180004f2c`
- `0x180004f4c`
- `0x180004f6c`
- `0x180004f8c`
- `0x18000501c`
- `0x1800050dc`
- `0x18000512c`
- `0x1800051bc`
- `0x18000524c`
- `0x1800052cc`
- `0x18000531c`

## callees

- `0x180002420`
- `0x180004a56`

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
0x180004a56  mov     [rsp+arg_0], rcx
0x180004a5b  mov     [rsp+arg_8], rdx
0x180004a60  mov     [rsp+arg_10], r8
0x180004a65  mov     [rsp+arg_18], r9
0x180004a6a  sub     rsp, 68h
0x180004a6e  movdqa  [rsp+68h+var_48], xmm0
0x180004a74  movdqa  [rsp+68h+var_38], xmm1
0x180004a7a  movdqa  [rsp+68h+var_28], xmm2
0x180004a80  movdqa  [rsp+68h+var_18], xmm3
0x180004a86  mov     rdx, rax
0x180004a89  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_oleaut32_dll
0x180004a90  call    __delayLoadHelper2
0x180004a95  movdqa  xmm0, [rsp+68h+var_48]
0x180004a9b  movdqa  xmm1, [rsp+68h+var_38]
0x180004aa1  movdqa  xmm2, [rsp+68h+var_28]
0x180004aa7  movdqa  xmm3, [rsp+68h+var_18]
0x180004aad  mov     rcx, [rsp+68h+arg_0]
0x180004ab2  mov     rdx, [rsp+68h+arg_8]
0x180004ab7  mov     r8, [rsp+68h+arg_10]
0x180004abf  mov     r9, [rsp+68h+arg_18]
0x180004ac7  add     rsp, 68h
0x180004acb  jmp     short $+2
0x180004acd  jmp     rax
```
