# CConditionEvaluator::_DoesItemMatchConditionWorker(ICondition *,int,TRIBIT *,int *)

- ea: `0x180026c80`
- end: `0x1800275cd`
- name: `?_DoesItemMatchConditionWorker@CConditionEvaluator@@AEAAJPEAUICondition@@HPEAW4TRIBIT@@PEAH@Z`
- size: `2381`
- prototype: `__int64 __fastcall(CConditionEvaluator *__hidden this, struct ICondition *, int, enum TRIBIT *, LPVOID)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024c40`
- `0x180025eb0`
- `0x1800261e0`
- `0x180026820`
- `0x180026bc0`
- `0x180026c80`

## callees

- `0x180025eb0`
- `0x180026820`
- `0x180026c80`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027105`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027105`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026e7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002733b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800274c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026e7b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026f83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002733b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800274c7`
- `PROPSYS!PropVariantToInt32` at `0x1800274b4`
- `PROPSYS!PropVariantToInt32` at `0x1800274b4`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::_DoesItemMatchConditionWorker(
        CConditionEvaluator *this,
        struct ICondition *a2,
        int a3,
        enum TRIBIT *a4,
        LONG *a5)
{
  LONG v5; // r13d
  struct IConditionVtbl *v10; // rax
  int DoesItemMatchConditionWorker; // ebx
  struct IConditionVtbl *v12; // rax
  LONG v13; // eax
  int v14; // ecx
  struct IConditionVtbl *v15; // rax
  int v16; // r14d
  struct IConditionVtbl *v17; // rax
  HRESULT (__stdcall *QueryInterface)(ICondition *, const IID *const, void **); // rax
  int v20; // edi
  struct ICondition **v21; // rcx
  struct IConditionVtbl *v22; // rax
  struct IConditionVtbl *v23; // rax
  int v24; // edi
  LONG *v25; // rax
  LONG v26; // eax
  int v27; // eax
  int v28; // ecx
  struct IConditionVtbl *v29; // rax
  int v30; // edi
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT v32; // ebx
  LONG plRet[2]; // [rsp+50h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-69h] BYREF
  struct ICondition *v35; // [rsp+60h] [rbp-61h] BYREF
  struct ICondition *v36; // [rsp+68h] [rbp-59h] BYREF
  int v37; // [rsp+70h] [rbp-51h] BYREF
  __int64 v38; // [rsp+78h] [rbp-49h] BYREF
  __int64 v39; // [rsp+80h] [rbp-41h] BYREF
  __int64 v40; // [rsp+88h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-21h]
  int v43; // [rsp+A8h] [rbp-19h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-11h] BYREF
  int v45; // [rsp+C0h] [rbp-1h]

  v5 = 0;
  if ( *((_DWORD *)this + 17) )
  {
    lpVtbl = a2->lpVtbl;
    v36 = 0;
    if ( ((int (__fastcall *)(struct ICondition *, GUID *, struct ICondition **))lpVtbl->QueryInterface)(
           a2,
           &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
           &v36) >= 0 )
    {
      ppv = 0;
      v32 = ((__int64 (__fastcall *)(struct ICondition *, __int64 *, GUID *, LPVOID *))v36->lpVtbl->IsDirty)(
              v36,
              qword_1800F7E38,
              &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
              &ppv);
      if ( v32 >= 0 )
      {
        v35 = 0;
        v32 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, struct ICondition **))(*(_QWORD *)ppv + 24LL))(
                ppv,
                &OID_PropertyStore,
                &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                &v35);
        if ( v32 >= 0 )
        {
          v42 = 0;
          *(_OWORD *)pvar = 0;
          v32 = ((__int64 (__fastcall *)(struct ICondition *, const wchar_t *, PROPVARIANT *))v35->lpVtbl->GetClassID)(
                  v35,
                  L"ES",
                  pvar);
          if ( v32 >= 0 )
          {
            plRet[0] = 0;
            v32 = PropVariantToInt32(pvar, plRet);
            if ( v32 >= 0 )
              v5 = plRet[0];
            PropVariantClear(pvar);
          }
          ((void (__fastcall *)(struct ICondition *))v35->lpVtbl->Release)(v35);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ((void (__fastcall *)(struct ICondition *))v36->lpVtbl->Release)(v36);
      if ( v32 >= 0 && v5 )
      {
        DoesItemMatchConditionWorker = 0;
        *(_DWORD *)a4 = v5;
        return (unsigned int)DoesItemMatchConditionWorker;
      }
      v5 = 0;
    }
  }
  v10 = a2->lpVtbl;
  v43 = 0;
  DoesItemMatchConditionWorker = ((__int64 (__fastcall *)(struct ICondition *, int *))v10->GetConditionType)(a2, &v43);
  if ( DoesItemMatchConditionWorker >= 0 )
  {
    if ( v43 == 3 )
    {
      if ( a5 )
        *a5 = 0;
      plRet[0] = 0;
      v45 = 0;
      v42 = 0;
      v17 = a2->lpVtbl;
      v40 = 0;
      v44 = 0;
      QueryInterface = v17->QueryInterface;
      *(_OWORD *)pvar = 0;
      DoesItemMatchConditionWorker = ((__int64 (__fastcall *)(struct ICondition *, GUID *, __int64 *))QueryInterface)(
                                       a2,
                                       &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                       &v40);
      if ( DoesItemMatchConditionWorker >= 0 )
      {
        DoesItemMatchConditionWorker = (*(__int64 (__fastcall **)(__int64, __int128 *, LONG *, PROPVARIANT *))(*(_QWORD *)v40 + 128LL))(
                                         v40,
                                         &v44,
                                         plRet,
                                         pvar);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        if ( DoesItemMatchConditionWorker >= 0 )
        {
          DoesItemMatchConditionWorker = (*(__int64 (__fastcall **)(CConditionEvaluator *, PROPVARIANT *, __int128 *, _QWORD, struct ICondition *, int, enum TRIBIT *, LONG *))(*(_QWORD *)this + 16LL))(
                                           this,
                                           pvar,
                                           &v44,
                                           (unsigned int)plRet[0],
                                           a2,
                                           a3,
                                           a4,
                                           a5);
          PropVariantClear(pvar);
        }
      }
    }
    else if ( v43 )
    {
      if ( v43 == 1 )
      {
        if ( a3 )
        {
          return (unsigned int)CConditionEvaluator::_DoesItemMatchAnd(this, a2, a3, a4, a5);
        }
        else
        {
          if ( a5 )
            *a5 = 0;
          v23 = a2->lpVtbl;
          v38 = 0;
          DoesItemMatchConditionWorker = ((__int64 (__fastcall *)(struct ICondition *, GUID *, __int64 *))v23->GetSubConditions)(
                                           a2,
                                           &GUID_00000100_0000_0000_c000_000000000046,
                                           &v38);
          if ( DoesItemMatchConditionWorker >= 0 )
          {
            plRet[0] = 0;
            v36 = 0;
            v37 = 2;
            while ( DoesItemMatchConditionWorker >= 0 )
            {
              v36 = 0;
              v35 = 0;
              LODWORD(ppv) = 0;
              if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct ICondition **, LPVOID *))(*(_QWORD *)v38 + 24LL))(
                     v38,
                     1,
                     &v35,
                     &ppv)
                || (v24 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, struct ICondition **))v35->lpVtbl->QueryInterface)(
                            v35,
                            &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                            &v36),
                    ((void (__fastcall *)(struct ICondition *))v35->lpVtbl->Release)(v35),
                    v24 < 0) )
              {
                v27 = v37;
LABEL_63:
                if ( v27 == 1 )
                {
                  v28 = 1;
                }
                else
                {
                  v28 = 2;
                  if ( plRet[0] )
                    v28 = 0;
                }
                *(_DWORD *)a4 = v28;
                break;
              }
              if ( !a5 || *a5 )
                v25 = 0;
              else
                v25 = a5;
              DoesItemMatchConditionWorker = CConditionEvaluator::_DoesItemMatchConditionWorker(
                                               this,
                                               v36,
                                               0,
                                               (enum TRIBIT *)&v37,
                                               v25);
              v26 = plRet[0];
              if ( !v37 )
                v26 = 1;
              plRet[0] = v26;
              ((void (*)(void))v36->lpVtbl->Release)();
              v27 = v37;
              if ( v37 == 1 )
              {
                if ( DoesItemMatchConditionWorker < 0 )
                  break;
                goto LABEL_63;
              }
            }
            v29 = a2->lpVtbl;
            v30 = *(_DWORD *)a4;
            *(_QWORD *)plRet = 0;
            if ( ((int (__fastcall *)(struct ICondition *, GUID *, LONG *))v29->QueryInterface)(
                   a2,
                   &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
                   plRet) >= 0 )
            {
              ppv = 0;
              if ( (*(int (__fastcall **)(_QWORD, __int64 *, GUID *, LPVOID *))(**(_QWORD **)plRet + 32LL))(
                     *(_QWORD *)plRet,
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
                v39 = 0;
                if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                       ppv,
                       &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                       &v39) >= 0 )
                {
                  v35 = 0;
                  if ( (*(int (__fastcall **)(__int64, __int64 *, GUID *, struct ICondition **))(*(_QWORD *)v39 + 24LL))(
                         v39,
                         &OID_PropertyStore,
                         &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                         &v35) >= 0 )
                  {
                    v42 = 0;
                    *(_OWORD *)pvar = 0;
                    LODWORD(pvar[1]) = v30;
                    LOWORD(pvar[0]) = 3;
                    if ( ((int (__fastcall *)(struct ICondition *, const wchar_t *, PROPVARIANT *))v35->lpVtbl->IsDirty)(
                           v35,
                           L"ES",
                           pvar) >= 0 )
                      (*(void (__fastcall **)(_QWORD, __int64 *, LPVOID))(**(_QWORD **)plRet + 24LL))(
                        *(_QWORD *)plRet,
                        qword_1800F7E38,
                        ppv);
                    PropVariantClear(pvar);
                    ((void (__fastcall *)(struct ICondition *))v35->lpVtbl->Release)(v35);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              }
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plRet + 16LL))(*(_QWORD *)plRet);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
        }
      }
      else if ( v43 == 2 )
      {
        v22 = a2->lpVtbl;
        v35 = 0;
        DoesItemMatchConditionWorker = ((__int64 (__fastcall *)(struct ICondition *, GUID *, struct ICondition **))v22->GetSubConditions)(
                                         a2,
                                         &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                         &v35);
        if ( DoesItemMatchConditionWorker >= 0 )
        {
          DoesItemMatchConditionWorker = CConditionEvaluator::_DoesItemMatchConditionWorker(this, v35, a3 == 0, a4, a5);
          ((void (__fastcall *)(struct ICondition *))v35->lpVtbl->Release)(v35);
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
    else if ( a3 )
    {
      return (unsigned int)CConditionEvaluator::_DoesItemMatchOr(this, a2, a3, a4, a5);
    }
    else
    {
      if ( a5 )
        *a5 = 0;
      v12 = a2->lpVtbl;
      v40 = 0;
      DoesItemMatchConditionWorker = ((__int64 (__fastcall *)(struct ICondition *, GUID *, __int64 *))v12->GetSubConditions)(
                                       a2,
                                       &GUID_00000100_0000_0000_c000_000000000046,
                                       &v40);
      if ( DoesItemMatchConditionWorker >= 0 )
      {
        LODWORD(ppv) = 0;
        v35 = 0;
        v13 = 1;
        plRet[0] = 1;
        LOBYTE(v5) = a5 != 0;
        while ( v13 != 2 || v5 )
        {
          if ( DoesItemMatchConditionWorker < 0 )
            goto LABEL_16;
          v35 = 0;
          v38 = 0;
          LODWORD(v36) = 0;
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, struct ICondition **))(*(_QWORD *)v40 + 24LL))(
                 v40,
                 1,
                 &v38,
                 &v36)
            || (v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICondition **))v38)(
                        v38,
                        &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                        &v35),
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38),
                v20 < 0) )
          {
            v13 = plRet[0];
            goto LABEL_13;
          }
          v21 = &v36;
          LODWORD(v36) = 0;
          v37 = 0;
          if ( !v5 )
            v21 = 0;
          DoesItemMatchConditionWorker = CConditionEvaluator::_DoesItemMatchConditionWorker(
                                           this,
                                           v35,
                                           0,
                                           (enum TRIBIT *)&v37,
                                           v21);
          if ( DoesItemMatchConditionWorker >= 0 )
          {
            if ( v37 )
            {
              if ( v37 == 2 )
                plRet[0] = 2;
              else
                v5 = v5 && (v37 == 1 || (_DWORD)v36);
            }
            else
            {
              LODWORD(ppv) = 1;
            }
          }
          ((void (__fastcall *)(struct ICondition *))v35->lpVtbl->Release)(v35);
          v13 = plRet[0];
        }
        if ( DoesItemMatchConditionWorker < 0 )
          goto LABEL_16;
LABEL_13:
        if ( v13 == 2 )
          v14 = 2;
        else
          v14 = (_DWORD)ppv == 0;
        *(_DWORD *)a4 = v14;
        if ( a5 && v13 == 2 )
          *a5 = v5;
LABEL_16:
        v15 = a2->lpVtbl;
        v16 = *(_DWORD *)a4;
        v36 = 0;
        if ( ((int (__fastcall *)(struct ICondition *, GUID *, struct ICondition **))v15->QueryInterface)(
               a2,
               &GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43,
               &v36) >= 0 )
        {
          ppv = 0;
          if ( ((int (__fastcall *)(struct ICondition *, __int64 *, GUID *, LPVOID *))v36->lpVtbl->IsDirty)(
                 v36,
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
            v39 = 0;
            if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                   ppv,
                   &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a,
                   &v39) >= 0 )
            {
              v38 = 0;
              if ( (*(int (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v39 + 24LL))(
                     v39,
                     &OID_PropertyStore,
                     &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                     &v38) >= 0 )
              {
                v42 = 0;
                *(_OWORD *)pvar = 0;
                LODWORD(pvar[1]) = v16;
                LOWORD(pvar[0]) = 3;
                if ( (*(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v38 + 32LL))(
                       v38,
                       L"ES",
                       pvar) >= 0 )
                  ((void (__fastcall *)(struct ICondition *, __int64 *, LPVOID))v36->lpVtbl->GetClassID)(
                    v36,
                    qword_1800F7E38,
                    ppv);
                PropVariantClear(pvar);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          ((void (__fastcall *)(struct ICondition *))v36->lpVtbl->Release)(v36);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      }
    }
  }
  return (unsigned int)DoesItemMatchConditionWorker;
}

```

## disassembly

```asm
0x180026c80  push    rbp
0x180026c82  push    rbx
0x180026c83  push    rsi
0x180026c84  push    rdi
0x180026c85  push    r12
0x180026c87  push    r13
0x180026c89  push    r14
0x180026c8b  push    r15
0x180026c8d  lea     rbp, [rsp-17h]
0x180026c92  sub     rsp, 0D8h
0x180026c99  mov     rax, cs:__security_cookie
0x180026ca0  xor     rax, rsp
0x180026ca3  mov     [rbp+4Fh+var_48], rax
0x180026ca7  mov     r15, [rbp+4Fh+arg_20]
0x180026cab  xor     r13d, r13d
0x180026cae  mov     r12, r9
0x180026cb1  mov     edi, r8d
0x180026cb4  mov     rsi, rdx
0x180026cb7  mov     r14, rcx
0x180026cba  cmp     [rcx+44h], r13d
0x180026cbe  jnz     loc_1800273F9
0x180026cc4  mov     rax, [rsi]
0x180026cc7  lea     rdx, [rbp+4Fh+var_68]
0x180026ccb  mov     rcx, rsi
0x180026cce  mov     [rbp+4Fh+var_68], r13d
0x180026cd2  mov     rax, [rax+40h]
0x180026cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cdb  mov     ebx, eax
0x180026cdd  test    eax, eax
0x180026cdf  js      loc_180026F89
0x180026ce5  mov     ecx, [rbp+4Fh+var_68]
0x180026ce8  cmp     ecx, 3
0x180026ceb  jz      loc_180026ED6
0x180026cf1  test    ecx, ecx
0x180026cf3  jnz     loc_18002707B
0x180026cf9  test    edi, edi
0x180026cfb  jnz     loc_180027567
0x180026d01  test    r15, r15
0x180026d04  jnz     loc_180027584
0x180026d0a  mov     rax, [rsi]
0x180026d0d  lea     r8, [rbp+4Fh+var_88]
0x180026d11  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x180026d18  mov     [rbp+4Fh+var_88], r13
0x180026d1c  mov     rcx, rsi
0x180026d1f  mov     rax, [rax+48h]
0x180026d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d28  mov     ebx, eax
0x180026d2a  test    eax, eax
0x180026d2c  js      loc_180026F89
0x180026d32  mov     edi, 1
0x180026d37  mov     dword ptr [rbp+4Fh+var_B8], r13d
0x180026d3b  test    r15, r15
0x180026d3e  mov     [rbp+4Fh+var_B0], r13
0x180026d42  mov     eax, edi
0x180026d44  mov     [rbp+4Fh+plRet], eax
0x180026d47  setnz   r13b
0x180026d4b  cmp     eax, 2
0x180026d4e  jnz     loc_180026FAB
0x180026d54  test    r13d, r13d
0x180026d57  jnz     loc_180026FAB
0x180026d5d  test    ebx, ebx
0x180026d5f  js      short loc_180026D79
0x180026d61  cmp     eax, 2
0x180026d64  jnz     loc_1800273EC
0x180026d6a  mov     ecx, eax
0x180026d6c  mov     [r12], ecx
0x180026d70  test    r15, r15
0x180026d73  jnz     loc_1800275B4
0x180026d79  mov     rax, [rsi]
0x180026d7c  lea     r8, [rbp+4Fh+var_A8]
0x180026d80  mov     r14d, [r12]
0x180026d84  lea     rdx, _GUID_dbc3cbf5_4131_4730_a738_0684ebfeae43
0x180026d8b  xor     r15d, r15d
0x180026d8e  mov     rcx, rsi
0x180026d91  mov     [rbp+4Fh+var_A8], r15
0x180026d95  mov     rax, [rax]
0x180026d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d9d  test    eax, eax
0x180026d9f  js      loc_180026EC1
0x180026da5  mov     rcx, [rbp+4Fh+var_A8]
0x180026da9  lea     r9, [rbp+4Fh+var_B8]
0x180026dad  mov     [rbp+4Fh+var_B8], r15
0x180026db1  lea     r8, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a
0x180026db8  lea     rdx, qword_1800F7E38
0x180026dbf  mov     rax, [rcx]
0x180026dc2  mov     rax, [rax+20h]
0x180026dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dcb  test    eax, eax
0x180026dcd  js      loc_1800270E9
0x180026dd3  mov     rcx, [rbp+4Fh+var_B8]
0x180026dd7  lea     r8, [rbp+4Fh+var_90]
0x180026ddb  mov     [rbp+4Fh+var_90], r15
0x180026ddf  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x180026de6  mov     rax, [rcx]
0x180026de9  mov     rax, [rax]
0x180026dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026df1  test    eax, eax
0x180026df3  js      loc_180026EA1
0x180026df9  mov     rcx, [rbp+4Fh+var_90]
0x180026dfd  lea     r9, [rbp+4Fh+var_98]
0x180026e01  mov     [rbp+4Fh+var_98], r15
0x180026e05  lea     r8, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x180026e0c  lea     rdx, OID_PropertyStore
0x180026e13  mov     rax, [rcx]
0x180026e16  mov     rax, [rax+18h]
0x180026e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e1f  test    eax, eax
0x180026e21  js      short loc_180026E91
0x180026e23  mov     rcx, [rbp+4Fh+var_98]
0x180026e27  lea     r8, [rbp+4Fh+pvar]
0x180026e2b  xor     eax, eax
0x180026e2d  lea     rdx, aEs; "ES"
0x180026e34  mov     [rbp+4Fh+var_70], rax
0x180026e38  xorps   xmm0, xmm0
0x180026e3b  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180026e3f  mov     eax, 3
0x180026e44  mov     dword ptr [rbp+4Fh+pvar+8], r14d
0x180026e48  mov     word ptr [rbp+4Fh+pvar], ax
0x180026e4c  mov     rax, [rcx]
0x180026e4f  mov     rax, [rax+20h]
0x180026e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e58  test    eax, eax
0x180026e5a  js      short loc_180026E77
0x180026e5c  mov     rcx, [rbp+4Fh+var_A8]
0x180026e60  lea     rdx, qword_1800F7E38
0x180026e67  mov     r8, [rbp+4Fh+var_B8]
0x180026e6b  mov     rax, [rcx]
0x180026e6e  mov     rax, [rax+18h]
0x180026e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e77  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180026e7b  call    cs:__imp_PropVariantClear
0x180026e81  mov     rcx, [rbp+4Fh+var_98]
0x180026e85  mov     rax, [rcx]
0x180026e88  mov     rax, [rax+10h]
0x180026e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e91  mov     rcx, [rbp+4Fh+var_90]
0x180026e95  mov     rax, [rcx]
0x180026e98  mov     rax, [rax+10h]
0x180026e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea1  mov     rcx, [rbp+4Fh+var_B8]
0x180026ea5  mov     rax, [rcx]
0x180026ea8  mov     rax, [rax+10h]
0x180026eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026eb1  mov     rcx, [rbp+4Fh+var_A8]
0x180026eb5  mov     rax, [rcx]
0x180026eb8  mov     rax, [rax+10h]
0x180026ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ec1  mov     rcx, [rbp+4Fh+var_88]
0x180026ec5  mov     rax, [rcx]
0x180026ec8  mov     rax, [rax+10h]
0x180026ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ed1  jmp     loc_180026F89
0x180026ed6  test    r15, r15
0x180026ed9  jnz     loc_1800275C5
0x180026edf  xor     eax, eax
0x180026ee1  mov     [rbp+4Fh+plRet], r13d
0x180026ee5  mov     [rbp+4Fh+var_50], eax
0x180026ee8  lea     r8, [rbp+4Fh+var_88]
0x180026eec  mov     [rbp+4Fh+var_70], rax
0x180026ef0  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180026ef7  mov     rax, [rsi]
0x180026efa  xorps   xmm0, xmm0
0x180026efd  mov     rcx, rsi
0x180026f00  mov     [rbp+4Fh+var_88], r13
0x180026f04  movups  [rbp+4Fh+var_60], xmm0
0x180026f08  mov     rax, [rax]
0x180026f0b  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180026f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f14  mov     ebx, eax
0x180026f16  test    eax, eax
0x180026f18  js      short loc_180026F89
0x180026f1a  mov     rcx, [rbp+4Fh+var_88]
0x180026f1e  lea     r9, [rbp+4Fh+pvar]
0x180026f22  lea     r8, [rbp+4Fh+plRet]
0x180026f26  lea     rdx, [rbp+4Fh+var_60]
0x180026f2a  mov     rax, [rcx]
0x180026f2d  mov     rax, [rax+80h]
0x180026f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f39  mov     rcx, [rbp+4Fh+var_88]
0x180026f3d  mov     ebx, eax
0x180026f3f  mov     rax, [rcx]
0x180026f42  mov     rax, [rax+10h]
0x180026f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f4b  test    ebx, ebx
0x180026f4d  js      short loc_180026F89
0x180026f4f  mov     rax, [r14]
0x180026f52  lea     r8, [rbp+4Fh+var_60]
0x180026f56  mov     r9d, [rbp+4Fh+plRet]
0x180026f5a  lea     rdx, [rbp+4Fh+pvar]
0x180026f5e  mov     [rsp+110h+var_D8], r15
0x180026f63  mov     rcx, r14
0x180026f66  mov     [rsp+110h+var_E0], r12
0x180026f6b  mov     rax, [rax+10h]
0x180026f6f  mov     [rsp+110h+var_E8], edi
0x180026f73  mov     [rsp+110h+ppv], rsi
0x180026f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f7d  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180026f81  mov     ebx, eax
0x180026f83  call    cs:__imp_PropVariantClear
0x180026f89  mov     eax, ebx
0x180026f8b  mov     rcx, [rbp+4Fh+var_48]
0x180026f8f  xor     rcx, rsp; StackCookie
0x180026f92  call    __security_check_cookie
0x180026f97  add     rsp, 0D8h
0x180026f9e  pop     r15
0x180026fa0  pop     r14
0x180026fa2  pop     r13
0x180026fa4  pop     r12
0x180026fa6  pop     rdi
0x180026fa7  pop     rsi
0x180026fa8  pop     rbx
0x180026fa9  pop     rbp
0x180026faa  retn
0x180026fab  test    ebx, ebx
0x180026fad  js      loc_180026D79
0x180026fb3  mov     rcx, [rbp+4Fh+var_88]
0x180026fb7  lea     r9, [rbp+4Fh+var_A8]
0x180026fbb  xor     eax, eax
0x180026fbd  lea     r8, [rbp+4Fh+var_98]
0x180026fc1  mov     [rbp+4Fh+var_B0], rax
0x180026fc5  mov     edx, edi
0x180026fc7  mov     [rbp+4Fh+var_98], rax
0x180026fcb  mov     dword ptr [rbp+4Fh+var_A8], eax
0x180026fce  mov     rax, [rcx]
0x180026fd1  mov     rax, [rax+18h]
0x180026fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fda  test    eax, eax
0x180026fdc  jnz     loc_1800275AC
0x180026fe2  mov     rcx, [rbp+4Fh+var_98]
0x180026fe6  lea     r8, [rbp+4Fh+var_B0]
0x180026fea  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180026ff1  mov     rax, [rcx]
0x180026ff4  mov     rax, [rax]
0x180026ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ffc  mov     rcx, [rbp+4Fh+var_98]
0x180027000  mov     edi, eax
0x180027002  mov     rdx, [rcx]
0x180027005  mov     rax, [rdx+10h]
0x180027009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002700e  test    edi, edi
0x180027010  js      loc_1800275A7
0x180027016  mov     rdx, [rbp+4Fh+var_B0]; struct ICondition *
0x18002701a  lea     rcx, [rbp+4Fh+var_A8]
0x18002701e  xor     edi, edi
0x180027020  lea     r9, [rbp+4Fh+var_A0]; enum TRIBIT *
0x180027024  test    r13d, r13d
0x180027027  mov     dword ptr [rbp+4Fh+var_A8], edi
0x18002702a  mov     [rbp+4Fh+var_A0], edi
0x18002702d  cmovz   rcx, rdi
0x180027031  xor     r8d, r8d; int
0x180027034  mov     [rsp+110h+ppv], rcx; LPVOID
0x180027039  mov     rcx, r14; this
0x18002703c  call    ?_DoesItemMatchConditionWorker@CConditionEvaluator@@AEAAJPEAUICondition@@HPEAW4TRIBIT@@PEAH@Z; CConditionEvaluator::_DoesItemMatchConditionWorker(ICondition *,int,TRIBIT *,int *)
0x180027041  mov     ebx, eax
0x180027043  test    eax, eax
0x180027045  js      short loc_18002705E
0x180027047  mov     eax, [rbp+4Fh+var_A0]
0x18002704a  test    eax, eax
0x18002704c  jz      loc_180027511
0x180027052  cmp     eax, 2
0x180027055  jnz     loc_180027396
0x18002705b  mov     [rbp+4Fh+plRet], eax
0x18002705e  mov     edi, 1
0x180027063  mov     rcx, [rbp+4Fh+var_B0]
0x180027067  mov     rax, [rcx]
0x18002706a  mov     rax, [rax+10h]
0x18002706e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027073  mov     eax, [rbp+4Fh+plRet]
0x180027076  jmp     loc_180026D4B
0x18002707b  sub     ecx, 1
0x18002707e  jz      loc_180027118
0x180027084  cmp     ecx, 1
0x180027087  jnz     loc_180027543
0x18002708d  mov     rax, [rsi]
0x180027090  lea     r8, [rbp+4Fh+var_B0]
0x180027094  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18002709b  mov     [rbp+4Fh+var_B0], r13
0x18002709f  mov     rcx, rsi
0x1800270a2  mov     rax, [rax+48h]
0x1800270a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ab  mov     ebx, eax
0x1800270ad  test    eax, eax
0x1800270af  js      loc_180026F89
0x1800270b5  mov     rdx, [rbp+4Fh+var_B0]; struct ICondition *
0x1800270b9  mov     r8d, r13d
0x1800270bc  test    edi, edi
0x1800270be  mov     [rsp+110h+ppv], r15; LPVOID
0x1800270c3  mov     r9, r12; enum TRIBIT *
0x1800270c6  mov     rcx, r14; this
0x1800270c9  setz    r8b; int
0x1800270cd  call    ?_DoesItemMatchConditionWorker@CConditionEvaluator@@AEAAJPEAUICondition@@HPEAW4TRIBIT@@PEAH@Z; CConditionEvaluator::_DoesItemMatchConditionWorker(ICondition *,int,TRIBIT *,int *)
0x1800270d2  mov     rcx, [rbp+4Fh+var_B0]
0x1800270d6  mov     ebx, eax
0x1800270d8  mov     rax, [rcx]
0x1800270db  mov     rax, [rax+10h]
0x1800270df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270e4  jmp     loc_180026F89
0x1800270e9  lea     rax, [rbp+4Fh+var_B8]
0x1800270ed  mov     r8d, edi; dwClsContext
0x1800270f0  lea     r9, _GUID_522e34a4_07f7_40a1_94d0_1bfe832efc3a; riid
  ... truncated ...
```
