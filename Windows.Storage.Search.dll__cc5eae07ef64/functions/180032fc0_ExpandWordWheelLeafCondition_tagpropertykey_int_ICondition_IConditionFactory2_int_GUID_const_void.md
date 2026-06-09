# ExpandWordWheelLeafCondition(_tagpropertykey *,int,ICondition *,IConditionFactory2 *,int,_GUID const &,void * *)

- ea: `0x180032fc0`
- end: `0x18003386b`
- name: `?ExpandWordWheelLeafCondition@@YAJPEAU_tagpropertykey@@HPEAUICondition@@PEAUIConditionFactory2@@HAEBU_GUID@@PEAPEAX@Z`
- size: `2219`
- prototype: `int(struct _tagpropertykey *, int, struct ICondition *, struct IConditionFactory2 *, int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032c40`

## callees

- `0x180006ca8`
- `0x180032fc0`
- `0x180033880`
- `0x180033bdc`
- `0x1800346e0`
- `0x1800468c8`
- `0x18006c218`
- `0x180071dc0`
- `0x180072cd0`
- `0x180076890`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180033592`
- `SHCORE!IUnknown_Set` at `0x18003367c`
- `SHCORE!IUnknown_Set` at `0x180033592`
- `SHCORE!IUnknown_Set` at `0x18003367c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003339c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003384a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003339c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003384a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033157`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033388`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033157`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180033388`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrPBrkW` at `0x180033742`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrPBrkW` at `0x180033742`
- `PROPSYS!PropVariantToStringAlloc` at `0x180033727`
- `PROPSYS!PropVariantToStringAlloc` at `0x180033727`
- `PROPSYS!PSGetPropertyDescription` at `0x1800332d7`
- `PROPSYS!PSGetPropertyDescription` at `0x1800332d7`

## pseudocode

```c
__int64 __fastcall ExpandWordWheelLeafCondition(
        struct _tagpropertykey *a1,
        int a2,
        struct ICondition *a3,
        struct IConditionFactory2 *a4,
        int a5,
        const struct _GUID *a6,
        void **a7)
{
  void **v7; // rsi
  struct IConditionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(ICondition *, const IID *const, void **); // rax
  HRESULT v12; // ebx
  int v13; // eax
  HRESULT (__stdcall *v14)(ICondition *, const IID *const, void **); // rax
  void *v15; // rcx
  __int128 *v17; // rdx
  GUID fmtid; // xmm0
  const struct _GUID *v19; // rdx
  int v20; // esi
  int v21; // ebx
  const struct _tagpropertykey *v22; // r14
  BOOL v23; // r13d
  HRESULT WholePropertyCondition; // edi
  struct IConditionFactory2 *v25; // r15
  PWSTR v26; // rcx
  struct IRichChunk *v27; // rcx
  int v28; // eax
  void *ppv; // [rsp+78h] [rbp-88h] BYREF
  IUnknown *punk; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v32; // [rsp+88h] [rbp-78h] BYREF
  IUnknown *ppunk; // [rsp+90h] [rbp-70h] BYREF
  PWSTR ppszOut; // [rsp+98h] [rbp-68h] BYREF
  struct IRichChunk *v35; // [rsp+A0h] [rbp-60h] BYREF
  struct IRichChunk *v36; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  void *v38; // [rsp+B8h] [rbp-48h] BYREF
  void *v39; // [rsp+C0h] [rbp-40h] BYREF
  enum tagCONDITION_OPERATION v40; // [rsp+C8h] [rbp-38h] BYREF
  struct _tagpropertykey v41; // [rsp+D0h] [rbp-30h] BYREF
  __int128 Buf1; // [rsp+E8h] [rbp-18h] BYREF
  int v43; // [rsp+F8h] [rbp-8h]
  struct tagPROPVARIANT pvar; // [rsp+100h] [rbp+0h] BYREF
  struct _tagpropertykey v45; // [rsp+118h] [rbp+18h] BYREF

  v7 = a7;
  v43 = 0;
  lpVtbl = a3->lpVtbl;
  LODWORD(ppunk) = a2;
  ppv = a1;
  QueryInterface = lpVtbl->QueryInterface;
  v38 = 0;
  Buf1 = 0;
  v32 = 0;
  v12 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, unsigned __int16 **))QueryInterface)(
          a3,
          &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
          &v32);
  if ( v12 < 0 )
  {
    v13 = 0;
    Buf1 = 0;
    v43 = 0;
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v32 + 128LL))(
            v32,
            &Buf1,
            0,
            0);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v32 + 16LL))(v32);
    v13 = v43;
  }
  if ( v12 < 0 )
    goto LABEL_20;
  v41.pid = 0;
  switch ( v13 )
  {
    case 12:
      if ( memcmp_0(&Buf1, &PKEY_Generic_String, 0x10u) )
        goto LABEL_9;
      fmtid = PKEY_ItemNameDisplay.fmtid;
      v41.pid = 10;
      goto LABEL_25;
    case 13:
      if ( memcmp_0(&Buf1, &PKEY_Generic_Integer, 0x10u) )
        goto LABEL_9;
      fmtid = PKEY_Size.fmtid;
      v41.pid = 12;
      goto LABEL_25;
    case 16:
      v17 = &PKEY_Generic_FloatingPoint;
LABEL_23:
      if ( memcmp_0(&Buf1, v17, 0x10u) )
        goto LABEL_9;
      fmtid = PKEY_Null.fmtid;
      v41.pid = PKEY_Null.pid;
LABEL_25:
      v40 = COP_IMPLICIT;
      pv = 0;
      v32 = 0;
      ppszOut = 0;
      v35 = 0;
      v41.fmtid = fmtid;
      v36 = 0;
      memset(&pvar, 0, sizeof(pvar));
      v12 = SHGetComparisonInfoEx(a3, 0, &v40, &pvar, &pv, &v32, &ppszOut, &v35, &v36);
      if ( v12 < 0 )
        goto LABEL_20;
      v39 = 0;
      v12 = CEnumerableObjectCollection::CreateInstance(4, v19, &v39);
      if ( v12 < 0 )
        goto LABEL_38;
      v20 = (int)ppunk;
      v21 = 0;
      v22 = (const struct _tagpropertykey *)ppv;
      v23 = 0;
      while ( 1 )
      {
        if ( v21 >= v20 )
        {
LABEL_33:
          v7 = a7;
          if ( v23 )
          {
            v25 = a4;
            goto LABEL_35;
          }
          if ( !v41.pid && !memcmp_0(&v41, &PKEY_Null, 0x10u) )
          {
            v25 = a4;
            goto LABEL_36;
          }
          v25 = a4;
          ppunk = 0;
          if ( (int)SHCreateLeafConditionEx(
                      &v41,
                      v40,
                      &pvar,
                      (const unsigned __int16 *)pv,
                      v32,
                      (struct IRichChunk *)ppszOut,
                      v35,
                      v36,
                      a4,
                      &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                      (void **)&ppunk) < 0 )
            goto LABEL_36;
          punk = 0;
          if ( a5 )
          {
            if ( _GetWholePropertyCondition(
                   (struct ICondition *)ppunk,
                   a4,
                   &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                   (void **)&punk) < 0 )
              goto LABEL_73;
          }
          else
          {
            IUnknown_Set(&punk, ppunk);
          }
          v23 = (*(int (__fastcall **)(void *, IUnknown *))(*(_QWORD *)v39 + 40LL))(v39, punk) >= 0;
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
LABEL_73:
          ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
LABEL_35:
          if ( v23 )
          {
            ppv = 0;
            v12 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))v39)(
                    v39,
                    &GUID_00000100_0000_0000_c000_000000000046,
                    &ppv);
            if ( v12 >= 0 )
            {
              v12 = SHNextObjectFromEnumUnknown((struct IEnumUnknown *)ppv, a6, &v38);
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
          else
          {
LABEL_36:
            v12 = ((__int64 (__fastcall *)(struct IConditionFactory2 *, __int64, void *, _QWORD, const struct _GUID *, void **))v25->lpVtbl->CreateCompoundFromObjectArray)(
                    v25,
                    1,
                    v39,
                    0,
                    a6,
                    &v38);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
LABEL_38:
          PropVariantClear((PROPVARIANT *)&pvar);
          CoTaskMemFree(pv);
          CoTaskMemFree(v32);
          v26 = ppszOut;
          ppszOut = 0;
          if ( v26 )
            (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v26 + 16LL))(v26);
          v27 = v35;
          v35 = 0;
          if ( v27 )
            ((void (__fastcall *)(struct IRichChunk *))v27->lpVtbl->Release)(v27);
          v15 = v36;
          v36 = 0;
LABEL_18:
          if ( v15 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
          goto LABEL_20;
        }
        ppv = 0;
        WholePropertyCondition = PSGetPropertyDescription(&v22[v21], &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &ppv);
        if ( WholePropertyCondition >= 0 )
          break;
LABEL_32:
        ++v21;
        if ( WholePropertyCondition < 0 )
          goto LABEL_33;
      }
      memset(&v45, 0, sizeof(v45));
      if ( !(unsigned int)GetCorrespondingGenericKey((struct IPropertyDescription *)ppv, &v45)
        || v45.pid != v43
        || memcmp_0(&v45, &Buf1, 0x10u)
        || (punk = 0,
            WholePropertyCondition = SHCreateLeafConditionEx(
                                       &v22[v21],
                                       v40,
                                       &pvar,
                                       (const unsigned __int16 *)pv,
                                       v32,
                                       (struct IRichChunk *)ppszOut,
                                       v35,
                                       v36,
                                       a4,
                                       &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                       (void **)&punk),
            WholePropertyCondition < 0) )
      {
LABEL_31:
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_32;
      }
      ppunk = 0;
      if ( a5 )
      {
        WholePropertyCondition = _GetWholePropertyCondition(
                                   (struct ICondition *)punk,
                                   a4,
                                   &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                   (void **)&ppunk);
        if ( WholePropertyCondition < 0 )
        {
LABEL_65:
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          goto LABEL_31;
        }
      }
      else
      {
        IUnknown_Set(&ppunk, punk);
      }
      WholePropertyCondition = (*(__int64 (__fastcall **)(void *, IUnknown *))(*(_QWORD *)v39 + 40LL))(v39, ppunk);
      ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
      v28 = v23 + 1;
      if ( WholePropertyCondition < 0 )
        v28 = v23;
      v23 = v28;
      goto LABEL_65;
    case 15:
      v17 = &PKEY_Generic_Boolean;
      goto LABEL_23;
  }
  if ( v13 == 14 && !memcmp_0(&Buf1, &PKEY_Generic_DateTime, 0x10u) )
  {
    fmtid = PKEY_ItemDate.fmtid;
    v41.pid = 100;
    goto LABEL_25;
  }
LABEL_9:
  v14 = a3->lpVtbl->QueryInterface;
  if ( a5 )
  {
    v38 = 0;
    v40 = COP_IMPLICIT;
    v32 = 0;
    ppv = 0;
    memset(&pvar, 0, sizeof(pvar));
    v12 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, void **))v14)(
            a3,
            &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
            &ppv);
    if ( v12 < 0 )
    {
      v40 = COP_IMPLICIT;
      memset(&pvar, 0, sizeof(pvar));
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(void *, _QWORD, enum tagCONDITION_OPERATION *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 128LL))(
              ppv,
              0,
              &v40,
              &pvar);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v12 >= 0 )
      {
        if ( v40 == COP_WORD_STARTSWITH || (v12 = 1, v40 == COP_WORD_EQUAL) )
        {
          ppszOut = 0;
          v12 = PropVariantToStringAlloc((const PROPVARIANT *const)&pvar, &ppszOut);
          if ( v12 >= 0 )
          {
            if ( StrPBrkW(ppszOut, L"\\/_") )
            {
              ppv = 0;
              pv = 0;
              punk = 0;
              v36 = 0;
              v35 = 0;
              memset(&v45, 0, sizeof(v45));
              v12 = SHGetComparisonInfoEx(a3, &v45, 0, 0, &ppv, &pv, &punk, &v36, &v35);
              if ( v12 >= 0 )
              {
                v12 = SHCreateLeafConditionEx(
                        &v45,
                        COP_VALUE_CONTAINS,
                        &pvar,
                        (const unsigned __int16 *)ppv,
                        (const unsigned __int16 *)pv,
                        (struct IRichChunk *)punk,
                        v36,
                        v35,
                        a4,
                        &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                        (void **)&v32);
                CoTaskMemFree(ppv);
                CoTaskMemFree(pv);
                SafeRelease<IShellItemArray>((__int64 *)&punk);
                SafeRelease<IShellItemArray>((__int64 *)&v36);
                SafeRelease<IShellItemArray>((__int64 *)&v35);
              }
            }
            CoTaskMemFree(ppszOut);
          }
        }
        PropVariantClear((PROPVARIANT *)&pvar);
        if ( v12 >= 0 )
        {
          if ( v32 )
            v12 = (**(__int64 (__fastcall ***)(unsigned __int16 *, const struct _GUID *, void **))v32)(v32, a6, &v38);
          else
            v12 = ((__int64 (__fastcall *)(struct ICondition *, const struct _GUID *, void **))a3->lpVtbl->QueryInterface)(
                    a3,
                    a6,
                    &v38);
        }
      }
    }
    v15 = v32;
    v32 = 0;
    goto LABEL_18;
  }
  ((void (__fastcall *)(struct ICondition *, const struct _GUID *, void **))v14)(a3, a6, &v38);
LABEL_20:
  *v7 = v38;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180032fc0  push    rbp
0x180032fc2  push    rbx
0x180032fc3  push    rsi
0x180032fc4  push    rdi
0x180032fc5  push    r12
0x180032fc7  push    r14
0x180032fc9  push    r15
0x180032fcb  lea     rbp, [rsp-40h]
0x180032fd0  sub     rsp, 140h
0x180032fd7  mov     rax, cs:__security_cookie
0x180032fde  xor     rax, rsp
0x180032fe1  mov     [rbp+70h+var_40], rax
0x180032fe5  mov     r14, [rbp+70h+arg_28]
0x180032fec  xor     eax, eax
0x180032fee  mov     rsi, [rbp+70h+arg_30]
0x180032ff5  mov     rdi, r8
0x180032ff8  mov     [rbp+70h+var_78], eax
0x180032ffb  xor     r12d, r12d
0x180032ffe  mov     rax, [r8]
0x180033001  xorps   xmm0, xmm0
0x180033004  mov     dword ptr [rbp+70h+ppunk], edx
0x180033007  lea     r8, [rbp+70h+var_E8]
0x18003300b  mov     [rsp+170h+ppv], rcx
0x180033010  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180033017  mov     rcx, rdi
0x18003301a  mov     [rsp+170h+var_110], r9
0x18003301f  mov     rax, [rax]
0x180033022  mov     r15, r9
0x180033025  mov     [rsp+170h+var_100], r14
0x18003302a  mov     [rsp+170h+var_108], rsi
0x18003302f  mov     [rbp+70h+var_B8], r12
0x180033033  movups  [rbp+70h+Buf1], xmm0
0x180033037  mov     [rbp+70h+var_E8], r12
0x18003303b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033040  mov     ebx, eax
0x180033042  test    eax, eax
0x180033044  js      loc_180033568
0x18003304a  mov     rcx, [rbp+70h+var_E8]
0x18003304e  lea     rdx, [rbp+70h+Buf1]
0x180033052  xor     r9d, r9d
0x180033055  xor     r8d, r8d
0x180033058  mov     rax, [rcx]
0x18003305b  mov     rax, [rax+80h]
0x180033062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033067  mov     rcx, [rbp+70h+var_E8]
0x18003306b  mov     ebx, eax
0x18003306d  mov     rax, [rcx]
0x180033070  mov     rax, [rax+10h]
0x180033074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033079  mov     eax, [rbp+70h+var_78]
0x18003307c  test    ebx, ebx
0x18003307e  js      loc_18003319E
0x180033084  mov     [rbp+70h+var_A0.pid], r12d
0x180033088  cmp     eax, 0Ch
0x18003308b  jz      loc_1800333ED
0x180033091  cmp     eax, 0Dh
0x180033094  jz      loc_180033430
0x18003309a  cmp     eax, 10h
0x18003309d  jz      loc_1800331D6
0x1800330a3  cmp     eax, 0Fh
0x1800330a6  jz      loc_1800333E1
0x1800330ac  cmp     eax, 0Eh
0x1800330af  jz      loc_180033461
0x1800330b5  mov     rax, [rdi]
0x1800330b8  mov     rax, [rax]
0x1800330bb  cmp     [rbp+70h+arg_20], r12d
0x1800330c2  jz      loc_1800331C5
0x1800330c8  xor     ecx, ecx
0x1800330ca  mov     [rbp+70h+var_B8], r12
0x1800330ce  mov     [rbp+70h+var_60], rcx
0x1800330d2  lea     r8, [rsp+170h+ppv]
0x1800330d7  xorps   xmm0, xmm0
0x1800330da  mov     [rbp+70h+var_A8], r12d
0x1800330de  mov     rcx, rdi
0x1800330e1  mov     [rbp+70h+var_E8], r12
0x1800330e5  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800330ec  mov     [rsp+170h+ppv], r12
0x1800330f1  movups  xmmword ptr [rbp+70h+pvar], xmm0
0x1800330f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330fa  mov     ebx, eax
0x1800330fc  test    eax, eax
0x1800330fe  js      loc_180033855
0x180033104  mov     rcx, [rsp+170h+ppv]
0x180033109  lea     r9, [rbp+70h+pvar]
0x18003310d  lea     r8, [rbp+70h+var_A8]
0x180033111  xor     edx, edx
0x180033113  mov     rax, [rcx]
0x180033116  mov     rax, [rax+80h]
0x18003311d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033122  mov     rcx, [rsp+170h+ppv]
0x180033127  mov     ebx, eax
0x180033129  mov     rax, [rcx]
0x18003312c  mov     rax, [rax+10h]
0x180033130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033135  test    ebx, ebx
0x180033137  js      short loc_180033185
0x180033139  mov     eax, [rbp+70h+var_A8]
0x18003313c  cmp     eax, 0Dh
0x18003313f  jz      loc_18003371B
0x180033145  mov     ebx, 1
0x18003314a  cmp     eax, 0Ch
0x18003314d  jz      loc_18003371B
0x180033153  lea     rcx, [rbp+70h+pvar]; pvar
0x180033157  call    cs:__imp_PropVariantClear
0x18003315d  test    ebx, ebx
0x18003315f  js      short loc_180033185
0x180033161  mov     rcx, [rbp+70h+var_E8]
0x180033165  lea     r8, [rbp+70h+var_B8]
0x180033169  mov     rdx, r14
0x18003316c  test    rcx, rcx
0x18003316f  jnz     loc_18003341E
0x180033175  mov     rax, [rdi]
0x180033178  mov     rcx, rdi
0x18003317b  mov     rax, [rax]
0x18003317e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033183  mov     ebx, eax
0x180033185  mov     rcx, [rbp+70h+var_E8]
0x180033189  mov     [rbp+70h+var_E8], r12
0x18003318d  test    rcx, rcx
0x180033190  jz      short loc_18003319E
0x180033192  mov     rax, [rcx]
0x180033195  mov     rax, [rax+10h]
0x180033199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003319e  mov     rax, [rbp+70h+var_B8]
0x1800331a2  mov     [rsi], rax
0x1800331a5  mov     eax, ebx
0x1800331a7  mov     rcx, [rbp+70h+var_40]
0x1800331ab  xor     rcx, rsp; StackCookie
0x1800331ae  call    __security_check_cookie
0x1800331b3  add     rsp, 140h
0x1800331ba  pop     r15
0x1800331bc  pop     r14
0x1800331be  pop     r12
0x1800331c0  pop     rdi
0x1800331c1  pop     rsi
0x1800331c2  pop     rbx
0x1800331c3  pop     rbp
0x1800331c4  retn
0x1800331c5  lea     r8, [rbp+70h+var_B8]
0x1800331c9  mov     rdx, r14
0x1800331cc  mov     rcx, rdi
0x1800331cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331d4  jmp     short loc_18003319E
0x1800331d6  lea     rdx, PKEY_Generic_FloatingPoint; Buf2
0x1800331dd  mov     r8d, 10h; Size
0x1800331e3  lea     rcx, [rbp+70h+Buf1]; Buf1
0x1800331e7  call    memcmp_0
0x1800331ec  test    eax, eax
0x1800331ee  jnz     loc_1800330B5
0x1800331f4  mov     eax, cs:PKEY_Null.pid
0x1800331fa  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x180033201  mov     [rbp+70h+var_A0.pid], eax
0x180033204  xor     eax, eax
0x180033206  mov     [rbp+70h+var_A8], r12d
0x18003320a  mov     [rbp+70h+var_60], rax
0x18003320e  lea     r9, [rbp+70h+pvar]
0x180033212  lea     rax, [rbp+70h+var_C8]
0x180033216  mov     [rbp+70h+pv], r12
0x18003321a  mov     [rsp+170h+var_130], rax
0x18003321f  lea     r8, [rbp+70h+var_A8]
0x180033223  lea     rax, [rbp+70h+var_D0]
0x180033227  mov     [rbp+70h+var_E8], r12
0x18003322b  mov     [rsp+170h+var_138], rax
0x180033230  xor     edx, edx
0x180033232  lea     rax, [rbp+70h+ppszOut]
0x180033236  mov     [rbp+70h+ppszOut], r12
0x18003323a  mov     [rsp+170h+var_140], rax
0x18003323f  mov     rcx, rdi
0x180033242  lea     rax, [rbp+70h+var_E8]
0x180033246  mov     [rbp+70h+var_D0], r12
0x18003324a  mov     [rsp+170h+var_148], rax
0x18003324f  lea     rax, [rbp+70h+pv]
0x180033253  movups  xmmword ptr [rbp+70h+var_A0.fmtid.Data1], xmm0
0x180033257  mov     [rsp+170h+var_150], rax
0x18003325c  xorps   xmm0, xmm0
0x18003325f  mov     [rbp+70h+var_C8], r12
0x180033263  movups  xmmword ptr [rbp+70h+pvar], xmm0
0x180033267  call    SHGetComparisonInfoEx
0x18003326c  mov     ebx, eax
0x18003326e  test    eax, eax
0x180033270  js      loc_18003319E
0x180033276  lea     r8, [rbp+70h+var_B0]; void **
0x18003327a  mov     [rbp+70h+var_B0], r12
0x18003327e  mov     ecx, 4; int
0x180033283  call    ?CreateInstance@CEnumerableObjectCollection@@SAJHAEBU_GUID@@PEAPEAX@Z; CEnumerableObjectCollection::CreateInstance(int,_GUID const &,void * *)
0x180033288  mov     ebx, eax
0x18003328a  test    eax, eax
0x18003328c  js      loc_180033384
0x180033292  mov     esi, dword ptr [rbp+70h+ppunk]
0x180033295  mov     ebx, r12d
0x180033298  mov     r14, [rsp+170h+ppv]
0x18003329d  mov     [rsp+170h+arg_8], r13
0x1800332a5  mov     r13d, r12d
0x1800332a8  lea     r12, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x1800332af  nop
0x1800332b0  cmp     ebx, esi
0x1800332b2  jge     short loc_18003331C
0x1800332b4  movsxd  rax, ebx
0x1800332b7  lea     r8, [rsp+170h+ppv]; ppv
0x1800332bc  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x1800332c3  mov     [rsp+170h+ppv], 0
0x1800332cc  lea     rcx, [rax+rax*4]
0x1800332d0  lea     r15, [r14+rcx*4]
0x1800332d4  mov     rcx, r15; propkey
0x1800332d7  call    cs:__imp_PSGetPropertyDescription
0x1800332dd  mov     edi, eax
0x1800332df  test    eax, eax
0x1800332e1  js      short loc_180033316
0x1800332e3  mov     rcx, [rsp+170h+ppv]; struct IPropertyDescription *
0x1800332e8  lea     rdx, [rbp+70h+var_58]; struct _tagpropertykey *
0x1800332ec  xorps   xmm0, xmm0
0x1800332ef  xor     eax, eax
0x1800332f1  movups  xmmword ptr [rbp+70h+var_58.fmtid.Data1], xmm0
0x1800332f5  mov     [rbp+70h+var_58.pid], eax
0x1800332f8  call    ?GetCorrespondingGenericKey@@YAHPEAUIPropertyDescription@@PEAU_tagpropertykey@@@Z; GetCorrespondingGenericKey(IPropertyDescription *,_tagpropertykey *)
0x1800332fd  test    eax, eax
0x1800332ff  jnz     loc_180033579
0x180033305  mov     rcx, [rsp+170h+ppv]
0x18003330a  mov     rax, [rcx]
0x18003330d  mov     rax, [rax+10h]
0x180033311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033316  inc     ebx
0x180033318  test    edi, edi
0x18003331a  jns     short loc_1800332B0
0x18003331c  mov     rsi, [rsp+170h+var_108]
0x180033321  mov     r14, [rsp+170h+var_100]
0x180033326  test    r13d, r13d
0x180033329  jz      loc_1800335E0
0x18003332f  mov     r15, [rsp+170h+var_110]
0x180033334  cmp     r13d, 1
0x180033338  jz      loc_1800336C5
0x18003333e  mov     rax, [r15]
0x180033341  lea     rcx, [rbp+70h+var_B8]
0x180033345  mov     r8, [rbp+70h+var_B0]
0x180033349  xor     r9d, r9d
0x18003334c  mov     [rsp+170h+var_148], rcx
0x180033351  mov     edx, 1
0x180033356  mov     rcx, r15
0x180033359  mov     [rsp+170h+var_150], r14
0x18003335e  mov     rax, [rax+48h]
0x180033362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033367  mov     ebx, eax
0x180033369  xor     r12d, r12d
0x18003336c  mov     rcx, [rbp+70h+var_B0]
0x180033370  mov     rax, [rcx]
0x180033373  mov     rax, [rax+10h]
0x180033377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003337c  mov     r13, [rsp+170h+arg_8]
0x180033384  lea     rcx, [rbp+70h+pvar]; pvar
0x180033388  call    cs:__imp_PropVariantClear
0x18003338e  mov     rcx, [rbp+70h+pv]; pv
0x180033392  call    cs:__imp_CoTaskMemFree
0x180033398  mov     rcx, [rbp+70h+var_E8]; pv
0x18003339c  call    cs:__imp_CoTaskMemFree
0x1800333a2  mov     rcx, [rbp+70h+ppszOut]
0x1800333a6  mov     [rbp+70h+ppszOut], r12
0x1800333aa  test    rcx, rcx
0x1800333ad  jz      short loc_1800333BB
0x1800333af  mov     rax, [rcx]
0x1800333b2  mov     rax, [rax+10h]
0x1800333b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333bb  mov     rcx, [rbp+70h+var_D0]
0x1800333bf  mov     [rbp+70h+var_D0], r12
0x1800333c3  test    rcx, rcx
0x1800333c6  jz      short loc_1800333D4
0x1800333c8  mov     rax, [rcx]
0x1800333cb  mov     rax, [rax+10h]
0x1800333cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333d4  mov     rcx, [rbp+70h+var_C8]
0x1800333d8  mov     [rbp+70h+var_C8], r12
0x1800333dc  jmp     loc_18003318D
0x1800333e1  lea     rdx, PKEY_Generic_Boolean
0x1800333e8  jmp     loc_1800331DD
0x1800333ed  mov     r8d, 10h; Size
0x1800333f3  lea     rdx, PKEY_Generic_String; Buf2
0x1800333fa  lea     rcx, [rbp+70h+Buf1]; Buf1
0x1800333fe  call    memcmp_0
0x180033403  test    eax, eax
0x180033405  jnz     loc_1800330B5
0x18003340b  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x180033412  mov     [rbp+70h+var_A0.pid], 0Ah
0x180033419  jmp     loc_180033204
0x18003341e  mov     rax, [rcx]
0x180033421  mov     rax, [rax]
0x180033424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033429  mov     ebx, eax
0x18003342b  jmp     loc_180033185
0x180033430  mov     r8d, 10h; Size
0x180033436  lea     rdx, PKEY_Generic_Integer; Buf2
0x18003343d  lea     rcx, [rbp+70h+Buf1]; Buf1
0x180033441  call    memcmp_0
0x180033446  test    eax, eax
0x180033448  jnz     loc_1800330B5
0x18003344e  movups  xmm0, xmmword ptr cs:PKEY_Size.fmtid.Data1
0x180033455  mov     [rbp+70h+var_A0.pid], 0Ch
0x18003345c  jmp     loc_180033204
0x180033461  mov     r8d, 10h; Size
0x180033467  lea     rdx, PKEY_Generic_DateTime; Buf2
0x18003346e  lea     rcx, [rbp+70h+Buf1]; Buf1
0x180033472  call    memcmp_0
  ... truncated ...
```
