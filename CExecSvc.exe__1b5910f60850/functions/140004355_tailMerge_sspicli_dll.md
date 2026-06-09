# __tailMerge_sspicli_dll

- ea: `0x140004355`
- end: `0x1400043ce`
- name: `__tailMerge_sspicli_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400043d4`

## callees

- `0x140004355`
- `0x14001d800`

## pseudocode

```c
__int64 __fastcall _tailMerge_sspicli_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_sspicli_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140004355  mov     [rsp+arg_0], rcx
0x14000435a  mov     [rsp+arg_8], rdx
0x14000435f  mov     [rsp+arg_10], r8
0x140004364  mov     [rsp+arg_18], r9
0x140004369  sub     rsp, 68h
0x14000436d  movdqa  [rsp+68h+var_48], xmm0
0x140004373  movdqa  [rsp+68h+var_38], xmm1
0x140004379  movdqa  [rsp+68h+var_28], xmm2
0x14000437f  movdqa  [rsp+68h+var_18], xmm3
0x140004385  mov     rdx, rax
0x140004388  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_sspicli_dll
0x14000438f  call    __delayLoadHelper2
0x140004394  movdqa  xmm0, [rsp+68h+var_48]
0x14000439a  movdqa  xmm1, [rsp+68h+var_38]
0x1400043a0  movdqa  xmm2, [rsp+68h+var_28]
0x1400043a6  movdqa  xmm3, [rsp+68h+var_18]
0x1400043ac  mov     rcx, [rsp+68h+arg_0]
0x1400043b1  mov     rdx, [rsp+68h+arg_8]
0x1400043b6  mov     r8, [rsp+68h+arg_10]
0x1400043be  mov     r9, [rsp+68h+arg_18]
0x1400043c6  add     rsp, 68h
0x1400043ca  jmp     short $+2
0x1400043cc  jmp     rax
```
