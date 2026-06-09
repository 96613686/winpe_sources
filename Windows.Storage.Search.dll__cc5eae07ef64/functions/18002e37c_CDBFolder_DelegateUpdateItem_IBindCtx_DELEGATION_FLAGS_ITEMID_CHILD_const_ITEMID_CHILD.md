# CDBFolder::_DelegateUpdateItem(IBindCtx *,DELEGATION_FLAGS,_ITEMID_CHILD const *,_ITEMID_CHILD * *)

- ea: `0x18002e37c`
- end: `0x18002e88c`
- name: `?_DelegateUpdateItem@CDBFolder@@AEAAJPEAUIBindCtx@@W4DELEGATION_FLAGS@@PEFBU_ITEMID_CHILD@@PEAPEAU4@@Z`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e100`

## callees

- `0x18000a350`
- `0x18002ca00`
- `0x18002e37c`
- `0x18002e894`
- `0x18002eab4`
- `0x18002eb08`
- `0x18002eb80`
- `0x18002ee20`
- `0x180071dc0`
- `0x1800722bc`
- `0x1800722e0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromIDList` at `0x18002e7e5`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18002e7e5`
- `Windows.Storage!ILGetSize` at `0x18002e4a7`
- `Windows.Storage!ILGetSize` at `0x18002e661`
- `Windows.Storage!ILGetSize` at `0x18002e4a7`
- `Windows.Storage!ILGetSize` at `0x18002e661`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e71f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e71f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e6f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e6f7`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002e4b6`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002e66f`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002e4b6`
- `PROPSYS!InitPropVariantFromBuffer` at `0x18002e66f`

## string_xrefs

- `0x18002e4e6`: `PropertyUpdateList`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDBFolder::_DelegateUpdateItem(
        CDBFolder *a1,
        struct IBindCtx *a2,
        unsigned int a3,
        struct _ITEMID_CHILD *a4,
        struct _ITEMID_CHILD **a5)
{
  struct _ITEMID_CHILD **v9; // r12
  int v10; // ebx
  HRESULT RealIDL; // esi
  ITEMIDLIST *v12; // r13
  UINT v13; // eax
  struct _ITEMID_CHILD *v14; // rbx
  int v15; // edi
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rax
  struct _tagpropertykey *v18; // rdi
  __int64 v19; // rax
  bool v20; // cf
  unsigned __int64 v21; // rax
  unsigned __int64 *v22; // rax
  const struct tagPROPVARIANT *v23; // r15
  __int64 v24; // rcx
  struct tagPROPVARIANT *v25; // rsi
  UINT v26; // eax
  struct _ITEMID_CHILD *v27; // rax
  void *v28; // rcx
  struct _ITEMID_CHILD *v29; // rcx
  __int64 v31; // rcx
  unsigned int i; // r12d
  DWORD v33; // edx
  __int64 v34; // rcx
  int v35; // r12d
  signed int v36; // [rsp+40h] [rbp-91h] BYREF
  void *ppv; // [rsp+48h] [rbp-89h] BYREF
  int v38[2]; // [rsp+50h] [rbp-81h] BYREF
  __int64 v39; // [rsp+58h] [rbp-79h] BYREF
  struct _ITEMID_CHILD *v40; // [rsp+60h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-69h] BYREF
  struct _ITEMID_CHILD *v42; // [rsp+70h] [rbp-61h] BYREF
  struct IShellFolder *v43; // [rsp+78h] [rbp-59h] BYREF
  __int64 v44; // [rsp+80h] [rbp-51h] BYREF
  LPCITEMIDLIST pidl; // [rsp+88h] [rbp-49h] BYREF
  const struct tagPROPVARIANT *v46; // [rsp+90h] [rbp-41h] BYREF
  struct _ITEMID_CHILD **v47; // [rsp+98h] [rbp-39h]
  struct _ITEMID_CHILD *v48; // [rsp+A0h] [rbp-31h]
  CDBFolder *v49; // [rsp+A8h] [rbp-29h]
  PROPVARIANT ppropvar[2]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-11h]
  struct _tagpropertykey *v52; // [rsp+C8h] [rbp-9h]
  GUID v53; // [rsp+D0h] [rbp-1h] BYREF
  DWORD v54; // [rsp+E0h] [rbp+Fh]

  v48 = a4;
  v49 = a1;
  v9 = a5;
  v47 = a5;
  *a5 = 0;
  v43 = 0;
  v42 = 0;
  v10 = 0;
  ppv = 0;
  if ( a2
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void **))a2->lpVtbl->GetObjectParam)(
         a2,
         L"Full Parse Bind",
         &ppv) >= 0 )
  {
    v10 = 1;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  RealIDL = CDBFolder::DelegateBindToParent(
              (char *)a1 + 184,
              a4,
              (unsigned int)(v10 + 1),
              a3,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &v43,
              &v42);
  if ( RealIDL >= 0 )
  {
    pv = 0;
    RealIDL = GetRealIDL(a2, v43, v42, (struct _ITEMID_CHILD **)&pv);
    if ( RealIDL < 0 )
    {
LABEL_36:
      v28 = pv;
      pv = 0;
      CoTaskMemFree(v28);
      goto LABEL_37;
    }
    pidl = 0;
    RealIDL = SHFullIDListFromFolderAndRelativeItem(v43, pv, &pidl);
    v12 = (ITEMIDLIST *)pidl;
    if ( RealIDL < 0 )
    {
LABEL_35:
      CoTaskMemFree(v12);
      goto LABEL_36;
    }
    *(_OWORD *)ppropvar = 0;
    v51 = 0;
    v13 = ILGetSize(pidl);
    RealIDL = InitPropVariantFromBuffer(v12, v13, ppropvar);
    if ( RealIDL < 0 )
    {
LABEL_34:
      PropVariantClear(ppropvar);
      goto LABEL_35;
    }
    v14 = 0;
    v40 = 0;
    v36 = 0;
    v39 = 0;
    *(_QWORD *)v38 = 0;
    if ( a2 )
    {
      if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, int *))a2->lpVtbl->GetObjectParam)(
             a2,
             L"PropertyUpdateList",
             v38) >= 0 )
      {
        v15 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v38)(
                *(_QWORD *)v38,
                &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                &v39);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 16LL))(*(_QWORD *)v38);
        if ( v15 >= 0 )
          (*(void (__fastcall **)(__int64, signed int *))(*(_QWORD *)v39 + 24LL))(v39, &v36);
      }
    }
    v38[0] = v36 + 1;
    v16 = v36 + 1;
    v17 = 20 * v16;
    if ( !is_mul_ok(v16, 0x14u) )
      v17 = -1;
    v18 = (struct _tagpropertykey *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    v52 = v18;
    v19 = 24 * v16;
    if ( !is_mul_ok(v16, 0x18u) )
      v19 = -1;
    v20 = __CFADD__(v19, 8);
    v21 = v19 + 8;
    if ( v20 )
      v21 = -1;
    v22 = (unsigned __int64 *)operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
    v46 = (const struct tagPROPVARIANT *)v22;
    if ( v22 )
    {
      *v22 = v16;
      v23 = (const struct tagPROPVARIANT *)(v22 + 1);
      `eh vector constructor iterator'(
        v22 + 1,
        0x18u,
        v16,
        (void (*)(void *))CComPropVariant::CComPropVariant,
        (void (*)(void *))CPropVariant::~CPropVariant);
    }
    else
    {
      v23 = 0;
    }
    v46 = v23;
    if ( v18 && v23 )
    {
      v31 = v39;
      if ( v39 )
      {
        for ( i = 0; (int)i < v36; ++i )
        {
          v53 = 0;
          v54 = 0;
          RealIDL = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *))(*(_QWORD *)v31 + 32LL))(v31, i, &v53);
          if ( RealIDL < 0 )
            goto LABEL_31;
          v33 = v54;
          v34 = (int)i;
          v18[v34].fmtid = v53;
          v18[v34].pid = v33;
          v31 = v39;
        }
        ppv = 0;
        RealIDL = SHCreateItemFromIDList(v12, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
        if ( RealIDL >= 0 )
        {
          v44 = 0;
          RealIDL = (*(__int64 (__fastcall **)(void *, struct _tagpropertykey *, _QWORD, __int64, GUID *, __int64 *))(*(_QWORD *)ppv + 80LL))(
                      ppv,
                      v18,
                      (unsigned int)v36,
                      8,
                      &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                      &v44);
          if ( RealIDL >= 0 )
          {
            v35 = 0;
            do
            {
              if ( v35 >= v36 )
                break;
              RealIDL = (*(__int64 (__fastcall **)(__int64, struct _tagpropertykey *, const struct tagPROPVARIANT *))(*(_QWORD *)v44 + 40LL))(
                          v44,
                          &v18[v35],
                          &v23[v35]);
              ++v35;
            }
            while ( RealIDL >= 0 );
          }
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( RealIDL < 0 )
          goto LABEL_31;
        v9 = v47;
      }
      v24 = v36;
      v18[v24].fmtid = (GUID)PKEY_DelegateIDList;
      v18[v24].pid = 32;
      v25 = (struct tagPROPVARIANT *)&v23[v36];
      *(_OWORD *)&v25->vt = 0;
      v25->bstrblobVal.pData = 0;
      v26 = ILGetSize(v12);
      RealIDL = InitPropVariantFromBuffer(v12, v26, (PROPVARIANT *)v25);
      if ( RealIDL >= 0 )
      {
        RealIDL = CDBFolder::_UpdateItem(v49, v48, v38[0], v18, v23, &v40);
        if ( RealIDL < 0 )
        {
          v14 = v40;
        }
        else
        {
          _BindCtx_SetValue<int>((__int64 *)a2);
          v27 = v40;
          v14 = 0;
          v40 = 0;
          *v9 = v27;
        }
      }
    }
    else
    {
      RealIDL = -2147024882;
    }
LABEL_31:
    CAutoArrayMemPtr<CComPropVariant>::~CAutoArrayMemPtr<CComPropVariant>(&v46);
    CZeroInitNew::operator delete(v18);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    CoTaskMemFree(v14);
    goto LABEL_34;
  }
LABEL_37:
  v29 = v42;
  v42 = 0;
  CoTaskMemFree(v29);
  if ( v43 )
    ((void (__fastcall *)(struct IShellFolder *))v43->lpVtbl->Release)(v43);
  return (unsigned int)RealIDL;
}

```

## disassembly

```asm
0x18002e37c  mov     [rsp-8+arg_10], rbx
0x18002e381  push    rbp
0x18002e382  push    rsi
0x18002e383  push    rdi
0x18002e384  push    r12
0x18002e386  push    r13
0x18002e388  push    r14
0x18002e38a  push    r15
0x18002e38c  lea     rbp, [rsp-1Fh]
0x18002e391  sub     rsp, 0F0h
0x18002e398  mov     rax, cs:__security_cookie
0x18002e39f  xor     rax, rsp
0x18002e3a2  mov     [rbp+4Fh+var_38], rax
0x18002e3a6  mov     r15, r9
0x18002e3a9  mov     [rbp+4Fh+var_80], r9
0x18002e3ad  mov     edi, r8d
0x18002e3b0  mov     r14, rdx
0x18002e3b3  mov     rsi, rcx
0x18002e3b6  mov     [rbp+4Fh+var_78], rcx
0x18002e3ba  mov     r12, [rbp+4Fh+arg_20]
0x18002e3be  mov     [rbp+4Fh+var_88], r12
0x18002e3c2  xor     r13d, r13d
0x18002e3c5  mov     [r12], r13
0x18002e3c9  mov     [rbp+4Fh+var_A8], r13
0x18002e3cd  mov     [rbp+4Fh+var_B0], r13
0x18002e3d1  mov     ebx, r13d
0x18002e3d4  mov     [rsp+120h+ppv], r13
0x18002e3d9  test    rdx, rdx
0x18002e3dc  jz      short loc_18002E412
0x18002e3de  mov     rax, [rdx]
0x18002e3e1  lea     r8, [rsp+120h+ppv]
0x18002e3e6  lea     rdx, aFullParseBind; "Full Parse Bind"
0x18002e3ed  mov     rcx, r14
0x18002e3f0  mov     rax, [rax+50h]
0x18002e3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3f9  test    eax, eax
0x18002e3fb  js      short loc_18002E412
0x18002e3fd  lea     ebx, [r13+1]
0x18002e401  mov     rcx, [rsp+120h+ppv]
0x18002e406  mov     rax, [rcx]
0x18002e409  mov     rax, [rax+10h]
0x18002e40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e412  lea     r8d, [rbx+1]
0x18002e416  lea     rcx, [rsi+0B8h]
0x18002e41d  lea     rax, [rbp+4Fh+var_B0]
0x18002e421  mov     [rsp+120h+var_F0], rax
0x18002e426  lea     rax, [rbp+4Fh+var_A8]
0x18002e42a  mov     [rsp+120h+var_F8], rax
0x18002e42f  lea     rax, _GUID_000214e6_0000_0000_c000_000000000046
0x18002e436  mov     [rsp+120h+var_100], rax
0x18002e43b  mov     r9d, edi
0x18002e43e  mov     rdx, r15
0x18002e441  call    ?DelegateBindToParent@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@W4DELBIND_TYPE@@W4DELEGATION_FLAGS@@AEBU_GUID@@PEAPEAXPEAPEAU2@@Z; CDBFolder::DelegateBindToParent(_ITEMID_CHILD const *,DELBIND_TYPE,DELEGATION_FLAGS,_GUID const &,void * *,_ITEMID_CHILD * *)
0x18002e446  mov     esi, eax
0x18002e448  xor     edi, edi
0x18002e44a  test    eax, eax
0x18002e44c  js      loc_18002E717
0x18002e452  mov     [rbp+4Fh+pv], rdi
0x18002e456  lea     r9, [rbp+4Fh+pv]; struct _ITEMID_CHILD **
0x18002e45a  mov     r8, [rbp+4Fh+var_B0]; struct _ITEMID_CHILD *
0x18002e45e  mov     rdx, [rbp+4Fh+var_A8]; struct IShellFolder *
0x18002e462  mov     rcx, r14; struct IBindCtx *
0x18002e465  call    ?GetRealIDL@@YAJPEAUIBindCtx@@PEAUIShellFolder@@PEFBU_ITEMID_CHILD@@PEAPEAU3@@Z; GetRealIDL(IBindCtx *,IShellFolder *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)
0x18002e46a  mov     esi, eax
0x18002e46c  test    eax, eax
0x18002e46e  js      loc_18002E708
0x18002e474  mov     [rbp+4Fh+pidl], rdi
0x18002e478  lea     r8, [rbp+4Fh+pidl]
0x18002e47c  mov     rdx, [rbp+4Fh+pv]
0x18002e480  mov     rcx, [rbp+4Fh+var_A8]
0x18002e484  call    SHFullIDListFromFolderAndRelativeItem
0x18002e489  mov     esi, eax
0x18002e48b  mov     r13, [rbp+4Fh+pidl]
0x18002e48f  test    eax, eax
0x18002e491  js      loc_18002E6FE
0x18002e497  xorps   xmm0, xmm0
0x18002e49a  xor     eax, eax
0x18002e49c  movups  xmmword ptr [rbp+4Fh+ppropvar], xmm0
0x18002e4a0  mov     [rbp+4Fh+var_60], rax
0x18002e4a4  mov     rcx, r13; pidl
0x18002e4a7  call    cs:__imp_ILGetSize
0x18002e4ad  mov     edx, eax; cb
0x18002e4af  lea     r8, [rbp+4Fh+ppropvar]; ppropvar
0x18002e4b3  mov     rcx, r13; pv
0x18002e4b6  call    cs:__imp_InitPropVariantFromBuffer
0x18002e4bc  mov     esi, eax
0x18002e4be  test    eax, eax
0x18002e4c0  js      loc_18002E6F3
0x18002e4c6  mov     ebx, edi
0x18002e4c8  mov     [rbp+4Fh+var_C0], rbx
0x18002e4cc  mov     [rsp+120h+var_E0], edi
0x18002e4d0  mov     [rbp+4Fh+var_C8], rdi
0x18002e4d4  mov     qword ptr [rsp+120h+var_D0], rdi
0x18002e4d9  test    r14, r14
0x18002e4dc  jz      short loc_18002E547
0x18002e4de  mov     rax, [r14]
0x18002e4e1  lea     r8, [rsp+120h+var_D0]
0x18002e4e6  lea     rdx, aPropertyupdate; "PropertyUpdateList"
0x18002e4ed  mov     rcx, r14
0x18002e4f0  mov     rax, [rax+50h]
0x18002e4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4f9  test    eax, eax
0x18002e4fb  js      short loc_18002E547
0x18002e4fd  mov     rcx, qword ptr [rsp+120h+var_D0]
0x18002e502  mov     rax, [rcx]
0x18002e505  lea     r8, [rbp+4Fh+var_C8]
0x18002e509  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x18002e510  mov     rax, [rax]
0x18002e513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e518  mov     edi, eax
0x18002e51a  mov     rdx, qword ptr [rsp+120h+var_D0]
0x18002e51f  mov     rcx, [rdx]
0x18002e522  mov     rax, [rcx+10h]
0x18002e526  mov     rcx, rdx
0x18002e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e52e  test    edi, edi
0x18002e530  js      short loc_18002E547
0x18002e532  mov     rcx, [rbp+4Fh+var_C8]
0x18002e536  mov     rax, [rcx]
0x18002e539  lea     rdx, [rsp+120h+var_E0]
0x18002e53e  mov     rax, [rax+18h]
0x18002e542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e547  mov     eax, [rsp+120h+var_E0]
0x18002e54b  inc     eax
0x18002e54d  mov     [rsp+120h+var_D0], eax
0x18002e551  movsxd  rsi, eax
0x18002e554  mov     eax, 14h
0x18002e559  mul     rsi
0x18002e55c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002e563  cmovb   rax, r15
0x18002e567  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e56e  mov     rcx, rax; unsigned __int64
0x18002e571  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002e576  mov     rdi, rax
0x18002e579  mov     [rbp+4Fh+var_58], rax
0x18002e57d  lea     eax, [r15+19h]
0x18002e581  mul     rsi
0x18002e584  cmovb   rax, r15
0x18002e588  add     rax, 8
0x18002e58c  cmovb   rax, r15
0x18002e590  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e597  mov     rcx, rax; unsigned __int64
0x18002e59a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002e59f  mov     [rbp+4Fh+var_90], rax
0x18002e5a3  test    rax, rax
0x18002e5a6  jz      loc_18002E87A
0x18002e5ac  mov     [rax], rsi
0x18002e5af  lea     r15, [rax+8]
0x18002e5b3  lea     rax, ??1CPropVariant@@QEAA@XZ; CPropVariant::~CPropVariant(void)
0x18002e5ba  mov     [rsp+120h+var_100], rax; void (*)(void *)
0x18002e5bf  lea     r9, ??0CComPropVariant@@QEAA@XZ; void (*)(void *)
0x18002e5c6  mov     r8, rsi; unsigned __int64
0x18002e5c9  mov     edx, 18h; unsigned __int64
0x18002e5ce  mov     rcx, r15; void *
0x18002e5d1  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002e5d6  nop
0x18002e5d7  mov     [rbp+4Fh+var_90], r15
0x18002e5db  test    rdi, rdi
0x18002e5de  jnz     loc_18002E765
0x18002e5e4  mov     esi, 8007000Eh
0x18002e5e9  jmp     loc_18002E6BE
0x18002e5ee  mov     rcx, [rbp+4Fh+var_A0]
0x18002e5f2  test    rcx, rcx
0x18002e5f5  jz      short loc_18002E604
0x18002e5f7  mov     rax, [rcx]
0x18002e5fa  mov     rax, [rax+10h]
0x18002e5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e603  nop
0x18002e604  mov     rcx, [rsp+120h+ppv]
0x18002e609  test    rcx, rcx
0x18002e60c  jz      short loc_18002E61B
0x18002e60e  mov     rax, [rcx]
0x18002e611  mov     rax, [rax+10h]
0x18002e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e61a  nop
0x18002e61b  test    esi, esi
0x18002e61d  js      loc_18002E6BE
0x18002e623  mov     r12, [rbp+4Fh+var_88]
0x18002e627  movups  xmm0, cs:PKEY_DelegateIDList
0x18002e62e  mov     edx, cs:dword_1800F7098
0x18002e634  movsxd  rax, [rsp+120h+var_E0]
0x18002e639  lea     rcx, [rax+rax*4]
0x18002e63d  movups  xmmword ptr [rdi+rcx*4], xmm0
0x18002e641  mov     [rdi+rcx*4+10h], edx
0x18002e645  movsxd  rax, [rsp+120h+var_E0]
0x18002e64a  lea     rcx, [rax+rax*2]
0x18002e64e  lea     rsi, [r15+rcx*8]
0x18002e652  xorps   xmm0, xmm0
0x18002e655  xor     eax, eax
0x18002e657  movups  xmmword ptr [rsi], xmm0
0x18002e65a  mov     [rsi+10h], rax
0x18002e65e  mov     rcx, r13; pidl
0x18002e661  call    cs:__imp_ILGetSize
0x18002e667  mov     edx, eax; cb
0x18002e669  mov     r8, rsi; ppropvar
0x18002e66c  mov     rcx, r13; pv
0x18002e66f  call    cs:__imp_InitPropVariantFromBuffer
0x18002e675  mov     esi, eax
0x18002e677  test    eax, eax
0x18002e679  js      short loc_18002E6BE
0x18002e67b  lea     rax, [rbp+4Fh+var_C0]
0x18002e67f  mov     [rsp+120h+var_F8], rax; struct _ITEMID_CHILD **
0x18002e684  mov     [rsp+120h+var_100], r15; struct tagPROPVARIANT *
0x18002e689  mov     r9, rdi; struct _tagpropertykey *
0x18002e68c  mov     r8d, [rsp+120h+var_D0]; int
0x18002e691  mov     rdx, [rbp+4Fh+var_80]; struct _ITEMID_CHILD *
0x18002e695  mov     rcx, [rbp+4Fh+var_78]; this
0x18002e699  call    ?_UpdateItem@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@HPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEAPEAU2@@Z; CDBFolder::_UpdateItem(_ITEMID_CHILD const *,int,_tagpropertykey const *,tagPROPVARIANT const *,_ITEMID_CHILD * *)
0x18002e69e  mov     esi, eax
0x18002e6a0  test    eax, eax
0x18002e6a2  js      loc_18002E882
0x18002e6a8  mov     rcx, r14
0x18002e6ab  call    ??$_BindCtx_SetValue@H@@YAJPEAUIBindCtx@@PEBGH@Z; _BindCtx_SetValue<int>(IBindCtx *,ushort const *,int)
0x18002e6b0  mov     rax, [rbp+4Fh+var_C0]
0x18002e6b4  xor     ebx, ebx
0x18002e6b6  mov     [rbp+4Fh+var_C0], rbx
0x18002e6ba  mov     [r12], rax
0x18002e6be  lea     rcx, [rbp+4Fh+var_90]
0x18002e6c2  call    ??1?$CAutoArrayMemPtr@VCComPropVariant@@@@QEAA@XZ; CAutoArrayMemPtr<CComPropVariant>::~CAutoArrayMemPtr<CComPropVariant>(void)
0x18002e6c7  nop
0x18002e6c8  mov     rcx, rdi; lpMem
0x18002e6cb  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x18002e6d0  nop
0x18002e6d1  mov     rcx, [rbp+4Fh+var_C8]
0x18002e6d5  xor     edi, edi
0x18002e6d7  test    rcx, rcx
0x18002e6da  jz      short loc_18002E6E9
0x18002e6dc  mov     rax, [rcx]
0x18002e6df  mov     rax, [rax+10h]
0x18002e6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6e8  nop
0x18002e6e9  mov     rcx, rbx; pv
0x18002e6ec  call    cs:__imp_CoTaskMemFree
0x18002e6f2  nop
0x18002e6f3  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x18002e6f7  call    cs:__imp_PropVariantClear
0x18002e6fd  nop
0x18002e6fe  mov     rcx, r13; pv
0x18002e701  call    cs:__imp_CoTaskMemFree
0x18002e707  nop
0x18002e708  mov     rcx, [rbp+4Fh+pv]; pv
0x18002e70c  mov     [rbp+4Fh+pv], rdi
0x18002e710  call    cs:__imp_CoTaskMemFree
0x18002e716  nop
0x18002e717  mov     rcx, [rbp+4Fh+var_B0]; pv
0x18002e71b  mov     [rbp+4Fh+var_B0], rdi
0x18002e71f  call    cs:__imp_CoTaskMemFree
0x18002e725  nop
0x18002e726  mov     rcx, [rbp+4Fh+var_A8]
0x18002e72a  test    rcx, rcx
0x18002e72d  jz      short loc_18002E73C
0x18002e72f  mov     rax, [rcx]
0x18002e732  mov     rax, [rax+10h]
0x18002e736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e73b  nop
0x18002e73c  mov     eax, esi
0x18002e73e  mov     rcx, [rbp+4Fh+var_38]
0x18002e742  xor     rcx, rsp; StackCookie
0x18002e745  call    __security_check_cookie
0x18002e74a  mov     rbx, [rsp+120h+arg_10]
0x18002e752  add     rsp, 0F0h
0x18002e759  pop     r15
0x18002e75b  pop     r14
0x18002e75d  pop     r13
0x18002e75f  pop     r12
0x18002e761  pop     rdi
0x18002e762  pop     rsi
0x18002e763  pop     rbp
0x18002e764  retn
0x18002e765  test    r15, r15
0x18002e768  jz      loc_18002E5E4
0x18002e76e  mov     rcx, [rbp+4Fh+var_C8]
0x18002e772  test    rcx, rcx
0x18002e775  jz      loc_18002E627
0x18002e77b  xor     r12d, r12d
0x18002e77e  cmp     r12d, [rsp+120h+var_E0]
0x18002e783  jge     short loc_18002E7CD
0x18002e785  xorps   xmm0, xmm0
0x18002e788  xor     eax, eax
0x18002e78a  movups  [rbp+4Fh+var_50], xmm0
0x18002e78e  mov     [rbp+4Fh+var_40], eax
0x18002e791  mov     rax, [rcx]
0x18002e794  lea     r8, [rbp+4Fh+var_50]
0x18002e798  mov     edx, r12d
0x18002e79b  mov     rax, [rax+20h]
0x18002e79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7a4  mov     esi, eax
0x18002e7a6  test    eax, eax
0x18002e7a8  js      loc_18002E6BE
0x18002e7ae  movups  xmm0, [rbp+4Fh+var_50]
0x18002e7b2  mov     edx, [rbp+4Fh+var_40]
0x18002e7b5  movsxd  rax, r12d
0x18002e7b8  lea     rcx, [rax+rax*4]
0x18002e7bc  movups  xmmword ptr [rdi+rcx*4], xmm0
0x18002e7c0  mov     [rdi+rcx*4+10h], edx
0x18002e7c4  inc     r12d
0x18002e7c7  mov     rcx, [rbp+4Fh+var_C8]
0x18002e7cb  jmp     short loc_18002E77E
0x18002e7cd  mov     [rsp+120h+ppv], 0
0x18002e7d6  lea     r8, [rsp+120h+ppv]; ppv
  ... truncated ...
```
