# tpm12class::TPMW8_SESSION::Validate(tpm12class::TpmDataObject *)

- ea: `0x1800413c0`
- end: `0x1800420c7`
- name: `?Validate@TPMW8_SESSION@tpm12class@@UEAAJPEAVTpmDataObject@2@@Z`
- size: `3335`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_SESSION *__hidden this, struct tpm12class::TpmDataObject *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800123f0`
- `0x1800413c0`
- `0x180042910`
- `0x18004ce90`
- `0x1800769e0`
- `0x180076e70`
- `0x180077028`
- `0x180077034`
- `0x18007704c`
- `0x18009c84c`
- `0x1800ba830`
- `0x1800be3bc`
- `0x1800c8010`

## string_xrefs

- `0x180041ff6`: `computedAuthorization`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_SESSION::Validate(
        tpm12class::TPMW8_SESSION *this,
        struct tpm12class::TpmDataObject *a2)
{
  int v4; // edi
  __int16 *v5; // r15
  __int64 v6; // rcx
  unsigned int v7; // eax
  char *v8; // r13
  __int16 v9; // di
  bool v10; // zf
  STRSAFE_LPWSTR v11; // rax
  _DWORD *v12; // r13
  void *v13; // rcx
  void *v14; // rax
  size_t v15; // r8
  size_t v16; // r15
  char *v17; // rdx
  __int64 v18; // rcx
  __int16 *v19; // r8
  __int64 v20; // rcx
  unsigned int v21; // eax
  char *v22; // r14
  __int16 v23; // di
  void *v24; // rcx
  void *v25; // rax
  size_t v26; // r8
  size_t v27; // r14
  unsigned int *v28; // rdi
  void *v29; // rcx
  void *v30; // rax
  size_t v31; // r8
  unsigned int v32; // eax
  int v33; // edi
  int v34; // eax
  int v35; // ecx
  int v36; // ecx
  void *v37; // rcx
  void *v38; // rax
  size_t v39; // r8
  unsigned __int8 *v40; // rcx
  int v41; // eax
  void *v42; // rcx
  void *v43; // rax
  size_t v44; // r8
  int v45; // ecx
  void *v46; // rcx
  void *v47; // rax
  size_t v48; // r8
  int v50; // ecx
  void *v51; // r9
  unsigned int v52; // ecx
  _BYTE *v53; // rdi
  char v54; // r14
  const void *v55; // r15
  unsigned int v56; // ecx
  unsigned int v57; // eax
  char *v58; // r12
  _BYTE *v59; // rax
  _BYTE *v60; // rax
  const void *v61; // rdi
  unsigned int v62; // ecx
  unsigned int v63; // eax
  int v64; // edx
  unsigned __int16 *v65; // rax
  size_t v66; // r14
  _BYTE *v67; // rax
  __int64 v68; // rcx
  int v69; // edx
  int v70; // r13d
  unsigned int v71; // edi
  _BYTE *v72; // rcx
  __int64 v73; // rax
  int v74; // ecx
  unsigned __int16 *v75; // rax
  size_t v76; // r8
  unsigned __int16 *v77; // r13
  _BYTE *v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rcx
  int v82; // ecx
  int v83; // ecx
  int Buffer; // eax
  unsigned __int16 *v85; // rdi
  int v86; // eax
  unsigned __int16 *v87; // rbx
  unsigned __int64 v88[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v89; // [rsp+A0h] [rbp+40h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v91; // [rsp+B8h] [rbp+58h] BYREF

  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 12) + 24LL))((char *)this + 96, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 48) + 24LL))((char *)this + 384, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = (__int16 *)((char *)this + 152);
  *((_BYTE *)a2 + 48) = 1;
  if ( this == (tpm12class::TPMW8_SESSION *)-152LL )
    return (unsigned int)-2147024809;
  v6 = *((unsigned int *)a2 + 6);
  v7 = *((_DWORD *)a2 + 4);
  if ( v7 >= (unsigned int)v6 && v7 - (unsigned int)v6 >= 2 )
  {
    v4 = 0;
    *v5 = __ROR2__(*(_WORD *)(*((_QWORD *)a2 + 1) + v6), 8);
    *((_DWORD *)a2 + 6) += 2;
    if ( *((_BYTE *)a2 + 48) )
      goto LABEL_10;
    v8 = (char *)*((_QWORD *)a2 + 4);
    v9 = *v5;
    if ( v8 )
    {
      if ( (unsigned __int64)*((unsigned int *)a2 + 10) + 2 < *((unsigned int *)a2 + 11) )
      {
LABEL_9:
        *(_WORD *)&v8[*((unsigned int *)a2 + 10)] = __ROR2__(v9, 8);
        *((_DWORD *)a2 + 10) += 2;
        v4 = 0;
        goto LABEL_10;
      }
    }
    else
    {
      *((_QWORD *)a2 + 5) = 0;
    }
    v8 = (char *)operator new((unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memset_0(v8, 0, (unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memcpy_0(v8, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
    v59 = (_BYTE *)*((_QWORD *)a2 + 4);
    if ( v59 )
    {
      v80 = *((unsigned int *)a2 + 10);
      if ( *((_DWORD *)a2 + 10) )
      {
        do
        {
          *v59++ = 0;
          --v80;
        }
        while ( v80 );
      }
      operator delete(*((void **)a2 + 4));
    }
    *((_QWORD *)a2 + 4) = v8;
    *((_DWORD *)a2 + 11) += 512;
    goto LABEL_9;
  }
  v4 = -2147024774;
LABEL_10:
  if ( v4 < 0 )
    return (unsigned int)v4;
  v10 = *v5 == 0;
  v11 = (STRSAFE_LPWSTR)((char *)a2 + 24);
  pszDest = (STRSAFE_LPWSTR)((char *)a2 + 24);
  v12 = (_DWORD *)((char *)a2 + 24);
  if ( !v10 )
  {
    v13 = (void *)*((_QWORD *)this + 20);
    if ( v13 )
    {
      operator delete(v13);
      *((_QWORD *)this + 20) = 0;
    }
    v14 = operator new((unsigned __int16)*v5);
    v15 = (unsigned __int16)*v5;
    *((_QWORD *)this + 20) = v14;
    memset_0(v14, 0, v15);
    v16 = (unsigned __int16)*v5;
    v4 = 0;
    if ( !(_DWORD)v16 )
      goto LABEL_15;
    v61 = (const void *)*((_QWORD *)this + 20);
    if ( !v61 )
      return (unsigned int)-2147024809;
    v62 = *((_DWORD *)a2 + 6);
    v63 = *((_DWORD *)a2 + 4);
    if ( v63 < v62 || v63 - v62 < (unsigned int)v16 )
    {
      v4 = -2147024774;
      goto LABEL_15;
    }
    memcpy_0(*((void **)this + 20), (const void *)(*((_QWORD *)a2 + 1) + v62), v16);
    *((_DWORD *)a2 + 6) += v16;
    if ( *((_BYTE *)a2 + 48) )
    {
      v4 = 0;
      pszDest = (STRSAFE_LPWSTR)((char *)a2 + 24);
LABEL_15:
      if ( v4 < 0 )
        return (unsigned int)v4;
      v11 = pszDest;
      goto LABEL_17;
    }
    v91 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
    if ( v91 )
    {
      v64 = *((_DWORD *)a2 + 10);
      if ( (unsigned int)(v64 + v16) < *((_DWORD *)a2 + 11) )
      {
        v65 = v91;
        pszDest = (STRSAFE_LPWSTR)((char *)a2 + 24);
        v66 = v16;
LABEL_129:
        memcpy_0((char *)v65 + *((unsigned int *)a2 + 10), v61, v66);
        *((_DWORD *)a2 + 10) += v16;
        v4 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      *((_QWORD *)a2 + 5) = 0;
      v64 = 0;
    }
    v74 = *((_DWORD *)a2 + 11);
    LODWORD(v89) = ((v64 + v16 - v74) & 0xFFFFFE00) + 512;
    v75 = (unsigned __int16 *)operator new((unsigned int)(v89 + v74));
    v76 = (unsigned int)(v89 + *((_DWORD *)a2 + 11));
    v77 = v75;
    v91 = v75;
    memset_0(v75, 0, v76);
    memcpy_0(v77, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
    v78 = (_BYTE *)*((_QWORD *)a2 + 4);
    v12 = (_DWORD *)((char *)a2 + 24);
    pszDest = (STRSAFE_LPWSTR)((char *)a2 + 24);
    if ( v78 )
    {
      v79 = *((unsigned int *)a2 + 10);
      if ( *((_DWORD *)a2 + 10) )
      {
        v66 = v16;
        do
        {
          *v78++ = 0;
          --v79;
        }
        while ( v79 );
      }
      else
      {
        pszDest = (STRSAFE_LPWSTR)((char *)a2 + 24);
        v66 = v16;
      }
      operator delete(*((void **)a2 + 4));
    }
    else
    {
      v66 = v16;
    }
    v65 = v91;
    v82 = v89;
    *((_QWORD *)a2 + 4) = v91;
    *((_DWORD *)a2 + 11) += v82;
    goto LABEL_129;
  }
LABEL_17:
  v17 = (char *)this + 764;
  if ( this == (tpm12class::TPMW8_SESSION *)-764LL )
    return (unsigned int)-2147024809;
  v18 = *(unsigned int *)v11;
  if ( *((_DWORD *)a2 + 4) > (unsigned int)v18 )
  {
    v4 = 0;
    *v17 = *(_BYTE *)(v18 + *((_QWORD *)a2 + 1));
    ++*v12;
    if ( *((_BYTE *)a2 + 48) )
      goto LABEL_20;
    v53 = (_BYTE *)*((_QWORD *)a2 + 4);
    v54 = *v17;
    if ( v53 )
    {
      if ( (unsigned __int64)*((unsigned int *)a2 + 10) + 1 < *((unsigned int *)a2 + 11) )
      {
LABEL_74:
        v53[(*((_DWORD *)a2 + 10))++] = v54;
        v4 = 0;
        goto LABEL_20;
      }
    }
    else
    {
      *((_QWORD *)a2 + 5) = 0;
    }
    v53 = operator new((unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memset_0(v53, 0, (unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memcpy_0(v53, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
    v67 = (_BYTE *)*((_QWORD *)a2 + 4);
    if ( v67 )
    {
      v68 = *((unsigned int *)a2 + 10);
      if ( *((_DWORD *)a2 + 10) )
      {
        do
        {
          *v67++ = 0;
          --v68;
        }
        while ( v68 );
      }
      operator delete(*((void **)a2 + 4));
    }
    *((_QWORD *)a2 + 4) = v53;
    *((_DWORD *)a2 + 11) += 512;
    goto LABEL_74;
  }
  v4 = -2147024774;
LABEL_20:
  if ( v4 < 0 )
    return (unsigned int)v4;
  v19 = (__int16 *)((char *)this + 584);
  if ( this == (tpm12class::TPMW8_SESSION *)-584LL )
    return (unsigned int)-2147024809;
  v20 = *((unsigned int *)a2 + 6);
  v21 = *((_DWORD *)a2 + 4);
  if ( v21 >= (unsigned int)v20 && v21 - (unsigned int)v20 >= 2 )
  {
    v4 = 0;
    *v19 = __ROR2__(*(_WORD *)(*((_QWORD *)a2 + 1) + v20), 8);
    *((_DWORD *)a2 + 6) += 2;
    if ( *((_BYTE *)a2 + 48) )
      goto LABEL_28;
    v22 = (char *)*((_QWORD *)a2 + 4);
    v23 = *v19;
    if ( v22 )
    {
      if ( (unsigned __int64)*((unsigned int *)a2 + 10) + 2 < *((unsigned int *)a2 + 11) )
      {
LABEL_27:
        *(_WORD *)&v22[*((unsigned int *)a2 + 10)] = __ROR2__(v23, 8);
        *((_DWORD *)a2 + 10) += 2;
        v4 = 0;
        goto LABEL_28;
      }
    }
    else
    {
      *((_QWORD *)a2 + 5) = 0;
    }
    v22 = (char *)operator new((unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memset_0(v22, 0, (unsigned int)(*((_DWORD *)a2 + 11) + 512));
    memcpy_0(v22, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
    v60 = (_BYTE *)*((_QWORD *)a2 + 4);
    if ( v60 )
    {
      v81 = *((unsigned int *)a2 + 10);
      if ( *((_DWORD *)a2 + 10) )
      {
        do
        {
          *v60++ = 0;
          --v81;
        }
        while ( v81 );
      }
      operator delete(*((void **)a2 + 4));
    }
    *((_QWORD *)a2 + 4) = v22;
    *((_DWORD *)a2 + 11) += 512;
    goto LABEL_27;
  }
  v4 = -2147024774;
LABEL_28:
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( *((_WORD *)this + 292) )
  {
    v24 = (void *)*((_QWORD *)this + 74);
    if ( v24 )
    {
      operator delete(v24);
      *((_QWORD *)this + 74) = 0;
    }
    v25 = operator new(*((unsigned __int16 *)this + 292));
    v26 = *((unsigned __int16 *)this + 292);
    *((_QWORD *)this + 74) = v25;
    memset_0(v25, 0, v26);
    v27 = *((unsigned __int16 *)this + 292);
    v4 = 0;
    if ( !*((_WORD *)this + 292) )
    {
LABEL_33:
      if ( v4 < 0 )
        return (unsigned int)v4;
      goto LABEL_34;
    }
    v55 = (const void *)*((_QWORD *)this + 74);
    if ( !v55 )
      return (unsigned int)-2147024809;
    v56 = *((_DWORD *)a2 + 6);
    v57 = *((_DWORD *)a2 + 4);
    if ( v57 < v56 || v57 - v56 < (unsigned int)v27 )
    {
      v4 = -2147024774;
      goto LABEL_33;
    }
    memcpy_0(*((void **)this + 74), (const void *)(*((_QWORD *)a2 + 1) + v56), *((unsigned __int16 *)this + 292));
    *((_DWORD *)a2 + 6) += v27;
    if ( *((_BYTE *)a2 + 48) )
      goto LABEL_33;
    v58 = (char *)*((_QWORD *)a2 + 4);
    if ( v58 )
    {
      if ( (unsigned int)(v27 + *((_DWORD *)a2 + 10)) < *((_DWORD *)a2 + 11) )
      {
LABEL_82:
        memcpy_0(&v58[*((unsigned int *)a2 + 10)], v55, v27);
        *((_DWORD *)a2 + 10) += v27;
        v4 = 0;
        goto LABEL_33;
      }
    }
    else
    {
      *((_QWORD *)a2 + 5) = 0;
    }
    v69 = *((_DWORD *)a2 + 11);
    v70 = *((_DWORD *)a2 + 10) + v27 - v69;
    v71 = (v70 & 0xFFFFFE00) + 512;
    v58 = (char *)operator new(v69 + v71);
    memset_0(v58, 0, v71 + *((_DWORD *)a2 + 11));
    memcpy_0(v58, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
    v72 = (_BYTE *)*((_QWORD *)a2 + 4);
    if ( v72 )
    {
      v73 = *((unsigned int *)a2 + 10);
      if ( *((_DWORD *)a2 + 10) )
      {
        do
        {
          *v72++ = 0;
          --v73;
        }
        while ( v73 );
      }
      operator delete(*((void **)a2 + 4));
    }
    *((_QWORD *)a2 + 4) = v58;
    *((_DWORD *)a2 + 11) += (v70 & 0xFFFFFE00) + 512;
    goto LABEL_82;
  }
LABEL_34:
  *((_BYTE *)a2 + 48) = 0;
  if ( *((_BYTE *)this + 760) )
    return (unsigned int)v4;
  if ( *((_BYTE *)this + 784) )
    return (unsigned int)v4;
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 21) + 24LL))((char *)this + 168, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v28 = (unsigned int *)((char *)this + 224);
  if ( this == (tpm12class::TPMW8_SESSION *)-224LL )
    return (unsigned int)-2147024809;
  *v28 = *((_DWORD *)a2 + 10);
  v29 = (void *)*((_QWORD *)this + 29);
  if ( v29 )
  {
    operator delete(v29);
    *((_QWORD *)this + 29) = 0;
  }
  v30 = operator new(*(unsigned __int16 *)v28);
  v31 = *(unsigned __int16 *)v28;
  *((_QWORD *)this + 29) = v30;
  memset_0(v30, 0, v31);
  v32 = *(unsigned __int16 *)v28;
  if ( *(_WORD *)v28 )
  {
    v51 = (void *)*((_QWORD *)this + 29);
    if ( !v51 )
      return (unsigned int)-2147024809;
    v52 = *((_DWORD *)a2 + 10);
    *v28 = v52;
    if ( v32 < v52 )
      return (unsigned int)-2147024774;
    memcpy_0(v51, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
  }
  else
  {
    *v28 = *((_DWORD *)a2 + 10);
  }
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 39) + 24LL))((char *)this + 312, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( this == (tpm12class::TPMW8_SESSION *)-368LL )
    return (unsigned int)-2147024809;
  v33 = -1073741822;
  if ( !g_fpHash )
  {
    v35 = -1073741822;
LABEL_139:
    v36 = v35 | 0x10000000;
    goto LABEL_47;
  }
  v34 = g_fpHash(
          *((unsigned __int16 **)this + 1),
          *((unsigned __int8 **)a2 + 4),
          *((_DWORD *)a2 + 10),
          0,
          0,
          0,
          0,
          (unsigned int *)this + 92,
          0);
  v35 = v34;
  if ( !v34 )
  {
    v36 = 0;
    goto LABEL_47;
  }
  if ( (v34 & 0xFFFF000) == 0x290000 )
  {
    v36 = v34 & 0xFFF | 0x80280000;
    goto LABEL_47;
  }
  if ( (v34 & 0xFFF0000) != 0x70000 )
    goto LABEL_139;
  v36 = (unsigned __int16)v34 | 0x80070000;
  if ( !(_WORD)v34 )
    v36 = 0;
LABEL_47:
  if ( v36 < 0 )
    return (unsigned int)v36;
  v37 = (void *)*((_QWORD *)this + 47);
  if ( v37 )
  {
    operator delete(v37);
    *((_QWORD *)this + 47) = 0;
  }
  v38 = operator new(*((unsigned __int16 *)this + 184));
  v39 = *((unsigned __int16 *)this + 184);
  *((_QWORD *)this + 47) = v38;
  memset_0(v38, 0, v39);
  v40 = (unsigned __int8 *)*((_QWORD *)this + 47);
  if ( *((_WORD *)this + 184) && !v40 )
    return (unsigned int)-2147024809;
  if ( !g_fpHash )
    goto LABEL_146;
  v41 = g_fpHash(
          *((unsigned __int16 **)this + 1),
          *((unsigned __int8 **)a2 + 4),
          *((_DWORD *)a2 + 10),
          0,
          0,
          v40,
          *((unsigned __int16 *)this + 184),
          (unsigned int *)this + 92,
          0);
  v33 = v41;
  if ( !v41 )
  {
    v4 = 0;
    goto LABEL_55;
  }
  if ( (v41 & 0xFFFF000) == 0x290000 )
  {
    v4 = v41 & 0xFFF | 0x80280000;
    goto LABEL_55;
  }
  if ( (v41 & 0xFFF0000) != 0x70000 )
  {
LABEL_146:
    v4 = v33 | 0x10000000;
    goto LABEL_55;
  }
  v4 = (unsigned __int16)v41 | 0x80070000;
  if ( !(_WORD)v41 )
    v4 = 0;
LABEL_55:
  if ( v4 < 0 )
    return (unsigned int)v4;
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 30) + 24LL))((char *)this + 240, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v42 = (void *)*((_QWORD *)this + 38);
  *((_WORD *)this + 148) = *((_WORD *)this + 184) + *((_WORD *)this + 40) + *((_WORD *)this + 76) + 1;
  if ( v42 )
  {
    operator delete(v42);
    *((_QWORD *)this + 38) = 0;
  }
  v43 = operator new(*((unsigned __int16 *)this + 148));
  v44 = *((unsigned __int16 *)this + 148);
  *((_QWORD *)this + 38) = v43;
  memset_0(v43, 0, v44);
  memcpy_0(*((void **)this + 38), *((const void **)this + 47), *((unsigned __int16 *)this + 184));
  memcpy_0(
    (void *)(*((_QWORD *)this + 38) + *((unsigned __int16 *)this + 184)),
    *((const void **)this + 20),
    *((unsigned __int16 *)this + 76));
  memcpy_0(
    (void *)(*((_QWORD *)this + 38)
           + *((unsigned __int16 *)this + 184)
           + (unsigned __int64)*((unsigned __int16 *)this + 76)),
    *((const void **)this + 11),
    *((unsigned __int16 *)this + 40));
  *(_BYTE *)(*((unsigned __int16 *)this + 184)
           + *((unsigned __int16 *)this + 40)
           + (unsigned __int64)*((unsigned __int16 *)this + 76)
           + *((_QWORD *)this + 38)) = *((_BYTE *)this + 764);
  v45 = *((unsigned __int16 *)this + 381);
  if ( v45 == 11 )
  {
    *((_WORD *)this + 220) = 32;
LABEL_61:
    v46 = (void *)*((_QWORD *)this + 56);
    if ( v46 )
    {
      operator delete(v46);
      *((_QWORD *)this + 56) = 0;
    }
    v47 = operator new(*((unsigned __int16 *)this + 220));
    v48 = *((unsigned __int16 *)this + 220);
    *((_QWORD *)this + 56) = v47;
    memset_0(v47, 0, v48);
    v4 = tpm12class::TPMW8_AUTH_PROVIDER::SymSign(
           *((tpm12class::TPMW8_AUTH_PROVIDER **)this + 97),
           1u,
           (tpm12class::TPMW8_SESSION *)((char *)this + 312),
           (tpm12class::TPMW8_SESSION *)((char *)this + 96),
           (tpm12class::TPMW8_SESSION *)((char *)this + 24),
           *((_BYTE *)this + 764),
           (tpm12class::TPMW8_SESSION *)((char *)this + 384));
    if ( v4 >= 0
      && (*((_WORD *)this + 292) != *((_WORD *)this + 220)
       || memcmp_0(*((const void **)this + 74), *((const void **)this + 56), *((unsigned __int16 *)this + 292))) )
    {
      v91 = 0;
      pszDest = 0;
      v88[0] = 0;
      v89 = 0;
      while ( 1 )
      {
        Buffer = TracepGetBuffer(&v91, &pszDest, v88, &v89);
        v85 = v91;
        if ( Buffer < 0 )
          break;
        if ( (unsigned int)StringCchPrintfExW(
                             pszDest,
                             v89,
                             &pszDest,
                             &v89,
                             0,
                             L"%s",
                             L"Session authorization validation failure:\r\n") != -2147024774 )
        {
          PlatformFlushTrace(v85, v88[0] - v89);
          break;
        }
      }
      PlatformFreeMemory(v85);
      v4 = TraceBufferValue(
             L"Validation failure: ",
             L"computedAuthorization",
             *((unsigned __int8 **)this + 56),
             *((unsigned __int16 *)this + 220));
      if ( v4 >= 0 )
      {
        v4 = TraceBufferValue(
               L"Validation failure: ",
               L"responseAuthorization",
               *((unsigned __int8 **)this + 74),
               *((unsigned __int16 *)this + 292));
        if ( v4 >= 0 )
        {
          v91 = 0;
          pszDest = 0;
          v88[0] = 0;
          v89 = 0;
          while ( 1 )
          {
            v86 = TracepGetBuffer(&v91, &pszDest, v88, &v89);
            v87 = v91;
            if ( v86 < 0 )
              break;
            if ( (unsigned int)StringCchPrintfExW(pszDest, v89, &pszDest, &v89, 0, L"%s", L"\r\n") != -2147024774 )
            {
              PlatformFlushTrace(v87, v88[0] - v89);
              break;
            }
          }
          PlatformFreeMemory(v87);
          return 2147942413LL;
        }
      }
    }
    return (unsigned int)v4;
  }
  v50 = v45 - 4;
  if ( !v50 )
  {
    *((_WORD *)this + 220) = 20;
    goto LABEL_61;
  }
  v83 = v50 - 8;
  if ( !v83 )
  {
    *((_WORD *)this + 220) = 48;
    goto LABEL_61;
  }
  if ( v83 == 1 )
  {
    *((_WORD *)this + 220) = 64;
    goto LABEL_61;
  }
  return 2147942413LL;
}

```

## disassembly

```asm
0x1800413c0  mov     [rsp-38h+arg_8], rbx
0x1800413c5  push    rbp
0x1800413c6  push    rsi
0x1800413c7  push    rdi
0x1800413c8  push    r12
0x1800413ca  push    r13
0x1800413cc  push    r14
0x1800413ce  push    r15
0x1800413d0  mov     rbp, rsp
0x1800413d3  sub     rsp, 60h
0x1800413d7  mov     rax, [rcx+60h]
0x1800413db  mov     rbx, rcx
0x1800413de  add     rcx, 60h ; '`'
0x1800413e2  mov     rsi, rdx
0x1800413e5  xor     edx, edx
0x1800413e7  mov     rax, [rax+18h]
0x1800413eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413f0  mov     edi, eax
0x1800413f2  test    eax, eax
0x1800413f4  js      loc_18004199A
0x1800413fa  lea     rcx, [rbx+180h]
0x180041401  xor     edx, edx
0x180041403  mov     rax, [rcx]
0x180041406  mov     rax, [rax+18h]
0x18004140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004140f  mov     edi, eax
0x180041411  test    eax, eax
0x180041413  js      loc_18004199A
0x180041419  lea     r15, [rbx+98h]
0x180041420  mov     byte ptr [rsi+30h], 1
0x180041424  test    r15, r15
0x180041427  jz      loc_180041A2D
0x18004142d  mov     ecx, [rsi+18h]
0x180041430  lea     r14, [rsi+18h]
0x180041434  mov     eax, [rsi+10h]
0x180041437  cmp     eax, ecx
0x180041439  jb      loc_180041DF6
0x18004143f  sub     eax, ecx
0x180041441  cmp     eax, 2
0x180041444  jb      loc_180041DF6
0x18004144a  mov     rax, [rsi+8]
0x18004144e  xor     edi, edi
0x180041450  movzx   edx, word ptr [rax+rcx]
0x180041454  ror     dx, 8
0x180041458  mov     [r15], dx
0x18004145c  add     dword ptr [r14], 2
0x180041460  cmp     [rsi+30h], dil
0x180041464  jnz     short loc_18004149C
0x180041466  mov     r13, [rsi+20h]
0x18004146a  movzx   edi, word ptr [r15]
0x18004146e  test    r13, r13
0x180041471  jz      loc_180041AB3
0x180041477  mov     ecx, [rsi+28h]
0x18004147a  mov     eax, [rsi+2Ch]
0x18004147d  add     rcx, 2
0x180041481  cmp     rcx, rax
0x180041484  jnb     loc_180041ABB
0x18004148a  mov     eax, [rsi+28h]
0x18004148d  ror     di, 8
0x180041491  mov     [rax+r13], di
0x180041496  add     dword ptr [rsi+28h], 2
0x18004149a  xor     edi, edi
0x18004149c  test    edi, edi
0x18004149e  js      loc_18004199A
0x1800414a4  cmp     word ptr [r15], 0
0x1800414a9  mov     rax, r14
0x1800414ac  mov     [rbp+pszDest], rax
0x1800414b0  mov     r13, r14
0x1800414b3  jz      short loc_1800414FE
0x1800414b5  mov     rcx, [rbx+0A0h]; Block
0x1800414bc  test    rcx, rcx
0x1800414bf  jnz     loc_180041E00
0x1800414c5  movzx   ecx, word ptr [r15]; Size
0x1800414c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800414ce  movzx   r8d, word ptr [r15]; Size
0x1800414d2  xor     edx, edx; Val
0x1800414d4  mov     rcx, rax; void *
0x1800414d7  mov     [rbx+0A0h], rax
0x1800414de  call    memset_0
0x1800414e3  movzx   r15d, word ptr [r15]
0x1800414e7  xor     edi, edi
0x1800414e9  test    r15d, r15d
0x1800414ec  jnz     loc_180041B69
0x1800414f2  test    edi, edi
0x1800414f4  js      loc_18004199A
0x1800414fa  mov     rax, [rbp+pszDest]
0x1800414fe  lea     rdx, [rbx+2FCh]
0x180041505  test    rdx, rdx
0x180041508  jz      loc_180041A2D
0x18004150e  mov     ecx, [rax]
0x180041510  mov     eax, [rsi+10h]
0x180041513  cmp     eax, ecx
0x180041515  jb      loc_180041E42
0x18004151b  sub     eax, ecx
0x18004151d  cmp     eax, 1
0x180041520  jb      loc_180041E42
0x180041526  mov     rax, [rsi+8]
0x18004152a  xor     edi, edi
0x18004152c  movzx   ecx, byte ptr [rcx+rax]
0x180041530  mov     [rdx], cl
0x180041532  inc     dword ptr [r13+0]
0x180041536  cmp     [rsi+30h], dil
0x18004153a  jz      loc_1800419F9
0x180041540  test    edi, edi
0x180041542  js      loc_18004199A
0x180041548  lea     r8, [rbx+248h]
0x18004154f  test    r8, r8
0x180041552  jz      loc_180041A2D
0x180041558  mov     ecx, [rsi+18h]
0x18004155b  mov     eax, [rsi+10h]
0x18004155e  cmp     eax, ecx
0x180041560  jb      loc_180041E4C
0x180041566  sub     eax, ecx
0x180041568  cmp     eax, 2
0x18004156b  jb      loc_180041E4C
0x180041571  mov     rax, [rsi+8]
0x180041575  xor     edi, edi
0x180041577  movzx   edx, word ptr [rax+rcx]
0x18004157b  ror     dx, 8
0x18004157f  mov     [r8], dx
0x180041583  add     dword ptr [rsi+18h], 2
0x180041587  cmp     [rsi+30h], dil
0x18004158b  jnz     short loc_1800415C3
0x18004158d  mov     r14, [rsi+20h]
0x180041591  movzx   edi, word ptr [r8]
0x180041595  test    r14, r14
0x180041598  jz      loc_180041B0E
0x18004159e  mov     ecx, [rsi+28h]
0x1800415a1  mov     eax, [rsi+2Ch]
0x1800415a4  add     rcx, 2
0x1800415a8  cmp     rcx, rax
0x1800415ab  jnb     loc_180041B16
0x1800415b1  mov     eax, [rsi+28h]
0x1800415b4  ror     di, 8
0x1800415b8  mov     [rax+r14], di
0x1800415bd  add     dword ptr [rsi+28h], 2
0x1800415c1  xor     edi, edi
0x1800415c3  test    edi, edi
0x1800415c5  js      loc_18004199A
0x1800415cb  cmp     word ptr [rbx+248h], 0
0x1800415d3  jz      short loc_180041625
0x1800415d5  mov     rcx, [rbx+250h]; Block
0x1800415dc  test    rcx, rcx
0x1800415df  jnz     loc_180041E56
0x1800415e5  movzx   ecx, word ptr [rbx+248h]; Size
0x1800415ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800415f1  movzx   r8d, word ptr [rbx+248h]; Size
0x1800415f9  xor     edx, edx; Val
0x1800415fb  mov     rcx, rax; void *
0x1800415fe  mov     [rbx+250h], rax
0x180041605  call    memset_0
0x18004160a  movzx   r14d, word ptr [rbx+248h]
0x180041612  xor     edi, edi
0x180041614  test    r14d, r14d
0x180041617  jnz     loc_180041A37
0x18004161d  test    edi, edi
0x18004161f  js      loc_18004199A
0x180041625  mov     byte ptr [rsi+30h], 0
0x180041629  cmp     byte ptr [rbx+2F8h], 0
0x180041630  jnz     loc_18004199A
0x180041636  cmp     byte ptr [rbx+310h], 0
0x18004163d  jnz     loc_18004199A
0x180041643  lea     rcx, [rbx+0A8h]
0x18004164a  xor     edx, edx
0x18004164c  mov     rax, [rcx]
0x18004164f  mov     rax, [rax+18h]
0x180041653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041658  mov     edi, eax
0x18004165a  test    eax, eax
0x18004165c  js      loc_18004199A
0x180041662  lea     rdi, [rbx+0E0h]
0x180041669  test    rdi, rdi
0x18004166c  jz      loc_180041A2D
0x180041672  mov     eax, [rsi+28h]
0x180041675  mov     [rdi], eax
0x180041677  mov     rcx, [rbx+0E8h]; Block
0x18004167e  test    rcx, rcx
0x180041681  jnz     loc_180041E6B
0x180041687  xor     r13d, r13d
0x18004168a  movzx   ecx, word ptr [rdi]; Size
0x18004168d  lea     r15, [rsi+28h]
0x180041691  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041696  movzx   r8d, word ptr [rdi]; Size
0x18004169a  xor     edx, edx; Val
0x18004169c  mov     rcx, rax; void *
0x18004169f  mov     [rbx+0E8h], rax
0x1800416a6  call    memset_0
0x1800416ab  movzx   eax, word ptr [rdi]
0x1800416ae  test    eax, eax
0x1800416b0  jnz     loc_1800419CC
0x1800416b6  mov     eax, [rsi+28h]
0x1800416b9  mov     [rdi], eax
0x1800416bb  lea     rcx, [rbx+138h]
0x1800416c2  xor     edx, edx
0x1800416c4  mov     rax, [rcx]
0x1800416c7  mov     rax, [rax+18h]
0x1800416cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416d0  mov     edi, eax
0x1800416d2  test    eax, eax
0x1800416d4  js      loc_18004199A
0x1800416da  lea     rcx, [rbx+170h]
0x1800416e1  test    rcx, rcx
0x1800416e4  jz      loc_180041A2D
0x1800416ea  mov     rax, cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x1800416f1  mov     edi, 0C0000002h
0x1800416f6  test    rax, rax
0x1800416f9  jz      loc_180041EBF
0x1800416ff  mov     r8d, [rsi+28h]
0x180041703  xor     r9d, r9d
0x180041706  mov     rdx, [rsi+20h]
0x18004170a  mov     [rsp+60h+var_20], r13d
0x18004170f  mov     [rsp+60h+var_28], rcx
0x180041714  mov     rcx, [rbx+8]
0x180041718  mov     dword ptr [rsp+60h+var_30], r13d
0x18004171d  mov     [rsp+60h+var_38], r13
0x180041722  mov     dword ptr [rsp+60h+var_40], r13d
0x180041727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004172c  mov     ecx, eax
0x18004172e  test    eax, eax
0x180041730  jnz     loc_180041E7F
0x180041736  mov     ecx, r13d
0x180041739  test    ecx, ecx
0x18004173b  js      loc_180041D95
0x180041741  mov     rcx, [rbx+178h]; Block
0x180041748  test    rcx, rcx
0x18004174b  jnz     loc_180041ECA
0x180041751  lea     r14, [rbx+170h]
0x180041758  movzx   ecx, word ptr [r14]; Size
0x18004175c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041761  movzx   r8d, word ptr [r14]; Size
0x180041765  xor     edx, edx; Val
0x180041767  mov     rcx, rax; void *
0x18004176a  mov     [rbx+178h], rax
0x180041771  call    memset_0
0x180041776  movzx   edx, word ptr [r14]
0x18004177a  mov     rcx, [rbx+178h]
0x180041781  test    edx, edx
0x180041783  jz      short loc_18004178E
0x180041785  test    rcx, rcx
0x180041788  jz      loc_180041A2D
0x18004178e  mov     rax, cs:?g_fpHash@@3P6AJPEAGPEAEI1I1IPEAIK@ZEA; long (*g_fpHash)(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)
0x180041795  test    rax, rax
0x180041798  jz      loc_180041F1B
0x18004179e  mov     r8d, [rsi+28h]
0x1800417a2  xor     r9d, r9d
0x1800417a5  mov     [rsp+60h+var_20], r13d
0x1800417aa  mov     [rsp+60h+var_28], r14
0x1800417af  mov     dword ptr [rsp+60h+var_30], edx
0x1800417b3  mov     rdx, [rsi+20h]
0x1800417b7  mov     [rsp+60h+var_38], rcx
0x1800417bc  mov     rcx, [rbx+8]
0x1800417c0  mov     dword ptr [rsp+60h+var_40], r13d
0x1800417c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417ca  mov     edi, eax
0x1800417cc  test    eax, eax
0x1800417ce  jnz     loc_180041EDB
0x1800417d4  mov     edi, r13d
0x1800417d7  test    edi, edi
0x1800417d9  js      loc_18004199A
0x1800417df  lea     rcx, [rbx+0F0h]
0x1800417e6  xor     edx, edx
0x1800417e8  mov     rax, [rcx]
0x1800417eb  mov     rax, [rax+18h]
0x1800417ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417f4  mov     edi, eax
0x1800417f6  test    eax, eax
0x1800417f8  js      loc_18004199A
0x1800417fe  movzx   eax, word ptr [rbx+98h]
0x180041805  mov     rcx, [rbx+130h]; Block
0x18004180c  inc     ax
0x18004180f  add     ax, [rbx+50h]
0x180041813  add     ax, [rbx+170h]
0x18004181a  mov     [rbx+128h], ax
0x180041821  test    rcx, rcx
0x180041824  jnz     loc_180041F24
0x18004182a  movzx   ecx, word ptr [rbx+128h]; Size
0x180041831  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041836  movzx   r8d, word ptr [rbx+128h]; Size
0x18004183e  xor     edx, edx; Val
0x180041840  mov     rcx, rax; void *
0x180041843  mov     [rbx+130h], rax
0x18004184a  call    memset_0
0x18004184f  movzx   r8d, word ptr [rbx+170h]; Size
0x180041857  mov     rdx, [rbx+178h]; Src
0x18004185e  mov     rcx, [rbx+130h]; void *
0x180041865  call    memcpy_0
0x18004186a  movzx   ecx, word ptr [rbx+170h]
0x180041871  add     rcx, [rbx+130h]; void *
0x180041878  movzx   r8d, word ptr [rbx+98h]; Size
0x180041880  mov     rdx, [rbx+0A0h]; Src
0x180041887  call    memcpy_0
0x18004188c  movzx   ecx, word ptr [rbx+98h]
0x180041893  movzx   eax, word ptr [rbx+170h]
0x18004189a  movzx   r8d, word ptr [rbx+50h]; Size
0x18004189f  add     rcx, rax
0x1800418a2  add     rcx, [rbx+130h]; void *
0x1800418a9  mov     rdx, [rbx+58h]; Src
0x1800418ad  call    memcpy_0
0x1800418b2  movzx   eax, word ptr [rbx+50h]
0x1800418b6  movzx   edx, word ptr [rbx+98h]
  ... truncated ...
```
