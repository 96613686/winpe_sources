# _LikeOpCompareValuesWorker(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,ulong,ulong)

- ea: `0x1802317a8`
- end: `0x180231a82`
- name: `?_LikeOpCompareValuesWorker@@YAHAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@KK@Z`
- size: `730`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarIn, PROPVARIANT *, enum tagCONDITION_OPERATION, LCID Locale, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18022df34`

## callees

- `0x18001a608`
- `0x18022963c`
- `0x180229a50`
- `0x18022ac5c`
- `0x18022cf2c`
- `0x18022eab0`
- `0x18022f308`
- `0x1802317a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231a22`
- `SHLWAPI!PathMatchSpecExW` at `0x1802318f3`
- `SHLWAPI!PathMatchSpecExW` at `0x1802318f3`
- `KERNEL32!FindNLSString` at `0x18023192f`
- `KERNEL32!FindNLSString` at `0x1802319f4`
- `KERNEL32!FindNLSString` at `0x180231a53`
- `KERNEL32!FindNLSString` at `0x18023192f`
- `KERNEL32!FindNLSString` at `0x1802319f4`
- `KERNEL32!FindNLSString` at `0x180231a53`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1802317df`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1802317f8`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1802317df`
- `PROPSYS!PropVariantToStringWithDefault` at `0x1802317f8`

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
  v9 = PropVariantToStringWithDefault(a2, &LocaleName);
  lpStringValue = PropVariantToStringWithDefault(propvarIn, &LocaleName);
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
                    && !CScriptAutoDetection::HasScript((CScriptAutoDetection *)&g_scriptAutoDetection, v13, v17) )
                  {
                    CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                      (CKoreanDecomposition *)&g_koreanDecomposition,
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
  if ( Locale != 1042 || CScriptAutoDetection::HasScript((CScriptAutoDetection *)&g_scriptAutoDetection, v9, v12) )
    goto LABEL_26;
  lpStringSource = 0;
  v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
          (CKoreanDecomposition *)&g_koreanDecomposition,
          v9,
          (unsigned __int16 **)&lpStringSource);
  if ( v22 >= 0 )
  {
    v27 = 0;
    v22 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
            (CKoreanDecomposition *)&g_koreanDecomposition,
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
0x1802317a8  mov     r11, rsp
0x1802317ab  mov     [r11+8], rbx
0x1802317af  mov     [r11+10h], rbp
0x1802317b3  push    rsi
0x1802317b4  push    rdi
0x1802317b5  push    r13
0x1802317b7  push    r14
0x1802317b9  push    r15
0x1802317bb  sub     rsp, 50h
0x1802317bf  mov     rax, rdx
0x1802317c2  mov     rbx, rcx
0x1802317c5  xor     r13d, r13d
0x1802317c8  lea     rdx, LocaleName; pszDefault
0x1802317cf  mov     rcx, rax; propvarIn
0x1802317d2  mov     [r11+18h], r13d
0x1802317d6  mov     r15d, r9d
0x1802317d9  mov     esi, r8d
0x1802317dc  mov     edi, r13d
0x1802317df  call    cs:__imp_PropVariantToStringWithDefault
0x1802317e6  nop     dword ptr [rax+rax+00h]
0x1802317eb  lea     rdx, LocaleName; pszDefault
0x1802317f2  mov     rcx, rbx; propvarIn
0x1802317f5  mov     r14, rax
0x1802317f8  call    cs:__imp_PropVariantToStringWithDefault
0x1802317ff  nop     dword ptr [rax+rax+00h]
0x180231804  mov     ecx, esi
0x180231806  mov     rbp, rax
0x180231809  sub     ecx, 7
0x18023180c  jz      loc_180231962
0x180231812  sub     ecx, 1
0x180231815  jz      loc_180231955
0x18023181b  sub     ecx, 1
0x18023181e  jz      loc_180231942
0x180231824  sub     ecx, 1
0x180231827  jz      loc_18023190A
0x18023182d  sub     ecx, 1
0x180231830  jz      loc_1802318EA
0x180231836  sub     ecx, 1; unsigned __int64
0x180231839  jz      short loc_180231844
0x18023183b  cmp     ecx, 1
0x18023183e  jnz     loc_180231A66
0x180231844  call    ??2CZeroInitNew@@SAPEAX_KAEBUnothrow_t@std@@@Z; CZeroInitNew::operator new(unsigned __int64,std::nothrow_t const &)
0x180231849  test    rax, rax
0x18023184c  jz      loc_180231A66
0x180231852  mov     edx, esi; enum tagCONDITION_OPERATION
0x180231854  mov     rcx, rax; this
0x180231857  call    ??0CWordMatch@@QEAA@W4tagCONDITION_OPERATION@@@Z; CWordMatch::CWordMatch(tagCONDITION_OPERATION)
0x18023185c  mov     rbx, rax
0x18023185f  test    rax, rax
0x180231862  jz      loc_180231A66
0x180231868  mov     [rax+228h], r15d
0x18023186f  mov     eax, [rsp+78h+arg_20]
0x180231876  mov     [rbx+22Ch], eax
0x18023187c  cmp     r15d, 412h
0x180231883  jnz     short loc_1802318AE
0x180231885  mov     rdx, rbp; unsigned __int16 *
0x180231888  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x18023188f  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x180231894  test    eax, eax
0x180231896  jnz     short loc_1802318AE
0x180231898  lea     r8, [rbx+218h]; unsigned __int16 **
0x18023189f  mov     rdx, rbp; unsigned __int16 *
0x1802318a2  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1802318a9  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x1802318ae  lea     rcx, [rbx+0Ch]; unsigned __int16 *
0x1802318b2  mov     r8, rbp; unsigned __int16 *
0x1802318b5  mov     edx, 104h; unsigned __int64
0x1802318ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802318bf  test    eax, eax
0x1802318c1  js      short loc_1802318DD
0x1802318c3  lea     r8, [rsp+78h+arg_10]; int *
0x1802318cb  mov     rdx, r14; unsigned __int16 *
0x1802318ce  mov     rcx, rbx; this
0x1802318d1  call    ?WordMatch@CWordMatch@@QEAAJPEBGPEAH@Z; CWordMatch::WordMatch(ushort const *,int *)
0x1802318d6  mov     edi, [rsp+78h+arg_10]
0x1802318dd  mov     rcx, rbx; this
0x1802318e0  call    ?Release@CWordMatch@@UEAAKXZ; CWordMatch::Release(void)
0x1802318e5  jmp     loc_180231A66
0x1802318ea  xor     r8d, r8d; dwFlags
0x1802318ed  mov     rdx, rbp; pszSpec
0x1802318f0  mov     rcx, r14; pszFile
0x1802318f3  call    cs:__imp_PathMatchSpecExW
0x1802318fa  nop     dword ptr [rax+rax+00h]
0x1802318ff  test    eax, eax
0x180231901  setz    dil
0x180231905  jmp     loc_180231A66
0x18023190a  mov     edx, [rsp+78h+arg_20]
0x180231911  or      esi, 0FFFFFFFFh
0x180231914  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180231919  bts     edx, 16h; dwFindNLSStringFlags
0x18023191d  mov     [rsp+78h+cchValue], esi; cchValue
0x180231921  mov     r9d, esi; cchSource
0x180231924  mov     r8, r14; lpStringSource
0x180231927  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x18023192c  mov     ecx, r15d; Locale
0x18023192f  call    cs:__imp_FindNLSString
0x180231936  nop     dword ptr [rax+rax+00h]
0x18023193b  mov     edi, eax
0x18023193d  jmp     loc_180231A63
0x180231942  mov     edx, [rsp+78h+arg_20]
0x180231949  bts     edx, 16h
0x18023194d  or      esi, 0FFFFFFFFh
0x180231950  jmp     loc_180231A3C
0x180231955  mov     edx, [rsp+78h+arg_20]
0x18023195c  bts     edx, 15h
0x180231960  jmp     short loc_18023194D
0x180231962  mov     ebx, [rsp+78h+arg_20]
0x180231969  or      esi, 0FFFFFFFFh
0x18023196c  cmp     r15d, 412h
0x180231973  jnz     loc_180231A36
0x180231979  mov     rdx, r14; unsigned __int16 *
0x18023197c  lea     rcx, ?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; this
0x180231983  call    ?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z; CScriptAutoDetection::HasScript(ushort const *,ushort const *)
0x180231988  test    eax, eax
0x18023198a  jnz     loc_180231A36
0x180231990  lea     r8, [rsp+78h+lpStringSource]; unsigned __int16 **
0x180231995  mov     [rsp+78h+lpStringSource], r13
0x18023199a  mov     rdx, r14; unsigned __int16 *
0x18023199d  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1802319a4  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x1802319a9  mov     r13d, eax
0x1802319ac  test    eax, eax
0x1802319ae  js      short loc_180231A2E
0x1802319b0  lea     r8, [rsp+78h+var_30]; unsigned __int16 **
0x1802319b5  mov     [rsp+78h+var_30], rdi
0x1802319ba  mov     rdx, rbp; unsigned __int16 *
0x1802319bd  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1802319c4  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x1802319c9  mov     r13d, eax
0x1802319cc  test    eax, eax
0x1802319ce  js      short loc_180231A1D
0x1802319d0  mov     r8, [rsp+78h+lpStringSource]; lpStringSource
0x1802319d5  mov     edx, ebx
0x1802319d7  mov     rbx, [rsp+78h+var_30]
0x1802319dc  bts     edx, 14h; dwFindNLSStringFlags
0x1802319e0  mov     [rsp+78h+pcchFound], rdi; pcchFound
0x1802319e5  mov     r9d, esi; cchSource
0x1802319e8  mov     [rsp+78h+cchValue], esi; cchValue
0x1802319ec  mov     ecx, r15d; Locale
0x1802319ef  mov     [rsp+78h+lpStringValue], rbx; lpStringValue
0x1802319f4  call    cs:__imp_FindNLSString
0x1802319fb  nop     dword ptr [rax+rax+00h]
0x180231a00  mov     edi, eax
0x180231a02  mov     rcx, rbx; pv
0x180231a05  not     edi
0x180231a07  shr     edi, 1Fh
0x180231a0a  call    cs:__imp_CoTaskMemFree
0x180231a11  nop     dword ptr [rax+rax+00h]
0x180231a16  mov     ebx, [rsp+78h+arg_20]
0x180231a1d  mov     rcx, [rsp+78h+lpStringSource]; pv
0x180231a22  call    cs:__imp_CoTaskMemFree
0x180231a29  nop     dword ptr [rax+rax+00h]
0x180231a2e  test    r13d, r13d
0x180231a31  jz      short loc_180231A66
0x180231a33  xor     r13d, r13d
0x180231a36  bts     ebx, 14h
0x180231a3a  mov     edx, ebx; dwFindNLSStringFlags
0x180231a3c  mov     [rsp+78h+pcchFound], r13; pcchFound
0x180231a41  mov     r9d, esi; cchSource
0x180231a44  mov     [rsp+78h+cchValue], esi; cchValue
0x180231a48  mov     r8, r14; lpStringSource
0x180231a4b  mov     ecx, r15d; Locale
0x180231a4e  mov     [rsp+78h+lpStringValue], rbp; lpStringValue
0x180231a53  call    cs:__imp_FindNLSString
0x180231a5a  nop     dword ptr [rax+rax+00h]
0x180231a5f  mov     edi, eax
0x180231a61  not     edi
0x180231a63  shr     edi, 1Fh
0x180231a66  lea     r11, [rsp+78h+var_28]
0x180231a6b  mov     eax, edi
0x180231a6d  mov     rbx, [r11+30h]
0x180231a71  mov     rbp, [r11+38h]
0x180231a75  mov     rsp, r11
0x180231a78  pop     r15
0x180231a7a  pop     r14
0x180231a7c  pop     r13
0x180231a7e  pop     rdi
0x180231a7f  pop     rsi
0x180231a80  retn
```
