# CScope::_AddScopeTreeItemInternal(IScopeItem *,IScopeItem * *,int *)

- ea: `0x180010cb0`
- end: `0x1800112dd`
- name: `?_AddScopeTreeItemInternal@CScope@@AEAAJPEAUIScopeItem@@PEAPEAU2@PEAH@Z`
- size: `1581`
- prototype: `int(CScope *__hidden this, struct IScopeItem *, struct IScopeItem **, int *)`
- caller_count: `8`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000e980`
- `0x18000f9f0`
- `0x18000fb74`
- `0x18000fd00`
- `0x18000ff10`
- `0x180012440`
- `0x1800b9284`
- `0x1800b9694`

## callees

- `0x1800105f0`
- `0x180010cb0`
- `0x180011ce0`
- `0x18003b150`
- `0x180040b10`
- `0x180047ae0`
- `0x18004c220`
- `0x18004d8f0`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x180010eab`
- `SHCORE!IUnknown_Set` at `0x1800112c6`
- `SHCORE!IUnknown_Set` at `0x180010eab`
- `SHCORE!IUnknown_Set` at `0x1800112c6`
- `Windows.Storage!ILFree` at `0x180010dc3`
- `Windows.Storage!ILFree` at `0x180010e12`
- `Windows.Storage!ILFree` at `0x180010e2b`
- `Windows.Storage!ILFree` at `0x18001110b`
- `Windows.Storage!ILFree` at `0x180011184`
- `Windows.Storage!ILFree` at `0x180010dc3`
- `Windows.Storage!ILFree` at `0x180010e12`
- `Windows.Storage!ILFree` at `0x180010e2b`
- `Windows.Storage!ILFree` at `0x18001110b`
- `Windows.Storage!ILFree` at `0x180011184`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010d46`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010da6`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010e81`
- `Windows.Storage!SHGetIDListFromObject` at `0x18001115c`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010d46`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010da6`
- `Windows.Storage!SHGetIDListFromObject` at `0x180010e81`
- `Windows.Storage!SHGetIDListFromObject` at `0x18001115c`
- `Windows.Storage!SHGetPathFromIDListEx` at `0x180010e9e`
- `Windows.Storage!SHGetPathFromIDListEx` at `0x180010e9e`
- `Windows.Storage!ILIsEqual` at `0x180010db7`
- `Windows.Storage!ILIsEqual` at `0x180010db7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010fa8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010fa8`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180010fc3`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180010fc3`

## string_xrefs

- `0x180010fd7`: `Composition Processor`

## pseudocode

```c
__int64 __fastcall CScope::_AddScopeTreeItemInternal(CScope *this, IUnknown *a2, IUnknown **a3, int *a4)
{
  IUnknown v7; // rax
  __int64 result; // rax
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT inserted; // ebx
  _DWORD *v11; // r15
  int v12; // r12d
  int v13; // r15d
  IUnknown *Ptr; // rax
  const ITEMIDLIST *v15; // rdi
  BOOL v16; // edi
  struct _DPA *v17; // rcx
  CScopeTreeNode *v18; // r12
  LPITEMIDLIST *v19; // rax
  LPITEMIDLIST *v20; // rdi
  IUnknown **v21; // rcx
  IUnknown *v22; // rcx
  HDPA v23; // rax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, LPVOID *); // rcx
  IUnknown *v25; // rbx
  int v26; // eax
  int v27; // r15d
  HRESULT v28; // edi
  struct IUnknownVtbl *v29; // rax
  LPITEMIDLIST v30; // rcx
  int (__fastcall **v31)(LPITEMIDLIST, GUID *, LPITEMIDLIST *); // rax
  int v32; // ebx
  int v33; // eax
  bool v34; // zf
  IUnknown *v35; // rdi
  HDPA v36; // rax
  int IsScopeItemEqualToIDList; // edi
  int i; // r15d
  struct _DPA *v39; // rcx
  int v40; // eax
  const struct _ITEMIDLIST_ABSOLUTE *v41; // rdi
  struct IScopeItem *v42; // rax
  CScope *v43; // rcx
  IUnknown *v44; // rdi
  IUnknown v45; // rax
  struct IUnknownVtbl *v46; // rax
  PVOID v47; // rax
  int v48; // [rsp+30h] [rbp-50h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-48h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-38h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp-30h] BYREF
  LPITEMIDLIST v53; // [rsp+58h] [rbp-28h] BYREF
  __int64 v54; // [rsp+60h] [rbp-20h] BYREF
  LPITEMIDLIST pidl; // [rsp+B8h] [rbp+38h] BYREF
  IUnknown **ppunk; // [rsp+C0h] [rbp+40h]
  IUnknown *v57; // [rsp+C8h] [rbp+48h] BYREF

  ppunk = a3;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v7.lpVtbl = a2->lpVtbl;
  punk = 0;
  result = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))v7.lpVtbl[5].QueryInterface)(
             a2,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &punk);
  if ( (int)result >= 0 )
  {
    lpVtbl = a2->lpVtbl;
    v48 = 0;
    inserted = ((__int64 (__fastcall *)(IUnknown *, int *))lpVtbl[2].Release)(a2, &v48);
    if ( inserted >= 0 )
    {
      if ( *((_QWORD *)this + 9)
        || (inserted = -2147024882, v23 = g_pfn_DPA_Create(8), (*((_QWORD *)this + 9) = v23) != 0) )
      {
        ppidl = 0;
        inserted = SHGetIDListFromObject(a2, &ppidl);
        if ( inserted >= 0 )
        {
          v11 = (_DWORD *)*((_QWORD *)this + 9);
          if ( v11 )
          {
            v12 = 0;
            v13 = *v11 - 1;
            if ( v13 >= 0 )
            {
              do
              {
                if ( v12 )
                  break;
                if ( inserted < 0 )
                  goto LABEL_22;
                Ptr = (IUnknown *)g_pfn_DPA_GetPtr(*((HDPA *)this + 9), (unsigned int)v13);
                v15 = ppidl;
                v57 = Ptr;
                pidl = 0;
                if ( SHGetIDListFromObject(Ptr, &pidl) >= 0 )
                {
                  v16 = ILIsEqual(pidl, v15);
                  ILFree(pidl);
                  if ( v16 )
                  {
                    v44 = v57;
                    if ( ((unsigned int (__fastcall *)(IUnknown *, IUnknown *, _QWORD))a2->lpVtbl[4].AddRef)(a2, v57, 0) )
                    {
                      v45.lpVtbl = a2->lpVtbl;
                      v12 = 0;
                      LODWORD(v57) = 0;
                      inserted = ((__int64 (__fastcall *)(IUnknown *, IUnknown **))v45.lpVtbl[1].AddRef)(a2, &v57);
                      if ( inserted >= 0 )
                      {
                        v46 = v44->lpVtbl;
                        LODWORD(pidl) = 0;
                        inserted = ((__int64 (__fastcall *)(IUnknown *, LPITEMIDLIST *))v46[1].AddRef)(v44, &pidl);
                        if ( inserted >= 0 && (_DWORD)v57 != (_DWORD)pidl )
                        {
                          v47 = g_pfn_DPA_DeletePtr(*((HDPA *)this + 9), v13);
                          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v47 + 16LL))(v47);
                        }
                      }
                    }
                    else
                    {
                      v12 = 1;
                    }
                  }
                }
                --v13;
              }
              while ( v13 >= 0 );
              if ( inserted < 0 || v12 )
                goto LABEL_22;
            }
          }
          v17 = (struct _DPA *)*((_QWORD *)this + 9);
          if ( v17 && (inserted = -2147467259, *(int *)v17 >= 64) )
          {
LABEL_22:
            ILFree(ppidl);
            if ( inserted >= 0 )
            {
LABEL_23:
              if ( (v48 & 2) != 0 )
                goto LABEL_24;
              v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 12);
              v25 = punk;
              ppv = 0;
              v26 = v24
                  ? (**v24)(v24, &GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534, &ppv)
                  : CoCreateInstance(
                      &GUID_db6efb73_5153_43b7_8078_c6ffc4c0238c,
                      0,
                      1u,
                      &GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534,
                      &ppv);
              if ( v26 < 0 )
                goto LABEL_24;
              ppbc = 0;
              v27 = 0;
              v28 = CreateBindCtx(0, &ppbc);
              if ( v28 >= 0 )
              {
                v28 = ((__int64 (__fastcall *)(LPBC, const WCHAR *, LPVOID))ppbc->lpVtbl->RegisterObjectParam)(
                        ppbc,
                        L"Composition Processor",
                        ppv);
                if ( v28 >= 0 )
                {
                  v29 = v25->lpVtbl;
                  ppidl = 0;
                  v28 = ((__int64 (__fastcall *)(IUnknown *, LPBC, const GUID *, GUID *, LPITEMIDLIST *))v29[1].QueryInterface)(
                          v25,
                          ppbc,
                          &BHID_SFObject,
                          &GUID_000214e6_0000_0000_c000_000000000046,
                          &ppidl);
                  if ( v28 >= 0 )
                  {
                    v30 = ppidl;
                    v54 = 0;
                    if ( ppidl )
                    {
                      v31 = *(int (__fastcall ***)(LPITEMIDLIST, GUID *, LPITEMIDLIST *))&ppidl->mkid.cb;
                      v53 = 0;
                      if ( (*v31)(ppidl, &GUID_a6087428_3be3_4d73_b308_7c04a540bf1a, &v53) >= 0 )
                      {
                        v32 = (*(__int64 (__fastcall **)(LPITEMIDLIST, GUID *, GUID *, __int64 *))(*(_QWORD *)&v53->mkid.cb
                                                                                                 + 24LL))(
                                v53,
                                &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
                                &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                &v54);
                        (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v53->mkid.cb + 16LL))(v53);
                        if ( v32 >= 0 )
                        {
                          v27 = 1;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
                        }
                      }
                      v30 = ppidl;
                    }
                    (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v30->mkid.cb + 16LL))(v30);
                  }
                }
                ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              v33 = 0;
              if ( v28 >= 0 )
                v33 = v27;
              if ( v33 )
              {
                v34 = *((_QWORD *)this + 10) == 0;
                v35 = punk;
                v57 = 0;
                LODWORD(pidl) = 0;
                if ( !v34 || (inserted = -2147024882, v36 = g_pfn_DPA_Create(8), (*((_QWORD *)this + 10) = v36) != 0) )
                {
                  v53 = 0;
                  if ( SHGetIDListFromObject(v35, &v53) < 0 )
                    goto LABEL_65;
                  IsScopeItemEqualToIDList = 0;
                  inserted = 1;
                  for ( i = 0; ; ++i )
                  {
                    v39 = (struct _DPA *)*((_QWORD *)this + 10);
                    v40 = v39 ? *(_DWORD *)v39 : 0;
                    if ( i >= v40 || IsScopeItemEqualToIDList )
                      break;
                    v41 = (const struct _ITEMIDLIST_ABSOLUTE *)v53;
                    v42 = (struct IScopeItem *)g_pfn_DPA_GetPtr(v39, i);
                    IsScopeItemEqualToIDList = CScope::_IsScopeItemEqualToIDList(v43, v42, v41);
                  }
                  ILFree(v53);
                  if ( !IsScopeItemEqualToIDList )
                  {
LABEL_65:
                    if ( DPA_InsertPtr(*((HDPA *)this + 10), 0x7FFFFFFF, a2) == -1 )
                    {
                      inserted = -2147024882;
                    }
                    else
                    {
                      inserted = 0;
                      ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
                    }
                  }
                }
              }
              else
              {
LABEL_24:
                v18 = (CScopeTreeNode *)*((_QWORD *)this + 11);
                v57 = 0;
                LODWORD(pidl) = 0;
                inserted = -2147024882;
                v19 = (LPITEMIDLIST *)operator new(0x228u, (const struct std::nothrow_t *)&std::nothrow);
                v20 = v19;
                if ( v19 )
                {
                  *(_DWORD *)v19 = 1;
                  v19[3] = 0;
                  inserted = SHGetIDListFromObject(a2, v19 + 2);
                  if ( inserted >= 0 )
                  {
                    SHGetPathFromIDListEx(v20[2], (PWSTR)v20 + 16, 0x104u, 0);
                    IUnknown_Set((IUnknown **)v20 + 1, a2);
                    _InterlockedIncrement((volatile signed __int32 *)v20);
                    CScopeTreeNode::Release((CScopeTreeNode *)v20);
                    inserted = CScopeTreeNode::InsertSubTree(
                                 v18,
                                 (struct CScopeTreeNode *)v20,
                                 0,
                                 (struct IScopeItem **)&v57,
                                 (int *)&pidl);
                  }
                  CScopeTreeNode::Release((CScopeTreeNode *)v20);
                }
              }
              if ( !inserted )
              {
                v21 = ppunk;
                *(GUID *)((char *)this + 52) = GUID_NULL;
                if ( v21 )
                  IUnknown_Set(v21, v57);
                if ( a4 )
                  *a4 = (int)pidl;
                v22 = v57;
                v57 = 0;
                if ( v22 )
                  ((void (__fastcall *)(IUnknown *))v22->lpVtbl->Release)(v22);
              }
            }
          }
          else
          {
            *((_DWORD *)this + 12) = 1;
            if ( DPA_InsertPtr(v17, 0x7FFFFFFF, a2) != -1 )
            {
              ((void (__fastcall *)(IUnknown *))a2->lpVtbl->AddRef)(a2);
              ILFree(ppidl);
              goto LABEL_23;
            }
            inserted = -2147024882;
            ILFree(ppidl);
          }
        }
      }
    }
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    return (unsigned int)inserted;
  }
  return result;
}

```

## disassembly

```asm
0x180010cb0  mov     [rsp-28h+ppunk], r8
0x180010cb5  push    rbp
0x180010cb6  push    rsi
0x180010cb7  push    rdi
0x180010cb8  push    r13
0x180010cba  push    r14
0x180010cbc  mov     rbp, rsp
0x180010cbf  sub     rsp, 80h
0x180010cc6  xor     edi, edi
0x180010cc8  mov     r13, r9
0x180010ccb  mov     r14, rdx
0x180010cce  mov     rsi, rcx
0x180010cd1  test    r8, r8
0x180010cd4  jnz     loc_180011215
0x180010cda  test    r13, r13
0x180010cdd  jnz     loc_18001121D
0x180010ce3  mov     rax, [rdx]
0x180010ce6  lea     r8, [rbp+punk]
0x180010cea  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180010cf1  mov     [rbp+punk], rdi
0x180010cf5  mov     rcx, r14
0x180010cf8  mov     rax, [rax+78h]
0x180010cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d01  test    eax, eax
0x180010d03  js      loc_180010F47
0x180010d09  mov     rax, [r14]
0x180010d0c  lea     rdx, [rbp+var_50]
0x180010d10  mov     rcx, r14
0x180010d13  mov     [rsp+80h+arg_0], rbx
0x180010d1b  mov     [rbp+var_50], edi
0x180010d1e  mov     rax, [rax+40h]
0x180010d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d27  mov     ebx, eax
0x180010d29  test    eax, eax
0x180010d2b  js      loc_180010F2D
0x180010d31  cmp     [rsi+48h], rdi
0x180010d35  jz      loc_180010F56
0x180010d3b  lea     rdx, [rbp+ppidl]; ppidl
0x180010d3f  mov     [rbp+ppidl], rdi
0x180010d43  mov     rcx, r14; punk
0x180010d46  call    cs:__imp_SHGetIDListFromObject
0x180010d4c  mov     ebx, eax
0x180010d4e  test    eax, eax
0x180010d50  js      loc_180010F2D
0x180010d56  mov     [rsp+80h+var_10], r15
0x180010d5b  mov     r15, [rsi+48h]
0x180010d5f  mov     [rsp+80h+var_8], r12
0x180010d64  test    r15, r15
0x180010d67  jz      short loc_180010DE2
0x180010d69  mov     r15d, [r15]
0x180010d6c  mov     r12d, edi
0x180010d6f  sub     r15d, 1
0x180010d73  js      short loc_180010DE2
0x180010d75  test    r12d, r12d
0x180010d78  jnz     short loc_180010DD7
0x180010d7a  test    ebx, ebx
0x180010d7c  js      loc_1800111E8
0x180010d82  mov     rcx, [rsi+48h]; hdpa
0x180010d86  mov     edx, r15d; i
0x180010d89  call    cs:g_pfn_DPA_GetPtr
0x180010d8f  mov     rdi, [rbp+ppidl]
0x180010d93  lea     rdx, [rbp+pidl]; ppidl
0x180010d97  mov     rcx, rax; punk
0x180010d9a  mov     [rbp+arg_18], rax
0x180010d9e  mov     [rbp+pidl], 0
0x180010da6  call    cs:__imp_SHGetIDListFromObject
0x180010dac  test    eax, eax
0x180010dae  js      short loc_180010DD1
0x180010db0  mov     rcx, [rbp+pidl]; pidl1
0x180010db4  mov     rdx, rdi; pidl2
0x180010db7  call    cs:__imp_ILIsEqual
0x180010dbd  mov     rcx, [rbp+pidl]; pidl
0x180010dc1  mov     edi, eax
0x180010dc3  call    cs:__imp_ILFree
0x180010dc9  test    edi, edi
0x180010dcb  jnz     loc_180011225
0x180010dd1  sub     r15d, 1
0x180010dd5  jns     short loc_180010D75
0x180010dd7  xor     edi, edi
0x180010dd9  test    ebx, ebx
0x180010ddb  js      short loc_180010E27
0x180010ddd  test    r12d, r12d
0x180010de0  jnz     short loc_180010E27
0x180010de2  mov     rcx, [rsi+48h]; hdpa
0x180010de6  test    rcx, rcx
0x180010de9  jnz     short loc_180010E1D
0x180010deb  mov     r8, r14; p
0x180010dee  mov     dword ptr [rsi+30h], 1
0x180010df5  mov     edx, 7FFFFFFFh; i
0x180010dfa  call    cs:__imp_DPA_InsertPtr
0x180010e00  cmp     eax, 0FFFFFFFFh
0x180010e03  jnz     loc_1800110F8
0x180010e09  mov     rcx, [rbp+ppidl]; pidl
0x180010e0d  mov     ebx, 8007000Eh
0x180010e12  call    cs:__imp_ILFree
0x180010e18  jmp     loc_180010F23
0x180010e1d  cmp     dword ptr [rcx], 40h ; '@'
0x180010e20  mov     ebx, 80004005h
0x180010e25  jl      short loc_180010DEB
0x180010e27  mov     rcx, [rbp+ppidl]; pidl
0x180010e2b  call    cs:__imp_ILFree
0x180010e31  test    ebx, ebx
0x180010e33  js      loc_180010F23
0x180010e39  test    byte ptr [rbp+var_50], 2
0x180010e3d  jz      loc_180010F74
0x180010e43  mov     r12, [rsi+58h]
0x180010e47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010e4e  mov     ecx, 228h; unsigned __int64
0x180010e53  mov     [rbp+arg_18], rdi
0x180010e57  mov     dword ptr [rbp+pidl], edi
0x180010e5a  mov     ebx, 8007000Eh
0x180010e5f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010e64  mov     rdi, rax
0x180010e67  test    rax, rax
0x180010e6a  jz      short loc_180010EE1
0x180010e6c  mov     dword ptr [rax], 1
0x180010e72  lea     rdx, [rax+10h]; ppidl
0x180010e76  mov     rcx, r14; punk
0x180010e79  mov     qword ptr [rax+18h], 0
0x180010e81  call    cs:__imp_SHGetIDListFromObject
0x180010e87  mov     ebx, eax
0x180010e89  test    eax, eax
0x180010e8b  js      short loc_180010ED9
0x180010e8d  mov     rcx, [rdi+10h]; pidl
0x180010e91  lea     rdx, [rdi+20h]; pszPath
0x180010e95  xor     r9d, r9d; uOpts
0x180010e98  mov     r8d, 104h; cchPath
0x180010e9e  call    cs:__imp_SHGetPathFromIDListEx
0x180010ea4  lea     rcx, [rdi+8]; ppunk
0x180010ea8  mov     rdx, r14; punk
0x180010eab  call    cs:__imp_IUnknown_Set
0x180010eb1  lock inc dword ptr [rdi]
0x180010eb4  mov     rcx, rdi; this
0x180010eb7  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x180010ebc  lea     rax, [rbp+pidl]
0x180010ec0  xor     r8d, r8d; int
0x180010ec3  lea     r9, [rbp+arg_18]; struct IScopeItem **
0x180010ec7  mov     [rsp+80h+ppv], rax; int *
0x180010ecc  mov     rdx, rdi; struct CScopeTreeNode *
0x180010ecf  mov     rcx, r12; this
0x180010ed2  call    ?InsertSubTree@CScopeTreeNode@@IEAAJPEAV1@HPEAPEAUIScopeItem@@PEAH@Z; CScopeTreeNode::InsertSubTree(CScopeTreeNode *,int,IScopeItem * *,int *)
0x180010ed7  mov     ebx, eax
0x180010ed9  mov     rcx, rdi; this
0x180010edc  call    ?Release@CScopeTreeNode@@QEAAXXZ; CScopeTreeNode::Release(void)
0x180010ee1  test    ebx, ebx
0x180010ee3  jnz     short loc_180010F23
0x180010ee5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010eec  mov     rcx, [rbp+ppunk]; ppunk
0x180010ef0  movups  xmmword ptr [rsi+34h], xmm0
0x180010ef4  test    rcx, rcx
0x180010ef7  jnz     loc_1800112C2
0x180010efd  test    r13, r13
0x180010f00  jnz     loc_1800112D1
0x180010f06  mov     rcx, [rbp+arg_18]
0x180010f0a  mov     [rbp+arg_18], 0
0x180010f12  test    rcx, rcx
0x180010f15  jz      short loc_180010F23
0x180010f17  mov     rax, [rcx]
0x180010f1a  mov     rax, [rax+10h]
0x180010f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f23  mov     r12, [rsp+80h+var_8]
0x180010f28  mov     r15, [rsp+80h+var_10]
0x180010f2d  mov     rcx, [rbp+punk]
0x180010f31  mov     rax, [rcx]
0x180010f34  mov     rax, [rax+10h]
0x180010f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f3d  mov     eax, ebx
0x180010f3f  mov     rbx, [rsp+80h+arg_0]
0x180010f47  add     rsp, 80h
0x180010f4e  pop     r14
0x180010f50  pop     r13
0x180010f52  pop     rdi
0x180010f53  pop     rsi
0x180010f54  pop     rbp
0x180010f55  retn
0x180010f56  mov     ecx, 8; cItemGrow
0x180010f5b  mov     ebx, 8007000Eh
0x180010f60  call    cs:g_pfn_DPA_Create
0x180010f66  mov     [rsi+48h], rax
0x180010f6a  test    rax, rax
0x180010f6d  jz      short loc_180010F2D
0x180010f6f  jmp     loc_180010D3B
0x180010f74  mov     rcx, [rsi+60h]
0x180010f78  mov     rbx, [rbp+punk]
0x180010f7c  mov     [rbp+var_38], rdi
0x180010f80  test    rcx, rcx
0x180010f83  jnz     loc_1800111CD
0x180010f89  lea     rax, [rbp+var_38]
0x180010f8d  xor     edx, edx; pUnkOuter
0x180010f8f  lea     r9, _GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534; riid
0x180010f96  mov     [rsp+80h+ppv], rax; ppv
0x180010f9b  mov     r8d, 1; dwClsContext
0x180010fa1  lea     rcx, _GUID_db6efb73_5153_43b7_8078_c6ffc4c0238c; rclsid
0x180010fa8  call    cs:__imp_CoCreateInstance
0x180010fae  test    eax, eax
0x180010fb0  js      loc_180010E43
0x180010fb6  lea     rdx, [rbp+ppbc]; ppbc
0x180010fba  mov     [rbp+ppbc], rdi
0x180010fbe  xor     ecx, ecx; reserved
0x180010fc0  mov     r15d, edi
0x180010fc3  call    cs:__imp_CreateBindCtx
0x180010fc9  mov     edi, eax
0x180010fcb  test    eax, eax
0x180010fcd  js      loc_1800110D5
0x180010fd3  mov     rcx, [rbp+ppbc]
0x180010fd7  lea     rdx, aCompositionPro; "Composition Processor"
0x180010fde  mov     r8, [rbp+var_38]
0x180010fe2  mov     rax, [rcx]
0x180010fe5  mov     rax, [rax+48h]
0x180010fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fee  mov     edi, eax
0x180010ff0  test    eax, eax
0x180010ff2  js      loc_1800110C5
0x180010ff8  mov     rax, [rbx]
0x180010ffb  lea     rcx, [rbp+ppidl]
0x180010fff  mov     rdx, [rbp+ppbc]
0x180011003  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18001100a  mov     [rsp+80h+ppv], rcx
0x18001100f  lea     r8, BHID_SFObject
0x180011016  mov     rcx, rbx
0x180011019  mov     [rbp+ppidl], 0
0x180011021  mov     rax, [rax+18h]
0x180011025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102a  mov     edi, eax
0x18001102c  test    eax, eax
0x18001102e  js      loc_1800110C5
0x180011034  mov     rcx, [rbp+ppidl]
0x180011038  mov     [rbp+var_20], 0
0x180011040  test    rcx, rcx
0x180011043  jz      short loc_1800110B9
0x180011045  mov     rax, [rcx]
0x180011048  lea     r8, [rbp+var_28]
0x18001104c  lea     rdx, _GUID_a6087428_3be3_4d73_b308_7c04a540bf1a
0x180011053  mov     [rbp+var_28], 0
0x18001105b  mov     rax, [rax]
0x18001105e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011063  test    eax, eax
0x180011065  js      short loc_1800110B5
0x180011067  mov     rcx, [rbp+var_28]
0x18001106b  lea     r9, [rbp+var_20]
0x18001106f  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180011076  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82
0x18001107d  mov     rax, [rcx]
0x180011080  mov     rax, [rax+18h]
0x180011084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011089  mov     rcx, [rbp+var_28]
0x18001108d  mov     ebx, eax
0x18001108f  mov     rdx, [rcx]
0x180011092  mov     rax, [rdx+10h]
0x180011096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001109b  test    ebx, ebx
0x18001109d  js      short loc_1800110B5
0x18001109f  mov     rcx, [rbp+var_20]
0x1800110a3  mov     r15d, 1
0x1800110a9  mov     rax, [rcx]
0x1800110ac  mov     rax, [rax+10h]
0x1800110b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110b5  mov     rcx, [rbp+ppidl]
0x1800110b9  mov     rax, [rcx]
0x1800110bc  mov     rax, [rax+10h]
0x1800110c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110c5  mov     rcx, [rbp+ppbc]
0x1800110c9  mov     rax, [rcx]
0x1800110cc  mov     rax, [rax+10h]
0x1800110d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d5  mov     rcx, [rbp+var_38]
0x1800110d9  mov     rax, [rcx]
0x1800110dc  mov     rax, [rax+10h]
0x1800110e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e5  xor     eax, eax
0x1800110e7  test    edi, edi
0x1800110e9  cmovns  eax, r15d
0x1800110ed  test    eax, eax
0x1800110ef  jnz     short loc_180011116
0x1800110f1  xor     edi, edi
0x1800110f3  jmp     loc_180010E43
0x1800110f8  mov     rax, [r14]
0x1800110fb  mov     rcx, r14
0x1800110fe  mov     rax, [rax+8]
0x180011102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011107  mov     rcx, [rbp+ppidl]; pidl
0x18001110b  call    cs:__imp_ILFree
0x180011111  jmp     loc_180010E39
0x180011116  cmp     qword ptr [rsi+50h], 0
0x18001111b  mov     rdi, [rbp+punk]
0x18001111f  mov     [rbp+arg_18], 0
0x180011127  mov     dword ptr [rbp+pidl], 0
0x18001112e  jnz     short loc_18001114D
0x180011130  mov     ecx, 8; cItemGrow
0x180011135  mov     ebx, 8007000Eh
0x18001113a  call    cs:g_pfn_DPA_Create
0x180011140  mov     [rsi+50h], rax
0x180011144  test    rax, rax
0x180011147  jz      loc_180010EE1
0x18001114d  lea     rdx, [rbp+var_28]; ppidl
0x180011151  mov     [rbp+var_28], 0
0x180011159  mov     rcx, rdi; punk
0x18001115c  call    cs:__imp_SHGetIDListFromObject
0x180011162  test    eax, eax
0x180011164  js      short loc_180011192
  ... truncated ...
```
