# ByteArrayToSafeArray(uchar *,ulong,tagSAFEARRAY * *)

- ea: `0x1800020c0`
- end: `0x1800021aa`
- name: `?ByteArrayToSafeArray@@YAJPEAEKPEAPEAUtagSAFEARRAY@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, size_t Size, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020c0`
- `0x180003574`
- `0x18000361c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000210f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000210f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800021a2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800021a2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180002133`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180002133`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002161`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002199`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002161`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002199`

## pseudocode

```c
__int64 __fastcall ByteArrayToSafeArray(unsigned __int8 *Src, size_t Size, struct tagSAFEARRAY **a3)
{
  size_t v3; // r14
  HRESULT v6; // ebx
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // rdi
  void *v9; // rcx
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+20h] BYREF

  v3 = (unsigned int)Size;
  ppvData = 0;
  rgsabound.lLbound = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  rgsabound.lLbound = 0;
  rgsabound.cElements = Size;
  v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v8 = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v6 = 0;
  if ( !Src )
  {
LABEL_11:
    *a3 = v8;
    return (unsigned int)v6;
  }
  v6 = SafeArrayAccessData(v7, &ppvData);
  if ( v6 >= 0 )
  {
    v9 = ppvData;
    if ( !ppvData )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(0);
      v9 = ppvData;
    }
    memcpy_0(v9, Src, v3);
    v6 = SafeArrayUnaccessData(v8);
    if ( v6 >= 0 )
    {
      ppvData = 0;
      goto LABEL_11;
    }
  }
  if ( ppvData )
    SafeArrayUnaccessData(v8);
  SafeArrayDestroy(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800020c0  mov     [rsp+arg_0], rbx
0x1800020c5  mov     [rsp+arg_8], rbp
0x1800020ca  push    rsi
0x1800020cb  push    rdi
0x1800020cc  push    r14
0x1800020ce  sub     rsp, 20h
0x1800020d2  xor     eax, eax
0x1800020d4  mov     r14d, edx
0x1800020d7  mov     [rsp+38h+ppvData], 0
0x1800020e0  mov     rsi, r8
0x1800020e3  mov     [rsp+38h+rgsabound.lLbound], eax
0x1800020e7  mov     rbp, rcx
0x1800020ea  test    r8, r8
0x1800020ed  jnz     short loc_1800020F9
0x1800020ef  mov     ebx, 80070057h
0x1800020f4  jmp     loc_180002179
0x1800020f9  mov     ecx, 11h; vt
0x1800020fe  mov     [rsp+38h+rgsabound.lLbound], eax
0x180002102  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x180002107  mov     [rsp+38h+rgsabound.cElements], r14d
0x18000210c  lea     edx, [rcx-10h]; cDims
0x18000210f  call    cs:__imp_SafeArrayCreate
0x180002115  mov     rdi, rax
0x180002118  test    rax, rax
0x18000211b  jnz     short loc_180002124
0x18000211d  mov     ebx, 8007000Eh
0x180002122  jmp     short loc_180002179
0x180002124  xor     ebx, ebx
0x180002126  test    rbp, rbp
0x180002129  jz      short loc_180002176
0x18000212b  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180002130  mov     rcx, rdi; psa
0x180002133  call    cs:__imp_SafeArrayAccessData
0x180002139  mov     ebx, eax
0x18000213b  test    eax, eax
0x18000213d  js      short loc_18000218E
0x18000213f  mov     rcx, [rsp+38h+ppvData]
0x180002144  test    rcx, rcx
0x180002147  jnz     short loc_180002153
0x180002149  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000214e  mov     rcx, [rsp+38h+ppvData]; void *
0x180002153  mov     r8, r14; Size
0x180002156  mov     rdx, rbp; Src
0x180002159  call    memcpy_0
0x18000215e  mov     rcx, rdi; psa
0x180002161  call    cs:__imp_SafeArrayUnaccessData
0x180002167  mov     ebx, eax
0x180002169  test    eax, eax
0x18000216b  js      short loc_18000218E
0x18000216d  mov     [rsp+38h+ppvData], 0
0x180002176  mov     [rsi], rdi
0x180002179  mov     rbp, [rsp+38h+arg_8]
0x18000217e  mov     eax, ebx
0x180002180  mov     rbx, [rsp+38h+arg_0]
0x180002185  add     rsp, 20h
0x180002189  pop     r14
0x18000218b  pop     rdi
0x18000218c  pop     rsi
0x18000218d  retn
0x18000218e  cmp     [rsp+38h+ppvData], 0
0x180002194  jz      short loc_18000219F
0x180002196  mov     rcx, rdi; psa
0x180002199  call    cs:__imp_SafeArrayUnaccessData
0x18000219f  mov     rcx, rdi; psa
0x1800021a2  call    cs:__imp_SafeArrayDestroy
0x1800021a8  jmp     short loc_180002179
```
