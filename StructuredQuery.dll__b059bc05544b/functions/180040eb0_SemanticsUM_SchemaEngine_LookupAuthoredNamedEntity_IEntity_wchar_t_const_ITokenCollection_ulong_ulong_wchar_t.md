# SemanticsUM::SchemaEngine::LookupAuthoredNamedEntity(IEntity *,wchar_t const *,ITokenCollection *,ulong,ulong *,wchar_t * *)

- ea: `0x180040eb0`
- end: `0x1800411bb`
- name: `?LookupAuthoredNamedEntity@SchemaEngine@SemanticsUM@@UEAAJPEAUIEntity@@PEB_WPEAUITokenCollection@@KPEAKPEAPEA_W@Z`
- size: `779`
- prototype: `__int64 __fastcall(SemanticsUM::SchemaEngine *__hidden this, struct IEntity *, const wchar_t *, struct ITokenCollection *, unsigned int, unsigned int *, wchar_t **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180015a40`
- `0x180040eb0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004104e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004116a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004104e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004116a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800410c7`

## pseudocode

```c
__int64 __fastcall SemanticsUM::SchemaEngine::LookupAuthoredNamedEntity(
        SemanticsUM::SchemaEngine *this,
        struct IEntity *a2,
        const wchar_t *a3,
        struct ITokenCollection *a4,
        unsigned int a5,
        unsigned int *a6,
        wchar_t **a7)
{
  unsigned int *v7; // r13
  struct ITokenCollection *v9; // rsi
  wchar_t **v10; // r15
  unsigned int v11; // r12d
  wchar_t *v12; // rdi
  struct IEntityVtbl *lpVtbl; // rax
  int v14; // ebx
  __int64 v15; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // r13
  unsigned int v18; // edi
  bool v19; // r15
  struct ITokenCollectionVtbl *v20; // rax
  const WCHAR *v21; // r13
  __int64 v22; // r14
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // kr00_8
  __int64 v26; // rdi
  int v27; // eax
  int v28; // eax
  __int64 v30; // r13
  __int64 v31; // rsi
  const WCHAR *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  const WCHAR *lpString2; // [rsp+20h] [rbp-60h]
  unsigned int v36; // [rsp+30h] [rbp-50h]
  unsigned int v37; // [rsp+34h] [rbp-4Ch] BYREF
  int cchCount1; // [rsp+38h] [rbp-48h] BYREF
  int v39; // [rsp+3Ch] [rbp-44h] BYREF
  LCID Locale; // [rsp+40h] [rbp-40h]
  __int64 v41; // [rsp+48h] [rbp-38h]
  __int64 v42; // [rsp+50h] [rbp-30h]
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *v44; // [rsp+60h] [rbp-20h] BYREF
  PCNZWCH lpString1; // [rsp+68h] [rbp-18h] BYREF
  __int64 v46; // [rsp+70h] [rbp-10h]
  __int64 v47; // [rsp+78h] [rbp-8h]

  v7 = a6;
  v9 = a4;
  if ( !a6 || (v10 = a7) == 0 )
    return (unsigned int)-2147467261;
  v44 = 0;
  v11 = 0;
  v12 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v14 = -2147024809;
    goto LABEL_31;
  }
  lpVtbl = a2->lpVtbl;
  lpString1 = 0;
  v14 = ((__int64 (__fastcall *)(struct IEntity *, PCNZWCH *))lpVtbl->Name)(a2, &lpString1);
  if ( v14 < 0 )
    goto LABEL_31;
  v37 = 0;
  v14 = ((__int64 (__fastcall *)(struct ITokenCollection *, unsigned int *))v9->lpVtbl->NumberOfTokens)(v9, &v37);
  if ( v14 < 0 )
    goto LABEL_30;
  v15 = *((_QWORD *)this + 1);
  v16 = *(_QWORD *)(v15 + 120);
  v17 = *(_QWORD *)(v15 + 128);
  v18 = a5;
  Locale = *(_DWORD *)(v15 + 12);
  v19 = a5 >= v37;
  v41 = v16;
  v42 = v17;
  v36 = a5;
  do
  {
    if ( v19 )
      goto LABEL_28;
    if ( v16 >= v17 )
      break;
    v20 = v9->lpVtbl;
    v39 = 0;
    cchCount1 = 0;
    pv = 0;
    v14 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, int *, int *, LPVOID *))v20->GetToken)(
            v9,
            v18,
            &v39,
            &cchCount1,
            &pv);
    if ( v14 < 0 )
      goto LABEL_44;
    v21 = (const WCHAR *)pv;
    if ( pv )
    {
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)pv + v22) );
    }
    else
    {
      LODWORD(v22) = cchCount1;
      v21 = &a3[v39];
    }
    v23 = v42;
    v24 = v41;
LABEL_15:
    v46 = v23;
    while ( 1 )
    {
      v25 = v23 - v24;
      v26 = v24 + 40 * ((v23 - v24) / 80);
      lpString2 = *(const WCHAR **)v26;
      v47 = v26;
      v27 = CompareStringW(Locale, 0x20001u, v21, v22, lpString2, -1) - 1;
      if ( !v27 )
      {
        if ( v26 != v24 )
        {
          v23 = v24 + 40 * (v25 / 80);
          goto LABEL_15;
        }
LABEL_24:
        v18 = v36;
        v16 = v41;
        v17 = v42;
LABEL_25:
        v19 = 1;
        goto LABEL_26;
      }
      v28 = v27 - 1;
      if ( !v28 )
        break;
      if ( v28 == 1 )
      {
        v23 = v46;
        v24 = v26 + 40;
        if ( v26 + 40 != v46 )
          continue;
      }
      goto LABEL_24;
    }
    if ( !v26 )
      goto LABEL_24;
    v30 = *(_QWORD *)(v26 + 32);
    v31 = *(_QWORD *)(v26 + 24);
    do
    {
      if ( v19 || v31 == v30 )
        break;
      if ( *(_DWORD *)v31 == 5 )
      {
        v32 = (const WCHAR *)(***(__int64 (__fastcall ****)(_QWORD))(v31 + 8))(*(_QWORD *)(v31 + 8));
        if ( CompareStringW(0x7Fu, 0, lpString1, -1, v32, -1) == 2 )
        {
          v11 = v36 - a5 + 1;
          v14 = _AllocString<CTCoAllocPolicy>(v34, v33, *(const size_t **)(v31 + 16), &v44);
          v19 = 1;
        }
      }
      v31 += 24;
    }
    while ( v14 >= 0 );
    v16 = *(_QWORD *)(v47 + 8);
    v17 = *(_QWORD *)(v47 + 16);
    v18 = v36 + 1;
    v41 = v16;
    v42 = v17;
    v36 = v18;
    if ( v18 >= v37 )
      goto LABEL_25;
LABEL_26:
    CoTaskMemFree(pv);
    v9 = a4;
  }
  while ( v14 >= 0 );
  if ( v14 >= 0 )
  {
LABEL_28:
    v12 = v44;
    v14 = v44 == 0;
    goto LABEL_29;
  }
LABEL_44:
  v12 = v44;
LABEL_29:
  v7 = a6;
  v10 = a7;
LABEL_30:
  CoTaskMemFree((LPVOID)lpString1);
LABEL_31:
  *v7 = v11;
  *v10 = v12;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180040eb0  mov     [rsp-38h+arg_0], rbx
0x180040eb5  mov     [rsp-38h+arg_18], r9
0x180040eba  mov     [rsp-38h+arg_10], r8
0x180040ebf  push    rbp
0x180040ec0  push    rsi
0x180040ec1  push    rdi
0x180040ec2  push    r12
0x180040ec4  push    r13
0x180040ec6  push    r14
0x180040ec8  push    r15
0x180040eca  mov     rbp, rsp
0x180040ecd  sub     rsp, 80h
0x180040ed4  mov     r13, [rbp+arg_28]
0x180040ed8  mov     r14, rcx
0x180040edb  xor     ecx, ecx
0x180040edd  mov     rsi, r9
0x180040ee0  mov     rax, r8
0x180040ee3  mov     r10, rdx
0x180040ee6  test    r13, r13
0x180040ee9  jz      loc_180041195
0x180040eef  mov     r15, [rbp+arg_30]
0x180040ef3  test    r15, r15
0x180040ef6  jz      loc_180041195
0x180040efc  mov     [rbp+var_20], rcx
0x180040f00  mov     r12d, ecx
0x180040f03  mov     edi, ecx
0x180040f05  test    rdx, rdx
0x180040f08  jz      loc_1800411B1
0x180040f0e  test    rax, rax
0x180040f11  jz      loc_1800411B1
0x180040f17  test    r9, r9
0x180040f1a  jz      loc_1800411B1
0x180040f20  mov     rax, [rdx]
0x180040f23  lea     rdx, [rbp+lpString1]
0x180040f27  mov     [rbp+lpString1], rcx
0x180040f2b  mov     rcx, r10
0x180040f2e  mov     rax, [rax+18h]
0x180040f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f37  mov     ebx, eax
0x180040f39  xor     eax, eax
0x180040f3b  test    ebx, ebx
0x180040f3d  js      loc_1800410CD
0x180040f43  mov     [rbp+var_4C], eax
0x180040f46  lea     rdx, [rbp+var_4C]
0x180040f4a  mov     rax, [rsi]
0x180040f4d  mov     rcx, rsi
0x180040f50  mov     rax, [rax+18h]
0x180040f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f59  xor     edx, edx
0x180040f5b  mov     ebx, eax
0x180040f5d  test    eax, eax
0x180040f5f  js      loc_1800410C3
0x180040f65  mov     rax, [r14+8]
0x180040f69  mov     ecx, [rax+0Ch]
0x180040f6c  mov     r14, [rax+78h]
0x180040f70  mov     r13, [rax+80h]
0x180040f77  mov     eax, [rbp+arg_20]
0x180040f7a  mov     edi, eax
0x180040f7c  cmp     eax, [rbp+var_4C]
0x180040f7f  mov     [rbp+Locale], ecx
0x180040f82  setnb   r15b
0x180040f86  mov     [rbp+var_38], r14
0x180040f8a  mov     [rbp+var_30], r13
0x180040f8e  mov     [rbp+var_50], eax
0x180040f91  test    r15b, r15b
0x180040f94  jnz     loc_1800410AF
0x180040f9a  cmp     r14, r13
0x180040f9d  jnb     loc_1800410A7
0x180040fa3  mov     rax, [rsi]
0x180040fa6  lea     rcx, [rbp+pv]
0x180040faa  mov     [rbp+var_44], edx
0x180040fad  lea     r9, [rbp+cchCount1]
0x180040fb1  mov     [rbp+cchCount1], edx
0x180040fb4  lea     r8, [rbp+var_44]
0x180040fb8  mov     [rbp+pv], rdx
0x180040fbc  mov     edx, edi
0x180040fbe  mov     rax, [rax+20h]
0x180040fc2  mov     [rsp+80h+lpString2], rcx
0x180040fc7  mov     rcx, rsi
0x180040fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fcf  mov     ebx, eax
0x180040fd1  xor     eax, eax
0x180040fd3  test    ebx, ebx
0x180040fd5  js      loc_1800411A8
0x180040fdb  mov     r13, [rbp+pv]
0x180040fdf  test    r13, r13
0x180040fe2  jnz     loc_18004119F
0x180040fe8  mov     eax, [rbp+var_44]
0x180040feb  mov     rcx, [rbp+arg_10]
0x180040fef  mov     r14d, [rbp+cchCount1]
0x180040ff3  lea     r13, [rcx+rax*2]
0x180040ff7  mov     rax, [rbp+var_30]
0x180040ffb  mov     rsi, [rbp+var_38]
0x180040fff  mov     [rbp+var_10], rax
0x180041003  mov     rcx, rax
0x180041006  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004100e  sub     rcx, rsi
0x180041011  mov     rax, 6666666666666667h
0x18004101b  imul    rcx
0x18004101e  mov     ecx, [rbp+Locale]; Locale
0x180041021  mov     r9d, r14d; cchCount1
0x180041024  sar     rdx, 5
0x180041028  mov     r8, r13; lpString1
0x18004102b  mov     rax, rdx
0x18004102e  shr     rax, 3Fh
0x180041032  add     rdx, rax
0x180041035  lea     rax, [rdx+rdx*4]
0x180041039  mov     edx, 20001h; dwCmpFlags
0x18004103e  lea     rdi, [rsi+rax*8]
0x180041042  mov     rax, [rdi]
0x180041045  mov     [rsp+80h+lpString2], rax; lpString2
0x18004104a  mov     [rbp+var_8], rdi
0x18004104e  call    cs:__imp_CompareStringW
0x180041054  sub     eax, 1
0x180041057  jnz     short loc_180041063
0x180041059  cmp     rdi, rsi
0x18004105c  jz      short loc_180041081
0x18004105e  mov     rax, rdi
0x180041061  jmp     short loc_180040FFF
0x180041063  sub     eax, 1
0x180041066  jz      short loc_18004107C
0x180041068  cmp     eax, 1
0x18004106b  jnz     short loc_180041081
0x18004106d  mov     rax, [rbp+var_10]
0x180041071  lea     rsi, [rdi+28h]
0x180041075  cmp     rsi, rax
0x180041078  jnz     short loc_180041003
0x18004107a  jmp     short loc_180041081
0x18004107c  test    rdi, rdi
0x18004107f  jnz     short loc_1800410F1
0x180041081  mov     edi, [rbp+var_50]
0x180041084  mov     r14, [rbp+var_38]
0x180041088  mov     r13, [rbp+var_30]
0x18004108c  mov     r15b, 1
0x18004108f  mov     rcx, [rbp+pv]; pv
0x180041093  call    cs:__imp_CoTaskMemFree
0x180041099  mov     rsi, [rbp+arg_18]
0x18004109d  xor     edx, edx
0x18004109f  test    ebx, ebx
0x1800410a1  jns     loc_180040F91
0x1800410a7  test    ebx, ebx
0x1800410a9  js      loc_1800411A8
0x1800410af  mov     rdi, [rbp+var_20]
0x1800410b3  mov     ebx, edx
0x1800410b5  test    rdi, rdi
0x1800410b8  setz    bl
0x1800410bb  mov     r13, [rbp+arg_28]
0x1800410bf  mov     r15, [rbp+arg_30]
0x1800410c3  mov     rcx, [rbp+lpString1]; pv
0x1800410c7  call    cs:__imp_CoTaskMemFree
0x1800410cd  mov     [r13+0], r12d
0x1800410d1  mov     [r15], rdi
0x1800410d4  mov     eax, ebx
0x1800410d6  mov     rbx, [rsp+80h+arg_0]
0x1800410de  add     rsp, 80h
0x1800410e5  pop     r15
0x1800410e7  pop     r14
0x1800410e9  pop     r13
0x1800410eb  pop     r12
0x1800410ed  pop     rdi
0x1800410ee  pop     rsi
0x1800410ef  pop     rbp
0x1800410f0  retn
0x1800410f1  mov     r13, [rdi+20h]
0x1800410f5  mov     rsi, [rdi+18h]
0x1800410f9  mov     edi, [rbp+arg_20]
0x1800410fc  mov     r14d, [rbp+var_50]
0x180041100  test    r15b, r15b
0x180041103  jnz     short loc_180041117
0x180041105  cmp     rsi, r13
0x180041108  jz      short loc_180041117
0x18004110a  cmp     dword ptr [rsi], 5
0x18004110d  jz      short loc_180041141
0x18004110f  add     rsi, 18h
0x180041113  test    ebx, ebx
0x180041115  jns     short loc_180041100
0x180041117  mov     rdi, [rbp+var_8]
0x18004111b  mov     r14, [rdi+8]
0x18004111f  mov     r13, [rdi+10h]
0x180041123  mov     edi, [rbp+var_50]
0x180041126  inc     edi
0x180041128  mov     [rbp+var_38], r14
0x18004112c  mov     [rbp+var_30], r13
0x180041130  mov     [rbp+var_50], edi
0x180041133  cmp     edi, [rbp+var_4C]
0x180041136  jnb     loc_18004108C
0x18004113c  jmp     loc_18004108F
0x180041141  mov     rcx, [rsi+8]
0x180041145  mov     rax, [rcx]
0x180041148  mov     rax, [rax]
0x18004114b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041150  mov     r8, [rbp+lpString1]; lpString1
0x180041154  xor     edx, edx; dwCmpFlags
0x180041156  mov     [rsp+80h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004115e  or      r9d, 0FFFFFFFFh; cchCount1
0x180041162  mov     [rsp+80h+lpString2], rax; lpString2
0x180041167  lea     ecx, [rdx+7Fh]; Locale
0x18004116a  call    cs:__imp_CompareStringW
0x180041170  cmp     eax, 2
0x180041173  jnz     short loc_18004110F
0x180041175  mov     r8, [rsi+10h]
0x180041179  lea     r9, [rbp+var_20]
0x18004117d  mov     r12d, r14d
0x180041180  sub     r12d, edi
0x180041183  inc     r12d
0x180041186  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18004118b  mov     ebx, eax
0x18004118d  mov     r15b, 1
0x180041190  jmp     loc_18004110F
0x180041195  mov     ebx, 80004003h
0x18004119a  jmp     loc_1800410D4
0x18004119f  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800411a3  jmp     loc_18008A4D8
0x1800411a8  mov     rdi, [rbp+var_20]
0x1800411ac  jmp     loc_1800410BB
0x1800411b1  mov     ebx, 80070057h
0x1800411b6  jmp     loc_1800410CD
0x18008a4d8  inc     r14
0x18008a4db  cmp     [r13+r14*2+0], ax
0x18008a4e1  jnz     short loc_18008A4D8
0x18008a4e3  jmp     loc_180040FF7
```
