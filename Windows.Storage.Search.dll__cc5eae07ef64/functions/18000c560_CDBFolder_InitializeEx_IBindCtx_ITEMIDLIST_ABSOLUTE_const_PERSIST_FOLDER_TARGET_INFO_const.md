# CDBFolder::InitializeEx(IBindCtx *,_ITEMIDLIST_ABSOLUTE const *,_PERSIST_FOLDER_TARGET_INFO const *)

- ea: `0x18000c560`
- end: `0x18000c907`
- name: `?InitializeEx@CDBFolder@@UEAAJPEAUIBindCtx@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBU_PERSIST_FOLDER_TARGET_INFO@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CDBFolder *__hidden this, struct IBindCtx *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _PERSIST_FOLDER_TARGET_INFO *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180006ca8`
- `0x18000ac10`
- `0x18000c560`
- `0x180045fe0`
- `0x18007dab0`
- `0x180082d5c`
- `0x180084270`
- `0x18008d228`
- `0x18008d2e0`
- `0x1800c1ff8`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18000c7af`
- `SHCORE!IUnknown_Set` at `0x18000c7af`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18000c590`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18000c590`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c8bf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c8bf`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x18000c8ab`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x18000c8ab`

## string_xrefs

- `0x18000c82c`: `Composition Processor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CDBFolder::InitializeEx(
        CDBFolder *this,
        struct IBindCtx *a2,
        const ITEMIDLIST *a3,
        const struct _PERSIST_FOLDER_TARGET_INFO *a4)
{
  HRESULT result; // eax
  void *v8; // r14
  int v9; // edi
  int ListDescriptionForItem; // edi
  IUnknown *v11; // rdi
  void *v12; // rcx
  int v13; // edi
  char *v14; // rdi
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  HWND UIWindow; // r14
  HINSTANCE v19; // rax
  HINSTANCE v20; // rax
  IUnknown *punk; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  HMODULE hLibModule; // [rsp+40h] [rbp-20h] BYREF
  void *v24; // [rsp+48h] [rbp-18h] BYREF
  void *ppv; // [rsp+50h] [rbp-10h] BYREF

  ppv = 0;
  result = SHCreateItemFromIDList(a3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( result >= 0 )
  {
    v8 = ppv;
    punk = 0;
    v22 = 0;
    hLibModule = 0;
    if ( !a2
      || ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HMODULE *))a2->lpVtbl->GetObjectParam)(
           a2,
           L"FolderDefinitionData",
           &hLibModule) < 0
      || (v9 = (**(__int64 (__fastcall ***)(HMODULE, GUID *, __int64 *))hLibModule)(
                 hLibModule,
                 &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                 &v22),
          (*(void (__fastcall **)(HMODULE))(*(_QWORD *)hLibModule + 16LL))(hLibModule),
          v9 < 0) )
    {
      v24 = 0;
      GetObjectFromBindCtx(a2, L"Composition Processor", &GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534, &v24);
      ListDescriptionForItem = GetListDescriptionForItem(v8, v24, v17, &v22);
      if ( ListDescriptionForItem < 0 )
      {
        UIWindow = BindCtx_GetUIWindow(a2);
        if ( UIWindow )
        {
          hLibModule = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
          {
            v19 = SearchFolderInstance::get(&hLibModule);
            MessageBoxHelper::ShellMessageBoxTextScaled__(v19, UIWindow);
          }
          else
          {
            v20 = SearchFolderInstance::get(&hLibModule);
            ShellMessageBoxW(v20, UIWindow, (LPCWSTR)0x9571, 0, 0x10u);
          }
          if ( hLibModule )
            FreeLibrary(hLibModule);
        }
      }
      SafeRelease<IShellItemArray>((__int64 *)&v24);
      if ( ListDescriptionForItem < 0 )
        goto LABEL_21;
    }
    ListDescriptionForItem = (**(__int64 (__fastcall ***)(__int64, GUID *, IUnknown **))v22)(
                               v22,
                               &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                               &punk);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( ListDescriptionForItem < 0 )
      goto LABEL_21;
    v11 = punk;
    v24 = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, void **))punk->lpVtbl->QueryInterface)(
           punk,
           &GUID_000214ea_0000_0000_c000_000000000046,
           &v24) >= 0 )
    {
      (*(void (__fastcall **)(void *, const ITEMIDLIST *))(*(_QWORD *)v24 + 32LL))(v24, a3);
      v12 = v24;
    }
    else
    {
      hLibModule = 0;
      if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, HMODULE *))v11->lpVtbl->QueryInterface)(
             v11,
             &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
             &hLibModule) < 0 )
      {
LABEL_10:
        *((_QWORD *)this + 35) = 0;
        v24 = 0;
        if ( a2
          && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void **))a2->lpVtbl->GetObjectParam)(
               a2,
               L"AutolistVisibleIn",
               &v24) >= 0
          && (v13 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v24)(
                      v24,
                      &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                      (char *)this + 280),
              (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24),
              v13 >= 0) )
        {
          v14 = (char *)this + 288;
          *((_DWORD *)this + 72) = 0;
          hLibModule = 0;
          v22 = 0;
        }
        else
        {
          ListDescriptionForItem = ((__int64 (__fastcall *)(IUnknown *, GUID *, char *))punk->lpVtbl[4].Release)(
                                     punk,
                                     &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                                     (char *)this + 280);
          if ( ListDescriptionForItem < 0 )
          {
LABEL_19:
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
LABEL_21:
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            return ListDescriptionForItem;
          }
          v14 = (char *)this + 288;
          *((_DWORD *)this + 72) = 0;
          hLibModule = 0;
          v22 = 0;
          if ( !a2 )
          {
LABEL_18:
            IUnknown_Set((IUnknown **)this + 32, punk);
            ListDescriptionForItem = CDBFolder::Initialize(this, a3);
            goto LABEL_19;
          }
        }
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))a2->lpVtbl->GetObjectParam)(
               a2,
               L"ProgressAggregatorProvider",
               &v22) >= 0 )
        {
          v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, HMODULE *))v22)(
                  v22,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  &hLibModule);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v15 >= 0 )
          {
            IUnknown_GetCookieFromProvider(hLibModule, v16, v14);
            (*(void (__fastcall **)(HMODULE))(*(_QWORD *)hLibModule + 16LL))(hLibModule);
          }
        }
        goto LABEL_18;
      }
      (*(void (__fastcall **)(HMODULE, const ITEMIDLIST *))(*(_QWORD *)hLibModule + 32LL))(hLibModule, a3);
      v12 = hLibModule;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x18000c560  push    rbp
0x18000c562  push    rbx
0x18000c563  push    rsi
0x18000c564  push    rdi
0x18000c565  push    r12
0x18000c567  push    r14
0x18000c569  push    r15
0x18000c56b  mov     rbp, rsp
0x18000c56e  sub     rsp, 60h
0x18000c572  mov     r15, r8
0x18000c575  mov     rbx, rdx
0x18000c578  mov     rsi, rcx
0x18000c57b  xor     r12d, r12d
0x18000c57e  mov     [rbp+ppv], r12
0x18000c582  lea     r8, [rbp+ppv]; ppv
0x18000c586  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000c58d  mov     rcx, r15; pidl
0x18000c590  call    cs:__imp_SHCreateItemFromIDList
0x18000c596  test    eax, eax
0x18000c598  js      loc_18000C7F7
0x18000c59e  mov     r14, [rbp+ppv]
0x18000c5a2  mov     [rbp+punk], r12
0x18000c5a6  mov     [rbp+var_28], r12
0x18000c5aa  mov     [rbp+hLibModule], r12
0x18000c5ae  test    rbx, rbx
0x18000c5b1  jz      loc_18000C81D
0x18000c5b7  mov     rax, [rbx]
0x18000c5ba  lea     r8, [rbp+hLibModule]
0x18000c5be  lea     rdx, aFolderdefiniti; "FolderDefinitionData"
0x18000c5c5  mov     rcx, rbx
0x18000c5c8  mov     rax, [rax+50h]
0x18000c5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5d1  test    eax, eax
0x18000c5d3  js      loc_18000C81D
0x18000c5d9  mov     rcx, [rbp+hLibModule]
0x18000c5dd  mov     rax, [rcx]
0x18000c5e0  lea     r8, [rbp+var_28]
0x18000c5e4  lea     rdx, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18000c5eb  mov     rax, [rax]
0x18000c5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5f3  mov     edi, eax
0x18000c5f5  mov     rcx, [rbp+hLibModule]
0x18000c5f9  mov     rdx, [rcx]
0x18000c5fc  mov     rax, [rdx+10h]
0x18000c600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c605  test    edi, edi
0x18000c607  js      loc_18000C81D
0x18000c60d  mov     rcx, [rbp+var_28]
0x18000c611  mov     rax, [rcx]
0x18000c614  lea     r8, [rbp+punk]
0x18000c618  lea     rdx, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18000c61f  mov     rax, [rax]
0x18000c622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c627  mov     edi, eax
0x18000c629  mov     rcx, [rbp+var_28]
0x18000c62d  mov     rax, [rcx]
0x18000c630  mov     rax, [rax+10h]
0x18000c634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c639  test    edi, edi
0x18000c63b  js      loc_18000C7E5
0x18000c641  mov     rdi, [rbp+punk]
0x18000c645  mov     [rbp+var_18], r12
0x18000c649  mov     rax, [rdi]
0x18000c64c  lea     r8, [rbp+var_18]
0x18000c650  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x18000c657  mov     rcx, rdi
0x18000c65a  mov     rax, [rax]
0x18000c65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c662  test    eax, eax
0x18000c664  jns     loc_18000C8CA
0x18000c66a  mov     [rbp+hLibModule], r12
0x18000c66e  mov     rax, [rdi]
0x18000c671  lea     r8, [rbp+hLibModule]
0x18000c675  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x18000c67c  mov     rcx, rdi
0x18000c67f  mov     rax, [rax]
0x18000c682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c687  test    eax, eax
0x18000c689  js      short loc_18000C6AE
0x18000c68b  mov     rcx, [rbp+hLibModule]
0x18000c68f  mov     rax, [rcx]
0x18000c692  mov     rdx, r15
0x18000c695  mov     rax, [rax+20h]
0x18000c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c69e  mov     rcx, [rbp+hLibModule]
0x18000c6a2  mov     rax, [rcx]
0x18000c6a5  mov     rax, [rax+10h]
0x18000c6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ae  mov     [rsi+118h], r12
0x18000c6b5  mov     [rbp+var_18], r12
0x18000c6b9  test    rbx, rbx
0x18000c6bc  jz      short loc_18000C713
0x18000c6be  mov     rax, [rbx]
0x18000c6c1  lea     r8, [rbp+var_18]
0x18000c6c5  lea     rdx, aAutolistvisibl; "AutolistVisibleIn"
0x18000c6cc  mov     rcx, rbx
0x18000c6cf  mov     rax, [rax+50h]
0x18000c6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d8  test    eax, eax
0x18000c6da  js      short loc_18000C713
0x18000c6dc  mov     rcx, [rbp+var_18]
0x18000c6e0  mov     rax, [rcx]
0x18000c6e3  lea     r8, [rsi+118h]
0x18000c6ea  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x18000c6f1  mov     rax, [rax]
0x18000c6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f9  mov     edi, eax
0x18000c6fb  mov     rcx, [rbp+var_18]
0x18000c6ff  mov     rdx, [rcx]
0x18000c702  mov     rax, [rdx+10h]
0x18000c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c70b  test    edi, edi
0x18000c70d  jns     loc_18000C806
0x18000c713  mov     rcx, [rbp+punk]
0x18000c717  mov     rax, [rcx]
0x18000c71a  lea     r8, [rsi+118h]
0x18000c721  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x18000c728  mov     rax, [rax+70h]
0x18000c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c731  mov     edi, eax
0x18000c733  test    eax, eax
0x18000c735  js      loc_18000C7C2
0x18000c73b  lea     rdi, [rsi+120h]
0x18000c742  mov     [rdi], r12d
0x18000c745  mov     [rbp+hLibModule], r12
0x18000c749  mov     [rbp+var_28], r12
0x18000c74d  test    rbx, rbx
0x18000c750  jz      short loc_18000C7A4
0x18000c752  mov     rax, [rbx]
0x18000c755  lea     r8, [rbp+var_28]
0x18000c759  lea     rdx, aProgressaggreg; "ProgressAggregatorProvider"
0x18000c760  mov     rcx, rbx
0x18000c763  mov     rax, [rax+50h]
0x18000c767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c76c  test    eax, eax
0x18000c76e  js      short loc_18000C7A4
0x18000c770  mov     rcx, [rbp+var_28]
0x18000c774  mov     rax, [rcx]
0x18000c777  lea     r8, [rbp+hLibModule]
0x18000c77b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c782  mov     rax, [rax]
0x18000c785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c78a  mov     ebx, eax
0x18000c78c  mov     rcx, [rbp+var_28]
0x18000c790  mov     rdx, [rcx]
0x18000c793  mov     rax, [rdx+10h]
0x18000c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79c  test    ebx, ebx
0x18000c79e  jns     loc_18000C8E6
0x18000c7a4  lea     rcx, [rsi+100h]; ppunk
0x18000c7ab  mov     rdx, [rbp+punk]; punk
0x18000c7af  call    cs:__imp_IUnknown_Set
0x18000c7b5  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x18000c7b8  mov     rcx, rsi; this
0x18000c7bb  call    ?Initialize@CDBFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CDBFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)
0x18000c7c0  mov     edi, eax
0x18000c7c2  mov     rcx, [rbp+punk]
0x18000c7c6  mov     rax, [rcx]
0x18000c7c9  mov     rax, [rax+10h]
0x18000c7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d2  jmp     short loc_18000C7E5
0x18000c7d4  lea     rcx, [rbp+var_18]
0x18000c7d8  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18000c7dd  test    edi, edi
0x18000c7df  jns     loc_18000C60D
0x18000c7e5  mov     rcx, [rbp+ppv]
0x18000c7e9  mov     rax, [rcx]
0x18000c7ec  mov     rax, [rax+10h]
0x18000c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f5  mov     eax, edi
0x18000c7f7  add     rsp, 60h
0x18000c7fb  pop     r15
0x18000c7fd  pop     r14
0x18000c7ff  pop     r12
0x18000c801  pop     rdi
0x18000c802  pop     rsi
0x18000c803  pop     rbx
0x18000c804  pop     rbp
0x18000c805  retn
0x18000c806  lea     rdi, [rsi+120h]
0x18000c80d  mov     [rdi], r12d
0x18000c810  mov     [rbp+hLibModule], r12
0x18000c814  mov     [rbp+var_28], r12
0x18000c818  jmp     loc_18000C752
0x18000c81d  mov     [rbp+var_18], r12
0x18000c821  lea     r9, [rbp+var_18]; void **
0x18000c825  lea     r8, _GUID_ea69859a_db5b_4c4a_8a8f_ae9759027534; struct _GUID *
0x18000c82c  lea     rdx, aCompositionPro; "Composition Processor"
0x18000c833  mov     rcx, rbx; struct IBindCtx *
0x18000c836  call    ?GetObjectFromBindCtx@@YAJPEAUIBindCtx@@PEBGAEBU_GUID@@PEAPEAX@Z; GetObjectFromBindCtx(IBindCtx *,ushort const *,_GUID const &,void * *)
0x18000c83b  lea     r9, [rbp+var_28]
0x18000c83f  mov     rdx, [rbp+var_18]
0x18000c843  mov     rcx, r14
0x18000c846  call    GetListDescriptionForItem
0x18000c84b  mov     edi, eax
0x18000c84d  test    eax, eax
0x18000c84f  jns     short loc_18000C7D4
0x18000c851  mov     rcx, rbx; struct IBindCtx *
0x18000c854  call    ?BindCtx_GetUIWindow@@YAPEAUHWND__@@PEAUIBindCtx@@@Z; BindCtx_GetUIWindow(IBindCtx *)
0x18000c859  mov     r14, rax
0x18000c85c  test    rax, rax
0x18000c85f  jz      loc_18000C7D4
0x18000c865  mov     [rbp+hLibModule], r12
0x18000c869  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18000c870  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18000c875  lea     rcx, [rbp+hLibModule]; this
0x18000c879  test    al, al
0x18000c87b  jz      short loc_18000C88F
0x18000c87d  call    ?get@SearchFolderInstance@@QEAAPEAUHINSTANCE__@@XZ; SearchFolderInstance::get(void)
0x18000c882  mov     rcx, rax; hAppInst
0x18000c885  mov     rdx, r14; hWnd
0x18000c888  call    MessageBoxHelper__ShellMessageBoxTextScaled__
0x18000c88d  jmp     short loc_18000C8B2
0x18000c88f  call    ?get@SearchFolderInstance@@QEAAPEAUHINSTANCE__@@XZ; SearchFolderInstance::get(void)
0x18000c894  mov     rcx, rax; hAppInst
0x18000c897  mov     [rsp+60h+fuStyle], 10h; fuStyle
0x18000c89f  xor     r9d, r9d; lpcTitle
0x18000c8a2  mov     r8d, 9571h; lpcText
0x18000c8a8  mov     rdx, r14; hWnd
0x18000c8ab  call    cs:__imp_ShellMessageBoxW
0x18000c8b1  nop
0x18000c8b2  mov     rcx, [rbp+hLibModule]; hLibModule
0x18000c8b6  test    rcx, rcx
0x18000c8b9  jz      loc_18000C7D4
0x18000c8bf  call    cs:__imp_FreeLibrary
0x18000c8c5  jmp     loc_18000C7D4
0x18000c8ca  mov     rcx, [rbp+var_18]
0x18000c8ce  mov     rax, [rcx]
0x18000c8d1  mov     rdx, r15
0x18000c8d4  mov     rax, [rax+20h]
0x18000c8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8dd  mov     rcx, [rbp+var_18]
0x18000c8e1  jmp     loc_18000C6A2
0x18000c8e6  mov     r8, rdi
0x18000c8e9  mov     rcx, [rbp+hLibModule]
0x18000c8ed  call    IUnknown_GetCookieFromProvider
0x18000c8f2  mov     rcx, [rbp+hLibModule]
0x18000c8f6  mov     rax, [rcx]
0x18000c8f9  mov     rax, [rax+10h]
0x18000c8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c902  jmp     loc_18000C7A4
```
