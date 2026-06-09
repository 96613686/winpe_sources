# __tailMerge_wldap32_dll

- ea: `0x180002039`
- end: `0x1800020b2`
- name: `__tailMerge_wldap32_dll`
- size: `121`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800020b8`
- `0x1800020ca`
- `0x1800020dc`
- `0x1800020ee`
- `0x180002100`
- `0x180002112`
- `0x180002124`
- `0x180002136`
- `0x180002148`
- `0x18000215a`
- `0x18000216c`
- `0x18000217e`
- `0x1800022b8`
- `0x1800022ca`
- `0x1800022dc`
- `0x1800022ee`
- `0x180002300`
- `0x180002312`
- `0x180002324`
- `0x180002336`
- `0x180002348`
- `0x18000235a`

## callees

- `0x180002039`
- `0x18001a560`

## pseudocode

```c
__int64 __fastcall _tailMerge_wldap32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wldap32_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002039  mov     [rsp+arg_0], rcx
0x18000203e  mov     [rsp+arg_8], rdx
0x180002043  mov     [rsp+arg_10], r8
0x180002048  mov     [rsp+arg_18], r9
0x18000204d  sub     rsp, 68h
0x180002051  movdqa  [rsp+68h+var_48], xmm0
0x180002057  movdqa  [rsp+68h+var_38], xmm1
0x18000205d  movdqa  [rsp+68h+var_28], xmm2
0x180002063  movdqa  [rsp+68h+var_18], xmm3
0x180002069  mov     rdx, rax
0x18000206c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wldap32_dll
0x180002073  call    __delayLoadHelper2
0x180002078  movdqa  xmm0, [rsp+68h+var_48]
0x18000207e  movdqa  xmm1, [rsp+68h+var_38]
0x180002084  movdqa  xmm2, [rsp+68h+var_28]
0x18000208a  movdqa  xmm3, [rsp+68h+var_18]
0x180002090  mov     rcx, [rsp+68h+arg_0]
0x180002095  mov     rdx, [rsp+68h+arg_8]
0x18000209a  mov     r8, [rsp+68h+arg_10]
0x1800020a2  mov     r9, [rsp+68h+arg_18]
0x1800020aa  add     rsp, 68h
0x1800020ae  jmp     short $+2
0x1800020b0  jmp     rax
```
