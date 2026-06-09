# StructuredQuery1::QueryParser::ParsePropertyValue(wchar_t const *,wchar_t const *,IQuerySolution * *)

- ea: `0x1800694b0`
- end: `0x180069630`
- name: `?ParsePropertyValue@QueryParser@StructuredQuery1@@UEAAJPEB_W0PEAPEAUIQuerySolution@@@Z`
- size: `384`
- prototype: `int(StructuredQuery1::QueryParser *__hidden this, const wchar_t *, const wchar_t *, struct IQuerySolution **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010700`
- `0x1800129bc`
- `0x18002eda8`
- `0x180034e80`
- `0x180035e7c`
- `0x1800694b0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006952e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006952e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800695e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800695e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006961b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800695cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006961b`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::ParsePropertyValue(
        RTL_SRWLOCK *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct IQuerySolution **a4)
{
  int v8; // ebx
  __int64 v9; // rcx
  const struct SemanticsUM::Relationship *RelationByName; // rax
  __int64 v11; // rax
  wchar_t *v12; // rsi
  int v13; // eax
  LPVOID pv; // [rsp+98h] [rbp+20h] BYREF

  v8 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    v8 = StructuredQuery1::QueryParser::ReadyToRun((StructuredQuery1::QueryParser *)&this[-1]);
    if ( v8 >= 0 )
    {
      pv = 0;
      v8 = _AllocArray<wchar_t,CTCoAllocPolicy>(v9, 1, 0x7800u, &pv);
      if ( v8 >= 0 )
      {
        v8 = -2147024809;
        AcquireSRWLockShared(this + 19);
        if ( a2
          && (RelationByName = SemanticsUM::Entity::FindRelationByName(
                                 *(SemanticsUM::Entity **)(*((_QWORD *)this[12].Ptr + 1) + 200LL),
                                 a2)) != 0 )
        {
          v11 = (*(__int64 (__fastcall **)(const struct SemanticsUM::Relationship *))(*(_QWORD *)RelationByName + 32LL))(RelationByName);
        }
        else
        {
          v11 = 0;
        }
        v12 = (wchar_t *)pv;
        if ( a3 && v11 )
        {
          pv = 0;
          v13 = StructuredQuery1::DefaultPhraseCommon(v11, 1, &pv);
          if ( v13 < 0 )
          {
            if ( v13 == -2147024774 )
              v13 = -2147024809;
            v8 = v13;
          }
          else
          {
            v8 = StringCchPrintfW(v12, 0x7800u, L"%s:(%s)", pv, a3);
            CoTaskMemFree(pv);
          }
        }
        ReleaseSRWLockShared(this + 19);
        if ( v8 >= 0 )
          v8 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, wchar_t *, _QWORD, _QWORD, GUID *, struct IQuerySolution **))this->Ptr
                + 11))(
                 this,
                 v12,
                 0,
                 HIDWORD(this[6].Ptr),
                 &GUID_d6ebc66b_8921_4193_afdd_a1789fb7ff57,
                 a4);
        CoTaskMemFree(v12);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800694b0  push    rbx
0x1800694b2  push    rbp
0x1800694b3  push    rsi
0x1800694b4  push    rdi
0x1800694b5  push    r14
0x1800694b7  push    r15
0x1800694b9  sub     rsp, 48h
0x1800694bd  mov     r14, r9
0x1800694c0  mov     r15, r8
0x1800694c3  mov     rsi, rdx
0x1800694c6  mov     rdi, rcx
0x1800694c9  mov     ebx, 80004003h
0x1800694ce  test    r9, r9
0x1800694d1  jz      loc_180069621
0x1800694d7  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x1800694db  mov     qword ptr [r9], 0
0x1800694e2  call    ?ReadyToRun@QueryParser@StructuredQuery1@@AEAAJXZ; StructuredQuery1::QueryParser::ReadyToRun(void)
0x1800694e7  mov     ebx, eax
0x1800694e9  test    eax, eax
0x1800694eb  js      loc_180069621
0x1800694f1  lea     r9, [rsp+78h+pv]
0x1800694f9  mov     [rsp+78h+pv], 0
0x180069505  mov     edx, 1
0x18006950a  mov     r8d, 7800h
0x180069510  call    ??$_AllocArray@_WVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEA_W@Z; _AllocArray<wchar_t,CTCoAllocPolicy>(void *,ulong,unsigned __int64,wchar_t * *)
0x180069515  mov     ebx, eax
0x180069517  test    eax, eax
0x180069519  js      loc_180069621
0x18006951f  lea     rbp, [rdi+98h]
0x180069526  mov     ebx, 80070057h
0x18006952b  mov     rcx, rbp; SRWLock
0x18006952e  call    cs:__imp_AcquireSRWLockShared
0x180069534  test    rsi, rsi
0x180069537  jz      short loc_180069569
0x180069539  mov     rax, [rdi+60h]
0x18006953d  mov     rdx, rsi; wchar_t *
0x180069540  mov     rcx, [rax+8]
0x180069544  mov     rcx, [rcx+0C8h]; this
0x18006954b  call    ?FindRelationByName@Entity@SemanticsUM@@QEBAPEBVRelationship@2@PEB_W@Z; SemanticsUM::Entity::FindRelationByName(wchar_t const *)
0x180069550  mov     rdx, rax
0x180069553  test    rax, rax
0x180069556  jz      short loc_180069569
0x180069558  mov     rcx, [rax]
0x18006955b  mov     rax, [rcx+20h]
0x18006955f  mov     rcx, rdx
0x180069562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069567  jmp     short loc_18006956B
0x180069569  xor     eax, eax
0x18006956b  mov     rsi, [rsp+78h+pv]
0x180069573  test    r15, r15
0x180069576  jz      short loc_1800695DF
0x180069578  test    rax, rax
0x18006957b  jz      short loc_1800695DF
0x18006957d  lea     r8, [rsp+78h+pv]
0x180069585  mov     [rsp+78h+pv], 0
0x180069591  mov     edx, 1
0x180069596  mov     rcx, rax
0x180069599  call    ?DefaultPhraseCommon@StructuredQuery1@@YAJPEB_WW4DEFAULT_PHRASE_FLAGS@1@PEAPEA_W@Z; StructuredQuery1::DefaultPhraseCommon(wchar_t const *,StructuredQuery1::DEFAULT_PHRASE_FLAGS,wchar_t * *)
0x18006959e  test    eax, eax
0x1800695a0  js      short loc_1800695D5
0x1800695a2  mov     r9, [rsp+78h+pv]
0x1800695aa  lea     r8, aSS; "%s:(%s)"
0x1800695b1  mov     edx, 7800h; unsigned __int64
0x1800695b6  mov     [rsp+78h+var_58], r15
0x1800695bb  mov     rcx, rsi; wchar_t *
0x1800695be  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800695c3  mov     rcx, [rsp+78h+pv]; pv
0x1800695cb  mov     ebx, eax
0x1800695cd  call    cs:__imp_CoTaskMemFree
0x1800695d3  jmp     short loc_1800695DF
0x1800695d5  cmp     eax, 8007007Ah
0x1800695da  cmovz   eax, ebx
0x1800695dd  mov     ebx, eax
0x1800695df  mov     rcx, rbp; SRWLock
0x1800695e2  call    cs:__imp_ReleaseSRWLockShared
0x1800695e8  test    ebx, ebx
0x1800695ea  js      short loc_180069618
0x1800695ec  mov     rax, [rdi]
0x1800695ef  lea     rcx, _GUID_d6ebc66b_8921_4193_afdd_a1789fb7ff57
0x1800695f6  mov     r9d, [rdi+34h]
0x1800695fa  xor     r8d, r8d
0x1800695fd  mov     [rsp+78h+var_50], r14
0x180069602  mov     rdx, rsi
0x180069605  mov     [rsp+78h+var_58], rcx
0x18006960a  mov     rcx, rdi
0x18006960d  mov     rax, [rax+58h]
0x180069611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069616  mov     ebx, eax
0x180069618  mov     rcx, rsi; pv
0x18006961b  call    cs:__imp_CoTaskMemFree
0x180069621  mov     eax, ebx
0x180069623  add     rsp, 48h
0x180069627  pop     r15
0x180069629  pop     r14
0x18006962b  pop     rdi
0x18006962c  pop     rsi
0x18006962d  pop     rbp
0x18006962e  pop     rbx
0x18006962f  retn
```
