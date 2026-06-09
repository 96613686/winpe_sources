# StructuredQuery1::ReadPROPVARIANT(IStream *,tagPROPVARIANT *)

- ea: `0x18003dc94`
- end: `0x18003e3e4`
- name: `?ReadPROPVARIANT@StructuredQuery1@@YAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z`
- size: `1872`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, struct IStream *, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003d210`
- `0x18003d820`
- `0x18003dc94`

## callees

- `0x18003bed0`
- `0x18003d398`
- `0x18003d6c4`
- `0x18003dc94`
- `0x18005bf14`
- `0x18005bfa8`
- `0x18005c60c`
- `0x18005e740`
- `0x18006749c`
- `0x18006bcd4`
- `0x18006bd54`
- `0x18006bed4`
- `0x18006bf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003de0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dfae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e1c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003de0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dfae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e1c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e2eb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dcb8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003ddd7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dec3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003df1f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dffa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e0e4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e18f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e2b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e330`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e37a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dcb8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003ddd7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dec3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003df1f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003dffa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e0e4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e18f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e2b4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e330`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003e37a`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadPROPVARIANT(
        StructuredQuery1 *this,
        struct IStream **a2,
        struct tagPROPVARIANT *a3)
{
  HRESULT PSTR; // ebx
  unsigned __int16 v6; // dx
  wchar_t **v7; // r8
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int IsEnabled; // eax
  GUID **v15; // rdx
  GUID *v16; // r9
  unsigned int *v18; // r14
  unsigned __int64 v19; // rcx
  struct IStream *v20; // rax
  struct IStream *v21; // rsi
  struct IStream *v22; // r14
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  bool v27; // cf
  IStream *v28; // rcx
  struct IStream *v29; // rdx
  struct IStream **v30; // r14
  unsigned __int64 v31; // rcx
  struct IStream *v32; // rax
  struct tagPROPVARIANT *v33; // r8
  struct IStream *v34; // rsi
  struct IStream *v35; // r14
  int PROPVARIANT; // eax
  struct IStream *v37; // rax
  struct tagPROPVARIANT *v38; // r8
  ULONG v39; // r8d
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int *v46; // r14
  struct IStream *v47; // rdx
  unsigned __int64 v48; // rcx
  struct IStream *v49; // rax
  wchar_t **v50; // r8
  struct IStream *v51; // rsi
  struct IStream *v52; // r14
  int PWSTR; // eax
  unsigned int *v54; // r14
  unsigned __int64 v55; // rcx
  struct IStream *v56; // rax
  struct IStream *v57; // rsi
  struct IStream *v58; // r14
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int *v66; // r14
  unsigned __int64 v67; // rcx
  struct IStream *v68; // rax
  struct IStream *v69; // rsi
  struct IStream *v70; // r14
  SIZE_T cb; // [rsp+58h] [rbp+28h] BYREF

  PSTR = IStream_Read(this, a2, 2u);
  if ( PSTR < 0 )
    return (unsigned int)PSTR;
  v6 = *(_WORD *)a2;
  *(_WORD *)a2 &= ~0x4000u;
  v7 = (wchar_t **)(v6 & 0xBFFF);
  if ( (v6 & 0x2000) != 0 )
    return (unsigned int)-2147467263;
  v8 = v6 & 0xFFF;
  if ( v8 == 4095 )
    goto LABEL_124;
  if ( v8 > 0x16 )
  {
    if ( v8 <= 0x40 )
    {
      if ( v8 == 64 )
        goto LABEL_64;
      if ( v8 > 0x1C )
      {
        v44 = v8 - 29;
        if ( !v44 )
          return (unsigned int)-2147467263;
        v45 = v44 - 1;
        if ( v45 )
        {
          if ( v45 != 1 )
            return (unsigned int)-2147467263;
          v46 = (unsigned int *)(a2 + 1);
          v27 = (v6 & 0x1000) != 0;
          v47 = (struct IStream *)(a2 + 1);
          if ( !v27 )
            return (unsigned int)StructuredQuery1::ReadPWSTR(this, v47, v7);
          PSTR = IStream_Read(this, v47, 4u);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v48 = *v46;
          cb = 0;
          PSTR = ULongLongMult(v48, 8u, &cb);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v49 = (struct IStream *)CoTaskMemAlloc(cb);
          a2[2] = v49;
          if ( v49 )
          {
            memset_0(v49, 0, cb);
            v51 = a2[2];
            v52 = (struct IStream *)((char *)v51 + 8 * *v46);
            do
            {
              if ( v51 == v52 )
                break;
              PWSTR = StructuredQuery1::ReadPWSTR(this, v51, v50);
              v51 = (struct IStream *)((char *)v51 + 8);
              PSTR = PWSTR;
            }
            while ( PWSTR >= 0 );
            return (unsigned int)PSTR;
          }
        }
        else
        {
          v54 = (unsigned int *)(a2 + 1);
          if ( (v6 & 0x1000) == 0 )
            return (unsigned int)StructuredQuery1::ReadPSTR(this);
          PSTR = IStream_Read(this, a2 + 1, 4u);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v55 = *v54;
          cb = 0;
          PSTR = ULongLongMult(v55, 8u, &cb);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v56 = (struct IStream *)CoTaskMemAlloc(cb);
          a2[2] = v56;
          if ( v56 )
          {
            memset_0(v56, 0, cb);
            v57 = a2[2];
            v58 = (struct IStream *)((char *)v57 + 8 * *v54);
            do
            {
              if ( v57 == v58 )
                break;
              v57 = (struct IStream *)((char *)v57 + 8);
              PSTR = StructuredQuery1::ReadPSTR(this);
            }
            while ( PSTR >= 0 );
            return (unsigned int)PSTR;
          }
        }
        return (unsigned int)-2147024882;
      }
      if ( v8 == 28 )
        return (unsigned int)-2147467263;
      v42 = v8 - 23;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( !v43 )
          return (unsigned int)PSTR;
        if ( v43 != 1 )
          return (unsigned int)-2147467263;
      }
      goto LABEL_76;
    }
    v59 = v8 - 65;
    if ( v59 )
    {
      v60 = v59 - 1;
      if ( !v60 )
        return (unsigned int)-2147467263;
      v61 = v60 - 1;
      if ( !v61 )
        return (unsigned int)-2147467263;
      v62 = v61 - 1;
      if ( !v62 )
        return (unsigned int)-2147467263;
      v63 = v62 - 1;
      if ( !v63 )
        return (unsigned int)-2147467263;
      v64 = v63 - 1;
      if ( v64 )
      {
        v65 = v64 - 1;
        if ( !v65 )
        {
          v66 = (unsigned int *)(a2 + 1);
          if ( (v6 & 0x1000) == 0 )
          {
            if ( *(_QWORD *)v66 )
            {
              PSTR = IStream_Read(this, (void *)(*(_QWORD *)v66 + 4LL), 4u);
              if ( PSTR >= 0 )
              {
                LODWORD(cb) = 0;
                StructuredQuery1::ReadBlob_unsigned_char_(this);
                **(_DWORD **)v66 = cb + 4;
              }
            }
            else
            {
              return (unsigned int)-2147024809;
            }
            return (unsigned int)PSTR;
          }
          PSTR = IStream_Read(this, a2 + 1, 4u);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v67 = *v66;
          cb = 0;
          PSTR = ULongLongMult(v67, 0x10u, &cb);
          if ( PSTR < 0 )
            return (unsigned int)PSTR;
          v68 = (struct IStream *)CoTaskMemAlloc(cb);
          a2[2] = v68;
          if ( v68 )
          {
            memset_0(v68, 0, cb);
            v69 = a2[2];
            v70 = (struct IStream *)((char *)v69 + 16 * *v66);
            while ( v69 != v70 )
            {
              PSTR = IStream_Read(this, (char *)v69 + 4, 4u);
              if ( PSTR < 0 )
                break;
              LODWORD(cb) = 0;
              StructuredQuery1::ReadBlob_unsigned_char_(this);
              *(_DWORD *)v69 = cb + 4;
              v69 = (struct IStream *)((char *)v69 + 16);
            }
            return (unsigned int)PSTR;
          }
          return (unsigned int)-2147024882;
        }
        if ( v65 != 1 )
          return (unsigned int)-2147467263;
        v28 = this;
        if ( (v6 & 0x1000) != 0 )
          return (unsigned int)StructuredQuery1::ReadBlob__GUID_(this);
        v29 = a2[1];
        v39 = 16;
        return (unsigned int)IStream_Read(v28, v29, v39);
      }
    }
LABEL_124:
    if ( (v6 & 0x1000) == 0 )
    {
      StructuredQuery1::ReadBlob_unsigned_char_(this);
      return (unsigned int)PSTR;
    }
    return (unsigned int)-2147467263;
  }
  if ( v8 == 22 )
    goto LABEL_76;
  if ( v8 > 0xA )
  {
    if ( v8 <= 0x11 )
    {
      if ( v8 != 17 )
      {
        v23 = v8 - 11;
        if ( !v23 )
          goto LABEL_66;
        v24 = v23 - 1;
        if ( !v24 )
        {
          v30 = a2 + 1;
          if ( (v6 & 0x1000) != 0 )
          {
            PSTR = IStream_Read(this, a2 + 1, 4u);
            if ( PSTR < 0 )
              return (unsigned int)PSTR;
            v31 = *(unsigned int *)v30;
            cb = 0;
            PSTR = ULongLongMult(v31, 0x18u, &cb);
            if ( PSTR < 0 )
              return (unsigned int)PSTR;
            v32 = (struct IStream *)CoTaskMemAlloc(cb);
            a2[2] = v32;
            if ( v32 )
            {
              memset_0(v32, 0, cb);
              v34 = a2[2];
              v35 = (struct IStream *)((char *)v34 + 24 * *(unsigned int *)v30);
              do
              {
                if ( v34 == v35 )
                  break;
                PROPVARIANT = StructuredQuery1::ReadPROPVARIANT(this, v34, v33);
                v34 = (struct IStream *)((char *)v34 + 24);
                PSTR = PROPVARIANT;
              }
              while ( PROPVARIANT >= 0 );
              return (unsigned int)PSTR;
            }
          }
          else
          {
            v37 = (struct IStream *)CoTaskMemAlloc(0x18u);
            *v30 = v37;
            if ( v37 )
            {
              *(_OWORD *)v37 = 0;
              *((_QWORD *)v37 + 2) = 0;
              PSTR = StructuredQuery1::ReadPROPVARIANT(this, *v30, v38);
              if ( PSTR >= 0 )
                *(_WORD *)a2 |= 0x4000u;
              return (unsigned int)PSTR;
            }
          }
          return (unsigned int)-2147024882;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl);
          v15 = off_180097280;
          if ( !(_BYTE)IsEnabled )
            v15 = off_1800972C0;
          v16 = &GUID_00000000_0000_0000_c000_000000000046;
          return (unsigned int)SQ_IUnknown_LoadKnownImplFromStream(
                                 this,
                                 (const struct _GUID *const *)v15,
                                 IsEnabled + 6,
                                 v16,
                                 a2 + 1);
        }
        v26 = v25 - 1;
        if ( !v26 )
        {
          PSTR = IStream_Read(this, a2, 0x10u);
          *(_WORD *)a2 = 14;
          return (unsigned int)PSTR;
        }
        if ( v26 != 2 )
          return (unsigned int)-2147467263;
      }
      v27 = (v6 & 0x1000) != 0;
      v28 = this;
      v29 = (struct IStream *)(a2 + 1);
      if ( v27 )
        return (unsigned int)StructuredQuery1::ReadBlob_unsigned_char_(this);
      v39 = 1;
      return (unsigned int)IStream_Read(v28, v29, v39);
    }
    v40 = v8 - 18;
    if ( !v40 )
      goto LABEL_66;
    v41 = v40 - 1;
    if ( v41 )
    {
      if ( v41 - 1 > 1 )
        return (unsigned int)-2147467263;
      goto LABEL_64;
    }
LABEL_76:
    v27 = (v6 & 0x1000) != 0;
    v28 = this;
    v29 = (struct IStream *)(a2 + 1);
    if ( v27 )
      return (unsigned int)StructuredQuery1::ReadBlob_long_(this);
    v39 = 4;
    return (unsigned int)IStream_Read(v28, v29, v39);
  }
  if ( v8 == 10 )
    goto LABEL_76;
  if ( v8 > 5 )
  {
    v11 = v8 - 6;
    if ( !v11 )
      goto LABEL_64;
    v12 = v11 - 1;
    if ( !v12 )
      goto LABEL_64;
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
        return (unsigned int)-2147467263;
      IsEnabled = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl'::`2'::impl);
      v15 = off_180097280;
      if ( !(_BYTE)IsEnabled )
        v15 = off_1800972C0;
      v16 = &GUID_00020400_0000_0000_c000_000000000046;
      return (unsigned int)SQ_IUnknown_LoadKnownImplFromStream(
                             this,
                             (const struct _GUID *const *)v15,
                             IsEnabled + 6,
                             v16,
                             a2 + 1);
    }
    v18 = (unsigned int *)(a2 + 1);
    if ( (v6 & 0x1000) == 0 )
      return (unsigned int)StructuredQuery1::ReadBSTR(this);
    PSTR = IStream_Read(this, a2 + 1, 4u);
    if ( PSTR < 0 )
      return (unsigned int)PSTR;
    v19 = *v18;
    cb = 0;
    PSTR = ULongLongMult(v19, 8u, &cb);
    if ( PSTR < 0 )
      return (unsigned int)PSTR;
    v20 = (struct IStream *)CoTaskMemAlloc(cb);
    a2[2] = v20;
    if ( v20 )
    {
      memset_0(v20, 0, cb);
      v21 = a2[2];
      v22 = (struct IStream *)((char *)v21 + 8 * *v18);
      do
      {
        if ( v21 == v22 )
          break;
        v21 = (struct IStream *)((char *)v21 + 8);
        PSTR = StructuredQuery1::ReadBSTR(this);
      }
      while ( PSTR >= 0 );
      return (unsigned int)PSTR;
    }
    return (unsigned int)-2147024882;
  }
  if ( v8 == 5 )
  {
LABEL_64:
    v27 = (v6 & 0x1000) != 0;
    v28 = this;
    v29 = (struct IStream *)(a2 + 1);
    if ( v27 )
      return (unsigned int)StructuredQuery1::ReadBlob_double_(this);
    v39 = 8;
    return (unsigned int)IStream_Read(v28, v29, v39);
  }
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 - 1 >= 2 )
          return (unsigned int)-2147467263;
        goto LABEL_76;
      }
LABEL_66:
      v27 = (v6 & 0x1000) != 0;
      v28 = this;
      v29 = (struct IStream *)(a2 + 1);
      if ( v27 )
        return (unsigned int)StructuredQuery1::ReadBlob_short_(this);
      v39 = 2;
      return (unsigned int)IStream_Read(v28, v29, v39);
    }
  }
  return (unsigned int)PSTR;
}

```

## disassembly

```asm
0x18003dc94  mov     [rsp-18h+arg_0], rbx
0x18003dc99  mov     [rsp-18h+arg_10], rsi
0x18003dc9e  push    rbp
0x18003dc9f  push    rdi
0x18003dca0  push    r14
0x18003dca2  mov     rbp, rsp
0x18003dca5  sub     rsp, 30h
0x18003dca9  mov     r14d, 2
0x18003dcaf  mov     rsi, rdx
0x18003dcb2  mov     r8d, r14d; cb
0x18003dcb5  mov     rdi, rcx
0x18003dcb8  call    cs:__imp_IStream_Read
0x18003dcbe  mov     ebx, eax
0x18003dcc0  test    eax, eax
0x18003dcc2  js      loc_18003E3CF
0x18003dcc8  movzx   edx, word ptr [rsi]
0x18003dccb  mov     eax, 0BFFFh
0x18003dcd0  movzx   ecx, dx
0x18003dcd3  and     cx, ax
0x18003dcd6  bt      cx, 0Dh
0x18003dcdb  mov     [rsi], cx
0x18003dcde  movzx   r8d, cx; wchar_t **
0x18003dce2  jnb     short loc_18003DCEE
0x18003dce4  mov     ebx, 80004001h
0x18003dce9  jmp     loc_18003E3CF
0x18003dcee  mov     eax, 0FFFh
0x18003dcf3  mov     ecx, r8d
0x18003dcf6  and     ecx, eax
0x18003dcf8  cmp     ecx, eax
0x18003dcfa  jz      loc_18003E3B4
0x18003dd00  cmp     ecx, 16h
0x18003dd03  ja      loc_18003E05A
0x18003dd09  jz      loc_18003E087
0x18003dd0f  cmp     ecx, 0Ah
0x18003dd12  ja      loc_18003DE67
0x18003dd18  jz      loc_18003E087
0x18003dd1e  cmp     ecx, 5
0x18003dd21  ja      short loc_18003DD57
0x18003dd23  jz      loc_18003E01F
0x18003dd29  test    ecx, ecx
0x18003dd2b  jz      loc_18003E3CF
0x18003dd31  sub     ecx, 1
0x18003dd34  jz      loc_18003E3CF
0x18003dd3a  sub     ecx, 1
0x18003dd3d  jz      loc_18003E03C
0x18003dd43  sub     ecx, 1
0x18003dd46  jz      loc_18003E087
0x18003dd4c  cmp     ecx, 1
0x18003dd4f  jz      loc_18003E087
0x18003dd55  jmp     short loc_18003DCE4
0x18003dd57  sub     ecx, 6
0x18003dd5a  jz      loc_18003E01F
0x18003dd60  sub     ecx, 1
0x18003dd63  jz      loc_18003E01F
0x18003dd69  sub     ecx, 1
0x18003dd6c  jz      short loc_18003DDBB
0x18003dd6e  cmp     ecx, 1
0x18003dd71  jnz     loc_18003DCE4
0x18003dd77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x18003dd7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x18003dd83  lea     r9, off_1800972C0
0x18003dd8a  movzx   eax, al
0x18003dd8d  test    al, al
0x18003dd8f  lea     rdx, off_180097280
0x18003dd96  cmovz   rdx, r9
0x18003dd9a  lea     r9, _GUID_00020400_0000_0000_c000_000000000046
0x18003dda1  lea     rcx, [rsi+8]
0x18003dda5  mov     [rsp+30h+var_10], rcx
0x18003ddaa  lea     r8d, [rax+6]
0x18003ddae  mov     rcx, rdi
0x18003ddb1  call    SQ_IUnknown_LoadKnownImplFromStream
0x18003ddb6  jmp     loc_18003E000
0x18003ddbb  bt      r8w, 0Ch
0x18003ddc1  mov     rcx, rdi; pstm
0x18003ddc4  lea     r14, [rsi+8]
0x18003ddc8  mov     rdx, r14; pv
0x18003ddcb  jnb     loc_18003DE5D
0x18003ddd1  mov     r8d, 4; cb
0x18003ddd7  call    cs:__imp_IStream_Read
0x18003dddd  mov     ebx, eax
0x18003dddf  test    eax, eax
0x18003dde1  js      loc_18003E3CF
0x18003dde7  mov     ecx, [r14]; unsigned __int64
0x18003ddea  lea     r8, [rbp+cb]; unsigned __int64 *
0x18003ddee  mov     edx, 8; unsigned __int64
0x18003ddf3  mov     [rbp+cb], 0
0x18003ddfb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003de00  mov     ebx, eax
0x18003de02  test    eax, eax
0x18003de04  js      loc_18003E3CF
0x18003de0a  mov     rcx, [rbp+cb]; cb
0x18003de0e  call    cs:__imp_CoTaskMemAlloc
0x18003de14  mov     [rsi+10h], rax
0x18003de18  test    rax, rax
0x18003de1b  jz      loc_18003DFEA
0x18003de21  mov     r8, [rbp+cb]; Size
0x18003de25  xor     edx, edx; Val
0x18003de27  mov     rcx, rax; void *
0x18003de2a  call    memset_0
0x18003de2f  mov     eax, [r14]
0x18003de32  mov     rsi, [rsi+10h]
0x18003de36  lea     r14, [rsi+rax*8]
0x18003de3a  cmp     rsi, r14
0x18003de3d  jz      loc_18003E3CF
0x18003de43  mov     rdx, rsi
0x18003de46  mov     rcx, rdi; pstm
0x18003de49  call    StructuredQuery1__ReadBSTR
0x18003de4e  add     rsi, 8
0x18003de52  mov     ebx, eax
0x18003de54  test    eax, eax
0x18003de56  jns     short loc_18003DE3A
0x18003de58  jmp     loc_18003E3CF
0x18003de5d  call    StructuredQuery1__ReadBSTR
0x18003de62  jmp     loc_18003E000
0x18003de67  cmp     ecx, 11h
0x18003de6a  ja      loc_18003E007
0x18003de70  jz      short loc_18003DE97
0x18003de72  sub     ecx, 0Bh
0x18003de75  jz      loc_18003E03C
0x18003de7b  sub     ecx, 1
0x18003de7e  jz      loc_18003DF04
0x18003de84  sub     ecx, 1
0x18003de87  jz      short loc_18003DED5
0x18003de89  sub     ecx, 1
0x18003de8c  jz      short loc_18003DEB7
0x18003de8e  cmp     ecx, r14d
0x18003de91  jnz     loc_18003DCE4
0x18003de97  bt      dx, 0Ch
0x18003de9c  mov     rcx, rdi; pstm
0x18003de9f  lea     rdx, [rsi+8]; pv
0x18003dea3  jnb     loc_18003DFF4
0x18003dea9  lea     r8, [rsi+10h]
0x18003dead  call    StructuredQuery1__ReadBlob_unsigned_char_
0x18003deb2  jmp     loc_18003E000
0x18003deb7  mov     r8d, 10h; cb
0x18003debd  mov     rdx, rsi; pv
0x18003dec0  mov     rcx, rdi; pstm
0x18003dec3  call    cs:__imp_IStream_Read
0x18003dec9  mov     ebx, eax
0x18003decb  mov     word ptr [rsi], 0Eh
0x18003ded0  jmp     loc_18003E3CF
0x18003ded5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45262758@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758> `wil::Feature<__WilFeatureTraits_Feature_FI45262758>::GetImpl(void)'::`2'::impl
0x18003dedc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45262758@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45262758>::__private_IsEnabled(void)
0x18003dee1  lea     r9, off_1800972C0
0x18003dee8  movzx   eax, al
0x18003deeb  test    al, al
0x18003deed  lea     rdx, off_180097280
0x18003def4  cmovz   rdx, r9
0x18003def8  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x18003deff  jmp     loc_18003DDA1
0x18003df04  bt      dx, 0Ch
0x18003df09  lea     r14, [rsi+8]
0x18003df0d  jnb     loc_18003DFA9
0x18003df13  mov     r8d, 4; cb
0x18003df19  mov     rdx, r14; pv
0x18003df1c  mov     rcx, rdi; pstm
0x18003df1f  call    cs:__imp_IStream_Read
0x18003df25  mov     ebx, eax
0x18003df27  test    eax, eax
0x18003df29  js      loc_18003E3CF
0x18003df2f  mov     ecx, [r14]; unsigned __int64
0x18003df32  lea     r8, [rbp+cb]; unsigned __int64 *
0x18003df36  mov     edx, 18h; unsigned __int64
0x18003df3b  mov     [rbp+cb], 0
0x18003df43  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003df48  mov     ebx, eax
0x18003df4a  test    eax, eax
0x18003df4c  js      loc_18003E3CF
0x18003df52  mov     rcx, [rbp+cb]; cb
0x18003df56  call    cs:__imp_CoTaskMemAlloc
0x18003df5c  mov     [rsi+10h], rax
0x18003df60  test    rax, rax
0x18003df63  jz      loc_18003DFEA
0x18003df69  mov     r8, [rbp+cb]; Size
0x18003df6d  xor     edx, edx; Val
0x18003df6f  mov     rcx, rax; void *
0x18003df72  call    memset_0
0x18003df77  mov     eax, [r14]
0x18003df7a  mov     rsi, [rsi+10h]
0x18003df7e  lea     rcx, [rax+rax*2]
0x18003df82  lea     r14, [rsi+rcx*8]
0x18003df86  cmp     rsi, r14
0x18003df89  jz      loc_18003E3CF
0x18003df8f  mov     rdx, rsi; struct IStream *
0x18003df92  mov     rcx, rdi; this
0x18003df95  call    ?ReadPROPVARIANT@StructuredQuery1@@YAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z; StructuredQuery1::ReadPROPVARIANT(IStream *,tagPROPVARIANT *)
0x18003df9a  add     rsi, 18h
0x18003df9e  mov     ebx, eax
0x18003dfa0  test    eax, eax
0x18003dfa2  jns     short loc_18003DF86
0x18003dfa4  jmp     loc_18003E3CF
0x18003dfa9  mov     ecx, 18h; cb
0x18003dfae  call    cs:__imp_CoTaskMemAlloc
0x18003dfb4  mov     [r14], rax
0x18003dfb7  test    rax, rax
0x18003dfba  jz      short loc_18003DFEA
0x18003dfbc  xor     ecx, ecx
0x18003dfbe  xorps   xmm0, xmm0
0x18003dfc1  movups  xmmword ptr [rax], xmm0
0x18003dfc4  mov     [rax+10h], rcx
0x18003dfc8  mov     rcx, rdi; this
0x18003dfcb  mov     rdx, [r14]; struct IStream *
0x18003dfce  call    ?ReadPROPVARIANT@StructuredQuery1@@YAJPEAUIStream@@PEAUtagPROPVARIANT@@@Z; StructuredQuery1::ReadPROPVARIANT(IStream *,tagPROPVARIANT *)
0x18003dfd3  mov     ebx, eax
0x18003dfd5  test    eax, eax
0x18003dfd7  js      loc_18003E3CF
0x18003dfdd  mov     eax, 4000h
0x18003dfe2  or      [rsi], ax
0x18003dfe5  jmp     loc_18003E3CF
0x18003dfea  mov     ebx, 8007000Eh
0x18003dfef  jmp     loc_18003E3CF
0x18003dff4  mov     r8d, 1; cb
0x18003dffa  call    cs:__imp_IStream_Read
0x18003e000  mov     ebx, eax
0x18003e002  jmp     loc_18003E3CF
0x18003e007  sub     ecx, 12h
0x18003e00a  jz      short loc_18003E03C
0x18003e00c  sub     ecx, 1
0x18003e00f  jz      short loc_18003E087
0x18003e011  sub     ecx, 1
0x18003e014  jz      short loc_18003E01F
0x18003e016  cmp     ecx, 1
0x18003e019  jnz     loc_18003DCE4
0x18003e01f  bt      dx, 0Ch
0x18003e024  mov     rcx, rdi; pstm
0x18003e027  lea     rdx, [rsi+8]
0x18003e02b  jnb     loc_18003E21F
0x18003e031  lea     r8, [rsi+10h]
0x18003e035  call    StructuredQuery1__ReadBlob_double_
0x18003e03a  jmp     short loc_18003E000
0x18003e03c  bt      dx, 0Ch
0x18003e041  mov     rcx, rdi; pstm
0x18003e044  lea     rdx, [rsi+8]
0x18003e048  jnb     short loc_18003E055
0x18003e04a  lea     r8, [rsi+10h]
0x18003e04e  call    StructuredQuery1__ReadBlob_short_
0x18003e053  jmp     short loc_18003E000
0x18003e055  mov     r8d, r14d
0x18003e058  jmp     short loc_18003DFFA
0x18003e05a  cmp     ecx, 40h ; '@'
0x18003e05d  ja      loc_18003E22A
0x18003e063  jz      short loc_18003E01F
0x18003e065  cmp     ecx, 1Ch
0x18003e068  ja      short loc_18003E0AE
0x18003e06a  jz      loc_18003DCE4
0x18003e070  sub     ecx, 17h
0x18003e073  jz      short loc_18003E087
0x18003e075  sub     ecx, 1
0x18003e078  jz      loc_18003E3CF
0x18003e07e  sub     ecx, 1
0x18003e081  jnz     loc_18003DCE4
0x18003e087  bt      dx, 0Ch
0x18003e08c  mov     rcx, rdi; pstm
0x18003e08f  lea     rdx, [rsi+8]
0x18003e093  jnb     short loc_18003E0A3
0x18003e095  lea     r8, [rsi+10h]
0x18003e099  call    StructuredQuery1__ReadBlob_long_
0x18003e09e  jmp     loc_18003E000
0x18003e0a3  mov     r8d, 4
0x18003e0a9  jmp     loc_18003DFFA
0x18003e0ae  sub     ecx, 1Dh
0x18003e0b1  jz      loc_18003DCE4
0x18003e0b7  sub     ecx, 1
0x18003e0ba  jz      loc_18003E174
0x18003e0c0  sub     ecx, 1
0x18003e0c3  jnz     loc_18003DCE4
0x18003e0c9  lea     r14, [rsi+8]
0x18003e0cd  mov     rcx, rdi; this
0x18003e0d0  bt      dx, 0Ch
0x18003e0d5  mov     rdx, r14; struct IStream *
0x18003e0d8  jnb     loc_18003E16A
0x18003e0de  mov     r8d, 4; cb
0x18003e0e4  call    cs:__imp_IStream_Read
0x18003e0ea  mov     ebx, eax
0x18003e0ec  test    eax, eax
0x18003e0ee  js      loc_18003E3CF
0x18003e0f4  mov     ecx, [r14]; unsigned __int64
0x18003e0f7  lea     r8, [rbp+cb]; unsigned __int64 *
0x18003e0fb  mov     edx, 8; unsigned __int64
0x18003e100  mov     [rbp+cb], 0
0x18003e108  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003e10d  mov     ebx, eax
0x18003e10f  test    eax, eax
0x18003e111  js      loc_18003E3CF
0x18003e117  mov     rcx, [rbp+cb]; cb
0x18003e11b  call    cs:__imp_CoTaskMemAlloc
0x18003e121  mov     [rsi+10h], rax
0x18003e125  test    rax, rax
0x18003e128  jz      loc_18003DFEA
0x18003e12e  mov     r8, [rbp+cb]; Size
0x18003e132  xor     edx, edx; Val
0x18003e134  mov     rcx, rax; void *
0x18003e137  call    memset_0
0x18003e13c  mov     eax, [r14]
0x18003e13f  mov     rsi, [rsi+10h]
0x18003e143  lea     r14, [rsi+rax*8]
0x18003e147  cmp     rsi, r14
0x18003e14a  jz      loc_18003E3CF
0x18003e150  mov     rdx, rsi; struct IStream *
0x18003e153  mov     rcx, rdi; this
  ... truncated ...
```
