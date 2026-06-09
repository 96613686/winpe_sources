# StructuredQuery1::SourceWordSink::MatchQueryNodeSiblings(wchar_t const *,int,ulong,ulong,ulong,int,StructuredQuery1::LinkedListOfHitRanges *,StructuredQuery1::QueryWordNode *)

- ea: `0x18002ff00`
- end: `0x180030154`
- name: `?MatchQueryNodeSiblings@SourceWordSink@StructuredQuery1@@AEAAJPEB_WHKKKHPEAVLinkedListOfHitRanges@2@PEAVQueryWordNode@2@@Z`
- size: `596`
- prototype: `__int64 __usercall@<rax>(StructuredQuery1::SourceWordSink *__hidden this@<rcx>, LPCWCH lpString1@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, int, struct StructuredQuery1::LinkedListOfHitRanges *, struct StructuredQuery1::QueryWordNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fd1c`

## callees

- `0x18002f714`
- `0x18002ff00`
- `0x180030160`
- `0x18003025c`
- `0x1800302ec`
- `0x18003040c`
- `0x1800305d8`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18002ffe4`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18003012e`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18002ffe4`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x18003012e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18002ff7c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18002ff7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030029`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SourceWordSink::MatchQueryNodeSiblings(
        StructuredQuery1::SourceWordSink *this,
        LPCWCH lpString1,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        struct StructuredQuery1::LinkedListOfHitRanges *a8,
        struct StructuredQuery1::QueryWordNode *pcchFound)
{
  struct StructuredQuery1::QueryWordNode *v9; // rbx
  WCHAR *v12; // r14
  int v13; // edi
  __int64 v14; // r12
  int cchCount2; // esi
  const WCHAR *v16; // r8
  DWORD v17; // edx
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rcx
  DWORD v20; // edx
  int v21; // eax
  unsigned int v22; // r8d
  bool v23; // si
  unsigned int fixed; // eax
  struct StructuredQuery1::LinkedListOfHitRanges *v26; // rsi
  struct StructuredQuery1::QueryWordNode *v27; // r9
  __int64 v28; // rdx
  int WordTracker; // eax
  int NLSString; // eax
  tagHITRANGE v31; // [rsp+50h] [rbp-10h] BYREF
  struct StructuredQuery1::LinkedListOfHitRanges *v32; // [rsp+58h] [rbp-8h] BYREF
  const WCHAR *lpStringSource; // [rsp+A8h] [rbp+48h]

  lpStringSource = lpString1;
  v9 = pcchFound;
  v31 = 0;
  v12 = 0;
  if ( !*((_QWORD *)pcchFound + 4) )
  {
    v13 = 0;
    LODWORD(v14) = 0;
    goto LABEL_3;
  }
  v13 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
          (CKoreanDecomposition *)g_koreanDecomposition,
          lpString1,
          a3,
          (wchar_t **)&v31);
  if ( v13 >= 0 )
  {
    v12 = (WCHAR *)v31;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*(_QWORD *)&v31 + 2 * v14) );
    lpString1 = lpStringSource;
LABEL_3:
    while ( 1 )
    {
      cchCount2 = *((_DWORD *)v9 + 4);
      v16 = lpString1;
      v17 = *((_DWORD *)this + 24);
      v18 = (const WCHAR *)*((_QWORD *)this + 3);
      LODWORD(pcchFound) = 0;
      if ( CompareStringEx(v18, v17, v16, a3, *((LPCWCH *)v9 + 3), cchCount2, 0, 0, 0) == 2 )
        break;
      if ( *((_BYTE *)this + 32) && !a7 && !*((_DWORD *)v9 + 11) )
      {
        v19 = (const WCHAR *)*((_QWORD *)this + 3);
        v20 = *((_DWORD *)this + 24) | 0x100000;
        if ( v12 )
        {
          NLSString = FindNLSStringEx(
                        v19,
                        v20,
                        v12,
                        v14,
                        *((LPCWSTR *)v9 + 4),
                        *((_DWORD *)v9 + 10),
                        (LPINT)&pcchFound,
                        0,
                        0,
                        0);
          v22 = (unsigned int)pcchFound;
          if ( NLSString < 0 )
          {
            v23 = 0;
          }
          else
          {
            v23 = 1;
            v22 = *((_DWORD *)v9 + 4) - *((_DWORD *)v9 + 10) + (_DWORD)pcchFound;
          }
        }
        else
        {
          v21 = FindNLSStringEx(
                  v19,
                  v20,
                  lpStringSource,
                  a3,
                  *((LPCWSTR *)v9 + 3),
                  cchCount2,
                  (LPINT)&pcchFound,
                  0,
                  0,
                  0);
          v22 = (unsigned int)pcchFound;
          v23 = v21 >= 0;
        }
        fixed = FixWordBreakBoundary(lpStringSource, a3, v22);
        LODWORD(pcchFound) = fixed;
        if ( v23 )
          goto LABEL_15;
      }
LABEL_10:
      if ( v13 >= 0 )
      {
        v9 = (struct StructuredQuery1::QueryWordNode *)*((_QWORD *)v9 + 6);
        lpString1 = lpStringSource;
        if ( v9 )
          continue;
      }
      CoTaskMemFree(v12);
      return (unsigned int)v13;
    }
    fixed = a6;
    LODWORD(pcchFound) = a6;
LABEL_15:
    v26 = 0;
    v32 = 0;
    if ( *((_BYTE *)this + 32) )
    {
      v31 = (tagHITRANGE)__PAIR64__(fixed, a5);
      StructuredQuery1::LinkedListOfHitRanges::Create((struct tagHITRANGE)__PAIR64__(fixed, a5), a8, &v32);
      fixed = (unsigned int)pcchFound;
      v26 = v32;
    }
    v27 = (struct StructuredQuery1::QueryWordNode *)*((_QWORD *)v9 + 7);
    v28 = fixed - a4 + a5;
    if ( v27 )
    {
      WordTracker = StructuredQuery1::SourceWordSink::AddNewQueryWordTracker(this, a4, v28, v27, v26);
    }
    else if ( *((_BYTE *)this + 32) )
    {
      WordTracker = StructuredQuery1::LinkedListOfHitRanges::AddAllHits((__int64)v26, *((_QWORD *)this + 11));
    }
    else
    {
      WordTracker = StructuredQuery1::AddMatch(a4, v28, *((_QWORD *)this + 11));
    }
    v13 = WordTracker;
    if ( v26 )
      (*(void (__fastcall **)(struct StructuredQuery1::LinkedListOfHitRanges *))(*(_QWORD *)v26 + 16LL))(v26);
    goto LABEL_10;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002ff00  mov     [rsp-38h+arg_0], rbx
0x18002ff05  mov     [rsp-38h+arg_18], r9d
0x18002ff0a  mov     [rsp-38h+lpStringSource], rdx
0x18002ff0f  push    rbp
0x18002ff10  push    rsi
0x18002ff11  push    rdi
0x18002ff12  push    r12
0x18002ff14  push    r13
0x18002ff16  push    r14
0x18002ff18  push    r15
0x18002ff1a  mov     rbp, rsp
0x18002ff1d  sub     rsp, 60h
0x18002ff21  mov     rbx, qword ptr [rbp+pcchFound]
0x18002ff28  xor     r10d, r10d
0x18002ff2b  mov     r13d, r8d
0x18002ff2e  mov     qword ptr [rbp+var_10.iPosition], r10
0x18002ff32  mov     r15, rcx
0x18002ff35  mov     r14d, r10d
0x18002ff38  cmp     [rbx+20h], r10
0x18002ff3c  jnz     loc_1800300EE
0x18002ff42  mov     edi, r10d
0x18002ff45  mov     r12d, r10d
0x18002ff48  mov     esi, [rbx+10h]
0x18002ff4b  mov     r8, rdx; lpString1
0x18002ff4e  mov     edx, [r15+60h]; dwCmpFlags
0x18002ff52  mov     r9d, r13d; cchCount1
0x18002ff55  mov     rcx, [r15+18h]; lpLocaleName
0x18002ff59  mov     [rsp+60h+lParam], r10; lParam
0x18002ff5e  mov     [rsp+60h+lpReserved], r10; lpReserved
0x18002ff63  mov     [rsp+60h+lpVersionInformation], r10; lpVersionInformation
0x18002ff68  mov     [rbp+pcchFound], r10d
0x18002ff6f  mov     rax, [rbx+18h]
0x18002ff73  mov     [rsp+60h+cchCount2], esi; cchCount2
0x18002ff77  mov     [rsp+60h+lpString2], rax; lpString2
0x18002ff7c  call    cs:__imp_CompareStringEx
0x18002ff82  xor     r10d, r10d
0x18002ff85  cmp     eax, 2
0x18002ff88  jz      loc_180030049
0x18002ff8e  cmp     [r15+20h], r10b
0x18002ff92  jz      short loc_180030011
0x18002ff94  cmp     [rbp+arg_30], r10d
0x18002ff98  jnz     short loc_180030011
0x18002ff9a  cmp     [rbx+2Ch], r10d
0x18002ff9e  jnz     short loc_180030011
0x18002ffa0  mov     edx, [r15+60h]
0x18002ffa4  lea     rax, [rbp+pcchFound]
0x18002ffab  mov     rcx, [r15+18h]; lpLocaleName
0x18002ffaf  bts     edx, 14h; dwFindNLSStringFlags
0x18002ffb3  mov     [rsp+60h+sortHandle], r10; sortHandle
0x18002ffb8  mov     [rsp+60h+lParam], r10; lpReserved
0x18002ffbd  mov     [rsp+60h+lpReserved], r10; lpVersionInformation
0x18002ffc2  mov     [rsp+60h+lpVersionInformation], rax; pcchFound
0x18002ffc7  test    r14, r14
0x18002ffca  jnz     loc_180030118
0x18002ffd0  mov     rax, [rbx+18h]
0x18002ffd4  mov     r9d, r13d; cchSource
0x18002ffd7  mov     r8, [rbp+lpStringSource]; lpStringSource
0x18002ffdb  mov     [rsp+60h+cchCount2], esi; cchValue
0x18002ffdf  mov     [rsp+60h+lpString2], rax; lpStringValue
0x18002ffe4  call    cs:__imp_FindNLSStringEx
0x18002ffea  mov     r8d, [rbp+pcchFound]; unsigned int
0x18002fff1  test    eax, eax
0x18002fff3  setns   sil
0x18002fff7  mov     rcx, [rbp+lpStringSource]; unsigned __int16 *
0x18002fffb  mov     edx, r13d; unsigned int
0x18002fffe  call    ?FixWordBreakBoundary@@YAKPEBGKK@Z; FixWordBreakBoundary(ushort const *,ulong,ulong)
0x180030003  xor     r10d, r10d
0x180030006  mov     [rbp+pcchFound], eax
0x18003000c  test    sil, sil
0x18003000f  jnz     short loc_180030052
0x180030011  test    edi, edi
0x180030013  js      short loc_180030026
0x180030015  mov     rbx, [rbx+30h]
0x180030019  mov     rdx, [rbp+lpStringSource]
0x18003001d  test    rbx, rbx
0x180030020  jnz     loc_18002FF48
0x180030026  mov     rcx, r14; pv
0x180030029  call    cs:__imp_CoTaskMemFree
0x18003002f  mov     rbx, [rsp+60h+arg_0]
0x180030037  mov     eax, edi
0x180030039  add     rsp, 60h
0x18003003d  pop     r15
0x18003003f  pop     r14
0x180030041  pop     r13
0x180030043  pop     r12
0x180030045  pop     rdi
0x180030046  pop     rsi
0x180030047  pop     rbp
0x180030048  retn
0x180030049  mov     eax, [rbp+arg_28]
0x18003004c  mov     [rbp+pcchFound], eax
0x180030052  mov     rsi, r10
0x180030055  mov     [rbp+var_8], r10
0x180030059  cmp     [r15+20h], r10b
0x18003005d  jz      short loc_180030086
0x18003005f  mov     ecx, [rbp+arg_20]
0x180030062  lea     r8, [rbp+var_8]; struct StructuredQuery1::LinkedListOfHitRanges **
0x180030066  mov     rdx, [rbp+arg_38]; struct StructuredQuery1::LinkedListOfHitRanges *
0x18003006a  mov     [rbp+var_10.iPosition], ecx
0x18003006d  mov     [rbp+var_10.cLength], eax
0x180030070  mov     rcx, qword ptr [rbp+var_10.iPosition]; struct tagHITRANGE
0x180030074  call    ?Create@LinkedListOfHitRanges@StructuredQuery1@@SAJUtagHITRANGE@@PEAV12@PEAPEAV12@@Z; StructuredQuery1::LinkedListOfHitRanges::Create(tagHITRANGE,StructuredQuery1::LinkedListOfHitRanges *,StructuredQuery1::LinkedListOfHitRanges * *)
0x180030079  mov     eax, [rbp+pcchFound]
0x18003007f  xor     r10d, r10d
0x180030082  mov     rsi, [rbp+var_8]
0x180030086  mov     ecx, [rbp+arg_18]
0x180030089  sub     eax, ecx
0x18003008b  mov     edx, [rbp+arg_20]
0x18003008e  mov     r9, [rbx+38h]; struct StructuredQuery1::QueryWordNode *
0x180030092  add     edx, eax
0x180030094  test    r9, r9
0x180030097  jz      short loc_1800300D0
0x180030099  mov     r8d, edx; unsigned int
0x18003009c  mov     [rsp+60h+lpString2], rsi; struct StructuredQuery1::LinkedListOfHitRanges *
0x1800300a1  mov     edx, ecx; unsigned int
0x1800300a3  mov     rcx, r15; this
0x1800300a6  call    ?AddNewQueryWordTracker@SourceWordSink@StructuredQuery1@@AEAAJKKPEAVQueryWordNode@2@PEAVLinkedListOfHitRanges@2@@Z; StructuredQuery1::SourceWordSink::AddNewQueryWordTracker(ulong,ulong,StructuredQuery1::QueryWordNode *,StructuredQuery1::LinkedListOfHitRanges *)
0x1800300ab  xor     r10d, r10d
0x1800300ae  mov     edi, eax
0x1800300b0  test    rsi, rsi
0x1800300b3  jz      loc_180030011
0x1800300b9  mov     rax, [rsi]
0x1800300bc  mov     rcx, rsi
0x1800300bf  mov     rax, [rax+10h]
0x1800300c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300c8  xor     r10d, r10d
0x1800300cb  jmp     loc_180030011
0x1800300d0  mov     r8, [r15+58h]
0x1800300d4  cmp     [r15+20h], r10b
0x1800300d8  jz      short loc_1800300E7
0x1800300da  mov     rdx, r8
0x1800300dd  mov     rcx, rsi
0x1800300e0  call    ?AddAllHits@LinkedListOfHitRanges@StructuredQuery1@@QEAAJPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; StructuredQuery1::LinkedListOfHitRanges::AddAllHits(GrowableBuffer<tagHITRANGE> *)
0x1800300e5  jmp     short loc_1800300AB
0x1800300e7  call    StructuredQuery1__AddMatch
0x1800300ec  jmp     short loc_1800300AB
0x1800300ee  lea     r9, [rbp+var_10]; wchar_t **
0x1800300f2  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x1800300f9  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEB_WKPEAPEA_W@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(wchar_t const *,ulong,wchar_t * *)
0x1800300fe  xor     r10d, r10d
0x180030101  mov     edi, eax
0x180030103  test    eax, eax
0x180030105  js      loc_18003002F
0x18003010b  mov     r14, qword ptr [rbp+var_10.iPosition]
0x18003010f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180030113  jmp     loc_180089876
0x180030118  mov     eax, [rbx+28h]
0x18003011b  mov     r9d, r12d; cchSource
0x18003011e  mov     [rsp+60h+cchCount2], eax; cchValue
0x180030122  mov     r8, r14; lpStringSource
0x180030125  mov     rax, [rbx+20h]
0x180030129  mov     [rsp+60h+lpString2], rax; lpStringValue
0x18003012e  call    cs:__imp_FindNLSStringEx
0x180030134  mov     r8d, [rbp+pcchFound]
0x18003013b  test    eax, eax
0x18003013d  js      loc_180089889
0x180030143  mov     eax, [rbx+10h]
0x180030146  mov     sil, 1
0x180030149  sub     eax, [rbx+28h]
0x18003014c  add     r8d, eax
0x18003014f  jmp     loc_18002FFF7
0x180089876  inc     r12
0x180089879  cmp     [r14+r12*2], r10w
0x18008987e  jnz     short loc_180089876
0x180089880  mov     rdx, [rbp+lpStringSource]
0x180089884  jmp     loc_18002FF48
0x180089889  xor     sil, sil
0x18008988c  jmp     loc_18002FFF7
```
