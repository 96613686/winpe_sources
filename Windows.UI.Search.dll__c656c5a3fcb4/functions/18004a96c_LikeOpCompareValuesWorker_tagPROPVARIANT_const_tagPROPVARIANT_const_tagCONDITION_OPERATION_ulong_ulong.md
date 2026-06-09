# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x18004a96c`
- end: `0x18004ac15`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `681`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800477e8`

## callees

- `0x180013810`
- `0x180043cd4`
- `0x180043f98`
- `0x180044b70`
- `0x180046818`
- `0x180048080`
- `0x18004889c`
- `0x18004a96c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004aae1`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004aba0`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004abed`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004aae1`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004aba0`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18004abed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abc2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18004aaab`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecExW` at `0x18004aaab`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004a9a3`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004a9b6`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004a9a3`
- `PROPSYS!PropVariantToStringWithDefault` at `0x18004a9b6`

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
                  if ( StringCchCopyW((unsigned __int16 *)v18 + 6, 0x104u, v13) >= 0 )
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
0x18004a96c  mov     r11, rsp
0x18004a96f  mov     [r11+8], rbx
0x18004a973  mov     [r11+10h], rbp
0x18004a977  push    rsi
0x18004a978  push    rdi
0x18004a979  push    r13
0x18004a97b  push    r14
0x18004a97d  push    r15
0x18004a97f  sub     rsp, 50h
0x18004a983  mov     rax, rdx
0x18004a986  mov     rbx, rcx
0x18004a989  xor     r13d, r13d
0x18004a98c  lea     rdx, pszDefault; pszDefault
0x18004a993  mov     rcx, rax; propvarIn
0x18004a996  mov     [r11+18h], r13d
0x18004a99a  mov     r15d, r9d
0x18004a99d  mov     esi, r8d
0x18004a9a0  mov     edi, r13d
0x18004a9a3  call    cs:__imp_PropVariantToStringWithDefault
0x18004a9a9  lea     rdx, pszDefault; pszDefault
0x18004a9b0  mov     rcx, rbx; propvarIn
0x18004a9b3  mov     r14, rax
0x18004a9b6  call    cs:__imp_PropVariantToStringWithDefault
0x18004a9bc  mov     ecx, esi
0x18004a9be  mov     rbp, rax
0x18004a9c1  sub     ecx, 7
0x18004a9c4  jz      loc_18004AB0E
0x18004a9ca  sub     ecx, 1
0x18004a9cd  jz      loc_18004AB01
0x18004a9d3  sub     ecx, 1
0x18004a9d6  jz      loc_18004AAEE
0x18004a9dc  sub     ecx, 1
0x18004a9df  jz      loc_18004AABC
0x18004a9e5  sub     ecx, 1
0x18004a9e8  jz      loc_18004AAA2
0x18004a9ee  sub     ecx, 1; unsigned __int64
0x18004a9f1  jz      short loc_18004A9FC
0x18004a9f3  cmp     ecx, 1
0x18004a9f6  jnz     loc_18004ABFA
0x18004a9fc  call    ??2CZeroInitNew@@SAPEAX_KAEBUnothrow_t@std@@@Z; CZeroInitNew::operator new(unsigned __int64,std::nothrow_t const &)
0x18004aa01  test    rax, rax
0x18004aa04  jz      loc_18004ABFA
0x18004aa0a  mov     edx, esi; enum tagCONDITION_OPERATION
0x18004aa0c  mov     rcx, rax; this
0x18004aa0f  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x18004aa14  mov     rbx, rax
0x18004aa17  test    rax, rax
0x18004aa1a  jz      loc_18004ABFA
0x18004aa20  mov     [rax+228h], r15d
0x18004aa27  mov     eax, [rsp+78h+arg_20]
0x18004aa2e  mov     [rbx+22Ch], eax
0x18004aa34  cmp     r15d, 412h
0x18004aa3b  jnz     short loc_18004AA66
0x18004aa3d  mov     rdx, rbp; unsigned __int16 *
0x18004aa40  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18004aa47  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18004aa4c  test    eax, eax
0x18004aa4e  jnz     short loc_18004AA66
0x18004aa50  lea     r8, [rbx+218h]; unsigned __int16 **
0x18004aa57  mov     rdx, rbp; unsigned __int16 *
0x18004aa5a  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18004aa61  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18004aa66  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x18004aa6a  mov     r8, rbp; unsigned __int16 *
0x18004aa6d  mov     edx, 104h; unsigned __int64
0x18004aa72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004aa77  test    eax, eax
0x18004aa79  js      short loc_18004AA95
0x18004aa7b  lea     r8, [rsp+78h+arg_10]; int *
0x18004aa83  mov     rdx, r14; unsigned __int16 *
0x18004aa86  mov     rcx, rbx; this
0x18004aa89  call    ?WordMatch@CWordMatch@@QEAAJPEBGPEAH@Z; CWordMatch::WordMatch(ushort const *,int *)
0x18004aa8e  mov     edi, [rsp+78h+arg_10]
0x18004aa95  mov     rcx, rbx; this
0x18004aa98  call    ?Release@CWordMatch@@UEAAKXZ; CWordMatch::Release(void)
0x18004aa9d  jmp     loc_18004ABFA
0x18004aaa2  xor     r8d, r8d; dwFlags
0x18004aaa5  mov     rdx, rbp; pszSpec
0x18004aaa8  mov     rcx, r14; pszFile
0x18004aaab  call    cs:__imp_PathMatchSpecExW
0x18004aab1  test    eax, eax
0x18004aab3  setz    dil
0x18004aab7  jmp     loc_18004ABFA
0x18004aabc  mov     edx, [rsp+78h+arg_20]
0x18004aac3  or      esi, 0FFFFFFFFh
0x18004aac6  mov     [rsp+78h+pcchFound], r13; pcchFound
0x18004aacb  bts     edx, 16h; dwFindNLSStringFlags
0x18004aacf  mov     [rsp+78h+cchValue], esi; cchValue
0x18004aad3  mov     r9d, esi; cchSource
0x18004aad6  mov     r8, r14; lpStringSource
0x18004aad9  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x18004aade  mov     ecx, r15d; Locale
0x18004aae1  call    cs:__imp_FindNLSString
0x18004aae7  mov     edi, eax
0x18004aae9  jmp     loc_18004ABF7
0x18004aaee  mov     edx, [rsp+78h+arg_20]
0x18004aaf5  bts     edx, 16h
0x18004aaf9  or      esi, 0FFFFFFFFh
0x18004aafc  jmp     loc_18004ABD6
0x18004ab01  mov     edx, [rsp+78h+arg_20]
0x18004ab08  bts     edx, 15h
0x18004ab0c  jmp     short loc_18004AAF9
0x18004ab0e  mov     ebx, [rsp+78h+arg_20]
0x18004ab15  or      esi, 0FFFFFFFFh
0x18004ab18  cmp     r15d, 412h
0x18004ab1f  jnz     loc_18004ABD0
0x18004ab25  mov     rdx, r14; unsigned __int16 *
0x18004ab28  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18004ab2f  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x18004ab34  test    eax, eax
0x18004ab36  jnz     loc_18004ABD0
0x18004ab3c  lea     r8, [rsp+78h+lpStringSource]; unsigned __int16 **
0x18004ab41  mov     [rsp+78h+lpStringSource], r13
0x18004ab46  mov     rdx, r14; unsigned __int16 *
0x18004ab49  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18004ab50  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18004ab55  mov     r13d, eax
0x18004ab58  test    eax, eax
0x18004ab5a  js      short loc_18004ABC8
0x18004ab5c  lea     r8, [rsp+78h+var_30]; unsigned __int16 **
0x18004ab61  mov     [rsp+78h+var_30], rdi
0x18004ab66  mov     rdx, rbp; unsigned __int16 *
0x18004ab69  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18004ab70  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18004ab75  mov     r13d, eax
0x18004ab78  test    eax, eax
0x18004ab7a  js      short loc_18004ABBD
0x18004ab7c  mov     r8, [rsp+78h+lpStringSource]; lpStringSource
0x18004ab81  mov     edx, ebx
0x18004ab83  mov     rbx, [rsp+78h+var_30]
0x18004ab88  bts     edx, 14h; dwFindNLSStringFlags
0x18004ab8c  mov     [rsp+78h+pcchFound], rdi; pcchFound
0x18004ab91  mov     r9d, esi; cchSource
0x18004ab94  mov     [rsp+78h+cchValue], esi; cchValue
0x18004ab98  mov     ecx, r15d; Locale
0x18004ab9b  mov     [rsp+78h+lpStringValue], rbx; lpStringValue
0x18004aba0  call    cs:__imp_FindNLSString
0x18004aba6  mov     edi, eax
0x18004aba8  mov     rcx, rbx; pv
0x18004abab  not     edi
0x18004abad  shr     edi, 1Fh
0x18004abb0  call    cs:__imp_CoTaskMemFree
0x18004abb6  mov     ebx, [rsp+78h+arg_20]
0x18004abbd  mov     rcx, [rsp+78h+lpStringSource]; pv
0x18004abc2  call    cs:__imp_CoTaskMemFree
0x18004abc8  test    r13d, r13d
0x18004abcb  jz      short loc_18004ABFA
0x18004abcd  xor     r13d, r13d
0x18004abd0  bts     ebx, 14h
0x18004abd4  mov     edx, ebx; dwFindNLSStringFlags
0x18004abd6  mov     [rsp+78h+pcchFound], r13; pcchFound
0x18004abdb  mov     r9d, esi; cchSource
0x18004abde  mov     [rsp+78h+cchValue], esi; cchValue
0x18004abe2  mov     r8, r14; lpStringSource
0x18004abe5  mov     ecx, r15d; Locale
0x18004abe8  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x18004abed  call    cs:__imp_FindNLSString
0x18004abf3  mov     edi, eax
0x18004abf5  not     edi
0x18004abf7  shr     edi, 1Fh
0x18004abfa  lea     r11, [rsp+78h+var_28]
0x18004abff  mov     eax, edi
0x18004ac01  mov     rbx, [r11+30h]
0x18004ac05  mov     rbp, [r11+38h]
0x18004ac09  mov     rsp, r11
0x18004ac0c  pop     r15
0x18004ac0e  pop     r14
0x18004ac10  pop     r13
0x18004ac12  pop     rdi
0x18004ac13  pop     rsi
0x18004ac14  retn
```
