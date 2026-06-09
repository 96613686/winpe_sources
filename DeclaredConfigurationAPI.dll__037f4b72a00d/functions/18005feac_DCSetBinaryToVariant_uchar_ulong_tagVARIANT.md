# DCSetBinaryToVariant(uchar *,ulong,tagVARIANT *)

- ea: `0x18005feac`
- end: `0x18005ff80`
- name: `?DCSetBinaryToVariant@@YAJPEAEKPEAUtagVARIANT@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, size_t Size, struct tagVARIANT *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18005dacc`
- `0x180087340`
- `0x1800882a0`
- `0x180091eec`
- `0x1800933a0`
- `0x1800ae150`
- `0x1800b7b20`
- `0x1800c4fe4`
- `0x1800e290c`

## callees

- `0x18000c8dc`
- `0x18005feac`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005fef5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005fef5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005ff65`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005ff65`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005ff12`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005ff12`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ff31`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ff5c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ff31`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ff5c`

## pseudocode

```c
__int64 __fastcall DCSetBinaryToVariant(unsigned __int8 *Src, size_t Size, struct tagVARIANT *a3)
{
  size_t v3; // rbp
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // rbx
  HRESULT v9; // edi
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp+20h] BYREF

  v3 = (unsigned int)Size;
  rgsabound.lLbound = 0;
  ppvData = 0;
  if ( !a3 )
    return 2147942487LL;
  rgsabound.lLbound = 0;
  rgsabound.cElements = Size;
  v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v8 = v7;
  if ( v7 )
  {
    v9 = SafeArrayAccessData(v7, &ppvData);
    if ( v9 < 0 || (memcpy_0(ppvData, Src, v3), v9 = SafeArrayUnaccessData(v8), v9 < 0) )
    {
      if ( ppvData )
        SafeArrayUnaccessData(v8);
      SafeArrayDestroy(v8);
    }
    else
    {
      ppvData = 0;
      a3->llVal = (LONGLONG)v8;
      a3->vt = 8209;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005feac  mov     [rsp+arg_0], rbx
0x18005feb1  mov     [rsp+arg_8], rbp
0x18005feb6  push    rsi
0x18005feb7  push    rdi
0x18005feb8  push    r14
0x18005feba  sub     rsp, 20h
0x18005febe  xor     eax, eax
0x18005fec0  mov     ebp, edx
0x18005fec2  mov     [rsp+38h+rgsabound.lLbound], eax
0x18005fec6  mov     rsi, r8
0x18005fec9  mov     [rsp+38h+ppvData], rax
0x18005fece  mov     r14, rcx
0x18005fed1  test    r8, r8
0x18005fed4  jnz     short loc_18005FEE0
0x18005fed6  mov     eax, 80070057h
0x18005fedb  jmp     loc_18005FF6D
0x18005fee0  mov     ecx, 11h; vt
0x18005fee5  mov     [rsp+38h+rgsabound.lLbound], eax
0x18005fee9  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x18005feee  mov     [rsp+38h+rgsabound.cElements], ebp
0x18005fef2  lea     edx, [rcx-10h]; cDims
0x18005fef5  call    cs:__imp_SafeArrayCreate
0x18005fefb  mov     rbx, rax
0x18005fefe  test    rax, rax
0x18005ff01  jnz     short loc_18005FF0A
0x18005ff03  mov     edi, 8007000Eh
0x18005ff08  jmp     short loc_18005FF6B
0x18005ff0a  lea     rdx, [rsp+38h+ppvData]; ppvData
0x18005ff0f  mov     rcx, rbx; psa
0x18005ff12  call    cs:__imp_SafeArrayAccessData
0x18005ff18  mov     edi, eax
0x18005ff1a  test    eax, eax
0x18005ff1c  js      short loc_18005FF51
0x18005ff1e  mov     rcx, [rsp+38h+ppvData]; void *
0x18005ff23  mov     r8, rbp; Size
0x18005ff26  mov     rdx, r14; Src
0x18005ff29  call    memcpy_0
0x18005ff2e  mov     rcx, rbx; psa
0x18005ff31  call    cs:__imp_SafeArrayUnaccessData
0x18005ff37  mov     edi, eax
0x18005ff39  test    eax, eax
0x18005ff3b  js      short loc_18005FF51
0x18005ff3d  mov     [rsp+38h+ppvData], 0
0x18005ff46  mov     [rsi+8], rbx
0x18005ff4a  mov     word ptr [rsi], 2011h
0x18005ff4f  jmp     short loc_18005FF6B
0x18005ff51  cmp     [rsp+38h+ppvData], 0
0x18005ff57  jz      short loc_18005FF62
0x18005ff59  mov     rcx, rbx; psa
0x18005ff5c  call    cs:__imp_SafeArrayUnaccessData
0x18005ff62  mov     rcx, rbx; psa
0x18005ff65  call    cs:__imp_SafeArrayDestroy
0x18005ff6b  mov     eax, edi
0x18005ff6d  mov     rbx, [rsp+38h+arg_0]
0x18005ff72  mov     rbp, [rsp+38h+arg_8]
0x18005ff77  add     rsp, 20h
0x18005ff7b  pop     r14
0x18005ff7d  pop     rdi
0x18005ff7e  pop     rsi
0x18005ff7f  retn
```
