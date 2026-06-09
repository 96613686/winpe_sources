# CMapi2AttachFilter::GetValue(tagPROPVARIANT * *)

- ea: `0x180026f00`
- end: `0x180027816`
- name: `?GetValue@CMapi2AttachFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `2326`
- prototype: `__int64 __fastcall(LARGE_INTEGER *this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002300`
- `0x180002714`
- `0x180011884`
- `0x180013fac`
- `0x180014420`
- `0x180014448`
- `0x1800149cc`
- `0x180017a64`
- `0x180017afc`
- `0x180018a20`
- `0x180018ae4`
- `0x180020d2c`
- `0x180021ae4`
- `0x180025a1c`
- `0x180026e94`
- `0x180026f00`
- `0x180028428`
- `0x1800289a4`
- `0x180028ad8`
- `0x18003a060`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002763f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002767b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002774b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002763f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002767b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800276f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002774b`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180027488`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180027488`

## string_xrefs

- `0x1800274ea`: `communication`
- `0x180027542`: `communication`

## pseudocode

```c
__int64 __fastcall CMapi2AttachFilter::GetValue(LARGE_INTEGER *this, struct tagPROPVARIANT **a2)
{
  wchar_t v5; // dx
  unsigned int LowPart; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  _QWORD *v13; // rax
  struct tagPROPVARIANT *v14; // rax
  LARGE_INTEGER *v15; // rdx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  const wchar_t *v23; // rdx
  const wchar_t *QuadPart; // rcx
  int v25; // edi
  int v26; // eax
  wchar_t **v27; // rcx
  int v28; // eax
  _QWORD *v29; // rax
  wchar_t v30; // dx
  int v31; // eax
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  _QWORD *v39; // rax
  struct tagPROPVARIANT *v40; // rax
  struct tagPROPVARIANT *v41; // rax
  LARGE_INTEGER v42; // rax
  struct tagPROPVARIANT *v43; // rax
  int v44; // eax
  __int64 v45; // rcx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  __int64 v53; // rcx
  LARGE_INTEGER v54; // rcx
  struct tagPROPVARIANT *v55; // rax
  LONG v56; // eax
  struct tagPROPVARIANT *v57; // rax
  struct tagPROPVARIANT *v58; // rax
  struct tagPROPVARIANT *v59; // rax
  struct tagPROPVARIANT *v60; // rax
  struct tagPROPVARIANT *v61; // rax
  int v62; // eax
  __int64 v63; // rcx
  unsigned int v64; // ebx
  unsigned int v65; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t **v67[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v69[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v70; // [rsp+74h] [rbp-8Ch]
  _QWORD v71[2]; // [rsp+880h] [rbp+780h] BYREF
  int v72; // [rsp+894h] [rbp+794h]
  wchar_t v73[1028]; // [rsp+898h] [rbp+798h] BYREF
  _BYTE pvData[528]; // [rsp+10A0h] [rbp+FA0h] BYREF

  if ( !a2 )
    return 2147500035LL;
  TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v69, &byte_1800444C0);
  LowPart = this[2124].LowPart;
  this[2124].LowPart = LowPart + 1;
  if ( LowPart <= 0x11 )
  {
    if ( LowPart == 17 )
    {
      if ( !this[1046].HighPart )
        goto LABEL_114;
      QuadPart = (const wchar_t *)this[1045].QuadPart;
    }
    else
    {
      if ( LowPart <= 8 )
      {
        if ( LowPart == 8 )
        {
LABEL_15:
          v13 = (_QWORD *)CMapiUrl::AttachmentName((__int64)&this[5], (__int64)v67);
          CLMString::operator=(v69, *v13);
          ATL::CStringData::Release((ATL::CStringData *)(v67[0] - 3));
LABEL_60:
          v28 = SetStringValue(a2, v69);
          goto LABEL_61;
        }
        if ( LowPart )
        {
          v7 = LowPart - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              v9 = v8 - 1;
              if ( v9 )
              {
                v10 = v9 - 1;
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    v12 = v11 - 1;
                    if ( v12 )
                    {
                      if ( v12 == 1 )
                        goto LABEL_15;
                      goto LABEL_91;
                    }
LABEL_59:
                    v39 = (_QWORD *)CMapiUrl::AttachmentName((__int64)&this[5], (__int64)v67);
                    CLMString::operator=(v69, *v39);
                    ATL::CStringData::Release((ATL::CStringData *)(v67[0] - 3));
                    (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v69[0] + 32LL))(
                      v69,
                      L" (",
                      (unsigned int)v70,
                      0xFFFFFFFFLL);
                    CLMString::operator+=(v69, &this[328]);
                    (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v69[0] + 32LL))(
                      v69,
                      L")",
                      (unsigned int)v70,
                      0xFFFFFFFFLL);
                    goto LABEL_60;
                  }
                  goto LABEL_16;
                }
                v15 = this + 224;
              }
              else
              {
                v15 = this + 172;
              }
            }
            else
            {
              v15 = this + 120;
            }
          }
          else
          {
            v15 = this + 68;
          }
        }
        else
        {
          v15 = this + 16;
        }
LABEL_23:
        CLMString::operator=(v69, v15);
        goto LABEL_60;
      }
      v16 = LowPart - 9;
      if ( !v16 )
      {
        v29 = (_QWORD *)CMapiUrl::AttachmentName((__int64)&this[5], (__int64)v67);
        TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v71, *v29);
        ATL::CStringData::Release((ATL::CStringData *)(v67[0] - 3));
        v31 = CLMString::ReverseFind((CLMString *)v71, v30);
        if ( v31 < 0 )
        {
          CLMString::operator=(v69, L".");
        }
        else
        {
          CLMString::Mid(v71, Block, (unsigned int)v31, (unsigned int)(v72 - v31));
          CLMString::operator=(v69, Block);
        }
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v71);
        goto LABEL_60;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
LABEL_16:
        v14 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
        *a2 = v14;
        if ( v14 )
        {
          *(_OWORD *)&v14->vt = 0;
          v14->bstrblobVal.pData = 0;
          (*a2)->vt = 11;
          (*a2)->iVal = -1;
          goto LABEL_114;
        }
LABEL_112:
        v25 = -2147024882;
        goto LABEL_115;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        v15 = this + 380;
        goto LABEL_23;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        v15 = this + 416;
        goto LABEL_23;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v67[0] = (wchar_t **)this[453].QuadPart;
        v28 = SetMultiStringValue(a2, 1u, (const wchar_t **)v67);
LABEL_61:
        v25 = v28;
        goto LABEL_115;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v15 = this + 488;
        goto LABEL_23;
      }
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 == 1 )
        {
          v23 = (const wchar_t *)this[785].QuadPart;
LABEL_33:
          CLMString::operator=(v69, v23);
          goto LABEL_60;
        }
LABEL_91:
        v53 = *(_QWORD *)CTPtrSListIterator<CValChunk>::GetCurrentValue(&this[2132]);
        if ( !v53 )
        {
          v54 = this[3];
          if ( !v54.QuadPart )
          {
            TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v69);
            return 2147500037LL;
          }
          v28 = (*(__int64 (__fastcall **)(LARGE_INTEGER, struct tagPROPVARIANT **))(*(_QWORD *)v54.QuadPart + 48LL))(
                  v54,
                  a2);
          goto LABEL_61;
        }
        *a2 = *(struct tagPROPVARIANT **)(v53 + 72);
        *(_QWORD *)(v53 + 72) = 0;
LABEL_114:
        v25 = 0;
        goto LABEL_115;
      }
      if ( !this[526].HighPart )
        goto LABEL_114;
      QuadPart = (const wchar_t *)this[525].QuadPart;
    }
LABEL_36:
    Block[0] = 0;
    v65 = 0;
    v25 = ConvertNameListToStringArray(QuadPart, (wchar_t ***)Block, &v65);
    if ( v25 >= 0 )
    {
      v26 = SetMultiStringValue(a2, v65, (const wchar_t **)Block[0]);
      v27 = (wchar_t **)Block[0];
LABEL_38:
      v25 = v26;
      operator delete(v27);
      goto LABEL_115;
    }
    goto LABEL_115;
  }
  if ( LowPart <= 0x1A )
  {
    if ( LowPart == 26 )
    {
      pcbData = 520;
      LODWORD(Block[0]) = 1;
      v44 = CLMString::ReverseFind((CLMString *)&this[16], v5);
      if ( v44 >= 0 )
      {
        CLMString::Mid(v45, v67, (unsigned int)v44, (unsigned int)(*(_DWORD *)(v45 + 20) - v44));
        CLMString::CLMString((CLMString *)v71, 0x401u, v73, (const struct CLMSubStr *)v67);
        v71[0] = &TLMString<1024,1024,1048576>::`vftable';
        if ( v72
          && !SHGetValueW(
                HKEY_LOCAL_MACHINE,
                L"software\\microsoft\\windows\\currentversion\\explorer\\kindmap",
                (LPCWSTR)v71[1],
                (DWORD *)Block,
                pvData,
                &pcbData) )
        {
          CLMString::operator=(v69, pvData);
        }
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v71);
      }
      if ( !(_DWORD)v70 )
      {
        TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v71, L"communication");
        v25 = SetStringValue(a2, v71);
        TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v71);
        goto LABEL_115;
      }
      (*(void (__fastcall **)(_QWORD *, const wchar_t *, __int64, __int64))(v69[0] + 32LL))(
        v69,
        L";",
        v70,
        0xFFFFFFFFLL);
      (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v69[0] + 32LL))(
        v69,
        L"communication",
        (unsigned int)v70,
        0xFFFFFFFFLL);
      v67[0] = 0;
      v65 = 0;
      v25 = ConvertNameListToStringArray((const wchar_t *)v69[1], v67, &v65);
      if ( v25 >= 0 )
      {
        v26 = SetMultiStringValue(a2, v65, (const wchar_t **)v67[0]);
        v27 = v67[0];
        goto LABEL_38;
      }
LABEL_115:
      TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v69);
      return (unsigned int)v25;
    }
    v32 = LowPart - 18;
    if ( !v32 )
    {
      v23 = (const wchar_t *)this[1305].QuadPart;
      goto LABEL_33;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      if ( !this[1566].HighPart )
        goto LABEL_114;
      QuadPart = (const wchar_t *)this[1565].QuadPart;
      goto LABEL_36;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      v23 = (const wchar_t *)this[1825].QuadPart;
      goto LABEL_33;
    }
    v35 = v34 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( !v36 )
      {
        v15 = this + 2084;
        goto LABEL_23;
      }
      v37 = v36 - 1;
      if ( v37 )
      {
        v38 = v37 - 1;
        if ( !v38 )
        {
          v40 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
          *a2 = v40;
          if ( v40 )
          {
            *(_OWORD *)&v40->vt = 0;
            v40->bstrblobVal.pData = 0;
            (*a2)->vt = 64;
            (*a2)->hVal = this[2123];
            goto LABEL_114;
          }
          goto LABEL_112;
        }
        if ( v38 == 1 )
          goto LABEL_59;
        goto LABEL_91;
      }
      v41 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
      *a2 = v41;
      if ( !v41 )
        goto LABEL_112;
      *(_OWORD *)&v41->vt = 0;
      v41->bstrblobVal.pData = 0;
      (*a2)->vt = 64;
      v42 = this[2122];
    }
    else
    {
      v43 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
      *a2 = v43;
      if ( !v43 )
        goto LABEL_112;
      *(_OWORD *)&v43->vt = 0;
      v43->bstrblobVal.pData = 0;
      (*a2)->vt = 64;
      v42 = this[2120];
    }
LABEL_69:
    (*a2)->hVal = v42;
    TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v69);
    return 0;
  }
  v46 = LowPart - 27;
  if ( v46 )
  {
    v47 = v46 - 1;
    if ( !v47 )
    {
      v61 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
      *a2 = v61;
      if ( v61 )
      {
        *(_OWORD *)&v61->vt = 0;
        v61->bstrblobVal.pData = 0;
        (*a2)->vt = 21;
        (*a2)->hVal.QuadPart = (unsigned int)this[2124].HighPart;
        goto LABEL_114;
      }
      goto LABEL_112;
    }
    v48 = v47 - 1;
    if ( v48 )
    {
      v49 = v48 - 1;
      if ( !v49 )
      {
        v59 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
        *a2 = v59;
        if ( v59 )
        {
          *(_OWORD *)&v59->vt = 0;
          v59->bstrblobVal.pData = 0;
          (*a2)->vt = 0;
          goto LABEL_114;
        }
        goto LABEL_112;
      }
      v50 = v49 - 1;
      if ( v50 )
      {
        v51 = v50 - 1;
        if ( !v51 )
        {
          v57 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
          *a2 = v57;
          if ( v57 )
          {
            *(_OWORD *)&v57->vt = 0;
            v57->bstrblobVal.pData = 0;
            (*a2)->vt = 11;
            (*a2)->iVal = -(this[2125].HighPart != 0);
            goto LABEL_114;
          }
          goto LABEL_112;
        }
        v52 = v51 - 1;
        if ( v52 )
        {
          if ( v52 == 1 )
          {
            v23 = L"hidden";
            if ( (this[2125].LowPart & 0x80000) == 0 )
              v23 = L"normal";
            goto LABEL_33;
          }
          goto LABEL_91;
        }
        if ( !this[2126].LowPart )
          goto LABEL_114;
        v55 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
        *a2 = v55;
        if ( !v55 )
          goto LABEL_112;
        *(_OWORD *)&v55->vt = 0;
        v55->bstrblobVal.pData = 0;
        (*a2)->vt = 19;
        v56 = this[2126].LowPart;
      }
      else
      {
        v58 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
        *a2 = v58;
        if ( !v58 )
          goto LABEL_112;
        *(_OWORD *)&v58->vt = 0;
        v58->bstrblobVal.pData = 0;
        (*a2)->vt = 19;
        v56 = this[2125].LowPart;
      }
      (*a2)->lVal = v56;
      goto LABEL_114;
    }
    v60 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
    *a2 = v60;
    if ( !v60 )
      goto LABEL_112;
    *(_OWORD *)&v60->vt = 0;
    v60->bstrblobVal.pData = 0;
    (*a2)->vt = 64;
    v42 = this[2121];
    goto LABEL_69;
  }
  v62 = CLMString::ReverseFind((CLMString *)&this[16], v5);
  if ( v62 < 0 )
  {
    CLMString::operator=(v69, L".");
  }
  else
  {
    CLMString::Mid(v63, v67, (unsigned int)v62, (unsigned int)(*(_DWORD *)(v63 + 20) - v62));
    CLMString::operator=(v69, v67);
  }
  v64 = SetStringValue(a2, v69);
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v69);
  return v64;
}

```

## disassembly

```asm
0x180026f00  mov     [rsp-8+arg_10], rbx
0x180026f05  push    rbp
0x180026f06  push    rdi
0x180026f07  push    r14
0x180026f09  lea     rbp, [rsp-11C0h]
0x180026f11  mov     eax, 12C0h
0x180026f16  call    _alloca_probe
0x180026f1b  sub     rsp, rax
0x180026f1e  mov     rax, cs:__security_cookie
0x180026f25  xor     rax, rsp
0x180026f28  mov     [rbp+11D0h+var_20], rax
0x180026f2f  mov     rbx, rdx
0x180026f32  mov     rdi, rcx
0x180026f35  xor     r14d, r14d
0x180026f38  test    rdx, rdx
0x180026f3b  jnz     short loc_180026F47
0x180026f3d  mov     eax, 80004003h
0x180026f42  jmp     loc_1800277F3
0x180026f47  lea     rdx, byte_1800444C0
0x180026f4e  lea     rcx, [rsp+12D0h+var_1270]
0x180026f53  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEBD@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(char const *)
0x180026f58  nop
0x180026f59  mov     ecx, [rdi+4260h]
0x180026f5f  lea     eax, [rcx+1]
0x180026f62  mov     [rdi+4260h], eax
0x180026f68  cmp     ecx, 11h
0x180026f6b  ja      loc_180027206
0x180026f71  jz      loc_1800271ED
0x180026f77  cmp     ecx, 8
0x180026f7a  ja      loc_180027068
0x180026f80  jz      short loc_180026FC5
0x180026f82  test    ecx, ecx
0x180026f84  jz      loc_180027052
0x180026f8a  sub     ecx, 1
0x180026f8d  jz      loc_180027049
0x180026f93  sub     ecx, 1
0x180026f96  jz      loc_180027040
0x180026f9c  sub     ecx, 1
0x180026f9f  jz      loc_180027037
0x180026fa5  sub     ecx, 1
0x180026fa8  jz      loc_18002702E
0x180026fae  sub     ecx, 1
0x180026fb1  jz      short loc_180026FF5
0x180026fb3  sub     ecx, 1
0x180026fb6  jz      loc_18002725D
0x180026fbc  cmp     ecx, 1
0x180026fbf  jnz     loc_1800275B7
0x180026fc5  lea     rcx, [rdi+28h]
0x180026fc9  lea     rdx, [rsp+12D0h+var_1288]
0x180026fce  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x180026fd3  nop
0x180026fd4  mov     rdx, [rax]
0x180026fd7  lea     rcx, [rsp+12D0h+var_1270]
0x180026fdc  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180026fe1  nop
0x180026fe2  mov     rcx, [rsp+12D0h+var_1288]
0x180026fe7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180026feb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026ff0  jmp     loc_1800272DF
0x180026ff5  mov     ecx, 18h; cb
0x180026ffa  call    cs:__imp_CoTaskMemAlloc
0x180027000  mov     [rbx], rax
0x180027003  test    rax, rax
0x180027006  jz      loc_180027759
0x18002700c  xorps   xmm0, xmm0
0x18002700f  xor     ecx, ecx
0x180027011  movups  xmmword ptr [rax], xmm0
0x180027014  mov     [rax+10h], rcx
0x180027018  mov     rax, [rbx]
0x18002701b  mov     word ptr [rax], 0Bh
0x180027020  mov     rax, [rbx]
0x180027023  mov     word ptr [rax+8], 0FFFFh
0x180027029  jmp     loc_180027781
0x18002702e  lea     rdx, [rdi+700h]
0x180027035  jmp     short loc_180027059
0x180027037  lea     rdx, [rdi+560h]
0x18002703e  jmp     short loc_180027059
0x180027040  lea     rdx, [rdi+3C0h]
0x180027047  jmp     short loc_180027059
0x180027049  lea     rdx, [rdi+220h]
0x180027050  jmp     short loc_180027059
0x180027052  lea     rdx, [rdi+80h]
0x180027059  lea     rcx, [rsp+12D0h+var_1270]
0x18002705e  call    ??4CLMString@@QEAAXAEBV0@@Z; CLMString::operator=(CLMString const &)
0x180027063  jmp     loc_1800272DF
0x180027068  sub     ecx, 9
0x18002706b  jz      loc_18002715E
0x180027071  sub     ecx, 1
0x180027074  jz      loc_180026FF5
0x18002707a  sub     ecx, 1
0x18002707d  jz      loc_180027152
0x180027083  sub     ecx, 1
0x180027086  jz      loc_180027146
0x18002708c  sub     ecx, 1
0x18002708f  jz      loc_180027123
0x180027095  sub     ecx, 1
0x180027098  jz      short loc_180027117
0x18002709a  sub     ecx, 1
0x18002709d  jz      short loc_1800270BE
0x18002709f  cmp     ecx, 1
0x1800270a2  jnz     loc_1800275B7
0x1800270a8  mov     rdx, [rdi+1888h]
0x1800270af  lea     rcx, [rsp+12D0h+var_1270]
0x1800270b4  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800270b9  jmp     loc_1800272DF
0x1800270be  cmp     [rdi+1074h], r14d
0x1800270c5  jz      loc_180027781
0x1800270cb  mov     rcx, [rdi+1068h]; wchar_t *
0x1800270d2  mov     [rsp+12D0h+Block], r14
0x1800270d7  mov     [rsp+12D0h+var_12A0], r14d
0x1800270dc  lea     r8, [rsp+12D0h+var_12A0]; unsigned int *
0x1800270e1  lea     rdx, [rsp+12D0h+Block]; wchar_t ***
0x1800270e6  call    ?ConvertNameListToStringArray@@YAJPEB_WPEAPEAPEA_WPEAK@Z; ConvertNameListToStringArray(wchar_t const *,wchar_t * * *,ulong *)
0x1800270eb  mov     edi, eax
0x1800270ed  test    eax, eax
0x1800270ef  js      loc_180027784
0x1800270f5  mov     r8, [rsp+12D0h+Block]; wchar_t **
0x1800270fa  mov     edx, [rsp+12D0h+var_12A0]; unsigned int
0x1800270fe  mov     rcx, rbx; struct tagPROPVARIANT **
0x180027101  call    ?SetMultiStringValue@@YAJPEAPEAUtagPROPVARIANT@@KPEAPEB_W@Z; SetMultiStringValue(tagPROPVARIANT * *,ulong,wchar_t const * *)
0x180027106  mov     rcx, [rsp+12D0h+Block]; Block
0x18002710b  mov     edi, eax
0x18002710d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027112  jmp     loc_180027784
0x180027117  lea     rdx, [rdi+0F40h]
0x18002711e  jmp     loc_180027059
0x180027123  mov     rax, [rdi+0E28h]
0x18002712a  mov     [rsp+12D0h+var_1288], rax
0x18002712f  lea     r8, [rsp+12D0h+var_1288]; wchar_t **
0x180027134  mov     edx, 1; unsigned int
0x180027139  mov     rcx, rbx; struct tagPROPVARIANT **
0x18002713c  call    ?SetMultiStringValue@@YAJPEAPEAUtagPROPVARIANT@@KPEAPEB_W@Z; SetMultiStringValue(tagPROPVARIANT * *,ulong,wchar_t const * *)
0x180027141  jmp     loc_1800272EC
0x180027146  lea     rdx, [rdi+0D00h]
0x18002714d  jmp     loc_180027059
0x180027152  lea     rdx, [rdi+0BE0h]
0x180027159  jmp     loc_180027059
0x18002715e  lea     rcx, [rdi+28h]
0x180027162  lea     rdx, [rsp+12D0h+var_1288]
0x180027167  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x18002716c  nop
0x18002716d  mov     rdx, [rax]
0x180027170  lea     rcx, [rbp+11D0h+var_A50]
0x180027177  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEB_W@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(wchar_t const *)
0x18002717c  nop
0x18002717d  mov     rcx, [rsp+12D0h+var_1288]
0x180027182  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027186  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002718b  lea     rcx, [rbp+11D0h+var_A50]; this
0x180027192  call    ?ReverseFind@CLMString@@QEBAH_W@Z; CLMString::ReverseFind(wchar_t)
0x180027197  test    eax, eax
0x180027199  js      short loc_1800271CA
0x18002719b  mov     r9d, [rbp+11D0h+var_A3C]
0x1800271a2  sub     r9d, eax
0x1800271a5  mov     r8d, eax
0x1800271a8  lea     rdx, [rsp+12D0h+Block]
0x1800271ad  lea     rcx, [rbp+11D0h+var_A50]
0x1800271b4  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x1800271b9  lea     rdx, [rsp+12D0h+Block]
0x1800271be  lea     rcx, [rsp+12D0h+var_1270]
0x1800271c3  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x1800271c8  jmp     short loc_1800271DC
0x1800271ca  lea     rdx, asc_180048F04; "."
0x1800271d1  lea     rcx, [rsp+12D0h+var_1270]
0x1800271d6  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800271db  nop
0x1800271dc  lea     rcx, [rbp+11D0h+var_A50]
0x1800271e3  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x1800271e8  jmp     loc_1800272DF
0x1800271ed  cmp     [rdi+20B4h], r14d
0x1800271f4  jz      loc_180027781
0x1800271fa  mov     rcx, [rdi+20A8h]
0x180027201  jmp     loc_1800270D2
0x180027206  cmp     ecx, 1Ah
0x180027209  ja      loc_180027577
0x18002720f  jz      loc_1800273EC
0x180027215  sub     ecx, 12h
0x180027218  jz      loc_1800273E0
0x18002721e  sub     ecx, 1
0x180027221  jz      loc_1800273C7
0x180027227  sub     ecx, 1
0x18002722a  jz      loc_1800273BB
0x180027230  sub     ecx, 1
0x180027233  jz      loc_180027371
0x180027239  sub     ecx, 1
0x18002723c  jz      loc_180027365
0x180027242  sub     ecx, 1
0x180027245  jz      loc_180027331
0x18002724b  sub     ecx, 1
0x18002724e  jz      loc_1800272F3
0x180027254  cmp     ecx, 1
0x180027257  jnz     loc_1800275B7
0x18002725d  lea     rcx, [rdi+28h]
0x180027261  lea     rdx, [rsp+12D0h+var_1288]
0x180027266  call    ?AttachmentName@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::AttachmentName(void)
0x18002726b  nop
0x18002726c  mov     rdx, [rax]
0x18002726f  lea     rcx, [rsp+12D0h+var_1270]
0x180027274  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180027279  nop
0x18002727a  mov     rcx, [rsp+12D0h+var_1288]
0x18002727f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027283  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027288  mov     rax, [rsp+12D0h+var_1270]
0x18002728d  or      r9d, 0FFFFFFFFh
0x180027291  mov     r8d, dword ptr [rsp+12D0h+var_125C]
0x180027296  lea     rdx, asc_180048EF8; " ("
0x18002729d  lea     rcx, [rsp+12D0h+var_1270]
0x1800272a2  mov     rax, [rax+20h]
0x1800272a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272ab  lea     rdx, [rdi+0A40h]
0x1800272b2  lea     rcx, [rsp+12D0h+var_1270]
0x1800272b7  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x1800272bc  mov     rax, [rsp+12D0h+var_1270]
0x1800272c1  or      r9d, 0FFFFFFFFh
0x1800272c5  mov     r8d, dword ptr [rsp+12D0h+var_125C]
0x1800272ca  lea     rdx, asc_180048F00; ")"
0x1800272d1  lea     rcx, [rsp+12D0h+var_1270]
0x1800272d6  mov     rax, [rax+20h]
0x1800272da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272df  lea     rdx, [rsp+12D0h+var_1270]
0x1800272e4  mov     rcx, rbx
0x1800272e7  call    ?SetStringValue@@YAJPEAPEAUtagPROPVARIANT@@AEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@Z; SetStringValue(tagPROPVARIANT * *,TLMString<1024,1024,1048576> &)
0x1800272ec  mov     edi, eax
0x1800272ee  jmp     loc_180027784
0x1800272f3  mov     ecx, 18h; cb
0x1800272f8  call    cs:__imp_CoTaskMemAlloc
0x1800272fe  mov     [rbx], rax
0x180027301  test    rax, rax
0x180027304  jz      loc_180027759
0x18002730a  xorps   xmm0, xmm0
0x18002730d  xor     ecx, ecx
0x18002730f  movups  xmmword ptr [rax], xmm0
0x180027312  mov     [rax+10h], rcx
0x180027316  mov     rax, [rbx]
0x180027319  mov     word ptr [rax], 40h ; '@'
0x18002731e  mov     rcx, [rbx]
0x180027321  mov     rax, [rdi+4258h]
0x180027328  mov     [rcx+8], rax
0x18002732c  jmp     loc_180027781
0x180027331  mov     ecx, 18h; cb
0x180027336  call    cs:__imp_CoTaskMemAlloc
0x18002733c  mov     [rbx], rax
0x18002733f  test    rax, rax
0x180027342  jz      loc_180027759
0x180027348  xorps   xmm0, xmm0
0x18002734b  xor     ecx, ecx
0x18002734d  movups  xmmword ptr [rax], xmm0
0x180027350  mov     [rax+10h], rcx
0x180027354  mov     rax, [rbx]
0x180027357  mov     word ptr [rax], 40h ; '@'
0x18002735c  mov     rax, [rdi+4250h]
0x180027363  jmp     short loc_1800273A3
0x180027365  lea     rdx, [rdi+4120h]
0x18002736c  jmp     loc_180027059
0x180027371  mov     ecx, 18h; cb
0x180027376  call    cs:__imp_CoTaskMemAlloc
0x18002737c  mov     [rbx], rax
0x18002737f  test    rax, rax
0x180027382  jz      loc_180027759
0x180027388  xorps   xmm0, xmm0
0x18002738b  xor     ecx, ecx
0x18002738d  movups  xmmword ptr [rax], xmm0
0x180027390  mov     [rax+10h], rcx
0x180027394  mov     rax, [rbx]
0x180027397  mov     word ptr [rax], 40h ; '@'
0x18002739c  mov     rax, [rdi+4240h]
0x1800273a3  mov     rcx, [rbx]
0x1800273a6  mov     [rcx+8], rax
0x1800273aa  lea     rcx, [rsp+12D0h+var_1270]
0x1800273af  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x1800273b4  xor     eax, eax
0x1800273b6  jmp     loc_1800277F3
0x1800273bb  mov     rdx, [rdi+3908h]
0x1800273c2  jmp     loc_1800270AF
0x1800273c7  cmp     [rdi+30F4h], r14d
0x1800273ce  jz      loc_180027781
0x1800273d4  mov     rcx, [rdi+30E8h]
0x1800273db  jmp     loc_1800270D2
0x1800273e0  mov     rdx, [rdi+28C8h]
0x1800273e7  jmp     loc_1800270AF
0x1800273ec  mov     [rsp+12D0h+var_1278], 208h
0x1800273f4  mov     dword ptr [rsp+12D0h+Block], 1
0x1800273fc  lea     rcx, [rdi+80h]; this
0x180027403  call    ?ReverseFind@CLMString@@QEBAH_W@Z; CLMString::ReverseFind(wchar_t)
0x180027408  test    eax, eax
0x18002740a  js      loc_1800274B0
0x180027410  mov     r9d, [rcx+14h]
0x180027414  sub     r9d, eax
0x180027417  mov     r8d, eax
0x18002741a  lea     rdx, [rsp+12D0h+var_1288]
0x18002741f  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180027424  lea     r9, [rsp+12D0h+var_1288]; struct CLMSubStr *
0x180027429  lea     r8, [rbp+11D0h+var_A38]; wchar_t *
0x180027430  mov     edx, 401h; unsigned int
0x180027435  lea     rcx, [rbp+11D0h+var_A50]; this
0x18002743c  call    ??0CLMString@@IEAA@IPEA_WAEBVCLMSubStr@@@Z; CLMString::CLMString(uint,wchar_t *,CLMSubStr const &)
0x180027441  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180027448  mov     [rbp+11D0h+var_A50], rax
0x18002744f  cmp     [rbp+11D0h+var_A3C], r14d
  ... truncated ...
```
