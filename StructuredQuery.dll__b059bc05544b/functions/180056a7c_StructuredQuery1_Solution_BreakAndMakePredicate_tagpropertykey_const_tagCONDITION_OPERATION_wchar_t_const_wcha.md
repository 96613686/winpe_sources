# StructuredQuery1::Solution::BreakAndMakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,wchar_t const *,wchar_t const *,IRichChunk *,IRichChunk *,IRichChunk *,int,bool,bool,bool,ICondition2 * *)

- ea: `0x180056a7c`
- end: `0x180057285`
- name: `?BreakAndMakePredicate@Solution@StructuredQuery1@@AEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_W22PEAUIRichChunk@@33H_N44PEAPEAUICondition2@@@Z`
- size: `2057`
- prototype: `__int64 __fastcall(StructuredQuery1::Solution *this, const struct _tagpropertykey *, enum tagCONDITION_OPERATION, wchar_t *, struct IObjectArray *lpSrcStr, PCWSTR psz1, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, unsigned int, struct StructuredQuery1::OneWord *, bool, bool, struct ICondition2 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ef3c`

## callees

- `0x1800090c0`
- `0x18000b180`
- `0x18000bd20`
- `0x18000ea6c`
- `0x18001b2b4`
- `0x18001cf9c`
- `0x18001ee60`
- `0x18001efa4`
- `0x180020420`
- `0x18002683c`
- `0x180032198`
- `0x180047790`
- `0x180055ef4`
- `0x180056a7c`
- `0x18005b4b8`
- `0x18005db14`
- `0x18005e048`
- `0x18006e8bc`
- `0x18006efc0`
- `0x18007add8`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056ea9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180056ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f14`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::BreakAndMakePredicate(
        StructuredQuery1::Solution *this,
        const struct _tagpropertykey *a2,
        enum tagCONDITION_OPERATION a3,
        wchar_t *a4,
        struct IObjectArray *lpSrcStr,
        PCWSTR psz1,
        struct IRichChunk *a7,
        struct IRichChunk *a8,
        struct IRichChunk *a9,
        unsigned int a10,
        struct StructuredQuery1::OneWord *a11,
        bool a12,
        bool a13,
        struct ICondition2 **a14)
{
  StructuredQuery1 **v15; // r15
  __int64 v16; // rdx
  struct IObjectArray *v17; // r14
  int StringFlags; // edi
  __int64 v19; // rbx
  struct IObjectArray *v20; // rsi
  unsigned int v21; // edx
  const struct std::nothrow_t *v22; // rdx
  unsigned __int64 v23; // rax
  int *v24; // rsi
  unsigned int v25; // ebx
  unsigned int v26; // edi
  unsigned int v27; // eax
  const struct std::nothrow_t *v28; // rdx
  StructuredQuery1::Solution *v29; // rcx
  unsigned int v30; // ebx
  const struct std::nothrow_t *v31; // rdx
  void *v32; // r14
  struct ICondition *v33; // rbx
  unsigned int v34; // r14d
  unsigned int v35; // r12d
  int v36; // ecx
  struct ICondition *v37; // rbx
  __int64 v38; // rdx
  StructuredQuery1::Solution *v39; // rcx
  struct IObjectArray *v40; // r12
  __int64 v41; // rcx
  int HasScript; // edi
  const wchar_t *v43; // r8
  __int64 v44; // rbx
  __int64 v45; // r14
  int v46; // edx
  char *v47; // rcx
  bool v48; // bl
  LPVOID v49; // r14
  StructuredQuery1::Solution *v50; // rcx
  bool v51; // r9
  struct ICondition *v52; // rbx
  unsigned int v53; // edx
  PCWSTR v54; // rdi
  __int16 v55; // ax
  unsigned __int64 i; // rcx
  __int64 v57; // rcx
  struct IObjectArray *v58; // rbx
  StructuredQuery1::Solution *v59; // rcx
  struct ICondition2 *v60; // rbx
  wchar_t **v62; // [rsp+28h] [rbp-B1h]
  wchar_t **v63; // [rsp+28h] [rbp-B1h]
  struct StructuredQuery1::OneWord *v64; // [rsp+30h] [rbp-A9h]
  unsigned int *v65; // [rsp+40h] [rbp-99h]
  struct ICondition2 *v66; // [rsp+88h] [rbp-51h] BYREF
  struct IObjectArray *v67; // [rsp+90h] [rbp-49h] BYREF
  struct IObjectArray *v68; // [rsp+98h] [rbp-41h] BYREF
  struct ICondition *v69; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-31h] BYREF
  __int16 v71; // [rsp+B0h] [rbp-29h]
  struct tagPROPVARIANT v72; // [rsp+B8h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+128h] [rbp+4Fh] BYREF
  const struct _tagpropertykey *v74; // [rsp+130h] [rbp+57h]
  enum tagCONDITION_OPERATION v75; // [rsp+138h] [rbp+5Fh]
  wchar_t *v76; // [rsp+140h] [rbp+67h]

  v76 = a4;
  v75 = a3;
  v74 = a2;
  v72.vt = 3;
  memset(&v72.decVal.scale, 0, 22);
  v72.lVal = a10 | 0x80;
  v66 = 0;
  v15 = 0;
  pv = 0;
  a10 = 0;
  LODWORD(a11) = 0;
  v16 = *((_QWORD *)this + 3);
  if ( v16 && a9 && *((_DWORD *)this + 20) == *((_DWORD *)this + 21) )
  {
    v17 = *(struct IObjectArray **)(v16 + 48);
    v68 = v17;
    v15 = (StructuredQuery1 **)((char *)this + 56);
    StringFlags = ((__int64 (__fastcall *)(struct IRichChunk *, unsigned int *, struct StructuredQuery1::OneWord **, _QWORD, _QWORD))a9->lpVtbl->GetData)(
                    a9,
                    &a10,
                    &a11,
                    0,
                    0);
  }
  else
  {
    v19 = -1;
    v20 = lpSrcStr;
    do
      ++v19;
    while ( *((_WORD *)&lpSrcStr->lpVtbl + v19) );
    v67 = 0;
    StringFlags = SemanticsUM::GetStringFlags(
                    (LPCWCH)lpSrcStr,
                    (const wchar_t *)(unsigned int)v19,
                    (unsigned int)&v67,
                    (unsigned __int16 **)a4);
    if ( StringFlags < 0 )
      goto LABEL_69;
    LODWORD(v17) = (_DWORD)v20;
    v68 = v20;
    LODWORD(v69) = LocaleNameToLCIDWithFallback(psz1, v21);
    v70 = 0;
    StringFlags = StructuredQuery1::Tokenizer::Initialize(
                    (StructuredQuery1::Tokenizer *)&v69,
                    *((struct ILanguageResourcePool **)this + 33));
    if ( StringFlags >= 0 )
    {
      StringFlags = StructuredQuery1::Tokenizer::TokenizeWorker(
                      (StructuredQuery1::Tokenizer *)&v69,
                      (const wchar_t *)v20,
                      (const unsigned __int16 *)v67,
                      v19,
                      (struct SemanticsUM::TokenCollectionUM **)&pv);
      v15 = (StructuredQuery1 **)pv;
      if ( StringFlags >= 0 )
      {
        a10 = 0;
        LODWORD(a11) = (**(__int64 (__fastcall ***)(LPVOID))pv)(pv);
      }
    }
    operator delete(v67, v22);
    IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(&v70);
  }
  if ( StringFlags >= 0 )
  {
    v23 = 16LL * (unsigned int)a11;
    if ( !is_mul_ok((unsigned int)a11, 0x10u) )
      v23 = -1;
    v24 = (int *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
    if ( v24 )
    {
      LODWORD(pv) = 0;
      v25 = (unsigned int)a11;
      v26 = a10;
      v27 = (*(__int64 (__fastcall **)(StructuredQuery1 **))*v15)(v15);
      LODWORD(v64) = v25;
      StringFlags = StructuredQuery1::ExtractWords(
                      v15[2],
                      (const struct SemanticsUM::TokenUM *)v27,
                      v26,
                      v25,
                      (unsigned int)v24,
                      v64,
                      (unsigned int)&pv,
                      v65);
      if ( StringFlags >= 0 )
      {
        if ( a13 )
        {
          v30 = (unsigned int)pv;
          if ( (_DWORD)pv )
          {
            pv = 0;
            StringFlags = StructuredQuery1::MakePhraseString(
                            (StructuredQuery1 *)v24,
                            (const struct StructuredQuery1::OneWord *)v30,
                            (unsigned int)v17,
                            (const wchar_t *)&pv,
                            v62);
            if ( StringFlags >= 0 )
            {
              v69 = 0;
              StringFlags = StructuredQuery1::TokenInformation::CreateInstance(
                              v24[2],
                              v24[4 * v30 - 2] + v24[4 * v30 - 1],
                              this,
                              &v72,
                              (const struct _GUID *)v63,
                              (void **)&v69);
              v32 = pv;
              if ( StringFlags >= 0 )
              {
                v33 = v69;
                StringFlags = StructuredQuery1::Solution::MakePredicate(this, v74, (unsigned int)v75, v76, pv, psz1);
                ((void (__fastcall *)(struct ICondition *))v33->lpVtbl->Release)(v33);
              }
              operator delete(v32, v31);
            }
          }
          else
          {
            StringFlags = StructuredQuery1::Solution::MakeTruthValue(
                            v29,
                            1,
                            &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                            (void **)&v66);
          }
        }
        else
        {
          v67 = 0;
          v34 = (unsigned int)pv;
          StringFlags = FixedCapacityObjectCollection::CreateInstance(
                          (unsigned int)pv,
                          &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                          (void **)&v67);
          if ( StringFlags >= 0 )
          {
            v35 = 0;
            while ( v35 < v34 )
            {
              pv = 0;
              v36 = v24[4 * v35 + 2];
              StringFlags = StructuredQuery1::TokenInformation::CreateInstance(
                              v36,
                              v36 + v24[4 * v35 + 3],
                              this,
                              &v72,
                              (const struct _GUID *)v62,
                              &pv);
              if ( StringFlags >= 0 )
              {
                v69 = 0;
                StringFlags = StructuredQuery1::Solution::MakePredicate(
                                this,
                                v74,
                                (unsigned int)v75,
                                v76,
                                (char *)v68 + 2 * (unsigned int)v24[4 * v35],
                                v24[4 * v35 + 1],
                                psz1);
                if ( StringFlags >= 0 )
                {
                  v37 = v69;
                  StringFlags = ((__int64 (__fastcall *)(struct IObjectArray *, struct ICondition *))v67->lpVtbl[1].QueryInterface)(
                                  v67,
                                  v69);
                  ((void (__fastcall *)(struct ICondition *))v37->lpVtbl->Release)(v37);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
              }
              ++v35;
              if ( StringFlags < 0 )
                goto LABEL_48;
            }
            if ( StrCmpIW(psz1, L"ko-KR") )
              goto LABEL_49;
            v40 = v68;
            if ( v34 )
            {
              pv = 0;
              v41 = (unsigned int)v24[4 * v34 - 3] - 1LL + (unsigned int)v24[4 * v34 - 4];
              HasScript = _AllocStringWorker<CTCoAllocPolicy>(
                            v41,
                            v38,
                            (const size_t *)((char *)v68 + 2 * v41),
                            1u,
                            (int)v62,
                            &pv);
              if ( HasScript >= 0 )
              {
                HasScript = CScriptAutoDetection::HasScript(
                              (CScriptAutoDetection *)g_scriptAutoDetection,
                              (const wchar_t *)pv,
                              v43);
                CoTaskMemFree(pv);
              }
              if ( HasScript )
                goto LABEL_49;
              if ( v34 < 2 )
                goto LABEL_49;
              if ( v24[4 * v34 - 3] == 1 )
              {
                v39 = (StructuredQuery1::Solution *)(16LL * (v34 - 2));
                if ( *(int *)((char *)v24 + (_QWORD)v39) + *(int *)((char *)v24 + (_QWORD)v39 + 4) < (unsigned int)v24[4 * v34 - 4] )
                  goto LABEL_49;
              }
            }
            if ( v34 < 2 || (v44 = 4LL * (v34 - 1), v24[v44 + 1] != 1) )
            {
LABEL_49:
              pv = 0;
              StringFlags = StructuredQuery1::Solution::MakeCompound(
                              v39,
                              CT_AND_CONDITION,
                              v67,
                              1,
                              a12,
                              &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                              &pv);
              if ( StringFlags >= 0 )
              {
                if ( v34 > 1 )
                {
                  v69 = (struct ICondition *)0x130014001D0007LL;
                  v70 = 0xB0006003E000FLL;
                  v71 = 14;
                  v54 = psz1;
                  v55 = LocaleNameToLCIDWithFallback(psz1, v53) & 0x3FF;
                  for ( i = 0; i < 9; ++i )
                  {
                    if ( v55 == *((_WORD *)&v69 + i) )
                    {
                      v69 = 0;
                      v57 = -1;
                      do
                        ++v57;
                      while ( *((_WORD *)&lpSrcStr->lpVtbl + v57) );
                      StringFlags = StructuredQuery1::Solution::MakePredicate(
                                      this,
                                      v74,
                                      (unsigned int)v75,
                                      v76,
                                      lpSrcStr,
                                      v57,
                                      v54);
                      if ( StringFlags >= 0 )
                      {
                        v68 = 0;
                        StringFlags = FixedCapacityObjectCollection::CreateInstance(
                                        2u,
                                        &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                        (void **)&v68);
                        if ( StringFlags >= 0 )
                        {
                          v58 = v68;
                          StringFlags = ((__int64 (__fastcall *)(struct IObjectArray *, struct ICondition *))v68->lpVtbl[1].QueryInterface)(
                                          v68,
                                          v69);
                          if ( StringFlags >= 0 )
                          {
                            StringFlags = ((__int64 (__fastcall *)(struct IObjectArray *, LPVOID))v58->lpVtbl[1].QueryInterface)(
                                            v58,
                                            pv);
                            if ( StringFlags >= 0 )
                              StringFlags = StructuredQuery1::Solution::MakeCompound(
                                              v59,
                                              CT_OR_CONDITION,
                                              v58,
                                              1,
                                              a12,
                                              &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                              (void **)&v66);
                          }
                        }
                        Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v68);
                      }
                      Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&v69);
                      goto LABEL_64;
                    }
                  }
                }
                v60 = (struct ICondition2 *)pv;
                if ( pv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 8LL))(pv);
                v66 = v60;
                StringFlags = 0;
              }
LABEL_64:
              Microsoft::WRL::ComPtr<IWordBreaker>::InternalRelease(&pv);
            }
            else
            {
              pv = 0;
              v45 = 4LL * (v34 - 2);
              StringFlags = StructuredQuery1::TokenInformation::CreateInstance(
                              v24[v45],
                              v24[v45 + 1] + v24[v45] + 1,
                              this,
                              &v72,
                              (const struct _GUID *)v62,
                              &pv);
              if ( StringFlags >= 0 )
              {
                v69 = 0;
                v46 = v24[v44 + 1] + v24[v45 + 1];
                v47 = (char *)v40 + 2 * (unsigned int)v24[v45];
                v48 = a12;
                v49 = pv;
                StringFlags = StructuredQuery1::Solution::MakePredicate(
                                this,
                                v74,
                                (unsigned int)v75,
                                v76,
                                v47,
                                v46,
                                psz1);
                if ( StringFlags >= 0 )
                {
                  v51 = v48;
                  v52 = v69;
                  StringFlags = StructuredQuery1::Solution::MakeKoreanCompound(
                                  v50,
                                  v69,
                                  (struct IObjectCollection *)v67,
                                  v51,
                                  &v66);
                  ((void (__fastcall *)(struct ICondition *))v52->lpVtbl->Release)(v52);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
              }
            }
LABEL_48:
            ((void (__fastcall *)(struct IObjectArray *))v67->lpVtbl->Release)(v67);
          }
        }
      }
      operator delete(v24, v28);
    }
    else
    {
      StringFlags = -2147024882;
    }
  }
LABEL_69:
  if ( !*((_QWORD *)this + 3) && v15 )
    (*((void (__fastcall **)(StructuredQuery1 **, __int64))*v15 + 2))(v15, 1);
  *a14 = v66;
  return (unsigned int)StringFlags;
}

```

## disassembly

```asm
0x180056a7c  mov     rax, rsp
0x180056a7f  mov     [rax+20h], r9
0x180056a83  mov     [rax+18h], r8d
0x180056a87  mov     [rax+10h], rdx
0x180056a8b  push    rbp
0x180056a8c  push    rbx
0x180056a8d  push    rsi
0x180056a8e  push    rdi
0x180056a8f  push    r12
0x180056a91  push    r13
0x180056a93  push    r14
0x180056a95  push    r15
0x180056a97  lea     rbp, [rax-47h]
0x180056a9b  sub     rsp, 0D8h
0x180056aa2  mov     r13, rcx
0x180056aa5  mov     eax, 3
0x180056aaa  mov     word ptr [rbp+3Fh+var_60], ax
0x180056aae  xorps   xmm0, xmm0
0x180056ab1  xor     eax, eax
0x180056ab3  movups  xmmword ptr [rbp+3Fh+var_60+2], xmm0
0x180056ab7  mov     qword ptr [rbp+3Fh+var_60+10h], rax
0x180056abb  mov     eax, [rbp+3Fh+arg_48]
0x180056ac1  bts     eax, 7
0x180056ac5  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x180056ac8  xor     ebx, ebx
0x180056aca  mov     [rbp+3Fh+var_90], rbx
0x180056ace  mov     r15d, ebx
0x180056ad1  mov     [rbp+3Fh+pv], rbx
0x180056ad5  mov     [rbp+3Fh+arg_48], ebx
0x180056adb  mov     dword ptr [rbp+3Fh+arg_50], ebx
0x180056ae1  mov     rdx, [rcx+18h]
0x180056ae5  or      r12, 0FFFFFFFFFFFFFFFFh
0x180056ae9  test    rdx, rdx
0x180056aec  jz      short loc_180056B39
0x180056aee  mov     rcx, [rbp+3Fh+arg_40]
0x180056af5  test    rcx, rcx
0x180056af8  jz      short loc_180056B39
0x180056afa  mov     eax, [r13+54h]
0x180056afe  cmp     [r13+50h], eax
0x180056b02  jnz     short loc_180056B39
0x180056b04  mov     r14, [rdx+30h]
0x180056b08  mov     [rbp+3Fh+var_80], r14
0x180056b0c  lea     r15, [r13+38h]
0x180056b10  mov     rax, [rcx]
0x180056b13  mov     [rsp+110h+var_F0], rbx
0x180056b18  xor     r9d, r9d
0x180056b1b  lea     r8, [rbp+3Fh+arg_50]
0x180056b22  lea     rdx, [rbp+3Fh+arg_48]
0x180056b29  mov     rax, [rax+18h]
0x180056b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b32  mov     edi, eax
0x180056b34  jmp     loc_180056BF0
0x180056b39  mov     rbx, r12
0x180056b3c  mov     rsi, [rbp+3Fh+lpSrcStr]
0x180056b40  xor     r14d, r14d
0x180056b43  inc     rbx
0x180056b46  cmp     [rsi+rbx*2], r14w
0x180056b4b  jnz     short loc_180056B43
0x180056b4d  mov     [rbp+3Fh+var_88], r14
0x180056b51  lea     r8, [rbp+3Fh+var_88]; unsigned int
0x180056b55  mov     edx, ebx; cchSrc
0x180056b57  mov     rcx, rsi; lpSrcStr
0x180056b5a  call    ?GetStringFlags@SemanticsUM@@YAJPEB_WKPEAPEAG@Z; SemanticsUM::GetStringFlags(wchar_t const *,ulong,ushort * *)
0x180056b5f  mov     edi, eax
0x180056b61  test    eax, eax
0x180056b63  js      loc_180057240
0x180056b69  mov     r14, rsi
0x180056b6c  mov     [rbp+3Fh+var_80], rsi
0x180056b70  mov     rcx, [rbp+3Fh+psz1]; wchar_t *
0x180056b74  call    ?LocaleNameToLCIDWithFallback@@YAKPEB_WK@Z; LocaleNameToLCIDWithFallback(wchar_t const *,ulong)
0x180056b79  mov     dword ptr [rbp+3Fh+var_78], eax
0x180056b7c  mov     [rbp+3Fh+var_70], r15
0x180056b80  mov     rdx, [r13+108h]; struct ILanguageResourcePool *
0x180056b87  lea     rcx, [rbp+3Fh+var_78]; this
0x180056b8b  call    ?Initialize@Tokenizer@StructuredQuery1@@QEAAJPEAUILanguageResourcePool@@@Z; StructuredQuery1::Tokenizer::Initialize(ILanguageResourcePool *)
0x180056b90  mov     edi, eax
0x180056b92  test    eax, eax
0x180056b94  js      short loc_180056BDA
0x180056b96  lea     rax, [rbp+3Fh+pv]
0x180056b9a  mov     [rsp+110h+var_F0], rax; struct SemanticsUM::TokenCollectionUM **
0x180056b9f  mov     r9d, ebx; unsigned int
0x180056ba2  mov     r8, [rbp+3Fh+var_88]; unsigned __int16 *
0x180056ba6  mov     rdx, rsi; wchar_t *
0x180056ba9  lea     rcx, [rbp+3Fh+var_78]; this
0x180056bad  call    ?TokenizeWorker@Tokenizer@StructuredQuery1@@AEAAJPEB_WPEBGKPEAPEAVTokenCollectionUM@SemanticsUM@@_N@Z; StructuredQuery1::Tokenizer::TokenizeWorker(wchar_t const *,ushort const *,ulong,SemanticsUM::TokenCollectionUM * *,bool)
0x180056bb2  mov     edi, eax
0x180056bb4  xor     ebx, ebx
0x180056bb6  mov     r15, [rbp+3Fh+pv]
0x180056bba  test    eax, eax
0x180056bbc  js      short loc_180056BDC
0x180056bbe  mov     [rbp+3Fh+arg_48], ebx
0x180056bc4  mov     rax, [r15]
0x180056bc7  mov     rcx, r15
0x180056bca  mov     rax, [rax]
0x180056bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bd2  mov     dword ptr [rbp+3Fh+arg_50], eax
0x180056bd8  jmp     short loc_180056BDC
0x180056bda  xor     ebx, ebx
0x180056bdc  mov     rcx, [rbp+3Fh+var_88]; void *
0x180056be0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056be5  nop
0x180056be6  lea     rcx, [rbp+3Fh+var_70]
0x180056bea  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180056bef  nop
0x180056bf0  test    edi, edi
0x180056bf2  js      loc_180057242
0x180056bf8  mov     ecx, dword ptr [rbp+3Fh+arg_50]
0x180056bfe  mov     eax, 10h
0x180056c03  mul     rcx
0x180056c06  cmovb   rax, r12
0x180056c0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180056c11  mov     rcx, rax; unsigned __int64
0x180056c14  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180056c19  mov     rsi, rax
0x180056c1c  test    rax, rax
0x180056c1f  jz      loc_180057239
0x180056c25  mov     dword ptr [rbp+3Fh+pv], ebx
0x180056c28  mov     ebx, dword ptr [rbp+3Fh+arg_50]
0x180056c2e  mov     edi, [rbp+3Fh+arg_48]
0x180056c34  mov     rcx, [r15]
0x180056c37  mov     rax, [rcx]
0x180056c3a  mov     rcx, r15
0x180056c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c42  lea     rcx, [rbp+3Fh+pv]
0x180056c46  mov     [rsp+110h+var_E0], rcx; unsigned int
0x180056c4b  mov     dword ptr [rsp+110h+var_E8], ebx; struct StructuredQuery1::OneWord *
0x180056c4f  mov     [rsp+110h+var_F0], rsi; struct _GUID *
0x180056c54  mov     r9d, ebx; unsigned int
0x180056c57  mov     r8d, edi; unsigned int
0x180056c5a  mov     edx, eax; struct SemanticsUM::TokenUM *
0x180056c5c  mov     rcx, [r15+10h]; this
0x180056c60  call    ?ExtractWords@StructuredQuery1@@YAJPEBVTokenUM@SemanticsUM@@KKKPEAUOneWord@1@KPEAK@Z; StructuredQuery1::ExtractWords(SemanticsUM::TokenUM const *,ulong,ulong,ulong,StructuredQuery1::OneWord *,ulong,ulong *)
0x180056c65  mov     edi, eax
0x180056c67  xor     ebx, ebx
0x180056c69  test    eax, eax
0x180056c6b  js      loc_180056D73
0x180056c71  cmp     [rbp+3Fh+arg_60], bl
0x180056c77  jz      loc_180056D80
0x180056c7d  mov     ebx, dword ptr [rbp+3Fh+pv]
0x180056c80  xor     r12d, r12d
0x180056c83  test    ebx, ebx
0x180056c85  jz      loc_180056D5D
0x180056c8b  mov     [rbp+3Fh+pv], r12
0x180056c8f  lea     r9, [rbp+3Fh+pv]; wchar_t *
0x180056c93  mov     r8, r14; unsigned int
0x180056c96  mov     edx, ebx; struct StructuredQuery1::OneWord *
0x180056c98  mov     rcx, rsi; this
0x180056c9b  call    ?MakePhraseString@StructuredQuery1@@YAJPEBUOneWord@1@KPEB_WPEAPEA_W@Z; StructuredQuery1::MakePhraseString(StructuredQuery1::OneWord const *,ulong,wchar_t const *,wchar_t * *)
0x180056ca0  mov     edi, eax
0x180056ca2  test    eax, eax
0x180056ca4  js      loc_180056D71
0x180056caa  mov     [rbp+3Fh+var_78], r12
0x180056cae  lea     ecx, [rbx-1]
0x180056cb1  shl     rcx, 4
0x180056cb5  mov     edx, [rcx+rsi+0Ch]
0x180056cb9  add     edx, [rcx+rsi+8]; int
0x180056cbd  lea     rax, [rbp+3Fh+var_78]
0x180056cc1  mov     [rsp+110h+var_E8], rax; void **
0x180056cc6  lea     r9, [rbp+3Fh+var_60]; struct tagPROPVARIANT *
0x180056cca  mov     r8, r13; struct StructuredQuery1::Solution *
0x180056ccd  mov     ecx, [rsi+8]; int
0x180056cd0  call    ?CreateInstance@TokenInformation@StructuredQuery1@@SAJJJPEAVSolution@2@PEAUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformation::CreateInstance(long,long,StructuredQuery1::Solution *,tagPROPVARIANT *,_GUID const &,void * *)
0x180056cd5  mov     edi, eax
0x180056cd7  mov     r14, [rbp+3Fh+pv]
0x180056cdb  xor     ebx, ebx
0x180056cdd  test    eax, eax
0x180056cdf  js      short loc_180056D53
0x180056ce1  lea     rax, [rbp+3Fh+var_90]
0x180056ce5  mov     [rsp+110h+var_A8], rax
0x180056cea  lea     r12, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180056cf1  mov     [rsp+110h+var_B0], r12
0x180056cf6  mov     al, [rbp+3Fh+arg_58]
0x180056cfc  mov     byte ptr [rsp+110h+var_B8], al
0x180056d00  mov     rbx, [rbp+3Fh+var_78]
0x180056d04  mov     [rsp+110h+var_C8], rbx
0x180056d09  mov     rax, [rbp+3Fh+arg_38]
0x180056d10  mov     [rsp+110h+var_D0], rax
0x180056d15  mov     rax, [rbp+3Fh+arg_30]
0x180056d19  mov     [rsp+110h+var_D8], rax
0x180056d1e  mov     rax, [rbp+3Fh+psz1]
0x180056d22  mov     [rsp+110h+var_E8], rax
0x180056d27  mov     [rsp+110h+var_F0], r14
0x180056d2c  mov     r9, [rbp+3Fh+arg_18]
0x180056d30  mov     r8d, [rbp+3Fh+arg_10]
0x180056d34  mov     rdx, [rbp+3Fh+arg_8]
0x180056d38  mov     rcx, r13
0x180056d3b  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_W22W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@44_N5AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,wchar_t const *,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x180056d40  mov     edi, eax
0x180056d42  mov     rax, [rbx]
0x180056d45  mov     rcx, rbx
0x180056d48  mov     rax, [rax+10h]
0x180056d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d51  xor     ebx, ebx
0x180056d53  mov     rcx, r14; void *
0x180056d56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056d5b  jmp     short loc_180056D73
0x180056d5d  lea     r9, [rbp+3Fh+var_90]; void **
0x180056d61  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7; struct _GUID *
0x180056d68  mov     dl, 1; bool
0x180056d6a  call    ?MakeTruthValue@Solution@StructuredQuery1@@QEAAJ_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeTruthValue(bool,_GUID const &,void * *)
0x180056d6f  mov     edi, eax
0x180056d71  xor     ebx, ebx
0x180056d73  mov     rcx, rsi; void *
0x180056d76  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180056d7b  jmp     loc_180057242
0x180056d80  mov     [rbp+3Fh+var_88], rbx
0x180056d84  lea     r8, [rbp+3Fh+var_88]; void **
0x180056d88  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x180056d8f  mov     r14d, dword ptr [rbp+3Fh+pv]
0x180056d93  mov     ecx, r14d; unsigned int
0x180056d96  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x180056d9b  mov     edi, eax
0x180056d9d  test    eax, eax
0x180056d9f  js      short loc_180056D73
0x180056da1  mov     r12d, ebx
0x180056da4  cmp     r12d, r14d
0x180056da7  jnb     loc_180056E9E
0x180056dad  mov     [rbp+3Fh+pv], rbx
0x180056db1  mov     ebx, r12d
0x180056db4  add     rbx, rbx
0x180056db7  mov     ecx, [rsi+rbx*8+8]; int
0x180056dbb  mov     edx, [rsi+rbx*8+0Ch]
0x180056dbf  add     edx, ecx; int
0x180056dc1  lea     rax, [rbp+3Fh+pv]
0x180056dc5  mov     [rsp+110h+var_E8], rax; void **
0x180056dca  lea     r9, [rbp+3Fh+var_60]; struct tagPROPVARIANT *
0x180056dce  mov     r8, r13; struct StructuredQuery1::Solution *
0x180056dd1  call    ?CreateInstance@TokenInformation@StructuredQuery1@@SAJJJPEAVSolution@2@PEAUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformation::CreateInstance(long,long,StructuredQuery1::Solution *,tagPROPVARIANT *,_GUID const &,void * *)
0x180056dd6  mov     edi, eax
0x180056dd8  test    eax, eax
0x180056dda  js      loc_180056E8C
0x180056de0  mov     [rbp+3Fh+var_78], 0
0x180056de8  mov     eax, [rsi+rbx*8]
0x180056deb  mov     rcx, [rbp+3Fh+var_80]
0x180056def  lea     rcx, [rcx+rax*2]
0x180056df3  lea     rax, [rbp+3Fh+var_78]
0x180056df7  mov     [rsp+70h], rax
0x180056dfc  mov     al, [rbp+3Fh+arg_58]
0x180056e02  mov     byte ptr [rsp+110h+var_B0], al
0x180056e06  mov     rax, [rbp+3Fh+pv]
0x180056e0a  mov     qword ptr [rsp+110h+var_C0], rax
0x180056e0f  mov     rax, [rbp+3Fh+arg_38]
0x180056e16  mov     [rsp+110h+var_C8], rax
0x180056e1b  mov     rax, [rbp+3Fh+arg_30]
0x180056e1f  mov     [rsp+110h+var_D0], rax
0x180056e24  mov     rax, [rbp+3Fh+psz1]
0x180056e28  mov     [rsp+110h+var_E0], rax
0x180056e2d  mov     eax, [rsi+rbx*8+4]
0x180056e31  mov     dword ptr [rsp+110h+var_E8], eax
0x180056e35  mov     [rsp+110h+var_F0], rcx
0x180056e3a  mov     r9, [rbp+3Fh+arg_18]
0x180056e3e  mov     r8d, [rbp+3Fh+arg_10]
0x180056e42  mov     rdx, [rbp+3Fh+arg_8]
0x180056e46  mov     rcx, r13
0x180056e49  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_W2K2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@44_N5AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,wchar_t const *,ulong,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x180056e4e  mov     edi, eax
0x180056e50  test    eax, eax
0x180056e52  js      short loc_180056E7C
0x180056e54  mov     rcx, [rbp+3Fh+var_88]
0x180056e58  mov     rax, [rcx]
0x180056e5b  mov     rbx, [rbp+3Fh+var_78]
0x180056e5f  mov     rdx, rbx
0x180056e62  mov     rax, [rax+28h]
0x180056e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e6b  mov     edi, eax
0x180056e6d  mov     rax, [rbx]
0x180056e70  mov     rcx, rbx
0x180056e73  mov     rax, [rax+10h]
0x180056e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e7c  mov     rcx, [rbp+3Fh+pv]
0x180056e80  mov     rax, [rcx]
0x180056e83  mov     rax, [rax+10h]
0x180056e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e8c  inc     r12d
0x180056e8f  xor     ebx, ebx
0x180056e91  test    edi, edi
0x180056e93  jns     loc_180056DA4
0x180056e99  jmp     loc_180057058
0x180056e9e  lea     rdx, psz2; "ko-KR"
0x180056ea5  mov     rcx, [rbp+3Fh+psz1]; psz1
0x180056ea9  call    cs:__imp_StrCmpIW
0x180056eaf  test    eax, eax
0x180056eb1  jnz     loc_18005706D
0x180056eb7  mov     r12, [rbp+3Fh+var_80]
0x180056ebb  test    r14d, r14d
0x180056ebe  jz      loc_180056F4B
0x180056ec4  lea     ebx, [r14-1]
0x180056ec8  add     rbx, rbx
0x180056ecb  mov     [rbp+3Fh+pv], 0
0x180056ed3  mov     ecx, [rsi+rbx*8]
0x180056ed6  mov     eax, [rsi+rbx*8+4]
0x180056eda  dec     rax
0x180056edd  add     rcx, rax
0x180056ee0  lea     r8, [r12+rcx*2]
0x180056ee4  lea     rax, [rbp+3Fh+pv]
0x180056ee8  mov     [rsp+110h+var_E8], rax
0x180056eed  mov     r9d, 1
0x180056ef3  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)
0x180056ef8  mov     edi, eax
0x180056efa  test    eax, eax
  ... truncated ...
```
