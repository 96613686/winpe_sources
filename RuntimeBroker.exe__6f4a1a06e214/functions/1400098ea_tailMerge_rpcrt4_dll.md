# __tailMerge_rpcrt4_dll

- ea: `0x1400098ea`
- end: `0x140009963`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009969`

## callees

- `0x140006ad0`
- `0x1400098ea`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400098ea  mov     [rsp+arg_0], rcx
0x1400098ef  mov     [rsp+arg_8], rdx
0x1400098f4  mov     [rsp+arg_10], r8
0x1400098f9  mov     [rsp+arg_18], r9
0x1400098fe  sub     rsp, 68h
0x140009902  movdqa  [rsp+68h+var_48], xmm0
0x140009908  movdqa  [rsp+68h+var_38], xmm1
0x14000990e  movdqa  [rsp+68h+var_28], xmm2
0x140009914  movdqa  [rsp+68h+var_18], xmm3
0x14000991a  mov     rdx, rax
0x14000991d  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x140009924  call    __delayLoadHelper2
0x140009929  movdqa  xmm0, [rsp+68h+var_48]
0x14000992f  movdqa  xmm1, [rsp+68h+var_38]
0x140009935  movdqa  xmm2, [rsp+68h+var_28]
0x14000993b  movdqa  xmm3, [rsp+68h+var_18]
0x140009941  mov     rcx, [rsp+68h+arg_0]
0x140009946  mov     rdx, [rsp+68h+arg_8]
0x14000994b  mov     r8, [rsp+68h+arg_10]
0x140009953  mov     r9, [rsp+68h+arg_18]
0x14000995b  add     rsp, 68h
0x14000995f  jmp     short $+2
0x140009961  jmp     rax
```
