# StructuredQuery1::Solution::AddStandardSemanticTypes(ICondition2 *,_GUID const &,void * *)

- ea: `0x18006dc70`
- end: `0x18006e043`
- name: `?AddStandardSemanticTypes@Solution@StructuredQuery1@@AEAAJPEAUICondition2@@AEBU_GUID@@PEAPEAX@Z`
- size: `979`
- prototype: `__int64 __fastcall(StructuredQuery1::Solution *__hidden this, struct ICondition2 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f7cc`
- `0x18006dc70`

## callees

- `0x180009a40`
- `0x18000b180`
- `0x18000bd20`
- `0x18000c3a0`
- `0x18003f7a0`
- `0x18005daf0`
- `0x18006dc70`
- `0x18006f830`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006de45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006de59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006de45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006de59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006de4f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006de4f`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::AddStandardSemanticTypes(
        StructuredQuery1::Solution *this,
        struct ICondition2 *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct ICondition2Vtbl *lpVtbl; // rax
  int Instance; // ebx
  struct ICondition2Vtbl *v10; // rax
  struct ICondition2Vtbl *v11; // rax
  HRESULT (__stdcall *GetLeafConditionInfo)(ICondition2 *, PROPERTYKEY *, CONDITION_OPERATION *, PROPVARIANT *); // rax
  struct ICondition2Vtbl *v13; // rax
  struct ICondition2Vtbl *v14; // rax
  const struct tagPROPVARIANT *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdi
  void *v18; // rsi
  LPVOID v19; // r14
  const wchar_t *v20; // rax
  struct ICondition2Vtbl *v21; // rax
  LPVOID v22; // rcx
  struct ICondition2Vtbl *v23; // rax
  StructuredQuery1::Solution *v24; // rcx
  struct IObjectArray *v25; // rdi
  unsigned int v26; // esi
  struct IObjectArray *v28; // [rsp+70h] [rbp-59h] BYREF
  unsigned int v29; // [rsp+78h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-49h] BYREF
  void *v31; // [rsp+88h] [rbp-41h] BYREF
  enum tagCONDITION_TYPE v32; // [rsp+90h] [rbp-39h] BYREF
  __int64 v33; // [rsp+98h] [rbp-31h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-11h]
  __int128 v37; // [rsp+C0h] [rbp-9h] BYREF
  int v38; // [rsp+D0h] [rbp+7h]

  *a4 = 0;
  lpVtbl = a2->lpVtbl;
  v32 = CT_AND_CONDITION;
  Instance = ((__int64 (__fastcall *)(struct ICondition2 *, enum tagCONDITION_TYPE *))lpVtbl->GetConditionType)(
               a2,
               &v32);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  if ( (unsigned int)v32 < CT_NOT_CONDITION )
  {
    v23 = a2->lpVtbl;
    v31 = 0;
    Instance = ((__int64 (__fastcall *)(struct ICondition2 *, GUID *, void **))v23->GetSubConditions)(
                 a2,
                 &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                 &v31);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    v29 = 0;
    Instance = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v31 + 24LL))(v31, &v29);
    if ( Instance >= 0 )
    {
      v28 = 0;
      Instance = FixedCapacityObjectCollection::CreateInstance(
                   v29,
                   &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                   (void **)&v28);
      if ( Instance >= 0 )
      {
        v25 = v28;
        v26 = 0;
        while ( v26 < v29 )
        {
          pv = 0;
          Instance = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v31 + 32LL))(
                       v31,
                       v26,
                       &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                       &pv);
          if ( Instance >= 0 )
          {
            v28 = 0;
            Instance = StructuredQuery1::Solution::AddStandardSemanticTypes(
                         this,
                         (struct ICondition2 *)pv,
                         &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                         (void **)&v28);
            if ( Instance >= 0 )
            {
              Instance = ((__int64 (__fastcall *)(struct IObjectArray *, struct IObjectArray *))v25->lpVtbl[1].QueryInterface)(
                           v25,
                           v28);
              ((void (__fastcall *)(struct IObjectArray *))v28->lpVtbl->Release)(v28);
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          }
          ++v26;
          if ( Instance < 0 )
            goto LABEL_32;
        }
        Instance = StructuredQuery1::Solution::MakeCompound(v24, v32, v25, 1, 0, a3, a4);
LABEL_32:
        ((void (__fastcall *)(struct IObjectArray *))v25->lpVtbl->Release)(v25);
      }
    }
    v22 = v31;
    goto LABEL_34;
  }
  if ( v32 == CT_NOT_CONDITION )
  {
    v21 = a2->lpVtbl;
    pv = 0;
    Instance = ((__int64 (__fastcall *)(struct ICondition2 *, GUID *, LPVOID *))v21->GetSubConditions)(
                 a2,
                 &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &pv);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    v28 = 0;
    Instance = StructuredQuery1::Solution::AddStandardSemanticTypes(
                 this,
                 (struct ICondition2 *)pv,
                 &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                 (void **)&v28);
    if ( Instance >= 0 )
    {
      Instance = StructuredQuery1::Solution::MakeNegation(this, (struct ICondition *)v28, 1, a3, a4);
      ((void (__fastcall *)(struct IObjectArray *))v28->lpVtbl->Release)(v28);
    }
    v22 = pv;
LABEL_34:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
    return (unsigned int)Instance;
  }
  if ( v32 == CT_LEAF_CONDITION )
  {
    v10 = a2->lpVtbl;
    v28 = 0;
    Instance = ((__int64 (__fastcall *)(struct ICondition2 *, struct IObjectArray **))v10->GetValueType)(a2, &v28);
    if ( Instance >= 0 )
    {
      v11 = a2->lpVtbl;
      if ( v28 )
      {
        Instance = ((__int64 (__fastcall *)(struct ICondition2 *, const struct _GUID *, void **))v11->QueryInterface)(
                     a2,
                     a3,
                     a4);
      }
      else
      {
        GetLeafConditionInfo = v11->GetLeafConditionInfo;
        v29 = 0;
        v38 = 0;
        v36 = 0;
        v37 = 0;
        *(_OWORD *)pvar = 0;
        Instance = ((__int64 (__fastcall *)(struct ICondition2 *, __int128 *, unsigned int *, PROPVARIANT *))GetLeafConditionInfo)(
                     a2,
                     &v37,
                     &v29,
                     pvar);
        if ( Instance >= 0 )
        {
          v13 = a2->lpVtbl;
          pv = 0;
          Instance = ((__int64 (__fastcall *)(struct ICondition2 *, LPVOID *))v13->GetLocale)(a2, &pv);
          if ( Instance >= 0 )
          {
            v14 = a2->lpVtbl;
            v31 = 0;
            v33 = 0;
            v34 = 0;
            Instance = ((__int64 (__fastcall *)(struct ICondition2 *, void **, __int64 *, __int64 *))v14->GetInputTerms)(
                         a2,
                         &v31,
                         &v33,
                         &v34);
            if ( Instance >= 0 )
            {
              v16 = v34;
              v17 = v33;
              v18 = v31;
              v19 = pv;
              v20 = StructuredQuery1::_SemanticTypeFromPropVariantRec((StructuredQuery1 *)pvar, v15);
              Instance = StructuredQuery1::Solution::MakePredicate(
                           this,
                           &v37,
                           v29,
                           v20,
                           pvar,
                           v19,
                           0,
                           v18,
                           v17,
                           v16,
                           0,
                           0,
                           a3,
                           a4);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v31);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v33);
              IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v34);
            }
            CoTaskMemFree(pv);
          }
          PropVariantClear(pvar);
        }
      }
      CoTaskMemFree(v28);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006dc70  push    rbp
0x18006dc72  push    rbx
0x18006dc73  push    rsi
0x18006dc74  push    rdi
0x18006dc75  push    r12
0x18006dc77  push    r13
0x18006dc79  push    r14
0x18006dc7b  push    r15
0x18006dc7d  lea     rbp, [rsp-1Fh]
0x18006dc82  sub     rsp, 0E8h
0x18006dc89  mov     rax, cs:__security_cookie
0x18006dc90  xor     rax, rsp
0x18006dc93  mov     [rbp+57h+var_48], rax
0x18006dc97  mov     rdi, rdx
0x18006dc9a  xor     r14d, r14d
0x18006dc9d  mov     [r9], r14
0x18006dca0  mov     r13, rcx
0x18006dca3  mov     rax, [rdx]
0x18006dca6  mov     rcx, rdi
0x18006dca9  lea     rdx, [rbp+57h+var_90]
0x18006dcad  mov     [rbp+57h+var_90], r14d
0x18006dcb1  mov     r15, r9
0x18006dcb4  mov     r12, r8
0x18006dcb7  mov     rax, [rax+40h]
0x18006dcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dcc0  mov     ebx, eax
0x18006dcc2  test    eax, eax
0x18006dcc4  js      loc_18006E021
0x18006dcca  mov     ecx, [rbp+57h+var_90]
0x18006dccd  test    ecx, ecx
0x18006dccf  jz      loc_18006DEDF
0x18006dcd5  sub     ecx, 1
0x18006dcd8  jz      loc_18006DEDF
0x18006dcde  sub     ecx, 1
0x18006dce1  jz      loc_18006DE64
0x18006dce7  cmp     ecx, 1
0x18006dcea  jz      short loc_18006DCF6
0x18006dcec  mov     ebx, 8000FFFFh
0x18006dcf1  jmp     loc_18006E021
0x18006dcf6  mov     rax, [rdi]
0x18006dcf9  lea     rdx, [rbp+57h+var_B0]
0x18006dcfd  mov     rcx, rdi
0x18006dd00  mov     [rbp+57h+var_B0], r14
0x18006dd04  mov     rax, [rax+58h]
0x18006dd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd0d  mov     ebx, eax
0x18006dd0f  test    eax, eax
0x18006dd11  js      loc_18006E021
0x18006dd17  mov     rax, [rdi]
0x18006dd1a  cmp     [rbp+57h+var_B0], r14
0x18006dd1e  jz      short loc_18006DD38
0x18006dd20  mov     rax, [rax]
0x18006dd23  mov     r8, r15
0x18006dd26  mov     rdx, r12
0x18006dd29  mov     rcx, rdi
0x18006dd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd31  mov     ebx, eax
0x18006dd33  jmp     loc_18006DE55
0x18006dd38  mov     rax, [rax+80h]
0x18006dd3f  lea     r9, [rbp+57h+pvar]
0x18006dd43  xor     ecx, ecx
0x18006dd45  mov     [rbp+57h+var_A8], r14d
0x18006dd49  xorps   xmm0, xmm0
0x18006dd4c  mov     [rbp+57h+var_50], ecx
0x18006dd4f  mov     [rbp+57h+var_68], rcx
0x18006dd53  lea     r8, [rbp+57h+var_A8]
0x18006dd57  mov     rcx, rdi
0x18006dd5a  lea     rdx, [rbp+57h+var_60]
0x18006dd5e  movups  [rbp+57h+var_60], xmm0
0x18006dd62  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18006dd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd6b  mov     ebx, eax
0x18006dd6d  test    eax, eax
0x18006dd6f  js      loc_18006DE55
0x18006dd75  mov     rax, [rdi]
0x18006dd78  lea     rdx, [rbp+57h+pv]
0x18006dd7c  mov     rcx, rdi
0x18006dd7f  mov     [rbp+57h+pv], r14
0x18006dd83  mov     rax, [rax+78h]
0x18006dd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd8c  mov     ebx, eax
0x18006dd8e  test    eax, eax
0x18006dd90  js      loc_18006DE4B
0x18006dd96  mov     rax, [rdi]
0x18006dd99  lea     r9, [rbp+57h+var_80]
0x18006dd9d  lea     r8, [rbp+57h+var_88]
0x18006dda1  mov     [rbp+57h+var_98], r14
0x18006dda5  lea     rdx, [rbp+57h+var_98]
0x18006dda9  mov     [rbp+57h+var_88], r14
0x18006ddad  mov     rcx, rdi
0x18006ddb0  mov     [rbp+57h+var_80], r14
0x18006ddb4  mov     rax, [rax+68h]
0x18006ddb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddbd  mov     ebx, eax
0x18006ddbf  test    eax, eax
0x18006ddc1  js      short loc_18006DE41
0x18006ddc3  mov     rbx, [rbp+57h+var_80]
0x18006ddc7  lea     rcx, [rbp+57h+pvar]; this
0x18006ddcb  mov     rdi, [rbp+57h+var_88]
0x18006ddcf  mov     rsi, [rbp+57h+var_98]
0x18006ddd3  mov     r14, [rbp+57h+pv]
0x18006ddd7  call    ?_SemanticTypeFromPropVariantRec@StructuredQuery1@@YAPEB_WAEBUtagPROPVARIANT@@@Z; StructuredQuery1::_SemanticTypeFromPropVariantRec(tagPROPVARIANT const &)
0x18006dddc  mov     r8d, [rbp+57h+var_A8]
0x18006dde0  lea     rdx, [rbp+57h+var_60]
0x18006dde4  mov     [rsp+120h+var_B8], r15
0x18006dde9  xor     ecx, ecx
0x18006ddeb  mov     [rsp+120h+var_C0], r12
0x18006ddf0  mov     r9, rax
0x18006ddf3  mov     [rsp+120h+var_C8], cl
0x18006ddf7  mov     [rsp+120h+var_D0], cl
0x18006ddfb  mov     [rsp+120h+var_D8], rbx
0x18006de00  mov     [rsp+120h+var_E0], rdi
0x18006de05  mov     [rsp+120h+var_E8], rsi
0x18006de0a  mov     dword ptr [rsp+120h+var_F0], ecx
0x18006de0e  lea     rcx, [rbp+57h+pvar]
0x18006de12  mov     [rsp+120h+var_F8], r14
0x18006de17  mov     [rsp+120h+var_100], rcx
0x18006de1c  mov     rcx, r13
0x18006de1f  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@55_N6AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x18006de24  lea     rcx, [rbp+57h+var_98]
0x18006de28  mov     ebx, eax
0x18006de2a  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18006de2f  lea     rcx, [rbp+57h+var_88]
0x18006de33  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18006de38  lea     rcx, [rbp+57h+var_80]
0x18006de3c  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x18006de41  mov     rcx, [rbp+57h+pv]; pv
0x18006de45  call    cs:__imp_CoTaskMemFree
0x18006de4b  lea     rcx, [rbp+57h+pvar]; pvar
0x18006de4f  call    cs:__imp_PropVariantClear
0x18006de55  mov     rcx, [rbp+57h+var_B0]; pv
0x18006de59  call    cs:__imp_CoTaskMemFree
0x18006de5f  jmp     loc_18006E021
0x18006de64  mov     rax, [rdi]
0x18006de67  lea     r8, [rbp+57h+pv]
0x18006de6b  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18006de72  mov     [rbp+57h+pv], r14
0x18006de76  mov     rcx, rdi
0x18006de79  mov     rax, [rax+48h]
0x18006de7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de82  mov     ebx, eax
0x18006de84  test    eax, eax
0x18006de86  js      loc_18006E021
0x18006de8c  mov     rdx, [rbp+57h+pv]; struct ICondition2 *
0x18006de90  lea     r9, [rbp+57h+var_B0]; void **
0x18006de94  lea     r8, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8; struct _GUID *
0x18006de9b  mov     [rbp+57h+var_B0], r14
0x18006de9f  mov     rcx, r13; this
0x18006dea2  call    ?AddStandardSemanticTypes@Solution@StructuredQuery1@@AEAAJPEAUICondition2@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::AddStandardSemanticTypes(ICondition2 *,_GUID const &,void * *)
0x18006dea7  mov     ebx, eax
0x18006dea9  test    eax, eax
0x18006deab  js      short loc_18006DED6
0x18006dead  mov     rdx, [rbp+57h+var_B0]; struct ICondition *
0x18006deb1  mov     r9, r12; struct _GUID *
0x18006deb4  mov     r8b, 1; bool
0x18006deb7  mov     [rsp+120h+var_100], r15; void **
0x18006debc  mov     rcx, r13; this
0x18006debf  call    ?MakeNegation@Solution@StructuredQuery1@@QEAAJPEAUICondition@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeNegation(ICondition *,bool,_GUID const &,void * *)
0x18006dec4  mov     rcx, [rbp+57h+var_B0]
0x18006dec8  mov     ebx, eax
0x18006deca  mov     rax, [rcx]
0x18006decd  mov     rax, [rax+10h]
0x18006ded1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ded6  mov     rcx, [rbp+57h+pv]
0x18006deda  jmp     loc_18006E015
0x18006dedf  mov     rax, [rdi]
0x18006dee2  lea     r8, [rbp+57h+var_98]
0x18006dee6  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18006deed  mov     [rbp+57h+var_98], r14
0x18006def1  mov     rcx, rdi
0x18006def4  mov     rax, [rax+48h]
0x18006def8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006defd  mov     ebx, eax
0x18006deff  test    eax, eax
0x18006df01  js      loc_18006E021
0x18006df07  mov     rcx, [rbp+57h+var_98]
0x18006df0b  lea     rdx, [rbp+57h+var_A8]
0x18006df0f  mov     [rbp+57h+var_A8], r14d
0x18006df13  mov     rax, [rcx]
0x18006df16  mov     rax, [rax+18h]
0x18006df1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df1f  mov     ebx, eax
0x18006df21  test    eax, eax
0x18006df23  js      loc_18006E011
0x18006df29  mov     ecx, [rbp+57h+var_A8]; unsigned int
0x18006df2c  lea     r8, [rbp+57h+var_B0]; void **
0x18006df30  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x18006df37  mov     [rbp+57h+var_B0], r14
0x18006df3b  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJIAEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(uint,_GUID const &,void * *)
0x18006df40  mov     ebx, eax
0x18006df42  test    eax, eax
0x18006df44  js      loc_18006E011
0x18006df4a  mov     rdi, [rbp+57h+var_B0]
0x18006df4e  mov     esi, r14d
0x18006df51  cmp     esi, [rbp+57h+var_A8]
0x18006df54  jnb     loc_18006DFE3
0x18006df5a  mov     rcx, [rbp+57h+var_98]
0x18006df5e  lea     r9, [rbp+57h+pv]
0x18006df62  mov     [rbp+57h+pv], r14
0x18006df66  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18006df6d  mov     edx, esi
0x18006df6f  mov     rax, [rcx]
0x18006df72  mov     rax, [rax+20h]
0x18006df76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df7b  mov     ebx, eax
0x18006df7d  test    eax, eax
0x18006df7f  js      short loc_18006DFD7
0x18006df81  mov     rdx, [rbp+57h+pv]; struct ICondition2 *
0x18006df85  lea     r9, [rbp+57h+var_B0]; void **
0x18006df89  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7; struct _GUID *
0x18006df90  mov     [rbp+57h+var_B0], r14
0x18006df94  mov     rcx, r13; this
0x18006df97  call    ?AddStandardSemanticTypes@Solution@StructuredQuery1@@AEAAJPEAUICondition2@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::AddStandardSemanticTypes(ICondition2 *,_GUID const &,void * *)
0x18006df9c  mov     ebx, eax
0x18006df9e  test    eax, eax
0x18006dfa0  js      short loc_18006DFC7
0x18006dfa2  mov     rax, [rdi]
0x18006dfa5  mov     rcx, rdi
0x18006dfa8  mov     rdx, [rbp+57h+var_B0]
0x18006dfac  mov     rax, [rax+28h]
0x18006dfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfb5  mov     rcx, [rbp+57h+var_B0]
0x18006dfb9  mov     ebx, eax
0x18006dfbb  mov     rax, [rcx]
0x18006dfbe  mov     rax, [rax+10h]
0x18006dfc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfc7  mov     rcx, [rbp+57h+pv]
0x18006dfcb  mov     rax, [rcx]
0x18006dfce  mov     rax, [rax+10h]
0x18006dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfd7  inc     esi
0x18006dfd9  test    ebx, ebx
0x18006dfdb  jns     loc_18006DF51
0x18006dfe1  jmp     short loc_18006E002
0x18006dfe3  mov     edx, [rbp+57h+var_90]; enum tagCONDITION_TYPE
0x18006dfe6  mov     r9b, 1; bool
0x18006dfe9  mov     [rsp+120h+var_F0], r15; void **
0x18006dfee  mov     r8, rdi; struct IObjectArray *
0x18006dff1  mov     [rsp+120h+var_F8], r12; struct _GUID *
0x18006dff6  mov     byte ptr [rsp+120h+var_100], r14b; bool
0x18006dffb  call    ?MakeCompound@Solution@StructuredQuery1@@QEAAJW4tagCONDITION_TYPE@@PEAUIObjectArray@@_N2AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeCompound(tagCONDITION_TYPE,IObjectArray *,bool,bool,_GUID const &,void * *)
0x18006e000  mov     ebx, eax
0x18006e002  mov     rax, [rdi]
0x18006e005  mov     rcx, rdi
0x18006e008  mov     rax, [rax+10h]
0x18006e00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e011  mov     rcx, [rbp+57h+var_98]
0x18006e015  mov     rax, [rcx]
0x18006e018  mov     rax, [rax+10h]
0x18006e01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e021  mov     eax, ebx
0x18006e023  mov     rcx, [rbp+57h+var_48]
0x18006e027  xor     rcx, rsp; StackCookie
0x18006e02a  call    __security_check_cookie
0x18006e02f  add     rsp, 0E8h
0x18006e036  pop     r15
0x18006e038  pop     r14
0x18006e03a  pop     r13
0x18006e03c  pop     r12
0x18006e03e  pop     rdi
0x18006e03f  pop     rsi
0x18006e040  pop     rbx
0x18006e041  pop     rbp
0x18006e042  retn
```
