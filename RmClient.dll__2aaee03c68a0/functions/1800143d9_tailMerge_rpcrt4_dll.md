# __tailMerge_rpcrt4_dll

- ea: `0x1800143d9`
- end: `0x180014452`
- name: `__tailMerge_rpcrt4_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014458`
- `0x18001446a`
- `0x18001447c`
- `0x180014a87`
- `0x180014af3`
- `0x180014b05`
- `0x180014b17`

## callees

- `0x18000f260`
- `0x1800143d9`

## pseudocode

```c
__int64 __fastcall _tailMerge_rpcrt4_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          (__int64)&_DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800143d9  mov     [rsp+arg_0], rcx
0x1800143de  mov     [rsp+arg_8], rdx
0x1800143e3  mov     [rsp+arg_10], r8
0x1800143e8  mov     [rsp+arg_18], r9
0x1800143ed  sub     rsp, 68h
0x1800143f1  movdqa  [rsp+68h+var_48], xmm0
0x1800143f7  movdqa  [rsp+68h+var_38], xmm1
0x1800143fd  movdqa  [rsp+68h+var_28], xmm2
0x180014403  movdqa  [rsp+68h+var_18], xmm3
0x180014409  mov     rdx, rax
0x18001440c  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_rpcrt4_dll
0x180014413  call    __delayLoadHelper2
0x180014418  movdqa  xmm0, [rsp+68h+var_48]
0x18001441e  movdqa  xmm1, [rsp+68h+var_38]
0x180014424  movdqa  xmm2, [rsp+68h+var_28]
0x18001442a  movdqa  xmm3, [rsp+68h+var_18]
0x180014430  mov     rcx, [rsp+68h+arg_0]
0x180014435  mov     rdx, [rsp+68h+arg_8]
0x18001443a  mov     r8, [rsp+68h+arg_10]
0x180014442  mov     r9, [rsp+68h+arg_18]
0x18001444a  add     rsp, 68h
0x18001444e  jmp     short $+2
0x180014450  jmp     rax
```
