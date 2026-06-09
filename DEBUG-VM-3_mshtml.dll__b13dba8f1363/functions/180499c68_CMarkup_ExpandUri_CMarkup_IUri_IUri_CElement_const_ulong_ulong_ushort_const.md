# CMarkup::ExpandUri(CMarkup *,IUri *,IUri * *,CElement const *,ulong,ulong,ushort const *)

- ea: `0x180499c68`
- end: `0x18049a389`
- name: `?ExpandUri@CMarkup@@SAJPEAV1@PEAUIUri@@PEAPEAU2@PEBVCElement@@KKPEBG@Z`
- size: `1825`
- prototype: `__int64 __usercall@<rax>(struct CMarkup *this@<rcx>, struct IUri *@<rdx>, struct IUri **@<r8>, const struct CElement *@<r9>, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18015111c`
- `0x1803702b4`
- `0x1804993ac`
- `0x18049b6a4`
- `0x1804fa67c`
- `0x180501cd0`
- `0x18054a704`
- `0x180655a54`
- `0x180832ec4`
- `0x18088243c`
- `0x180890f8c`
- `0x1808c893c`
- `0x1808eefac`
- `0x1808ef39c`
- `0x1809955d8`
- `0x180a62ecc`

## callees

- `0x18006f7c8`
- `0x1800cd38c`
- `0x1800de220`
- `0x1800e4c70`
- `0x1800f5454`
- `0x18010ce6c`
- `0x180135278`
- `0x18019b034`
- `0x180499c20`
- `0x180499c68`
- `0x1808393c4`
- `0x180890d04`
- `0x1810d1010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18049a1d9`
- `msvcrt!_wcsnicmp` at `0x18049a1d9`
- `iertutil!GetIUriPriv` at `0x18049a2ad`
- `iertutil!GetIUriPriv` at `0x18049a2ad`
- `iertutil!CreateUri` at `0x18049a087`
- `iertutil!CreateUri` at `0x18049a132`
- `iertutil!CreateUri` at `0x18049a200`
- `iertutil!CreateUri` at `0x18049a087`
- `iertutil!CreateUri` at `0x18049a132`
- `iertutil!CreateUri` at `0x18049a200`
- `urlmon!CoInternetQueryInfo` at `0x18049a056`
- `urlmon!CoInternetQueryInfo` at `0x18049a056`
- `urlmon!CoInternetCombineIUri` at `0x180499e8a`
- `urlmon!CoInternetCombineIUri` at `0x18049a0b0`
- `urlmon!CoInternetCombineIUri` at `0x180499e8a`
- `urlmon!CoInternetCombineIUri` at `0x18049a0b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18049a301`
- `OLEAUT32!__imp_SysFreeString` at `0x18049a376`
- `OLEAUT32!__imp_SysFreeString` at `0x18049a301`
- `OLEAUT32!__imp_SysFreeString` at `0x18049a376`
- `OLEAUT32!__imp_SysStringLen` at `0x18049a338`
- `OLEAUT32!__imp_SysStringLen` at `0x18049a338`

## pseudocode

```c
__int64 __fastcall CMarkup::ExpandUri(
        struct CMarkup *this,
        struct IUri *a2,
        struct IUri **a3,
        const struct CElement *a4,
        char a5,
        DWORD a6,
        struct IUri *a7)
{
  DWORD v9; // ecx
  int v10; // r13d
  const struct CMarkup *MarkupPtr; // rbx
  const unsigned __int16 *v12; // r14
  struct CMarkup *v13; // rdi
  CDoc *v14; // rax
  struct CMarkupTopElemCache *v15; // rax
  __int64 v16; // rax
  const unsigned __int16 *OriginUrl; // rax
  IUri *UriRaw; // rax
  wchar_t *v19; // rbx
  IUri *v20; // rdi
  BOOL v21; // r14d
  BOOL v22; // r12d
  int v23; // edi
  IUri **v24; // r14
  DWORD v25; // r12d
  struct IUriVtbl *lpVtbl; // rax
  CDoc *v28; // rax
  const WCHAR *v29; // rdi
  IUri **v30; // rcx
  IUri *v31; // rdi
  DWORD v32; // edx
  const WCHAR *v33; // rcx
  __int64 v34; // rcx
  struct CDoc *v35; // rax
  CDoc *v36; // rax
  struct CMarkup *v37; // rcx
  const unsigned __int16 *v38; // r12
  UINT v39; // ebx
  wchar_t *v40; // [rsp+48h] [rbp-61h] BYREF
  IUri *pBaseUri; // [rsp+50h] [rbp-59h] BYREF
  int pvBuffer; // [rsp+58h] [rbp-51h] BYREF
  void **v43; // [rsp+60h] [rbp-49h]
  IUri *v44; // [rsp+68h] [rbp-41h]
  unsigned int v45; // [rsp+70h] [rbp-39h]
  wchar_t *String2[2]; // [rsp+78h] [rbp-31h] BYREF
  UINT v47; // [rsp+88h] [rbp-21h] BYREF
  int v48; // [rsp+90h] [rbp-19h] BYREF
  DWORD dwCombineFlags; // [rsp+94h] [rbp-15h]
  DWORD pcbBuffer; // [rsp+98h] [rbp-11h] BYREF
  const unsigned __int16 *v51; // [rsp+A0h] [rbp-9h] BYREF
  const unsigned __int16 *Url; // [rsp+A8h] [rbp-1h]
  IUri **ppCombinedUri; // [rsp+108h] [rbp+5Fh] BYREF

  ppCombinedUri = a3;
  pvBuffer = 0;
  v43 = &CUString::`vftable';
  pcbBuffer = 0;
  pBaseUri = 0;
  v44 = 0;
  v45 = 11;
  v47 = 0;
  *(_OWORD *)String2 = 0;
  if ( !a3 )
  {
    LODWORD(v19) = -2147024809;
LABEL_40:
    v10 = 0;
    goto LABEL_41;
  }
  v9 = 100663296;
  v10 = 1;
  if ( a6 != -1 )
    v9 = a6;
  dwCombineFlags = v9;
  if ( !a2 )
  {
    LODWORD(v19) = CreateUri(&LocaleName, 0x3002B81u, 0, a3);
    goto LABEL_37;
  }
  MarkupPtr = this;
  if ( this
    || (Url = 0, (unsigned __int64)a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL)
    && ((MarkupPtr = CElement::GetMarkupPtr(a4)) != 0
     || (v36 = CElement::Doc(a4), (MarkupPtr = CDoc::PrimaryMarkup(v36)) != 0)) )
  {
    Url = CMarkup::GetUrl(MarkupPtr);
    if ( MarkupPtr )
    {
      if ( *(__int64 (__fastcall **)())(*(_QWORD *)MarkupPtr + 984LL) != _vtguard )
        _report_securityfailure(1);
      if ( (*(unsigned __int8 (__fastcall **)(const struct CMarkup *))(*(_QWORD *)MarkupPtr + 1216LL))(MarkupPtr) )
      {
        OriginUrl = CMarkup::GetUrl(MarkupPtr);
        goto LABEL_19;
      }
    }
  }
  v12 = 0;
  v13 = MarkupPtr;
  if ( MarkupPtr )
  {
    if ( !a4 )
      goto LABEL_15;
    if ( a4 == (const struct CElement *)-1LL )
    {
LABEL_17:
      if ( (*((_BYTE *)v13 + 97) & 2) != 0 )
      {
        if ( (unsigned int)CMarkup::IsXmlParsingMode(v13) )
        {
          if ( *((int *)v13 + 212) >= 90000 )
          {
            a7 = 0;
            if ( (int)CMarkup::GetMarkupPrintUri(v37, &a7) >= 0 )
            {
              v38 = (const unsigned __int16 *)a7;
              v40 = 0;
              if ( (int)GetIUriPriv(a7, &v40) >= 0 )
              {
                v48 = 0;
                v51 = 0;
                if ( (*(int (__fastcall **)(wchar_t *, const unsigned __int16 **, int *))(*(_QWORD *)v40 + 232LL))(
                       v40,
                       &v51,
                       &v48) >= 0 )
                  v12 = v51;
                (*(void (**)(void))(*(_QWORD *)v40 + 16LL))();
              }
              (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v38 + 16LL))(v38);
              if ( v12 )
                goto LABEL_84;
            }
          }
        }
      }
      goto LABEL_18;
    }
  }
  else
  {
    if ( (unsigned __int64)a4 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_18;
    v13 = CElement::GetMarkupPtr(a4);
    if ( !v13 )
    {
      v14 = CElement::Doc(a4);
      v13 = CDoc::PrimaryMarkup(v14);
    }
  }
  CElement::Doc(a4);
  if ( !v13 )
    goto LABEL_18;
LABEL_15:
  v15 = CMarkup::EnsureTopElems(v13);
  if ( !v15 )
    goto LABEL_17;
  v16 = *((_QWORD *)v15 + 6);
  if ( !v16 )
    goto LABEL_17;
  v12 = *(const unsigned __int16 **)(v16 + 88);
  if ( !v12 )
  {
    if ( v13 )
      goto LABEL_17;
LABEL_18:
    OriginUrl = CMarkup::GetOriginUrl(v13);
LABEL_19:
    LODWORD(a7) = 1;
    v12 = OriginUrl;
    goto LABEL_20;
  }
LABEL_84:
  LODWORD(a7) = 0;
LABEL_20:
  if ( v12 == Url )
  {
    UriRaw = CMarkup::GetUriRaw(MarkupPtr);
    pBaseUri = UriRaw;
    if ( UriRaw )
    {
      v19 = 0;
      ((void (__fastcall *)(IUri *))UriRaw->lpVtbl->AddRef)(UriRaw);
      goto LABEL_23;
    }
    v32 = 50342784;
    v33 = L"about:blank";
  }
  else
  {
    v32 = 50342789;
    v33 = v12;
  }
  v19 = (wchar_t *)(unsigned int)CreateUri(v33, v32, 0, &pBaseUri);
LABEL_23:
  if ( (_DWORD)v19 )
    goto LABEL_37;
  v20 = pBaseUri;
  v21 = pBaseUri != v44;
  v22 = v45 != 12;
  if ( pBaseUri != v44 || v45 != 12 )
  {
    if ( String2[0] )
    {
      SysFreeString(String2[0]);
      String2[0] = v19;
    }
    String2[1] = v19;
    v47 = 0;
    if ( v21 && v44 )
    {
      ((void (__fastcall *)(IUri *))v44->lpVtbl->Release)(v44);
      v44 = (IUri *)v19;
    }
  }
  v45 = 12;
  if ( !v20 || !v22 && !v21 )
    goto LABEL_31;
  lpVtbl = v20->lpVtbl;
  v40 = v19;
  if ( ((__int64 (__fastcall *)(IUri *, GUID *, wchar_t **))lpVtbl->QueryInterface)(
         v20,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v40) < 0 )
  {
    LODWORD(v19) = ((__int64 (__fastcall *)(IUri *, _QWORD, wchar_t **, _QWORD))v20->lpVtbl->GetPropertyBSTR)(
                     v20,
                     v45,
                     String2,
                     0);
    if ( (int)v19 >= 0 )
    {
      String2[1] = String2[0];
      v47 = SysStringLen(String2[0]);
    }
  }
  else
  {
    LODWORD(v19) = (*(__int64 (__fastcall **)(wchar_t *, _QWORD, wchar_t **, UINT *))(*(_QWORD *)v40 + 224LL))(
                     v40,
                     v45,
                     &String2[1],
                     &v47);
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  if ( v21 )
  {
    if ( (int)v19 < 0 )
      goto LABEL_37;
    v44 = v20;
    ((void (__fastcall *)(IUri *))v20->lpVtbl->AddRef)(v20);
  }
  else
  {
LABEL_31:
    if ( (int)v19 < 0 )
      goto LABEL_37;
  }
  v23 = (int)a7;
  if ( !bCallCoInternetCombineUrl && !(_DWORD)a7 )
  {
    v39 = v47;
    if ( v47 )
    {
      if ( (unsigned __int64)a4 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( !this )
          goto LABEL_34;
        v34 = *((_QWORD *)this + 40);
        v35 = 0;
        if ( v34 )
          v35 = *(struct CDoc **)(v34 + 16);
      }
      else
      {
        v35 = CElement::Doc(a4);
      }
      if ( v35 && (*((_DWORD *)v35 + 1217) & 0x800) != 0 && v39 == 7 )
        _wcsnicmp(L"outbind", String2[1], 7u);
    }
  }
LABEL_34:
  v24 = ppCombinedUri;
  v25 = dwCombineFlags;
  LODWORD(v19) = CoInternetCombineIUri(pBaseUri, a2, dwCombineFlags, ppCombinedUri, a5 & 3);
  if ( !(_DWORD)v19 )
  {
    if ( (unsigned __int64)a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL && !this )
    {
      this = CElement::GetMarkupForBaseUrl(a4);
      if ( !this )
      {
        v28 = CElement::Doc(a4);
        if ( v28 )
          this = CDoc::PrimaryMarkup(v28);
      }
    }
    if ( !v23 )
    {
      if ( this )
      {
        v29 = CMarkup::GetUrl(this);
        if ( !CoInternetQueryInfo(v29, QUERY_RECOMBINE, 0, &pvBuffer, 4u, &pcbBuffer, 0) )
        {
          if ( pvBuffer )
          {
            v30 = 0;
            ppCombinedUri = 0;
            if ( v29 )
            {
              LODWORD(v19) = CreateUri(v29, 0x3002B84u, 0, (IUri **)&ppCombinedUri);
              if ( (int)v19 < 0 )
                goto LABEL_37;
              v30 = ppCombinedUri;
            }
            v31 = *v24;
            LODWORD(v19) = CoInternetCombineIUri((IUri *)v30, *v24, v25, v24, 0);
            if ( ppCombinedUri )
              ((void (__fastcall *)(IUri **))(*ppCombinedUri)[2].lpVtbl)(ppCombinedUri);
            if ( v31 )
              ((void (__fastcall *)(IUri *))v31->lpVtbl->Release)(v31);
          }
        }
      }
    }
  }
LABEL_37:
  if ( pBaseUri )
    ((void (__fastcall *)(IUri *))pBaseUri->lpVtbl->Release)(pBaseUri);
  v43 = &CUString::`vftable';
  if ( !v44 )
    goto LABEL_40;
LABEL_41:
  if ( v10 || v45 != 11 )
  {
    if ( String2[0] )
    {
      SysFreeString(String2[0]);
      String2[0] = 0;
    }
    String2[1] = 0;
    v47 = 0;
    if ( v10 && v44 )
      ((void (__fastcall *)(IUri *))v44->lpVtbl->Release)(v44);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180499c68  mov     rax, rsp
0x180499c6b  mov     [rax+8], rbx
0x180499c6f  mov     [rax+18h], r8
0x180499c73  mov     [rax+10h], rdx
0x180499c77  push    rbp
0x180499c78  push    rsi
0x180499c79  push    rdi
0x180499c7a  push    r12
0x180499c7c  push    r13
0x180499c7e  push    r14
0x180499c80  push    r15
0x180499c82  lea     rbp, [rax-47h]
0x180499c86  sub     rsp, 0B0h
0x180499c8d  mov     [rbp+3Fh+pvBuffer], 0
0x180499c94  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180499c9b  mov     [rbp+3Fh+var_88], r14
0x180499c9f  xorps   xmm0, xmm0
0x180499ca2  mov     [rbp+3Fh+var_50], 0
0x180499ca9  mov     rsi, r9
0x180499cac  mov     [rbp+3Fh+pBaseUri], 0
0x180499cb4  mov     r15, rcx
0x180499cb7  mov     [rbp+3Fh+var_80], 0
0x180499cbf  mov     [rbp+3Fh+var_78], 0Bh
0x180499cc6  mov     [rbp+3Fh+var_60], 0
0x180499ccd  movdqu  xmmword ptr [rbp+3Fh+String2], xmm0
0x180499cd2  test    r8, r8
0x180499cd5  jz      loc_18049A1E4
0x180499cdb  cmp     [rbp+3Fh+arg_28], 0FFFFFFFFh
0x180499cdf  mov     ecx, 6000000h
0x180499ce4  mov     r13d, 1
0x180499cea  cmovnz  ecx, [rbp+3Fh+arg_28]
0x180499cee  mov     [rbp+3Fh+dwCombineFlags], ecx
0x180499cf1  test    rdx, rdx
0x180499cf4  jz      loc_18049A1EE
0x180499cfa  mov     rbx, r15
0x180499cfd  test    r15, r15
0x180499d00  jz      loc_18049A20D
0x180499d06  mov     rcx, rbx; struct CMarkup *
0x180499d09  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x180499d0e  mov     [rbp+3Fh+var_40], rax
0x180499d12  test    rbx, rbx
0x180499d15  jz      short loc_180499D45
0x180499d17  mov     rax, [rbx]
0x180499d1a  lea     rcx, __vtguard
0x180499d21  cmp     [rax+3D8h], rcx
0x180499d28  jnz     loc_18049A258
0x180499d2e  mov     rax, [rax+4C0h]
0x180499d35  mov     rcx, rbx
0x180499d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499d3d  test    al, al
0x180499d3f  jnz     loc_18049A13F
0x180499d45  xor     r14d, r14d
0x180499d48  mov     rdi, rbx
0x180499d4b  test    rbx, rbx
0x180499d4e  jz      loc_18049A0EA
0x180499d54  test    rsi, rsi
0x180499d57  jz      short loc_180499D81
0x180499d59  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180499d5d  jnz     short loc_180499D74
0x180499d5f  jmp     short loc_180499D9B
0x180499d61  mov     rcx, rsi; this
0x180499d64  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180499d69  mov     rcx, rax; this
0x180499d6c  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x180499d71  mov     rdi, rax
0x180499d74  mov     rcx, rsi; this
0x180499d77  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180499d7c  test    rdi, rdi
0x180499d7f  jz      short loc_180499DA5
0x180499d81  mov     rcx, rdi; this
0x180499d84  call    ?EnsureTopElems@CMarkup@@QEAAPEAVCMarkupTopElemCache@@XZ; CMarkup::EnsureTopElems(void)
0x180499d89  test    rax, rax
0x180499d8c  jz      short loc_180499D9B
0x180499d8e  mov     rax, [rax+30h]
0x180499d92  test    rax, rax
0x180499d95  jnz     loc_18049A189
0x180499d9b  test    byte ptr [rdi+61h], 2
0x180499d9f  jnz     loc_18049A261
0x180499da5  mov     rcx, rdi; this
0x180499da8  call    ?GetOriginUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetOriginUrl(CMarkup const * const)
0x180499dad  mov     dword ptr [rbp+3Fh+arg_30], r13d
0x180499db1  mov     r14, rax
0x180499db4  cmp     r14, [rbp+3Fh+var_40]
0x180499db8  jnz     loc_18049A14C
0x180499dbe  mov     rcx, rbx; struct CMarkup *
0x180499dc1  call    ?GetUriRaw@CMarkup@@SAPEAUIUri@@QEBV1@@Z; CMarkup::GetUriRaw(CMarkup const * const)
0x180499dc6  mov     [rbp+3Fh+pBaseUri], rax
0x180499dca  mov     rcx, rax
0x180499dcd  test    rax, rax
0x180499dd0  jz      loc_18049A11F
0x180499dd6  mov     rax, [rax]
0x180499dd9  xor     ebx, ebx
0x180499ddb  mov     rax, [rax+8]
0x180499ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499de4  test    ebx, ebx
0x180499de6  jnz     loc_180499EAC
0x180499dec  mov     rdi, [rbp+3Fh+pBaseUri]
0x180499df0  xor     r14d, r14d
0x180499df3  cmp     rdi, [rbp+3Fh+var_80]
0x180499df7  setnz   r14b
0x180499dfb  xor     r12d, r12d
0x180499dfe  cmp     [rbp+3Fh+var_78], 0Ch
0x180499e02  setnz   r12b
0x180499e06  test    r14d, r14d
0x180499e09  jz      loc_18049A00D
0x180499e0f  mov     rcx, [rbp+3Fh+String2]; bstrString
0x180499e13  test    rcx, rcx
0x180499e16  jnz     loc_18049A301
0x180499e1c  mov     [rbp+3Fh+String2+8], rbx
0x180499e20  mov     [rbp+3Fh+var_60], ebx
0x180499e23  test    r14d, r14d
0x180499e26  jz      short loc_180499E41
0x180499e28  mov     rcx, [rbp+3Fh+var_80]
0x180499e2c  test    rcx, rcx
0x180499e2f  jz      short loc_180499E41
0x180499e31  mov     rax, [rcx]
0x180499e34  mov     rax, [rax+10h]
0x180499e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499e3d  mov     [rbp+3Fh+var_80], rbx
0x180499e41  mov     [rbp+3Fh+var_78], 0Ch
0x180499e48  test    rdi, rdi
0x180499e4b  jnz     loc_180499F3B
0x180499e51  test    ebx, ebx
0x180499e53  js      short loc_180499EAC
0x180499e55  cmp     cs:?bCallCoInternetCombineUrl@@3HA, 0; int bCallCoInternetCombineUrl
0x180499e5c  mov     edi, dword ptr [rbp+3Fh+arg_30]
0x180499e5f  jnz     short loc_180499E69
0x180499e61  test    edi, edi
0x180499e63  jz      loc_18049A346
0x180499e69  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x180499e6c  mov     r14, [rbp+3Fh+ppCombinedUri]
0x180499e70  and     eax, 3
0x180499e73  mov     r12d, [rbp+3Fh+dwCombineFlags]
0x180499e77  mov     r9, r14; ppCombinedUri
0x180499e7a  mov     rdx, [rbp+3Fh+pRelativeUri]; pRelativeUri
0x180499e7e  mov     r8d, r12d; dwCombineFlags
0x180499e81  mov     rcx, [rbp+3Fh+pBaseUri]; pBaseUri
0x180499e85  mov     [rsp+0E0h+dwReserved], rax; dwReserved
0x180499e8a  call    cs:__imp_CoInternetCombineIUri
0x180499e90  mov     ebx, eax
0x180499e92  test    eax, eax
0x180499e94  jnz     short loc_180499EAC
0x180499e96  lea     rax, [rsi-1]
0x180499e9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180499e9e  jbe     loc_180499FCF
0x180499ea4  test    edi, edi
0x180499ea6  jz      loc_18049A01B
0x180499eac  lea     r14, ??_7CUString@@6B@; const CUString::`vftable'
0x180499eb3  mov     rcx, [rbp+3Fh+pBaseUri]
0x180499eb7  test    rcx, rcx
0x180499eba  jz      short loc_180499EC8
0x180499ebc  mov     rax, [rcx]
0x180499ebf  mov     rax, [rax+10h]
0x180499ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499ec8  cmp     [rbp+3Fh+var_80], 0
0x180499ecd  mov     [rbp+3Fh+var_88], r14
0x180499ed1  jnz     short loc_180499ED6
0x180499ed3  xor     r13d, r13d
0x180499ed6  xor     eax, eax
0x180499ed8  cmp     [rbp+3Fh+var_78], 0Bh
0x180499edc  setnz   al
0x180499edf  test    r13d, r13d
0x180499ee2  jz      loc_180499FC2
0x180499ee8  mov     rcx, [rbp+3Fh+String2]; bstrString
0x180499eec  test    rcx, rcx
0x180499eef  jnz     loc_18049A376
0x180499ef5  mov     [rbp+3Fh+String2+8], 0
0x180499efd  mov     [rbp+3Fh+var_60], 0
0x180499f04  test    r13d, r13d
0x180499f07  jz      short loc_180499F1E
0x180499f09  mov     rcx, [rbp+3Fh+var_80]
0x180499f0d  test    rcx, rcx
0x180499f10  jz      short loc_180499F1E
0x180499f12  mov     rax, [rcx]
0x180499f15  mov     rax, [rax+10h]
0x180499f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499f1e  mov     eax, ebx
0x180499f20  mov     rbx, [rsp+0E0h+arg_0]
0x180499f28  add     rsp, 0B0h
0x180499f2f  pop     r15
0x180499f31  pop     r14
0x180499f33  pop     r13
0x180499f35  pop     r12
0x180499f37  pop     rdi
0x180499f38  pop     rsi
0x180499f39  pop     rbp
0x180499f3a  retn
0x180499f3b  test    r12d, r12d
0x180499f3e  jz      loc_18049A111
0x180499f44  mov     rax, [rdi]
0x180499f47  lea     r8, [rbp+3Fh+var_A0]
0x180499f4b  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x180499f52  mov     [rbp+3Fh+var_A0], rbx
0x180499f56  mov     rcx, rdi
0x180499f59  mov     rax, [rax]
0x180499f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499f61  mov     edx, [rbp+3Fh+var_78]
0x180499f64  test    eax, eax
0x180499f66  js      loc_18049A310
0x180499f6c  mov     rcx, [rbp+3Fh+var_A0]
0x180499f70  lea     r9, [rbp+3Fh+var_60]
0x180499f74  lea     r8, [rbp+3Fh+String2+8]
0x180499f78  mov     rax, [rcx]
0x180499f7b  mov     rax, [rax+0E0h]
0x180499f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499f87  mov     rcx, [rbp+3Fh+var_A0]
0x180499f8b  mov     ebx, eax
0x180499f8d  mov     rax, [rcx]
0x180499f90  mov     rax, [rax+10h]
0x180499f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499f99  test    r14d, r14d
0x180499f9c  jz      loc_180499E51
0x180499fa2  test    ebx, ebx
0x180499fa4  js      loc_180499EAC
0x180499faa  mov     [rbp+3Fh+var_80], rdi
0x180499fae  mov     rcx, rdi
0x180499fb1  mov     rax, [rdi]
0x180499fb4  mov     rax, [rax+8]
0x180499fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180499fbd  jmp     loc_180499E55
0x180499fc2  test    eax, eax
0x180499fc4  jz      loc_180499F1E
0x180499fca  jmp     loc_180499EE8
0x180499fcf  test    r15, r15
0x180499fd2  jnz     loc_180499EA4
0x180499fd8  mov     rcx, rsi; this
0x180499fdb  call    ?GetMarkupForBaseUrl@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupForBaseUrl(void)
0x180499fe0  mov     r15, rax
0x180499fe3  test    rax, rax
0x180499fe6  jnz     loc_180499EA4
0x180499fec  mov     rcx, rsi; this
0x180499fef  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180499ff4  test    rax, rax
0x180499ff7  jz      loc_180499EA4
0x180499ffd  mov     rcx, rax; this
0x18049a000  call    ?PrimaryMarkup@CDoc@@QEBAPEAVCMarkup@@XZ; CDoc::PrimaryMarkup(void)
0x18049a005  mov     r15, rax
0x18049a008  jmp     loc_180499EA4
0x18049a00d  test    r12d, r12d
0x18049a010  jz      loc_180499E41
0x18049a016  jmp     loc_180499E0F
0x18049a01b  test    r15, r15
0x18049a01e  jz      loc_180499EAC
0x18049a024  mov     rcx, r15; struct CMarkup *
0x18049a027  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x18049a02c  mov     rdi, rax
0x18049a02f  mov     dword ptr [rsp+30h], 0; dwReserved
0x18049a037  xor     r8d, r8d; dwQueryFlags
0x18049a03a  lea     rax, [rbp+3Fh+var_50]
0x18049a03e  mov     [rsp+0E0h+pcbBuffer], rax; pcbBuffer
0x18049a043  lea     r9, [rbp+3Fh+pvBuffer]; pvBuffer
0x18049a047  mov     rcx, rdi; pwzUrl
0x18049a04a  mov     dword ptr [rsp+0E0h+dwReserved], 4; cbBuffer
0x18049a052  lea     edx, [r8+6]; QueryOptions
0x18049a056  call    cs:__imp_CoInternetQueryInfo
0x18049a05c  test    eax, eax
0x18049a05e  jnz     loc_180499EAC
0x18049a064  cmp     [rbp+3Fh+pvBuffer], eax
0x18049a067  jz      loc_180499EAC
0x18049a06d  xor     ecx, ecx
0x18049a06f  mov     [rbp+3Fh+ppCombinedUri], rcx
0x18049a073  test    rdi, rdi
0x18049a076  jz      short loc_18049A09B
0x18049a078  lea     r9, [rbp+3Fh+ppCombinedUri]; ppURI
0x18049a07c  xor     r8d, r8d; dwReserved
0x18049a07f  mov     edx, 3002B84h; dwFlags
0x18049a084  mov     rcx, rdi; pwzURI
0x18049a087  call    cs:__imp_CreateUri
0x18049a08d  mov     ebx, eax
0x18049a08f  test    eax, eax
0x18049a091  js      loc_180499EAC
0x18049a097  mov     rcx, [rbp+3Fh+ppCombinedUri]; pBaseUri
0x18049a09b  mov     rdi, [r14]
0x18049a09e  mov     r9, r14; ppCombinedUri
0x18049a0a1  mov     rdx, rdi; pRelativeUri
0x18049a0a4  mov     [rsp+0E0h+dwReserved], 0; dwReserved
0x18049a0ad  mov     r8d, r12d; dwCombineFlags
0x18049a0b0  call    cs:__imp_CoInternetCombineIUri
0x18049a0b6  mov     rcx, [rbp+3Fh+ppCombinedUri]
0x18049a0ba  mov     ebx, eax
0x18049a0bc  test    rcx, rcx
0x18049a0bf  jz      short loc_18049A0CD
0x18049a0c1  mov     rax, [rcx]
0x18049a0c4  mov     rax, [rax+10h]
0x18049a0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18049a0cd  test    rdi, rdi
0x18049a0d0  jz      loc_180499EAC
0x18049a0d6  mov     rax, [rdi]
0x18049a0d9  mov     rcx, rdi
0x18049a0dc  mov     rax, [rax+10h]
0x18049a0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18049a0e5  jmp     loc_180499EAC
0x18049a0ea  lea     rax, [rsi-1]
0x18049a0ee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18049a0f2  ja      loc_180499DA5
0x18049a0f8  mov     rcx, rsi; this
0x18049a0fb  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x18049a100  mov     rdi, rax
0x18049a103  test    rax, rax
0x18049a106  jz      loc_180499D61
  ... truncated ...
```
