# __tailMerge_urlmon_dll

- ea: `0x180002861`
- end: `0x1800028da`
- name: `__tailMerge_urlmon_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028e0`

## callees

- `0x180002861`
- `0x180013920`

## pseudocode

```c
__int64 __fastcall _tailMerge_urlmon_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_urlmon_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002861  mov     [rsp+arg_0], rcx
0x180002866  mov     [rsp+arg_8], rdx
0x18000286b  mov     [rsp+arg_10], r8
0x180002870  mov     [rsp+arg_18], r9
0x180002875  sub     rsp, 68h
0x180002879  movdqa  [rsp+68h+var_48], xmm0
0x18000287f  movdqa  [rsp+68h+var_38], xmm1
0x180002885  movdqa  [rsp+68h+var_28], xmm2
0x18000288b  movdqa  [rsp+68h+var_18], xmm3
0x180002891  mov     rdx, rax
0x180002894  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_urlmon_dll
0x18000289b  call    __delayLoadHelper2
0x1800028a0  movdqa  xmm0, [rsp+68h+var_48]
0x1800028a6  movdqa  xmm1, [rsp+68h+var_38]
0x1800028ac  movdqa  xmm2, [rsp+68h+var_28]
0x1800028b2  movdqa  xmm3, [rsp+68h+var_18]
0x1800028b8  mov     rcx, [rsp+68h+arg_0]
0x1800028bd  mov     rdx, [rsp+68h+arg_8]
0x1800028c2  mov     r8, [rsp+68h+arg_10]
0x1800028ca  mov     r9, [rsp+68h+arg_18]
0x1800028d2  add     rsp, 68h
0x1800028d6  jmp     short $+2
0x1800028d8  jmp     rax
```
