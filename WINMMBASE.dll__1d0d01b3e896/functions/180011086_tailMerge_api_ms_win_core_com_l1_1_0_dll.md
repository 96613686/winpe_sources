# __tailMerge_api_ms_win_core_com_l1_1_0_dll

- ea: `0x180011086`
- end: `0x1800110ff`
- name: `__tailMerge_api_ms_win_core_com_l1_1_0_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011105`
- `0x18001122d`
- `0x1800112dc`
- `0x180011324`
- `0x180011348`
- `0x18001135a`

## callees

- `0x18000f240`
- `0x180011086`

## pseudocode

```c
__int64 __fastcall _tailMerge_api_ms_win_core_com_l1_1_0_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180011086  mov     [rsp+arg_0], rcx
0x18001108b  mov     [rsp+arg_8], rdx
0x180011090  mov     [rsp+arg_10], r8
0x180011095  mov     [rsp+arg_18], r9
0x18001109a  sub     rsp, 68h
0x18001109e  movdqa  [rsp+68h+var_48], xmm0
0x1800110a4  movdqa  [rsp+68h+var_38], xmm1
0x1800110aa  movdqa  [rsp+68h+var_28], xmm2
0x1800110b0  movdqa  [rsp+68h+var_18], xmm3
0x1800110b6  mov     rdx, rax
0x1800110b9  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_api_ms_win_core_com_l1_1_0_dll
0x1800110c0  call    __delayLoadHelper2
0x1800110c5  movdqa  xmm0, [rsp+68h+var_48]
0x1800110cb  movdqa  xmm1, [rsp+68h+var_38]
0x1800110d1  movdqa  xmm2, [rsp+68h+var_28]
0x1800110d7  movdqa  xmm3, [rsp+68h+var_18]
0x1800110dd  mov     rcx, [rsp+68h+arg_0]
0x1800110e2  mov     rdx, [rsp+68h+arg_8]
0x1800110e7  mov     r8, [rsp+68h+arg_10]
0x1800110ef  mov     r9, [rsp+68h+arg_18]
0x1800110f7  add     rsp, 68h
0x1800110fb  jmp     short $+2
0x1800110fd  jmp     rax
```
