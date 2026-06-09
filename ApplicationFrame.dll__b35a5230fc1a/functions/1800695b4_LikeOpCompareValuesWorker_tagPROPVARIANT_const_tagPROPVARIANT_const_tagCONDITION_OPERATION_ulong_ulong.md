# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x1800695b4`
- end: `0x18006985d`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `681`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800663c8`

## callees

- `0x18002cf10`
- `0x180062930`
- `0x180062cec`
- `0x180063a34`
- `0x18006557c`
- `0x180066d20`
- `0x18006759c`
- `0x1800695b4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069729`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800697e8`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069835`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069729`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800697e8`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180069835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006980a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800697f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006980a`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800695eb`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800695fe`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800695eb`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1800695fe`
- `SHLWAPI!PathMatchSpecExW` at `0x1800696f3`
- `SHLWAPI!PathMatchSpecExW` at `0x1800696f3`

## pseudocode

```c
__int64 __fastcall _LikeOpCompareValuesWorker(
        PROPVARIANT *propvarIn,
        PROPVARIANT *a2,
        enum tagCONDITION_OPERATION a3,
        LCID Locale,
        unsigned int a5)
{
  unsigned int v8; // edi
  const WCHAR *v9; // r14
  const WCHAR *lpStringValue; // rax
  const struct std::nothrow_t *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // rbp
  unsigned __int64 v14; // rcx
  CWordMatch *v15; // rax
  CWordMatch *v16; // rax
  const unsigned __int16 *v17; // r8
  CWordMatch *v18; // rbx
  unsigned int NLSString; // edi
  DWORD v20; // edx
  unsigned int v21; // ebx
  int v22; // r13d
  unsigned int v23; // edx
  WCHAR *v24; // rbx
  LPCWSTR lpStringSource; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR v27; // [rsp+48h] [rbp-30h] BYREF
  int v28; // [rsp+90h] [rbp+18h] BYREF

  v28 = 0;
  v8 = 0;
  v9 = PropVariantToStringWithDefault(a2, &pszDefault);
  lpStringValue = PropVariantToStringWithDefault(propvarIn, &pszDefault);
  v13 = lpStringValue;
  if ( a3 != COP_VALUE_STARTSWITH )
  {
    if ( a3 == COP_VALUE_ENDSWITH )
    {
      v20 = a5 | 0x200000;
    }
    else
    {
      if ( a3 != COP_VALUE_CONTAINS )
      {
        if ( a3 != COP_VALUE_NOTCONTAINS )
        {
          if ( a3 == COP_DOSWILDCARDS )
          {
            LOBYTE(v8) = PathMatchSpecExW(v9, lpStringValue, 0) == 0;
          }
          else
          {
            v14 = (unsigned int)(a3 - 12);
            if ( (unsigned int)v14 <= 1 )
            {
              v15 = (CWordMatch *)CZeroInitNew::operator new(v14, v11);
              if ( v15 )
              {
                v16 = CWordMatch::CWordMatch(v15, a3);
                v18 = v16;
                if ( v16 )
                {
                  *((_DWORD *)v16 + 138) = Locale;
                  *((_DWORD *)v16 + 139) = a5;
                  if ( Locale == 1042
                    && !CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v13, v17) )
                  {
                    CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                      (CKoreanDecomposition *)g_koreanDecomposition,
                      v13,
                      (unsigned __int16 **)v18 + 67);
                  }
                  if ( (int)StringCchCopyW((unsigned __int16 *)v18 + 6, 0x104u, v13) >= 0 )
                  {
                    CWordMatch::WordMatch(v18, v9, &v28);
                    v8 = v28;
                  }
                  CWordMatch::Release(v18);
                }
              }
            }
          }
          return v8;
        }
        NLSString = FindNLSString(Locale, a5 | 0x400000, v9, -1, lpStringValue, -1, 0);
        return NLSString >> 31;
      }
      v20 = a5 | 0x400000;
    }
LABEL_27:
    NLSString = ~FindNLSString(Locale, v20, v9, -1, v13, -1, 0);
    return NLSString >> 31;
  }
  v21 = a5;
  if ( Locale != 1042 || CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v9, v12) )
    goto LABEL_26;
  lpStringSource = 0;
  v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
          (CKoreanDecomposition *)g_koreanDecomposition,
          v9,
          (unsigned __int16 **)&lpStringSource);
  if ( v22 >= 0 )
  {
    v27 = 0;
    v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
            (CKoreanDecomposition *)g_koreanDecomposition,
            v13,
            (unsigned __int16 **)&v27);
    if ( v22 >= 0 )
    {
      v23 = v21;
      v24 = (WCHAR *)v27;
      v8 = FindNLSString(0x412u, v23 | 0x100000, lpStringSource, -1, v27, -1, 0) >= 0;
      CoTaskMemFree(v24);
      v21 = a5;
    }
    CoTaskMemFree((LPVOID)lpStringSource);
  }
  if ( v22 )
  {
LABEL_26:
    v20 = v21 | 0x100000;
    goto LABEL_27;
  }
  return v8;
}

```

## disassembly

```asm
0x1800695b4  mov     r11, rsp
0x1800695b7  mov     [r11+8], rbx
0x1800695bb  mov     [r11+10h], rbp
0x1800695bf  push    rsi
0x1800695c0  push    rdi
0x1800695c1  push    r13
0x1800695c3  push    r14
0x1800695c5  push    r15
0x1800695c7  sub     rsp, 50h
0x1800695cb  mov     rax, rdx
0x1800695ce  mov     rbx, rcx
0x1800695d1  xor     r13d, r13d
0x1800695d4  lea     rdx, pszDefault; pszDefault
0x1800695db  mov     rcx, rax; propvarIn
0x1800695de  mov     [r11+18h], r13d
0x1800695e2  mov     r15d, r9d
0x1800695e5  mov     esi, r8d
0x1800695e8  mov     edi, r13d
0x1800695eb  call    cs:__imp_PropVariantToStringWithDefault
0x1800695f1  lea     rdx, pszDefault; pszDefault
0x1800695f8  mov     rcx, rbx; propvarIn
0x1800695fb  mov     r14, rax
0x1800695fe  call    cs:__imp_PropVariantToStringWithDefault
0x180069604  mov     ecx, esi
0x180069606  mov     rbp, rax
0x180069609  sub     ecx, 7
0x18006960c  jz      loc_180069756
0x180069612  sub     ecx, 1
0x180069615  jz      loc_180069749
0x18006961b  sub     ecx, 1
0x18006961e  jz      loc_180069736
0x180069624  sub     ecx, 1
0x180069627  jz      loc_180069704
0x18006962d  sub     ecx, 1
0x180069630  jz      loc_1800696EA
0x180069636  sub     ecx, 1; unsigned __int64
0x180069639  jz      short loc_180069644
0x18006963b  cmp     ecx, 1
0x18006963e  jnz     loc_180069842
0x180069644  call    ??2CZeroInitNew@@SAPEAX_KAEBUnothrow_t@std@@@Z; CZeroInitNew::operator new(unsigned __int64,std::nothrow_t const &)
0x180069649  test    rax, rax
0x18006964c  jz      loc_180069842
0x180069652  mov     edx, esi; enum tagCONDITION_OPERATION
0x180069654  mov     rcx, rax; this
0x180069657  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x18006965c  mov     rbx, rax
0x18006965f  test    rax, rax
0x180069662  jz      loc_180069842
0x180069668  mov     [rax+228h], r15d
0x18006966f  mov     eax, [rsp+78h+arg_20]
0x180069676  mov     [rbx+22Ch], eax
0x18006967c  cmp     r15d, 412h
0x180069683  jnz     short loc_1800696AE
0x180069685  mov     rdx, rbp; unsigned __int16 *
0x180069688  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18006968f  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x180069694  test    eax, eax
0x180069696  jnz     short loc_1800696AE
0x180069698  lea     r8, [rbx+218h]; unsigned __int16 **
0x18006969f  mov     rdx, rbp; unsigned __int16 *
0x1800696a2  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1800696a9  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x1800696ae  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x1800696b2  mov     r8, rbp; unsigned __int16 *
0x1800696b5  mov     edx, 104h; unsigned __int64
0x1800696ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800696bf  test    eax, eax
0x1800696c1  js      short loc_1800696DD
0x1800696c3  lea     r8, [rsp+78h+arg_10]; int *
0x1800696cb  mov     rdx, r14; unsigned __int16 *
0x1800696ce  mov     rcx, rbx; this
0x1800696d1  call    ?WordMatch@CWordMatch@@QEAAJPEBGPEAH@Z; CWordMatch::WordMatch(ushort const *,int *)
0x1800696d6  mov     edi, [rsp+78h+arg_10]
0x1800696dd  mov     rcx, rbx; this
0x1800696e0  call    ?Release@CWordMatch@@UEAAKXZ; CWordMatch::Release(void)
0x1800696e5  jmp     loc_180069842
0x1800696ea  xor     r8d, r8d; dwFlags
0x1800696ed  mov     rdx, rbp; pszSpec
0x1800696f0  mov     rcx, r14; pszFile
0x1800696f3  call    cs:__imp_PathMatchSpecExW
0x1800696f9  test    eax, eax
0x1800696fb  setz    dil
0x1800696ff  jmp     loc_180069842
0x180069704  mov     edx, [rsp+78h+arg_20]
0x18006970b  or      esi, 0FFFFFFFFh
0x18006970e  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180069713  bts     edx, 16h; dwFindNLSStringFlags
0x180069717  mov     [rsp+78h+cchValue], esi; cchValue
0x18006971b  mov     r9d, esi; cchSource
0x18006971e  mov     r8, r14; lpStringSource
0x180069721  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x180069726  mov     ecx, r15d; Locale
0x180069729  call    cs:__imp_FindNLSString
0x18006972f  mov     edi, eax
0x180069731  jmp     loc_18006983F
0x180069736  mov     edx, [rsp+78h+arg_20]
0x18006973d  bts     edx, 16h
0x180069741  or      esi, 0FFFFFFFFh
0x180069744  jmp     loc_18006981E
0x180069749  mov     edx, [rsp+78h+arg_20]
0x180069750  bts     edx, 15h
0x180069754  jmp     short loc_180069741
0x180069756  mov     ebx, [rsp+78h+arg_20]
0x18006975d  or      esi, 0FFFFFFFFh
0x180069760  cmp     r15d, 412h
0x180069767  jnz     loc_180069818
0x18006976d  mov     rdx, r14; unsigned __int16 *
0x180069770  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x180069777  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18006977c  test    eax, eax
0x18006977e  jnz     loc_180069818
0x180069784  lea     r8, [rsp+78h+lpStringSource]; unsigned __int16 **
0x180069789  mov     [rsp+78h+lpStringSource], r13
0x18006978e  mov     rdx, r14; unsigned __int16 *
0x180069791  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180069798  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18006979d  mov     r13d, eax
0x1800697a0  test    eax, eax
0x1800697a2  js      short loc_180069810
0x1800697a4  lea     r8, [rsp+78h+var_30]; unsigned __int16 **
0x1800697a9  mov     [rsp+78h+var_30], rdi
0x1800697ae  mov     rdx, rbp; unsigned __int16 *
0x1800697b1  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1800697b8  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x1800697bd  mov     r13d, eax
0x1800697c0  test    eax, eax
0x1800697c2  js      short loc_180069805
0x1800697c4  mov     r8, [rsp+78h+lpStringSource]; lpStringSource
0x1800697c9  mov     edx, ebx
0x1800697cb  mov     rbx, [rsp+78h+var_30]
0x1800697d0  bts     edx, 14h; dwFindNLSStringFlags
0x1800697d4  mov     [rsp+78h+pcchFound], rdi; pcchFound
0x1800697d9  mov     r9d, esi; cchSource
0x1800697dc  mov     [rsp+78h+cchValue], esi; cchValue
0x1800697e0  mov     ecx, r15d; Locale
0x1800697e3  mov     [rsp+78h+lpStringValue], rbx; lpStringValue
0x1800697e8  call    cs:__imp_FindNLSString
0x1800697ee  mov     edi, eax
0x1800697f0  mov     rcx, rbx; pv
0x1800697f3  not     edi
0x1800697f5  shr     edi, 1Fh
0x1800697f8  call    cs:__imp_CoTaskMemFree
0x1800697fe  mov     ebx, [rsp+78h+arg_20]
0x180069805  mov     rcx, [rsp+78h+lpStringSource]; pv
0x18006980a  call    cs:__imp_CoTaskMemFree
0x180069810  test    r13d, r13d
0x180069813  jz      short loc_180069842
0x180069815  xor     r13d, r13d
0x180069818  bts     ebx, 14h
0x18006981c  mov     edx, ebx; dwFindNLSStringFlags
0x18006981e  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180069823  mov     r9d, esi; cchSource
0x180069826  mov     [rsp+78h+cchValue], esi; cchValue
0x18006982a  mov     r8, r14; lpStringSource
0x18006982d  mov     ecx, r15d; Locale
0x180069830  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x180069835  call    cs:__imp_FindNLSString
0x18006983b  mov     edi, eax
0x18006983d  not     edi
0x18006983f  shr     edi, 1Fh
0x180069842  lea     r11, [rsp+78h+var_28]
0x180069847  mov     eax, edi
0x180069849  mov     rbx, [r11+30h]
0x18006984d  mov     rbp, [r11+38h]
0x180069851  mov     rsp, r11
0x180069854  pop     r15
0x180069856  pop     r14
0x180069858  pop     r13
0x18006985a  pop     rdi
0x18006985b  pop     rsi
0x18006985c  retn
```
