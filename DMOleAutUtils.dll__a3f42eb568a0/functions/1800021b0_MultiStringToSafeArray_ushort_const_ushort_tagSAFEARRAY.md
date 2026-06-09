# MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)

- ea: `0x1800021b0`
- end: `0x18000237a`
- name: `?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(OLECHAR *strIn, __int16, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800021b0`
- `0x180003574`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800022f1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800022f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000233e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000233e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002213`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002277`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002213`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002277`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000235b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000235b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000228c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000228c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002326`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002352`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002326`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180002352`

## pseudocode

```c
__int64 __fastcall MultiStringToSafeArray(OLECHAR *strIn, __int16 a2, struct tagSAFEARRAY **a3)
{
  OLECHAR *v5; // rdi
  SAFEARRAY *v6; // rsi
  HRESULT v7; // ebx
  ULONG v8; // edx
  OLECHAR v9; // cx
  OLECHAR *v10; // rax
  OLECHAR v11; // cx
  SAFEARRAY *v12; // rax
  ULONG cElements; // edx
  const OLECHAR *v14; // rcx
  ULONG i; // ebx
  OLECHAR v16; // ax
  BSTR v17; // rax
  __int64 v18; // rdx
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+30h] BYREF
  void *ppvData; // [rsp+68h] [rbp+48h] BYREF

  ppvData = 0;
  rgsabound = 0;
  v5 = strIn;
  v6 = 0;
  if ( !strIn || !a3 )
  {
    v7 = -2147024809;
    goto LABEL_38;
  }
  v8 = 0;
  rgsabound.cElements = 0;
  if ( !a2 && !*strIn )
  {
    v6 = SafeArrayCreate(8u, 1u, &rgsabound);
    if ( !v6 )
    {
LABEL_7:
      v7 = -2147024882;
      goto LABEL_38;
    }
    v7 = 0;
    goto LABEL_37;
  }
  v9 = *strIn;
  v10 = v5;
  do
  {
    ++v8;
    if ( v9 != a2 )
    {
      v11 = *v10;
      do
      {
        if ( !v11 )
          break;
        v11 = *++v10;
      }
      while ( *v10 != a2 );
    }
    v9 = *++v10;
  }
  while ( *v10 && v9 != a2 );
  rgsabound.cElements = v8;
  v12 = SafeArrayCreate(8u, 1u, &rgsabound);
  v6 = v12;
  if ( !v12 )
    goto LABEL_7;
  v7 = SafeArrayAccessData(v12, &ppvData);
  if ( v7 >= 0 )
  {
    if ( !ppvData )
      ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    cElements = rgsabound.cElements;
    v14 = v5;
    for ( i = 0; i < rgsabound.cElements; cElements = rgsabound.cElements )
    {
      v16 = *v5;
      if ( !*v5 )
        break;
      while ( v16 != a2 && v16 )
        v16 = *++v5;
      if ( a2 && !i && v5 == v14 && cElements == 1 )
        ++v5;
      v17 = SysAllocStringLen(v14, v5 - v14);
      if ( !v17 )
        goto LABEL_7;
      ++v5;
      v18 = i++;
      *((_QWORD *)ppvData + v18) = v17;
      v14 = v5;
    }
    if ( i != cElements )
      MicrosoftTelemetryAssertTriggeredNoArgs(v14);
    v7 = SafeArrayUnaccessData(v6);
    if ( v7 >= 0 )
    {
      ppvData = 0;
LABEL_37:
      *a3 = v6;
      v6 = 0;
    }
  }
LABEL_38:
  SysFreeString(0);
  if ( v6 )
  {
    if ( ppvData )
      SafeArrayUnaccessData(v6);
    SafeArrayDestroy(v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp-28h+arg_8], rbx
0x1800021b5  mov     [rsp-28h+arg_10], rsi
0x1800021ba  push    rbp
0x1800021bb  push    rdi
0x1800021bc  push    r12
0x1800021be  push    r14
0x1800021c0  push    r15
0x1800021c2  mov     rbp, rsp
0x1800021c5  sub     rsp, 20h
0x1800021c9  xor     r12d, r12d
0x1800021cc  mov     r15, r8
0x1800021cf  mov     [rbp+ppvData], r12
0x1800021d3  movzx   r14d, dx
0x1800021d7  mov     qword ptr [rbp+rgsabound.cElements], r12
0x1800021db  mov     rdi, rcx
0x1800021de  mov     esi, r12d
0x1800021e1  test    rcx, rcx
0x1800021e4  jnz     short loc_1800021F0
0x1800021e6  mov     ebx, 80070057h
0x1800021eb  jmp     loc_18000233C
0x1800021f0  test    r15, r15
0x1800021f3  jz      short loc_1800021E6
0x1800021f5  mov     edx, r12d
0x1800021f8  mov     [rbp+rgsabound.cElements], edx
0x1800021fb  cmp     r12w, r14w
0x1800021ff  jnz     short loc_180002233
0x180002201  cmp     r12w, [rcx]
0x180002205  jnz     short loc_180002233
0x180002207  mov     ecx, 8; vt
0x18000220c  lea     r8, [rbp+rgsabound]; rgsabound
0x180002210  lea     edx, [rcx-7]; cDims
0x180002213  call    cs:__imp_SafeArrayCreate
0x180002219  mov     rsi, rax
0x18000221c  test    rax, rax
0x18000221f  jnz     short loc_18000222B
0x180002221  mov     ebx, 8007000Eh
0x180002226  jmp     loc_18000233C
0x18000222b  mov     ebx, r12d
0x18000222e  jmp     loc_180002336
0x180002233  movzx   ecx, word ptr [rcx]
0x180002236  mov     rax, rdi
0x180002239  inc     edx
0x18000223b  cmp     cx, r14w
0x18000223f  jz      short loc_180002256
0x180002241  movzx   ecx, word ptr [rax]
0x180002244  test    cx, cx
0x180002247  jz      short loc_180002256
0x180002249  add     rax, 2
0x18000224d  movzx   ecx, word ptr [rax]
0x180002250  cmp     cx, r14w
0x180002254  jnz     short loc_180002244
0x180002256  add     rax, 2
0x18000225a  movzx   ecx, word ptr [rax]
0x18000225d  test    cx, cx
0x180002260  jz      short loc_180002268
0x180002262  cmp     cx, r14w
0x180002266  jnz     short loc_180002239
0x180002268  mov     ecx, 8; vt
0x18000226d  mov     [rbp+rgsabound.cElements], edx
0x180002270  lea     r8, [rbp+rgsabound]; rgsabound
0x180002274  lea     edx, [rcx-7]; cDims
0x180002277  call    cs:__imp_SafeArrayCreate
0x18000227d  mov     rsi, rax
0x180002280  test    rax, rax
0x180002283  jz      short loc_180002221
0x180002285  lea     rdx, [rbp+ppvData]; ppvData
0x180002289  mov     rcx, rax; psa
0x18000228c  call    cs:__imp_SafeArrayAccessData
0x180002292  mov     ebx, eax
0x180002294  test    eax, eax
0x180002296  js      loc_18000233C
0x18000229c  cmp     [rbp+ppvData], r12
0x1800022a0  jnz     short loc_1800022A7
0x1800022a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800022a7  mov     edx, [rbp+rgsabound.cElements]
0x1800022aa  mov     rcx, rdi; strIn
0x1800022ad  mov     ebx, r12d
0x1800022b0  test    edx, edx
0x1800022b2  jz      short loc_18000231A
0x1800022b4  movzx   eax, word ptr [rdi]
0x1800022b7  test    ax, ax
0x1800022ba  jz      short loc_18000231A
0x1800022bc  jmp     short loc_1800022CA
0x1800022be  test    ax, ax
0x1800022c1  jz      short loc_1800022D0
0x1800022c3  add     rdi, 2
0x1800022c7  movzx   eax, word ptr [rdi]
0x1800022ca  cmp     ax, r14w
0x1800022ce  jnz     short loc_1800022BE
0x1800022d0  cmp     r12w, r14w
0x1800022d4  jz      short loc_1800022E8
0x1800022d6  test    ebx, ebx
0x1800022d8  jnz     short loc_1800022E8
0x1800022da  cmp     rdi, rcx
0x1800022dd  jnz     short loc_1800022E8
0x1800022df  cmp     edx, 1
0x1800022e2  jnz     short loc_1800022E8
0x1800022e4  add     rdi, 2
0x1800022e8  mov     rdx, rdi
0x1800022eb  sub     rdx, rcx
0x1800022ee  sar     rdx, 1; ui
0x1800022f1  call    cs:__imp_SysAllocStringLen
0x1800022f7  test    rax, rax
0x1800022fa  jz      loc_180002221
0x180002300  mov     rcx, [rbp+ppvData]
0x180002304  add     rdi, 2
0x180002308  mov     edx, ebx
0x18000230a  inc     ebx
0x18000230c  mov     [rcx+rdx*8], rax
0x180002310  mov     rcx, rdi
0x180002313  mov     edx, [rbp+rgsabound.cElements]
0x180002316  cmp     ebx, edx
0x180002318  jb      short loc_1800022B4
0x18000231a  cmp     ebx, edx
0x18000231c  jz      short loc_180002323
0x18000231e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002323  mov     rcx, rsi; psa
0x180002326  call    cs:__imp_SafeArrayUnaccessData
0x18000232c  mov     ebx, eax
0x18000232e  test    eax, eax
0x180002330  js      short loc_18000233C
0x180002332  mov     [rbp+ppvData], r12
0x180002336  mov     [r15], rsi
0x180002339  mov     rsi, r12
0x18000233c  xor     ecx, ecx; bstrString
0x18000233e  call    cs:__imp_SysFreeString
0x180002344  test    rsi, rsi
0x180002347  jz      short loc_180002361
0x180002349  cmp     [rbp+ppvData], r12
0x18000234d  jz      short loc_180002358
0x18000234f  mov     rcx, rsi; psa
0x180002352  call    cs:__imp_SafeArrayUnaccessData
0x180002358  mov     rcx, rsi; psa
0x18000235b  call    cs:__imp_SafeArrayDestroy
0x180002361  mov     rsi, [rsp+20h+arg_10]
0x180002366  mov     eax, ebx
0x180002368  mov     rbx, [rsp+20h+arg_8]
0x18000236d  add     rsp, 20h
0x180002371  pop     r15
0x180002373  pop     r14
0x180002375  pop     r12
0x180002377  pop     rdi
0x180002378  pop     rbp
0x180002379  retn
```
