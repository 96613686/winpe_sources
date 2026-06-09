# CScopeData::GetData(ulong,tagVARIANT *,wchar_t const *)

- ea: `0x1801b62b8`
- end: `0x1801b6502`
- name: `?GetData@CScopeData@@QEAAJKPEAUtagVARIANT@@PEB_W@Z`
- size: `586`
- prototype: `int(CScopeData *__hidden this, unsigned int, struct tagVARIANT *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801b6510`

## callees

- `0x1801b62b8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801b6355`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b63d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b6496`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b6355`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b63d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1801b6496`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b637c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b63fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b64b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b637c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b63fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b64b9`
- `OLEAUT32!__imp_VariantClear` at `0x1801b62ea`
- `OLEAUT32!__imp_VariantClear` at `0x1801b62ea`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b6326`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b639b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b641c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b646f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b6326`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b639b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b641c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b646f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b64d0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b64d0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b6371`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b63f2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b644a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b64ae`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b6371`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b63f2`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b644a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1801b64ae`

## pseudocode

```c
__int64 __fastcall CScopeData::GetData(CScopeData *this, int a2, struct tagVARIANT *a3, const wchar_t *a4)
{
  ULONG v4; // eax
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  SAFEARRAY *v13; // rdi
  __int64 j; // r14
  __int64 v15; // rax
  BSTR v16; // rax
  OLECHAR *v17; // r12
  HRESULT v18; // ebx
  __int64 k; // r14
  __int64 v20; // rax
  const OLECHAR *v21; // rcx
  BSTR v22; // rax
  OLECHAR *v23; // r12
  __int64 m; // r14
  __int64 v25; // rax
  __int64 i; // r14
  __int64 v27; // rax
  BSTR v28; // rax
  OLECHAR *v29; // r12
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp+40h] BYREF
  LONG rgIndices; // [rsp+68h] [rbp+48h] BYREF

  v4 = *((_DWORD *)this + 1);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v4;
  VariantClear(a3);
  v9 = a2 - 1;
  if ( !v9 )
  {
    v13 = SafeArrayCreate(8u, 1u, &rgsabound);
    if ( v13 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 1); i = (unsigned int)(i + 1) )
      {
        v27 = *((_QWORD *)this + 4);
        rgIndices = i;
        v28 = SysAllocString((const OLECHAR *)(*((_QWORD *)this + 7) + *(unsigned int *)(v27 + 4 * i)));
        v29 = v28;
        if ( !v28 )
        {
LABEL_33:
          v18 = -2147024882;
LABEL_34:
          SafeArrayDestroy(v13);
          return (unsigned int)v18;
        }
        v18 = SafeArrayPutElement(v13, &rgIndices, v28);
        SysFreeString(v29);
        if ( v18 < 0 )
          goto LABEL_34;
      }
      goto LABEL_35;
    }
    return 2147942414LL;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        return 2147942487LL;
      v13 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( v13 )
      {
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 1); j = (unsigned int)(j + 1) )
        {
          v15 = *((_QWORD *)this + 5);
          rgIndices = j;
          v16 = SysAllocString((const OLECHAR *)(*((_QWORD *)this + 7) + *(unsigned int *)(v15 + 4 * j)));
          v17 = v16;
          if ( !v16 )
            goto LABEL_33;
          v18 = SafeArrayPutElement(v13, &rgIndices, v16);
          SysFreeString(v17);
          if ( v18 < 0 )
            goto LABEL_34;
        }
LABEL_35:
        a3->vt = 8200;
        goto LABEL_36;
      }
    }
    else
    {
      v13 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( v13 )
      {
        for ( k = 0; (unsigned int)k < *((_DWORD *)this + 1); k = (unsigned int)(k + 1) )
        {
          v20 = *((_QWORD *)this + 3);
          rgIndices = k;
          if ( *(_DWORD *)(v20 + 4 * k) == -1 )
            v21 = a4;
          else
            v21 = (const OLECHAR *)(*((_QWORD *)this + 7) + *(unsigned int *)(v20 + 4 * k));
          v22 = SysAllocString(v21);
          v23 = v22;
          if ( !v22 )
            goto LABEL_33;
          v18 = SafeArrayPutElement(v13, &rgIndices, v22);
          SysFreeString(v23);
          if ( v18 < 0 )
            goto LABEL_34;
        }
        goto LABEL_35;
      }
    }
    return 2147942414LL;
  }
  v13 = SafeArrayCreate(3u, 1u, &rgsabound);
  if ( !v13 )
    return 2147942414LL;
  for ( m = 0; (unsigned int)m < *((_DWORD *)this + 1); m = (unsigned int)(m + 1) )
  {
    v25 = *((_QWORD *)this + 2);
    rgIndices = m;
    v18 = SafeArrayPutElement(v13, &rgIndices, (void *)(v25 + 4 * m));
    if ( v18 < 0 )
      goto LABEL_34;
  }
  a3->vt = 8195;
LABEL_36:
  a3->llVal = (LONGLONG)v13;
  return 0;
}

```

## disassembly

```asm
0x1801b62b8  mov     [rsp-38h+arg_10], rbx
0x1801b62bd  push    rbp
0x1801b62be  push    rsi
0x1801b62bf  push    rdi
0x1801b62c0  push    r12
0x1801b62c2  push    r13
0x1801b62c4  push    r14
0x1801b62c6  push    r15
0x1801b62c8  mov     rbp, rsp
0x1801b62cb  sub     rsp, 20h
0x1801b62cf  mov     eax, [rcx+4]
0x1801b62d2  mov     rsi, rcx
0x1801b62d5  mov     rcx, r8; pvarg
0x1801b62d8  mov     [rbp+rgsabound.lLbound], 0
0x1801b62df  mov     r13, r9
0x1801b62e2  mov     [rbp+rgsabound.cElements], eax
0x1801b62e5  mov     r15, r8
0x1801b62e8  mov     ebx, edx
0x1801b62ea  call    cs:__imp_VariantClear
0x1801b62f0  sub     ebx, 1
0x1801b62f3  jz      loc_1801B6463
0x1801b62f9  sub     ebx, 1
0x1801b62fc  jz      loc_1801B6410
0x1801b6302  sub     ebx, 1
0x1801b6305  jz      loc_1801B638F
0x1801b630b  cmp     ebx, 1
0x1801b630e  jz      short loc_1801B631A
0x1801b6310  mov     eax, 80070057h
0x1801b6315  jmp     loc_1801B64ED
0x1801b631a  mov     ecx, 8; vt
0x1801b631f  lea     r8, [rbp+rgsabound]; rgsabound
0x1801b6323  lea     edx, [rcx-7]; cDims
0x1801b6326  call    cs:__imp_SafeArrayCreate
0x1801b632c  mov     rdi, rax
0x1801b632f  test    rax, rax
0x1801b6332  jz      loc_1801B64E8
0x1801b6338  xor     r14d, r14d
0x1801b633b  cmp     r14d, [rsi+4]
0x1801b633f  jnb     loc_1801B64D8
0x1801b6345  mov     rax, [rsi+28h]
0x1801b6349  mov     [rbp+rgIndices], r14d
0x1801b634d  mov     ecx, [rax+r14*4]
0x1801b6351  add     rcx, [rsi+38h]; psz
0x1801b6355  call    cs:__imp_SysAllocString
0x1801b635b  mov     r12, rax
0x1801b635e  test    rax, rax
0x1801b6361  jz      loc_1801B64C8
0x1801b6367  mov     r8, rax; pv
0x1801b636a  lea     rdx, [rbp+rgIndices]; rgIndices
0x1801b636e  mov     rcx, rdi; psa
0x1801b6371  call    cs:__imp_SafeArrayPutElement
0x1801b6377  mov     rcx, r12; bstrString
0x1801b637a  mov     ebx, eax
0x1801b637c  call    cs:__imp_SysFreeString
0x1801b6382  test    ebx, ebx
0x1801b6384  js      loc_1801B64CD
0x1801b638a  inc     r14d
0x1801b638d  jmp     short loc_1801B633B
0x1801b638f  mov     ecx, 8; vt
0x1801b6394  lea     r8, [rbp+rgsabound]; rgsabound
0x1801b6398  lea     edx, [rcx-7]; cDims
0x1801b639b  call    cs:__imp_SafeArrayCreate
0x1801b63a1  mov     rdi, rax
0x1801b63a4  test    rax, rax
0x1801b63a7  jz      loc_1801B64E8
0x1801b63ad  xor     r14d, r14d
0x1801b63b0  cmp     r14d, [rsi+4]
0x1801b63b4  jnb     loc_1801B64D8
0x1801b63ba  mov     rax, [rsi+18h]
0x1801b63be  mov     [rbp+rgIndices], r14d
0x1801b63c2  cmp     dword ptr [rax+r14*4], 0FFFFFFFFh
0x1801b63c7  jz      short loc_1801B63D3
0x1801b63c9  mov     ecx, [rax+r14*4]
0x1801b63cd  add     rcx, [rsi+38h]
0x1801b63d1  jmp     short loc_1801B63D6
0x1801b63d3  mov     rcx, r13; psz
0x1801b63d6  call    cs:__imp_SysAllocString
0x1801b63dc  mov     r12, rax
0x1801b63df  test    rax, rax
0x1801b63e2  jz      loc_1801B64C8
0x1801b63e8  mov     r8, rax; pv
0x1801b63eb  lea     rdx, [rbp+rgIndices]; rgIndices
0x1801b63ef  mov     rcx, rdi; psa
0x1801b63f2  call    cs:__imp_SafeArrayPutElement
0x1801b63f8  mov     rcx, r12; bstrString
0x1801b63fb  mov     ebx, eax
0x1801b63fd  call    cs:__imp_SysFreeString
0x1801b6403  test    ebx, ebx
0x1801b6405  js      loc_1801B64CD
0x1801b640b  inc     r14d
0x1801b640e  jmp     short loc_1801B63B0
0x1801b6410  mov     ecx, 3; vt
0x1801b6415  lea     r8, [rbp+rgsabound]; rgsabound
0x1801b6419  lea     edx, [rcx-2]; cDims
0x1801b641c  call    cs:__imp_SafeArrayCreate
0x1801b6422  mov     rdi, rax
0x1801b6425  test    rax, rax
0x1801b6428  jz      loc_1801B64E8
0x1801b642e  xor     r14d, r14d
0x1801b6431  cmp     r14d, [rsi+4]
0x1801b6435  jnb     short loc_1801B645B
0x1801b6437  mov     rax, [rsi+10h]
0x1801b643b  lea     rdx, [rbp+rgIndices]; rgIndices
0x1801b643f  mov     rcx, rdi; psa
0x1801b6442  mov     [rbp+rgIndices], r14d
0x1801b6446  lea     r8, [rax+r14*4]; pv
0x1801b644a  call    cs:__imp_SafeArrayPutElement
0x1801b6450  mov     ebx, eax
0x1801b6452  test    eax, eax
0x1801b6454  js      short loc_1801B64CD
0x1801b6456  inc     r14d
0x1801b6459  jmp     short loc_1801B6431
0x1801b645b  mov     word ptr [r15], 2003h
0x1801b6461  jmp     short loc_1801B64DE
0x1801b6463  mov     ecx, 8; vt
0x1801b6468  lea     r8, [rbp+rgsabound]; rgsabound
0x1801b646c  lea     edx, [rcx-7]; cDims
0x1801b646f  call    cs:__imp_SafeArrayCreate
0x1801b6475  mov     rdi, rax
0x1801b6478  test    rax, rax
0x1801b647b  jz      short loc_1801B64E8
0x1801b647d  xor     r14d, r14d
0x1801b6480  cmp     r14d, [rsi+4]
0x1801b6484  jnb     short loc_1801B64D8
0x1801b6486  mov     rax, [rsi+20h]
0x1801b648a  mov     [rbp+rgIndices], r14d
0x1801b648e  mov     ecx, [rax+r14*4]
0x1801b6492  add     rcx, [rsi+38h]; psz
0x1801b6496  call    cs:__imp_SysAllocString
0x1801b649c  mov     r12, rax
0x1801b649f  test    rax, rax
0x1801b64a2  jz      short loc_1801B64C8
0x1801b64a4  mov     r8, rax; pv
0x1801b64a7  lea     rdx, [rbp+rgIndices]; rgIndices
0x1801b64ab  mov     rcx, rdi; psa
0x1801b64ae  call    cs:__imp_SafeArrayPutElement
0x1801b64b4  mov     rcx, r12; bstrString
0x1801b64b7  mov     ebx, eax
0x1801b64b9  call    cs:__imp_SysFreeString
0x1801b64bf  test    ebx, ebx
0x1801b64c1  js      short loc_1801B64CD
0x1801b64c3  inc     r14d
0x1801b64c6  jmp     short loc_1801B6480
0x1801b64c8  mov     ebx, 8007000Eh
0x1801b64cd  mov     rcx, rdi; psa
0x1801b64d0  call    cs:__imp_SafeArrayDestroy
0x1801b64d6  jmp     short loc_1801B64E4
0x1801b64d8  mov     word ptr [r15], 2008h
0x1801b64de  mov     [r15+8], rdi
0x1801b64e2  xor     ebx, ebx
0x1801b64e4  mov     eax, ebx
0x1801b64e6  jmp     short loc_1801B64ED
0x1801b64e8  mov     eax, 8007000Eh
0x1801b64ed  mov     rbx, [rsp+20h+arg_10]
0x1801b64f2  add     rsp, 20h
0x1801b64f6  pop     r15
0x1801b64f8  pop     r14
0x1801b64fa  pop     r13
0x1801b64fc  pop     r12
0x1801b64fe  pop     rdi
0x1801b64ff  pop     rsi
0x1801b6500  pop     rbp
0x1801b6501  retn
```
