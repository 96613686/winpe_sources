# StructuredQuery1::QueryParser::SameProperty(ICondition *,wchar_t * &,IRichChunk * &,unsigned __int64 &,bool,bool *)

- ea: `0x18002eebc`
- end: `0x18002f290`
- name: `?SameProperty@QueryParser@StructuredQuery1@@AEBAJPEAUICondition@@AEAPEA_WAEAPEAUIRichChunk@@AEA_K_NPEA_N@Z`
- size: `980`
- prototype: `__int64 __fastcall(StructuredQuery1::QueryParser *__hidden this, struct ICondition *, wchar_t **, struct IRichChunk **, unsigned __int64 *, bool, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ce3c`
- `0x18002eebc`
- `0x1800696c0`

## callees

- `0x180015a40`
- `0x18002eebc`
- `0x18002f298`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f039`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f11a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f11a`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::SameProperty(
        StructuredQuery1::QueryParser *this,
        struct ICondition *a2,
        wchar_t **a3,
        struct IRichChunk **a4,
        unsigned __int64 *a5,
        bool a6,
        bool *a7)
{
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetConditionType)(ICondition *, CONDITION_TYPE *); // rax
  int v13; // ebx
  struct IConditionVtbl *v14; // rax
  bool IsDefaultPropertyName; // al
  const size_t *v16; // rsi
  bool v17; // r14
  __int64 v18; // r10
  unsigned __int64 *v19; // rcx
  const WCHAR *lpString2; // rax
  bool v22; // di
  struct IRichChunk *v23; // rcx
  bool v24; // zf
  struct IConditionVtbl *v25; // rax
  int v26; // eax
  LPVOID v27; // rcx
  struct IConditionVtbl *v28; // rax
  bool v29; // r14
  bool v30; // al
  unsigned __int64 *v31; // r13
  unsigned int v33; // [rsp+40h] [rbp-38h] BYREF
  int v34; // [rsp+44h] [rbp-34h] BYREF
  int v35; // [rsp+48h] [rbp-30h] BYREF
  int v36; // [rsp+4Ch] [rbp-2Ch] BYREF
  void *v37; // [rsp+50h] [rbp-28h] BYREF
  __int64 v38; // [rsp+58h] [rbp-20h] BYREF
  LPVOID pv[3]; // [rsp+60h] [rbp-18h] BYREF
  bool i; // [rsp+C8h] [rbp+50h] BYREF

  lpVtbl = a2->lpVtbl;
  i = 0;
  GetConditionType = lpVtbl->GetConditionType;
  v33 = 0;
  v13 = ((__int64 (__fastcall *)(struct ICondition *, unsigned int *))GetConditionType)(a2, &v33);
  if ( v13 >= 0 )
  {
    if ( v33 < 2 )
    {
      v28 = a2->lpVtbl;
      v37 = 0;
      v13 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, void **))v28->GetSubConditions)(
              a2,
              &GUID_00000100_0000_0000_c000_000000000046,
              &v37);
      if ( v13 < 0 )
        goto LABEL_52;
      v29 = a6;
      v30 = 1;
      v38 = 0;
      v31 = a5;
      for ( i = 1; v30; v30 = i )
      {
        v13 = (*(__int64 (__fastcall **)(void *, __int64, __int64 *, _QWORD))(*(_QWORD *)v37 + 24LL))(v37, 1, &v38, 0);
        if ( v13 )
          break;
        pv[0] = 0;
        v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v38)(
                v38,
                &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                pv);
        if ( v13 >= 0 )
        {
          v13 = StructuredQuery1::QueryParser::SameProperty(this, (struct ICondition *)pv[0], a3, a4, v31, v29, &i);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        if ( v13 < 0 )
          break;
      }
      v27 = v37;
    }
    else
    {
      if ( v33 != 2 )
      {
        if ( v33 != 3 )
        {
          v13 = -2147024809;
          goto LABEL_52;
        }
        v14 = a2->lpVtbl;
        pv[0] = 0;
        v13 = ((__int64 (__fastcall *)(struct ICondition *, LPVOID *, _QWORD, _QWORD))v14->GetComparisonInfo)(
                a2,
                pv,
                0,
                0);
        if ( v13 < 0 )
          goto LABEL_52;
        if ( !pv[0]
          || (IsDefaultPropertyName = StructuredQuery1::QueryParser::IsDefaultPropertyName(
                                        this,
                                        (const wchar_t *)pv[0],
                                        a2),
              v16 = 0,
              !IsDefaultPropertyName) )
        {
          v16 = (const size_t *)pv[0];
        }
        v17 = a6;
        v18 = 0;
        v38 = 0;
        if ( a6 )
        {
          v13 = ((__int64 (__fastcall *)(struct ICondition *, __int64 *, _QWORD, _QWORD))a2->lpVtbl->GetInputTerms)(
                  a2,
                  &v38,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_39;
          v18 = v38;
        }
        v19 = a5;
        if ( !(*a5)++ )
        {
          i = 1;
          if ( v16 )
          {
            v13 = _AllocString<CTCoAllocPolicy>((__int64)v19, 0, v16, a3);
            if ( v13 < 0 )
            {
LABEL_19:
              v18 = v38;
              goto LABEL_37;
            }
            v18 = v38;
          }
          if ( v18 )
          {
            v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IRichChunk **))v18)(
                    v18,
                    &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                    a4);
            goto LABEL_19;
          }
LABEL_39:
          CoTaskMemFree(pv[0]);
          goto LABEL_52;
        }
        lpString2 = *a3;
        if ( v16 )
        {
          if ( lpString2 )
          {
            if ( CompareStringW(0x7Fu, 0, (PCNZWCH)v16, -1, lpString2, -1) == 2 )
            {
              v22 = 1;
              i = 1;
              if ( !v17 )
                goto LABEL_19;
              v18 = v38;
              if ( v38 )
              {
                if ( *a4 )
                {
                  v35 = 0;
                  LODWORD(v37) = 0;
                  v13 = (*(__int64 (__fastcall **)(__int64, int *, void **, _QWORD, _QWORD))(*(_QWORD *)v38 + 24LL))(
                          v38,
                          &v35,
                          &v37,
                          0,
                          0);
                  if ( v13 >= 0 )
                  {
                    v23 = *a4;
                    v34 = 0;
                    v36 = 0;
                    v13 = ((__int64 (__fastcall *)(struct IRichChunk *, int *, int *, _QWORD, _QWORD))v23->lpVtbl->GetData)(
                            v23,
                            &v34,
                            &v36,
                            0,
                            0);
                    if ( v13 >= 0 )
                    {
                      if ( v35 != v34 || (_DWORD)v37 != v36 )
                        v22 = 0;
                      i = v22;
                    }
                  }
                  goto LABEL_19;
                }
                goto LABEL_34;
              }
              v24 = *a4 == 0;
LABEL_36:
              i = v24;
LABEL_37:
              if ( v18 )
              {
                v38 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              }
              goto LABEL_39;
            }
            v18 = v38;
          }
LABEL_34:
          i = 0;
          goto LABEL_37;
        }
        v24 = lpString2 == 0;
        goto LABEL_36;
      }
      v25 = a2->lpVtbl;
      pv[0] = 0;
      v13 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, LPVOID *))v25->GetSubConditions)(
              a2,
              &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
              pv);
      if ( v13 < 0 )
        goto LABEL_52;
      v26 = StructuredQuery1::QueryParser::SameProperty(this, (struct ICondition *)pv[0], a3, a4, a5, a6, &i);
      v27 = pv[0];
      v13 = v26;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
LABEL_52:
  *a7 = i;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002eebc  push    rbp
0x18002eebe  push    rbx
0x18002eebf  push    rsi
0x18002eec0  push    rdi
0x18002eec1  push    r12
0x18002eec3  push    r13
0x18002eec5  push    r14
0x18002eec7  push    r15
0x18002eec9  mov     rbp, rsp
0x18002eecc  sub     rsp, 78h
0x18002eed0  mov     rax, [rdx]
0x18002eed3  mov     rdi, rdx
0x18002eed6  mov     rsi, rcx
0x18002eed9  lea     rdx, [rbp+var_38]
0x18002eedd  xor     r13d, r13d
0x18002eee0  mov     rcx, rdi
0x18002eee3  mov     r15, r9
0x18002eee6  mov     [rbp+arg_8], r13b
0x18002eeea  mov     rax, [rax+40h]
0x18002eeee  mov     r12, r8
0x18002eef1  mov     [rbp+var_38], r13d
0x18002eef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eefa  mov     ebx, eax
0x18002eefc  test    eax, eax
0x18002eefe  js      loc_18002F274
0x18002ef04  mov     ecx, [rbp+var_38]
0x18002ef07  test    ecx, ecx
0x18002ef09  jz      loc_18002F183
0x18002ef0f  sub     ecx, 1
0x18002ef12  jz      loc_18002F183
0x18002ef18  sub     ecx, 1
0x18002ef1b  jz      loc_18002F125
0x18002ef21  cmp     ecx, 1
0x18002ef24  jz      short loc_18002EF30
0x18002ef26  mov     ebx, 80070057h
0x18002ef2b  jmp     loc_18002F274
0x18002ef30  mov     rax, [rdi]
0x18002ef33  lea     rdx, [rbp+pv]
0x18002ef37  xor     r9d, r9d
0x18002ef3a  mov     [rbp+pv], r13
0x18002ef3e  xor     r8d, r8d
0x18002ef41  mov     rcx, rdi
0x18002ef44  mov     rax, [rax+50h]
0x18002ef48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef4d  mov     ebx, eax
0x18002ef4f  test    eax, eax
0x18002ef51  js      loc_18002F274
0x18002ef57  mov     rdx, [rbp+pv]; wchar_t *
0x18002ef5b  test    rdx, rdx
0x18002ef5e  jz      short loc_18002EF72
0x18002ef60  mov     r8, rdi; struct ICondition *
0x18002ef63  mov     rcx, rsi; this
0x18002ef66  call    ?IsDefaultPropertyName@QueryParser@StructuredQuery1@@AEBA_NPEB_WPEAUICondition@@@Z; StructuredQuery1::QueryParser::IsDefaultPropertyName(wchar_t const *,ICondition *)
0x18002ef6b  mov     rsi, r13
0x18002ef6e  test    al, al
0x18002ef70  jnz     short loc_18002EF76
0x18002ef72  mov     rsi, [rbp+pv]
0x18002ef76  mov     r14b, [rbp+arg_28]
0x18002ef7a  mov     r10, r13
0x18002ef7d  mov     [rbp+var_20], r13
0x18002ef81  test    r14b, r14b
0x18002ef84  jz      short loc_18002EFAD
0x18002ef86  mov     rax, [rdi]
0x18002ef89  lea     rdx, [rbp+var_20]
0x18002ef8d  xor     r9d, r9d
0x18002ef90  xor     r8d, r8d
0x18002ef93  mov     rcx, rdi
0x18002ef96  mov     rax, [rax+68h]
0x18002ef9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef9f  mov     ebx, eax
0x18002efa1  test    eax, eax
0x18002efa3  js      loc_18002F116
0x18002efa9  mov     r10, [rbp+var_20]
0x18002efad  mov     rcx, [rbp+arg_20]
0x18002efb1  mov     rdx, [rcx]
0x18002efb4  lea     rax, [rdx+1]
0x18002efb8  mov     [rcx], rax
0x18002efbb  test    rdx, rdx
0x18002efbe  jnz     short loc_18002F00D
0x18002efc0  lea     edi, [rdx+1]
0x18002efc3  mov     [rbp+arg_8], dil
0x18002efc7  test    rsi, rsi
0x18002efca  jz      short loc_18002EFE1
0x18002efcc  mov     r9, r12
0x18002efcf  mov     r8, rsi
0x18002efd2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18002efd7  mov     ebx, eax
0x18002efd9  test    eax, eax
0x18002efdb  js      short loc_18002F004
0x18002efdd  mov     r10, [rbp+var_20]
0x18002efe1  test    r10, r10
0x18002efe4  jz      loc_18002F116
0x18002efea  mov     rax, [r10]
0x18002efed  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18002eff4  mov     r8, r15
0x18002eff7  mov     rcx, r10
0x18002effa  mov     rax, [rax]
0x18002effd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f002  mov     ebx, eax
0x18002f004  mov     r10, [rbp+var_20]
0x18002f008  jmp     loc_18002F0FE
0x18002f00d  mov     rax, [r12]
0x18002f011  test    rsi, rsi
0x18002f014  jz      loc_18002F0F7
0x18002f01a  test    rax, rax
0x18002f01d  jz      loc_18002F0F1
0x18002f023  xor     edx, edx; dwCmpFlags
0x18002f025  or      r9d, 0FFFFFFFFh; cchCount1
0x18002f029  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x18002f02e  mov     r8, rsi; lpString1
0x18002f031  mov     [rsp+78h+lpString2], rax; lpString2
0x18002f036  lea     ecx, [rdx+7Fh]; Locale
0x18002f039  call    cs:__imp_CompareStringW
0x18002f03f  cmp     eax, 2
0x18002f042  jnz     loc_18002F0ED
0x18002f048  lea     edi, [rax-1]
0x18002f04b  mov     [rbp+arg_8], dil
0x18002f04f  test    r14b, r14b
0x18002f052  jz      short loc_18002F004
0x18002f054  mov     r10, [rbp+var_20]
0x18002f058  test    r10, r10
0x18002f05b  jz      loc_18002F0E8
0x18002f061  cmp     [r15], r13
0x18002f064  jz      loc_18002F0F1
0x18002f06a  mov     [rbp+var_30], r13d
0x18002f06e  lea     r8, [rbp+var_28]
0x18002f072  mov     dword ptr [rbp+var_28], r13d
0x18002f076  lea     rdx, [rbp+var_30]
0x18002f07a  mov     rax, [r10]
0x18002f07d  xor     r9d, r9d
0x18002f080  mov     rcx, r10
0x18002f083  mov     [rsp+78h+lpString2], r13
0x18002f088  mov     rax, [rax+18h]
0x18002f08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f091  mov     ebx, eax
0x18002f093  test    eax, eax
0x18002f095  js      loc_18002F004
0x18002f09b  mov     rcx, [r15]
0x18002f09e  lea     r8, [rbp+var_2C]
0x18002f0a2  mov     [rbp+var_34], r13d
0x18002f0a6  lea     rdx, [rbp+var_34]
0x18002f0aa  mov     [rbp+var_2C], r13d
0x18002f0ae  xor     r9d, r9d
0x18002f0b1  mov     [rsp+78h+lpString2], r13
0x18002f0b6  mov     rax, [rcx]
0x18002f0b9  mov     rax, [rax+18h]
0x18002f0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0c2  mov     ebx, eax
0x18002f0c4  test    eax, eax
0x18002f0c6  js      loc_18002F004
0x18002f0cc  mov     eax, [rbp+var_34]
0x18002f0cf  cmp     [rbp+var_30], eax
0x18002f0d2  jnz     short loc_18002F0DC
0x18002f0d4  mov     eax, [rbp+var_2C]
0x18002f0d7  cmp     dword ptr [rbp+var_28], eax
0x18002f0da  jz      short loc_18002F0DF
0x18002f0dc  mov     dil, r13b
0x18002f0df  mov     [rbp+arg_8], dil
0x18002f0e3  jmp     loc_18002F004
0x18002f0e8  cmp     [r15], r13
0x18002f0eb  jmp     short loc_18002F0FA
0x18002f0ed  mov     r10, [rbp+var_20]
0x18002f0f1  mov     [rbp+arg_8], r13b
0x18002f0f5  jmp     short loc_18002F0FE
0x18002f0f7  test    rax, rax
0x18002f0fa  setz    [rbp+arg_8]
0x18002f0fe  test    r10, r10
0x18002f101  jz      short loc_18002F116
0x18002f103  mov     [rbp+var_20], r13
0x18002f107  mov     rcx, r10
0x18002f10a  mov     rax, [r10]
0x18002f10d  mov     rax, [rax+10h]
0x18002f111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f116  mov     rcx, [rbp+pv]; pv
0x18002f11a  call    cs:__imp_CoTaskMemFree
0x18002f120  jmp     loc_18002F274
0x18002f125  mov     rax, [rdi]
0x18002f128  lea     r8, [rbp+pv]
0x18002f12c  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18002f133  mov     [rbp+pv], r13
0x18002f137  mov     rcx, rdi
0x18002f13a  mov     rax, [rax+48h]
0x18002f13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f143  mov     ebx, eax
0x18002f145  test    eax, eax
0x18002f147  js      loc_18002F274
0x18002f14d  mov     rdx, [rbp+pv]; struct ICondition *
0x18002f151  lea     rax, [rbp+arg_8]
0x18002f155  mov     [rsp+78h+var_48], rax; bool *
0x18002f15a  mov     r9, r15; struct IRichChunk **
0x18002f15d  mov     al, [rbp+arg_28]
0x18002f160  mov     r8, r12; wchar_t **
0x18002f163  mov     byte ptr [rsp+78h+cchCount2], al; bool
0x18002f167  mov     rcx, rsi; this
0x18002f16a  mov     rax, [rbp+arg_20]
0x18002f16e  mov     [rsp+78h+lpString2], rax; unsigned __int64 *
0x18002f173  call    ?SameProperty@QueryParser@StructuredQuery1@@AEBAJPEAUICondition@@AEAPEA_WAEAPEAUIRichChunk@@AEA_K_NPEA_N@Z; StructuredQuery1::QueryParser::SameProperty(ICondition *,wchar_t * &,IRichChunk * &,unsigned __int64 &,bool,bool *)
0x18002f178  mov     rcx, [rbp+pv]
0x18002f17c  mov     ebx, eax
0x18002f17e  jmp     loc_18002F268
0x18002f183  mov     rax, [rdi]
0x18002f186  lea     r8, [rbp+var_28]
0x18002f18a  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x18002f191  mov     [rbp+var_28], r13
0x18002f195  mov     rcx, rdi
0x18002f198  mov     rax, [rax+48h]
0x18002f19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1a1  mov     ebx, eax
0x18002f1a3  test    eax, eax
0x18002f1a5  js      loc_18002F274
0x18002f1ab  mov     r14b, [rbp+arg_28]
0x18002f1af  mov     edi, 1
0x18002f1b4  mov     al, dil
0x18002f1b7  mov     [rbp+var_20], r13
0x18002f1bb  mov     r13, [rbp+arg_20]
0x18002f1bf  mov     [rbp+arg_8], al
0x18002f1c2  test    al, al
0x18002f1c4  jz      loc_18002F264
0x18002f1ca  mov     rcx, [rbp+var_28]
0x18002f1ce  lea     r8, [rbp+var_20]
0x18002f1d2  xor     r9d, r9d
0x18002f1d5  mov     edx, edi
0x18002f1d7  mov     rax, [rcx]
0x18002f1da  mov     rax, [rax+18h]
0x18002f1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1e3  mov     ebx, eax
0x18002f1e5  test    eax, eax
0x18002f1e7  jnz     short loc_18002F264
0x18002f1e9  mov     rcx, [rbp+var_20]
0x18002f1ed  lea     r8, [rbp+pv]
0x18002f1f1  mov     [rbp+pv], 0
0x18002f1f9  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18002f200  mov     rax, [rcx]
0x18002f203  mov     rax, [rax]
0x18002f206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f20b  mov     ebx, eax
0x18002f20d  test    eax, eax
0x18002f20f  js      short loc_18002F248
0x18002f211  mov     rdx, [rbp+pv]; struct ICondition *
0x18002f215  lea     rax, [rbp+arg_8]
0x18002f219  mov     [rsp+78h+var_48], rax; bool *
0x18002f21e  mov     r9, r15; struct IRichChunk **
0x18002f221  mov     byte ptr [rsp+78h+cchCount2], r14b; bool
0x18002f226  mov     r8, r12; wchar_t **
0x18002f229  mov     rcx, rsi; this
0x18002f22c  mov     [rsp+78h+lpString2], r13; unsigned __int64 *
0x18002f231  call    ?SameProperty@QueryParser@StructuredQuery1@@AEBAJPEAUICondition@@AEAPEA_WAEAPEAUIRichChunk@@AEA_K_NPEA_N@Z; StructuredQuery1::QueryParser::SameProperty(ICondition *,wchar_t * &,IRichChunk * &,unsigned __int64 &,bool,bool *)
0x18002f236  mov     rcx, [rbp+pv]
0x18002f23a  mov     ebx, eax
0x18002f23c  mov     rax, [rcx]
0x18002f23f  mov     rax, [rax+10h]
0x18002f243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f248  mov     rcx, [rbp+var_20]
0x18002f24c  mov     rax, [rcx]
0x18002f24f  mov     rax, [rax+10h]
0x18002f253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f258  test    ebx, ebx
0x18002f25a  js      short loc_18002F264
0x18002f25c  mov     al, [rbp+arg_8]
0x18002f25f  jmp     loc_18002F1C2
0x18002f264  mov     rcx, [rbp+var_28]
0x18002f268  mov     rax, [rcx]
0x18002f26b  mov     rax, [rax+10h]
0x18002f26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f274  mov     al, [rbp+arg_8]
0x18002f277  mov     rcx, [rbp+arg_30]
0x18002f27b  mov     [rcx], al
0x18002f27d  mov     eax, ebx
0x18002f27f  add     rsp, 78h
0x18002f283  pop     r15
0x18002f285  pop     r14
0x18002f287  pop     r13
0x18002f289  pop     r12
0x18002f28b  pop     rdi
0x18002f28c  pop     rsi
0x18002f28d  pop     rbx
0x18002f28e  pop     rbp
0x18002f28f  retn
```
