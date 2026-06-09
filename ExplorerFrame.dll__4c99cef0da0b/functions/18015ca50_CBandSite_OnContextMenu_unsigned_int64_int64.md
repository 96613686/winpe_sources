# CBandSite::_OnContextMenu(unsigned __int64,__int64)

- ea: `0x18015ca50`
- end: `0x18015d059`
- name: `?_OnContextMenu@CBandSite@@MEAAJ_K_J@Z`
- size: `1545`
- prototype: `__int64 __fastcall(CBandSite *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800266fc`
- `0x180077a38`
- `0x1800aa478`
- `0x1800ae318`
- `0x1800c2604`
- `0x1801190b4`
- `0x180136f68`
- `0x18013f7d0`
- `0x1801406ec`
- `0x18015c344`
- `0x18015c540`
- `0x18015c858`
- `0x18015ca50`
- `0x1801f900c`
- `0x1801f9930`
- `0x180210010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18015cae6`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18015caf9`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18015cae6`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18015caf9`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18015cbf5`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18015cdf1`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18015cbf5`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18015cdf1`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18015cccf`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x18015cccf`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x18015cdb7`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x18015cdce`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x18015cdb7`
- `SHLWAPI!__imp_SHCheckMenuItem` at `0x18015cdce`
- `USER32!GetParent` at `0x18015ce9f`
- `USER32!GetParent` at `0x18015ce9f`
- `USER32!GetMenuItemCount` at `0x18015cb21`
- `USER32!GetMenuItemCount` at `0x18015cc89`
- `USER32!GetMenuItemCount` at `0x18015ce68`
- `USER32!GetMenuItemCount` at `0x18015cb21`
- `USER32!GetMenuItemCount` at `0x18015cc89`
- `USER32!GetMenuItemCount` at `0x18015ce68`
- `USER32!CreatePopupMenu` at `0x18015ca8c`
- `USER32!CreatePopupMenu` at `0x18015ca8c`
- `USER32!CheckMenuItem` at `0x18015cb61`
- `USER32!CheckMenuItem` at `0x18015cb61`
- `USER32!EnableMenuItem` at `0x18015cbb7`
- `USER32!EnableMenuItem` at `0x18015cca4`
- `USER32!EnableMenuItem` at `0x18015ccf8`
- `USER32!EnableMenuItem` at `0x18015cbb7`
- `USER32!EnableMenuItem` at `0x18015cca4`
- `USER32!EnableMenuItem` at `0x18015ccf8`
- `USER32!DeleteMenu` at `0x18015cbcb`
- `USER32!DeleteMenu` at `0x18015cd6a`
- `USER32!DeleteMenu` at `0x18015cd83`
- `USER32!DeleteMenu` at `0x18015cd93`
- `USER32!DeleteMenu` at `0x18015cbcb`
- `USER32!DeleteMenu` at `0x18015cd6a`
- `USER32!DeleteMenu` at `0x18015cd83`
- `USER32!DeleteMenu` at `0x18015cd93`
- `USER32!DestroyMenu` at `0x18015cc01`
- `USER32!DestroyMenu` at `0x18015cdfd`
- `USER32!DestroyMenu` at `0x18015d01c`
- `USER32!DestroyMenu` at `0x18015cc01`
- `USER32!DestroyMenu` at `0x18015cdfd`
- `USER32!DestroyMenu` at `0x18015d01c`
- `USER32!TrackPopupMenu` at `0x18015cf1d`
- `USER32!TrackPopupMenu` at `0x18015cf1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBandSite::_OnContextMenu(HWND *this, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  HMENU PopupMenu; // r12
  int v7; // eax
  struct CBandItemData *BandItemDataStructByID; // r13
  int v9; // edi
  HMENU v10; // rax
  HMENU v11; // rbx
  int MenuItemCount; // r15d
  BOOL v13; // edi
  const struct CBandItemData *v14; // rdx
  UINT v15; // r15d
  int v16; // ebx
  int (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  int v18; // eax
  signed int v19; // edi
  signed int i; // ebx
  HMENU v21; // rax
  HMENU v22; // rbx
  unsigned int v23; // edi
  char AdminSettings; // di
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  int v26; // ebx
  unsigned int v27; // ebx
  void (__fastcall *v28)(__int64, HMENU, _QWORD, _QWORD, int, unsigned int); // rdi
  int v29; // eax
  unsigned int v30; // ecx
  HWND Parent; // rdi
  int v32; // ebx
  HWND v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // edx
  unsigned int v37; // eax
  __int64 v38; // rcx
  unsigned __int16 v39; // bx
  int v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh]
  unsigned int v43; // [rsp+48h] [rbp-B8h]
  signed int v44; // [rsp+4Ch] [rbp-B4h]
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  int x[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+68h] [rbp-98h]
  signed int v49; // [rsp+6Ch] [rbp-94h]
  _QWORD hData[5]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v51[5]; // [rsp+A0h] [rbp-60h] BYREF
  int v52; // [rsp+C8h] [rbp-38h]
  __int128 v53; // [rsp+CCh] [rbp-34h]
  __int128 v54; // [rsp+DCh] [rbp-24h]
  _BYTE v55[28]; // [rsp+ECh] [rbp-14h] BYREF
  DESKBANDINFO v56; // [rsp+110h] [rbp+10h] BYREF

  v5 = 0;
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
    return v5;
  v45 = 0;
  v47 = 0;
  *(_QWORD *)x = 0;
  v7 = (*((__int64 (__fastcall **)(HWND *, __int64, int *))*this + 14))(this, a3, x);
  v43 = CBandSite::_IndexToBandID((CBandSite *)this, v7);
  BandItemDataStructByID = CBandSite::_GetBandItemDataStructByID((CBandSite *)this, v43);
  v9 = SHWindowsPolicy(POLID_TaskbarLockAll);
  v42 = v9;
  v48 = SHWindowsPolicy(POLID_TaskbarNoAddRemoveToolbar);
  v10 = (HMENU)(*((__int64 (__fastcall **)(HWND *))*this + 12))(this);
  v11 = v10;
  if ( v10 )
  {
    MenuItemCount = GetMenuItemCount(v10);
    v41 = MenuItemCount;
    v13 = 1;
    if ( BandItemDataStructByID )
    {
      if ( (*((_DWORD *)this + 41) & 0x100) == 0 )
      {
        CheckMenuItem(v11, 2u, ~(4 * (unsigned __int8)*((_DWORD *)BandItemDataStructByID + 144)) & 8);
        memset_0(&v56.ptMinSize, 0, 0x228u);
        v56.dwMask = 0;
        CBandSite::_GetBandInfo((CBandSite *)this, BandItemDataStructByID, &v56);
        if ( (v56.dwMask & 0x10) != 0 )
          v13 = CBandSite::_IsEnableTitle((CBandSite *)this, v14) == 0;
      }
    }
    if ( v42 )
      EnableMenuItem(v11, 2u, 1u);
    if ( v13 )
    {
      DeleteMenu(v11, 2u, 0);
      v41 = MenuItemCount - 1;
    }
    v15 = Shell_MergeMenus(PopupMenu, v11, 0, 1u, 0x7FFFu, 0);
    DestroyMenu(v11);
    v16 = v41;
    v9 = v42;
  }
  else
  {
    v15 = 1;
    v16 = 0;
  }
  v44 = v15;
  if ( BandItemDataStructByID )
  {
    v17 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)BandItemDataStructByID + 1);
    if ( v17 )
    {
      if ( (**v17)(v17, &GUID_000214e4_0000_0000_c000_000000000046, &v47) >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(__int64, HMENU, _QWORD, _QWORD, int, _DWORD))(*(_QWORD *)v47 + 24LL))(
                v47,
                PopupMenu,
                0,
                v15,
                0x7FFF,
                0);
        if ( v18 >= 0 )
        {
          v15 += (unsigned __int16)v18;
          if ( v9 )
          {
            v19 = GetMenuItemCount(PopupMenu) - v16;
            for ( i = 0; i < v19; ++i )
              EnableMenuItem(PopupMenu, i, 0x401u);
          }
        }
      }
    }
  }
  v49 = v15;
  if ( (*((_BYTE *)this + 164) & 0x10) == 0 )
  {
    v21 = (HMENU)SHLoadMenuPopup(g_hinst, 257);
    v22 = v21;
    if ( v21 )
    {
      if ( v42 || v48 )
        EnableMenuItem(v21, 1u, 1u);
      v23 = v43;
      if ( v43 == -1
        || (v41 = 0,
            (*(int (__fastcall **)(HWND, _QWORD, _QWORD, int *, _QWORD, _DWORD))(*(_QWORD *)this[16] + 40LL))(
              this[16],
              v43,
              0,
              &v41,
              0,
              0) < 0)
        || (v41 & 0x1000) != 0
        || !(unsigned int)CBandSite::_IsRestricted((CBandSite *)this, v23, 1u, 1u)
        || (*((_DWORD *)this + 41) & 0x100) != 0 )
      {
        DeleteMenu(v22, 1u, 0);
      }
      if ( ((_BYTE)this[30] & 8) != 0 )
      {
        AdminSettings = CBandSite::_GetAdminSettings((CBandSite *)this, v23);
        if ( (AdminSettings & 1) != 0 )
          SHCheckMenuItem(v22, 3, 1);
        if ( (AdminSettings & 2) != 0 )
          SHCheckMenuItem(v22, 4, 1);
      }
      else
      {
        DeleteMenu(v22, 3u, 0);
        DeleteMenu(v22, 4u, 0);
      }
      v15 = Shell_MergeMenus(PopupMenu, v22, 0xFFFFFFFF, v15, 0x7FFFu, 0);
      DestroyMenu(v22);
    }
  }
  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[15];
  if ( v25 )
  {
    v26 = (**v25)(v25, &GUID_bcfce0a0_ec17_11d0_8d10_00a0c90f2719, this + 27);
    if ( (**(__int64 (__fastcall ***)(HWND, GUID *, __int64 *))this[15])(
           this[15],
           &GUID_000214e4_0000_0000_c000_000000000046,
           &v45) >= 0 )
    {
      v27 = ((v26 >> 31) & 0xFFFE0000) + 0x20000;
      v28 = *(void (__fastcall **)(__int64, HMENU, _QWORD, _QWORD, int, unsigned int))(*(_QWORD *)v45 + 24LL);
      v29 = GetMenuItemCount(PopupMenu);
      v30 = -1;
      if ( v29 != -1 )
        v30 = v29;
      v28(v45, PopupMenu, v30, v15, 0x7FFF, v27);
    }
  }
  Parent = GetParent(this[17]);
  if ( !Parent )
    Parent = this[17];
  memset(hData, 0, 32);
  ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu((int)PopupMenu, (int)Parent, (int)x, 8, hData);
  v32 = TrackPopupMenu(PopupMenu, 0x102u, x[0], x[1], 0, Parent, 0);
  ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(PopupMenu, (HMENU)Parent, v33);
  if ( !v32 )
  {
    v5 = 0;
    goto LABEL_59;
  }
  if ( v32 < 1 || v32 >= v44 )
  {
    if ( v32 < v49 )
    {
      if ( v32 < (int)v15 )
      {
        v38 = v47;
        v39 = v32 - v44;
LABEL_57:
        v51[0] = 104;
        v51[1] = this[17];
        v51[2] = v39;
        v51[3] = 0;
        v51[4] = 0;
        v52 = 1;
        v53 = 0;
        v54 = 0;
        memset(v55, 0, sizeof(v55));
        v37 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v38 + 32LL))(v38, v51);
        goto LABEL_53;
      }
    }
    else if ( v32 < (int)v15 )
    {
      v36 = v32 - v49;
      goto LABEL_52;
    }
    v38 = v45;
    v39 = v32 - v15;
    goto LABEL_57;
  }
  v36 = v32 - 1;
LABEL_52:
  v37 = CBandSite::_OnBSCommand((CBandSite *)this, v36, v43, BandItemDataStructByID);
LABEL_53:
  v5 = v37;
LABEL_59:
  if ( BandItemDataStructByID )
    CBandItemData::Release(BandItemDataStructByID);
  SafeRelease<ILinguisticAlternativeGenerator>(this + 27, v34, v35);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  DestroyMenu(PopupMenu);
  CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>::~CSimplePointerArray<ContextMenuRenderingData,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>>(hData);
  return v5;
}

```

## disassembly

```asm
0x18015ca50  mov     [rsp-8+arg_8], rbx
0x18015ca55  push    rbp
0x18015ca56  push    rsi
0x18015ca57  push    rdi
0x18015ca58  push    r12
0x18015ca5a  push    r13
0x18015ca5c  push    r14
0x18015ca5e  push    r15
0x18015ca60  lea     rbp, [rsp-250h]
0x18015ca68  sub     rsp, 350h
0x18015ca6f  mov     rax, cs:__security_cookie
0x18015ca76  xor     rax, rsp
0x18015ca79  mov     [rbp+280h+var_40], rax
0x18015ca80  mov     rdi, r8
0x18015ca83  mov     rsi, rcx
0x18015ca86  xor     r14d, r14d
0x18015ca89  mov     ebx, r14d
0x18015ca8c  call    cs:__imp_CreatePopupMenu
0x18015ca92  mov     r12, rax
0x18015ca95  test    rax, rax
0x18015ca98  jz      loc_18015D02D
0x18015ca9e  mov     [rsp+380h+var_330], r14
0x18015caa3  mov     [rsp+380h+var_320], r14
0x18015caa8  mov     qword ptr [rsp+380h+x], r14
0x18015caad  mov     rax, [rsi]
0x18015cab0  lea     r8, [rsp+380h+x]
0x18015cab5  mov     rdx, rdi
0x18015cab8  mov     rcx, rsi
0x18015cabb  mov     rax, [rax+70h]
0x18015cabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cac4  mov     edx, eax; int
0x18015cac6  mov     rcx, rsi; this
0x18015cac9  call    ?_IndexToBandID@CBandSite@@IEAAKH@Z; CBandSite::_IndexToBandID(int)
0x18015cace  mov     [rsp+380h+var_338], eax
0x18015cad2  mov     edx, eax; unsigned int
0x18015cad4  mov     rcx, rsi; this
0x18015cad7  call    ?_GetBandItemDataStructByID@CBandSite@@IEAAPEAVCBandItemData@@K@Z; CBandSite::_GetBandItemDataStructByID(ulong)
0x18015cadc  mov     r13, rax
0x18015cadf  lea     rcx, POLID_TaskbarLockAll
0x18015cae6  call    cs:__imp_SHWindowsPolicy
0x18015caec  mov     edi, eax
0x18015caee  mov     [rsp+380h+var_33C], eax
0x18015caf2  lea     rcx, POLID_TaskbarNoAddRemoveToolbar
0x18015caf9  call    cs:__imp_SHWindowsPolicy
0x18015caff  mov     [rsp+380h+var_318], eax
0x18015cb03  mov     rax, [rsi]
0x18015cb06  mov     rcx, rsi
0x18015cb09  mov     rax, [rax+60h]
0x18015cb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cb12  mov     rbx, rax
0x18015cb15  test    rax, rax
0x18015cb18  jz      loc_18015CC11
0x18015cb1e  mov     rcx, rax; hMenu
0x18015cb21  call    cs:__imp_GetMenuItemCount
0x18015cb27  mov     r15d, eax
0x18015cb2a  mov     [rsp+380h+var_340], eax
0x18015cb2e  mov     r14d, 1
0x18015cb34  mov     edi, r14d
0x18015cb37  test    r13, r13
0x18015cb3a  jz      short loc_18015CBA5
0x18015cb3c  test    dword ptr [rsi+0A4h], 100h
0x18015cb46  jnz     short loc_18015CBA5
0x18015cb48  mov     r8d, [r13+240h]
0x18015cb4f  shl     r8d, 2
0x18015cb53  not     r8d
0x18015cb56  and     r8d, 8; uCheck
0x18015cb5a  lea     edx, [r14+1]; uIDCheckItem
0x18015cb5e  mov     rcx, rbx; hMenu
0x18015cb61  call    cs:__imp_CheckMenuItem
0x18015cb67  xor     edx, edx; Val
0x18015cb69  mov     r8d, 228h; Size
0x18015cb6f  lea     rcx, [rbp+280h+var_270.ptMinSize]; void *
0x18015cb73  call    memset_0
0x18015cb78  mov     [rbp+280h+var_270.dwMask], 0
0x18015cb7f  lea     r8, [rbp+280h+var_270]; struct DESKBANDINFO *
0x18015cb83  mov     rdx, r13; struct CBandItemData *
0x18015cb86  mov     rcx, rsi; this
0x18015cb89  call    ?_GetBandInfo@CBandSite@@IEAAXPEAVCBandItemData@@PEAUDESKBANDINFO@@@Z; CBandSite::_GetBandInfo(CBandItemData *,DESKBANDINFO *)
0x18015cb8e  test    byte ptr [rbp+280h+var_270.dwMask], 10h
0x18015cb92  jz      short loc_18015CBA5
0x18015cb94  mov     rcx, rsi; this
0x18015cb97  call    ?_IsEnableTitle@CBandSite@@IEAAHPEBVCBandItemData@@@Z; CBandSite::_IsEnableTitle(CBandItemData const *)
0x18015cb9c  mov     ecx, eax
0x18015cb9e  xor     eax, eax
0x18015cba0  test    ecx, ecx
0x18015cba2  cmovnz  edi, eax
0x18015cba5  cmp     [rsp+380h+var_33C], 0
0x18015cbaa  jz      short loc_18015CBBD
0x18015cbac  mov     r8d, r14d; uEnable
0x18015cbaf  mov     edx, 2; uIDEnableItem
0x18015cbb4  mov     rcx, rbx; hMenu
0x18015cbb7  call    cs:__imp_EnableMenuItem
0x18015cbbd  test    edi, edi
0x18015cbbf  jz      short loc_18015CBD9
0x18015cbc1  xor     r8d, r8d; uFlags
0x18015cbc4  lea     edx, [r8+2]; uPosition
0x18015cbc8  mov     rcx, rbx; hMenu
0x18015cbcb  call    cs:__imp_DeleteMenu
0x18015cbd1  sub     r15d, r14d
0x18015cbd4  mov     [rsp+380h+var_340], r15d
0x18015cbd9  mov     [rsp+380h+uFlags], 0; uFlags
0x18015cbe1  mov     [rsp+380h+uIDAdjustMax], 7FFFh; uIDAdjustMax
0x18015cbe9  mov     r9d, r14d; uIDAdjust
0x18015cbec  xor     r8d, r8d; uInsert
0x18015cbef  mov     rdx, rbx; hmSrc
0x18015cbf2  mov     rcx, r12; hmDst
0x18015cbf5  call    cs:__imp_Shell_MergeMenus
0x18015cbfb  mov     r15d, eax
0x18015cbfe  mov     rcx, rbx; hMenu
0x18015cc01  call    cs:__imp_DestroyMenu
0x18015cc07  mov     ebx, [rsp+380h+var_340]
0x18015cc0b  mov     edi, [rsp+380h+var_33C]
0x18015cc0f  jmp     short loc_18015CC1C
0x18015cc11  mov     r14d, 1
0x18015cc17  mov     r15d, r14d
0x18015cc1a  xor     ebx, ebx
0x18015cc1c  mov     [rsp+380h+var_334], r15d
0x18015cc21  test    r13, r13
0x18015cc24  jz      loc_18015CCB1
0x18015cc2a  mov     rcx, [r13+8]
0x18015cc2e  test    rcx, rcx
0x18015cc31  jz      short loc_18015CCB1
0x18015cc33  mov     rax, [rcx]
0x18015cc36  lea     r8, [rsp+380h+var_320]
0x18015cc3b  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x18015cc42  mov     rax, [rax]
0x18015cc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cc4a  test    eax, eax
0x18015cc4c  js      short loc_18015CCB1
0x18015cc4e  mov     rcx, [rsp+380h+var_320]
0x18015cc53  mov     rax, [rcx]
0x18015cc56  mov     [rsp+380h+uFlags], 0
0x18015cc5e  mov     [rsp+380h+uIDAdjustMax], 7FFFh
0x18015cc66  mov     r9d, r15d
0x18015cc69  xor     r8d, r8d
0x18015cc6c  mov     rdx, r12
0x18015cc6f  mov     rax, [rax+18h]
0x18015cc73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cc78  test    eax, eax
0x18015cc7a  js      short loc_18015CCB1
0x18015cc7c  movzx   eax, ax
0x18015cc7f  add     r15d, eax
0x18015cc82  test    edi, edi
0x18015cc84  jz      short loc_18015CCB1
0x18015cc86  mov     rcx, r12; hMenu
0x18015cc89  call    cs:__imp_GetMenuItemCount
0x18015cc8f  mov     edi, eax
0x18015cc91  sub     edi, ebx
0x18015cc93  xor     ebx, ebx
0x18015cc95  test    edi, edi
0x18015cc97  jle     short loc_18015CCB1
0x18015cc99  mov     r8d, 401h; uEnable
0x18015cc9f  mov     edx, ebx; uIDEnableItem
0x18015cca1  mov     rcx, r12; hMenu
0x18015cca4  call    cs:__imp_EnableMenuItem
0x18015ccaa  add     ebx, r14d
0x18015ccad  cmp     ebx, edi
0x18015ccaf  jl      short loc_18015CC99
0x18015ccb1  mov     [rsp+380h+var_314], r15d
0x18015ccb6  test    byte ptr [rsi+0A4h], 10h
0x18015ccbd  jnz     loc_18015CE03
0x18015ccc3  mov     edx, 101h
0x18015ccc8  mov     rcx, cs:g_hinst
0x18015cccf  call    cs:__imp_SHLoadMenuPopup
0x18015ccd5  mov     rbx, rax
0x18015ccd8  xor     edx, edx
0x18015ccda  test    rax, rax
0x18015ccdd  jz      loc_18015CE03
0x18015cce3  cmp     [rsp+380h+var_33C], edx
0x18015cce7  jnz     short loc_18015CCEF
0x18015cce9  cmp     [rsp+380h+var_318], edx
0x18015cced  jz      short loc_18015CD00
0x18015ccef  mov     r8d, r14d; uEnable
0x18015ccf2  mov     edx, r14d; uIDEnableItem
0x18015ccf5  mov     rcx, rbx; hMenu
0x18015ccf8  call    cs:__imp_EnableMenuItem
0x18015ccfe  xor     edx, edx
0x18015cd00  mov     edi, [rsp+380h+var_338]
0x18015cd04  cmp     edi, 0FFFFFFFFh
0x18015cd07  jz      short loc_18015CD61
0x18015cd09  mov     [rsp+380h+var_340], edx
0x18015cd0d  mov     rcx, [rsi+80h]
0x18015cd14  mov     rax, [rcx]
0x18015cd17  mov     [rsp+380h+uFlags], edx
0x18015cd1b  mov     qword ptr [rsp+380h+uIDAdjustMax], rdx
0x18015cd20  lea     r9, [rsp+380h+var_340]
0x18015cd25  xor     r8d, r8d
0x18015cd28  mov     edx, edi
0x18015cd2a  mov     rax, [rax+28h]
0x18015cd2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cd33  test    eax, eax
0x18015cd35  js      short loc_18015CD61
0x18015cd37  test    [rsp+380h+var_340], 1000h
0x18015cd3f  jnz     short loc_18015CD61
0x18015cd41  mov     r9d, r14d; unsigned int
0x18015cd44  mov     r8d, r14d; unsigned int
0x18015cd47  mov     edx, edi; unsigned int
0x18015cd49  mov     rcx, rsi; this
0x18015cd4c  call    ?_IsRestricted@CBandSite@@IEAAJKKK@Z; CBandSite::_IsRestricted(ulong,ulong,ulong)
0x18015cd51  test    eax, eax
0x18015cd53  jz      short loc_18015CD61
0x18015cd55  test    dword ptr [rsi+0A4h], 100h
0x18015cd5f  jz      short loc_18015CD70
0x18015cd61  xor     r8d, r8d; uFlags
0x18015cd64  mov     edx, r14d; uPosition
0x18015cd67  mov     rcx, rbx; hMenu
0x18015cd6a  call    cs:__imp_DeleteMenu
0x18015cd70  test    byte ptr [rsi+0F0h], 8
0x18015cd77  jnz     short loc_18015CD9B
0x18015cd79  xor     r8d, r8d; uFlags
0x18015cd7c  lea     edx, [r8+3]; uPosition
0x18015cd80  mov     rcx, rbx; hMenu
0x18015cd83  call    cs:__imp_DeleteMenu
0x18015cd89  xor     r8d, r8d; uFlags
0x18015cd8c  lea     edx, [r8+4]; uPosition
0x18015cd90  mov     rcx, rbx; hMenu
0x18015cd93  call    cs:__imp_DeleteMenu
0x18015cd99  jmp     short loc_18015CDD4
0x18015cd9b  mov     edx, edi; unsigned int
0x18015cd9d  mov     rcx, rsi; this
0x18015cda0  call    ?_GetAdminSettings@CBandSite@@IEAAKK@Z; CBandSite::_GetAdminSettings(ulong)
0x18015cda5  mov     edi, eax
0x18015cda7  test    r14b, al
0x18015cdaa  jz      short loc_18015CDBD
0x18015cdac  mov     r8d, r14d
0x18015cdaf  mov     edx, 3
0x18015cdb4  mov     rcx, rbx
0x18015cdb7  call    cs:__imp_SHCheckMenuItem
0x18015cdbd  test    dil, 2
0x18015cdc1  jz      short loc_18015CDD4
0x18015cdc3  mov     r8d, r14d
0x18015cdc6  mov     edx, 4
0x18015cdcb  mov     rcx, rbx
0x18015cdce  call    cs:__imp_SHCheckMenuItem
0x18015cdd4  mov     [rsp+380h+uFlags], 0; uFlags
0x18015cddc  mov     [rsp+380h+uIDAdjustMax], 7FFFh; uIDAdjustMax
0x18015cde4  mov     r9d, r15d; uIDAdjust
0x18015cde7  or      r8d, 0FFFFFFFFh; uInsert
0x18015cdeb  mov     rdx, rbx; hmSrc
0x18015cdee  mov     rcx, r12; hmDst
0x18015cdf1  call    cs:__imp_Shell_MergeMenus
0x18015cdf7  mov     r15d, eax
0x18015cdfa  mov     rcx, rbx; hMenu
0x18015cdfd  call    cs:__imp_DestroyMenu
0x18015ce03  mov     rcx, [rsi+78h]
0x18015ce07  test    rcx, rcx
0x18015ce0a  jz      loc_18015CE98
0x18015ce10  mov     rax, [rcx]
0x18015ce13  lea     r8, [rsi+0D8h]
0x18015ce1a  lea     rdx, _GUID_bcfce0a0_ec17_11d0_8d10_00a0c90f2719
0x18015ce21  mov     rax, [rax]
0x18015ce24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ce29  mov     ebx, eax
0x18015ce2b  mov     rcx, [rsi+78h]
0x18015ce2f  mov     rax, [rcx]
0x18015ce32  lea     r8, [rsp+380h+var_330]
0x18015ce37  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x18015ce3e  mov     rax, [rax]
0x18015ce41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ce46  test    eax, eax
0x18015ce48  js      short loc_18015CE98
0x18015ce4a  sar     ebx, 1Fh
0x18015ce4d  and     ebx, 0FFFE0000h
0x18015ce53  add     ebx, 20000h
0x18015ce59  mov     rax, [rsp+380h+var_330]
0x18015ce5e  mov     rcx, [rax]
0x18015ce61  mov     rdi, [rcx+18h]
0x18015ce65  mov     rcx, r12; hMenu
0x18015ce68  call    cs:__imp_GetMenuItemCount
0x18015ce6e  or      ecx, 0FFFFFFFFh
0x18015ce71  cmp     eax, ecx
0x18015ce73  cmovb   ecx, eax
0x18015ce76  mov     [rsp+380h+uFlags], ebx
0x18015ce7a  mov     [rsp+380h+uIDAdjustMax], 7FFFh
0x18015ce82  mov     r9d, r15d
0x18015ce85  mov     r8d, ecx
0x18015ce88  mov     rdx, r12
0x18015ce8b  mov     rcx, [rsp+380h+var_330]
0x18015ce90  mov     rax, rdi
0x18015ce93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ce98  mov     rcx, [rsi+88h]; hWnd
0x18015ce9f  call    cs:__imp_GetParent
0x18015cea5  mov     rdi, rax
0x18015cea8  test    rax, rax
0x18015ceab  jnz     short loc_18015CEB4
0x18015cead  mov     rdi, [rsi+88h]
0x18015ceb4  mov     [rsp+380h+hData], 0
0x18015cebd  mov     [rbp+280h+var_300], 0
0x18015cec5  mov     [rbp+280h+var_2F8], 0
0x18015cecd  mov     [rbp+280h+var_2F0], 0
0x18015ced5  lea     rax, [rsp+380h+hData]
0x18015ceda  mov     qword ptr [rsp+380h+uIDAdjustMax], rax; hData
0x18015cedf  mov     r9d, 8; int
0x18015cee5  lea     r8, [rsp+380h+x]; int
0x18015ceea  mov     rdx, rdi; int
0x18015ceed  mov     rcx, r12; int
0x18015cef0  call    ?ApplyOwnerDrawToMenu@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@PEAUtagPOINT@@W4ImmersiveContextMenuOptions@@AEAV?$CSimplePointerArrayNewMem@UContextMenuRenderingData@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@@@@Z; ImmersiveContextMenuHelper::ApplyOwnerDrawToMenu(HMENU__ *,HWND__ *,tagPOINT *,ImmersiveContextMenuOptions,CSimplePointerArrayNewMem<ContextMenuRenderingData,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>> &)
0x18015cef5  mov     [rsp+380h+prcRect], 0; prcRect
0x18015cefe  mov     qword ptr [rsp+380h+uFlags], rdi; hWnd
0x18015cf03  mov     [rsp+380h+uIDAdjustMax], 0; nReserved
  ... truncated ...
```
