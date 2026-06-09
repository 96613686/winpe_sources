# __tailMerge_wlanapi_dll

- ea: `0x18002abfd`
- end: `0x18002ac76`
- name: `__tailMerge_wlanapi_dll`
- size: `121`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002ac7c`
- `0x18002ac8e`
- `0x18002aca0`
- `0x18002acb2`
- `0x18002ada3`
- `0x18002adb5`
- `0x18002adc7`
- `0x18002add9`
- `0x18002adeb`
- `0x18002adfd`
- `0x18002ae0f`
- `0x18002ae21`

## callees

- `0x18001ddc0`
- `0x18002abfd`

## pseudocode

```c
__int64 __fastcall _tailMerge_wlanapi_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_wlanapi_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18002abfd  mov     [rsp+arg_0], rcx
0x18002ac02  mov     [rsp+arg_8], rdx
0x18002ac07  mov     [rsp+arg_10], r8
0x18002ac0c  mov     [rsp+arg_18], r9
0x18002ac11  sub     rsp, 68h
0x18002ac15  movdqa  [rsp+68h+var_48], xmm0
0x18002ac1b  movdqa  [rsp+68h+var_38], xmm1
0x18002ac21  movdqa  [rsp+68h+var_28], xmm2
0x18002ac27  movdqa  [rsp+68h+var_18], xmm3
0x18002ac2d  mov     rdx, rax
0x18002ac30  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_wlanapi_dll
0x18002ac37  call    __delayLoadHelper2
0x18002ac3c  movdqa  xmm0, [rsp+68h+var_48]
0x18002ac42  movdqa  xmm1, [rsp+68h+var_38]
0x18002ac48  movdqa  xmm2, [rsp+68h+var_28]
0x18002ac4e  movdqa  xmm3, [rsp+68h+var_18]
0x18002ac54  mov     rcx, [rsp+68h+arg_0]
0x18002ac59  mov     rdx, [rsp+68h+arg_8]
0x18002ac5e  mov     r8, [rsp+68h+arg_10]
0x18002ac66  mov     r9, [rsp+68h+arg_18]
0x18002ac6e  add     rsp, 68h
0x18002ac72  jmp     short $+2
0x18002ac74  jmp     rax
```
