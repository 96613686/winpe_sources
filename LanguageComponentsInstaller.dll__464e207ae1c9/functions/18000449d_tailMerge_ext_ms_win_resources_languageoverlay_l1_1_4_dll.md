# __tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll

- ea: `0x18000449d`
- end: `0x180004516`
- name: `__tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000451c`
- `0x18000452e`

## callees

- `0x18000449d`
- `0x180027c00`

## pseudocode

```c
__int64 __fastcall _tailMerge_ext_ms_win_resources_languageoverlay_l1_1_4_dll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resources_languageoverlay_l1_1_4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000449d  mov     [rsp+arg_0], rcx
0x1800044a2  mov     [rsp+arg_8], rdx
0x1800044a7  mov     [rsp+arg_10], r8
0x1800044ac  mov     [rsp+arg_18], r9
0x1800044b1  sub     rsp, 68h
0x1800044b5  movdqa  [rsp+68h+var_48], xmm0
0x1800044bb  movdqa  [rsp+68h+var_38], xmm1
0x1800044c1  movdqa  [rsp+68h+var_28], xmm2
0x1800044c7  movdqa  [rsp+68h+var_18], xmm3
0x1800044cd  mov     rdx, rax
0x1800044d0  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_ext_ms_win_resources_languageoverlay_l1_1_4_dll
0x1800044d7  call    __delayLoadHelper2
0x1800044dc  movdqa  xmm0, [rsp+68h+var_48]
0x1800044e2  movdqa  xmm1, [rsp+68h+var_38]
0x1800044e8  movdqa  xmm2, [rsp+68h+var_28]
0x1800044ee  movdqa  xmm3, [rsp+68h+var_18]
0x1800044f4  mov     rcx, [rsp+68h+arg_0]
0x1800044f9  mov     rdx, [rsp+68h+arg_8]
0x1800044fe  mov     r8, [rsp+68h+arg_10]
0x180004506  mov     r9, [rsp+68h+arg_18]
0x18000450e  add     rsp, 68h
0x180004512  jmp     short $+2
0x180004514  jmp     rax
```
