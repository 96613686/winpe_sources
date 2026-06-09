# CConditionEvaluator::v_DoesItemMatchLeafCondition(tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,TRIBIT *,int *)

- ea: `0x180029fa0`
- end: `0x18002a86b`
- name: `?v_DoesItemMatchLeafCondition@CConditionEvaluator@@MEAAJAEBUtagPROPVARIANT@@AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAW4TRIBIT@@PEAH@Z`
- size: `2251`
- prototype: `__int64 __usercall@<rax>(CConditionEvaluator *__hidden this@<rcx>, const struct tagPROPVARIANT *@<rdx>, const struct _tagpropertykey *@<r8>, enum tagCONDITION_OPERATION@<r9d>, struct ICondition *p, int, enum TRIBIT *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180029a00`

## callees

- `0x180027da0`
- `0x180029fa0`
- `0x18002a880`
- `0x180031920`
- `0x180040b10`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a21d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a7d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a80e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a21d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a7d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a80e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a185`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a72e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a185`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a3be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a72e`
- `PROPSYS!PSGetPropertyDescription` at `0x18002a320`
- `PROPSYS!PSGetPropertyDescription` at `0x18002a320`
- `PROPSYS!__imp_PSGetCanonicalValue` at `0x18002a026`
- `PROPSYS!__imp_PSGetCanonicalValue` at `0x18002a36b`
- `PROPSYS!__imp_PSGetCanonicalValue` at `0x18002a026`
- `PROPSYS!__imp_PSGetCanonicalValue` at `0x18002a36b`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::v_DoesItemMatchLeafCondition(
        CConditionEvaluator *this,
        struct tagPROPVARIANT *a2,
        struct _tagpropertykey *a3,
        enum tagCONDITION_OPERATION a4,
        struct ICondition *p,
        unsigned int a6,
        enum TRIBIT *a7,
        int *a8)
{
  DWORD pid; // eax
  int v11; // edi
  int v12; // esi
  __int64 result; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  PROPVARIANT *v17; // rsi
  tagCONDITION_OPERATION v18; // r13d
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 ulVal; // rdx
  __int64 v27; // rcx
  int v28; // eax
  struct IConditionVtbl *lpVtbl; // rcx
  HRESULT v30; // esi
  __int64 v31; // r8
  LPVOID ppv; // [rsp+50h] [rbp-69h] BYREF
  tagCONDITION_OPERATION v33[2]; // [rsp+58h] [rbp-61h] BYREF
  struct tagPROPVARIANT *v34; // [rsp+60h] [rbp-59h] BYREF
  int v35; // [rsp+68h] [rbp-51h]
  __int64 v36; // [rsp+70h] [rbp-49h] BYREF
  int v37; // [rsp+78h] [rbp-41h] BYREF
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v39; // [rsp+90h] [rbp-29h]
  PROPVARIANT v40[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-11h]

  pid = a3->pid;
  v33[0] = a4;
  v34 = a2;
  if ( pid == 6 )
  {
    v14 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FullText.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FullText.fmtid.Data1 )
      v14 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FullText.fmtid.Data4;
    if ( v14 )
      goto LABEL_4;
  }
  else
  {
    if ( pid != 5 )
    {
      if ( pid == 12 )
      {
        v24 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_Generic_String;
        if ( *(_QWORD *)&a3->fmtid.Data1 == (_QWORD)PKEY_Generic_String )
          v24 = *(_QWORD *)a3->fmtid.Data4 - *((_QWORD *)&PKEY_Generic_String + 1);
        if ( !v24 )
          goto LABEL_26;
      }
LABEL_4:
      v41 = 0;
      *(_OWORD *)v40 = 0;
      if ( pid != 25 )
        goto LABEL_5;
      v25 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_SFGAOFlags.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_SFGAOFlags.fmtid.Data1 )
        v25 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_SFGAOFlags.fmtid.Data4;
      if ( !v25 && a2->vt == 19 && (ulVal = a2->ulVal, (_DWORD)ulVal) && (v27 = *((_QWORD *)this + 5)) != 0 )
      {
        LODWORD(ppv) = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v27 + 48LL))(v27, ulVal, &ppv);
        if ( v28 >= 0 )
        {
          LOWORD(v40[0]) = 19;
          LODWORD(v40[1]) = (_DWORD)ppv;
        }
        v11 = 0;
        if ( v28 < 0 )
          v11 = v28;
      }
      else
      {
LABEL_5:
        v11 = PSGetCanonicalValue(*((_QWORD *)this + 1), a3, v40);
      }
      if ( v11 >= 0 )
      {
        if ( LOWORD(v40[0]) )
        {
          LODWORD(ppv) = 0;
          v11 = CConditionEvaluator::_EvaluateProperty(
                  this,
                  (PROPVARIANT *)v34,
                  v40,
                  a3,
                  v33[0],
                  p,
                  a6,
                  (int *)&ppv,
                  a8);
          *(_QWORD *)v33 = 0;
          v12 = 2 - ((_DWORD)ppv != 0);
          *(_DWORD *)a7 = v12;
          if ( ((__int64 (__fastcall *)(struct ICondition *, GUID *, tagCONDITION_OPERATION *))p->lpVtbl->QueryInterface)(
                 p,
                 &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
                 v33) >= 0 )
          {
            ppv = 0;
            if ( (*(int (__fastcall **)(_QWORD, __int64 *, GUID *, LPVOID *))(**(_QWORD **)v33 + 32LL))(
                   *(_QWORD *)v33,
                   qword_1800F7E38,
                   &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                   &ppv) >= 0
              || CoCreateInstance(
                   &GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8,
                   0,
                   1u,
                   &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                   &ppv) >= 0 )
            {
              v36 = 0;
              if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                     ppv,
                     &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                     &v36) >= 0 )
              {
                v34 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64 *, GUID *, struct tagPROPVARIANT **))(*(_QWORD *)v36 + 24LL))(
                       v36,
                       &OID_PropertyStore,
                       &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                       &v34) >= 0 )
                {
                  v39 = 0;
                  *(_OWORD *)pvar = 0;
                  LODWORD(pvar[1]) = v12;
                  LOWORD(pvar[0]) = 3;
                  if ( (*(int (__fastcall **)(struct tagPROPVARIANT *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)&v34->vt + 32LL))(
                         v34,
                         L"ES",
                         pvar) >= 0 )
                    (*(void (__fastcall **)(_QWORD, __int64 *, LPVOID))(**(_QWORD **)v33 + 24LL))(
                      *(_QWORD *)v33,
                      qword_1800F7E38,
                      ppv);
                  PropVariantClear(pvar);
                  (*(void (__fastcall **)(struct tagPROPVARIANT *))(*(_QWORD *)&v34->vt + 16LL))(v34);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
          }
        }
        else
        {
          *(_DWORD *)a7 = 0;
          lpVtbl = p->lpVtbl;
          *(_QWORD *)v33 = 0;
          v30 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, tagCONDITION_OPERATION *))lpVtbl->QueryInterface)(
                  p,
                  &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
                  v33);
          if ( v30 >= 0 )
          {
            ppv = 0;
            if ( (*(int (__fastcall **)(_QWORD, __int64 *, GUID *, LPVOID *))(**(_QWORD **)v33 + 32LL))(
                   *(_QWORD *)v33,
                   qword_1800F7E38,
                   &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                   &ppv) >= 0
              || (v30 = CoCreateInstance(
                          &GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8,
                          0,
                          1u,
                          &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                          &ppv),
                  v30 >= 0) )
            {
              v36 = 0;
              v30 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                      ppv,
                      &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                      &v36);
              if ( v30 >= 0 )
              {
                v34 = 0;
                v30 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, struct tagPROPVARIANT **))(*(_QWORD *)v36 + 24LL))(
                        v36,
                        &OID_PropertyStore,
                        &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                        &v34);
                if ( v30 >= 0 )
                {
                  v39 = 0;
                  *(_OWORD *)pvar = 0;
                  LOWORD(pvar[0]) = 3;
                  LODWORD(pvar[1]) = 0;
                  v30 = (*(__int64 (__fastcall **)(struct tagPROPVARIANT *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)&v34->vt + 32LL))(
                          v34,
                          L"ES",
                          pvar);
                  if ( v30 >= 0 )
                    v30 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, LPVOID))(**(_QWORD **)v33 + 24LL))(
                            *(_QWORD *)v33,
                            qword_1800F7E38,
                            ppv);
                  PropVariantClear(pvar);
                  (*(void (__fastcall **)(struct tagPROPVARIANT *))(*(_QWORD *)&v34->vt + 16LL))(v34);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
          }
          if ( !*((_DWORD *)this + 17) && v30 >= 0 )
          {
            *(_QWORD *)v33 = 0;
            v11 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, tagCONDITION_OPERATION *))p->lpVtbl->QueryInterface)(
                    p,
                    &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
                    v33);
            if ( v11 >= 0 )
            {
              ppv = 0;
              if ( (*(int (__fastcall **)(_QWORD, __int64 *, GUID *, LPVOID *))(**(_QWORD **)v33 + 32LL))(
                     *(_QWORD *)v33,
                     qword_1800F7E38,
                     &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                     &ppv) >= 0
                || (v11 = CoCreateInstance(
                            &GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8,
                            0,
                            1u,
                            &GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a,
                            &ppv),
                    v11 >= 0) )
              {
                v36 = 0;
                v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                        ppv,
                        &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                        &v36);
                if ( v11 >= 0 )
                {
                  v34 = 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, struct tagPROPVARIANT **))(*(_QWORD *)v36 + 24LL))(
                          v36,
                          &OID_PropertyStore,
                          &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                          &v34);
                  if ( v11 >= 0 )
                  {
                    v39 = 0;
                    *(_OWORD *)pvar = 0;
                    LOWORD(pvar[0]) = 3;
                    LODWORD(pvar[1]) = 2 - (a6 != 0);
                    v11 = (*(__int64 (__fastcall **)(struct tagPROPVARIANT *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)&v34->vt + 32LL))(
                            v34,
                            L"Negate",
                            pvar);
                    if ( v11 >= 0 )
                      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, LPVOID))(**(_QWORD **)v33 + 24LL))(
                              *(_QWORD *)v33,
                              qword_1800F7E38,
                              ppv);
                    PropVariantClear(pvar);
                    (*(void (__fastcall **)(struct tagPROPVARIANT *))(*(_QWORD *)&v34->vt + 16LL))(v34);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              }
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
              if ( v11 >= 0 )
              {
                if ( DPA_InsertPtr(*((HDPA *)this + 10), 0x7FFFFFFF, p) == -1 )
                {
                  v11 = -2147024882;
                }
                else
                {
                  v11 = 0;
                  ((void (__fastcall *)(struct ICondition *))p->lpVtbl->AddRef)(p);
                  *((_DWORD *)this + 16) = 1;
                }
              }
            }
          }
        }
        PropVariantClear(v40);
      }
      return (unsigned int)v11;
    }
    v23 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ForceFullText;
    if ( *(_QWORD *)&a3->fmtid.Data1 == (_QWORD)PKEY_ForceFullText )
      v23 = *(_QWORD *)a3->fmtid.Data4 - *((_QWORD *)&PKEY_ForceFullText + 1);
    if ( v23 )
      goto LABEL_4;
  }
LABEL_26:
  v37 = 2;
  if ( *((_DWORD *)this + 17) )
  {
    GetEvalStateEx(p, L"FTSearched", &v37);
    if ( v37 == 1 )
      return 0;
    goto LABEL_29;
  }
  result = SetEvalStateEx(p, L"FTSearched", 2);
  if ( (int)result >= 0 )
  {
    result = SetEvalStateEx(p, L"ES", 0);
    if ( (int)result >= 0 )
    {
LABEL_29:
      v15 = *((_QWORD *)this + 1);
      LODWORD(v36) = 0;
      v37 = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, &v36);
      v11 = v35;
      LODWORD(ppv) = 0;
      v16 = 0;
      if ( v35 >= 0 )
      {
        v17 = (PROPVARIANT *)v34;
        v18 = v33[0];
        do
        {
          if ( v37 || (unsigned int)v16 >= (unsigned int)v36 )
            break;
          v19 = *((_QWORD *)this + 1);
          LODWORD(v41) = 0;
          *(_OWORD *)v40 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v19 + 32LL))(v19, v16, v40);
          v35 = v20;
          if ( v20 >= 0 )
          {
            v34 = 0;
            if ( PSGetPropertyDescription(
                   (const PROPERTYKEY *const)v40,
                   &GUID_078f91bd_29a2_440f_924e_46a291524520,
                   (void **)&v34) >= 0 )
            {
              v33[0] = COP_IMPLICIT;
              if ( (*(int (__fastcall **)(struct tagPROPVARIANT *, tagCONDITION_OPERATION *))(*(_QWORD *)&v34->vt + 192LL))(
                     v34,
                     v33) >= 0
                && (v33[0] & 1) != 0 )
              {
                v21 = *((_QWORD *)this + 1);
                *(_OWORD *)pvar = 0;
                v39 = 0;
                v35 = PSGetCanonicalValue(v21, v40, pvar);
                if ( v35 >= 0 )
                {
                  v22 = CConditionEvaluator::_EvaluateProperty(
                          this,
                          v17,
                          pvar,
                          (struct _tagpropertykey *)v40,
                          v18,
                          p,
                          0,
                          &v37,
                          0);
                  v35 = v22;
                  if ( v22 >= 0 )
                  {
                    if ( v37 )
                    {
                      v31 = (unsigned int)(a6 != 0) + 1;
                      *(_DWORD *)a7 = v31;
                      SetEvalStateEx(p, L"ES", v31);
                    }
                  }
                  else
                  {
                    if ( v22 != -2147024882 )
                      v22 = 0;
                    v35 = v22;
                  }
                  PropVariantClear(pvar);
                }
              }
              (*(void (__fastcall **)(struct tagPROPVARIANT *))(*(_QWORD *)&v34->vt + 16LL))(v34);
            }
            v20 = v35;
          }
          v16 = (unsigned int)((_DWORD)ppv + 1);
          LODWORD(ppv) = (_DWORD)ppv + 1;
        }
        while ( v20 >= 0 );
        v11 = v35;
      }
      SetEvalStateEx(p, L"FTSearched", 1);
      return (unsigned int)v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029fa0  mov     [rsp-8+arg_18], rbx
0x180029fa5  push    rbp
0x180029fa6  push    rsi
0x180029fa7  push    rdi
0x180029fa8  push    r12
0x180029faa  push    r13
0x180029fac  push    r14
0x180029fae  push    r15
0x180029fb0  lea     rbp, [rsp-7]
0x180029fb5  sub     rsp, 0C0h
0x180029fbc  mov     rax, cs:__security_cookie
0x180029fc3  xor     rax, rsp
0x180029fc6  mov     [rbp+37h+var_40], rax
0x180029fca  mov     eax, [r8+10h]
0x180029fce  mov     rsi, r8
0x180029fd1  mov     r15, [rbp+37h+p]
0x180029fd5  mov     r14, rcx
0x180029fd8  mov     r12, [rbp+37h+arg_30]
0x180029fdc  mov     r13, [rbp+37h+arg_38]
0x180029fe0  mov     [rbp+37h+var_98], r9d
0x180029fe4  mov     [rbp+37h+var_90], rdx
0x180029fe8  cmp     eax, 6
0x180029feb  jz      loc_18002A22D
0x180029ff1  cmp     eax, 5
0x180029ff4  jz      loc_18002A404
0x180029ffa  cmp     eax, 0Ch
0x180029ffd  jz      loc_18002A429
0x18002a003  xor     ecx, ecx
0x18002a005  xor     ebx, ebx
0x18002a007  mov     [rbp+37h+var_48], rcx
0x18002a00b  xorps   xmm0, xmm0
0x18002a00e  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x18002a012  cmp     eax, 19h
0x18002a015  jz      loc_18002A44E
0x18002a01b  mov     rcx, [r14+8]
0x18002a01f  lea     r8, [rbp+37h+var_58]
0x18002a023  mov     rdx, rsi
0x18002a026  call    cs:__imp_PSGetCanonicalValue
0x18002a02c  mov     edi, eax
0x18002a02e  test    edi, edi
0x18002a030  js      loc_18002A1D5
0x18002a036  cmp     word ptr [rbp+37h+var_58], bx
0x18002a03a  jz      loc_18002A4C2
0x18002a040  mov     rdx, [rbp+37h+var_90]; struct tagPROPVARIANT *
0x18002a044  lea     rax, [rbp+37h+var_A0]
0x18002a048  mov     [rsp+0F0h+var_B0], r13; int *
0x18002a04d  lea     r8, [rbp+37h+var_58]; struct tagPROPVARIANT *
0x18002a051  mov     r13d, [rbp+37h+var_98]
0x18002a055  mov     r9, rsi; struct _tagpropertykey *
0x18002a058  mov     [rsp+0F0h+var_B8], rax; int *
0x18002a05d  mov     rcx, r14; this
0x18002a060  mov     eax, [rbp+37h+arg_28]
0x18002a063  mov     [rsp+0F0h+var_C0], eax; int
0x18002a067  mov     [rsp+0F0h+var_C8], r15; struct ICondition *
0x18002a06c  mov     dword ptr [rsp+0F0h+ppv], r13d; tagCONDITION_OPERATION
0x18002a071  mov     dword ptr [rbp+37h+var_A0], ebx
0x18002a074  call    ?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z; CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)
0x18002a079  mov     edi, eax
0x18002a07b  mov     qword ptr [rbp+37h+var_98], rbx
0x18002a07f  mov     eax, dword ptr [rbp+37h+var_A0]
0x18002a082  lea     r8, [rbp+37h+var_98]
0x18002a086  neg     eax
0x18002a088  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x18002a08f  mov     rcx, r15
0x18002a092  sbb     esi, esi
0x18002a094  add     esi, 2
0x18002a097  mov     [r12], esi
0x18002a09b  mov     rax, [r15]
0x18002a09e  mov     rax, [rax]
0x18002a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0a6  test    eax, eax
0x18002a0a8  js      loc_18002A1CB
0x18002a0ae  mov     rcx, qword ptr [rbp+37h+var_98]
0x18002a0b2  lea     r9, [rbp+37h+var_A0]
0x18002a0b6  mov     [rbp+37h+var_A0], rbx
0x18002a0ba  lea     r8, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x18002a0c1  lea     rdx, qword_1800F7E38
0x18002a0c8  mov     rax, [rcx]
0x18002a0cb  mov     rax, [rax+20h]
0x18002a0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0d4  test    eax, eax
0x18002a0d6  js      loc_18002A1FE
0x18002a0dc  mov     rcx, [rbp+37h+var_A0]
0x18002a0e0  lea     r8, [rbp+37h+var_80]
0x18002a0e4  mov     [rbp+37h+var_80], rbx
0x18002a0e8  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x18002a0ef  mov     rax, [rcx]
0x18002a0f2  mov     rax, [rax]
0x18002a0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0fa  test    eax, eax
0x18002a0fc  js      loc_18002A1AB
0x18002a102  mov     rcx, [rbp+37h+var_80]
0x18002a106  lea     r9, [rbp+37h+var_90]
0x18002a10a  mov     [rbp+37h+var_90], rbx
0x18002a10e  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18002a115  lea     rdx, OID_PropertyStore
0x18002a11c  mov     rax, [rcx]
0x18002a11f  mov     rax, [rax+18h]
0x18002a123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a128  test    eax, eax
0x18002a12a  js      short loc_18002A19B
0x18002a12c  mov     rcx, [rbp+37h+var_90]
0x18002a130  lea     r8, [rbp+37h+pvar]
0x18002a134  xor     eax, eax
0x18002a136  lea     rdx, aEs; "ES"
0x18002a13d  mov     [rbp+37h+var_60], rax
0x18002a141  xorps   xmm0, xmm0
0x18002a144  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18002a148  mov     dword ptr [rbp+37h+pvar+8], esi
0x18002a14b  mov     r12d, 3
0x18002a151  mov     word ptr [rbp+37h+pvar], r12w
0x18002a156  mov     rax, [rcx]
0x18002a159  mov     rax, [rax+20h]
0x18002a15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a162  test    eax, eax
0x18002a164  js      short loc_18002A181
0x18002a166  mov     rcx, qword ptr [rbp+37h+var_98]
0x18002a16a  lea     rdx, qword_1800F7E38
0x18002a171  mov     r8, [rbp+37h+var_A0]
0x18002a175  mov     rax, [rcx]
0x18002a178  mov     rax, [rax+18h]
0x18002a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a181  lea     rcx, [rbp+37h+pvar]; pvar
0x18002a185  call    cs:__imp_PropVariantClear
0x18002a18b  mov     rcx, [rbp+37h+var_90]
0x18002a18f  mov     rax, [rcx]
0x18002a192  mov     rax, [rax+10h]
0x18002a196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a19b  mov     rcx, [rbp+37h+var_80]
0x18002a19f  mov     rax, [rcx]
0x18002a1a2  mov     rax, [rax+10h]
0x18002a1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1ab  mov     rcx, [rbp+37h+var_A0]
0x18002a1af  mov     rax, [rcx]
0x18002a1b2  mov     rax, [rax+10h]
0x18002a1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1bb  mov     rcx, qword ptr [rbp+37h+var_98]
0x18002a1bf  mov     rax, [rcx]
0x18002a1c2  mov     rax, [rax+10h]
0x18002a1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1cb  lea     rcx, [rbp+37h+var_58]; pvar
0x18002a1cf  call    cs:__imp_PropVariantClear
0x18002a1d5  mov     eax, edi
0x18002a1d7  mov     rcx, [rbp+37h+var_40]
0x18002a1db  xor     rcx, rsp; StackCookie
0x18002a1de  call    __security_check_cookie
0x18002a1e3  mov     rbx, [rsp+0F0h+arg_18]
0x18002a1eb  add     rsp, 0C0h
0x18002a1f2  pop     r15
0x18002a1f4  pop     r14
0x18002a1f6  pop     r13
0x18002a1f8  pop     r12
0x18002a1fa  pop     rdi
0x18002a1fb  pop     rsi
0x18002a1fc  pop     rbp
0x18002a1fd  retn
0x18002a1fe  lea     rax, [rbp+37h+var_A0]
0x18002a202  xor     edx, edx; pUnkOuter
0x18002a204  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a; riid
0x18002a20b  mov     [rsp+0F0h+ppv], rax; ppv
0x18002a210  mov     r8d, 1; dwClsContext
0x18002a216  lea     rcx, _GUID_18907f3b_9afb_4f87_b764_f9a4e16a21b8; rclsid
0x18002a21d  call    cs:__imp_CoCreateInstance
0x18002a223  test    eax, eax
0x18002a225  jns     loc_18002A0DC
0x18002a22b  jmp     short loc_18002A1BB
0x18002a22d  mov     rcx, [r8]
0x18002a230  sub     rcx, qword ptr cs:PKEY_FullText.fmtid.Data1
0x18002a237  jnz     short loc_18002A244
0x18002a239  mov     rcx, [r8+8]
0x18002a23d  sub     rcx, qword ptr cs:PKEY_FullText.fmtid.Data4
0x18002a244  test    rcx, rcx
0x18002a247  jnz     loc_18002A003
0x18002a24d  xor     ebx, ebx
0x18002a24f  mov     [rbp+37h+var_78], 2
0x18002a256  lea     rdx, aFtsearched; "FTSearched"
0x18002a25d  mov     rcx, r15
0x18002a260  cmp     [r14+44h], ebx
0x18002a264  jnz     loc_18002A851
0x18002a26a  mov     r8d, 2
0x18002a270  call    SetEvalStateEx
0x18002a275  test    eax, eax
0x18002a277  js      loc_18002A1D7
0x18002a27d  xor     r8d, r8d
0x18002a280  lea     rdx, aEs; "ES"
0x18002a287  mov     rcx, r15
0x18002a28a  call    SetEvalStateEx
0x18002a28f  test    eax, eax
0x18002a291  js      loc_18002A1D7
0x18002a297  mov     rcx, [r14+8]
0x18002a29b  lea     rdx, [rbp+37h+var_80]
0x18002a29f  mov     dword ptr [rbp+37h+var_80], ebx
0x18002a2a2  mov     [rbp+37h+var_78], ebx
0x18002a2a5  mov     rax, [rcx]
0x18002a2a8  mov     rax, [rax+18h]
0x18002a2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2b1  mov     [rbp+37h+var_88], eax
0x18002a2b4  mov     edi, eax
0x18002a2b6  mov     dword ptr [rbp+37h+var_A0], ebx
0x18002a2b9  mov     edx, ebx
0x18002a2bb  test    eax, eax
0x18002a2bd  js      loc_18002A3EA
0x18002a2c3  mov     rsi, [rbp+37h+var_90]
0x18002a2c7  mov     edi, 8007000Eh
0x18002a2cc  mov     r13d, [rbp+37h+var_98]
0x18002a2d0  cmp     [rbp+37h+var_78], ebx
0x18002a2d3  jnz     loc_18002A3E7
0x18002a2d9  cmp     edx, dword ptr [rbp+37h+var_80]
0x18002a2dc  jnb     loc_18002A3E7
0x18002a2e2  mov     rcx, [r14+8]
0x18002a2e6  lea     r8, [rbp+37h+var_58]
0x18002a2ea  xor     eax, eax
0x18002a2ec  xorps   xmm0, xmm0
0x18002a2ef  mov     dword ptr [rbp+37h+var_48], eax
0x18002a2f2  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x18002a2f6  mov     rax, [rcx]
0x18002a2f9  mov     rax, [rax+20h]
0x18002a2fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a302  mov     [rbp+37h+var_88], eax
0x18002a305  test    eax, eax
0x18002a307  js      loc_18002A3D7
0x18002a30d  lea     r8, [rbp+37h+var_90]; ppv
0x18002a311  mov     [rbp+37h+var_90], rbx
0x18002a315  lea     rdx, _GUID_078f91bd_29a2_440f_924e_46a291524520; riid
0x18002a31c  lea     rcx, [rbp+37h+var_58]; propkey
0x18002a320  call    cs:__imp_PSGetPropertyDescription
0x18002a326  test    eax, eax
0x18002a328  js      loc_18002A3D4
0x18002a32e  mov     rcx, [rbp+37h+var_90]
0x18002a332  lea     rdx, [rbp+37h+var_98]
0x18002a336  mov     [rbp+37h+var_98], ebx
0x18002a339  mov     rax, [rcx]
0x18002a33c  mov     rax, [rax+0C0h]
0x18002a343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a348  test    eax, eax
0x18002a34a  js      short loc_18002A3C4
0x18002a34c  test    byte ptr [rbp+37h+var_98], 1
0x18002a350  jz      short loc_18002A3C4
0x18002a352  mov     rcx, [r14+8]
0x18002a356  lea     r8, [rbp+37h+pvar]
0x18002a35a  xorps   xmm0, xmm0
0x18002a35d  lea     rdx, [rbp+37h+var_58]
0x18002a361  xor     eax, eax
0x18002a363  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18002a367  mov     [rbp+37h+var_60], rax
0x18002a36b  call    cs:__imp_PSGetCanonicalValue
0x18002a371  mov     [rbp+37h+var_88], eax
0x18002a374  test    eax, eax
0x18002a376  js      short loc_18002A3C4
0x18002a378  mov     [rsp+0F0h+var_B0], rbx; int *
0x18002a37d  lea     rax, [rbp+37h+var_78]
0x18002a381  mov     [rsp+0F0h+var_B8], rax; int *
0x18002a386  lea     r9, [rbp+37h+var_58]; struct _tagpropertykey *
0x18002a38a  mov     [rsp+0F0h+var_C0], ebx; int
0x18002a38e  lea     r8, [rbp+37h+pvar]; struct tagPROPVARIANT *
0x18002a392  mov     [rsp+0F0h+var_C8], r15; struct ICondition *
0x18002a397  mov     rdx, rsi; struct tagPROPVARIANT *
0x18002a39a  mov     rcx, r14; this
0x18002a39d  mov     dword ptr [rsp+0F0h+ppv], r13d; tagCONDITION_OPERATION
0x18002a3a2  call    ?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z; CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)
0x18002a3a7  mov     [rbp+37h+var_88], eax
0x18002a3aa  test    eax, eax
0x18002a3ac  jns     loc_18002A823
0x18002a3b2  cmp     eax, edi
0x18002a3b4  cmovnz  eax, ebx
0x18002a3b7  mov     [rbp+37h+var_88], eax
0x18002a3ba  lea     rcx, [rbp+37h+pvar]; pvar
0x18002a3be  call    cs:__imp_PropVariantClear
0x18002a3c4  mov     rcx, [rbp+37h+var_90]
0x18002a3c8  mov     rax, [rcx]
0x18002a3cb  mov     rax, [rax+10h]
0x18002a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3d4  mov     eax, [rbp+37h+var_88]
0x18002a3d7  mov     edx, dword ptr [rbp+37h+var_A0]
0x18002a3da  inc     edx
0x18002a3dc  mov     dword ptr [rbp+37h+var_A0], edx
0x18002a3df  test    eax, eax
0x18002a3e1  jns     loc_18002A2D0
0x18002a3e7  mov     edi, [rbp+37h+var_88]
0x18002a3ea  mov     r8d, 1
0x18002a3f0  lea     rdx, aFtsearched; "FTSearched"
0x18002a3f7  mov     rcx, r15
0x18002a3fa  call    SetEvalStateEx
0x18002a3ff  jmp     loc_18002A1D5
0x18002a404  mov     rcx, [r8]
0x18002a407  sub     rcx, qword ptr cs:PKEY_ForceFullText
0x18002a40e  jnz     short loc_18002A41B
0x18002a410  mov     rcx, [r8+8]
0x18002a414  sub     rcx, qword ptr cs:PKEY_ForceFullText+8
0x18002a41b  test    rcx, rcx
0x18002a41e  jnz     loc_18002A003
0x18002a424  jmp     loc_18002A24D
0x18002a429  mov     rcx, [r8]
0x18002a42c  sub     rcx, qword ptr cs:PKEY_Generic_String
0x18002a433  jnz     short loc_18002A440
0x18002a435  mov     rcx, [r8+8]
0x18002a439  sub     rcx, qword ptr cs:PKEY_Generic_String+8
0x18002a440  test    rcx, rcx
0x18002a443  jnz     loc_18002A003
0x18002a449  jmp     loc_18002A24D
  ... truncated ...
```
