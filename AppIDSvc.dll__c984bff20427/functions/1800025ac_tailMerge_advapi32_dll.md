# __tailMerge_advapi32_dll

- ea: `0x1800025ac`
- end: `0x180002625`
- name: `__tailMerge_advapi32_dll`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002630`
- `0x180002650`
- `0x180002670`
- `0x180002690`

## callees

- `0x1800025ac`
- `0x18000ba60`

## pseudocode

```c
__int64 __fastcall _tailMerge_advapi32_dll(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  FARPROC *v4; // rax
  FARPROC Helper2; // rax

  Helper2 = _delayLoadHelper2((const ImgDelayDescr *)&_DELAY_IMPORT_DESCRIPTOR_advapi32_dll, v4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64))Helper2)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800025ac  mov     [rsp+arg_0], rcx
0x1800025b1  mov     [rsp+arg_8], rdx
0x1800025b6  mov     [rsp+arg_10], r8
0x1800025bb  mov     [rsp+arg_18], r9
0x1800025c0  sub     rsp, 68h
0x1800025c4  movdqa  [rsp+68h+var_48], xmm0
0x1800025ca  movdqa  [rsp+68h+var_38], xmm1
0x1800025d0  movdqa  [rsp+68h+var_28], xmm2
0x1800025d6  movdqa  [rsp+68h+var_18], xmm3
0x1800025dc  mov     rdx, rax
0x1800025df  lea     rcx, __DELAY_IMPORT_DESCRIPTOR_advapi32_dll
0x1800025e6  call    __delayLoadHelper2
0x1800025eb  movdqa  xmm0, [rsp+68h+var_48]
0x1800025f1  movdqa  xmm1, [rsp+68h+var_38]
0x1800025f7  movdqa  xmm2, [rsp+68h+var_28]
0x1800025fd  movdqa  xmm3, [rsp+68h+var_18]
0x180002603  mov     rcx, [rsp+68h+arg_0]
0x180002608  mov     rdx, [rsp+68h+arg_8]
0x18000260d  mov     r8, [rsp+68h+arg_10]
0x180002615  mov     r9, [rsp+68h+arg_18]
0x18000261d  add     rsp, 68h
0x180002621  jmp     short $+2
0x180002623  jmp     rax
```
