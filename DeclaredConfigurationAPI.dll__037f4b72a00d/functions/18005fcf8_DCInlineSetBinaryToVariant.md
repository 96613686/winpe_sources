# DCInlineSetBinaryToVariant

- ea: `0x18005fcf8`
- end: `0x18005fdd8`
- name: `DCInlineSetBinaryToVariant`
- size: `224`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180076c10`
- `0x180078e2c`
- `0x18007f370`
- `0x180081a94`
- `0x1800ad2b4`
- `0x1800baf74`
- `0x1800c0f2c`
- `0x1800ca3c4`
- `0x1800d0ae0`
- `0x180110328`
- `0x18011440c`
- `0x1801247b4`

## callees

- `0x18000c8dc`
- `0x18005fcf8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005fd41`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18005fd41`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005fdbd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005fdbd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005fd5e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005fd5e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005fd89`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005fdb4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005fd89`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005fdb4`

## pseudocode

```c
__int64 __fastcall DCInlineSetBinaryToVariant(void *Src, size_t Size, __int64 a3)
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
    if ( v9 < 0 )
      goto LABEL_10;
    if ( !ppvData )
      return 2147549183LL;
    memcpy_0(ppvData, Src, v3);
    v9 = SafeArrayUnaccessData(v8);
    if ( v9 < 0 )
    {
LABEL_10:
      if ( ppvData )
        SafeArrayUnaccessData(v8);
      SafeArrayDestroy(v8);
    }
    else
    {
      ppvData = 0;
      *(_QWORD *)(a3 + 8) = v8;
      *(_WORD *)a3 = 8209;
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
0x18005fcf8  mov     [rsp+arg_0], rbx
0x18005fcfd  mov     [rsp+arg_8], rbp
0x18005fd02  push    rsi
0x18005fd03  push    rdi
0x18005fd04  push    r14
0x18005fd06  sub     rsp, 20h
0x18005fd0a  xor     eax, eax
0x18005fd0c  mov     ebp, edx
0x18005fd0e  mov     [rsp+38h+rgsabound.lLbound], eax
0x18005fd12  mov     rsi, r8
0x18005fd15  mov     [rsp+38h+ppvData], rax
0x18005fd1a  mov     r14, rcx
0x18005fd1d  test    r8, r8
0x18005fd20  jnz     short loc_18005FD2C
0x18005fd22  mov     eax, 80070057h
0x18005fd27  jmp     loc_18005FDC5
0x18005fd2c  mov     ecx, 11h; vt
0x18005fd31  mov     [rsp+38h+rgsabound.lLbound], eax
0x18005fd35  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x18005fd3a  mov     [rsp+38h+rgsabound.cElements], ebp
0x18005fd3e  lea     edx, [rcx-10h]; cDims
0x18005fd41  call    cs:__imp_SafeArrayCreate
0x18005fd47  mov     rbx, rax
0x18005fd4a  test    rax, rax
0x18005fd4d  jnz     short loc_18005FD56
0x18005fd4f  mov     edi, 8007000Eh
0x18005fd54  jmp     short loc_18005FDC3
0x18005fd56  lea     rdx, [rsp+38h+ppvData]; ppvData
0x18005fd5b  mov     rcx, rbx; psa
0x18005fd5e  call    cs:__imp_SafeArrayAccessData
0x18005fd64  mov     edi, eax
0x18005fd66  test    eax, eax
0x18005fd68  js      short loc_18005FDA9
0x18005fd6a  mov     rcx, [rsp+38h+ppvData]; void *
0x18005fd6f  test    rcx, rcx
0x18005fd72  jnz     short loc_18005FD7B
0x18005fd74  mov     eax, 8000FFFFh
0x18005fd79  jmp     short loc_18005FDC5
0x18005fd7b  mov     r8, rbp; Size
0x18005fd7e  mov     rdx, r14; Src
0x18005fd81  call    memcpy_0
0x18005fd86  mov     rcx, rbx; psa
0x18005fd89  call    cs:__imp_SafeArrayUnaccessData
0x18005fd8f  mov     edi, eax
0x18005fd91  test    eax, eax
0x18005fd93  js      short loc_18005FDA9
0x18005fd95  mov     [rsp+38h+ppvData], 0
0x18005fd9e  mov     [rsi+8], rbx
0x18005fda2  mov     word ptr [rsi], 2011h
0x18005fda7  jmp     short loc_18005FDC3
0x18005fda9  cmp     [rsp+38h+ppvData], 0
0x18005fdaf  jz      short loc_18005FDBA
0x18005fdb1  mov     rcx, rbx; psa
0x18005fdb4  call    cs:__imp_SafeArrayUnaccessData
0x18005fdba  mov     rcx, rbx; psa
0x18005fdbd  call    cs:__imp_SafeArrayDestroy
0x18005fdc3  mov     eax, edi
0x18005fdc5  mov     rbx, [rsp+38h+arg_0]
0x18005fdca  mov     rbp, [rsp+38h+arg_8]
0x18005fdcf  add     rsp, 20h
0x18005fdd3  pop     r14
0x18005fdd5  pop     rdi
0x18005fdd6  pop     rsi
0x18005fdd7  retn
```
