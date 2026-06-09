# CmRegUtilCreateWstrKey

- ea: `0x14000e6b8`
- end: `0x14000e70f`
- name: `CmRegUtilCreateWstrKey`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dea8`
- `0x14000e390`

## callees

- `0x1400022c0`
- `0x14000e60c`
- `0x14000e6b8`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  void *v10; // r10
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
    return CmRegUtilCreateUcKey(v10, &DestinationString, v8, v9, a5, a6, a7);
  return result;
}

```

## disassembly

```asm
0x14000e6b8  sub     rsp, 58h
0x14000e6bc  mov     r10, rcx
0x14000e6bf  xorps   xmm0, xmm0
0x14000e6c2  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14000e6c7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14000e6cc  call    WdmlibRtlInitUnicodeStringEx
0x14000e6d1  test    eax, eax
0x14000e6d3  js      short loc_14000E709
0x14000e6d5  mov     rax, [rsp+58h+arg_30]
0x14000e6dd  lea     rdx, [rsp+58h+DestinationString]
0x14000e6e2  mov     [rsp+58h+var_28], rax
0x14000e6e7  mov     rcx, r10
0x14000e6ea  mov     rax, [rsp+58h+arg_28]
0x14000e6f2  mov     [rsp+58h+var_30], rax
0x14000e6f7  mov     rax, [rsp+58h+arg_20]
0x14000e6ff  mov     [rsp+58h+var_38], rax
0x14000e704  call    CmRegUtilCreateUcKey
0x14000e709  add     rsp, 58h
0x14000e70d  retn
```
