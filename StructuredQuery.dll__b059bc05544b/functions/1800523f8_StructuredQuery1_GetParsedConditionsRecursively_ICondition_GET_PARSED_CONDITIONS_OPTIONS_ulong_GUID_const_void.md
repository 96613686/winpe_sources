# StructuredQuery1::GetParsedConditionsRecursively(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,ulong,_GUID const &,void * *,wchar_t * *,wchar_t * *,ulong *,_FILETIME const *,_GUID const &,void * *,StructuredQuery1::Solution *)

- ea: `0x1800523f8`
- end: `0x1800528eb`
- name: `?GetParsedConditionsRecursively@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@KAEBU_GUID@@PEAPEAXPEAPEA_W4PEAKPEBU_FILETIME@@23PEAVSolution@1@@Z`
- size: `1267`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800523f8`
- `0x180055a30`

## callees

- `0x18000b180`
- `0x18000bd20`
- `0x1800523f8`
- `0x1800528f4`
- `0x180055ef4`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005249f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005249f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005255b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005255b`

## pseudocode

```c
__int64 StructuredQuery1::GetParsedConditionsRecursively(
        __int64 (__fastcall ***a1)(_QWORD, struct _GUID *, void **),
        __int64 a2,
        unsigned int a3,
        struct _GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        FILETIME *lpFileTime1,
        struct _GUID *a10,
        ...)
{
  void **v10; // rsi
  DWORD v11; // r15d
  unsigned int v13; // r14d
  int ParsedQueryRoot; // ebx
  __int64 v16; // r15
  StructuredQuery1::Solution *v17; // rcx
  __int64 v18; // rcx
  __int64 (__fastcall **v19)(_QWORD, struct _GUID *, void **); // rax
  __int64 (__fastcall **v20)(_QWORD, struct _GUID *, void **); // rax
  StructuredQuery1::Solution *v21; // rcx
  struct IObjectArray *v22; // rdi
  int ParsedConditionsRecursively; // eax
  GUID *v24; // rdx
  DWORD v25; // edi
  __int64 v26; // r15
  enum tagCONDITION_TYPE v28; // [rsp+60h] [rbp-31h] BYREF
  __int64 v29; // [rsp+68h] [rbp-29h] BYREF
  __int64 v30; // [rsp+70h] [rbp-21h] BYREF
  __int64 v31; // [rsp+78h] [rbp-19h] BYREF
  struct IObjectArray *v32[10]; // [rsp+80h] [rbp-11h] BYREF
  FILETIME FileTime2; // [rsp+130h] [rbp+9Fh] BYREF
  va_list FileTime2a; // [rsp+130h] [rbp+9Fh]
  __int64 v36; // [rsp+138h] [rbp+A7h]
  va_list va1; // [rsp+140h] [rbp+AFh] BYREF

  va_start(va1, a10);
  va_start(FileTime2a, a10);
  FileTime2 = va_arg(va1, FILETIME);
  v36 = va_arg(va1, _QWORD);
  v10 = (void **)FileTime2;
  v11 = 0;
  v13 = a2;
  if ( FileTime2 )
    **(_QWORD **)&FileTime2 = 0;
  v29 = 0;
  ParsedQueryRoot = StructuredQuery1::GetParsedQueryRoot(a1, a2, &v29);
  if ( ParsedQueryRoot >= 0 )
  {
    if ( v29 )
    {
      FileTime2 = 0;
      ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v29 + 72LL))(
                          v29,
                          (FILETIME *)FileTime2a);
      if ( ParsedQueryRoot >= 0 )
      {
        v16 = *a8;
        if ( (unsigned int)v16 >= a3
          || (v17 = (StructuredQuery1::Solution *)lpFileTime1) != 0
          && CompareFileTime(lpFileTime1, (const FILETIME *)FileTime2a) )
        {
          if ( (v13 & 4) != 0 )
          {
            ParsedQueryRoot = -2147024774;
          }
          else if ( v10 )
          {
            ParsedQueryRoot = (**a1)(a1, a10, v10);
          }
          goto LABEL_29;
        }
        if ( !a5 || (ParsedQueryRoot = (**a1)(a1, a4, (void **)(a5 + 8 * v16)), ParsedQueryRoot >= 0) )
        {
          if ( a6 )
          {
            ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 32LL))(v29, a6 + 8 * v16);
            if ( ParsedQueryRoot < 0 )
            {
LABEL_21:
              if ( a5 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a5 + 8 * v16) + 16LL))(*(_QWORD *)(a5 + 8 * v16));
                *(_QWORD *)(a5 + 8 * v16) = 0;
              }
              goto LABEL_29;
            }
          }
          if ( a7 )
          {
            ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 40LL))(v29, a7 + 8 * v16);
            if ( ParsedQueryRoot < 0 )
            {
LABEL_19:
              if ( a6 )
              {
                CoTaskMemFree(*(LPVOID *)(a6 + 8 * v16));
                *(_QWORD *)(a6 + 8 * v16) = 0;
              }
              goto LABEL_21;
            }
          }
          if ( v10 )
          {
            ParsedQueryRoot = StructuredQuery1::Solution::MakeTruthValue(v17, 1, a10, v10);
            if ( ParsedQueryRoot < 0 )
            {
              if ( a7 )
              {
                CoTaskMemFree(*(LPVOID *)(a7 + 8 * v16));
                *(_QWORD *)(a7 + 8 * v16) = 0;
              }
              goto LABEL_19;
            }
          }
          else
          {
            ParsedQueryRoot = 0;
          }
          ++*a8;
        }
      }
LABEL_29:
      v18 = v29;
LABEL_58:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      return (unsigned int)ParsedQueryRoot;
    }
    v19 = *a1;
    v28 = CT_AND_CONDITION;
    ParsedQueryRoot = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, struct _GUID *, void **), enum tagCONDITION_TYPE *))v19[8])(
                        a1,
                        &v28);
    if ( ParsedQueryRoot >= 0 )
    {
      if ( v28 )
      {
        if ( v10 )
          return (unsigned int)(**a1)(a1, a10, v10);
      }
      else
      {
        v20 = *a1;
        v30 = 0;
        ParsedQueryRoot = v20[9](a1, &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9, (void **)&v30);
        if ( ParsedQueryRoot >= 0 )
        {
          FileTime2.dwLowDateTime = 0;
          ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v30 + 24LL))(
                              v30,
                              (FILETIME *)FileTime2a);
          if ( ParsedQueryRoot >= 0 )
          {
            if ( v10 )
            {
              v32[0] = 0;
              ParsedQueryRoot = FixedCapacityObjectCollection::CreateInstance(
                                  FileTime2.dwLowDateTime,
                                  &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                  (void **)v32);
              if ( ParsedQueryRoot >= 0 )
              {
                v22 = v32[0];
                while ( v11 < FileTime2.dwLowDateTime )
                {
                  v32[0] = 0;
                  ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IObjectArray **))(*(_QWORD *)v30 + 32LL))(
                                      v30,
                                      v11,
                                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                      v32);
                  if ( ParsedQueryRoot >= 0 )
                  {
                    v31 = 0;
                    if ( *a8 < a3 || (v13 & 6) != 0 )
                      ParsedConditionsRecursively = StructuredQuery1::GetParsedConditionsRecursively(
                                                      v32[0],
                                                      v13,
                                                      a3,
                                                      a4,
                                                      a5,
                                                      a6,
                                                      a7,
                                                      a8,
                                                      lpFileTime1,
                                                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                                      &v31,
                                                      v36);
                    else
                      ParsedConditionsRecursively = ((__int64 (__fastcall *)(struct IObjectArray *, GUID *, __int64 *))v32[0]->lpVtbl->QueryInterface)(
                                                      v32[0],
                                                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                                      &v31);
                    ParsedQueryRoot = ParsedConditionsRecursively;
                    if ( ParsedConditionsRecursively >= 0 )
                    {
                      ParsedQueryRoot = ((__int64 (__fastcall *)(struct IObjectArray *, __int64))v22->lpVtbl[1].QueryInterface)(
                                          v22,
                                          v31);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                    ((void (__fastcall *)(struct IObjectArray *))v32[0]->lpVtbl->Release)(v32[0]);
                  }
                  ++v11;
                  v24 = &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7;
                  if ( ParsedQueryRoot < 0 )
                    goto LABEL_49;
                }
                ParsedQueryRoot = StructuredQuery1::Solution::MakeCompound(v21, v28, v22, 1, 1, a10, v10);
LABEL_49:
                ((void (__fastcall *)(struct IObjectArray *, GUID *))v22->lpVtbl->Release)(v22, v24);
              }
            }
            else
            {
              v25 = 0;
              v26 = v36;
              do
              {
                if ( v25 >= FileTime2.dwLowDateTime || *a8 >= a3 && (v13 & 6) == 0 )
                  break;
                v32[0] = 0;
                ParsedQueryRoot = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, struct IObjectArray **))(*(_QWORD *)v30 + 32LL))(
                                    v30,
                                    v25,
                                    &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                    v32);
                if ( ParsedQueryRoot >= 0 )
                {
                  ParsedQueryRoot = StructuredQuery1::GetParsedConditionsRecursively(
                                      v32[0],
                                      v13,
                                      a3,
                                      a4,
                                      a5,
                                      a6,
                                      a7,
                                      a8,
                                      lpFileTime1,
                                      a10,
                                      0,
                                      v26);
                  ((void (__fastcall *)(struct IObjectArray *))v32[0]->lpVtbl->Release)(v32[0]);
                }
                ++v25;
              }
              while ( ParsedQueryRoot >= 0 );
            }
          }
          v18 = v30;
          goto LABEL_58;
        }
      }
    }
  }
  return (unsigned int)ParsedQueryRoot;
}

```

## disassembly

```asm
0x1800523f8  mov     [rsp-8+arg_18], r9
0x1800523fd  push    rbp
0x1800523fe  push    rbx
0x1800523ff  push    rsi
0x180052400  push    rdi
0x180052401  push    r12
0x180052403  push    r13
0x180052405  push    r14
0x180052407  push    r15
0x180052409  lea     rbp, [rsp-7]
0x18005240e  sub     rsp, 98h
0x180052415  mov     rsi, qword ptr [rbp+3Fh+FileTime2.dwLowDateTime]
0x18005241c  xor     r15d, r15d
0x18005241f  mov     r12d, r8d
0x180052422  mov     r14d, edx
0x180052425  mov     rdi, rcx
0x180052428  test    rsi, rsi
0x18005242b  jz      short loc_180052430
0x18005242d  mov     [rsi], r15
0x180052430  lea     r8, [rbp+3Fh+var_68]
0x180052434  mov     [rbp+3Fh+var_68], r15
0x180052438  call    ?GetParsedQueryRoot@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@PEAPEAUIConditionHistory@@@Z; StructuredQuery1::GetParsedQueryRoot(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,IConditionHistory * *)
0x18005243d  mov     ebx, eax
0x18005243f  test    eax, eax
0x180052441  js      loc_1800528D5
0x180052447  mov     rcx, [rbp+3Fh+var_68]
0x18005244b  test    rcx, rcx
0x18005244e  jz      loc_1800525CC
0x180052454  mov     qword ptr [rbp+3Fh+FileTime2.dwLowDateTime], r15
0x18005245b  lea     rdx, [rbp+3Fh+FileTime2]
0x180052462  mov     rax, [rcx]
0x180052465  mov     rax, [rax+48h]
0x180052469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005246e  mov     ebx, eax
0x180052470  test    eax, eax
0x180052472  js      loc_1800525C3
0x180052478  mov     r13, [rbp+3Fh+arg_38]
0x18005247f  mov     r15d, [r13+0]
0x180052483  cmp     r15d, r12d
0x180052486  jnb     loc_180052597
0x18005248c  mov     rcx, [rbp+3Fh+lpFileTime1]; lpFileTime1
0x180052493  test    rcx, rcx
0x180052496  jz      short loc_1800524AD
0x180052498  lea     rdx, [rbp+3Fh+FileTime2]; lpFileTime2
0x18005249f  call    cs:__imp_CompareFileTime
0x1800524a5  test    eax, eax
0x1800524a7  jnz     loc_180052597
0x1800524ad  mov     r12, [rbp+3Fh+arg_20]
0x1800524b1  mov     r14, r15
0x1800524b4  test    r12, r12
0x1800524b7  jz      short loc_1800524D9
0x1800524b9  mov     rax, [rdi]
0x1800524bc  lea     r8, [r12+r15*8]
0x1800524c0  mov     rdx, [rbp+3Fh+arg_18]
0x1800524c4  mov     rcx, rdi
0x1800524c7  mov     rax, [rax]
0x1800524ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524cf  mov     ebx, eax
0x1800524d1  test    eax, eax
0x1800524d3  js      loc_1800525C3
0x1800524d9  mov     rdi, [rbp+3Fh+arg_28]
0x1800524dd  test    rdi, rdi
0x1800524e0  jz      short loc_1800524FC
0x1800524e2  mov     rcx, [rbp+3Fh+var_68]
0x1800524e6  lea     rdx, [rdi+r15*8]
0x1800524ea  mov     rax, [rcx]
0x1800524ed  mov     rax, [rax+20h]
0x1800524f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524f6  mov     ebx, eax
0x1800524f8  test    eax, eax
0x1800524fa  js      short loc_18005256D
0x1800524fc  mov     r15, [rbp+3Fh+arg_30]
0x180052500  test    r15, r15
0x180052503  jz      short loc_18005251F
0x180052505  mov     rcx, [rbp+3Fh+var_68]
0x180052509  lea     rdx, [r15+r14*8]
0x18005250d  mov     rax, [rcx]
0x180052510  mov     rax, [rax+28h]
0x180052514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052519  mov     ebx, eax
0x18005251b  test    eax, eax
0x18005251d  js      short loc_180052552
0x18005251f  test    rsi, rsi
0x180052522  jz      short loc_18005258F
0x180052524  mov     r8, [rbp+3Fh+arg_48]; struct _GUID *
0x18005252b  mov     r9, rsi; void **
0x18005252e  mov     dl, 1; bool
0x180052530  call    ?MakeTruthValue@Solution@StructuredQuery1@@QEAAJ_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeTruthValue(bool,_GUID const &,void * *)
0x180052535  mov     ebx, eax
0x180052537  test    eax, eax
0x180052539  jns     short loc_180052591
0x18005253b  test    r15, r15
0x18005253e  jz      short loc_180052552
0x180052540  mov     rcx, [r15+r14*8]; pv
0x180052544  call    cs:__imp_CoTaskMemFree
0x18005254a  mov     qword ptr [r15+r14*8], 0
0x180052552  test    rdi, rdi
0x180052555  jz      short loc_18005256D
0x180052557  mov     rcx, [rdi+r14*8]; pv
0x18005255b  call    cs:__imp_CoTaskMemFree
0x180052561  mov     qword ptr [rdi+r14*8], 0
0x180052569  test    ebx, ebx
0x18005256b  jns     short loc_1800525C3
0x18005256d  test    r12, r12
0x180052570  jz      short loc_1800525C3
0x180052572  lfence
0x180052575  mov     rcx, [r12+r14*8]
0x180052579  mov     rax, [rcx]
0x18005257c  mov     rax, [rax+10h]
0x180052580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052585  mov     qword ptr [r12+r14*8], 0
0x18005258d  jmp     short loc_1800525C3
0x18005258f  xor     ebx, ebx
0x180052591  inc     dword ptr [r13+0]
0x180052595  jmp     short loc_1800525C3
0x180052597  test    r14b, 4
0x18005259b  jz      short loc_1800525A4
0x18005259d  mov     ebx, 8007007Ah
0x1800525a2  jmp     short loc_1800525C3
0x1800525a4  test    rsi, rsi
0x1800525a7  jz      short loc_1800525C3
0x1800525a9  mov     rax, [rdi]
0x1800525ac  mov     r8, rsi
0x1800525af  mov     rdx, [rbp+3Fh+arg_48]
0x1800525b6  mov     rcx, rdi
0x1800525b9  mov     rax, [rax]
0x1800525bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525c1  mov     ebx, eax
0x1800525c3  mov     rcx, [rbp+3Fh+var_68]
0x1800525c7  jmp     loc_1800528A8
0x1800525cc  mov     rax, [rdi]
0x1800525cf  lea     rdx, [rbp+3Fh+var_70]
0x1800525d3  mov     rcx, rdi
0x1800525d6  mov     [rbp+3Fh+var_70], r15d
0x1800525da  mov     rax, [rax+40h]
0x1800525de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525e3  mov     ebx, eax
0x1800525e5  test    eax, eax
0x1800525e7  js      loc_1800528D5
0x1800525ed  cmp     [rbp+3Fh+var_70], r15d
0x1800525f1  jnz     loc_1800528B6
0x1800525f7  mov     rax, [rdi]
0x1800525fa  lea     r8, [rbp+3Fh+var_60]
0x1800525fe  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180052605  mov     [rbp+3Fh+var_60], r15
0x180052609  mov     rcx, rdi
0x18005260c  mov     rax, [rax+48h]
0x180052610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052615  mov     ebx, eax
0x180052617  test    eax, eax
0x180052619  js      loc_1800528D5
0x18005261f  mov     rcx, [rbp+3Fh+var_60]
0x180052623  lea     rdx, [rbp+3Fh+FileTime2]
0x18005262a  mov     [rbp+3Fh+FileTime2.dwLowDateTime], r15d
0x180052631  mov     rax, [rcx]
0x180052634  mov     rax, [rax+18h]
0x180052638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005263d  mov     ebx, eax
0x18005263f  test    eax, eax
0x180052641  js      loc_1800528A4
0x180052647  test    rsi, rsi
0x18005264a  jz      loc_1800527D8
0x180052650  mov     ecx, [rbp+3Fh+FileTime2.dwLowDateTime]; unsigned int
0x180052656  lea     r8, [rbp+3Fh+var_50]; void **
0x18005265a  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x180052661  mov     [rbp+3Fh+var_50], r15
0x180052665  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x18005266a  mov     ebx, eax
0x18005266c  test    eax, eax
0x18005266e  js      loc_1800528A4
0x180052674  mov     r13, [rbp+3Fh+arg_38]
0x18005267b  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180052682  mov     rdi, [rbp+3Fh+var_50]
0x180052686  cmp     r15d, [rbp+3Fh+FileTime2.dwLowDateTime]
0x18005268d  jnb     loc_18005279E
0x180052693  mov     rcx, [rbp+3Fh+var_60]
0x180052697  lea     r9, [rbp+3Fh+var_50]
0x18005269b  mov     [rbp+3Fh+var_50], 0
0x1800526a3  mov     r8, rdx
0x1800526a6  mov     edx, r15d
0x1800526a9  mov     rax, [rcx]
0x1800526ac  mov     rax, [rax+20h]
0x1800526b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526b5  mov     ebx, eax
0x1800526b7  test    eax, eax
0x1800526b9  js      loc_18005278A
0x1800526bf  mov     [rbp+3Fh+var_58], 0
0x1800526c7  cmp     [r13+0], r12d
0x1800526cb  jb      short loc_1800526EF
0x1800526cd  test    r14b, 6
0x1800526d1  jnz     short loc_1800526EF
0x1800526d3  mov     rcx, [rbp+3Fh+var_50]
0x1800526d7  lea     r8, [rbp+3Fh+var_58]
0x1800526db  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800526e2  mov     rax, [rcx]
0x1800526e5  mov     rax, [rax]
0x1800526e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526ed  jmp     short loc_18005274F
0x1800526ef  mov     rax, [rbp+3Fh+arg_58]
0x1800526f6  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800526fd  mov     r9, [rbp+3Fh+arg_18]
0x180052701  mov     r8d, r12d
0x180052704  mov     rcx, [rbp+3Fh+var_50]
0x180052708  mov     [rsp+0D0h+var_78], rax
0x18005270d  lea     rax, [rbp+3Fh+var_58]
0x180052711  mov     [rsp+0D0h+var_80], rax
0x180052716  mov     rax, [rbp+3Fh+lpFileTime1]
0x18005271d  mov     [rsp+0D0h+var_88], rdx
0x180052722  mov     edx, r14d
0x180052725  mov     [rsp+0D0h+var_90], rax
0x18005272a  mov     rax, [rbp+3Fh+arg_30]
0x18005272e  mov     [rsp+0D0h+var_98], r13
0x180052733  mov     [rsp+0D0h+var_A0], rax
0x180052738  mov     rax, [rbp+3Fh+arg_28]
0x18005273c  mov     [rsp+0D0h+var_A8], rax
0x180052741  mov     rax, [rbp+3Fh+arg_20]
0x180052745  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18005274a  call    ?GetParsedConditionsRecursively@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@KAEBU_GUID@@PEAPEAXPEAPEA_W4PEAKPEBU_FILETIME@@23PEAVSolution@1@@Z; StructuredQuery1::GetParsedConditionsRecursively(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,ulong,_GUID const &,void * *,wchar_t * *,wchar_t * *,ulong *,_FILETIME const *,_GUID const &,void * *,StructuredQuery1::Solution *)
0x18005274f  mov     ebx, eax
0x180052751  test    eax, eax
0x180052753  js      short loc_18005277A
0x180052755  mov     rax, [rdi]
0x180052758  mov     rcx, rdi
0x18005275b  mov     rdx, [rbp+3Fh+var_58]
0x18005275f  mov     rax, [rax+28h]
0x180052763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052768  mov     rcx, [rbp+3Fh+var_58]
0x18005276c  mov     ebx, eax
0x18005276e  mov     rax, [rcx]
0x180052771  mov     rax, [rax+10h]
0x180052775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005277a  mov     rcx, [rbp+3Fh+var_50]
0x18005277e  mov     rax, [rcx]
0x180052781  mov     rax, [rax+10h]
0x180052785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005278a  inc     r15d
0x18005278d  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180052794  test    ebx, ebx
0x180052796  jns     loc_180052686
0x18005279c  jmp     short loc_1800527C4
0x18005279e  mov     rax, [rbp+3Fh+arg_48]
0x1800527a5  mov     r9b, 1; bool
0x1800527a8  mov     edx, [rbp+3Fh+var_70]; enum tagCONDITION_TYPE
0x1800527ab  mov     r8, rdi; struct IObjectArray *
0x1800527ae  mov     [rsp+0D0h+var_A0], rsi; void **
0x1800527b3  mov     [rsp+0D0h+var_A8], rax; struct _GUID *
0x1800527b8  mov     [rsp+0D0h+var_B0], 1; bool
0x1800527bd  call    ?MakeCompound@Solution@StructuredQuery1@@QEAAJW4tagCONDITION_TYPE@@PEAUIObjectArray@@_N2AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeCompound(tagCONDITION_TYPE,IObjectArray *,bool,bool,_GUID const &,void * *)
0x1800527c2  mov     ebx, eax
0x1800527c4  mov     rax, [rdi]
0x1800527c7  mov     rcx, rdi
0x1800527ca  mov     rax, [rax+10h]
0x1800527ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527d3  jmp     loc_1800528A4
0x1800527d8  mov     r13, [rbp+3Fh+arg_48]
0x1800527df  mov     edi, r15d
0x1800527e2  mov     r15, [rbp+3Fh+arg_58]
0x1800527e9  mov     rsi, [rbp+3Fh+arg_38]
0x1800527f0  cmp     edi, [rbp+3Fh+FileTime2.dwLowDateTime]
0x1800527f6  jnb     loc_1800528A4
0x1800527fc  cmp     [rsi], r12d
0x1800527ff  jb      short loc_18005280B
0x180052801  test    r14b, 6
0x180052805  jz      loc_1800528A4
0x18005280b  mov     rcx, [rbp+3Fh+var_60]
0x18005280f  lea     r9, [rbp+3Fh+var_50]
0x180052813  mov     [rbp+3Fh+var_50], 0
0x18005281b  lea     r8, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180052822  mov     edx, edi
0x180052824  mov     rax, [rcx]
0x180052827  mov     rax, [rax+20h]
0x18005282b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052830  mov     ebx, eax
0x180052832  test    eax, eax
0x180052834  js      short loc_18005289A
0x180052836  mov     rax, [rbp+3Fh+lpFileTime1]
0x18005283d  mov     r8d, r12d
0x180052840  mov     r9, [rbp+3Fh+arg_18]
0x180052844  mov     edx, r14d
0x180052847  mov     rcx, [rbp+3Fh+var_50]
0x18005284b  mov     [rsp+0D0h+var_78], r15
0x180052850  mov     [rsp+0D0h+var_80], 0
0x180052859  mov     [rsp+0D0h+var_88], r13
0x18005285e  mov     [rsp+0D0h+var_90], rax
0x180052863  mov     rax, [rbp+3Fh+arg_30]
0x180052867  mov     [rsp+0D0h+var_98], rsi
0x18005286c  mov     [rsp+0D0h+var_A0], rax
0x180052871  mov     rax, [rbp+3Fh+arg_28]
0x180052875  mov     [rsp+0D0h+var_A8], rax
0x18005287a  mov     rax, [rbp+3Fh+arg_20]
0x18005287e  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180052883  call    ?GetParsedConditionsRecursively@StructuredQuery1@@YAJPEAUICondition@@W4GET_PARSED_CONDITIONS_OPTIONS@@KAEBU_GUID@@PEAPEAXPEAPEA_W4PEAKPEBU_FILETIME@@23PEAVSolution@1@@Z; StructuredQuery1::GetParsedConditionsRecursively(ICondition *,GET_PARSED_CONDITIONS_OPTIONS,ulong,_GUID const &,void * *,wchar_t * *,wchar_t * *,ulong *,_FILETIME const *,_GUID const &,void * *,StructuredQuery1::Solution *)
0x180052888  mov     rcx, [rbp+3Fh+var_50]
0x18005288c  mov     ebx, eax
0x18005288e  mov     rax, [rcx]
0x180052891  mov     rax, [rax+10h]
0x180052895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005289a  inc     edi
0x18005289c  test    ebx, ebx
0x18005289e  jns     loc_1800527F0
  ... truncated ...
```
