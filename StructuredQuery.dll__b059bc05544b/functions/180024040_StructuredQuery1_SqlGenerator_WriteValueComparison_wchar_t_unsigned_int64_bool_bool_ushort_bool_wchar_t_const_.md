# StructuredQuery1::SqlGenerator::WriteValueComparison(wchar_t *,unsigned __int64,bool,bool,ushort,bool,wchar_t const *,wchar_t const *,wchar_t const *,tagPROPVARIANT const &,wchar_t * *,unsigned __int64 *)

- ea: `0x180024040`
- end: `0x1800243b8`
- name: `?WriteValueComparison@SqlGenerator@StructuredQuery1@@AEAAJPEA_W_K_N2G2PEB_W33AEBUtagPROPVARIANT@@PEAPEA_WPEA_K@Z`
- size: `888`
- prototype: `int(StructuredQuery1::SqlGenerator *__hidden this, wchar_t *, unsigned __int64, bool, bool, unsigned __int16, bool, const wchar_t *, const wchar_t *, const wchar_t *, const struct tagPROPVARIANT *, wchar_t **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004a374`
- `0x1800810fc`

## callees

- `0x180023e60`
- `0x180024040`
- `0x1800243c0`
- `0x18002e5c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800240c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800242e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800240c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800242e5`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SqlGenerator::WriteValueComparison(
        StructuredQuery1::SqlGenerator *this,
        wchar_t *a2,
        wchar_t *a3,
        char a4,
        bool a5,
        unsigned __int16 a6,
        bool a7,
        const wchar_t *a8,
        PCNZWCH lpString1,
        const wchar_t *a10,
        const struct tagPROPVARIANT *a11,
        wchar_t **a12,
        unsigned __int64 *a13)
{
  const struct tagPROPVARIANT *v13; // rbx
  const WCHAR *v15; // rsi
  unsigned int v17; // edi
  signed int v18; // r8d
  wchar_t *v19; // rax
  int v20; // eax
  wchar_t *v21; // r10
  unsigned __int64 v22; // r9
  __int64 v23; // rcx
  const wchar_t *v24; // rdx
  unsigned __int64 v25; // r11
  wchar_t *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  wchar_t *v31; // rax
  signed int v32; // eax
  int v33; // eax
  const wchar_t *v34; // rcx
  unsigned int cchCount2; // [rsp+28h] [rbp-28h]
  unsigned int cchCount2a; // [rsp+28h] [rbp-28h]
  unsigned __int64 v37; // [rsp+90h] [rbp+40h] BYREF
  wchar_t *v38; // [rsp+98h] [rbp+48h] BYREF
  wchar_t *v39; // [rsp+A0h] [rbp+50h] BYREF

  v39 = a3;
  v38 = a2;
  v37 = (unsigned __int64)this;
  v13 = a11;
  v15 = a10;
  if ( !a7 )
    v15 = lpString1;
  if ( a11->vt < 2u )
  {
    v33 = CompareStringW(0x7Fu, 0, v15, -1, L"=", -1);
    v34 = L"NOT ";
    if ( v33 == 2 )
      v34 = (const wchar_t *)&cchOriginalDestLength;
    v32 = StringCchPrintfExW(a2, (unsigned __int64)a3, &v38, (unsigned __int64 *)&v39, 0, L"%s IS %sNULL", a8, v34);
    v22 = (unsigned __int64)v39;
    v21 = v38;
    goto LABEL_27;
  }
  v17 = 64;
  if ( a6 != 7 )
    v17 = 0;
  if ( !a4 )
  {
    v18 = StringCchPrintfExW(a2, (unsigned __int64)a3, &v38, (unsigned __int64 *)&v39, 0, L"%s %s ");
    if ( v18 < 0 )
      goto LABEL_37;
    v31 = v39;
    v37 = (unsigned __int64)v39;
    v39 = v38;
    if ( a5 && v13->vt == 31 )
      v32 = StringCchCopyExW(v38, (unsigned __int64)v31, v13->bstrVal, &v39, &v37, cchCount2a);
    else
      v32 = StructuredQuery1::ValueNormalization(v13, 2, v17, v38, v31, &v39, &v37);
    v21 = v39;
    v22 = v37;
LABEL_27:
    v18 = v32;
    goto LABEL_22;
  }
  CompareStringW(0x7Fu, 0, v15, -1, L"<>", -1);
  v18 = StringCchPrintfExW(a2, (unsigned __int64)a3, &v38, (unsigned __int64 *)&v39, 0, L"%s%s %s SOME ARRAY[");
  if ( v18 < 0 )
  {
LABEL_37:
    v22 = (unsigned __int64)v39;
    v21 = v38;
    goto LABEL_22;
  }
  v19 = v39;
  v37 = (unsigned __int64)v39;
  v39 = v38;
  if ( a5 && v13->vt == 31 )
    v20 = StringCchCopyExW(v38, (unsigned __int64)v19, v13->bstrVal, &v39, &v37, cchCount2);
  else
    v20 = StructuredQuery1::ValueNormalization(v13, 2, v17, v38, v19, &v39, &v37);
  v21 = v39;
  v18 = v20;
  v22 = v37;
  if ( v20 >= 0 )
  {
    if ( v37 )
    {
      if ( v37 > 0x7FFFFFFF )
      {
        v18 = -2147024809;
        *v39 = 0;
      }
      else
      {
        v23 = 2147483646;
        v24 = L"]";
        v25 = v37;
        v26 = v39;
        v27 = 0;
        do
        {
          if ( !v23 )
            break;
          if ( !*v24 )
            break;
          *v26++ = *v24++;
          --v23;
          ++v27;
          --v25;
        }
        while ( v25 );
        v28 = v27 - 1;
        v29 = v26 - 1;
        if ( v25 )
          v28 = v27;
        v21 += v28;
        v18 = v25 == 0 ? 0x8007007A : 0;
        if ( v25 )
          v29 = v26;
        v22 -= v28;
        *v29 = 0;
      }
    }
    else
    {
      v18 = -2147024809;
    }
  }
LABEL_22:
  *a12 = v21;
  *a13 = v22;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180024040  mov     r11, rsp
0x180024043  mov     [r11+20h], rbx
0x180024047  mov     [r11+18h], r8
0x18002404b  mov     [r11+10h], rdx
0x18002404f  mov     [r11+8], rcx
0x180024053  push    rbp
0x180024054  push    rsi
0x180024055  push    rdi
0x180024056  push    r12
0x180024058  push    r13
0x18002405a  push    r14
0x18002405c  push    r15
0x18002405e  mov     rbp, rsp
0x180024061  sub     rsp, 50h
0x180024065  mov     rbx, [rbp+arg_50]
0x18002406c  xor     r12d, r12d
0x18002406f  cmp     [rbp+arg_30], r12b
0x180024073  mov     r14, r8
0x180024076  mov     rsi, [rbp+arg_48]
0x18002407d  mov     r15, rdx
0x180024080  cmovz   rsi, [rbp+lpString1]
0x180024088  lea     r13d, [r12+2]
0x18002408d  cmp     [rbx], r13w
0x180024091  jb      loc_1800242C8
0x180024097  cmp     [rbp+arg_28], 7
0x18002409c  lea     edi, [r12+40h]
0x1800240a1  cmovnz  edi, r12d
0x1800240a5  test    r9b, r9b
0x1800240a8  jz      loc_180024239
0x1800240ae  xor     edx, edx; dwCmpFlags
0x1800240b0  lea     rax, asc_18009AA1C; "<>"
0x1800240b7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800240bb  mov     r8, rsi; lpString1
0x1800240be  mov     [r11-60h], r9d
0x1800240c2  mov     [r11-68h], rax
0x1800240c6  lea     ecx, [rdx+7Fh]; Locale
0x1800240c9  call    cs:__imp_CompareStringW
0x1800240cf  cmp     eax, r13d
0x1800240d2  lea     r8, cchOriginalDestLength
0x1800240d9  mov     rax, [rbp+arg_38]
0x1800240dd  lea     rdx, asc_18009AA0C; "="
0x1800240e4  cmovnz  rdx, rsi
0x1800240e8  lea     rcx, aNot_1; "NOT "
0x1800240ef  mov     [rsp+50h+var_10], rdx
0x1800240f4  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800240f8  mov     [rsp+50h+var_18], rax
0x1800240fd  cmovnz  rcx, r8
0x180024101  mov     [rsp+50h+var_20], rcx
0x180024106  lea     rax, aSSSSomeArray; "%s%s %s SOME ARRAY["
0x18002410d  mov     qword ptr [rsp+50h+cchCount2], rax; unsigned int
0x180024112  lea     r8, [rbp+arg_8]; wchar_t **
0x180024116  mov     rdx, r14; unsigned __int64
0x180024119  mov     [rsp+50h+lpString2], r12; unsigned int
0x18002411e  mov     rcx, r15; pszDest
0x180024121  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x180024126  mov     r8d, eax
0x180024129  test    eax, eax
0x18002412b  js      loc_1800243AB
0x180024131  mov     rax, [rbp+arg_10]
0x180024135  mov     rcx, [rbp+arg_8]; wchar_t *
0x180024139  mov     [rbp+arg_0], rax
0x18002413d  mov     [rbp+arg_10], rcx
0x180024141  cmp     [rbp+arg_20], r12b
0x180024145  jnz     loc_18002433C
0x18002414b  lea     rdx, [rbp+arg_0]
0x18002414f  mov     r9, rcx
0x180024152  mov     [rsp+50h+var_20], rdx
0x180024157  mov     r8d, edi
0x18002415a  lea     rdx, [rbp+arg_10]
0x18002415e  mov     rcx, rbx
0x180024161  mov     qword ptr [rsp+50h+cchCount2], rdx
0x180024166  mov     edx, r13d
0x180024169  mov     [rsp+50h+lpString2], rax
0x18002416e  call    ?ValueNormalization@StructuredQuery1@@YAJPEBUtagPROPVARIANT@@W4VALUE_NORMALIZATION_STYLE@1@W4PROPDESC_FORMAT_FLAGS@@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::ValueNormalization(tagPROPVARIANT const *,StructuredQuery1::VALUE_NORMALIZATION_STYLE,PROPDESC_FORMAT_FLAGS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180024173  mov     r10, [rbp+arg_10]
0x180024177  mov     r8d, eax
0x18002417a  mov     r9, [rbp+arg_0]
0x18002417e  test    eax, eax
0x180024180  js      loc_18002420A
0x180024186  test    r9, r9
0x180024189  jz      loc_18002436F
0x18002418f  cmp     r9, 7FFFFFFFh
0x180024196  ja      loc_180024364
0x18002419c  mov     ecx, 7FFFFFFEh
0x1800241a1  lea     rdx, asc_18009AA50; "]"
0x1800241a8  mov     r11, r9
0x1800241ab  mov     rbx, r10
0x1800241ae  mov     rax, r12
0x1800241b1  test    rcx, rcx
0x1800241b4  jz      short loc_1800241D6
0x1800241b6  movzx   r8d, word ptr [rdx]
0x1800241ba  test    r8w, r8w
0x1800241be  jz      short loc_1800241D6
0x1800241c0  mov     [rbx], r8w
0x1800241c4  add     rdx, r13
0x1800241c7  add     rbx, r13
0x1800241ca  dec     rcx
0x1800241cd  inc     rax
0x1800241d0  sub     r11, 1
0x1800241d4  jnz     short loc_1800241B1
0x1800241d6  test    r11, r11
0x1800241d9  lea     rdx, [rax-1]
0x1800241dd  lea     rcx, [rbx-2]
0x1800241e1  cmovnz  rdx, rax
0x1800241e5  mov     rax, r11
0x1800241e8  neg     rax
0x1800241eb  sbb     r8d, r8d
0x1800241ee  not     r8d
0x1800241f1  lea     r10, [r10+rdx*2]
0x1800241f5  and     r8d, 8007007Ah
0x1800241fc  test    r11, r11
0x1800241ff  cmovnz  rcx, rbx
0x180024203  sub     r9, rdx
0x180024206  mov     [rcx], r12w
0x18002420a  mov     rax, [rbp+arg_58]
0x180024211  mov     rbx, [rsp+50h+arg_18]
0x180024219  mov     [rax], r10
0x18002421c  mov     rax, [rbp+arg_60]
0x180024223  mov     [rax], r9
0x180024226  mov     eax, r8d
0x180024229  add     rsp, 50h
0x18002422d  pop     r15
0x18002422f  pop     r14
0x180024231  pop     r13
0x180024233  pop     r12
0x180024235  pop     rdi
0x180024236  pop     rsi
0x180024237  pop     rbp
0x180024238  retn
0x180024239  mov     rax, [rbp+arg_38]
0x18002423d  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024241  mov     [rsp+50h+var_18], rsi
0x180024246  lea     r8, [rbp+arg_8]; wchar_t **
0x18002424a  mov     [rsp+50h+var_20], rax
0x18002424f  mov     rdx, r14; unsigned __int64
0x180024252  lea     rax, aSS_4; "%s %s "
0x180024259  mov     rcx, r15; pszDest
0x18002425c  mov     qword ptr [rsp+50h+cchCount2], rax; unsigned int
0x180024261  mov     [rsp+50h+lpString2], r12; unsigned int
0x180024266  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x18002426b  mov     r8d, eax
0x18002426e  test    eax, eax
0x180024270  js      loc_1800243AB
0x180024276  mov     rax, [rbp+arg_10]
0x18002427a  mov     rcx, [rbp+arg_8]; wchar_t *
0x18002427e  mov     [rbp+arg_0], rax
0x180024282  mov     [rbp+arg_10], rcx
0x180024286  cmp     [rbp+arg_20], r12b
0x18002428a  jnz     loc_180024383
0x180024290  lea     r8, [rbp+arg_0]
0x180024294  mov     r9, rcx
0x180024297  mov     [rsp+50h+var_20], r8
0x18002429c  mov     edx, r13d
0x18002429f  lea     r8, [rbp+arg_10]
0x1800242a3  mov     rcx, rbx
0x1800242a6  mov     qword ptr [rsp+50h+cchCount2], r8
0x1800242ab  mov     r8d, edi
0x1800242ae  mov     [rsp+50h+lpString2], rax
0x1800242b3  call    ?ValueNormalization@StructuredQuery1@@YAJPEBUtagPROPVARIANT@@W4VALUE_NORMALIZATION_STYLE@1@W4PROPDESC_FORMAT_FLAGS@@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::ValueNormalization(tagPROPVARIANT const *,StructuredQuery1::VALUE_NORMALIZATION_STYLE,PROPDESC_FORMAT_FLAGS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x1800242b8  mov     r10, [rbp+arg_10]
0x1800242bc  mov     r9, [rbp+arg_0]
0x1800242c0  mov     r8d, eax
0x1800242c3  jmp     loc_18002420A
0x1800242c8  lea     rdx, asc_18009AA0C; "="
0x1800242cf  or      r9d, 0FFFFFFFFh; cchCount1
0x1800242d3  mov     [rsp+50h+cchCount2], r9d; cchCount2
0x1800242d8  mov     r8, rsi; lpString1
0x1800242db  mov     [rsp+50h+lpString2], rdx; lpString2
0x1800242e0  xor     edx, edx; dwCmpFlags
0x1800242e2  lea     ecx, [rdx+7Fh]; Locale
0x1800242e5  call    cs:__imp_CompareStringW
0x1800242eb  lea     r8, cchOriginalDestLength
0x1800242f2  mov     rdx, r14; unsigned __int64
0x1800242f5  cmp     eax, r13d
0x1800242f8  lea     rcx, aNot_1; "NOT "
0x1800242ff  mov     rax, [rbp+arg_38]
0x180024303  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x180024307  cmovz   rcx, r8
0x18002430b  lea     r8, [rbp+arg_8]; wchar_t **
0x18002430f  mov     [rsp+50h+var_18], rcx
0x180024314  mov     rcx, r15; pszDest
0x180024317  mov     [rsp+50h+var_20], rax
0x18002431c  lea     rax, aSIsSnull; "%s IS %sNULL"
0x180024323  mov     qword ptr [rsp+50h+cchCount2], rax; wchar_t *
0x180024328  mov     [rsp+50h+lpString2], r12; unsigned int
0x18002432d  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x180024332  mov     r9, [rbp+arg_10]
0x180024336  mov     r10, [rbp+arg_8]
0x18002433a  jmp     short loc_1800242C0
0x18002433c  cmp     word ptr [rbx], 1Fh
0x180024340  jnz     loc_18002414B
0x180024346  mov     r8, [rbx+8]; wchar_t *
0x18002434a  lea     rdx, [rbp+arg_0]
0x18002434e  mov     [rsp+50h+lpString2], rdx; unsigned __int64 *
0x180024353  lea     r9, [rbp+arg_10]; wchar_t **
0x180024357  mov     rdx, rax; unsigned __int64
0x18002435a  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18002435f  jmp     loc_180024173
0x180024364  mov     r8d, 80070057h
0x18002436a  jmp     loc_180088DCC
0x18002436f  mov     r8d, 80070057h
0x180024375  test    r9, r9
0x180024378  jz      loc_18002420A
0x18002437e  jmp     loc_180088DCC
0x180024383  cmp     word ptr [rbx], 1Fh
0x180024387  jnz     loc_180024290
0x18002438d  mov     r8, [rbx+8]; wchar_t *
0x180024391  lea     rdx, [rbp+arg_0]
0x180024395  mov     [rsp+50h+lpString2], rdx; unsigned __int64 *
0x18002439a  lea     r9, [rbp+arg_10]; wchar_t **
0x18002439e  mov     rdx, rax; unsigned __int64
0x1800243a1  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800243a6  jmp     loc_1800242B8
0x1800243ab  mov     r9, [rbp+arg_10]
0x1800243af  mov     r10, [rbp+arg_8]
0x1800243b3  jmp     loc_18002420A
0x180088dcc  mov     [r10], r12w
0x180088dd0  jmp     loc_18002420A
```
