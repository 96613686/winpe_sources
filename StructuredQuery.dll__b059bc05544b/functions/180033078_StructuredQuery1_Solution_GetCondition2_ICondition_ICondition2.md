# StructuredQuery1::Solution::GetCondition2(ICondition *,ICondition2 * *)

- ea: `0x180033078`
- end: `0x18003314c`
- name: `?GetCondition2@Solution@StructuredQuery1@@AEAAJPEAUICondition@@PEAPEAUICondition2@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(StructuredQuery1::Solution *__hidden this, struct ICondition *, struct ICondition2 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032f34`

## callees

- `0x1800094f8`
- `0x180009a40`
- `0x18000b180`
- `0x18000c3a0`
- `0x180033078`
- `0x18003f7a0`
- `0x1800575c0`
- `0x180059920`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180089d7f`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180089d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089e1a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180089e24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180089e24`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::GetCondition2(
        StructuredQuery1::Solution *this,
        struct ICondition *a2,
        struct ICondition2 **a3)
{
  HRESULT (__stdcall *QueryInterface)(ICondition *, const IID *const, void **); // rax
  int Compound; // edi
  struct IConditionVtbl *lpVtbl; // rax
  struct IConditionVtbl *v10; // rax
  struct _tagpropertykey *v11; // r8
  struct IConditionVtbl *v12; // rax
  struct IConditionVtbl *v13; // rax
  int Predicate; // eax
  struct IConditionVtbl *v15; // rax
  struct IConditionVtbl *v16; // rax
  StructuredQuery1::Solution *v17; // rcx
  LPVOID v18; // rbx
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  enum tagCONDITION_TYPE v20; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  enum tagCONDITION_OPERATION v22; // [rsp+88h] [rbp-78h] BYREF
  void *v23; // [rsp+90h] [rbp-70h] BYREF
  struct IRichChunk *v24; // [rsp+98h] [rbp-68h] BYREF
  struct IRichChunk *v25; // [rsp+A0h] [rbp-60h] BYREF
  struct IRichChunk *v26; // [rsp+A8h] [rbp-58h] BYREF
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-40h]
  PROPERTYKEY v29; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR LocaleName[88]; // [rsp+E0h] [rbp-20h] BYREF

  QueryInterface = a2->lpVtbl->QueryInterface;
  v23 = 0;
  Compound = ((__int64 (__fastcall *)(struct ICondition *, GUID *, void **))QueryInterface)(
               a2,
               &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
               &v23);
  if ( Compound >= 0 )
    goto LABEL_2;
  lpVtbl = a2->lpVtbl;
  v20 = CT_AND_CONDITION;
  Compound = ((__int64 (__fastcall *)(struct ICondition *, enum tagCONDITION_TYPE *))lpVtbl->GetConditionType)(a2, &v20);
  if ( Compound < 0 )
    goto LABEL_2;
  if ( (unsigned int)v20 < CT_NOT_CONDITION )
  {
    v16 = a2->lpVtbl;
    Buffer = 0;
    Compound = ((__int64 (__fastcall *)(struct ICondition *, GUID *, wchar_t **))v16->GetSubConditions)(
                 a2,
                 &GUID_00000100_0000_0000_c000_000000000046,
                 &Buffer);
    if ( Compound < 0 )
      goto LABEL_2;
    pv = 0;
    Compound = FixedCapacityObjectCollection::CreateInstance(
                 (struct IEnumUnknown *)Buffer,
                 &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                 &pv);
    if ( Compound >= 0 )
    {
      v18 = pv;
      Compound = StructuredQuery1::Solution::MakeCompound(
                   v17,
                   v20,
                   (struct IObjectArray *)pv,
                   1,
                   0,
                   &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                   &v23);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    }
    goto LABEL_23;
  }
  if ( v20 == CT_NOT_CONDITION )
  {
    v15 = a2->lpVtbl;
    Buffer = 0;
    Compound = ((__int64 (__fastcall *)(struct ICondition *, GUID *, wchar_t **))v15->GetSubConditions)(
                 a2,
                 &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                 &Buffer);
    if ( Compound < 0 )
      goto LABEL_2;
    Compound = StructuredQuery1::Solution::MakeNegation(
                 this,
                 (struct ICondition *)Buffer,
                 0,
                 &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                 &v23);
LABEL_23:
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)Buffer + 16LL))(Buffer);
    goto LABEL_2;
  }
  if ( v20 == CT_LEAF_CONDITION )
  {
    Buffer = 0;
    v28 = 0;
    v10 = a2->lpVtbl;
    v22 = COP_IMPLICIT;
    *(_OWORD *)pvar = 0;
    Compound = ((__int64 (__fastcall *)(struct ICondition *, wchar_t **, enum tagCONDITION_OPERATION *, PROPVARIANT *))v10->GetComparisonInfo)(
                 a2,
                 &Buffer,
                 &v22,
                 pvar);
    if ( Compound >= 0 )
    {
      memset(&v29, 0, sizeof(v29));
      Compound = StructuredQuery1::GetKeyFromConditionPropertyName(Buffer, &v29, v11);
      if ( Compound >= 0 )
      {
        v12 = a2->lpVtbl;
        pv = 0;
        Compound = ((__int64 (__fastcall *)(struct ICondition *, LPVOID *))v12->GetValueType)(a2, &pv);
        if ( Compound >= 0 )
        {
          v13 = a2->lpVtbl;
          v24 = 0;
          v25 = 0;
          v26 = 0;
          Compound = ((__int64 (__fastcall *)(struct ICondition *, struct IRichChunk **, struct IRichChunk **, struct IRichChunk **))v13->GetInputTerms)(
                       a2,
                       &v24,
                       &v25,
                       &v26);
          if ( Compound >= 0 )
          {
            if ( GetUserDefaultLocaleName(LocaleName, 85) )
              Predicate = StructuredQuery1::Solution::MakePredicate(
                            (__int64)this,
                            &v29,
                            v22,
                            (const wchar_t *)pv,
                            pvar,
                            LocaleName,
                            0,
                            v24,
                            v25,
                            v26,
                            0,
                            0,
                            &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                            &v23);
            else
              Predicate = ResultFromKnownLastError();
            Compound = Predicate;
            IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v24);
            IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v25);
            IUnknown_SafeReleaseAndNullPtr<IRichChunk>(&v26);
          }
          CoTaskMemFree(pv);
        }
      }
      CoTaskMemFree(Buffer);
      PropVariantClear(pvar);
    }
  }
  else
  {
    Compound = -2147418113;
  }
LABEL_2:
  *a3 = (struct ICondition2 *)v23;
  return (unsigned int)Compound;
}

```

## disassembly

```asm
0x180033078  push    rbp
0x18003307a  push    rbx
0x18003307b  push    rsi
0x18003307c  push    rdi
0x18003307d  push    r12
0x18003307f  push    r14
0x180033081  push    r15
0x180033083  lea     rbp, [rsp-0A0h]
0x18003308b  sub     rsp, 1A0h
0x180033092  mov     rax, cs:__security_cookie
0x180033099  xor     rax, rsp
0x18003309c  mov     [rbp+0D0h+var_40], rax
0x1800330a3  mov     rax, [rdx]
0x1800330a6  lea     r12, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800330ad  mov     rbx, rdx
0x1800330b0  mov     r14, r8
0x1800330b3  mov     rsi, rcx
0x1800330b6  lea     r8, [rbp+0D0h+var_140]
0x1800330ba  xor     r15d, r15d
0x1800330bd  mov     rdx, r12
0x1800330c0  mov     rax, [rax]
0x1800330c3  mov     rcx, rbx
0x1800330c6  mov     [rbp+0D0h+var_140], r15
0x1800330ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330cf  mov     edi, eax
0x1800330d1  test    eax, eax
0x1800330d3  js      short loc_1800330FF
0x1800330d5  mov     rax, [rbp+0D0h+var_140]
0x1800330d9  mov     [r14], rax
0x1800330dc  mov     eax, edi
0x1800330de  mov     rcx, [rbp+0D0h+var_40]
0x1800330e5  xor     rcx, rsp; StackCookie
0x1800330e8  call    __security_check_cookie
0x1800330ed  add     rsp, 1A0h
0x1800330f4  pop     r15
0x1800330f6  pop     r14
0x1800330f8  pop     r12
0x1800330fa  pop     rdi
0x1800330fb  pop     rsi
0x1800330fc  pop     rbx
0x1800330fd  pop     rbp
0x1800330fe  retn
0x1800330ff  mov     rax, [rbx]
0x180033102  lea     rdx, [rsp+1D0h+var_158]
0x180033107  mov     rcx, rbx
0x18003310a  mov     [rsp+1D0h+var_158], r15d
0x18003310f  mov     rax, [rax+40h]
0x180033113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033118  mov     edi, eax
0x18003311a  test    eax, eax
0x18003311c  js      short loc_1800330D5
0x18003311e  mov     ecx, [rsp+1D0h+var_158]
0x180033122  test    ecx, ecx
0x180033124  jz      loc_180089E7D
0x18003312a  sub     ecx, 1
0x18003312d  jz      loc_180089E7D
0x180033133  sub     ecx, 1
0x180033136  jz      loc_180089E30
0x18003313c  cmp     ecx, 1
0x18003313f  jz      loc_180089CC4
0x180033145  mov     edi, 8000FFFFh
0x18003314a  jmp     short loc_1800330D5
0x180089cc4  xor     eax, eax
0x180089cc6  mov     [rsp+1D0h+Buffer], r15
0x180089ccb  mov     [rbp+0D0h+var_110], rax
0x180089ccf  lea     r9, [rbp+0D0h+pvar]
0x180089cd3  mov     rax, [rbx]
0x180089cd6  lea     r8, [rbp+0D0h+var_148]
0x180089cda  xorps   xmm0, xmm0
0x180089cdd  mov     [rbp+0D0h+var_148], r15d
0x180089ce1  lea     rdx, [rsp+1D0h+Buffer]
0x180089ce6  mov     rcx, rbx
0x180089ce9  movups  xmmword ptr [rbp+0D0h+pvar], xmm0
0x180089ced  mov     rax, [rax+50h]
0x180089cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089cf6  mov     edi, eax
0x180089cf8  test    eax, eax
0x180089cfa  js      loc_1800330D5
0x180089d00  mov     rcx, [rsp+1D0h+Buffer]; Buffer
0x180089d05  lea     rdx, [rbp+0D0h+var_108]; wchar_t *
0x180089d09  xorps   xmm0, xmm0
0x180089d0c  xor     eax, eax
0x180089d0e  movups  xmmword ptr [rbp+0D0h+var_108], xmm0
0x180089d12  mov     [rbp+0D0h+var_F8], eax
0x180089d15  call    ?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z; StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)
0x180089d1a  mov     edi, eax
0x180089d1c  test    eax, eax
0x180089d1e  js      loc_180089E15
0x180089d24  mov     rax, [rbx]
0x180089d27  lea     rdx, [rbp+0D0h+pv]
0x180089d2b  mov     rcx, rbx
0x180089d2e  mov     [rbp+0D0h+pv], r15
0x180089d32  mov     rax, [rax+58h]
0x180089d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d3b  mov     edi, eax
0x180089d3d  test    eax, eax
0x180089d3f  js      loc_180089E15
0x180089d45  mov     rax, [rbx]
0x180089d48  lea     r9, [rbp+0D0h+var_128]
0x180089d4c  lea     r8, [rbp+0D0h+var_130]
0x180089d50  mov     [rbp+0D0h+var_138], r15
0x180089d54  lea     rdx, [rbp+0D0h+var_138]
0x180089d58  mov     [rbp+0D0h+var_130], r15
0x180089d5c  mov     rcx, rbx
0x180089d5f  mov     [rbp+0D0h+var_128], r15
0x180089d63  mov     rax, [rax+68h]
0x180089d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d6c  mov     edi, eax
0x180089d6e  test    eax, eax
0x180089d70  js      loc_180089E0B
0x180089d76  mov     edx, 55h ; 'U'; cchLocaleName
0x180089d7b  lea     rcx, [rbp+0D0h+LocaleName]; lpLocaleName
0x180089d7f  call    cs:__imp_GetUserDefaultLocaleName
0x180089d85  test    eax, eax
0x180089d87  jz      short loc_180089DE9
0x180089d89  mov     rax, [rbp+0D0h+var_128]
0x180089d8d  lea     rcx, [rbp+0D0h+var_140]
0x180089d91  mov     rdx, [rbp+0D0h+var_130]
0x180089d95  mov     r10, [rbp+0D0h+var_138]
0x180089d99  mov     r9, [rbp+0D0h+pv]
0x180089d9d  mov     r8d, [rbp+0D0h+var_148]
0x180089da1  mov     [rsp+1D0h+var_168], rcx
0x180089da6  mov     rcx, rsi
0x180089da9  mov     [rsp+1D0h+var_170], r12
0x180089dae  mov     [rsp+1D0h+var_178], r15b
0x180089db3  mov     [rsp+1D0h+var_180], r15b
0x180089db8  mov     [rsp+1D0h+var_188], rax
0x180089dbd  lea     rax, [rbp+0D0h+LocaleName]
0x180089dc1  mov     [rsp+1D0h+var_190], rdx
0x180089dc6  lea     rdx, [rbp+0D0h+var_108]
0x180089dca  mov     [rsp+1D0h+var_198], r10
0x180089dcf  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x180089dd4  mov     [rsp+1D0h+var_1A8], rax
0x180089dd9  lea     rax, [rbp+0D0h+pvar]
0x180089ddd  mov     [rsp+1D0h+var_1B0], rax
0x180089de2  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@55_N6AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x180089de7  jmp     short loc_180089DEE
0x180089de9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180089dee  lea     rcx, [rbp+0D0h+var_138]
0x180089df2  mov     edi, eax
0x180089df4  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x180089df9  lea     rcx, [rbp+0D0h+var_130]
0x180089dfd  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x180089e02  lea     rcx, [rbp+0D0h+var_128]
0x180089e06  call    ??$IUnknown_SafeReleaseAndNullPtr@UIRichChunk@@@@YAXAEAPEAUIRichChunk@@@Z; IUnknown_SafeReleaseAndNullPtr<IRichChunk>(IRichChunk * &)
0x180089e0b  mov     rcx, [rbp+0D0h+pv]; pv
0x180089e0f  call    cs:__imp_CoTaskMemFree
0x180089e15  mov     rcx, [rsp+1D0h+Buffer]; pv
0x180089e1a  call    cs:__imp_CoTaskMemFree
0x180089e20  lea     rcx, [rbp+0D0h+pvar]; pvar
0x180089e24  call    cs:__imp_PropVariantClear
0x180089e2a  nop
0x180089e2b  jmp     loc_1800330D5
0x180089e30  mov     rax, [rbx]
0x180089e33  lea     r8, [rsp+1D0h+Buffer]
0x180089e38  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180089e3f  mov     [rsp+1D0h+Buffer], r15
0x180089e44  mov     rcx, rbx
0x180089e47  mov     rax, [rax+48h]
0x180089e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e50  mov     edi, eax
0x180089e52  test    eax, eax
0x180089e54  js      loc_1800330D5
0x180089e5a  mov     rdx, [rsp+1D0h+Buffer]; struct ICondition *
0x180089e5f  lea     rax, [rbp+0D0h+var_140]
0x180089e63  mov     r9, r12; struct _GUID *
0x180089e66  mov     [rsp+1D0h+var_1B0], rax; void **
0x180089e6b  xor     r8d, r8d; bool
0x180089e6e  mov     rcx, rsi; this
0x180089e71  call    ?MakeNegation@Solution@StructuredQuery1@@QEAAJPEAUICondition@@_NAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeNegation(ICondition *,bool,_GUID const &,void * *)
0x180089e76  mov     edi, eax
0x180089e78  jmp     loc_180089EFD
0x180089e7d  mov     rax, [rbx]
0x180089e80  lea     r8, [rsp+1D0h+Buffer]
0x180089e85  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x180089e8c  mov     [rsp+1D0h+Buffer], r15
0x180089e91  mov     rcx, rbx
0x180089e94  mov     rax, [rax+48h]
0x180089e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e9d  mov     edi, eax
0x180089e9f  test    eax, eax
0x180089ea1  js      loc_1800330D5
0x180089ea7  mov     rcx, [rsp+1D0h+Buffer]; this
0x180089eac  lea     r8, [rbp+0D0h+pv]; void **
0x180089eb0  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; struct _GUID *
0x180089eb7  mov     [rbp+0D0h+pv], r15
0x180089ebb  call    ?CreateInstance@FixedCapacityObjectCollection@@SAJPEAUIEnumUnknown@@AEBU_GUID@@PEAPEAX@Z; FixedCapacityObjectCollection::CreateInstance(IEnumUnknown *,_GUID const &,void * *)
0x180089ec0  mov     edi, eax
0x180089ec2  test    eax, eax
0x180089ec4  js      short loc_180089EFD
0x180089ec6  mov     rbx, [rbp+0D0h+pv]
0x180089eca  lea     rax, [rbp+0D0h+var_140]
0x180089ece  mov     edx, [rsp+1D0h+var_158]; enum tagCONDITION_TYPE
0x180089ed2  mov     r9b, 1; bool
0x180089ed5  mov     [rsp+1D0h+var_1A0], rax; void **
0x180089eda  mov     r8, rbx; struct IObjectArray *
0x180089edd  mov     [rsp+1D0h+var_1A8], r12; struct _GUID *
0x180089ee2  mov     byte ptr [rsp+1D0h+var_1B0], r15b; bool
0x180089ee7  call    ?MakeCompound@Solution@StructuredQuery1@@QEAAJW4tagCONDITION_TYPE@@PEAUIObjectArray@@_N2AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakeCompound(tagCONDITION_TYPE,IObjectArray *,bool,bool,_GUID const &,void * *)
0x180089eec  mov     edi, eax
0x180089eee  mov     rcx, rbx
0x180089ef1  mov     rax, [rbx]
0x180089ef4  mov     rax, [rax+10h]
0x180089ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089efd  mov     rcx, [rsp+1D0h+Buffer]
0x180089f02  mov     rax, [rcx]
0x180089f05  mov     rax, [rax+10h]
0x180089f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f0e  nop
0x180089f0f  jmp     loc_1800330D5
```
