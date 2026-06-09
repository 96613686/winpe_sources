# StructuredQuery1::ParseTracer::WriteLeafCondition(void *,ICondition *,int)

- ea: `0x180041af8`
- end: `0x180041ee3`
- name: `?WriteLeafCondition@ParseTracer@StructuredQuery1@@AEAAJPEAXPEAUICondition@@H@Z`
- size: `1003`
- prototype: `__int64 __fastcall(StructuredQuery1::ParseTracer *__hidden this, void *, struct ICondition *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180041618`

## callees

- `0x180041a30`
- `0x180041af8`
- `0x180041eec`
- `0x1800421dc`
- `0x18005b244`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d83`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ParseTracer::WriteLeafCondition(
        StructuredQuery1::ParseTracer *this,
        void *a2,
        struct ICondition *a3,
        int a4)
{
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetInputTerms)(ICondition *, IRichChunk **, IRichChunk **, IRichChunk **); // rax
  int v10; // ebx
  struct IConditionVtbl *v11; // rax
  __int64 v12; // r15
  __int64 v13; // rax
  unsigned int v14; // r14d
  enum tagCONDITION_OPERATION v15; // edx
  const wchar_t *v16; // rax
  struct IConditionVtbl *v17; // rax
  unsigned __int16 *v18; // r14
  int v19; // eax
  struct IConditionVtbl *v20; // rax
  struct IRichChunk *v21; // rcx
  struct IRichChunk *v22; // rcx
  struct IRichChunk *v23; // rcx
  const wchar_t *v25; // r8
  wchar_t *v26; // [rsp+30h] [rbp-38h] BYREF
  struct IRichChunk *v27; // [rsp+38h] [rbp-30h] BYREF
  struct IRichChunk *v28; // [rsp+40h] [rbp-28h] BYREF
  struct IRichChunk *v29; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-18h] BYREF
  LPVOID v31[2]; // [rsp+58h] [rbp-10h] BYREF
  StructuredQuery1 *v32; // [rsp+C0h] [rbp+58h] BYREF

  lpVtbl = a3->lpVtbl;
  v27 = 0;
  v28 = 0;
  GetInputTerms = lpVtbl->GetInputTerms;
  v29 = 0;
  v10 = ((__int64 (__fastcall *)(struct ICondition *, struct IRichChunk **, struct IRichChunk **, struct IRichChunk **))GetInputTerms)(
          a3,
          &v27,
          &v28,
          &v29);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v11 = a3->lpVtbl;
  v26 = 0;
  LODWORD(v32) = 0;
  v10 = ((__int64 (__fastcall *)(struct ICondition *, wchar_t **, StructuredQuery1 **, _QWORD))v11->GetComparisonInfo)(
          a3,
          &v26,
          &v32,
          0);
  if ( v10 < 0 )
    goto LABEL_32;
  v12 = -1;
  if ( v26 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v26[v13] );
    if ( v13 )
    {
      v10 = StructuredQuery1::ParseTracer::Format(
              this,
              a2,
              L"%*s<Property",
              (unsigned int)(2 * a4),
              &cchOriginalDestLength);
      if ( v10 < 0 )
        goto LABEL_31;
      v10 = StructuredQuery1::ParseTracer::WriteAttribute(this, a2, L"name", v26);
      if ( v10 < 0 )
        goto LABEL_31;
      v10 = StructuredQuery1::ParseTracer::WriteTerm(this, a2, v27);
      if ( v10 < 0 )
        goto LABEL_31;
      v10 = StructuredQuery1::ParseTracer::Format(this, a2, L">\n");
      if ( v10 < 0 )
        goto LABEL_31;
    }
  }
  v14 = 2 * a4;
  v10 = StructuredQuery1::ParseTracer::Format(this, a2, L"%*s<Operation", v14, &cchOriginalDestLength);
  if ( v10 < 0 )
    goto LABEL_31;
  v16 = StructuredQuery1::OperationText((StructuredQuery1 *)(unsigned int)v32, v15);
  v10 = StructuredQuery1::ParseTracer::WriteAttribute(this, a2, L"op", v16);
  if ( v10 < 0 )
    goto LABEL_31;
  v10 = StructuredQuery1::ParseTracer::WriteTerm(this, a2, v28);
  if ( v10 < 0 )
    goto LABEL_31;
  v10 = StructuredQuery1::ParseTracer::Format(this, a2, L">\n");
  if ( v10 < 0 )
    goto LABEL_31;
  v17 = a3->lpVtbl;
  v31[0] = 0;
  v10 = ((__int64 (__fastcall *)(struct ICondition *, LPVOID *))v17->GetValueNormalization)(a3, v31);
  if ( v10 < 0 )
    goto LABEL_31;
  v10 = StructuredQuery1::ParseTracer::Format(this, a2, L"%*s<Value", v14, &cchOriginalDestLength);
  if ( v10 < 0 )
    goto LABEL_30;
  v18 = (unsigned __int16 *)v31[0];
  v10 = StructuredQuery1::ParseTracer::Format(this, a2, L" %s=\"", L"normalized");
  if ( v10 < 0 )
    goto LABEL_30;
  while ( *v18 )
  {
    if ( *v18 < 0x20u )
    {
      v19 = StructuredQuery1::ParseTracer::Format(this, a2, L"&#%d;", *v18);
    }
    else
    {
      if ( *v18 == 60 )
      {
        v25 = L"&lt;";
      }
      else if ( *v18 == 34 )
      {
        v25 = L"&quot;";
      }
      else
      {
        if ( *v18 != 38 )
        {
          if ( *v18 == 62 )
            v19 = StructuredQuery1::ParseTracer::Format(this, a2, L"&gt;");
          else
            v19 = StructuredQuery1::ParseTracer::Format(this, a2, L"%c", *v18);
          goto LABEL_21;
        }
        v25 = L"&amp;";
      }
      v19 = StructuredQuery1::ParseTracer::Format(this, a2, v25);
    }
LABEL_21:
    ++v18;
    v10 = v19;
    if ( v19 < 0 )
      goto LABEL_30;
  }
  v10 = StructuredQuery1::ParseTracer::Format(this, a2, L"\"");
  if ( v10 >= 0 )
  {
    v20 = a3->lpVtbl;
    pv = 0;
    v10 = ((__int64 (__fastcall *)(struct ICondition *, LPVOID *))v20->GetValueType)(a3, &pv);
    if ( v10 >= 0 )
    {
      if ( !pv )
        goto LABEL_55;
      do
        ++v12;
      while ( *((_WORD *)pv + v12) );
      if ( !v12
        || (v10 = StructuredQuery1::ParseTracer::WriteAttribute(this, a2, L"type", (const wchar_t *)pv), v10 >= 0) )
      {
LABEL_55:
        v10 = StructuredQuery1::ParseTracer::WriteTerm(this, a2, v29);
        if ( v10 >= 0 )
          v10 = StructuredQuery1::ParseTracer::Format(this, a2, L">\n");
      }
      CoTaskMemFree(pv);
    }
  }
LABEL_30:
  CoTaskMemFree(v31[0]);
LABEL_31:
  CoTaskMemFree(v26);
LABEL_32:
  v21 = v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(struct IRichChunk *))v21->lpVtbl->Release)(v21);
  }
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    ((void (__fastcall *)(struct IRichChunk *))v22->lpVtbl->Release)(v22);
  }
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    ((void (__fastcall *)(struct IRichChunk *))v23->lpVtbl->Release)(v23);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180041af8  push    rbp
0x180041afa  push    rbx
0x180041afb  push    rsi
0x180041afc  push    rdi
0x180041afd  push    r12
0x180041aff  push    r13
0x180041b01  push    r14
0x180041b03  push    r15
0x180041b05  mov     rbp, rsp
0x180041b08  sub     rsp, 68h
0x180041b0c  mov     rax, [r8]
0x180041b0f  mov     r12, r8
0x180041b12  xor     r13d, r13d
0x180041b15  lea     r8, [rbp+var_28]
0x180041b19  mov     r14d, r9d
0x180041b1c  mov     [rbp+var_30], r13
0x180041b20  mov     rdi, rdx
0x180041b23  mov     [rbp+var_28], r13
0x180041b27  mov     rax, [rax+68h]
0x180041b2b  lea     r9, [rbp+var_20]
0x180041b2f  mov     rsi, rcx
0x180041b32  mov     [rbp+var_20], r13
0x180041b36  lea     rdx, [rbp+var_30]
0x180041b3a  mov     rcx, r12
0x180041b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b42  mov     ebx, eax
0x180041b44  test    eax, eax
0x180041b46  js      loc_180041DD4
0x180041b4c  mov     rax, [r12]
0x180041b50  lea     r8, [rbp+arg_10]
0x180041b54  xor     r9d, r9d
0x180041b57  mov     [rbp+var_38], r13
0x180041b5b  lea     rdx, [rbp+var_38]
0x180041b5f  mov     dword ptr [rbp+arg_10], r13d
0x180041b63  mov     rcx, r12
0x180041b66  mov     rax, [rax+50h]
0x180041b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b6f  mov     ebx, eax
0x180041b71  test    eax, eax
0x180041b73  js      loc_180041D89
0x180041b79  mov     rcx, [rbp+var_38]
0x180041b7d  lea     rdx, cchOriginalDestLength
0x180041b84  or      r15, 0FFFFFFFFFFFFFFFFh
0x180041b88  test    rcx, rcx
0x180041b8b  jz      short loc_180041BA3
0x180041b8d  mov     rax, r15
0x180041b90  inc     rax
0x180041b93  cmp     [rcx+rax*2], r13w
0x180041b98  jnz     short loc_180041B90
0x180041b9a  test    rax, rax
0x180041b9d  jnz     loc_180041DE7
0x180041ba3  mov     [rsp+68h+var_48], rdx
0x180041ba8  lea     r8, aSOperation; "%*s<Operation"
0x180041baf  add     r14d, r14d
0x180041bb2  mov     rdx, rdi; void *
0x180041bb5  mov     r9d, r14d
0x180041bb8  mov     rcx, rsi; this
0x180041bbb  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041bc0  mov     ebx, eax
0x180041bc2  test    eax, eax
0x180041bc4  js      loc_180041D7F
0x180041bca  mov     ecx, dword ptr [rbp+arg_10]; this
0x180041bcd  call    ?OperationText@StructuredQuery1@@YAPEB_WW4tagCONDITION_OPERATION@@@Z; StructuredQuery1::OperationText(tagCONDITION_OPERATION)
0x180041bd2  mov     r9, rax; wchar_t *
0x180041bd5  lea     r8, aOp; "op"
0x180041bdc  mov     rcx, rsi; this
0x180041bdf  mov     rdx, rdi; void *
0x180041be2  call    ?WriteAttribute@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_W1@Z; StructuredQuery1::ParseTracer::WriteAttribute(void *,wchar_t const *,wchar_t const *)
0x180041be7  mov     ebx, eax
0x180041be9  test    eax, eax
0x180041beb  js      loc_180041D7F
0x180041bf1  mov     r8, [rbp+var_28]; struct IRichChunk *
0x180041bf5  mov     rdx, rdi; void *
0x180041bf8  mov     rcx, rsi; this
0x180041bfb  call    ?WriteTerm@ParseTracer@StructuredQuery1@@AEAAJPEAXPEAUIRichChunk@@@Z; StructuredQuery1::ParseTracer::WriteTerm(void *,IRichChunk *)
0x180041c00  mov     ebx, eax
0x180041c02  test    eax, eax
0x180041c04  js      loc_180041D7F
0x180041c0a  lea     r8, asc_18009BC60; ">\n"
0x180041c11  mov     rdx, rdi; void *
0x180041c14  mov     rcx, rsi; this
0x180041c17  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041c1c  mov     ebx, eax
0x180041c1e  test    eax, eax
0x180041c20  js      loc_180041D7F
0x180041c26  mov     rax, [r12]
0x180041c2a  lea     rdx, [rbp+var_10]
0x180041c2e  mov     rcx, r12
0x180041c31  mov     [rbp+var_10], r13
0x180041c35  mov     rax, [rax+60h]
0x180041c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c3e  mov     ebx, eax
0x180041c40  test    eax, eax
0x180041c42  js      loc_180041D7F
0x180041c48  lea     rax, cchOriginalDestLength
0x180041c4f  mov     r9d, r14d
0x180041c52  lea     r8, aSValue; "%*s<Value"
0x180041c59  mov     [rsp+68h+var_48], rax
0x180041c5e  mov     rdx, rdi; void *
0x180041c61  mov     rcx, rsi; this
0x180041c64  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041c69  mov     ebx, eax
0x180041c6b  test    eax, eax
0x180041c6d  js      loc_180041D75
0x180041c73  mov     r14, [rbp+var_10]
0x180041c77  lea     r9, aNormalized; "normalized"
0x180041c7e  lea     r8, aS_3; " %s=\""
0x180041c85  mov     rdx, rdi; void *
0x180041c88  mov     rcx, rsi; this
0x180041c8b  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041c90  mov     ebx, eax
0x180041c92  test    eax, eax
0x180041c94  js      loc_180041D75
0x180041c9a  cmp     [r14], r13w
0x180041c9e  jz      short loc_180041CF9
0x180041ca0  cmp     word ptr [r14], 20h ; ' '
0x180041ca5  jb      loc_180041E6D
0x180041cab  cmp     word ptr [r14], 3Ch ; '<'
0x180041cb0  jz      loc_180041E7F
0x180041cb6  cmp     word ptr [r14], 22h ; '"'
0x180041cbb  jz      loc_180041EDA
0x180041cc1  cmp     word ptr [r14], 26h ; '&'
0x180041cc6  jz      loc_180041ED1
0x180041ccc  cmp     word ptr [r14], 3Eh ; '>'
0x180041cd1  mov     rdx, rdi; void *
0x180041cd4  mov     rcx, rsi; this
0x180041cd7  jz      loc_180041EC8
0x180041cdd  lea     r8, aC; "%c"
0x180041ce4  movzx   r9d, word ptr [r14]
0x180041ce8  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041ced  add     r14, 2
0x180041cf1  mov     ebx, eax
0x180041cf3  test    eax, eax
0x180041cf5  jns     short loc_180041C9A
0x180041cf7  jmp     short loc_180041D75
0x180041cf9  lea     r8, asc_18009BCB4; "\""
0x180041d00  mov     rdx, rdi; void *
0x180041d03  mov     rcx, rsi; this
0x180041d06  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041d0b  mov     ebx, eax
0x180041d0d  test    eax, eax
0x180041d0f  js      short loc_180041D75
0x180041d11  mov     rax, [r12]
0x180041d15  lea     rdx, [rbp+pv]
0x180041d19  mov     rcx, r12
0x180041d1c  mov     [rbp+pv], r13
0x180041d20  mov     rax, [rax+58h]
0x180041d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d29  mov     ebx, eax
0x180041d2b  test    eax, eax
0x180041d2d  js      short loc_180041D75
0x180041d2f  mov     r9, [rbp+pv]; wchar_t *
0x180041d33  test    r9, r9
0x180041d36  jz      loc_180041E96
0x180041d3c  inc     r15
0x180041d3f  cmp     [r9+r15*2], r13w
0x180041d44  jnz     short loc_180041D3C
0x180041d46  test    r15, r15
0x180041d49  jz      loc_180041E96
0x180041d4f  lea     r8, aType; "type"
0x180041d56  mov     rdx, rdi; void *
0x180041d59  mov     rcx, rsi; this
0x180041d5c  call    ?WriteAttribute@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_W1@Z; StructuredQuery1::ParseTracer::WriteAttribute(void *,wchar_t const *,wchar_t const *)
0x180041d61  mov     ebx, eax
0x180041d63  test    eax, eax
0x180041d65  jns     loc_180041E96
0x180041d6b  mov     rcx, [rbp+pv]; pv
0x180041d6f  call    cs:__imp_CoTaskMemFree
0x180041d75  mov     rcx, [rbp+var_10]; pv
0x180041d79  call    cs:__imp_CoTaskMemFree
0x180041d7f  mov     rcx, [rbp+var_38]; pv
0x180041d83  call    cs:__imp_CoTaskMemFree
0x180041d89  mov     rcx, [rbp+var_30]
0x180041d8d  test    rcx, rcx
0x180041d90  jz      short loc_180041DA2
0x180041d92  mov     [rbp+var_30], r13
0x180041d96  mov     rax, [rcx]
0x180041d99  mov     rax, [rax+10h]
0x180041d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041da2  mov     rcx, [rbp+var_28]
0x180041da6  test    rcx, rcx
0x180041da9  jz      short loc_180041DBB
0x180041dab  mov     [rbp+var_28], r13
0x180041daf  mov     rax, [rcx]
0x180041db2  mov     rax, [rax+10h]
0x180041db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dbb  mov     rcx, [rbp+var_20]
0x180041dbf  test    rcx, rcx
0x180041dc2  jz      short loc_180041DD4
0x180041dc4  mov     [rbp+var_20], r13
0x180041dc8  mov     rax, [rcx]
0x180041dcb  mov     rax, [rax+10h]
0x180041dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dd4  mov     eax, ebx
0x180041dd6  add     rsp, 68h
0x180041dda  pop     r15
0x180041ddc  pop     r14
0x180041dde  pop     r13
0x180041de0  pop     r12
0x180041de2  pop     rdi
0x180041de3  pop     rsi
0x180041de4  pop     rbx
0x180041de5  pop     rbp
0x180041de6  retn
0x180041de7  mov     [rsp+68h+var_48], rdx
0x180041dec  lea     r9d, [r14+r14]
0x180041df0  mov     rdx, rdi; void *
0x180041df3  lea     r8, aSProperty; "%*s<Property"
0x180041dfa  mov     rcx, rsi; this
0x180041dfd  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041e02  mov     ebx, eax
0x180041e04  test    eax, eax
0x180041e06  js      loc_180041D7F
0x180041e0c  mov     r9, [rbp+var_38]; wchar_t *
0x180041e10  lea     r8, aName; "name"
0x180041e17  mov     rdx, rdi; void *
0x180041e1a  mov     rcx, rsi; this
0x180041e1d  call    ?WriteAttribute@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_W1@Z; StructuredQuery1::ParseTracer::WriteAttribute(void *,wchar_t const *,wchar_t const *)
0x180041e22  mov     ebx, eax
0x180041e24  test    eax, eax
0x180041e26  js      loc_180041D7F
0x180041e2c  mov     r8, [rbp+var_30]; struct IRichChunk *
0x180041e30  mov     rdx, rdi; void *
0x180041e33  mov     rcx, rsi; this
0x180041e36  call    ?WriteTerm@ParseTracer@StructuredQuery1@@AEAAJPEAXPEAUIRichChunk@@@Z; StructuredQuery1::ParseTracer::WriteTerm(void *,IRichChunk *)
0x180041e3b  mov     ebx, eax
0x180041e3d  test    eax, eax
0x180041e3f  js      loc_180041D7F
0x180041e45  lea     r8, asc_18009BC60; ">\n"
0x180041e4c  mov     rdx, rdi; void *
0x180041e4f  mov     rcx, rsi; this
0x180041e52  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041e57  mov     ebx, eax
0x180041e59  test    eax, eax
0x180041e5b  js      loc_180041D7F
0x180041e61  lea     rdx, cchOriginalDestLength
0x180041e68  jmp     loc_180041BA3
0x180041e6d  lea     r8, aD_4; "&#%d;"
0x180041e74  mov     rdx, rdi
0x180041e77  mov     rcx, rsi
0x180041e7a  jmp     loc_180041CE4
0x180041e7f  lea     r8, aLt; "&lt;"
0x180041e86  mov     rdx, rdi; void *
0x180041e89  mov     rcx, rsi; this
0x180041e8c  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041e91  jmp     loc_180041CED
0x180041e96  mov     r8, [rbp+var_20]; struct IRichChunk *
0x180041e9a  mov     rdx, rdi; void *
0x180041e9d  mov     rcx, rsi; this
0x180041ea0  call    ?WriteTerm@ParseTracer@StructuredQuery1@@AEAAJPEAXPEAUIRichChunk@@@Z; StructuredQuery1::ParseTracer::WriteTerm(void *,IRichChunk *)
0x180041ea5  mov     ebx, eax
0x180041ea7  test    eax, eax
0x180041ea9  js      loc_180041D6B
0x180041eaf  lea     r8, asc_18009BC60; ">\n"
0x180041eb6  mov     rdx, rdi; void *
0x180041eb9  mov     rcx, rsi; this
0x180041ebc  call    ?Format@ParseTracer@StructuredQuery1@@AEAAJPEAXPEB_WZZ; StructuredQuery1::ParseTracer::Format(void *,wchar_t const *,...)
0x180041ec1  mov     ebx, eax
0x180041ec3  jmp     loc_180041D6B
0x180041ec8  lea     r8, aGt; "&gt;"
0x180041ecf  jmp     short loc_180041E8C
0x180041ed1  lea     r8, aAmp; "&amp;"
0x180041ed8  jmp     short loc_180041E86
0x180041eda  lea     r8, aQuot; "&quot;"
0x180041ee1  jmp     short loc_180041E86
```
