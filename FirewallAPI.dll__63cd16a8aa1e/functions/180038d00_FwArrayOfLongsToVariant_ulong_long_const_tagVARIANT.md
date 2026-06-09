# FwArrayOfLongsToVariant(ulong,long const *,tagVARIANT *)

- ea: `0x180038d00`
- end: `0x180038de1`
- name: `?FwArrayOfLongsToVariant@@YAJKPEBJPEAUtagVARIANT@@@Z`
- size: `225`
- prototype: `int(unsigned int, const int *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038de8`

## callees

- `0x1800277b0`
- `0x180038d00`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180038d32`
- `OLEAUT32!__imp_VariantInit` at `0x180038d32`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180038d59`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180038d59`
- `fwbase!FwReportReturnError` at `0x180038d75`
- `fwbase!FwReportReturnError` at `0x180038d84`
- `fwbase!FwReportReturnError` at `0x180038d75`
- `fwbase!FwReportReturnError` at `0x180038d84`

## pseudocode

```c
__int64 __fastcall FwArrayOfLongsToVariant(ULONG a1, const int *a2, struct tagVARIANT *a3)
{
  SAFEARRAY *v6; // rax
  LONGLONG v7; // rdx
  _WORD *pvData; // r10
  ULONG v10; // r9d
  __int64 v11; // r8
  __int64 v12; // rcx
  int v13; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-18h] BYREF

  rgsabound = 0;
  VariantInit(a3);
  if ( a1 )
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = a1;
    v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v7 = (LONGLONG)v6;
    if ( !v6 )
    {
      FwReportReturnError("FwArrayOfLongsToVariant", 2147942414LL);
      return FwReportReturnError("FwArrayOfLongsToVariant", 2147942414LL);
    }
    pvData = v6->pvData;
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = 3 * v11;
      ++v10;
      pvData[4 * v12] = 3;
      v13 = a2[v11++];
      *(_DWORD *)&pvData[4 * v12 + 4] = v13;
    }
    while ( v10 < a1 );
    a3->vt = 8204;
    a3->llVal = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180038d00  mov     [rsp+arg_0], rbx
0x180038d05  mov     [rsp+arg_8], rsi
0x180038d0a  push    rdi
0x180038d0b  sub     rsp, 30h
0x180038d0f  mov     rax, cs:__security_cookie
0x180038d16  xor     rax, rsp
0x180038d19  mov     [rsp+38h+var_10], rax
0x180038d1e  mov     edi, ecx
0x180038d20  mov     qword ptr [rsp+38h+rgsabound.cElements], 0
0x180038d29  mov     rcx, r8; pvarg
0x180038d2c  mov     rbx, r8
0x180038d2f  mov     rsi, rdx
0x180038d32  call    cs:__imp_VariantInit
0x180038d38  test    edi, edi
0x180038d3a  jz      loc_180038DC2
0x180038d40  mov     ecx, 0Ch; vt
0x180038d45  mov     [rsp+38h+rgsabound.lLbound], 0
0x180038d4d  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x180038d52  mov     [rsp+38h+rgsabound.cElements], edi
0x180038d56  lea     edx, [rcx-0Bh]; cDims
0x180038d59  call    cs:__imp_SafeArrayCreate
0x180038d5f  mov     rdx, rax
0x180038d62  test    rax, rax
0x180038d65  jnz     short loc_180038D8C
0x180038d67  mov     ebx, 8007000Eh
0x180038d6c  lea     rcx, aFwarrayoflongs; "FwArrayOfLongsToVariant"
0x180038d73  mov     edx, ebx
0x180038d75  call    cs:__imp_FwReportReturnError
0x180038d7b  mov     edx, ebx
0x180038d7d  lea     rcx, aFwarrayoflongs; "FwArrayOfLongsToVariant"
0x180038d84  call    cs:__imp_FwReportReturnError
0x180038d8a  jmp     short loc_180038DC4
0x180038d8c  mov     r10, [rax+10h]
0x180038d90  xor     r9d, r9d
0x180038d93  test    edi, edi
0x180038d95  jz      short loc_180038DB9
0x180038d97  xor     r8d, r8d
0x180038d9a  lea     rcx, [r8+r8*2]
0x180038d9e  inc     r9d
0x180038da1  mov     word ptr [r10+rcx*8], 3
0x180038da8  mov     eax, [rsi+r8*4]
0x180038dac  inc     r8
0x180038daf  mov     [r10+rcx*8+8], eax
0x180038db4  cmp     r9d, edi
0x180038db7  jb      short loc_180038D9A
0x180038db9  mov     word ptr [rbx], 200Ch
0x180038dbe  mov     [rbx+8], rdx
0x180038dc2  xor     eax, eax
0x180038dc4  mov     rcx, [rsp+38h+var_10]
0x180038dc9  xor     rcx, rsp; StackCookie
0x180038dcc  call    __security_check_cookie
0x180038dd1  mov     rbx, [rsp+38h+arg_0]
0x180038dd6  mov     rsi, [rsp+38h+arg_8]
0x180038ddb  add     rsp, 30h
0x180038ddf  pop     rdi
0x180038de0  retn
```
