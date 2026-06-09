# __tailMerge_urlmon_dll

- ea: `0x1400025b8`
- end: `0x140002631`
- name: `__tailMerge_urlmon_dll`
- size: `121`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002637`
- `0x140002649`
- `0x14000265b`
- `0x14000266d`
- `0x14000267f`
- `0x140002691`

## callees

- `0x1400025b8`
- `0x140012e70`

## pseudocode

```c
__int64 __fastcall _tailMerge_urlmon_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *Helper2)(__int64, __int64, __int64, __int64); // rax

  Helper2 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))_delayLoadHelper2(
                                                                          &_DELAY_IMPORT_DESCRIPTOR_urlmon_dll,
                                                                          v4);
  return Helper2(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1400025b8  mov     [rsp+arg_0], rcx
0x1400025bd  mov     [rsp+arg_8], rdx
0x1400025c2  mov     [rsp+arg_10], r8
0x1400025c7  mov     [rsp+arg_18], r9
0x1400025cc  sub     rsp, 68h
0x1400025d0  movdqa  [rsp+68h+var_48], xmm0
0x1400025d6  movdqa  [rsp+68h+var_38], xmm1
0x1400025dc  movdqa  [rsp+68h+var_28], xmm2
0x1400025e2  movdqa  [rsp+68h+var_18], xmm3
0x1400025e8  mov     rdx, rax
0x1400025eb  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_urlmon_dll
0x1400025f2  call    __delayLoadHelper2
0x1400025f7  movdqa  xmm0, [rsp+68h+var_48]
0x1400025fd  movdqa  xmm1, [rsp+68h+var_38]
0x140002603  movdqa  xmm2, [rsp+68h+var_28]
0x140002609  movdqa  xmm3, [rsp+68h+var_18]
0x14000260f  mov     rcx, [rsp+68h+arg_0]
0x140002614  mov     rdx, [rsp+68h+arg_8]
0x140002619  mov     r8, [rsp+68h+arg_10]
0x140002621  mov     r9, [rsp+68h+arg_18]
0x140002629  add     rsp, 68h
0x14000262d  jmp     short $+2
0x14000262f  jmp     rax
```
