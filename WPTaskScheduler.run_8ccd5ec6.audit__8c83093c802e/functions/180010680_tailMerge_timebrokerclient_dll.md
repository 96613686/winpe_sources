# __tailMerge_timebrokerclient_dll

- ea: `0x180010680`
- end: `0x1800106f9`
- name: `__tailMerge_timebrokerclient_dll`
- size: `121`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800106ff`
- `0x180010711`
- `0x180010723`
- `0x180010735`

## callees

- `0x180010680`
- `0x180020ac0`

## pseudocode

```c
__int64 __fastcall _tailMerge_timebrokerclient_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_timebrokerclient_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180010680  mov     [rsp+arg_0], rcx
0x180010685  mov     [rsp+arg_8], rdx
0x18001068a  mov     [rsp+arg_10], r8
0x18001068f  mov     [rsp+arg_18], r9
0x180010694  sub     rsp, 68h
0x180010698  movdqa  [rsp+68h+var_48], xmm0
0x18001069e  movdqa  [rsp+68h+var_38], xmm1
0x1800106a4  movdqa  [rsp+68h+var_28], xmm2
0x1800106aa  movdqa  [rsp+68h+var_18], xmm3
0x1800106b0  mov     rdx, rax
0x1800106b3  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_timebrokerclient_dll
0x1800106ba  call    __delayLoadHelper2
0x1800106bf  movdqa  xmm0, [rsp+68h+var_48]
0x1800106c5  movdqa  xmm1, [rsp+68h+var_38]
0x1800106cb  movdqa  xmm2, [rsp+68h+var_28]
0x1800106d1  movdqa  xmm3, [rsp+68h+var_18]
0x1800106d7  mov     rcx, [rsp+68h+arg_0]
0x1800106dc  mov     rdx, [rsp+68h+arg_8]
0x1800106e1  mov     r8, [rsp+68h+arg_10]
0x1800106e9  mov     r9, [rsp+68h+arg_18]
0x1800106f1  add     rsp, 68h
0x1800106f5  jmp     short $+2
0x1800106f7  jmp     rax
```
