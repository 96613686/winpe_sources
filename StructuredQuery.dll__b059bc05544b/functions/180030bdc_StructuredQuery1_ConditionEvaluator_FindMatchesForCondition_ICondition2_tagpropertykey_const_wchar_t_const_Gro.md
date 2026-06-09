# StructuredQuery1::ConditionEvaluator::FindMatchesForCondition(ICondition2 *,_tagpropertykey const &,wchar_t const *,GrowableBuffer<tagHITRANGE> *)

- ea: `0x180030bdc`
- end: `0x180030d3b`
- name: `?FindMatchesForCondition@ConditionEvaluator@StructuredQuery1@@QEAAJPEAUICondition2@@AEBU_tagpropertykey@@PEB_WPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z`
- size: `351`
- prototype: `__int64 __usercall@<rax>(StructuredQuery1::ConditionEvaluator *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030a10`

## callees

- `0x18001ee60`
- `0x180030bdc`
- `0x180030d44`
- `0x1800317c4`
- `0x18003c580`
- `0x18005daf0`
- `0x180070590`
- `0x180070690`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180030cb0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180089925`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180030cb0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180089925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089966`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030cf1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030cf1`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ConditionEvaluator::FindMatchesForCondition(
        StructuredQuery1::ConditionEvaluator *this,
        __int64 *a2,
        StructuredQuery1 *a3,
        const WCHAR *a4,
        __int64 a5)
{
  __int64 v8; // rax
  __int64 (__fastcall *v10)(__int64 *, struct _tagpropertykey *, unsigned int *, PROPVARIANT *); // rax
  int MatchesForOneSegment; // ebx
  const WCHAR *v12; // rsi
  __int64 v13; // rax
  const struct _tagpropertykey *v14; // rdx
  PWSTR v15; // r15
  __int64 v17; // rdx
  const wchar_t *v18; // rdi
  __int64 v19; // rax
  wchar_t *v20; // r12
  int v21; // [rsp+20h] [rbp-71h]
  unsigned int v22; // [rsp+40h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-49h] BYREF
  __int64 v24; // [rsp+50h] [rbp-41h]
  wchar_t *v25; // [rsp+58h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v27; // [rsp+70h] [rbp-21h]
  unsigned __int64 v28; // [rsp+78h] [rbp-19h]
  struct _tagpropertykey v29; // [rsp+80h] [rbp-11h] BYREF

  v24 = a5;
  v27 = 0;
  v8 = *a2;
  memset(&v29, 0, sizeof(v29));
  v10 = *(__int64 (__fastcall **)(__int64 *, struct _tagpropertykey *, unsigned int *, PROPVARIANT *))(v8 + 128);
  v22 = 0;
  *(_OWORD *)pvar = 0;
  MatchesForOneSegment = v10(a2, &v29, &v22, pvar);
  if ( MatchesForOneSegment >= 0 )
  {
    if ( LOWORD(pvar[0]) == 8 || LOWORD(pvar[0]) == 31 )
    {
      v12 = (const WCHAR *)pvar[1];
      if ( pvar[1] )
      {
        if ( *(_WORD *)pvar[1] )
        {
          if ( (unsigned int)StructuredQuery1::ConditionEvaluator::PropertyMatch(
                               this,
                               &v29,
                               (const struct _tagpropertykey *)a3) )
          {
            v13 = *a2;
            pv = 0;
            MatchesForOneSegment = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v13 + 120))(a2, &pv);
            if ( MatchesForOneSegment >= 0 )
            {
              v15 = StrStrW(a4, L"; ");
              if ( v15 && (unsigned int)StructuredQuery1::_ShouldDisplayAsMultiValuedProperty(a3, v14) )
              {
                v18 = a4;
                v19 = -1;
                do
                  ++v19;
                while ( a4[v19] );
                v25 = 0;
                v28 = (unsigned int)v19;
                MatchesForOneSegment = _AllocStringWorker<CTCoAllocPolicy>(
                                         (__int64)&v25,
                                         v17,
                                         0,
                                         (unsigned int)v19,
                                         v21,
                                         &v25);
                if ( MatchesForOneSegment >= 0 )
                {
                  v20 = v25;
                  while ( 1 )
                  {
                    MatchesForOneSegment = StringCchCopyNW(v20, v28, v18, v15 - v18);
                    if ( MatchesForOneSegment < 0 )
                      break;
                    MatchesForOneSegment = StructuredQuery1::ConditionEvaluator::_FindMatchesForOneSegment(
                                             (__int64)this,
                                             (__int64)v12,
                                             (__int64)pv,
                                             v22,
                                             (__int64)v20,
                                             v18 - a4,
                                             v24);
                    if ( MatchesForOneSegment < 0 )
                      break;
                    v18 = v15 + 2;
                    v15 = StrStrW(v15 + 2, L"; ");
                    if ( !v15 )
                    {
                      MatchesForOneSegment = StructuredQuery1::ConditionEvaluator::_FindMatchesForOneSegment(
                                               (__int64)this,
                                               (__int64)v12,
                                               (__int64)pv,
                                               v22,
                                               (__int64)v18,
                                               v18 - a4,
                                               v24);
                      break;
                    }
                  }
                  CoTaskMemFree(v20);
                }
              }
              else
              {
                MatchesForOneSegment = StructuredQuery1::ConditionEvaluator::_FindMatchesForOneString(
                                         (__int64)this,
                                         v12,
                                         (const WCHAR *)pv,
                                         v22,
                                         a4,
                                         v24);
              }
              CoTaskMemFree(pv);
            }
          }
        }
      }
    }
    PropVariantClear(pvar);
  }
  return (unsigned int)MatchesForOneSegment;
}

```

## disassembly

```asm
0x180030bdc  push    rbp
0x180030bde  push    rbx
0x180030bdf  push    rsi
0x180030be0  push    rdi
0x180030be1  push    r12
0x180030be3  push    r13
0x180030be5  push    r14
0x180030be7  push    r15
0x180030be9  lea     rbp, [rsp-17h]
0x180030bee  sub     rsp, 0A8h
0x180030bf5  mov     rax, cs:__security_cookie
0x180030bfc  xor     rax, rsp
0x180030bff  mov     [rbp+4Fh+var_48], rax
0x180030c03  mov     rax, [rbp+4Fh+arg_20]
0x180030c07  mov     rdi, rdx
0x180030c0a  mov     [rbp+4Fh+var_90], rax
0x180030c0e  xorps   xmm0, xmm0
0x180030c11  xor     eax, eax
0x180030c13  mov     r14, r9
0x180030c16  mov     [rbp+4Fh+var_60.pid], eax
0x180030c19  lea     r9, [rbp+4Fh+pvar]
0x180030c1d  mov     [rbp+4Fh+var_70], rax
0x180030c21  mov     r12, r8
0x180030c24  mov     rax, [rdx]
0x180030c27  lea     r8, [rbp+4Fh+var_A0]
0x180030c2b  mov     r13, rcx
0x180030c2e  lea     rdx, [rbp+4Fh+var_60]
0x180030c32  xor     r15d, r15d
0x180030c35  mov     rcx, rdi
0x180030c38  movups  xmmword ptr [rbp+4Fh+var_60.fmtid.Data1], xmm0
0x180030c3c  mov     rax, [rax+80h]
0x180030c43  mov     [rbp+4Fh+var_A0], r15d
0x180030c47  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180030c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c50  mov     ebx, eax
0x180030c52  test    eax, eax
0x180030c54  js      loc_180030CF7
0x180030c5a  movzx   eax, word ptr [rbp+4Fh+pvar]
0x180030c5e  cmp     eax, 8
0x180030c61  jnz     loc_180030D19
0x180030c67  mov     rsi, [rbp+4Fh+pvar+8]
0x180030c6b  test    rsi, rsi
0x180030c6e  jz      short loc_180030CED
0x180030c70  cmp     [rsi], r15w
0x180030c74  jz      short loc_180030CED
0x180030c76  mov     r8, r12; struct _tagpropertykey *
0x180030c79  lea     rdx, [rbp+4Fh+var_60]; struct _tagpropertykey *
0x180030c7d  mov     rcx, r13; this
0x180030c80  call    ?PropertyMatch@ConditionEvaluator@StructuredQuery1@@AEAAHAEBU_tagpropertykey@@0@Z; StructuredQuery1::ConditionEvaluator::PropertyMatch(_tagpropertykey const &,_tagpropertykey const &)
0x180030c85  test    eax, eax
0x180030c87  jz      short loc_180030CED
0x180030c89  mov     rax, [rdi]
0x180030c8c  lea     rdx, [rbp+4Fh+pv]
0x180030c90  mov     rcx, rdi
0x180030c93  mov     [rbp+4Fh+pv], r15
0x180030c97  mov     rax, [rax+78h]
0x180030c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ca0  mov     ebx, eax
0x180030ca2  test    eax, eax
0x180030ca4  js      short loc_180030CED
0x180030ca6  lea     rdx, pszSrch; "; "
0x180030cad  mov     rcx, r14; pszFirst
0x180030cb0  call    cs:__imp_StrStrW
0x180030cb6  xor     ebx, ebx
0x180030cb8  mov     r15, rax
0x180030cbb  test    rax, rax
0x180030cbe  jnz     short loc_180030D23
0x180030cc0  mov     rax, [rbp+4Fh+var_90]
0x180030cc4  mov     rdx, rsi
0x180030cc7  mov     r9d, [rbp+4Fh+var_A0]
0x180030ccb  mov     rcx, r13
0x180030cce  mov     r8, [rbp+4Fh+pv]
0x180030cd2  mov     [rsp+0E0h+var_B8], rax
0x180030cd7  mov     [rsp+0E0h+var_C0], r14
0x180030cdc  call    ?_FindMatchesForOneString@ConditionEvaluator@StructuredQuery1@@AEAAJPEB_W0W4tagCONDITION_OPERATION@@0PEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; StructuredQuery1::ConditionEvaluator::_FindMatchesForOneString(wchar_t const *,wchar_t const *,tagCONDITION_OPERATION,wchar_t const *,GrowableBuffer<tagHITRANGE> *)
0x180030ce1  mov     ebx, eax
0x180030ce3  mov     rcx, [rbp+4Fh+pv]; pv
0x180030ce7  call    cs:__imp_CoTaskMemFree
0x180030ced  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180030cf1  call    cs:__imp_PropVariantClear
0x180030cf7  mov     eax, ebx
0x180030cf9  mov     rcx, [rbp+4Fh+var_48]
0x180030cfd  xor     rcx, rsp; StackCookie
0x180030d00  call    __security_check_cookie
0x180030d05  add     rsp, 0A8h
0x180030d0c  pop     r15
0x180030d0e  pop     r14
0x180030d10  pop     r13
0x180030d12  pop     r12
0x180030d14  pop     rdi
0x180030d15  pop     rsi
0x180030d16  pop     rbx
0x180030d17  pop     rbp
0x180030d18  retn
0x180030d19  cmp     eax, 1Fh
0x180030d1c  jnz     short loc_180030CED
0x180030d1e  jmp     loc_180030C67
0x180030d23  mov     rcx, r12; this
0x180030d26  call    ?_ShouldDisplayAsMultiValuedProperty@StructuredQuery1@@YAHAEBU_tagpropertykey@@@Z; StructuredQuery1::_ShouldDisplayAsMultiValuedProperty(_tagpropertykey const &)
0x180030d2b  test    eax, eax
0x180030d2d  jz      short loc_180030CC0
0x180030d2f  mov     rdi, r14
0x180030d32  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030d36  jmp     loc_180089892
0x180089892  inc     rax
0x180089895  cmp     [r14+rax*2], bx
0x18008989a  jnz     short loc_180089892
0x18008989c  mov     eax, eax
0x18008989e  lea     rcx, [rbp+4Fh+var_88]
0x1800898a2  mov     r9d, eax
0x1800898a5  mov     [rbp+4Fh+var_88], rbx
0x1800898a9  xor     r8d, r8d
0x1800898ac  mov     [rbp+4Fh+var_68], rax
0x1800898b0  mov     [rsp+0E0h+var_B8], rcx
0x1800898b5  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)
0x1800898ba  mov     ebx, eax
0x1800898bc  test    eax, eax
0x1800898be  js      loc_180030CE3
0x1800898c4  mov     r12, [rbp+4Fh+var_88]
0x1800898c8  mov     rdx, [rbp+4Fh+var_68]; unsigned __int64
0x1800898cc  mov     r9, r15
0x1800898cf  sub     r9, rdi
0x1800898d2  mov     r8, rdi; wchar_t *
0x1800898d5  sar     r9, 1; unsigned __int64
0x1800898d8  mov     rcx, r12; wchar_t *
0x1800898db  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x1800898e0  mov     ebx, eax
0x1800898e2  test    eax, eax
0x1800898e4  js      short loc_180089963
0x1800898e6  mov     rax, [rbp+4Fh+var_90]
0x1800898ea  sub     rdi, r14
0x1800898ed  mov     r9d, [rbp+4Fh+var_A0]
0x1800898f1  mov     rdx, rsi
0x1800898f4  mov     r8, [rbp+4Fh+pv]
0x1800898f8  mov     rcx, r13
0x1800898fb  mov     [rsp+0E0h+var_B0], rax
0x180089900  sar     rdi, 1
0x180089903  mov     dword ptr [rsp+0E0h+var_B8], edi
0x180089907  mov     [rsp+0E0h+var_C0], r12
0x18008990c  call    ?_FindMatchesForOneSegment@ConditionEvaluator@StructuredQuery1@@AEAAJPEB_W0W4tagCONDITION_OPERATION@@0KPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; StructuredQuery1::ConditionEvaluator::_FindMatchesForOneSegment(wchar_t const *,wchar_t const *,tagCONDITION_OPERATION,wchar_t const *,ulong,GrowableBuffer<tagHITRANGE> *)
0x180089911  mov     ebx, eax
0x180089913  test    eax, eax
0x180089915  js      short loc_180089963
0x180089917  lea     rdi, [r15+4]
0x18008991b  mov     rcx, rdi; pszFirst
0x18008991e  lea     rdx, pszSrch; "; "
0x180089925  call    cs:__imp_StrStrW
0x18008992b  mov     r15, rax
0x18008992e  test    rax, rax
0x180089931  jnz     short loc_1800898C8
0x180089933  mov     rcx, [rbp+4Fh+var_90]
0x180089937  mov     rax, rdi
0x18008993a  mov     r9d, [rbp+4Fh+var_A0]
0x18008993e  sub     rax, r14
0x180089941  mov     r8, [rbp+4Fh+pv]
0x180089945  mov     rdx, rsi
0x180089948  mov     [rsp+0E0h+var_B0], rcx
0x18008994d  mov     rcx, r13
0x180089950  sar     rax, 1
0x180089953  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180089957  mov     [rsp+0E0h+var_C0], rdi
0x18008995c  call    ?_FindMatchesForOneSegment@ConditionEvaluator@StructuredQuery1@@AEAAJPEB_W0W4tagCONDITION_OPERATION@@0KPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; StructuredQuery1::ConditionEvaluator::_FindMatchesForOneSegment(wchar_t const *,wchar_t const *,tagCONDITION_OPERATION,wchar_t const *,ulong,GrowableBuffer<tagHITRANGE> *)
0x180089961  mov     ebx, eax
0x180089963  mov     rcx, r12; pv
0x180089966  call    cs:__imp_CoTaskMemFree
0x18008996c  nop
0x18008996d  jmp     loc_180030CE3
```
