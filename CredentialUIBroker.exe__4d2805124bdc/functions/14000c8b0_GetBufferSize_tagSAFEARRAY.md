# GetBufferSize(tagSAFEARRAY *)

- ea: `0x14000c8b0`
- end: `0x14000c948`
- name: `?GetBufferSize@@YAKPEAUtagSAFEARRAY@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(SAFEARRAY *psa)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140010da0`
- `0x140010f10`
- `0x140017fc0`

## callees

- `0x14000c8b0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x14000c8ca`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x14000c8ca`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14000c8d8`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x14000c8d8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000c926`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000c926`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000c8ed`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000c8ed`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000c905`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x14000c905`

## pseudocode

```c
__int64 __fastcall GetBufferSize(SAFEARRAY *psa)
{
  unsigned int v1; // edi
  VARTYPE pvt; // [rsp+38h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+40h] [rbp+18h] BYREF
  LONG plUbound; // [rsp+48h] [rbp+20h] BYREF

  v1 = 0;
  plLbound = 0;
  pvt = 0;
  if ( SafeArrayGetDim(psa) == 1
    && SafeArrayGetElemsize(psa) == 1
    && SafeArrayGetLBound(psa, 1u, &plLbound) >= 0
    && !plLbound
    && SafeArrayGetVartype(psa, &pvt) >= 0
    && pvt == 17 )
  {
    plUbound = 0;
    if ( SafeArrayGetUBound(psa, 1u, &plUbound) >= 0 && plUbound > 0 )
      return (unsigned int)(plUbound + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x14000c8b0  mov     [rsp+arg_0], rbx
0x14000c8b5  push    rdi
0x14000c8b6  sub     rsp, 20h
0x14000c8ba  xor     eax, eax
0x14000c8bc  xor     edi, edi
0x14000c8be  mov     [rsp+28h+plLbound], edi
0x14000c8c2  mov     rbx, rcx
0x14000c8c5  mov     [rsp+28h+pvt], ax
0x14000c8ca  call    cs:__imp_SafeArrayGetDim
0x14000c8d0  cmp     eax, 1
0x14000c8d3  jnz     short loc_14000C93B
0x14000c8d5  mov     rcx, rbx; psa
0x14000c8d8  call    cs:__imp_SafeArrayGetElemsize
0x14000c8de  cmp     eax, 1
0x14000c8e1  jnz     short loc_14000C93B
0x14000c8e3  lea     r8, [rsp+28h+plLbound]; plLbound
0x14000c8e8  mov     edx, eax; nDim
0x14000c8ea  mov     rcx, rbx; psa
0x14000c8ed  call    cs:__imp_SafeArrayGetLBound
0x14000c8f3  test    eax, eax
0x14000c8f5  js      short loc_14000C93B
0x14000c8f7  cmp     [rsp+28h+plLbound], edi
0x14000c8fb  jnz     short loc_14000C93B
0x14000c8fd  lea     rdx, [rsp+28h+pvt]; pvt
0x14000c902  mov     rcx, rbx; psa
0x14000c905  call    cs:__imp_SafeArrayGetVartype
0x14000c90b  test    eax, eax
0x14000c90d  js      short loc_14000C93B
0x14000c90f  cmp     [rsp+28h+pvt], 11h
0x14000c915  jnz     short loc_14000C93B
0x14000c917  lea     r8, [rsp+28h+plUbound]; plUbound
0x14000c91c  mov     [rsp+28h+plUbound], edi
0x14000c920  lea     edx, [rdi+1]; nDim
0x14000c923  mov     rcx, rbx; psa
0x14000c926  call    cs:__imp_SafeArrayGetUBound
0x14000c92c  test    eax, eax
0x14000c92e  js      short loc_14000C93B
0x14000c930  mov     eax, [rsp+28h+plUbound]
0x14000c934  test    eax, eax
0x14000c936  jle     short loc_14000C93B
0x14000c938  lea     edi, [rax+1]
0x14000c93b  mov     rbx, [rsp+28h+arg_0]
0x14000c940  mov     eax, edi
0x14000c942  add     rsp, 20h
0x14000c946  pop     rdi
0x14000c947  retn
```
