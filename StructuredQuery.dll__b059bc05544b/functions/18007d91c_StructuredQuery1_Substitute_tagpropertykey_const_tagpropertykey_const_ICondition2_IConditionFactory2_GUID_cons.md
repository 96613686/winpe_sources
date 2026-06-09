# StructuredQuery1::Substitute(_tagpropertykey const &,_tagpropertykey const &,ICondition2 *,IConditionFactory2 *,_GUID const &,void * *)

- ea: `0x18007d91c`
- end: `0x18007dd80`
- name: `?Substitute@StructuredQuery1@@YAJAEBU_tagpropertykey@@0PEAUICondition2@@PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z`
- size: `1124`
- prototype: `__int64 __fastcall(StructuredQuery1 *__hidden this, const struct _tagpropertykey *, const struct _tagpropertykey *, struct ICondition2 *, struct IConditionFactory2 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007d790`
- `0x18007d91c`

## callees

- `0x18000bd20`
- `0x18003f7a0`
- `0x18004146c`
- `0x18005daf0`
- `0x18007d91c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007db1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007db25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007db1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007db25`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007db2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007db2f`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Substitute(
        StructuredQuery1 *this,
        const struct _tagpropertykey *a2,
        const struct _tagpropertykey *a3,
        struct ICondition2 *a4,
        struct IConditionFactory2 *a5,
        struct _GUID *a6)
{
  __int64 v6; // rax
  struct _GUID *v8; // r14
  __int64 (__fastcall *v10)(const struct _tagpropertykey *, unsigned int *); // rax
  int Instance; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  LPVOID v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r14
  unsigned int v23; // edi
  void **v25; // [rsp+30h] [rbp-B9h]
  struct _GUID v26; // [rsp+70h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-69h] BYREF
  void *v28; // [rsp+88h] [rbp-61h] BYREF
  unsigned int v29; // [rsp+90h] [rbp-59h] BYREF
  __int64 v30; // [rsp+98h] [rbp-51h] BYREF
  const struct _GUID *v31; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-41h] BYREF
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-29h]
  __int128 v35; // [rsp+C8h] [rbp-21h] BYREF
  int v36; // [rsp+D8h] [rbp-11h]

  v6 = *(_QWORD *)&a3->fmtid.Data1;
  v8 = a6;
  v31 = a6;
  v10 = *(__int64 (__fastcall **)(const struct _tagpropertykey *, unsigned int *))(v6 + 64);
  v30 = 0;
  v29 = 0;
  Instance = v10(a3, &v29);
  if ( Instance < 0 )
    goto LABEL_36;
  if ( v29 < 2 )
  {
    v21 = *(_QWORD *)&a3->fmtid.Data1;
    v28 = 0;
    Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, GUID *, void **))(v21 + 72))(
                 a3,
                 &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                 &v28);
    if ( Instance < 0 )
      goto LABEL_36;
    *(_DWORD *)v26.Data4 = 0;
    Instance = (*(__int64 (__fastcall **)(void *, unsigned __int8 *))(*(_QWORD *)v28 + 24LL))(v28, v26.Data4);
    if ( Instance >= 0 )
    {
      *(_QWORD *)&v26.Data1 = 0;
      Instance = FixedCapacityObjectCollection::CreateInstance(
                   *(unsigned int *)v26.Data4,
                   &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                   (void **)&v26);
      if ( Instance >= 0 )
      {
        v22 = *(_QWORD *)&v26.Data1;
        v23 = 0;
        while ( v23 < *(_DWORD *)v26.Data4 )
        {
          pv = 0;
          Instance = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v28 + 32LL))(
                       v28,
                       v23,
                       &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                       &pv);
          if ( Instance >= 0 )
          {
            *(_QWORD *)&v26.Data1 = 0;
            Instance = StructuredQuery1::Substitute(
                         this,
                         a2,
                         (const struct _tagpropertykey *)pv,
                         a4,
                         (struct IConditionFactory2 *)&GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                         &v26,
                         v25);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 40LL))(
                           v22,
                           *(_QWORD *)&v26.Data1);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v26.Data1 + 16LL))(*(_QWORD *)&v26.Data1);
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
          ++v23;
          if ( Instance < 0 )
            goto LABEL_33;
        }
        Instance = ((__int64 (__fastcall *)(struct ICondition2 *, _QWORD, __int64, __int64, GUID *, __int64 *))a4->lpVtbl->GetSubConditions)(
                     a4,
                     v29,
                     v22,
                     1,
                     &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                     &v30);
LABEL_33:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v8 = (struct _GUID *)v31;
      }
    }
    v20 = v28;
    goto LABEL_35;
  }
  if ( v29 == 2 )
  {
    v19 = *(_QWORD *)&a3->fmtid.Data1;
    pv = 0;
    Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, GUID *, LPVOID *))(v19 + 72))(
                 a3,
                 &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &pv);
    if ( Instance < 0 )
      goto LABEL_36;
    *(_QWORD *)&v26.Data1 = 0;
    Instance = StructuredQuery1::Substitute(
                 this,
                 a2,
                 (const struct _tagpropertykey *)pv,
                 a4,
                 (struct IConditionFactory2 *)&GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &v26,
                 v25);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct ICondition2 *, _QWORD, __int64, GUID *, __int64 *))a4->lpVtbl->GetConditionType)(
                   a4,
                   *(_QWORD *)&v26.Data1,
                   1,
                   &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                   &v30);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v26.Data1 + 16LL))(*(_QWORD *)&v26.Data1);
    }
    v20 = pv;
LABEL_35:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_36;
  }
  if ( v29 == 3 )
  {
    v36 = 0;
    v14 = *(_QWORD *)&a3->fmtid.Data1;
    v35 = 0;
    if ( (*(int (__fastcall **)(const struct _tagpropertykey *, __int128 *, _QWORD, _QWORD))(v14 + 128))(a3, &v35, 0, 0) >= 0
      && operator==((__int64)&v35, (__int64)this) )
    {
      *(_DWORD *)v26.Data4 = 0;
      v34 = 0;
      v15 = *(_QWORD *)&a3->fmtid.Data1;
      *(_OWORD *)pvar = 0;
      Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, _QWORD, unsigned __int8 *, PROPVARIANT *))(v15 + 128))(
                   a3,
                   0,
                   v26.Data4,
                   pvar);
      if ( Instance >= 0 )
      {
        v16 = *(_QWORD *)&a3->fmtid.Data1;
        *(_QWORD *)&v26.Data1 = 0;
        Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, struct _GUID *))(v16 + 88))(a3, &v26);
        if ( Instance >= 0 )
        {
          v17 = *(_QWORD *)&a3->fmtid.Data1;
          pv = 0;
          Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, LPVOID *))(v17 + 120))(a3, &pv);
          if ( Instance >= 0 )
          {
            v18 = *(_QWORD *)&a3->fmtid.Data1;
            v28 = 0;
            v32 = 0;
            v31 = 0;
            Instance = (*(__int64 (__fastcall **)(const struct _tagpropertykey *, void **, __int64 *, const struct _GUID **))(v18 + 104))(
                         a3,
                         &v28,
                         &v32,
                         &v31);
            if ( Instance >= 0 )
            {
              Instance = ((__int64 (__fastcall *)(struct ICondition2 *, const struct _tagpropertykey *, _QWORD, PROPVARIANT *, _QWORD, LPVOID, void *, __int64, const struct _GUID *, int, GUID *, __int64 *))a4->lpVtbl->Clone)(
                           a4,
                           a2,
                           *(unsigned int *)v26.Data4,
                           pvar,
                           *(_QWORD *)&v26.Data1,
                           pv,
                           v28,
                           v32,
                           v31,
                           1,
                           &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                           &v30);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v28);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v32);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v31);
            }
            CoTaskMemFree(pv);
          }
          CoTaskMemFree(*(LPVOID *)&v26.Data1);
        }
        PropVariantClear(pvar);
      }
    }
    else
    {
      Instance = (**(__int64 (__fastcall ***)(const struct _tagpropertykey *, GUID *, __int64 *))&a3->fmtid.Data1)(
                   a3,
                   &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                   &v30);
    }
  }
  else
  {
    Instance = -2147418113;
  }
LABEL_36:
  *(_QWORD *)&v8->Data1 = v30;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18007d91c  push    rbp
0x18007d91e  push    rbx
0x18007d91f  push    rsi
0x18007d920  push    rdi
0x18007d921  push    r12
0x18007d923  push    r13
0x18007d925  push    r14
0x18007d927  push    r15
0x18007d929  lea     rbp, [rsp-0Fh]
0x18007d92e  sub     rsp, 0F8h
0x18007d935  mov     rax, cs:__security_cookie
0x18007d93c  xor     rax, rsp
0x18007d93f  mov     [rbp+47h+var_50], rax
0x18007d943  mov     rax, [r8]
0x18007d946  mov     r13, rdx
0x18007d949  mov     r14, [rbp+47h+arg_28]
0x18007d94d  lea     rdx, [rbp+47h+var_A0]
0x18007d951  mov     r12, rcx
0x18007d954  mov     [rbp+47h+var_90], r14
0x18007d958  xor     esi, esi
0x18007d95a  mov     rcx, r8
0x18007d95d  mov     rax, [rax+40h]
0x18007d961  mov     r15, r9
0x18007d964  mov     rdi, r8
0x18007d967  mov     [rbp+47h+var_98], rsi
0x18007d96b  mov     [rbp+47h+var_A0], esi
0x18007d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d973  mov     ebx, eax
0x18007d975  test    eax, eax
0x18007d977  js      loc_18007DD57
0x18007d97d  mov     ecx, [rbp+47h+var_A0]
0x18007d980  test    ecx, ecx
0x18007d982  jz      loc_18007DBF3
0x18007d988  sub     ecx, 1
0x18007d98b  jz      loc_18007DBF3
0x18007d991  sub     ecx, 1
0x18007d994  jz      loc_18007DB5A
0x18007d99a  cmp     ecx, 1
0x18007d99d  jz      short loc_18007D9A9
0x18007d99f  mov     ebx, 8000FFFFh
0x18007d9a4  jmp     loc_18007DD57
0x18007d9a9  xor     eax, eax
0x18007d9ab  lea     rdx, [rbp+47h+var_68]
0x18007d9af  mov     [rbp+47h+var_58], eax
0x18007d9b2  xorps   xmm0, xmm0
0x18007d9b5  mov     rax, [rdi]
0x18007d9b8  xor     r9d, r9d
0x18007d9bb  xor     r8d, r8d
0x18007d9be  mov     rcx, rdi
0x18007d9c1  movups  [rbp+47h+var_68], xmm0
0x18007d9c5  mov     rax, [rax+80h]
0x18007d9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9d1  test    eax, eax
0x18007d9d3  js      loc_18007DB3A
0x18007d9d9  mov     rdx, r12
0x18007d9dc  lea     rcx, [rbp+47h+var_68]
0x18007d9e0  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18007d9e5  test    eax, eax
0x18007d9e7  jz      loc_18007DB3A
0x18007d9ed  xor     eax, eax
0x18007d9ef  mov     dword ptr [rbp+47h+var_C0.Data4], esi
0x18007d9f2  mov     [rbp+47h+var_70], rax
0x18007d9f6  lea     r9, [rbp+47h+pvar]
0x18007d9fa  mov     rax, [rdi]
0x18007d9fd  lea     r8, [rbp+47h+var_C0.Data4]
0x18007da01  xorps   xmm0, xmm0
0x18007da04  xor     edx, edx
0x18007da06  mov     rcx, rdi
0x18007da09  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18007da0d  mov     rax, [rax+80h]
0x18007da14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da19  mov     ebx, eax
0x18007da1b  test    eax, eax
0x18007da1d  js      loc_18007DD57
0x18007da23  mov     rax, [rdi]
0x18007da26  lea     rdx, [rbp+47h+var_C0]
0x18007da2a  mov     rcx, rdi
0x18007da2d  mov     qword ptr [rbp+47h+var_C0.Data1], rsi
0x18007da31  mov     rax, [rax+58h]
0x18007da35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da3a  mov     ebx, eax
0x18007da3c  test    eax, eax
0x18007da3e  js      loc_18007DB2B
0x18007da44  mov     rax, [rdi]
0x18007da47  lea     rdx, [rbp+47h+pv]
0x18007da4b  mov     rcx, rdi
0x18007da4e  mov     [rbp+47h+pv], rsi
0x18007da52  mov     rax, [rax+78h]
0x18007da56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da5b  mov     ebx, eax
0x18007da5d  test    eax, eax
0x18007da5f  js      loc_18007DB21
0x18007da65  mov     rax, [rdi]
0x18007da68  lea     r9, [rbp+47h+var_90]
0x18007da6c  lea     r8, [rbp+47h+var_88]
0x18007da70  mov     [rbp+47h+var_A8], rsi
0x18007da74  lea     rdx, [rbp+47h+var_A8]
0x18007da78  mov     [rbp+47h+var_88], rsi
0x18007da7c  mov     rcx, rdi
0x18007da7f  mov     [rbp+47h+var_90], rsi
0x18007da83  mov     rax, [rax+68h]
0x18007da87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da8c  mov     ebx, eax
0x18007da8e  test    eax, eax
0x18007da90  js      loc_18007DB17
0x18007da96  mov     r8, [rbp+47h+var_90]
0x18007da9a  lea     rcx, [rbp+47h+var_98]
0x18007da9e  mov     rax, [r15]
0x18007daa1  lea     rsi, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18007daa8  mov     [rsp+130h+var_D8], rcx
0x18007daad  lea     r9, [rbp+47h+pvar]
0x18007dab1  mov     [rsp+130h+var_E0], rsi
0x18007dab6  mov     rdx, r13
0x18007dab9  mov     [rsp+130h+var_E8], 1
0x18007dac1  mov     rcx, r15
0x18007dac4  mov     rax, [rax+70h]
0x18007dac8  mov     [rsp+130h+var_F0], r8
0x18007dacd  mov     r8, [rbp+47h+var_88]
0x18007dad1  mov     [rsp+130h+var_F8], r8
0x18007dad6  mov     r8, [rbp+47h+var_A8]
0x18007dada  mov     [rsp+130h+var_100], r8
0x18007dadf  mov     r8, [rbp+47h+pv]
0x18007dae3  mov     [rsp+130h+var_108], r8
0x18007dae8  mov     r8, qword ptr [rbp+47h+var_C0.Data1]
0x18007daec  mov     [rsp+130h+var_110], r8
0x18007daf1  mov     r8d, dword ptr [rbp+47h+var_C0.Data4]
0x18007daf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dafa  lea     rcx, [rbp+47h+var_A8]
0x18007dafe  mov     ebx, eax
0x18007db00  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18007db05  lea     rcx, [rbp+47h+var_88]
0x18007db09  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18007db0e  lea     rcx, [rbp+47h+var_90]
0x18007db12  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18007db17  mov     rcx, [rbp+47h+pv]; pv
0x18007db1b  call    cs:__imp_CoTaskMemFree
0x18007db21  mov     rcx, qword ptr [rbp+47h+var_C0.Data1]; pv
0x18007db25  call    cs:__imp_CoTaskMemFree
0x18007db2b  lea     rcx, [rbp+47h+pvar]; pvar
0x18007db2f  call    cs:__imp_PropVariantClear
0x18007db35  jmp     loc_18007DD57
0x18007db3a  mov     rax, [rdi]
0x18007db3d  lea     r8, [rbp+47h+var_98]
0x18007db41  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18007db48  mov     rcx, rdi
0x18007db4b  mov     rax, [rax]
0x18007db4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db53  mov     ebx, eax
0x18007db55  jmp     loc_18007DD57
0x18007db5a  mov     rax, [rdi]
0x18007db5d  lea     r8, [rbp+47h+pv]
0x18007db61  mov     [rbp+47h+pv], rsi
0x18007db65  mov     rcx, rdi
0x18007db68  lea     rsi, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18007db6f  mov     rdx, rsi
0x18007db72  mov     rax, [rax+48h]
0x18007db76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db7b  mov     ebx, eax
0x18007db7d  test    eax, eax
0x18007db7f  js      loc_18007DD57
0x18007db85  mov     r8, [rbp+47h+pv]; struct _tagpropertykey *
0x18007db89  lea     rax, [rbp+47h+var_C0]
0x18007db8d  mov     [rsp+130h+var_108], rax; struct _GUID *
0x18007db92  mov     r9, r15; struct ICondition2 *
0x18007db95  mov     rdx, r13; struct _tagpropertykey *
0x18007db98  mov     [rsp+130h+var_110], rsi; struct IConditionFactory2 *
0x18007db9d  mov     rcx, r12; this
0x18007dba0  mov     qword ptr [rbp+47h+var_C0.Data1], 0
0x18007dba8  call    ?Substitute@StructuredQuery1@@YAJAEBU_tagpropertykey@@0PEAUICondition2@@PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Substitute(_tagpropertykey const &,_tagpropertykey const &,ICondition2 *,IConditionFactory2 *,_GUID const &,void * *)
0x18007dbad  mov     ebx, eax
0x18007dbaf  test    eax, eax
0x18007dbb1  js      short loc_18007DBEA
0x18007dbb3  mov     rax, [r15]
0x18007dbb6  lea     rcx, [rbp+47h+var_98]
0x18007dbba  mov     rdx, qword ptr [rbp+47h+var_C0.Data1]
0x18007dbbe  mov     r9, rsi
0x18007dbc1  mov     [rsp+130h+var_110], rcx
0x18007dbc6  mov     r8d, 1
0x18007dbcc  mov     rcx, r15
0x18007dbcf  mov     rax, [rax+40h]
0x18007dbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbd8  mov     rcx, qword ptr [rbp+47h+var_C0.Data1]
0x18007dbdc  mov     ebx, eax
0x18007dbde  mov     rax, [rcx]
0x18007dbe1  mov     rax, [rax+10h]
0x18007dbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dbea  mov     rcx, [rbp+47h+pv]
0x18007dbee  jmp     loc_18007DD4B
0x18007dbf3  mov     rax, [rdi]
0x18007dbf6  lea     r8, [rbp+47h+var_A8]
0x18007dbfa  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18007dc01  mov     [rbp+47h+var_A8], rsi
0x18007dc05  mov     rcx, rdi
0x18007dc08  mov     rax, [rax+48h]
0x18007dc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc11  mov     ebx, eax
0x18007dc13  test    eax, eax
0x18007dc15  js      loc_18007DD57
0x18007dc1b  mov     rcx, [rbp+47h+var_A8]
0x18007dc1f  lea     rdx, [rbp+47h+var_C0.Data4]
0x18007dc23  mov     dword ptr [rbp+47h+var_C0.Data4], esi
0x18007dc26  mov     rax, [rcx]
0x18007dc29  mov     rax, [rax+18h]
0x18007dc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc32  mov     ebx, eax
0x18007dc34  test    eax, eax
0x18007dc36  js      loc_18007DD47
0x18007dc3c  mov     ecx, dword ptr [rbp+47h+var_C0.Data4]; unsigned int
0x18007dc3f  lea     r8, [rbp+47h+var_C0]; void **
0x18007dc43  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x18007dc4a  mov     qword ptr [rbp+47h+var_C0.Data1], rsi
0x18007dc4e  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x18007dc53  mov     ebx, eax
0x18007dc55  test    eax, eax
0x18007dc57  js      loc_18007DD47
0x18007dc5d  mov     r14, qword ptr [rbp+47h+var_C0.Data1]
0x18007dc61  mov     edi, esi
0x18007dc63  lea     rsi, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18007dc6a  cmp     edi, dword ptr [rbp+47h+var_C0.Data4]
0x18007dc6d  jnb     loc_18007DD09
0x18007dc73  mov     rcx, [rbp+47h+var_A8]
0x18007dc77  lea     r9, [rbp+47h+pv]
0x18007dc7b  mov     [rbp+47h+pv], 0
0x18007dc83  mov     r8, rsi
0x18007dc86  mov     edx, edi
0x18007dc88  mov     rax, [rcx]
0x18007dc8b  mov     rax, [rax+20h]
0x18007dc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc94  mov     ebx, eax
0x18007dc96  test    eax, eax
0x18007dc98  js      short loc_18007DCFD
0x18007dc9a  mov     r8, [rbp+47h+pv]; struct _tagpropertykey *
0x18007dc9e  lea     rax, [rbp+47h+var_C0]
0x18007dca2  mov     [rsp+130h+var_108], rax; struct _GUID *
0x18007dca7  mov     r9, r15; struct ICondition2 *
0x18007dcaa  mov     rdx, r13; struct _tagpropertykey *
0x18007dcad  mov     [rsp+130h+var_110], rsi; struct IConditionFactory2 *
0x18007dcb2  mov     rcx, r12; this
0x18007dcb5  mov     qword ptr [rbp+47h+var_C0.Data1], 0
0x18007dcbd  call    ?Substitute@StructuredQuery1@@YAJAEBU_tagpropertykey@@0PEAUICondition2@@PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Substitute(_tagpropertykey const &,_tagpropertykey const &,ICondition2 *,IConditionFactory2 *,_GUID const &,void * *)
0x18007dcc2  mov     ebx, eax
0x18007dcc4  test    eax, eax
0x18007dcc6  js      short loc_18007DCED
0x18007dcc8  mov     rax, [r14]
0x18007dccb  mov     rcx, r14
0x18007dcce  mov     rdx, qword ptr [rbp+47h+var_C0.Data1]
0x18007dcd2  mov     rax, [rax+28h]
0x18007dcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcdb  mov     rcx, qword ptr [rbp+47h+var_C0.Data1]
0x18007dcdf  mov     ebx, eax
0x18007dce1  mov     rax, [rcx]
0x18007dce4  mov     rax, [rax+10h]
0x18007dce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dced  mov     rcx, [rbp+47h+pv]
0x18007dcf1  mov     rax, [rcx]
0x18007dcf4  mov     rax, [rax+10h]
0x18007dcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcfd  inc     edi
0x18007dcff  test    ebx, ebx
0x18007dd01  jns     loc_18007DC6A
0x18007dd07  jmp     short loc_18007DD34
0x18007dd09  mov     rax, [r15]
0x18007dd0c  lea     rcx, [rbp+47h+var_98]
0x18007dd10  mov     edx, [rbp+47h+var_A0]
0x18007dd13  mov     r9d, 1
0x18007dd19  mov     [rsp+130h+var_108], rcx
0x18007dd1e  mov     r8, r14
0x18007dd21  mov     rcx, r15
0x18007dd24  mov     [rsp+130h+var_110], rsi
0x18007dd29  mov     rax, [rax+48h]
0x18007dd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd32  mov     ebx, eax
0x18007dd34  mov     rax, [r14]
0x18007dd37  mov     rcx, r14
0x18007dd3a  mov     rax, [rax+10h]
0x18007dd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd43  mov     r14, [rbp+47h+var_90]
0x18007dd47  mov     rcx, [rbp+47h+var_A8]
0x18007dd4b  mov     rax, [rcx]
0x18007dd4e  mov     rax, [rax+10h]
0x18007dd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dd57  mov     rax, [rbp+47h+var_98]
0x18007dd5b  mov     [r14], rax
0x18007dd5e  mov     eax, ebx
0x18007dd60  mov     rcx, [rbp+47h+var_50]
0x18007dd64  xor     rcx, rsp; StackCookie
0x18007dd67  call    __security_check_cookie
0x18007dd6c  add     rsp, 0F8h
0x18007dd73  pop     r15
0x18007dd75  pop     r14
0x18007dd77  pop     r13
0x18007dd79  pop     r12
0x18007dd7b  pop     rdi
0x18007dd7c  pop     rsi
0x18007dd7d  pop     rbx
0x18007dd7e  pop     rbp
0x18007dd7f  retn
```
