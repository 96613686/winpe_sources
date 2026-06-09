# StructuredQuery1::CSchemaFromPropertySystem::ProcessBooleanPrefix(wchar_t const *,StructuredQuery1::IEntityInfo *,wchar_t const *,IMnemonics *,wchar_t const *)

- ea: `0x180051028`
- end: `0x18005135f`
- name: `?ProcessBooleanPrefix@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAUIEntityInfo@2@0PEAUIMnemonics@@0@Z`
- size: `823`
- prototype: `__int64 __usercall@<rax>(StructuredQuery1::CSchemaFromPropertySystem *__hidden this@<rcx>, const wchar_t *@<rdx>, struct StructuredQuery1::IEntityInfo *@<r8>, const wchar_t *@<r9>, struct IMnemonics *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c8c4`

## callees

- `0x180012148`
- `0x180012310`
- `0x18001e110`
- `0x180051028`
- `0x180051368`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800511a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180051228`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800511a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180051228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005125b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800511dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005125b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051311`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::ProcessBooleanPrefix(
        LCID *this,
        const wchar_t *a2,
        const struct _GUID *a3,
        const wchar_t *a4,
        struct IMnemonics *a5,
        const wchar_t *a6)
{
  unsigned int v7; // r14d
  int Instance; // ebx
  PCNZWCH v10; // rsi
  const struct _GUID *v11; // r8
  PCNZWCH v12; // r15
  unsigned int v13; // r12d
  __int64 cchCount2; // rdi
  WCHAR *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  StructuredQuery1 *v18; // rax
  wchar_t **v19; // r9
  WCHAR *v20; // rdi
  int v22; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned int v24; // [rsp+38h] [rbp-28h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  PCNZWCH lpString1; // [rsp+48h] [rbp-18h] BYREF
  PCNZWCH lpString2[2]; // [rsp+50h] [rbp-10h] BYREF

  v7 = 0;
  lpString2[0] = 0;
  Instance = StructuredQuery1::RestrictionInfo::CreateInstance(a4, (int)a2, a3, (void **)lpString2);
  if ( Instance >= 0 )
  {
    v10 = lpString2[0];
    v25 = 0;
    Instance = (**(__int64 (__fastcall ***)(PCNZWCH, GUID *, __int64 *))lpString2[0])(
                 lpString2[0],
                 &GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0,
                 &v25);
    if ( Instance >= 0 )
    {
      lpString2[0] = 0;
      Instance = StructuredQuery1::CSchemaFromPropertySystem::LocalizeString(
                   (StructuredQuery1::CSchemaFromPropertySystem *)this,
                   (__int64)a2,
                   v11,
                   (void **)lpString2);
      if ( Instance >= 0 )
      {
        v12 = lpString2[0];
        v23 = 0;
        v22 = 0;
        Instance = (*(__int64 (__fastcall **)(PCNZWCH, unsigned int *))(*(_QWORD *)lpString2[0] + 24LL))(
                     lpString2[0],
                     &v23);
        v13 = 0;
        if ( Instance >= 0 )
        {
          while ( v13 < v23 )
          {
            lpString2[0] = 0;
            Instance = (*(__int64 (__fastcall **)(PCNZWCH, _QWORD, PCNZWCH *))(*(_QWORD *)v12 + 32LL))(
                         v12,
                         v13,
                         lpString2);
            if ( Instance >= 0 )
            {
              cchCount2 = -1;
              do
                ++cchCount2;
              while ( lpString2[0][cchCount2] );
              v24 = 0;
              Instance = (*(__int64 (__fastcall **)(struct IMnemonics *, unsigned int *))(*(_QWORD *)a5 + 24LL))(
                           a5,
                           &v24);
              if ( Instance >= 0 )
              {
                while ( v7 < v24 )
                {
                  lpString1 = 0;
                  Instance = (*(__int64 (__fastcall **)(struct IMnemonics *, _QWORD, PCNZWCH *))(*(_QWORD *)a5 + 32LL))(
                               a5,
                               v7,
                               &lpString1);
                  if ( Instance >= 0 )
                  {
                    v15 = (WCHAR *)lpString1;
                    v16 = -1;
                    do
                      ++v16;
                    while ( lpString1[v16] );
                    if ( (int)v16 >= (int)cchCount2 )
                    {
                      if ( CompareStringW(this[3], 0x20001u, lpString1, cchCount2, lpString2[0], cchCount2) == 2 )
                        Instance = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                     this,
                                     &lpString1[(int)cchCount2],
                                     &v22,
                                     1,
                                     v25);
                      v15 = (WCHAR *)lpString1;
                    }
                    CoTaskMemFree(v15);
                  }
                  ++v7;
                  if ( Instance < 0 )
                    goto LABEL_27;
                }
                if ( a6 )
                {
                  v17 = -1;
                  do
                    ++v17;
                  while ( a6[v17] );
                  if ( (int)v17 >= (int)cchCount2
                    && CompareStringW(this[3], 0x20001u, a6, cchCount2, lpString2[0], cchCount2) == 2 )
                  {
                    Instance = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                 this,
                                 &a6[(int)cchCount2],
                                 &v22,
                                 1,
                                 v25);
                  }
                }
              }
LABEL_27:
              CoTaskMemFree((LPVOID)lpString2[0]);
              v7 = 0;
            }
            ++v13;
            if ( Instance < 0 )
              goto LABEL_36;
          }
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25) )
          {
            lpString2[0] = 0;
            v18 = (StructuredQuery1 *)(*(__int64 (__fastcall **)(const struct _GUID *))(*(_QWORD *)&a3->Data1 + 32LL))(a3);
            Instance = StructuredQuery1::MakeNamedEntityCanonicalName(v18, a4, (const wchar_t *)lpString2, v19);
            if ( Instance >= 0 )
            {
              v20 = (WCHAR *)lpString2[0];
              Instance = (*(__int64 (__fastcall **)(PCNZWCH, PCNZWCH))(*(_QWORD *)v10 + 40LL))(v10, lpString2[0]);
              if ( Instance >= 0 )
              {
                Instance = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(this, v20, &v22, 2, v25);
                if ( Instance >= 0 )
                  Instance = (*(__int64 (__fastcall **)(const struct _GUID *, PCNZWCH))(*(_QWORD *)&a3->Data1 + 112LL))(
                               a3,
                               v10);
              }
              CoTaskMemFree(v20);
            }
          }
        }
LABEL_36:
        (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)v12 + 16LL))(v12);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    (*(void (__fastcall **)(PCNZWCH))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180051028  mov     [rsp-38h+arg_0], rbx
0x18005102d  mov     [rsp-38h+arg_18], r9
0x180051032  mov     [rsp-38h+arg_10], r8
0x180051037  push    rbp
0x180051038  push    rsi
0x180051039  push    rdi
0x18005103a  push    r12
0x18005103c  push    r13
0x18005103e  push    r14
0x180051040  push    r15
0x180051042  mov     rbp, rsp
0x180051045  sub     rsp, 60h
0x180051049  mov     rax, r9
0x18005104c  mov     r13, rcx
0x18005104f  xor     r14d, r14d
0x180051052  lea     r9, [rbp+var_10]; void **
0x180051056  mov     rcx, rax; wchar_t *
0x180051059  mov     [rbp+var_10], r14
0x18005105d  mov     rdi, rdx
0x180051060  call    ?CreateInstance@RestrictionInfo@StructuredQuery1@@SAJPEB_WHAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::RestrictionInfo::CreateInstance(wchar_t const *,int,_GUID const &,void * *)
0x180051065  mov     ebx, eax
0x180051067  test    eax, eax
0x180051069  js      loc_180051345
0x18005106f  mov     rsi, [rbp+var_10]
0x180051073  lea     r8, [rbp+var_20]
0x180051077  mov     [rbp+var_20], r14
0x18005107b  lea     rdx, _GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0
0x180051082  mov     rcx, rsi
0x180051085  mov     rax, [rsi]
0x180051088  mov     rax, [rax]
0x18005108b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051090  mov     ebx, eax
0x180051092  test    eax, eax
0x180051094  js      loc_180051336
0x18005109a  lea     r9, [rbp+var_10]; void **
0x18005109e  mov     [rbp+var_10], r14
0x1800510a2  mov     rdx, rdi; wchar_t *
0x1800510a5  mov     rcx, r13; this
0x1800510a8  call    ?LocalizeString@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::CSchemaFromPropertySystem::LocalizeString(wchar_t const *,_GUID const &,void * *)
0x1800510ad  mov     ebx, eax
0x1800510af  test    eax, eax
0x1800510b1  js      loc_180051326
0x1800510b7  mov     r15, [rbp+var_10]
0x1800510bb  lea     rdx, [rbp+var_2C]
0x1800510bf  mov     [rbp+var_2C], r14d
0x1800510c3  mov     rcx, r15
0x1800510c6  mov     [rbp+var_30], r14d
0x1800510ca  mov     rax, [r15]
0x1800510cd  mov     rax, [rax+18h]
0x1800510d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510d6  mov     ebx, eax
0x1800510d8  mov     r12d, r14d
0x1800510db  test    eax, eax
0x1800510dd  js      loc_180051317
0x1800510e3  cmp     r12d, [rbp+var_2C]
0x1800510e7  jnb     loc_180051274
0x1800510ed  mov     [rbp+var_10], r14
0x1800510f1  lea     r8, [rbp+var_10]
0x1800510f5  mov     rax, [r15]
0x1800510f8  mov     edx, r12d
0x1800510fb  mov     rcx, r15
0x1800510fe  mov     rax, [rax+20h]
0x180051102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051107  mov     ebx, eax
0x180051109  test    eax, eax
0x18005110b  js      loc_180051264
0x180051111  mov     rax, [rbp+var_10]
0x180051115  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180051119  inc     rdi
0x18005111c  cmp     [rax+rdi*2], r14w
0x180051121  jnz     short loc_180051119
0x180051123  mov     rcx, [rbp+arg_20]
0x180051127  lea     rdx, [rbp+var_28]
0x18005112b  mov     [rbp+var_28], r14d
0x18005112f  mov     rax, [rcx]
0x180051132  mov     rax, [rax+18h]
0x180051136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005113b  xor     edx, edx
0x18005113d  mov     ebx, eax
0x18005113f  test    eax, eax
0x180051141  js      loc_180051257
0x180051147  cmp     r14d, [rbp+var_28]
0x18005114b  jnb     loc_1800511F1
0x180051151  mov     rcx, [rbp+arg_20]
0x180051155  lea     r8, [rbp+lpString1]
0x180051159  mov     [rbp+lpString1], rdx
0x18005115d  mov     edx, r14d
0x180051160  mov     rax, [rcx]
0x180051163  mov     rax, [rax+20h]
0x180051167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005116c  xor     edx, edx
0x18005116e  mov     ebx, eax
0x180051170  test    eax, eax
0x180051172  js      short loc_1800511E4
0x180051174  mov     rcx, [rbp+lpString1]
0x180051178  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005117c  inc     rax
0x18005117f  cmp     [rcx+rax*2], dx
0x180051183  jnz     short loc_18005117C
0x180051185  cmp     eax, edi
0x180051187  jl      short loc_1800511DC
0x180051189  mov     rax, [rbp+var_10]
0x18005118d  mov     r8, rcx; lpString1
0x180051190  mov     ecx, [r13+0Ch]; Locale
0x180051194  mov     r9d, edi; cchCount1
0x180051197  mov     [rsp+60h+cchCount2], edi; cchCount2
0x18005119b  mov     edx, 20001h; dwCmpFlags
0x1800511a0  mov     [rsp+60h+lpString2], rax; lpString2
0x1800511a5  call    cs:__imp_CompareStringW
0x1800511ab  cmp     eax, 2
0x1800511ae  jnz     short loc_1800511D8
0x1800511b0  mov     rax, [rbp+lpString1]
0x1800511b4  lea     r8, [rbp+var_30]
0x1800511b8  movsxd  rcx, edi
0x1800511bb  mov     r9d, 1
0x1800511c1  lea     rdx, [rax+rcx*2]
0x1800511c5  mov     rax, [rbp+var_20]
0x1800511c9  mov     rcx, r13
0x1800511cc  mov     [rsp+60h+lpString2], rax
0x1800511d1  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x1800511d6  mov     ebx, eax
0x1800511d8  mov     rcx, [rbp+lpString1]; pv
0x1800511dc  call    cs:__imp_CoTaskMemFree
0x1800511e2  xor     edx, edx
0x1800511e4  inc     r14d
0x1800511e7  test    ebx, ebx
0x1800511e9  jns     loc_180051147
0x1800511ef  jmp     short loc_180051257
0x1800511f1  mov     r14, [rbp+arg_28]
0x1800511f5  test    r14, r14
0x1800511f8  jz      short loc_180051257
0x1800511fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800511fe  inc     rax
0x180051201  cmp     [r14+rax*2], dx
0x180051206  jnz     short loc_1800511FE
0x180051208  cmp     eax, edi
0x18005120a  jl      short loc_180051257
0x18005120c  mov     rax, [rbp+var_10]
0x180051210  mov     r9d, edi; cchCount1
0x180051213  mov     ecx, [r13+0Ch]; Locale
0x180051217  mov     r8, r14; lpString1
0x18005121a  mov     [rsp+60h+cchCount2], edi; cchCount2
0x18005121e  mov     edx, 20001h; dwCmpFlags
0x180051223  mov     [rsp+60h+lpString2], rax; lpString2
0x180051228  call    cs:__imp_CompareStringW
0x18005122e  cmp     eax, 2
0x180051231  jnz     short loc_180051257
0x180051233  movsxd  rax, edi
0x180051236  lea     r8, [rbp+var_30]
0x18005123a  mov     r9d, 1
0x180051240  mov     rcx, r13
0x180051243  lea     rdx, [r14+rax*2]
0x180051247  mov     rax, [rbp+var_20]
0x18005124b  mov     [rsp+60h+lpString2], rax
0x180051250  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x180051255  mov     ebx, eax
0x180051257  mov     rcx, [rbp+var_10]; pv
0x18005125b  call    cs:__imp_CoTaskMemFree
0x180051261  xor     r14d, r14d
0x180051264  inc     r12d
0x180051267  test    ebx, ebx
0x180051269  jns     loc_1800510E3
0x18005126f  jmp     loc_180051317
0x180051274  mov     rcx, [rbp+var_20]
0x180051278  mov     rax, [rcx]
0x18005127b  mov     rax, [rax+20h]
0x18005127f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051284  test    rax, rax
0x180051287  jz      loc_180051317
0x18005128d  mov     [rbp+var_10], r14
0x180051291  mov     r14, [rbp+arg_10]
0x180051295  mov     rcx, r14
0x180051298  mov     rax, [r14]
0x18005129b  mov     rax, [rax+20h]
0x18005129f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512a4  mov     rdx, [rbp+arg_18]; wchar_t *
0x1800512a8  lea     r8, [rbp+var_10]; wchar_t *
0x1800512ac  mov     rcx, rax; this
0x1800512af  call    ?MakeNamedEntityCanonicalName@StructuredQuery1@@YAJPEB_W0PEAPEA_W@Z; StructuredQuery1::MakeNamedEntityCanonicalName(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800512b4  mov     ebx, eax
0x1800512b6  test    eax, eax
0x1800512b8  js      short loc_180051317
0x1800512ba  mov     rax, [rsi]
0x1800512bd  mov     rcx, rsi
0x1800512c0  mov     rdi, [rbp+var_10]
0x1800512c4  mov     rdx, rdi
0x1800512c7  mov     rax, [rax+28h]
0x1800512cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512d0  mov     ebx, eax
0x1800512d2  test    eax, eax
0x1800512d4  js      short loc_18005130E
0x1800512d6  mov     rax, [rbp+var_20]
0x1800512da  lea     r8, [rbp+var_30]
0x1800512de  mov     r9d, 2
0x1800512e4  mov     [rsp+60h+lpString2], rax
0x1800512e9  mov     rdx, rdi
0x1800512ec  mov     rcx, r13
0x1800512ef  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x1800512f4  mov     ebx, eax
0x1800512f6  test    eax, eax
0x1800512f8  js      short loc_18005130E
0x1800512fa  mov     rax, [r14]
0x1800512fd  mov     rdx, rsi
0x180051300  mov     rcx, r14
0x180051303  mov     rax, [rax+70h]
0x180051307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005130c  mov     ebx, eax
0x18005130e  mov     rcx, rdi; pv
0x180051311  call    cs:__imp_CoTaskMemFree
0x180051317  mov     rax, [r15]
0x18005131a  mov     rcx, r15
0x18005131d  mov     rax, [rax+10h]
0x180051321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051326  mov     rcx, [rbp+var_20]
0x18005132a  mov     rax, [rcx]
0x18005132d  mov     rax, [rax+10h]
0x180051331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051336  mov     rax, [rsi]
0x180051339  mov     rcx, rsi
0x18005133c  mov     rax, [rax+10h]
0x180051340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051345  mov     eax, ebx
0x180051347  mov     rbx, [rsp+60h+arg_0]
0x18005134f  add     rsp, 60h
0x180051353  pop     r15
0x180051355  pop     r14
0x180051357  pop     r13
0x180051359  pop     r12
0x18005135b  pop     rdi
0x18005135c  pop     rsi
0x18005135d  pop     rbp
0x18005135e  retn
```
