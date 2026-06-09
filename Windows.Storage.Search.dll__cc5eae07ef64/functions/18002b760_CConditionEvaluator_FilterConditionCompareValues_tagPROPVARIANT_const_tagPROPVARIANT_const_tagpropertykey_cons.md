# CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)

- ea: `0x18002b760`
- end: `0x18002beb2`
- name: `?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z`
- size: `1874`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029690`
- `0x18002a880`

## callees

- `0x18002b760`
- `0x18002c2c0`
- `0x18002cc90`
- `0x18003bde0`
- `0x180046860`
- `0x18006b9cc`
- `0x180071dc0`
- `0x180072cdc`
- `0x180092ddc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b8e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b8e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b942`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ba33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ba59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bc4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd78`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b942`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ba33`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ba59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bc4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002bd78`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002bd2d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002bd2d`
- `PROPSYS!PSFormatForDisplay` at `0x18002b898`
- `PROPSYS!PSFormatForDisplay` at `0x18002b898`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002bcdc`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002bcdc`
- `PROPSYS!PSGetPropertyDescription` at `0x18002b9ac`
- `PROPSYS!PSGetPropertyDescription` at `0x18002b9ac`
- `PROPSYS!PropVariantCompareEx` at `0x18002bb90`
- `PROPSYS!PropVariantCompareEx` at `0x18002bb90`
- `PROPSYS!PropVariantChangeType` at `0x18002baa5`
- `PROPSYS!PropVariantChangeType` at `0x18002bae4`
- `PROPSYS!PropVariantChangeType` at `0x18002bbd5`
- `PROPSYS!PropVariantChangeType` at `0x18002be1f`
- `PROPSYS!PropVariantChangeType` at `0x18002baa5`
- `PROPSYS!PropVariantChangeType` at `0x18002bae4`
- `PROPSYS!PropVariantChangeType` at `0x18002bbd5`
- `PROPSYS!PropVariantChangeType` at `0x18002be1f`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::FilterConditionCompareValues(
        CConditionEvaluator *a1,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        PROPERTYKEY *a4,
        enum tagCONDITION_OPERATION a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        unsigned int a11,
        const WCHAR *pszStr1,
        LCID Locale,
        int *a14,
        _DWORD *a15)
{
  __int64 v15; // r10
  LCID v18; // r14d
  HRESULT v19; // ebx
  VARTYPE v20; // ax
  int v21; // esi
  PROPDESC_FORMAT_FLAGS v22; // r8d
  __int64 v23; // rax
  SIZE_T v25; // rbx
  void *v26; // rax
  __int64 v27; // rax
  PROPVARIANT *v28; // rdi
  int v29; // esi
  int v30; // edi
  HRESULT v32; // eax
  PROPVARIANT *v33; // rdx
  VARTYPE v34; // r9
  PKA_FLAGS v35; // edi
  __int16 v36; // ax
  PROPVARIANT *v37; // rbx
  PROPVARIANT *v38; // r14
  int v39; // eax
  int v40; // eax
  PROPERTYKEY *v41; // r14
  unsigned int InputLocale; // eax
  PROPERTYKEY *propkey; // [rsp+30h] [rbp-D0h] BYREF
  PROPDESC_FORMAT_FLAGS pdfFlags[2]; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h]
  PROPVARIANT *propvar; // [rsp+58h] [rbp-A8h]
  PROPVARIANT *propvar2; // [rsp+60h] [rbp-A0h]
  CConditionEvaluator *v49; // [rsp+68h] [rbp-98h]
  PROPVARIANT ppropvarDest[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h]
  WCHAR pwszText[1024]; // [rsp+90h] [rbp-70h] BYREF

  v15 = a8;
  propvar2 = a2;
  v49 = a1;
  propvar = a3;
  *(_QWORD *)pdfFlags = a8;
  propkey = a4;
  if ( a5 == COP_IMPLICIT )
    return 1;
  if ( (unsigned int)(a5 - 7) <= 6 )
  {
    v18 = Locale;
    *a14 = 0;
    if ( !Locale )
    {
      InputLocale = CConditionEvaluator::_GetInputLocale(a1);
      a4 = propkey;
      v18 = InputLocale;
      v15 = *(_QWORD *)pdfFlags;
    }
    v19 = 0;
    v51 = 0;
    v20 = *(_WORD *)a2;
    *(_OWORD *)ppropvarDest = 0;
    if ( v20 != 31 && v20 != 8 )
    {
      v19 = PropVariantChangeType(ppropvarDest, a2, 0, 0x1Fu);
      if ( v19 < 0 )
        goto LABEL_33;
      a4 = propkey;
      v15 = *(_QWORD *)pdfFlags;
      propvar2 = ppropvarDest;
    }
    v21 = 0;
    if ( a6 )
    {
      if ( a7 || a4->pid != 10 )
        goto LABEL_9;
      v27 = *(_QWORD *)&a4->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
      if ( *(_QWORD *)&a4->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
        v27 = *(_QWORD *)a4->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
      if ( v27 )
      {
LABEL_9:
        pdfFlags[0] = PDFF_DEFAULT;
        if ( v15
          && (*(int (__fastcall **)(__int64, PROPERTYKEY *, PROPDESC_FORMAT_FLAGS *))(*(_QWORD *)v15 + 24LL))(
               v15,
               a4,
               pdfFlags) >= 0 )
        {
          v22 = pdfFlags[0];
        }
        else
        {
          v22 = PDFF_ALWAYSKB;
          pdfFlags[0] = PDFF_ALWAYSKB;
        }
        v19 = PSFormatForDisplay(propkey, propvar, v22, pwszText, 0x400u);
        if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147024774 )
          goto LABEL_33;
        v46 = 0;
        v23 = -1;
        *(_OWORD *)pvar = 0;
        while ( pwszText[++v23] != 0 )
          ;
        v25 = 2 * v23 + 2;
        v26 = CoTaskMemAlloc(v25);
        pvar[1] = v26;
        if ( !v26 )
        {
          v19 = -2147024882;
          goto LABEL_33;
        }
        if ( v25 )
          memcpy_0(v26, pwszText, v25);
        LOWORD(pvar[0]) = 31;
        v19 = 0;
        v21 = _LikeOpCompareValuesWorker(propvar2, pvar, a5, v18, *((_DWORD *)v49 + 18));
        PropVariantClear(pvar);
        a4 = propkey;
      }
    }
    if ( v21 )
      goto LABEL_96;
    if ( a6 )
    {
      if ( a7 && (unsigned int)operator==(a4, &PKEY_ItemNameDisplay) )
        goto LABEL_30;
      pdfFlags[0] = PDFF_DEFAULT;
      propkey = 0;
      if ( PSGetPropertyDescription(a4, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, (void **)&propkey) >= 0 )
      {
        (*(void (__fastcall **)(PROPERTYKEY *, __int64, PROPDESC_FORMAT_FLAGS *))(*(_QWORD *)&propkey->fmtid.Data1 + 64LL))(
          propkey,
          1024,
          pdfFlags);
        (*(void (__fastcall **)(PROPERTYKEY *))(*(_QWORD *)&propkey->fmtid.Data1 + 16LL))(propkey);
      }
      if ( (pdfFlags[0] & 0x400) == 0 )
        goto LABEL_30;
    }
    v28 = propvar;
    v46 = 0;
    *(_OWORD *)pvar = 0;
    if ( *(_WORD *)propvar != 31 && *(_WORD *)propvar != 8 )
    {
      v32 = PropVariantChangeType(pvar, propvar, 0, 0x1Fu);
      v33 = pvar;
      if ( v32 < 0 )
        v33 = v28;
      v28 = v33;
    }
    v29 = _LikeOpCompareValuesWorker(propvar2, v28, a5, v18, *((_DWORD *)v49 + 18));
    PropVariantClear(pvar);
    if ( v29 )
    {
LABEL_96:
      if ( a9 )
        goto LABEL_31;
    }
    else
    {
LABEL_30:
      if ( !a9 )
      {
LABEL_31:
        v30 = 0;
LABEL_32:
        *a14 = v30;
LABEL_33:
        PropVariantClear(ppropvarDest);
        return (unsigned int)v19;
      }
    }
    v30 = 1;
    goto LABEL_32;
  }
  if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
    return (unsigned int)SortKeyCompareValues(
                           (const struct tagPROPVARIANT *)a2,
                           (const struct tagPROPVARIANT *)a3,
                           a5,
                           a9,
                           a14);
  if ( a11 )
    return (unsigned int)BitwiseCompareValues(a2, a3, a11, a9, a14);
  *a14 = 0;
  v34 = *(_WORD *)a2;
  v35 = PKA_APPEND;
  v36 = *(_WORD *)a3;
  if ( v34 == *(_WORD *)a3 || v34 && v36 )
  {
    v37 = propvar2;
    v46 = 0;
    v38 = propvar2;
    *(_OWORD *)pvar = 0;
    if ( v34 != v36 && v36 != 1 && v34 != 1 )
    {
      if ( PropVariantChangeType(pvar, propvar, 0, v34) < 0 )
      {
        v38 = pvar;
        if ( PropVariantChangeType(pvar, v37, 0, *(_WORD *)propvar) < 0 )
          v38 = v37;
      }
      else
      {
        propvar = pvar;
      }
    }
    v39 = PropVariantCompareEx(propvar, v38, PVCU_DEFAULT, 0);
    *a14 = 0;
    switch ( a5 )
    {
      case COP_EQUAL:
        if ( v39 )
          break;
        goto LABEL_85;
      case COP_NOTEQUAL:
        if ( v39 )
        {
          if ( a9 )
            goto LABEL_86;
          goto LABEL_68;
        }
        break;
      case COP_LESSTHAN:
        if ( v39 < 0 )
        {
          if ( a9 )
            goto LABEL_86;
LABEL_68:
          v40 = 1;
LABEL_69:
          *a14 = v40;
          PropVariantClear(pvar);
          goto LABEL_70;
        }
        break;
      case COP_GREATERTHAN:
        if ( v39 > 0 )
        {
          if ( a9 )
            goto LABEL_86;
          goto LABEL_68;
        }
        break;
      case COP_LESSTHANOREQUAL:
        if ( v39 <= 0 )
        {
          if ( a9 )
            goto LABEL_86;
          goto LABEL_68;
        }
        break;
      case COP_GREATERTHANOREQUAL:
        if ( v39 >= 0 )
        {
LABEL_85:
          if ( a9 )
            goto LABEL_86;
          goto LABEL_68;
        }
        break;
      default:
        PropVariantClear(pvar);
        return (unsigned int)-2147024809;
    }
    if ( a9 )
      goto LABEL_68;
LABEL_86:
    v40 = 0;
    goto LABEL_69;
  }
  if ( !a9 )
  {
    if ( a5 != COP_NOTEQUAL )
      goto LABEL_70;
    goto LABEL_100;
  }
  if ( a5 == COP_EQUAL )
  {
LABEL_100:
    *a14 = 1;
LABEL_70:
    v19 = 0;
    if ( *a14 )
      return (unsigned int)v19;
    goto LABEL_71;
  }
  v19 = 0;
LABEL_71:
  if ( a15 )
  {
    if ( a10 )
    {
      v41 = propkey;
      if ( (GetPropertyTypeFlags(propkey, PDTF_ISINNATE) & 2) == 0 )
      {
        if ( a9 )
        {
          if ( a5 != COP_NOTEQUAL )
            return (unsigned int)v19;
        }
        else if ( a5 != COP_EQUAL )
        {
          return (unsigned int)v19;
        }
        propkey = 0;
        if ( (GetPropertyTypeFlags(v41, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)propvar2 )
          v35 = PKA_SET;
        v19 = PSCreateSimplePropertyChange(
                v35,
                v41,
                propvar2,
                &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431,
                (void **)&propkey);
        if ( v19 >= 0 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, PROPERTYKEY *))(*(_QWORD *)a10 + 48LL))(a10, propkey);
          (*(void (__fastcall **)(PROPERTYKEY *))(*(_QWORD *)&propkey->fmtid.Data1 + 16LL))(propkey);
        }
        *a15 = v19 >= 0;
      }
    }
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18002b760  push    rbp
0x18002b762  push    rbx
0x18002b763  push    rsi
0x18002b764  push    rdi
0x18002b765  push    r12
0x18002b767  push    r13
0x18002b769  push    r15
0x18002b76b  lea     rbp, [rsp-7B0h]
0x18002b773  sub     rsp, 8B0h
0x18002b77a  mov     rax, cs:__security_cookie
0x18002b781  xor     rax, rsp
0x18002b784  mov     [rbp+7E0h+var_50], rax
0x18002b78b  mov     r10, [rbp+7E0h+arg_38]
0x18002b792  mov     rbx, r8
0x18002b795  mov     r13d, [rbp+7E0h+arg_20]
0x18002b79c  mov     rdi, rdx
0x18002b79f  mov     r15, [rbp+7E0h+arg_48]
0x18002b7a6  mov     r12, [rbp+7E0h+arg_68]
0x18002b7ad  mov     rsi, [rbp+7E0h+arg_70]
0x18002b7b4  mov     [rsp+8E0h+propvar2], rdx
0x18002b7b9  mov     rdx, rcx
0x18002b7bc  mov     [rsp+8E0h+var_878], rcx
0x18002b7c1  mov     rcx, [rbp+7E0h+pszStr1]; pszStr1
0x18002b7c8  mov     [rsp+8E0h+propvar], rbx
0x18002b7cd  mov     qword ptr [rsp+8E0h+pdfFlags], r10
0x18002b7d2  mov     [rsp+8E0h+propkey], r9
0x18002b7d7  test    r13d, r13d
0x18002b7da  jz      loc_18002BB1E
0x18002b7e0  lea     eax, [r13-7]
0x18002b7e4  mov     [rsp+8E0h+var_38], r14
0x18002b7ec  cmp     eax, 6
0x18002b7ef  ja      loc_18002BB32
0x18002b7f5  mov     r14d, [rbp+7E0h+Locale]
0x18002b7fc  mov     dword ptr [r12], 0
0x18002b804  test    r14d, r14d
0x18002b807  jz      loc_18002BD88
0x18002b80d  xor     eax, eax
0x18002b80f  xor     ebx, ebx
0x18002b811  mov     [rbp+7E0h+var_860], rax
0x18002b815  xorps   xmm0, xmm0
0x18002b818  movzx   eax, word ptr [rdi]
0x18002b81b  movups  xmmword ptr [rsp+8E0h+ppropvarDest], xmm0
0x18002b820  cmp     ax, 1Fh
0x18002b824  jnz     loc_18002BA8A
0x18002b82a  mov     r15d, [rbp+7E0h+arg_28]
0x18002b831  xor     esi, esi
0x18002b833  mov     edi, [rbp+7E0h+arg_30]
0x18002b839  test    r15d, r15d
0x18002b83c  jz      loc_18002B96F
0x18002b842  test    edi, edi
0x18002b844  jnz     short loc_18002B851
0x18002b846  cmp     dword ptr [r9+10h], 0Ah
0x18002b84b  jz      loc_18002B94F
0x18002b851  mov     [rsp+8E0h+pdfFlags], esi
0x18002b855  test    r10, r10
0x18002b858  jz      loc_18002BB0E
0x18002b85e  mov     rax, [r10]
0x18002b861  lea     r8, [rsp+8E0h+pdfFlags]
0x18002b866  mov     rdx, r9
0x18002b869  mov     rcx, r10
0x18002b86c  mov     rax, [rax+18h]
0x18002b870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b875  test    eax, eax
0x18002b877  js      loc_18002BB0E
0x18002b87d  mov     r8d, [rsp+8E0h+pdfFlags]; pdfFlags
0x18002b882  mov     rdx, [rsp+8E0h+propvar]; propvar
0x18002b887  lea     r9, [rbp+7E0h+pwszText]; pwszText
0x18002b88b  mov     rcx, [rsp+8E0h+propkey]; propkey
0x18002b890  mov     [rsp+8E0h+cchText], 400h; cchText
0x18002b898  call    cs:__imp_PSFormatForDisplay
0x18002b89e  mov     ecx, 80000000h
0x18002b8a3  mov     ebx, eax
0x18002b8a5  add     eax, ecx
0x18002b8a7  test    ecx, eax
0x18002b8a9  jz      loc_18002BAFD
0x18002b8af  xor     eax, eax
0x18002b8b1  lea     rcx, [rbp+7E0h+pwszText]
0x18002b8b5  xorps   xmm0, xmm0
0x18002b8b8  mov     [rsp+8E0h+var_890], rax
0x18002b8bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002b8c4  movups  xmmword ptr [rsp+8E0h+pvar], xmm0
0x18002b8c9  nop     dword ptr [rax+00000000h]
0x18002b8d0  cmp     [rcx+rax*2+2], si
0x18002b8d5  lea     rax, [rax+1]
0x18002b8d9  jnz     short loc_18002B8D0
0x18002b8db  lea     rbx, ds:2[rax*2]
0x18002b8e3  mov     rcx, rbx; cb
0x18002b8e6  call    cs:__imp_CoTaskMemAlloc
0x18002b8ec  mov     [rsp+8E0h+pvar+8], rax
0x18002b8f1  test    rax, rax
0x18002b8f4  jz      loc_18002BDA2
0x18002b8fa  test    rbx, rbx
0x18002b8fd  jz      short loc_18002B90E
0x18002b8ff  mov     r8, rbx; Size
0x18002b902  lea     rdx, [rbp+7E0h+pwszText]; Src
0x18002b906  mov     rcx, rax; void *
0x18002b909  call    memcpy_0
0x18002b90e  mov     rcx, [rsp+8E0h+propvar2]; propvarIn
0x18002b913  lea     rdx, [rsp+8E0h+pvar]; PROPVARIANT *
0x18002b918  mov     eax, 1Fh
0x18002b91d  mov     r9d, r14d; Locale
0x18002b920  mov     word ptr [rsp+8E0h+pvar], ax
0x18002b925  mov     r8d, r13d; enum tagCONDITION_OPERATION
0x18002b928  mov     rax, [rsp+8E0h+var_878]
0x18002b92d  xor     ebx, ebx
0x18002b92f  mov     eax, [rax+48h]
0x18002b932  mov     [rsp+8E0h+cchText], eax; unsigned int
0x18002b936  call    ?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z; _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)
0x18002b93b  lea     rcx, [rsp+8E0h+pvar]; pvar
0x18002b940  mov     esi, eax
0x18002b942  call    cs:__imp_PropVariantClear
0x18002b948  mov     r9, [rsp+8E0h+propkey]
0x18002b94d  jmp     short loc_18002B977
0x18002b94f  mov     rax, [r9]
0x18002b952  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18002b959  jnz     short loc_18002B966
0x18002b95b  mov     rax, [r9+8]
0x18002b95f  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x18002b966  test    rax, rax
0x18002b969  jnz     loc_18002B851
0x18002b96f  test    ebx, ebx
0x18002b971  js      loc_18002BA54
0x18002b977  test    esi, esi
0x18002b979  jnz     loc_18002BDC8
0x18002b97f  test    r15d, r15d
0x18002b982  jz      short loc_18002B9EC
0x18002b984  test    edi, edi
0x18002b986  jnz     loc_18002BDAC
0x18002b98c  lea     r8, [rsp+8E0h+propkey]; ppv
0x18002b991  mov     [rsp+8E0h+pdfFlags], 0
0x18002b999  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18002b9a0  mov     [rsp+8E0h+propkey], 0
0x18002b9a9  mov     rcx, r9; propkey
0x18002b9ac  call    cs:__imp_PSGetPropertyDescription
0x18002b9b2  test    eax, eax
0x18002b9b4  js      short loc_18002B9E2
0x18002b9b6  mov     rcx, [rsp+8E0h+propkey]
0x18002b9bb  lea     r8, [rsp+8E0h+pdfFlags]
0x18002b9c0  mov     edx, 400h
0x18002b9c5  mov     rax, [rcx]
0x18002b9c8  mov     rax, [rax+40h]
0x18002b9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9d1  mov     rcx, [rsp+8E0h+propkey]
0x18002b9d6  mov     rax, [rcx]
0x18002b9d9  mov     rax, [rax+10h]
0x18002b9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9e2  test    [rsp+8E0h+pdfFlags], 400h
0x18002b9ea  jz      short loc_18002BA41
0x18002b9ec  mov     rdi, [rsp+8E0h+propvar]
0x18002b9f1  xor     eax, eax
0x18002b9f3  mov     [rsp+8E0h+var_890], rax
0x18002b9f8  xorps   xmm0, xmm0
0x18002b9fb  movups  xmmword ptr [rsp+8E0h+pvar], xmm0
0x18002ba00  movzx   eax, word ptr [rdi]
0x18002ba03  cmp     ax, 1Fh
0x18002ba07  jnz     loc_18002BACA
0x18002ba0d  mov     rax, [rsp+8E0h+var_878]
0x18002ba12  mov     r9d, r14d; Locale
0x18002ba15  mov     rcx, [rsp+8E0h+propvar2]; propvarIn
0x18002ba1a  mov     r8d, r13d; enum tagCONDITION_OPERATION
0x18002ba1d  mov     rdx, rdi; PROPVARIANT *
0x18002ba20  mov     eax, [rax+48h]
0x18002ba23  mov     [rsp+8E0h+cchText], eax; unsigned int
0x18002ba27  call    ?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z; _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)
0x18002ba2c  lea     rcx, [rsp+8E0h+pvar]; pvar
0x18002ba31  mov     esi, eax
0x18002ba33  call    cs:__imp_PropVariantClear
0x18002ba39  test    esi, esi
0x18002ba3b  jnz     loc_18002BDC8
0x18002ba41  cmp     [rbp+7E0h+arg_40], 0
0x18002ba48  jnz     loc_18002BB28
0x18002ba4e  xor     edi, edi
0x18002ba50  mov     [r12], edi
0x18002ba54  lea     rcx, [rsp+8E0h+ppropvarDest]; pvar
0x18002ba59  call    cs:__imp_PropVariantClear
0x18002ba5f  mov     r14, [rsp+8E0h+var_38]
0x18002ba67  mov     eax, ebx
0x18002ba69  mov     rcx, [rbp+7E0h+var_50]
0x18002ba70  xor     rcx, rsp; StackCookie
0x18002ba73  call    __security_check_cookie
0x18002ba78  add     rsp, 8B0h
0x18002ba7f  pop     r15
0x18002ba81  pop     r13
0x18002ba83  pop     r12
0x18002ba85  pop     rdi
0x18002ba86  pop     rsi
0x18002ba87  pop     rbx
0x18002ba88  pop     rbp
0x18002ba89  retn
0x18002ba8a  cmp     ax, 8
0x18002ba8e  jz      loc_18002B82A
0x18002ba94  mov     r9d, 1Fh; vt
0x18002ba9a  lea     rcx, [rsp+8E0h+ppropvarDest]; ppropvarDest
0x18002ba9f  xor     r8d, r8d; flags
0x18002baa2  mov     rdx, rdi; propvarSrc
0x18002baa5  call    cs:__imp_PropVariantChangeType
0x18002baab  mov     ebx, eax
0x18002baad  test    eax, eax
0x18002baaf  js      short loc_18002BA54
0x18002bab1  mov     r9, [rsp+8E0h+propkey]
0x18002bab6  lea     rax, [rsp+8E0h+ppropvarDest]
0x18002babb  mov     r10, qword ptr [rsp+8E0h+pdfFlags]
0x18002bac0  mov     [rsp+8E0h+propvar2], rax
0x18002bac5  jmp     loc_18002B82A
0x18002baca  cmp     ax, 8
0x18002bace  jz      loc_18002BA0D
0x18002bad4  mov     r9w, 1Fh; vt
0x18002bad9  lea     rcx, [rsp+8E0h+pvar]; ppropvarDest
0x18002bade  xor     r8d, r8d; flags
0x18002bae1  mov     rdx, rdi; propvarSrc
0x18002bae4  call    cs:__imp_PropVariantChangeType
0x18002baea  test    eax, eax
0x18002baec  lea     rdx, [rsp+8E0h+pvar]
0x18002baf1  cmovs   rdx, rdi
0x18002baf5  mov     rdi, rdx
0x18002baf8  jmp     loc_18002BA0D
0x18002bafd  cmp     ebx, 8007007Ah
0x18002bb03  jz      loc_18002B8AF
0x18002bb09  jmp     loc_18002BA54
0x18002bb0e  mov     r8d, 4
0x18002bb14  mov     [rsp+8E0h+pdfFlags], r8d
0x18002bb19  jmp     loc_18002B882
0x18002bb1e  mov     ebx, 1
0x18002bb23  jmp     loc_18002BA67
0x18002bb28  mov     edi, 1
0x18002bb2d  jmp     loc_18002BA50
0x18002bb32  test    rcx, rcx
0x18002bb35  jnz     loc_18002BD26
0x18002bb3b  mov     r8d, [rbp+7E0h+arg_50]
0x18002bb42  test    r8d, r8d
0x18002bb45  jnz     loc_18002BDDA
0x18002bb4b  mov     [r12], r8d
0x18002bb4f  movzx   r9d, word ptr [rdi]; vt
0x18002bb53  mov     edi, 1
0x18002bb58  movzx   eax, word ptr [rbx]
0x18002bb5b  cmp     r9w, ax
0x18002bb5f  jnz     loc_18002BBEF
0x18002bb65  mov     rbx, [rsp+8E0h+propvar2]
0x18002bb6a  xor     ecx, ecx
0x18002bb6c  mov     [rsp+8E0h+var_890], rcx
0x18002bb71  xorps   xmm0, xmm0
0x18002bb74  mov     r14, rbx
0x18002bb77  movups  xmmword ptr [rsp+8E0h+pvar], xmm0
0x18002bb7c  cmp     r9w, ax
0x18002bb80  jnz     short loc_18002BBBD
0x18002bb82  mov     rcx, [rsp+8E0h+propvar]; propvar1
0x18002bb87  xor     r9d, r9d; flags
0x18002bb8a  xor     r8d, r8d; unit
0x18002bb8d  mov     rdx, r14; propvar2
0x18002bb90  call    cs:__imp_PropVariantCompareEx
0x18002bb96  mov     dword ptr [r12], 0
0x18002bb9e  cmp     r13d, edi
0x18002bba1  jnz     short loc_18002BC18
0x18002bba3  test    eax, eax
0x18002bba5  jz      loc_18002BD12
0x18002bbab  cmp     [rbp+7E0h+arg_40], 0
0x18002bbb2  jz      loc_18002BD1F
0x18002bbb8  jmp     loc_18002BC40
0x18002bbbd  cmp     ax, di
0x18002bbc0  jz      short loc_18002BB82
0x18002bbc2  cmp     r9w, di
0x18002bbc6  jz      short loc_18002BB82
0x18002bbc8  mov     rdx, [rsp+8E0h+propvar]; propvarSrc
0x18002bbcd  lea     rcx, [rsp+8E0h+pvar]; ppropvarDest
0x18002bbd2  xor     r8d, r8d; flags
0x18002bbd5  call    cs:__imp_PropVariantChangeType
0x18002bbdb  test    eax, eax
0x18002bbdd  js      loc_18002BE0B
0x18002bbe3  lea     rdx, [rsp+8E0h+pvar]
0x18002bbe8  mov     [rsp+8E0h+propvar], rdx
0x18002bbed  jmp     short loc_18002BB82
0x18002bbef  test    r9w, r9w
0x18002bbf3  jz      short loc_18002BBFE
0x18002bbf5  test    ax, ax
0x18002bbf8  jnz     loc_18002BB65
0x18002bbfe  cmp     [rbp+7E0h+arg_40], 0
0x18002bc05  jz      loc_18002BDF8
0x18002bc0b  cmp     r13d, edi
0x18002bc0e  jz      loc_18002BE02
0x18002bc14  xor     ebx, ebx
0x18002bc16  jmp     short loc_18002BC5D
0x18002bc18  mov     edx, r13d
0x18002bc1b  sub     edx, 2
0x18002bc1e  jz      loc_18002BE4F
0x18002bc24  sub     edx, edi
0x18002bc26  jnz     loc_18002BCFA
0x18002bc2c  test    eax, eax
0x18002bc2e  jns     loc_18002BBAB
0x18002bc34  cmp     [rbp+7E0h+arg_40], edx
0x18002bc3a  jnz     loc_18002BD1F
0x18002bc40  mov     eax, edi
0x18002bc42  lea     rcx, [rsp+8E0h+pvar]; pvar
0x18002bc47  mov     [r12], eax
0x18002bc4b  call    cs:__imp_PropVariantClear
0x18002bc51  xor     ebx, ebx
0x18002bc53  cmp     [r12], ebx
0x18002bc57  jnz     loc_18002BA5F
0x18002bc5d  test    rsi, rsi
0x18002bc60  jz      loc_18002BA5F
0x18002bc66  test    r15, r15
  ... truncated ...
```
