# StructuredQuery1::QueryParser::ParseWithLocale(wchar_t const *,IEnumUnknown *,ulong,_GUID const &,void * *)

- ea: `0x1800123f0`
- end: `0x180012850`
- name: `?ParseWithLocale@QueryParser@StructuredQuery1@@UEAAJPEB_WPEAUIEnumUnknown@@KAEBU_GUID@@PEAPEAX@Z`
- size: `1120`
- prototype: `__int64 __fastcall(StructuredQuery1::QueryParser *this, wchar_t *, struct IEnumUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180010700`
- `0x1800123f0`
- `0x180012858`
- `0x1800128e8`
- `0x1800129bc`
- `0x180012ab0`
- `0x180012b60`
- `0x180012d84`
- `0x1800130ac`
- `0x18001b2b4`
- `0x18001cf9c`
- `0x18001efa4`
- `0x180020420`
- `0x18005ab08`
- `0x18005bec0`
- `0x18005daf0`
- `0x18005db14`
- `0x18005db64`
- `0x1800689f0`
- `0x18007abe0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800124db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800124db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001275d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001275d`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180012602`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180012602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088338`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088338`

## string_xrefs

- `0x180012457`: `"onecoreuap\\base\\appmodel\\search\\structuredquery\\dll\\queryparser.cpp"`
- `0x1800127c8`: `"onecoreuap\\base\\appmodel\\search\\structuredquery\\dll\\queryparser.cpp"`
- `0x18001244b`: `Attempting to parse query: %ws`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::ParseWithLocale(
        StructuredQuery1::QueryParser *this,
        wchar_t *a2,
        struct IEnumUnknown *a3,
        unsigned int a4,
        const struct _GUID *a5,
        void **a6)
{
  const wchar_t *v7; // rbx
  __int64 v9; // r8
  struct SemanticsUM::TokenCollectionUM *v10; // r15
  void *v11; // r13
  int StringFlags; // edi
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // r12
  unsigned __int16 **v16; // r9
  __int64 v17; // rcx
  const struct std::nothrow_t *v18; // rdx
  struct SemanticsUM::NamedEntityCollectionUM *v19; // r12
  unsigned int v20; // eax
  const struct _GUID *v21; // rdx
  const struct _GUID *v22; // r8
  struct SemanticsUM::NamedEntityCollectionUM *v23; // r13
  struct SemanticsUM::NamedEntityCollectionUM *v24; // rax
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, struct SemanticsUM::StructuredSemanticSolution *, _QWORD, struct SemanticsUM::TokenCollectionUM *, struct SemanticsUM::TokenCollectionUM **); // rdi
  struct SemanticsUM::TokenCollectionUM **v27; // rbx
  LCID UserDefaultLCID; // eax
  const wchar_t *v29; // r9
  struct SemanticsUM::StructuredSemanticSolution *v30; // rsi
  struct SemanticsUM::NamedEntityCollectionUM *v31; // rbx
  struct SemanticsUM::NamedEntityCollectionUM **v33; // r12
  int TokenSpan; // ebx
  const struct SemanticsUM::Relationship *RelationByName; // rdi
  char *v36; // rax
  struct SemanticsUM::TokenCollectionUM **v37; // [rsp+20h] [rbp-99h]
  unsigned int *v38; // [rsp+28h] [rbp-91h]
  struct SemanticsUM::NamedEntityCollectionUM *v39; // [rsp+40h] [rbp-79h] BYREF
  struct SemanticsUM::TokenCollectionUM *v40; // [rsp+48h] [rbp-71h] BYREF
  void *v41; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 *v42; // [rsp+58h] [rbp-61h] BYREF
  void *v43; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-51h] BYREF
  struct ITokenCollection v45; // [rsp+6Ch] [rbp-4Dh] BYREF
  struct SemanticsUM::StructuredSemanticSolution *v46; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v47; // [rsp+80h] [rbp-39h]
  LPVOID pv; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v49; // [rsp+90h] [rbp-29h]
  const struct _GUID *v50; // [rsp+98h] [rbp-21h]
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-19h]
  void **v52; // [rsp+A8h] [rbp-11h]
  char *v53; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-1h] BYREF

  v47 = a4;
  v7 = a2;
  v46 = (struct SemanticsUM::StructuredSemanticSolution *)a2;
  v50 = a5;
  v52 = a6;
  if ( (byte_1800B11C3 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_StructuredQuery_ParseText_Start,
      a3,
      1,
      &v53);
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\structuredquery\\\\dll\\\\queryparser.cpp\"",
    (const wchar_t *)0x1AB,
    (unsigned int)L"Attempting to parse query: %ws",
    v7);
  v10 = 0;
  if ( a6 )
  {
    v11 = 0;
    v43 = 0;
    StringFlags = -2147024809;
    if ( !v7 )
      goto LABEL_37;
    v13 = 30720;
    v14 = v7;
    do
    {
      if ( !*v14 )
        break;
      ++v14;
      --v13;
    }
    while ( v13 );
    v15 = (30720 - v13) & -(__int64)(v13 != 0);
    v49 = v15;
    if ( !v13 )
      goto LABEL_37;
    StringFlags = StructuredQuery1::QueryParser::ReadyToRun((StructuredQuery1::QueryParser *)((char *)this - 8));
    if ( StringFlags < 0 )
      goto LABEL_37;
    SRWLock = (PSRWLOCK)((char *)this + 152);
    AcquireSRWLockShared((PSRWLOCK)this + 19);
    v40 = 0;
    v42 = 0;
    StringFlags = SemanticsUM::GetStringFlags(v7, (const wchar_t *)(unsigned int)v15, (unsigned int)&v42, v16);
    if ( StringFlags < 0 )
    {
LABEL_36:
      ReleaseSRWLockShared(SRWLock);
LABEL_37:
      *v52 = v11;
      goto LABEL_38;
    }
    LODWORD(v53) = *((_DWORD *)this + 12);
    v54 = 0;
    v17 = *((_QWORD *)this + 7);
    if ( v17 )
    {
      v54 = *((_QWORD *)this + 7);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    }
    else
    {
      StringFlags = StructuredQuery1::Tokenizer::Initialize(
                      (StructuredQuery1::Tokenizer *)&v53,
                      *((struct ILanguageResourcePool **)this + 8));
      if ( StringFlags < 0 )
        goto LABEL_14;
    }
    StringFlags = StructuredQuery1::Tokenizer::TokenizeWorker(
                    (StructuredQuery1::Tokenizer *)&v53,
                    v7,
                    v42,
                    v15,
                    &v40,
                    (bool)v38);
    v10 = v40;
LABEL_14:
    operator delete(v42, v18);
    IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(&v54);
    if ( StringFlags >= 0 )
    {
      v19 = 0;
      v39 = 0;
      if ( a3 )
      {
        v33 = &v39;
        ((void (__fastcall *)(struct IEnumUnknown *))a3->lpVtbl->Reset)(a3);
        v40 = 0;
        do
        {
          if ( ((unsigned int (__fastcall *)(struct IEnumUnknown *, __int64, struct SemanticsUM::TokenCollectionUM **))a3->lpVtbl->Next)(
                 a3,
                 1,
                 &v40) )
          {
            break;
          }
          v41 = 0;
          TokenSpan = (**(__int64 (__fastcall ***)(struct SemanticsUM::TokenCollectionUM *, GUID *, void **))v40)(
                        v40,
                        &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                        &v41);
          if ( TokenSpan >= 0 )
          {
            LODWORD(v45.lpVtbl) = 0;
            v44 = 0;
            pv = 0;
            TokenSpan = (*(__int64 (__fastcall **)(void *, struct ITokenCollection *, unsigned int *, LPVOID *, _QWORD))(*(_QWORD *)v41 + 24LL))(
                          v41,
                          &v45,
                          &v44,
                          &pv,
                          0);
            if ( TokenSpan >= 0 )
            {
              HIDWORD(v45.lpVtbl) = 0;
              LODWORD(v42) = 0;
              TokenSpan = SemanticsUM::FindTokenSpan(
                            (SemanticsUM *)LODWORD(v45.lpVtbl),
                            v44,
                            (unsigned int)v10,
                            (const struct ITokenCollection *)((char *)&v45.lpVtbl + 4),
                            (unsigned int *)&v42,
                            v38);
              if ( !TokenSpan )
              {
                RelationByName = SemanticsUM::Entity::FindRelationByName(
                                   *(SemanticsUM::Entity **)(*(_QWORD *)(*((_QWORD *)this + 12) + 8LL) + 200LL),
                                   (const wchar_t *)pv);
                v36 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                v53 = v36;
                if ( v36 )
                {
                  *(_DWORD *)v36 = HIDWORD(v45.lpVtbl);
                  *((_DWORD *)v36 + 1) = (_DWORD)v42;
                  *((_QWORD *)v36 + 1) = RelationByName;
                  *((_QWORD *)v36 + 2) = 0;
                  *v33 = (struct SemanticsUM::NamedEntityCollectionUM *)v36;
                  v33 = (struct SemanticsUM::NamedEntityCollectionUM **)(v36 + 16);
                }
                else
                {
                  TokenSpan = -2147024882;
                }
              }
              CoTaskMemFree(pv);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
          }
          (*(void (__fastcall **)(struct SemanticsUM::TokenCollectionUM *))(*(_QWORD *)v40 + 16LL))(v40);
        }
        while ( TokenSpan >= 0 );
        v19 = v39;
        v7 = (const wchar_t *)v46;
      }
      v39 = 0;
      v20 = (**(__int64 (__fastcall ***)(struct SemanticsUM::TokenCollectionUM *))v10)(v10);
      StringFlags = SemanticsUM::NamedEntityCollectionUM::Create(v20, &v39);
      if ( StringFlags >= 0 )
      {
        v41 = 0;
        v23 = v39;
        StringFlags = StructuredQuery1::NamedEntityCollector::CreateInstance(
                        v39,
                        *((struct SemanticsUM::SchemaEngine **)this + 12),
                        v22,
                        &v41);
        if ( StringFlags >= 0 )
        {
          v40 = 0;
          StringFlags = StructuredQuery1::TokenCollection::CreateInstance(v10, v21, (void **)&v40);
          if ( StringFlags >= 0 )
          {
            v24 = *(struct SemanticsUM::NamedEntityCollectionUM **)(*((_QWORD *)this + 13) + 24LL);
            v39 = v24;
            while ( v24 )
            {
              v25 = *((_QWORD *)v24 + 1);
              v26 = *(__int64 (__fastcall **)(__int64, struct SemanticsUM::StructuredSemanticSolution *, _QWORD, struct SemanticsUM::TokenCollectionUM *, struct SemanticsUM::TokenCollectionUM **))(*(_QWORD *)v25 + 32LL);
              v27 = (struct SemanticsUM::TokenCollectionUM **)v41;
              UserDefaultLCID = GetUserDefaultLCID();
              v37 = v27;
              v7 = (const wchar_t *)v46;
              StringFlags = v26(v25, v46, UserDefaultLCID, v40, v37);
              v24 = (struct SemanticsUM::NamedEntityCollectionUM *)*((_QWORD *)v39 + 2);
              v39 = v24;
              if ( StringFlags < 0 )
                goto LABEL_27;
            }
            v46 = 0;
            StringFlags = StructuredQuery1::QueryParser::ProcessInputString(
                            (StructuredQuery1::QueryParser *)((char *)this - 8),
                            v7,
                            v49,
                            v10,
                            v23,
                            v19,
                            v47,
                            &v46);
            if ( StringFlags < 0 )
            {
              SearchIndexerTrace::Warning(
                (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\structuredquery\\\\dll\\\\queryparser.cpp\"",
                (const wchar_t *)0x224,
                (unsigned int)L"Failed to parse the input string.",
                v29);
            }
            else
            {
              v43 = 0;
              v39 = 0;
              v30 = v46;
              StringFlags = StructuredQuery1::Solution::Create(
                              *((struct StructuredQuery1::QueryExpressionCustomization **)this + 13),
                              *((struct SemanticsUM::SchemaEngine **)this + 12),
                              *((_BYTE *)this + 84),
                              v46,
                              v10,
                              *((struct ILanguageResourcePool **)this + 8),
                              &v39);
              if ( StringFlags >= 0 )
              {
                v31 = v39;
                StringFlags = (**(__int64 (__fastcall ***)(struct SemanticsUM::NamedEntityCollectionUM *, const struct _GUID *, void **))v39)(
                                v39,
                                v50,
                                &v43);
                (*(void (__fastcall **)(struct SemanticsUM::NamedEntityCollectionUM *))(*(_QWORD *)v31 + 16LL))(v31);
              }
              (*(void (__fastcall **)(struct SemanticsUM::StructuredSemanticSolution *))(*(_QWORD *)v30 + 16LL))(v30);
            }
LABEL_27:
            (*(void (__fastcall **)(struct SemanticsUM::TokenCollectionUM *))(*(_QWORD *)v40 + 16LL))(v40);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
        }
        if ( v23 )
          (*(void (__fastcall **)(struct SemanticsUM::NamedEntityCollectionUM *, __int64))(*(_QWORD *)v23 + 24LL))(
            v23,
            1);
        v11 = v43;
      }
      if ( v19 )
        SemanticsUM::CustomProperty::`scalar deleting destructor'(v19, (unsigned int)v21);
      if ( v10 )
        (*(void (__fastcall **)(struct SemanticsUM::TokenCollectionUM *, __int64))(*(_QWORD *)v10 + 16LL))(v10, 1);
    }
    goto LABEL_36;
  }
  StringFlags = -2147467261;
LABEL_38:
  if ( (byte_1800B11C3 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_StructuredQuery_ParseText_Stop,
      v9,
      1,
      &v53);
  return (unsigned int)StringFlags;
}

```

## disassembly

```asm
0x1800123f0  mov     [rsp-8+arg_18], rbx
0x1800123f5  push    rbp
0x1800123f6  push    rsi
0x1800123f7  push    rdi
0x1800123f8  push    r12
0x1800123fa  push    r13
0x1800123fc  push    r14
0x1800123fe  push    r15
0x180012400  lea     rbp, [rsp-17h]
0x180012405  sub     rsp, 0D0h
0x18001240c  mov     rax, cs:__security_cookie
0x180012413  xor     rax, rsp
0x180012416  mov     [rbp+47h+var_40], rax
0x18001241a  mov     [rbp+47h+var_80], r9d
0x18001241e  mov     rsi, r8
0x180012421  mov     rbx, rdx
0x180012424  mov     [rbp+47h+var_88], rdx
0x180012428  mov     r14, rcx
0x18001242b  mov     rax, [rbp+47h+arg_20]
0x18001242f  mov     [rbp+47h+var_68], rax
0x180012433  mov     rdi, [rbp+47h+arg_28]
0x180012437  mov     [rbp+47h+var_58], rdi
0x18001243b  test    cs:byte_1800B11C3, 40h
0x180012442  jnz     loc_1800127F5
0x180012448  mov     r9, rbx; wchar_t *
0x18001244b  lea     r8, aAttemptingToPa; "Attempting to parse query: %ws"
0x180012452  mov     edx, 1ABh; wchar_t *
0x180012457  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18001245e  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180012463  xor     r15d, r15d
0x180012466  test    rdi, rdi
0x180012469  jz      loc_1800127A0
0x18001246f  mov     r13d, r15d
0x180012472  mov     [rbp+47h+var_A0], r15
0x180012476  mov     edi, 80070057h
0x18001247b  test    rbx, rbx
0x18001247e  jz      loc_180012763
0x180012484  mov     edx, 7800h
0x180012489  mov     ecx, edx
0x18001248b  mov     rax, rbx
0x18001248e  cmp     [rax], r15w
0x180012492  jz      short loc_18001249E
0x180012494  add     rax, 2
0x180012498  sub     rcx, 1
0x18001249c  jnz     short loc_18001248E
0x18001249e  mov     rax, rcx
0x1800124a1  sub     rdx, rcx
0x1800124a4  neg     rax
0x1800124a7  sbb     r12, r12
0x1800124aa  and     r12, rdx
0x1800124ad  mov     [rbp+47h+var_70], r12
0x1800124b1  test    rcx, rcx
0x1800124b4  jz      loc_180012763
0x1800124ba  lea     rcx, [r14-8]; this
0x1800124be  call    ?ReadyToRun@QueryParser@StructuredQuery1@@AEAAJXZ; StructuredQuery1::QueryParser::ReadyToRun(void)
0x1800124c3  mov     edi, eax
0x1800124c5  test    eax, eax
0x1800124c7  js      loc_180012763
0x1800124cd  lea     rax, [r14+98h]
0x1800124d4  mov     [rbp+47h+SRWLock], rax
0x1800124d8  mov     rcx, rax; SRWLock
0x1800124db  call    cs:__imp_AcquireSRWLockShared
0x1800124e1  mov     [rbp+47h+var_B8], r15
0x1800124e5  mov     [rbp+47h+var_A8], r13
0x1800124e9  lea     r8, [rbp+47h+var_A8]; unsigned int
0x1800124ed  mov     edx, r12d; cchSrc
0x1800124f0  mov     rcx, rbx; lpSrcStr
0x1800124f3  call    ?GetStringFlags@SemanticsUM@@YAJPEB_WKPEAPEAG@Z; SemanticsUM::GetStringFlags(wchar_t const *,ulong,ushort * *)
0x1800124f8  mov     edi, eax
0x1800124fa  test    eax, eax
0x1800124fc  js      loc_180012759
0x180012502  mov     eax, [r14+30h]
0x180012506  mov     dword ptr [rbp+47h+var_50], eax
0x180012509  mov     [rbp+47h+var_48], r13
0x18001250d  mov     rcx, [r14+38h]
0x180012511  test    rcx, rcx
0x180012514  jnz     loc_1800127A7
0x18001251a  mov     rdx, [r14+40h]; struct ILanguageResourcePool *
0x18001251e  lea     rcx, [rbp+47h+var_50]; this
0x180012522  call    ?Initialize@Tokenizer@StructuredQuery1@@QEAAJPEAUILanguageResourcePool@@@Z; StructuredQuery1::Tokenizer::Initialize(ILanguageResourcePool *)
0x180012527  mov     edi, eax
0x180012529  test    eax, eax
0x18001252b  js      short loc_18001254F
0x18001252d  lea     rax, [rbp+47h+var_B8]
0x180012531  mov     [rsp+100h+var_E0], rax; struct SemanticsUM::TokenCollectionUM **
0x180012536  mov     r9d, r12d; unsigned int
0x180012539  mov     r8, [rbp+47h+var_A8]; unsigned __int16 *
0x18001253d  mov     rdx, rbx; wchar_t *
0x180012540  lea     rcx, [rbp+47h+var_50]; this
0x180012544  call    ?TokenizeWorker@Tokenizer@StructuredQuery1@@AEAAJPEB_WPEBGKPEAPEAVTokenCollectionUM@SemanticsUM@@_N@Z; StructuredQuery1::Tokenizer::TokenizeWorker(wchar_t const *,ushort const *,ulong,SemanticsUM::TokenCollectionUM * *,bool)
0x180012549  mov     edi, eax
0x18001254b  mov     r15, [rbp+47h+var_B8]
0x18001254f  mov     rcx, [rbp+47h+var_A8]; void *
0x180012553  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012558  nop
0x180012559  lea     rcx, [rbp+47h+var_48]
0x18001255d  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180012562  nop
0x180012563  test    edi, edi
0x180012565  js      loc_180012759
0x18001256b  xor     edi, edi
0x18001256d  mov     r12d, edi
0x180012570  mov     [rbp+47h+var_C0], rdi
0x180012574  test    rsi, rsi
0x180012577  jnz     loc_1800127D9
0x18001257d  mov     [rbp+47h+var_C0], rdi
0x180012581  mov     rax, [r15]
0x180012584  mov     rcx, r15
0x180012587  mov     rax, [rax]
0x18001258a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001258f  mov     ecx, eax; unsigned int
0x180012591  lea     rdx, [rbp+47h+var_C0]; struct SemanticsUM::NamedEntityCollectionUM **
0x180012595  call    ?Create@NamedEntityCollectionUM@SemanticsUM@@SAJKPEAPEAV12@@Z; SemanticsUM::NamedEntityCollectionUM::Create(ulong,SemanticsUM::NamedEntityCollectionUM * *)
0x18001259a  mov     edi, eax
0x18001259c  xor     esi, esi
0x18001259e  test    eax, eax
0x1800125a0  js      loc_180012737
0x1800125a6  mov     [rbp+47h+var_B0], rsi
0x1800125aa  lea     r9, [rbp+47h+var_B0]; void **
0x1800125ae  mov     rdx, [r14+60h]; struct SemanticsUM::SchemaEngine *
0x1800125b2  mov     r13, [rbp+47h+var_C0]
0x1800125b6  mov     rcx, r13; struct SemanticsUM::NamedEntityCollectionUM *
0x1800125b9  call    ?CreateInstance@NamedEntityCollector@StructuredQuery1@@SAJPEAVNamedEntityCollectionUM@SemanticsUM@@PEAVSchemaEngine@4@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::NamedEntityCollector::CreateInstance(SemanticsUM::NamedEntityCollectionUM *,SemanticsUM::SchemaEngine *,_GUID const &,void * *)
0x1800125be  mov     edi, eax
0x1800125c0  test    eax, eax
0x1800125c2  js      loc_180012719
0x1800125c8  mov     [rbp+47h+var_B8], rsi
0x1800125cc  lea     r8, [rbp+47h+var_B8]; void **
0x1800125d0  mov     rcx, r15; struct SemanticsUM::TokenCollectionUM *
0x1800125d3  call    ?CreateInstance@TokenCollection@StructuredQuery1@@SAJAEBVTokenCollectionUM@SemanticsUM@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenCollection::CreateInstance(SemanticsUM::TokenCollectionUM const &,_GUID const &,void * *)
0x1800125d8  mov     edi, eax
0x1800125da  test    eax, eax
0x1800125dc  js      loc_180012709
0x1800125e2  mov     rax, [r14+68h]
0x1800125e6  mov     rax, [rax+18h]
0x1800125ea  mov     [rbp+47h+var_C0], rax
0x1800125ee  test    rax, rax
0x1800125f1  jz      short loc_18001263F
0x1800125f3  mov     rsi, [rax+8]
0x1800125f7  mov     rax, [rsi]
0x1800125fa  mov     rdi, [rax+20h]
0x1800125fe  mov     rbx, [rbp+47h+var_B0]
0x180012602  call    cs:__imp_GetUserDefaultLCID
0x180012608  mov     [rsp+100h+var_E0], rbx
0x18001260d  mov     r9, [rbp+47h+var_B8]
0x180012611  mov     r8d, eax
0x180012614  mov     rbx, [rbp+47h+var_88]
0x180012618  mov     rdx, rbx
0x18001261b  mov     rcx, rsi
0x18001261e  mov     rax, rdi
0x180012621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012626  mov     edi, eax
0x180012628  mov     rax, [rbp+47h+var_C0]
0x18001262c  mov     rax, [rax+10h]
0x180012630  mov     [rbp+47h+var_C0], rax
0x180012634  xor     esi, esi
0x180012636  test    edi, edi
0x180012638  jns     short loc_1800125EE
0x18001263a  jmp     loc_1800126F9
0x18001263f  mov     [rbp+47h+var_88], rsi
0x180012643  lea     rax, [rbp+47h+var_88]
0x180012647  mov     [rsp+100h+var_C8], rax; struct SemanticsUM::StructuredSemanticSolution **
0x18001264c  mov     eax, [rbp+47h+var_80]
0x18001264f  mov     dword ptr [rsp+100h+var_D0], eax; unsigned int
0x180012653  mov     [rsp+100h+var_D8], r12; struct SemanticsUM::CustomProperty *
0x180012658  mov     [rsp+100h+var_E0], r13; struct SemanticsUM::NamedEntityCollectionUM *
0x18001265d  mov     r9, r15; struct SemanticsUM::TokenCollectionUM *
0x180012660  mov     r8, [rbp+47h+var_70]; unsigned __int64
0x180012664  mov     rdx, rbx; wchar_t *
0x180012667  lea     rcx, [r14-8]; this
0x18001266b  call    ?ProcessInputString@QueryParser@StructuredQuery1@@AEBAJPEB_W_KAEBVTokenCollectionUM@SemanticsUM@@AEBVNamedEntityCollectionUM@4@PEBVCustomProperty@4@KPEAPEAVStructuredSemanticSolution@4@@Z; StructuredQuery1::QueryParser::ProcessInputString(wchar_t const *,unsigned __int64,SemanticsUM::TokenCollectionUM const &,SemanticsUM::NamedEntityCollectionUM const &,SemanticsUM::CustomProperty const *,ulong,SemanticsUM::StructuredSemanticSolution * *)
0x180012670  mov     edi, eax
0x180012672  test    eax, eax
0x180012674  js      loc_1800127BC
0x18001267a  mov     [rbp+47h+var_A0], rsi
0x18001267e  mov     [rbp+47h+var_C0], rsi
0x180012682  lea     rax, [rbp+47h+var_C0]
0x180012686  mov     [rsp+100h+var_D0], rax; struct StructuredQuery1::Solution **
0x18001268b  mov     rax, [r14+40h]
0x18001268f  mov     [rsp+100h+var_D8], rax; struct ILanguageResourcePool *
0x180012694  mov     [rsp+100h+var_E0], r15; struct SemanticsUM::TokenCollectionUM *
0x180012699  mov     rsi, [rbp+47h+var_88]
0x18001269d  mov     r9, rsi; struct SemanticsUM::StructuredSemanticSolution *
0x1800126a0  mov     r8b, [r14+54h]; bool
0x1800126a4  mov     rdx, [r14+60h]; struct SemanticsUM::SchemaEngine *
0x1800126a8  mov     rcx, [r14+68h]; struct StructuredQuery1::QueryExpressionCustomization *
0x1800126ac  call    ?Create@Solution@StructuredQuery1@@SAJPEAVQueryExpressionCustomization@2@PEAVSchemaEngine@SemanticsUM@@_NPEAVStructuredSemanticSolution@5@PEBVTokenCollectionUM@5@PEAUILanguageResourcePool@@PEAPEAV12@@Z; StructuredQuery1::Solution::Create(StructuredQuery1::QueryExpressionCustomization *,SemanticsUM::SchemaEngine *,bool,SemanticsUM::StructuredSemanticSolution *,SemanticsUM::TokenCollectionUM const *,ILanguageResourcePool *,StructuredQuery1::Solution * *)
0x1800126b1  mov     edi, eax
0x1800126b3  test    eax, eax
0x1800126b5  js      short loc_1800126E2
0x1800126b7  mov     rbx, [rbp+47h+var_C0]
0x1800126bb  mov     rax, [rbx]
0x1800126be  lea     r8, [rbp+47h+var_A0]
0x1800126c2  mov     rdx, [rbp+47h+var_68]
0x1800126c6  mov     rcx, rbx
0x1800126c9  mov     rax, [rax]
0x1800126cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126d1  mov     edi, eax
0x1800126d3  mov     rax, [rbx]
0x1800126d6  mov     rcx, rbx
0x1800126d9  mov     rax, [rax+10h]
0x1800126dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e2  mov     rax, [rbp+47h+var_A0]
0x1800126e6  mov     [rbp+47h+var_A0], rax
0x1800126ea  mov     rax, [rsi]
0x1800126ed  mov     rcx, rsi
0x1800126f0  mov     rax, [rax+10h]
0x1800126f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f9  mov     rcx, [rbp+47h+var_B8]
0x1800126fd  mov     rax, [rcx]
0x180012700  mov     rax, [rax+10h]
0x180012704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012709  mov     rcx, [rbp+47h+var_B0]
0x18001270d  mov     rax, [rcx]
0x180012710  mov     rax, [rax+10h]
0x180012714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012719  test    r13, r13
0x18001271c  jz      short loc_180012733
0x18001271e  mov     rax, [r13+0]
0x180012722  mov     edx, 1
0x180012727  mov     rcx, r13
0x18001272a  mov     rax, [rax+18h]
0x18001272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012733  mov     r13, [rbp+47h+var_A0]
0x180012737  test    r12, r12
0x18001273a  jnz     loc_18001281C
0x180012740  test    r15, r15
0x180012743  jz      short loc_180012759
0x180012745  mov     rax, [r15]
0x180012748  mov     edx, 1
0x18001274d  mov     rcx, r15
0x180012750  mov     rax, [rax+10h]
0x180012754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012759  mov     rcx, [rbp+47h+SRWLock]; SRWLock
0x18001275d  call    cs:__imp_ReleaseSRWLockShared
0x180012763  mov     rax, [rbp+47h+var_58]
0x180012767  mov     [rax], r13
0x18001276a  test    cs:byte_1800B11C3, 40h
0x180012771  jnz     loc_180012829
0x180012777  mov     eax, edi
0x180012779  mov     rcx, [rbp+47h+var_40]
0x18001277d  xor     rcx, rsp; StackCookie
0x180012780  call    __security_check_cookie
0x180012785  mov     rbx, [rsp+100h+arg_18]
0x18001278d  add     rsp, 0D0h
0x180012794  pop     r15
0x180012796  pop     r14
0x180012798  pop     r13
0x18001279a  pop     r12
0x18001279c  pop     rdi
0x18001279d  pop     rsi
0x18001279e  pop     rbp
0x18001279f  retn
0x1800127a0  mov     edi, 80004003h
0x1800127a5  jmp     short loc_18001276A
0x1800127a7  mov     [rbp+47h+var_48], rcx
0x1800127ab  mov     rax, [rcx]
0x1800127ae  mov     rax, [rax+8]
0x1800127b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b7  jmp     loc_18001252D
0x1800127bc  lea     r8, aFailedToParseT; "Failed to parse the input string."
0x1800127c3  mov     edx, 224h; wchar_t *
0x1800127c8  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800127cf  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x1800127d4  jmp     loc_1800126F9
0x1800127d9  lea     r12, [rbp+47h+var_C0]
0x1800127dd  mov     rax, [rsi]
0x1800127e0  mov     rcx, rsi
0x1800127e3  mov     rax, [rax+28h]
0x1800127e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ec  mov     [rbp+47h+var_B8], rdi
0x1800127f0  jmp     loc_180088230
0x1800127f5  lea     rax, [rbp+47h+var_50]
0x1800127f9  mov     [rsp+100h+var_E0], rax
0x1800127fe  mov     r9d, 1
0x180012804  lea     rdx, ShellTraceId_StructuredQuery_ParseText_Start
0x18001280b  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180012812  call    McGenEventWrite_EventWriteTransfer
0x180012817  jmp     loc_180012448
0x18001281c  mov     rcx, r12; this
0x18001281f  call    ??_GCustomProperty@SemanticsUM@@QEAAPEAXI@Z; SemanticsUM::CustomProperty::`scalar deleting destructor'(uint)
0x180012824  jmp     loc_180012740
0x180012829  lea     rax, [rbp+47h+var_50]
0x18001282d  mov     [rsp+100h+var_E0], rax
0x180012832  mov     r9d, 1
0x180012838  lea     rdx, ShellTraceId_StructuredQuery_ParseText_Stop
0x18001283f  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180012846  call    McGenEventWrite_EventWriteTransfer
0x18001284b  jmp     loc_180012777
0x180088230  mov     rax, [rsi]
0x180088233  xor     r9d, r9d
0x180088236  lea     r8, [rbp+47h+var_B8]
0x18008823a  lea     edx, [r9+1]
0x18008823e  mov     rcx, rsi
0x180088241  mov     rax, [rax+18h]
0x180088245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008824a  test    eax, eax
0x18008824c  jnz     loc_180088366
0x180088252  mov     [rbp+47h+var_B0], rdi
0x180088256  mov     rcx, [rbp+47h+var_B8]
  ... truncated ...
```
