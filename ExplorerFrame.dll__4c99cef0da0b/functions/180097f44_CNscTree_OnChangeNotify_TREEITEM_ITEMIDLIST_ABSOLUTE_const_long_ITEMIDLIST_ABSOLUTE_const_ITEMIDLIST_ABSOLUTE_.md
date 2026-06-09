# CNscTree::_OnChangeNotify(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,CHANGENOTIFY_CALLBACK_FLAGS)

- ea: `0x180097f44`
- end: `0x180098676`
- name: `?_OnChangeNotify@CNscTree@@AEAAXPEAU_TREEITEM@@PEBU_ITEMIDLIST_ABSOLUTE@@J11W4CHANGENOTIFY_CALLBACK_FLAGS@@@Z`
- size: `1842`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180097cb0`
- `0x180097d30`

## callees

- `0x180027e0c`
- `0x180028dbc`
- `0x18002a3c4`
- `0x18002c1d0`
- `0x18002c854`
- `0x18002f35c`
- `0x180039680`
- `0x180047410`
- `0x1800903fc`
- `0x1800941dc`
- `0x180096624`
- `0x18009696c`
- `0x180097f44`
- `0x180098860`
- `0x18009aa84`
- `0x18009abf4`
- `0x18009ac90`
- `0x1800a36c0`
- `0x1800b5af8`
- `0x1800c1824`
- `0x1800d0e90`
- `0x1800d12e8`
- `0x1800e00bc`
- `0x1801086a0`
- `0x180128964`
- `0x18013f7d0`
- `0x1801b7068`
- `0x1801b7a50`
- `0x1801b8a68`
- `0x1801b9150`
- `0x1801b918c`
- `0x180210010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x1800980db`
- `SHELL32!SHBindToParent` at `0x1800980db`
- `SHELL32!__imp_ILIsEqual` at `0x180098263`
- `SHELL32!__imp_ILIsEqual` at `0x1800985e4`
- `SHELL32!__imp_ILIsEqual` at `0x180098263`
- `SHELL32!__imp_ILIsEqual` at `0x1800985e4`
- `SHELL32!__imp_ILIsParent` at `0x1800980b8`
- `SHELL32!__imp_ILIsParent` at `0x180098311`
- `SHELL32!__imp_ILIsParent` at `0x1800980b8`
- `SHELL32!__imp_ILIsParent` at `0x180098311`
- `SHELL32!__imp_SHRestricted` at `0x18009833e`
- `SHELL32!__imp_SHRestricted` at `0x18009833e`
- `SHELL32!__imp_ILFree` at `0x180098197`
- `SHELL32!__imp_ILFree` at `0x180098197`
- `SHELL32!__imp_SHHandleUpdateImage` at `0x18009850d`
- `SHELL32!__imp_SHHandleUpdateImage` at `0x18009850d`
- `SHLWAPI!PathGetDriveNumberW` at `0x18009834a`
- `SHLWAPI!PathGetDriveNumberW` at `0x18009834a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180098480`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180098480`
- `USER32!SendMessageW` at `0x180098133`
- `USER32!SendMessageW` at `0x180098153`
- `USER32!SendMessageW` at `0x180098176`
- `USER32!SendMessageW` at `0x1800981ce`
- `USER32!SendMessageW` at `0x1800983f1`
- `USER32!SendMessageW` at `0x180098421`
- `USER32!SendMessageW` at `0x180098133`
- `USER32!SendMessageW` at `0x180098153`
- `USER32!SendMessageW` at `0x180098176`
- `USER32!SendMessageW` at `0x1800981ce`
- `USER32!SendMessageW` at `0x1800983f1`
- `USER32!SendMessageW` at `0x180098421`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNscTree::_OnChangeNotify(
        __int64 a1,
        struct _TREEITEM *a2,
        const struct _ITEMIDLIST_ABSOLUTE *a3,
        int a4,
        LPCITEMIDLIST pidl1,
        const struct _ITEMIDLIST_ABSOLUTE *pidlExtra,
        int a7)
{
  char IsEnabled; // al
  __int64 v12; // r8
  struct _TREEITEM *v13; // r15
  ITEMIDLIST *v14; // r14
  LPARAM i; // r9
  const struct _ITEMIDLIST_RELATIVE **TreeOrderItem; // rax
  struct _TREEITEM *v17; // rax
  CNscTree *v18; // rcx
  struct _TREEITEM *v19; // rbx
  LRESULT v20; // r9
  int v21; // ebx
  unsigned int v22; // r8d
  struct _TREEITEM *v23; // rdx
  const ITEMIDLIST *v24; // rdx
  int v25; // eax
  const ITEMIDLIST *v26; // rcx
  DWORD v27; // ebx
  int v28; // eax
  bool v29; // r15
  struct _TREEITEM *v30; // r14
  char EnumFlags; // bl
  bool v32; // zf
  int v33; // ebx
  struct _TREEITEM *v34; // rax
  int updated; // eax
  __int64 v36; // rcx
  const ITEMIDLIST *HomePidl; // rax
  struct _TREEITEM *v38; // rax
  HWND *v39; // [rsp+20h] [rbp-30h]
  LPCITEMIDLIST pidl2; // [rsp+30h] [rbp-20h] BYREF
  HWND v41[2]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl'::`2'::impl);
  v12 = 0;
  if ( IsEnabled && *(_BYTE *)(a1 + 1128) )
  {
    *(_BYTE *)(a1 + 1129) = 1;
    return;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v39 = v41;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_NamespaceControl_ChangeNotify_Start,
      0,
      1);
    v12 = 0;
  }
  if ( a4 <= 256 )
  {
    if ( a4 == 256 )
      goto LABEL_37;
    if ( a4 != 1 )
    {
      if ( a4 != 2 )
      {
        if ( a4 == 4 )
          goto LABEL_16;
        if ( a4 != 8 )
        {
          if ( a4 == 16 )
            goto LABEL_16;
          if ( a4 != 32 && a4 != 64 )
          {
            if ( a4 == 128 )
            {
LABEL_16:
              if ( pidl1 )
                CNscTree::_OnSHNotifyDelete(
                  (CNscTree *)a1,
                  (LPARAM)a2,
                  a3,
                  (const struct _ITEMIDLIST_ABSOLUTE *)pidl1,
                  0);
              goto LABEL_99;
            }
            goto LABEL_99;
          }
          if ( !pidl1 )
            goto LABEL_99;
          v13 = CNscTree::_FindFromRoot((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1, 0);
          if ( !v13 )
            goto LABEL_99;
          if ( a4 == 64 )
          {
            pidl2 = 0;
            if ( (int)CNscTree::_GetSelectedItem((CNscTree *)a1, (struct _ITEMIDLIST_ABSOLUTE **)&pidl2, v12) >= 0 )
            {
              v14 = (ITEMIDLIST *)pidl2;
              if ( (unsigned int)ILIsEqualIncludingHiddenEx(pidl1, pidl2, 0xFFFFFFFFLL) || ILIsParent(pidl1, v14, 0) )
              {
                pidl2 = 0;
                if ( SHBindToParent(pidl1, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&pidl2, 0) >= 0 )
                {
                  for ( i = (LPARAM)v13; ; i = (LPARAM)v19 )
                  {
                    v17 = (struct _TREEITEM *)SendMessageW(*(HWND *)(a1 + 400), 0x110Au, 1u, i);
                    v19 = v17;
                    if ( !v17 )
                    {
                      v20 = SendMessageW(*(HWND *)(a1 + 400), 0x110Au, 3u, (LPARAM)v13);
                      goto LABEL_31;
                    }
                    TreeOrderItem = (const struct _ITEMIDLIST_RELATIVE **)CNscTree::_GetTreeOrderItem(
                                                                            v18,
                                                                            *(HWND *)(a1 + 400),
                                                                            v17);
                    if ( TreeOrderItem )
                    {
                      if ( !SHGetAttributesWithBindCtx((struct IShellFolder *)pidl2, *TreeOrderItem, 0, 0x2000000u) )
                        break;
                    }
                  }
                  v20 = (LRESULT)v19;
LABEL_31:
                  *(_DWORD *)(a1 + 464) |= 0x40000u;
                  SendMessageW(*(HWND *)(a1 + 400), 0x110Bu, 0x8009u, v20);
                  *(_DWORD *)(a1 + 464) &= ~0x40000u;
                  (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl2->mkid.cb + 16LL))(pidl2);
                }
              }
              ILFree(v14);
            }
            TreeView_DeleteChildren(*(HWND *)(a1 + 400), (LPARAM)v13);
            v21 = *(_DWORD *)(a1 + 504);
            *(_DWORD *)(a1 + 504) = 0;
            SendMessageW(*(HWND *)(a1 + 400), 0x1102u, 0x8001u, (LPARAM)v13);
            *(_DWORD *)(a1 + 504) = v21;
            v22 = 0;
          }
          else
          {
            v22 = 3;
          }
          TreeView_SetChildren(*(HWND *)(a1 + 400), v13, v22);
          v23 = v13;
LABEL_98:
          CNscTree::_TreeInvalidateItemInfo((CNscTree *)a1, v23, 1u);
          goto LABEL_99;
        }
      }
LABEL_37:
      if ( !pidl1 )
        goto LABEL_99;
      if ( a4 == 2 )
      {
        if ( CNscTree::_FindFromRoot((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1, 0) )
        {
          CNscTree::_OnSHNotifyUpdateDir((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1);
          goto LABEL_99;
        }
        if ( *(_QWORD *)(a1 + 800) )
        {
          v24 = *(const ITEMIDLIST **)(a1 + 808);
          if ( v24 )
          {
            if ( ILIsEqual(pidl1, v24) )
            {
              CNscTree::_OnSHNotifyRename(a1, a2, a3, *(_QWORD *)(a1 + 800), pidl1, 0);
              goto LABEL_99;
            }
          }
        }
      }
      else if ( a4 == 256 )
      {
        pidl2 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pidl2,
          0);
        v25 = DisplayNameOfAsString(0, (const struct _ITEMIDLIST_RELATIVE *)pidl1, 0x8000u, (unsigned __int16 **)&pidl2);
        if ( v25 >= 0 )
        {
          v27 = SHRestricted(REST_NODRIVES);
          if ( ((1 << PathGetDriveNumberW(&pidl2->mkid.cb)) & v27) != 0 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
            goto LABEL_99;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x20BD,
            (unsigned int)"shell\\explorerframe\\nsc.cpp",
            (const char *)(unsigned int)v25,
            (int)v39);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
      }
      CNscTree::_OnSHNotifyCreate((CNscTree *)a1, a2, 0, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1, 0);
      if ( a4 == 8 )
      {
        v26 = *(const ITEMIDLIST **)(a1 + 712);
        if ( v26 )
        {
          if ( ILIsParent(v26, pidl1, 1) )
          {
            Pidl_Set(a1 + 712, 0);
            CNscTree::_EnterNewFolderEditMode((CNscTree *)a1, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1);
          }
        }
      }
      goto LABEL_99;
    }
LABEL_77:
    if ( pidl1 && pidlExtra )
      CNscTree::_OnSHNotifyRename(a1, a2, a3, pidl1, pidlExtra, a7);
    goto LABEL_99;
  }
  if ( ((a4 - 512) & 0xFFFFFDFF) == 0 )
  {
    if ( !pidl1 )
      goto LABEL_99;
    v38 = CNscTree::_FindFromRoot((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1, 0);
    if ( (((unsigned __int64)v38 + 0x10000) & 0xFFFFFFFFFFFEFFFFuLL) == 0 )
      goto LABEL_99;
    v23 = v38;
    goto LABEL_98;
  }
  if ( a4 == 4096 )
  {
    if ( !pidl1 )
      goto LABEL_99;
    CNscTree::_OnSHNotifyUpdateDir((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58447884>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58447884>::GetImpl'::`2'::impl) )
      goto LABEL_99;
    HomePidl = (const ITEMIDLIST *)GetHomePidl(v36);
    v32 = !ILIsEqual(pidl1, HomePidl);
    goto LABEL_67;
  }
  if ( a4 == 0x2000 )
  {
    if ( pidl1 )
    {
      pidl2 = 0;
      v41[0] = 0;
      if ( (int)CNscTree::_GetTreeItemParentFolder(
                  (CNscTree *)a1,
                  a2,
                  0,
                  (void **)&pidl2,
                  (const struct _ITEMID_CHILD **)v41) >= 0 )
      {
        if ( SHGetAttributesWithBindCtx(
               (struct IShellFolder *)pidl2,
               (const struct _ITEMIDLIST_RELATIVE *)v41[0],
               0,
               0x20000000u) )
        {
          CNscTree::_OnSHNotifyUpdateDir((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1);
        }
        CNscTree::_OnSHNotifyUpdateItem((CNscTree *)a1, a2, a3, (const struct _ITEMIDLIST_ABSOLUTE *)pidl1);
        (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl2->mkid.cb + 16LL))(pidl2);
      }
    }
    goto LABEL_99;
  }
  if ( a4 != 0x8000 )
  {
    if ( a4 == 0x20000 )
      goto LABEL_77;
    if ( a4 != 0x4000000 )
      goto LABEL_99;
    v28 = *(_DWORD *)pidl1->mkid.abID;
    if ( v28 == 2 )
    {
      if ( (*(_DWORD *)(a1 + 464) & 0x820) == 0 && CNscTree::_ModeSupportsOrder((CNscTree *)a1, a2) )
      {
        if ( pidl1->mkid.cb < 0x12u
          || *(_QWORD *)&pidl1[2].mkid.cb != a1
          || (v33 = *(_DWORD *)pidl1[4].mkid.abID, v33 != GetCurrentProcessId()) )
        {
          ++*(_DWORD *)(a1 + 764);
          v34 = 0;
          if ( pidlExtra )
            v34 = CNscTree::_FindFromRoot((CNscTree *)a1, (struct _TREEITEM *)0xFFFFFFFFFFFF0000LL, 0, pidlExtra, 0);
          CNscTree::_UpdateDir((CNscTree *)a1, v34, 0);
        }
      }
      goto LABEL_99;
    }
    if ( v28 != 21 )
      goto LABEL_99;
    v29 = 0;
    v30 = (struct _TREEITEM *)SendMessageW(*(HWND *)(a1 + 400), 0x110Au, 4u, -65536);
    do
    {
      if ( !v30 )
        break;
      EnumFlags = CNscTree::_GetEnumFlags((CNscTree *)a1, v30, 0, 0, v39);
      v30 = (struct _TREEITEM *)SendMessageW(*(HWND *)(a1 + 400), 0x110Au, 1u, (LPARAM)v30);
      v29 = (EnumFlags & 0x40) != 0;
    }
    while ( (EnumFlags & 0x40) == 0 );
    v32 = !v29;
LABEL_67:
    if ( !v32 )
      CNscTree::_Refresh((CNscTree *)a1);
    goto LABEL_99;
  }
  if ( !pidl1 )
    goto LABEL_99;
  if ( pidlExtra )
  {
    updated = SHHandleUpdateImage((LPCITEMIDLIST)pidlExtra);
    if ( updated == -1 )
      goto LABEL_99;
  }
  else
  {
    updated = *(_DWORD *)pidl1->mkid.abID;
  }
  CNscTree::_InvalidateImageIndex((CNscTree *)a1, a2, updated);
LABEL_99:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_NamespaceControl_ChangeNotify_Stop,
      v12,
      1);
}

```

## disassembly

```asm
0x180097f44  mov     [rsp-38h+arg_18], rbx
0x180097f49  push    rbp
0x180097f4a  push    rsi
0x180097f4b  push    rdi
0x180097f4c  push    r12
0x180097f4e  push    r13
0x180097f50  push    r14
0x180097f52  push    r15
0x180097f54  mov     rbp, rsp
0x180097f57  sub     rsp, 50h
0x180097f5b  mov     rax, cs:__security_cookie
0x180097f62  xor     rax, rsp
0x180097f65  mov     [rbp+var_8], rax
0x180097f69  mov     r14d, r9d
0x180097f6c  mov     rbx, r8
0x180097f6f  mov     r15, rdx
0x180097f72  mov     rdi, rcx
0x180097f75  mov     rsi, [rbp+pidl1]
0x180097f79  mov     r13, [rbp+pidlExtra]
0x180097f7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59355007@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007> `wil::Feature<__WilFeatureTraits_Feature_59355007>::GetImpl(void)'::`2'::impl
0x180097f84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59355007@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59355007>::__private_IsEnabled(void)
0x180097f89  xor     r8d, r8d
0x180097f8c  test    al, al
0x180097f8e  jz      short loc_180097FA5
0x180097f90  cmp     [rdi+468h], r8b
0x180097f97  jz      short loc_180097FA5
0x180097f99  mov     byte ptr [rdi+469h], 1
0x180097fa0  jmp     loc_180098652
0x180097fa5  mov     r12d, 1
0x180097fab  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r12b
0x180097fb2  jz      short loc_180097FD6
0x180097fb4  lea     rax, [rbp+var_18]
0x180097fb8  mov     [rsp+50h+var_30], rax; HWND *
0x180097fbd  mov     r9d, r12d
0x180097fc0  lea     rdx, ShellTraceId_NamespaceControl_ChangeNotify_Start
0x180097fc7  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180097fce  call    McGenEventWrite_EventWriteTransfer
0x180097fd3  xor     r8d, r8d; struct _GUID *
0x180097fd6  cmp     r14d, 100h
0x180097fdd  jg      loc_18009836D
0x180097fe3  jz      loc_180098204
0x180097fe9  mov     ecx, r14d
0x180097fec  sub     ecx, r12d
0x180097fef  jz      loc_1800984C8
0x180097ff5  sub     ecx, r12d
0x180097ff8  jz      loc_180098204
0x180097ffe  sub     ecx, 2
0x180098001  jz      short loc_180098024
0x180098003  sub     ecx, 4
0x180098006  jz      loc_180098204
0x18009800c  sub     ecx, 8
0x18009800f  jz      short loc_180098024
0x180098011  sub     ecx, 10h
0x180098014  jz      short loc_180098048
0x180098016  sub     ecx, 20h ; ' '
0x180098019  jz      short loc_180098048
0x18009801b  cmp     ecx, 40h ; '@'
0x18009801e  jnz     loc_18009862A
0x180098024  test    rsi, rsi
0x180098027  jz      loc_18009862A
0x18009802d  mov     [rsp+50h+var_30], r8; struct _TREEITEM **
0x180098032  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180098035  mov     r8, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x180098038  mov     rdx, r15; lParam
0x18009803b  mov     rcx, rdi; this
0x18009803e  call    ?_OnSHNotifyDelete@CNscTree@@AEAAJPEAU_TREEITEM@@PEBU_ITEMIDLIST_ABSOLUTE@@1PEAPEAU2@@Z; CNscTree::_OnSHNotifyDelete(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_TREEITEM * *)
0x180098043  jmp     loc_18009862A
0x180098048  test    rsi, rsi
0x18009804b  jz      loc_18009862A
0x180098051  mov     dword ptr [rsp+50h+var_30], r8d; int
0x180098056  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180098059  mov     r8, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x18009805c  mov     rdx, r15; struct _TREEITEM *
0x18009805f  mov     rcx, rdi; this
0x180098062  call    ?_FindFromRoot@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEBU_ITEMIDLIST_ABSOLUTE@@1H@Z; CNscTree::_FindFromRoot(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x180098067  mov     r15, rax
0x18009806a  xor     r13d, r13d
0x18009806d  test    rax, rax
0x180098070  jz      loc_18009862A
0x180098076  cmp     r14d, 40h ; '@'
0x18009807a  jnz     loc_1800981E7
0x180098080  mov     [rbp+pidl2], r13
0x180098084  lea     rdx, [rbp+pidl2]; struct _ITEMIDLIST_ABSOLUTE **
0x180098088  mov     rcx, rdi; this
0x18009808b  call    ?_GetSelectedItem@CNscTree@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@H@Z; CNscTree::_GetSelectedItem(_ITEMIDLIST_ABSOLUTE * *,int)
0x180098090  test    eax, eax
0x180098092  js      loc_18009819D
0x180098098  or      r8d, 0FFFFFFFFh
0x18009809c  mov     r14, [rbp+pidl2]
0x1800980a0  mov     rdx, r14
0x1800980a3  mov     rcx, rsi
0x1800980a6  call    ?ILIsEqualIncludingHiddenEx@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@0W4IIEIHE@@@Z; ILIsEqualIncludingHiddenEx(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,IIEIHE)
0x1800980ab  test    eax, eax
0x1800980ad  jnz     short loc_1800980C6
0x1800980af  xor     r8d, r8d; fImmediate
0x1800980b2  mov     rdx, r14; pidl2
0x1800980b5  mov     rcx, rsi; pidl1
0x1800980b8  call    cs:__imp_ILIsParent
0x1800980be  test    eax, eax
0x1800980c0  jz      loc_180098194
0x1800980c6  mov     [rbp+pidl2], r13
0x1800980ca  xor     r9d, r9d; ppidlLast
0x1800980cd  lea     r8, [rbp+pidl2]; ppv
0x1800980d1  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800980d8  mov     rcx, rsi; pidl
0x1800980db  call    cs:__imp_SHBindToParent
0x1800980e1  test    eax, eax
0x1800980e3  js      loc_180098194
0x1800980e9  mov     r9, r15
0x1800980ec  mov     esi, 110Ah
0x1800980f1  jmp     short loc_180098127
0x1800980f3  mov     r8, rbx; struct _TREEITEM *
0x1800980f6  mov     rdx, [rdi+190h]; HWND
0x1800980fd  call    ?_GetTreeOrderItem@CNscTree@@AEAAPEAUORDERITEM@@PEAUHWND__@@PEAU_TREEITEM@@@Z; CNscTree::_GetTreeOrderItem(HWND__ *,_TREEITEM *)
0x180098102  test    rax, rax
0x180098105  jz      short loc_180098124
0x180098107  mov     r9d, 2000000h; unsigned int
0x18009810d  xor     r8d, r8d; struct IBindCtx *
0x180098110  mov     rdx, [rax]; struct _ITEMIDLIST_RELATIVE *
0x180098113  mov     rcx, [rbp+pidl2]; struct IShellFolder *
0x180098117  call    ?SHGetAttributesWithBindCtx@@YAKPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@K@Z; SHGetAttributesWithBindCtx(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong)
0x18009811c  test    eax, eax
0x18009811e  jz      loc_1800981DF
0x180098124  mov     r9, rbx; lParam
0x180098127  mov     r8, r12; wParam
0x18009812a  mov     edx, esi; Msg
0x18009812c  mov     rcx, [rdi+190h]; hWnd
0x180098133  call    cs:__imp_SendMessageW
0x180098139  test    rax, rax
0x18009813c  mov     rbx, rax
0x18009813f  jnz     short loc_1800980F3
0x180098141  mov     r9, r15; lParam
0x180098144  mov     r8d, 3; wParam
0x18009814a  mov     edx, esi; Msg
0x18009814c  mov     rcx, [rdi+190h]; hWnd
0x180098153  call    cs:__imp_SendMessageW
0x180098159  mov     r9, rax; lParam
0x18009815c  bts     dword ptr [rdi+1D0h], 12h
0x180098164  mov     r8d, 8009h; wParam
0x18009816a  mov     edx, 110Bh; Msg
0x18009816f  mov     rcx, [rdi+190h]; hWnd
0x180098176  call    cs:__imp_SendMessageW
0x18009817c  btr     dword ptr [rdi+1D0h], 12h
0x180098184  mov     rcx, [rbp+pidl2]
0x180098188  mov     rax, [rcx]
0x18009818b  mov     rax, [rax+10h]
0x18009818f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098194  mov     rcx, r14; pidl
0x180098197  call    cs:__imp_ILFree
0x18009819d  mov     rdx, r15; lParam
0x1800981a0  mov     rcx, [rdi+190h]; hWnd
0x1800981a7  call    ?TreeView_DeleteChildren@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_DeleteChildren(HWND__ *,_TREEITEM *)
0x1800981ac  mov     ebx, [rdi+1F8h]
0x1800981b2  mov     [rdi+1F8h], r13d
0x1800981b9  mov     r9, r15; lParam
0x1800981bc  mov     edx, 1102h; Msg
0x1800981c1  mov     r8d, 8001h; wParam
0x1800981c7  mov     rcx, [rdi+190h]; hWnd
0x1800981ce  call    cs:__imp_SendMessageW
0x1800981d4  mov     [rdi+1F8h], ebx
0x1800981da  mov     r8d, r13d
0x1800981dd  jmp     short loc_1800981ED
0x1800981df  mov     r9, rbx
0x1800981e2  jmp     loc_18009815C
0x1800981e7  mov     r8d, 3; unsigned int
0x1800981ed  mov     rdx, r15; struct _TREEITEM *
0x1800981f0  mov     rcx, [rdi+190h]; HWND
0x1800981f7  call    ?TreeView_SetChildren@@YAXPEAUHWND__@@PEAU_TREEITEM@@I@Z; TreeView_SetChildren(HWND__ *,_TREEITEM *,uint)
0x1800981fc  mov     rdx, r15
0x1800981ff  jmp     loc_18009861F
0x180098204  test    rsi, rsi
0x180098207  jz      loc_18009862A
0x18009820d  cmp     r14d, 2
0x180098211  jnz     short loc_180098286
0x180098213  mov     dword ptr [rsp+50h+var_30], r8d; int
0x180098218  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x18009821b  mov     r8, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x18009821e  mov     rdx, r15; struct _TREEITEM *
0x180098221  mov     rcx, rdi; this
0x180098224  call    ?_FindFromRoot@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEBU_ITEMIDLIST_ABSOLUTE@@1H@Z; CNscTree::_FindFromRoot(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x180098229  xor     r8d, r8d
0x18009822c  test    rax, rax
0x18009822f  jz      short loc_180098247
0x180098231  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180098234  mov     r8, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x180098237  mov     rdx, r15; struct _TREEITEM *
0x18009823a  mov     rcx, rdi; this
0x18009823d  call    ?_OnSHNotifyUpdateDir@CNscTree@@AEAAJPEAU_TREEITEM@@PEBU_ITEMIDLIST_ABSOLUTE@@1@Z; CNscTree::_OnSHNotifyUpdateDir(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x180098242  jmp     loc_18009862A
0x180098247  cmp     [rdi+320h], r8
0x18009824e  jz      loc_1800982DB
0x180098254  mov     rdx, [rdi+328h]; pidl2
0x18009825b  test    rdx, rdx
0x18009825e  jz      short loc_1800982DB
0x180098260  mov     rcx, rsi; pidl1
0x180098263  call    cs:__imp_ILIsEqual
0x180098269  xor     r8d, r8d
0x18009826c  test    eax, eax
0x18009826e  jz      short loc_1800982DB
0x180098270  mov     [rsp+50h+var_28], r8d
0x180098275  mov     [rsp+50h+var_30], rsi
0x18009827a  mov     r9, [rdi+320h]
0x180098281  jmp     loc_1800984E9
0x180098286  cmp     r14d, 100h
0x18009828d  jnz     short loc_1800982DB
0x18009828f  mov     [rbp+pidl2], r8
0x180098293  xor     edx, edx
0x180098295  lea     rcx, [rbp+pidl2]
0x180098299  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009829e  lea     r9, [rbp+pidl2]; unsigned __int16 **
0x1800982a2  mov     r8d, 8000h; unsigned int
0x1800982a8  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800982ab  xor     ecx, ecx; struct IShellFolder *
0x1800982ad  call    ?DisplayNameOfAsString@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@KPEAPEAG@Z; DisplayNameOfAsString(IShellFolder *,_ITEMIDLIST_RELATIVE const *,ulong,ushort * *)
0x1800982b2  mov     rcx, [rbp+38h]; this
0x1800982b6  test    eax, eax
0x1800982b8  jns     short loc_180098339
0x1800982ba  mov     r9d, eax; char *
0x1800982bd  lea     r8, aShellExplorerf_35; "shell\\explorerframe\\nsc.cpp"
0x1800982c4  mov     edx, 20BDh; void *
0x1800982c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800982ce  nop
0x1800982cf  lea     rcx, [rbp+pidl2]; void *
0x1800982d3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1800982d8  xor     r8d, r8d; struct _ITEMIDLIST_ABSOLUTE *
0x1800982db  mov     [rsp+50h+var_30], r8; struct _TREEITEM *
0x1800982e0  mov     r9, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x1800982e3  mov     rdx, r15; struct _TREEITEM *
0x1800982e6  mov     rcx, rdi; this
0x1800982e9  call    ?_OnSHNotifyCreate@CNscTree@@AEAAJPEAU_TREEITEM@@PEBU_ITEMIDLIST_ABSOLUTE@@10@Z; CNscTree::_OnSHNotifyCreate(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_TREEITEM *)
0x1800982ee  cmp     r14d, 8
0x1800982f2  jnz     loc_18009862A
0x1800982f8  lea     rbx, [rdi+2C8h]
0x1800982ff  mov     rcx, [rbx]; pidl1
0x180098302  test    rcx, rcx
0x180098305  jz      loc_18009862A
0x18009830b  mov     r8d, r12d; fImmediate
0x18009830e  mov     rdx, rsi; pidl2
0x180098311  call    cs:__imp_ILIsParent
0x180098317  test    eax, eax
0x180098319  jz      loc_18009862A
0x18009831f  xor     edx, edx
0x180098321  mov     rcx, rbx
0x180098324  call    Pidl_Set
0x180098329  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x18009832c  mov     rcx, rdi; this
0x18009832f  call    ?_EnterNewFolderEditMode@CNscTree@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CNscTree::_EnterNewFolderEditMode(_ITEMIDLIST_ABSOLUTE const *)
0x180098334  jmp     loc_18009862A
0x180098339  mov     ecx, 100h; rest
0x18009833e  call    cs:__imp_SHRestricted
0x180098344  mov     ebx, eax
0x180098346  mov     rcx, [rbp+pidl2]; pszPath
0x18009834a  call    cs:__imp_PathGetDriveNumberW
0x180098350  mov     ecx, eax
0x180098352  mov     edx, r12d
0x180098355  shl     edx, cl
0x180098357  test    ebx, edx
0x180098359  jz      loc_1800982CF
0x18009835f  lea     rcx, [rbp+pidl2]; void *
0x180098363  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180098368  jmp     loc_18009862A
0x18009836d  lea     eax, [r14-200h]
0x180098374  test    eax, 0FFFFFDFFh
0x180098379  jz      loc_1800985F1
0x18009837f  cmp     r14d, 1000h
0x180098386  jz      loc_1800985B3
0x18009838c  cmp     r14d, 2000h
0x180098393  jz      loc_180098534
0x180098399  cmp     r14d, 8000h
0x1800983a0  jz      loc_1800984FC
0x1800983a6  cmp     r14d, 20000h
0x1800983ad  jz      loc_1800984C8
0x1800983b3  cmp     r14d, 4000000h
0x1800983ba  jnz     loc_18009862A
0x1800983c0  mov     eax, [rsi+2]
0x1800983c3  cmp     eax, 2
0x1800983c6  jz      loc_18009844E
0x1800983cc  cmp     eax, 15h
0x1800983cf  jnz     loc_18009862A
0x1800983d5  mov     r15b, r8b
0x1800983d8  mov     esi, 110Ah
0x1800983dd  mov     r9, 0FFFFFFFFFFFF0000h; lParam
0x1800983e4  lea     r8d, [rax-11h]; wParam
0x1800983e8  mov     edx, esi; Msg
0x1800983ea  mov     rcx, [rdi+190h]; hWnd
0x1800983f1  call    cs:__imp_SendMessageW
0x1800983f7  mov     r14, rax
0x1800983fa  test    r14, r14
0x1800983fd  jz      short loc_180098438
0x1800983ff  xor     r9d, r9d; struct _ITEMIDLIST_ABSOLUTE *
0x180098402  xor     r8d, r8d; struct IShellFolder *
0x180098405  mov     rdx, r14; struct _TREEITEM *
0x180098408  mov     rcx, rdi; this
0x18009840b  call    ?_GetEnumFlags@CNscTree@@AEAAKPEAU_TREEITEM@@PEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUHWND__@@@Z; CNscTree::_GetEnumFlags(_TREEITEM *,IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,HWND__ * *)
0x180098410  mov     ebx, eax
0x180098412  mov     r9, r14; lParam
0x180098415  mov     r8, r12; wParam
0x180098418  mov     edx, esi; Msg
0x18009841a  mov     rcx, [rdi+190h]; hWnd
0x180098421  call    cs:__imp_SendMessageW
  ... truncated ...
```
