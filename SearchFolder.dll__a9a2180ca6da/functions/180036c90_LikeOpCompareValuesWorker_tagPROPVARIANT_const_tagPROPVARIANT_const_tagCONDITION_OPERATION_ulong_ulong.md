# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x180036c90`
- end: `0x180036f43`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `691`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e5cc`

## callees

- `0x180004740`
- `0x18000ecc4`
- `0x180027a78`
- `0x180029d08`
- `0x18002d70c`
- `0x18002f990`
- `0x180030da4`
- `0x180036c90`

## import_xrefs

- `SHLWAPI!PathMatchSpecExW` at `0x180036dd9`
- `SHLWAPI!PathMatchSpecExW` at `0x180036dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ef0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036ef0`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036e0f`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036ece`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036f1b`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036e0f`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036ece`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180036f1b`
- `PROPSYS!PropVariantToStringWithDefault` at `0x180036cc7`
- `PROPSYS!PropVariantToStringWithDefault` at `0x180036cda`
- `PROPSYS!PropVariantToStringWithDefault` at `0x180036cc7`
- `PROPSYS!PropVariantToStringWithDefault` at `0x180036cda`

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
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // rbp
  WCHAR *v13; // rax
  CWordMatch *v14; // rax
  const unsigned __int16 *v15; // r8
  CWordMatch *v16; // rbx
  unsigned int NLSString; // edi
  DWORD v18; // edx
  unsigned int v19; // ebx
  int v20; // r13d
  unsigned int v21; // edx
  WCHAR *v22; // rbx
  LPCWSTR lpStringSource; // [rsp+40h] [rbp-38h] BYREF
  LPCWSTR v25; // [rsp+48h] [rbp-30h] BYREF
  int v26; // [rsp+90h] [rbp+18h] BYREF

  v26 = 0;
  v8 = 0;
  v9 = PropVariantToStringWithDefault(a2, &psz);
  lpStringValue = PropVariantToStringWithDefault(propvarIn, &psz);
  v12 = lpStringValue;
  if ( a3 != COP_VALUE_STARTSWITH )
  {
    if ( a3 == COP_VALUE_ENDSWITH )
    {
      v18 = a5 | 0x200000;
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
          else if ( (unsigned int)(a3 - 12) <= 1 )
          {
            v13 = (WCHAR *)operator new(0x230u);
            v25 = v13;
            if ( v13 )
            {
              v14 = CWordMatch::CWordMatch((CWordMatch *)v13, a3);
              v16 = v14;
              if ( v14 )
              {
                *((_DWORD *)v14 + 138) = Locale;
                *((_DWORD *)v14 + 139) = a5;
                if ( Locale == 1042
                  && !CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v12, v15) )
                {
                  CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                    (CKoreanDecomposition *)g_koreanDecomposition,
                    v12,
                    (unsigned __int16 **)v16 + 67);
                }
                if ( StringCchCopyW((unsigned __int16 *)v16 + 6, 0x104u, v12) >= 0 )
                {
                  CWordMatch::WordMatch(v16, v9, &v26);
                  v8 = v26;
                }
                CWordMatch::Release(v16);
              }
            }
          }
          return v8;
        }
        NLSString = FindNLSString(Locale, a5 | 0x400000, v9, -1, lpStringValue, -1, 0);
        return NLSString >> 31;
      }
      v18 = a5 | 0x400000;
    }
LABEL_27:
    NLSString = ~FindNLSString(Locale, v18, v9, -1, v12, -1, 0);
    return NLSString >> 31;
  }
  v19 = a5;
  if ( Locale != 1042 || CScriptAutoDetection::HasScript((CScriptAutoDetection *)g_scriptAutoDetection, v9, v11) )
    goto LABEL_26;
  lpStringSource = 0;
  v20 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
          (CKoreanDecomposition *)g_koreanDecomposition,
          v9,
          (unsigned __int16 **)&lpStringSource);
  if ( v20 >= 0 )
  {
    v25 = 0;
    v20 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
            (CKoreanDecomposition *)g_koreanDecomposition,
            v12,
            (unsigned __int16 **)&v25);
    if ( v20 >= 0 )
    {
      v21 = v19;
      v22 = (WCHAR *)v25;
      v8 = FindNLSString(0x412u, v21 | 0x100000, lpStringSource, -1, v25, -1, 0) >= 0;
      CoTaskMemFree(v22);
      v19 = a5;
    }
    CoTaskMemFree((LPVOID)lpStringSource);
  }
  if ( v20 )
  {
LABEL_26:
    v18 = v19 | 0x100000;
    goto LABEL_27;
  }
  return v8;
}

```

## disassembly

```asm
0x180036c90  mov     r11, rsp
0x180036c93  mov     [r11+8], rbx
0x180036c97  mov     [r11+10h], rbp
0x180036c9b  push    rsi
0x180036c9c  push    rdi
0x180036c9d  push    r13
0x180036c9f  push    r14
0x180036ca1  push    r15
0x180036ca3  sub     rsp, 50h
0x180036ca7  mov     rax, rdx
0x180036caa  mov     rbx, rcx
0x180036cad  xor     r13d, r13d
0x180036cb0  lea     rdx, psz; pszDefault
0x180036cb7  mov     rcx, rax; propvarIn
0x180036cba  mov     [r11+18h], r13d
0x180036cbe  mov     r15d, r9d
0x180036cc1  mov     esi, r8d
0x180036cc4  mov     edi, r13d
0x180036cc7  call    cs:__imp_PropVariantToStringWithDefault
0x180036ccd  lea     rdx, psz; pszDefault
0x180036cd4  mov     rcx, rbx; propvarIn
0x180036cd7  mov     r14, rax
0x180036cda  call    cs:__imp_PropVariantToStringWithDefault
0x180036ce0  mov     ecx, esi
0x180036ce2  mov     rbp, rax
0x180036ce5  sub     ecx, 7
0x180036ce8  jz      loc_180036E3C
0x180036cee  sub     ecx, 1
0x180036cf1  jz      loc_180036E2F
0x180036cf7  sub     ecx, 1
0x180036cfa  jz      loc_180036E1C
0x180036d00  sub     ecx, 1
0x180036d03  jz      loc_180036DEA
0x180036d09  sub     ecx, 1
0x180036d0c  jz      loc_180036DD0
0x180036d12  sub     ecx, 1
0x180036d15  jz      short loc_180036D20
0x180036d17  cmp     ecx, 1
0x180036d1a  jnz     loc_180036F28
0x180036d20  mov     ecx, 230h; unsigned __int64
0x180036d25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036d2a  mov     [rsp+78h+var_30], rax
0x180036d2f  test    rax, rax
0x180036d32  jz      loc_180036F28
0x180036d38  mov     edx, esi; enum tagCONDITION_OPERATION
0x180036d3a  mov     rcx, rax; this
0x180036d3d  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x180036d42  mov     rbx, rax
0x180036d45  test    rax, rax
0x180036d48  jz      loc_180036F28
0x180036d4e  mov     [rax+228h], r15d
0x180036d55  mov     eax, [rsp+78h+arg_20]
0x180036d5c  mov     [rbx+22Ch], eax
0x180036d62  cmp     r15d, 412h
0x180036d69  jnz     short loc_180036D94
0x180036d6b  mov     rdx, rbp; unsigned __int16 *
0x180036d6e  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x180036d75  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x180036d7a  test    eax, eax
0x180036d7c  jnz     short loc_180036D94
0x180036d7e  lea     r8, [rbx+218h]; unsigned __int16 **
0x180036d85  mov     rdx, rbp; unsigned __int16 *
0x180036d88  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180036d8f  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180036d94  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x180036d98  mov     r8, rbp; unsigned __int16 *
0x180036d9b  mov     edx, 104h; unsigned __int64
0x180036da0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036da5  test    eax, eax
0x180036da7  js      short loc_180036DC3
0x180036da9  lea     r8, [rsp+78h+arg_10]; int *
0x180036db1  mov     rdx, r14; unsigned __int16 *
0x180036db4  mov     rcx, rbx; this
0x180036db7  call    ?WordMatch@CWordMatch@@QEAAJPEBGPEAH@Z; CWordMatch::WordMatch(ushort const *,int *)
0x180036dbc  mov     edi, [rsp+78h+arg_10]
0x180036dc3  mov     rcx, rbx; this
0x180036dc6  call    ?Release@CWordMatch@@UEAAKXZ; CWordMatch::Release(void)
0x180036dcb  jmp     loc_180036F28
0x180036dd0  xor     r8d, r8d; dwFlags
0x180036dd3  mov     rdx, rbp; pszSpec
0x180036dd6  mov     rcx, r14; pszFile
0x180036dd9  call    cs:__imp_PathMatchSpecExW
0x180036ddf  test    eax, eax
0x180036de1  setz    dil
0x180036de5  jmp     loc_180036F28
0x180036dea  mov     edx, [rsp+78h+arg_20]
0x180036df1  or      esi, 0FFFFFFFFh
0x180036df4  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180036df9  bts     edx, 16h; dwFindNLSStringFlags
0x180036dfd  mov     [rsp+78h+cchValue], esi; cchValue
0x180036e01  mov     r9d, esi; cchSource
0x180036e04  mov     r8, r14; lpStringSource
0x180036e07  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x180036e0c  mov     ecx, r15d; Locale
0x180036e0f  call    cs:__imp_FindNLSString
0x180036e15  mov     edi, eax
0x180036e17  jmp     loc_180036F25
0x180036e1c  mov     edx, [rsp+78h+arg_20]
0x180036e23  bts     edx, 16h
0x180036e27  or      esi, 0FFFFFFFFh
0x180036e2a  jmp     loc_180036F04
0x180036e2f  mov     edx, [rsp+78h+arg_20]
0x180036e36  bts     edx, 15h
0x180036e3a  jmp     short loc_180036E27
0x180036e3c  mov     ebx, [rsp+78h+arg_20]
0x180036e43  or      esi, 0FFFFFFFFh
0x180036e46  cmp     r15d, 412h
0x180036e4d  jnz     loc_180036EFE
0x180036e53  mov     rdx, r14; unsigned __int16 *
0x180036e56  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x180036e5d  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x180036e62  test    eax, eax
0x180036e64  jnz     loc_180036EFE
0x180036e6a  lea     r8, [rsp+78h+lpStringSource]; unsigned __int16 **
0x180036e6f  mov     [rsp+78h+lpStringSource], r13
0x180036e74  mov     rdx, r14; unsigned __int16 *
0x180036e77  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180036e7e  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180036e83  mov     r13d, eax
0x180036e86  test    eax, eax
0x180036e88  js      short loc_180036EF6
0x180036e8a  lea     r8, [rsp+78h+var_30]; unsigned __int16 **
0x180036e8f  mov     [rsp+78h+var_30], rdi
0x180036e94  mov     rdx, rbp; unsigned __int16 *
0x180036e97  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x180036e9e  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180036ea3  mov     r13d, eax
0x180036ea6  test    eax, eax
0x180036ea8  js      short loc_180036EEB
0x180036eaa  mov     r8, [rsp+78h+lpStringSource]; lpStringSource
0x180036eaf  mov     edx, ebx
0x180036eb1  mov     rbx, [rsp+78h+var_30]
0x180036eb6  bts     edx, 14h; dwFindNLSStringFlags
0x180036eba  mov     [rsp+78h+pcchFound], rdi; pcchFound
0x180036ebf  mov     r9d, esi; cchSource
0x180036ec2  mov     [rsp+78h+cchValue], esi; cchValue
0x180036ec6  mov     ecx, r15d; Locale
0x180036ec9  mov     [rsp+78h+lpStringValue], rbx; lpStringValue
0x180036ece  call    cs:__imp_FindNLSString
0x180036ed4  mov     edi, eax
0x180036ed6  mov     rcx, rbx; pv
0x180036ed9  not     edi
0x180036edb  shr     edi, 1Fh
0x180036ede  call    cs:__imp_CoTaskMemFree
0x180036ee4  mov     ebx, [rsp+78h+arg_20]
0x180036eeb  mov     rcx, [rsp+78h+lpStringSource]; pv
0x180036ef0  call    cs:__imp_CoTaskMemFree
0x180036ef6  test    r13d, r13d
0x180036ef9  jz      short loc_180036F28
0x180036efb  xor     r13d, r13d
0x180036efe  bts     ebx, 14h
0x180036f02  mov     edx, ebx; dwFindNLSStringFlags
0x180036f04  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180036f09  mov     r9d, esi; cchSource
0x180036f0c  mov     [rsp+78h+cchValue], esi; cchValue
0x180036f10  mov     r8, r14; lpStringSource
0x180036f13  mov     ecx, r15d; Locale
0x180036f16  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x180036f1b  call    cs:__imp_FindNLSString
0x180036f21  mov     edi, eax
0x180036f23  not     edi
0x180036f25  shr     edi, 1Fh
0x180036f28  lea     r11, [rsp+78h+var_28]
0x180036f2d  mov     eax, edi
0x180036f2f  mov     rbx, [r11+30h]
0x180036f33  mov     rbp, [r11+38h]
0x180036f37  mov     rsp, r11
0x180036f3a  pop     r15
0x180036f3c  pop     r14
0x180036f3e  pop     r13
0x180036f40  pop     rdi
0x180036f41  pop     rsi
0x180036f42  retn
```
