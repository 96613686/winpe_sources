# __tailMerge_winscard_dll

- ea: `0x180002955`
- end: `0x1800029ce`
- name: `__tailMerge_winscard_dll`
- size: `121`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800029d4`
- `0x1800029e6`
- `0x1800029f8`
- `0x180002a0a`
- `0x180002a1c`
- `0x180002a2e`
- `0x180002a40`
- `0x180002a52`
- `0x180002a64`
- `0x180002a76`
- `0x180002a88`
- `0x180002a9a`
- `0x180002aac`
- `0x180002abe`
- `0x180002ad0`
- `0x180002ae2`
- `0x180002af4`
- `0x180002b06`

## callees

- `0x180002955`
- `0x18002cea0`

## pseudocode

```c
__int64 __fastcall _tailMerge_winscard_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_winscard_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002955  mov     [rsp+arg_0], rcx
0x18000295a  mov     [rsp+arg_8], rdx
0x18000295f  mov     [rsp+arg_10], r8
0x180002964  mov     [rsp+arg_18], r9
0x180002969  sub     rsp, 68h
0x18000296d  movdqa  [rsp+68h+var_48], xmm0
0x180002973  movdqa  [rsp+68h+var_38], xmm1
0x180002979  movdqa  [rsp+68h+var_28], xmm2
0x18000297f  movdqa  [rsp+68h+var_18], xmm3
0x180002985  mov     rdx, rax
0x180002988  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_winscard_dll
0x18000298f  call    __delayLoadHelper2
0x180002994  movdqa  xmm0, [rsp+68h+var_48]
0x18000299a  movdqa  xmm1, [rsp+68h+var_38]
0x1800029a0  movdqa  xmm2, [rsp+68h+var_28]
0x1800029a6  movdqa  xmm3, [rsp+68h+var_18]
0x1800029ac  mov     rcx, [rsp+68h+arg_0]
0x1800029b1  mov     rdx, [rsp+68h+arg_8]
0x1800029b6  mov     r8, [rsp+68h+arg_10]
0x1800029be  mov     r9, [rsp+68h+arg_18]
0x1800029c6  add     rsp, 68h
0x1800029ca  jmp     short $+2
0x1800029cc  jmp     rax
```
