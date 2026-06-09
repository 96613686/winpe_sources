# CSimpleAppList::WndProc(uint,unsigned __int64,__int64)

- ea: `0x18026ca6c`
- end: `0x18026cf59`
- name: `?WndProc@CSimpleAppList@@QEAA_NI_K_J@Z`
- size: `1261`
- prototype: `bool __fastcall(CSimpleAppList *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18026dc30`

## callees

- `0x180009dd0`
- `0x18000aa70`
- `0x180025710`
- `0x1800a4d94`
- `0x180142e10`
- `0x180269bdc`
- `0x18026c1dc`
- `0x18026ca6c`
- `0x18026cf60`
- `0x18026d368`
- `0x18026d5a0`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026cdcd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026cdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026cb4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ccec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026cb4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ccec`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18026cba8`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x18026cba8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x18026cef3`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x18026cef3`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18026cb0c`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18026ced9`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18026cb0c`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18026ced9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18026cb33`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18026cf09`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18026cb33`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18026cf09`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18026cbd5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18026cbd5`
- `DUI70!StrToID` at `0x18026cbc3`
- `DUI70!StrToID` at `0x18026cbc3`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026cdeb`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026cdeb`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026cb1e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026cb1e`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18026cb68`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18026cd35`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18026cb68`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18026cd35`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026ce2f`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026cf18`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026ce2f`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18026cf18`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026ccca`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026ce7a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026ccca`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18026ce7a`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Unlock` at `0x18026cc87`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Unlock` at `0x18026cc87`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Lock` at `0x18026cc5e`
- `api-ms-win-shell-changenotify-l1-1-1!SHChangeNotification_Lock` at `0x18026cc5e`

## string_xrefs

- `0x18026cbbc`: `LockScreenRemoveApp`

## pseudocode

```c
char __fastcall CSimpleAppList::WndProc(CSimpleAppList *this, int a2, void *a3, ITEMIDLIST *a4)
{
  char v7; // bl
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  unsigned int v12; // edx
  int v13; // eax
  LPITEMIDLIST *v14; // r15
  DirectUI::Element *v15; // rcx
  _DWORD *v16; // rax
  bool v17; // dl
  __int64 v18; // r8
  struct DirectUI::Element **v19; // rcx
  struct DirectUI::Element *Descendent; // rcx
  DirectUI::Element *Parent; // rdi
  unsigned __int16 v22; // ax
  HANDLE v23; // rbx
  const struct _ITEMIDLIST_ABSOLUTE *v24; // r9
  void **ppvItem; // rax
  LPITEMIDLIST *v26; // rdi
  void (__fastcall *v27)(LPITEMIDLIST *, const PROPERTYKEY *, LONG *); // rbx
  _DWORD *Children; // rax
  _DWORD *v29; // r15
  unsigned int v30; // edi
  unsigned int v31; // r12d
  _QWORD *v32; // r13
  struct DirectUI::Element *v33; // r13
  __int64 v34; // rax
  const WCHAR *v35; // rax
  bool v36; // dl
  __int64 v37; // rcx
  __int64 v38; // rcx
  int ScaleFactorForPart; // eax
  LPITEMIDLIST *pppidl; // [rsp+30h] [rbp-30h] BYREF
  LONG plEvent[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v43; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v44[2]; // [rsp+48h] [rbp-18h] BYREF

  v7 = 0;
  v8 = a2 - 1034;
  if ( !v8 )
  {
    pppidl = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    if ( SHCreateItemWithParent(
           *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
           0,
           a4,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           (void **)&pppidl) >= 0 )
    {
      v38 = *((_QWORD *)this + 29);
      *(_QWORD *)plEvent = 0;
      if ( (*(int (__fastcall **)(__int64, LPITEMIDLIST *, __int64, LONG *))(*(_QWORD *)v38 + 48LL))(
             v38,
             pppidl,
             2,
             plEvent) >= 0 )
      {
        ScaleFactorForPart = CLauncherSettings::GetScaleFactorForPart();
        DirectUI::Element::SetWidth(
          *(DirectUI::Element **)plEvent,
          (int)(float)((float)(344 * ScaleFactorForPart) / 100.0));
        if ( (int)DirectUI::Element::Add(
                    this,
                    *(struct DirectUI::Element **)plEvent,
                    (int (*)(const void *, const void *))CSimpleAppList::_s_SortItemsProc) < 0 )
          DirectUI::Element::Destroy(*(DirectUI::Element **)plEvent, 0);
      }
    }
    ILFree(a4);
    v7 = 1;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    return v7;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    *(_QWORD *)plEvent = 0;
    pppidl = 0;
    ppvItem = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&pppidl);
    if ( SHCreateItemWithParent(
           *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
           0,
           a4,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           ppvItem) >= 0 )
    {
      v26 = pppidl;
      v27 = *(void (__fastcall **)(LPITEMIDLIST *, const PROPERTYKEY *, LONG *))((char *)&(*pppidl)[45].mkid.cb + 1);
      CoTaskMemFree(*(LPVOID *)plEvent);
      v27(v26, &PKEY_AppUserModel_ID, plEvent);
    }
    v7 = 1;
    if ( *(_QWORD *)plEvent && **(_WORD **)plEvent )
    {
      v44[0] = 0;
      Children = (_DWORD *)DirectUI::Element::GetChildren(this, v44);
      v29 = Children;
      if ( Children )
      {
        v30 = 0;
        v31 = *Children & 0xFFFFFFF;
        while ( v30 < v31 )
        {
          v32 = v29 + 2;
          if ( (*v29 & 0x10000000) != 0 )
            v32 = (_QWORD *)*v32;
          v33 = (struct DirectUI::Element *)v32[v30];
          if ( v33 )
          {
            v34 = *(_QWORD *)v33;
            v43 = 0;
            if ( (*(int (__fastcall **)(struct DirectUI::Element *, GUID *, __int64 *))(v34 + 200))(
                   v33,
                   &GUID_5b485fb6_49e4_4d60_9ac4_19ea5e074d57,
                   &v43) >= 0 )
            {
              v35 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
              if ( CompareStringOrdinal(*(LPCWCH *)plEvent, -1, v35, -1, 1) != 2 )
              {
                if ( (int)DirectUI::Element::Remove(this, v33) >= 0 && v31 == 1 )
                {
                  CSimpleAppList::_SetEmptyListMessage(this, v36);
                  v37 = *((_QWORD *)this + 26);
                  if ( v37 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 168LL))(v37);
                }
                break;
              }
            }
          }
          ++v30;
        }
      }
      CValuePtr::Release((CValuePtr *)v44);
    }
    ILFree(a4);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pppidl);
    v15 = *(DirectUI::Element **)plEvent;
    goto LABEL_12;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    pppidl = 0;
    plEvent[0] = 0;
    v23 = SHChangeNotification_Lock(a3, (DWORD)a4, &pppidl, plEvent);
    if ( v23 )
    {
      CSimpleAppList::_OnChange(this, plEvent[0], (const struct _ITEMIDLIST_ABSOLUTE *)*pppidl, v24);
      SHChangeNotification_Unlock(v23);
    }
    return 1;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    pppidl = 0;
    v16 = (_DWORD *)DirectUI::Element::GetChildren(this, &pppidl);
    v7 = 1;
    if ( !v16 || (*v16 & 0xFFFFFFF) == 0 )
      goto LABEL_22;
    v19 = (struct DirectUI::Element **)(v16 + 2);
    if ( (*v16 & 0x10000000) != 0 )
      v19 = (struct DirectUI::Element **)*v19;
    Descendent = *v19;
    if ( Descendent )
    {
      if ( (*((_BYTE *)this + 244) & 1) != 0 )
      {
        Parent = DirectUI::Element::GetParent(this);
        if ( !Parent )
          goto LABEL_25;
        v22 = StrToID(L"LockScreenRemoveApp");
        Descendent = DirectUI::Element::FindDescendent(Parent, v22);
        if ( !Descendent )
          goto LABEL_25;
      }
    }
    else
    {
LABEL_22:
      if ( !*((_QWORD *)this + 26) )
      {
LABEL_25:
        if ( (Microsoft_Windows_Immersive_ShellEnableBits & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &MICROSOFT_TWINUI_PUBLISHER_Context,
            LockscreenApplications_LoadPopup_Stop,
            v18,
            1,
            v44);
        CValuePtr::Release((CValuePtr *)&pppidl);
        return v7;
      }
      CSimpleAppList::_SetEmptyListMessage(this, v17);
      Descendent = (struct DirectUI::Element *)*((_QWORD *)this + 26);
    }
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 168LL))(Descendent);
    goto LABEL_25;
  }
  if ( v11 == 1 )
  {
    pppidl = 0;
    if ( (int)CSimpleAppList::_CreatePackageElement(
                this,
                (const unsigned __int16 *)a3,
                (struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *)a4,
                (struct DirectUI::Element **)&pppidl) >= 0 )
    {
      v13 = CLauncherSettings::GetScaleFactorForPart();
      v14 = pppidl;
      DirectUI::Element::SetWidth((DirectUI::Element *)pppidl, (int)(float)((float)(344 * v13) / 100.0));
      if ( (int)DirectUI::Element::Add(this, (struct DirectUI::Element *)v14) < 0 )
        DirectUI::Element::Destroy((DirectUI::Element *)v14, 0);
    }
    if ( a4 )
      CSimpleUserDefaultLocaleCaseInsensitiveStringArray::`scalar deleting destructor'(
        (CSimpleUserDefaultLocaleCaseInsensitiveStringArray *)a4,
        v12);
    v15 = (DirectUI::Element *)a3;
LABEL_12:
    CoTaskMemFree(v15);
  }
  return v7;
}

```

## disassembly

```asm
0x18026ca6c  mov     [rsp-38h+arg_8], rbx
0x18026ca71  push    rbp
0x18026ca72  push    rsi
0x18026ca73  push    rdi
0x18026ca74  push    r12
0x18026ca76  push    r13
0x18026ca78  push    r14
0x18026ca7a  push    r15
0x18026ca7c  mov     rbp, rsp
0x18026ca7f  sub     rsp, 60h
0x18026ca83  mov     rax, cs:__security_cookie
0x18026ca8a  xor     rax, rsp
0x18026ca8d  mov     [rbp+var_8], rax
0x18026ca91  xor     r13d, r13d
0x18026ca94  mov     r14, r9
0x18026ca97  mov     rdi, r8
0x18026ca9a  mov     rsi, rcx
0x18026ca9d  mov     bl, r13b
0x18026caa0  sub     edx, 40Ah
0x18026caa6  jz      loc_18026CE4D
0x18026caac  sub     edx, 1
0x18026caaf  jz      loc_18026CC9D
0x18026cab5  sub     edx, 1
0x18026cab8  jz      loc_18026CC48
0x18026cabe  sub     edx, 1
0x18026cac1  jz      loc_18026CB60
0x18026cac7  cmp     edx, 1
0x18026caca  jnz     loc_18026CF32
0x18026cad0  lea     r9, [rbp+pppidl]; struct DirectUI::Element **
0x18026cad4  mov     [rbp+pppidl], r13
0x18026cad8  mov     r8, r14; struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *
0x18026cadb  mov     rdx, rdi; unsigned __int16 *
0x18026cade  call    ?_CreatePackageElement@CSimpleAppList@@AEAAJPEBGPEAVCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@PEAPEAVElement@DirectUI@@@Z; CSimpleAppList::_CreatePackageElement(ushort const *,CSimpleUserDefaultLocaleCaseInsensitiveStringArray *,DirectUI::Element * *)
0x18026cae3  test    eax, eax
0x18026cae5  js      short loc_18026CB3F
0x18026cae7  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18026caec  mov     r15, [rbp+pppidl]
0x18026caf0  imul    edx, eax, 158h
0x18026caf6  mov     rcx, r15
0x18026caf9  movd    xmm0, edx
0x18026cafd  cvtdq2ps xmm0, xmm0
0x18026cb00  divss   xmm0, cs:__real@42c80000
0x18026cb08  cvttss2si edx, xmm0
0x18026cb0c  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18026cb13  nop     dword ptr [rax+rax+00h]
0x18026cb18  mov     rdx, r15
0x18026cb1b  mov     rcx, rsi
0x18026cb1e  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18026cb25  nop     dword ptr [rax+rax+00h]
0x18026cb2a  test    eax, eax
0x18026cb2c  jns     short loc_18026CB3F
0x18026cb2e  xor     edx, edx
0x18026cb30  mov     rcx, r15
0x18026cb33  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18026cb3a  nop     dword ptr [rax+rax+00h]
0x18026cb3f  test    r14, r14
0x18026cb42  jz      short loc_18026CB4C
0x18026cb44  mov     rcx, r14; this
0x18026cb47  call    ??_GCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@QEAAPEAXI@Z; CSimpleUserDefaultLocaleCaseInsensitiveStringArray::`scalar deleting destructor'(uint)
0x18026cb4c  mov     rcx, rdi; pv
0x18026cb4f  call    cs:__imp_CoTaskMemFree
0x18026cb56  nop     dword ptr [rax+rax+00h]
0x18026cb5b  jmp     loc_18026CF32
0x18026cb60  lea     rdx, [rbp+pppidl]
0x18026cb64  mov     [rbp+pppidl], r13
0x18026cb68  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18026cb6f  nop     dword ptr [rax+rax+00h]
0x18026cb74  mov     ebx, 1
0x18026cb79  test    rax, rax
0x18026cb7c  jz      short loc_18026CBEB
0x18026cb7e  test    dword ptr [rax], 0FFFFFFFh
0x18026cb84  jbe     short loc_18026CBEB
0x18026cb86  test    dword ptr [rax], 10000000h
0x18026cb8c  lea     rcx, [rax+8]
0x18026cb90  jz      short loc_18026CB95
0x18026cb92  mov     rcx, [rcx]
0x18026cb95  mov     rcx, [rcx]
0x18026cb98  test    rcx, rcx
0x18026cb9b  jz      short loc_18026CBEB
0x18026cb9d  test    [rsi+0F4h], bl
0x18026cba3  jz      short loc_18026CC03
0x18026cba5  mov     rcx, rsi
0x18026cba8  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18026cbaf  nop     dword ptr [rax+rax+00h]
0x18026cbb4  mov     rdi, rax
0x18026cbb7  test    rax, rax
0x18026cbba  jz      short loc_18026CC12
0x18026cbbc  lea     rcx, aLockscreenremo; "LockScreenRemoveApp"
0x18026cbc3  call    cs:__imp_StrToID
0x18026cbca  nop     dword ptr [rax+rax+00h]
0x18026cbcf  movzx   edx, ax
0x18026cbd2  mov     rcx, rdi
0x18026cbd5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18026cbdc  nop     dword ptr [rax+rax+00h]
0x18026cbe1  mov     rcx, rax
0x18026cbe4  test    rax, rax
0x18026cbe7  jz      short loc_18026CC12
0x18026cbe9  jmp     short loc_18026CC03
0x18026cbeb  cmp     [rsi+0D0h], r13
0x18026cbf2  jz      short loc_18026CC12
0x18026cbf4  mov     rcx, rsi; this
0x18026cbf7  call    ?_SetEmptyListMessage@CSimpleAppList@@AEAAX_N@Z; CSimpleAppList::_SetEmptyListMessage(bool)
0x18026cbfc  mov     rcx, [rsi+0D0h]
0x18026cc03  mov     rax, [rcx]
0x18026cc06  mov     rax, [rax+0A8h]
0x18026cc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cc12  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 4
0x18026cc19  jz      short loc_18026CC3A
0x18026cc1b  lea     rax, [rbp+var_18]
0x18026cc1f  mov     r9d, ebx
0x18026cc22  lea     rdx, LockscreenApplications_LoadPopup_Stop
0x18026cc29  mov     [rsp+60h+ppvItem], rax
0x18026cc2e  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18026cc35  call    McGenEventWrite_EventWriteTransfer
0x18026cc3a  lea     rcx, [rbp+pppidl]; this
0x18026cc3e  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18026cc43  jmp     loc_18026CF32
0x18026cc48  mov     edx, r14d; dwProcId
0x18026cc4b  mov     [rbp+pppidl], r13
0x18026cc4f  lea     r9, [rbp+plEvent]; plEvent
0x18026cc53  mov     [rbp+plEvent], r13d
0x18026cc57  lea     r8, [rbp+pppidl]; pppidl
0x18026cc5b  mov     rcx, rdi; hChange
0x18026cc5e  call    cs:__imp_SHChangeNotification_Lock
0x18026cc65  nop     dword ptr [rax+rax+00h]
0x18026cc6a  mov     rbx, rax
0x18026cc6d  test    rax, rax
0x18026cc70  jz      short loc_18026CC93
0x18026cc72  mov     r8, [rbp+pppidl]
0x18026cc76  mov     rcx, rsi; this
0x18026cc79  mov     edx, [rbp+plEvent]; int
0x18026cc7c  mov     r8, [r8]; struct _ITEMIDLIST_ABSOLUTE *
0x18026cc7f  call    ?_OnChange@CSimpleAppList@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z; CSimpleAppList::_OnChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x18026cc84  mov     rcx, rbx; hLock
0x18026cc87  call    cs:__imp_SHChangeNotification_Unlock
0x18026cc8e  nop     dword ptr [rax+rax+00h]
0x18026cc93  mov     ebx, 1
0x18026cc98  jmp     loc_18026CF32
0x18026cc9d  lea     rcx, [rbp+pppidl]
0x18026cca1  mov     qword ptr [rbp+plEvent], r13
0x18026cca5  mov     [rbp+pppidl], r13
0x18026cca9  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18026ccae  mov     rcx, [rsi+0C8h]
0x18026ccb5  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18026ccbc  mov     r8, r14; pidl
0x18026ccbf  mov     [rsp+60h+ppvItem], rax; ppvItem
0x18026ccc4  xor     edx, edx; psfParent
0x18026ccc6  mov     rcx, [rcx+18h]; pidlParent
0x18026ccca  call    cs:__imp_SHCreateItemWithParent
0x18026ccd1  nop     dword ptr [rax+rax+00h]
0x18026ccd6  test    eax, eax
0x18026ccd8  js      short loc_18026CD0E
0x18026ccda  mov     rdi, [rbp+pppidl]
0x18026ccde  mov     rcx, qword ptr [rbp+plEvent]; pv
0x18026cce2  mov     rax, [rdi]
0x18026cce5  mov     rbx, [rax+88h]
0x18026ccec  call    cs:__imp_CoTaskMemFree
0x18026ccf3  nop     dword ptr [rax+rax+00h]
0x18026ccf8  lea     r8, [rbp+plEvent]
0x18026ccfc  mov     rcx, rdi
0x18026ccff  lea     rdx, PKEY_AppUserModel_ID
0x18026cd06  mov     rax, rbx
0x18026cd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cd0e  mov     rax, qword ptr [rbp+plEvent]
0x18026cd12  mov     ebx, 1
0x18026cd17  test    rax, rax
0x18026cd1a  jz      loc_18026CE2C
0x18026cd20  cmp     [rax], r13w
0x18026cd24  jz      loc_18026CE2C
0x18026cd2a  lea     rdx, [rbp+var_18]
0x18026cd2e  mov     [rbp+var_18], r13
0x18026cd32  mov     rcx, rsi
0x18026cd35  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18026cd3c  nop     dword ptr [rax+rax+00h]
0x18026cd41  mov     r15, rax
0x18026cd44  test    rax, rax
0x18026cd47  jz      loc_18026CE23
0x18026cd4d  mov     r12d, [rax]
0x18026cd50  mov     edi, r13d
0x18026cd53  and     r12d, 0FFFFFFFh
0x18026cd5a  cmp     edi, r12d
0x18026cd5d  jnb     loc_18026CE23
0x18026cd63  test    dword ptr [r15], 10000000h
0x18026cd6a  lea     r13, [r15+8]
0x18026cd6e  jz      short loc_18026CD74
0x18026cd70  mov     r13, [r13+0]
0x18026cd74  mov     eax, edi
0x18026cd76  mov     r13, [r13+rax*8+0]
0x18026cd7b  test    r13, r13
0x18026cd7e  jz      short loc_18026CDDE
0x18026cd80  mov     rax, [r13+0]
0x18026cd84  lea     r8, [rbp+var_20]
0x18026cd88  lea     rdx, _GUID_5b485fb6_49e4_4d60_9ac4_19ea5e074d57
0x18026cd8f  mov     [rbp+var_20], 0
0x18026cd97  mov     rcx, r13
0x18026cd9a  mov     rax, [rax+0C8h]
0x18026cda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cda6  test    eax, eax
0x18026cda8  js      short loc_18026CDDE
0x18026cdaa  mov     rcx, [rbp+var_20]
0x18026cdae  mov     rax, [rcx]
0x18026cdb1  mov     rax, [rax+8]
0x18026cdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cdba  or      ecx, 0FFFFFFFFh
0x18026cdbd  mov     dword ptr [rsp+60h+ppvItem], ebx; bIgnoreCase
0x18026cdc1  mov     r9d, ecx; cchCount2
0x18026cdc4  mov     edx, ecx; cchCount1
0x18026cdc6  mov     rcx, qword ptr [rbp+plEvent]; lpString1
0x18026cdca  mov     r8, rax; lpString2
0x18026cdcd  call    cs:__imp_CompareStringOrdinal
0x18026cdd4  nop     dword ptr [rax+rax+00h]
0x18026cdd9  cmp     eax, 2
0x18026cddc  jnz     short loc_18026CDE5
0x18026cdde  add     edi, ebx
0x18026cde0  jmp     loc_18026CD5A
0x18026cde5  mov     rdx, r13
0x18026cde8  mov     rcx, rsi
0x18026cdeb  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x18026cdf2  nop     dword ptr [rax+rax+00h]
0x18026cdf7  test    eax, eax
0x18026cdf9  js      short loc_18026CE23
0x18026cdfb  cmp     r12d, ebx
0x18026cdfe  jnz     short loc_18026CE23
0x18026ce00  mov     rcx, rsi; this
0x18026ce03  call    ?_SetEmptyListMessage@CSimpleAppList@@AEAAX_N@Z; CSimpleAppList::_SetEmptyListMessage(bool)
0x18026ce08  mov     rcx, [rsi+0D0h]
0x18026ce0f  test    rcx, rcx
0x18026ce12  jz      short loc_18026CE23
0x18026ce14  mov     rax, [rcx]
0x18026ce17  mov     rax, [rax+0A8h]
0x18026ce1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ce23  lea     rcx, [rbp+var_18]; this
0x18026ce27  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18026ce2c  mov     rcx, r14; pidl
0x18026ce2f  call    cs:__imp_ILFree
0x18026ce36  nop     dword ptr [rax+rax+00h]
0x18026ce3b  lea     rcx, [rbp+pppidl]
0x18026ce3f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026ce44  mov     rcx, qword ptr [rbp+plEvent]
0x18026ce48  jmp     loc_18026CB4F
0x18026ce4d  lea     rcx, [rbp+pppidl]
0x18026ce51  mov     [rbp+pppidl], r13
0x18026ce55  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026ce5a  mov     rcx, [rsi+0C8h]
0x18026ce61  lea     rax, [rbp+pppidl]
0x18026ce65  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18026ce6c  mov     [rsp+60h+ppvItem], rax; ppvItem
0x18026ce71  mov     r8, r14; pidl
0x18026ce74  xor     edx, edx; psfParent
0x18026ce76  mov     rcx, [rcx+18h]; pidlParent
0x18026ce7a  call    cs:__imp_SHCreateItemWithParent
0x18026ce81  nop     dword ptr [rax+rax+00h]
0x18026ce86  test    eax, eax
0x18026ce88  js      loc_18026CF15
0x18026ce8e  mov     rcx, [rsi+0E8h]
0x18026ce95  lea     r9, [rbp+plEvent]
0x18026ce99  mov     rdx, [rbp+pppidl]
0x18026ce9d  mov     r8d, 2
0x18026cea3  mov     qword ptr [rbp+plEvent], r13
0x18026cea7  mov     rax, [rcx]
0x18026ceaa  mov     rax, [rax+30h]
0x18026ceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ceb3  test    eax, eax
0x18026ceb5  js      short loc_18026CF15
0x18026ceb7  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18026cebc  imul    ecx, eax, 158h
0x18026cec2  movd    xmm0, ecx
0x18026cec6  mov     rcx, qword ptr [rbp+plEvent]
0x18026ceca  cvtdq2ps xmm0, xmm0
0x18026cecd  divss   xmm0, cs:__real@42c80000
0x18026ced5  cvttss2si edx, xmm0
0x18026ced9  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18026cee0  nop     dword ptr [rax+rax+00h]
0x18026cee5  mov     rdx, qword ptr [rbp+plEvent]
0x18026cee9  lea     r8, ?_s_SortItemsProc@CSimpleAppList@@CAHPEBX0@Z; CSimpleAppList::_s_SortItemsProc(void const *,void const *)
0x18026cef0  mov     rcx, rsi
0x18026cef3  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z; DirectUI::Element::Add(DirectUI::Element *,int (*)(void const *,void const *))
0x18026cefa  nop     dword ptr [rax+rax+00h]
0x18026ceff  test    eax, eax
0x18026cf01  jns     short loc_18026CF15
0x18026cf03  mov     rcx, qword ptr [rbp+plEvent]
0x18026cf07  xor     edx, edx
0x18026cf09  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18026cf10  nop     dword ptr [rax+rax+00h]
0x18026cf15  mov     rcx, r14; pidl
0x18026cf18  call    cs:__imp_ILFree
0x18026cf1f  nop     dword ptr [rax+rax+00h]
0x18026cf24  lea     rcx, [rbp+pppidl]
0x18026cf28  mov     ebx, 1
0x18026cf2d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18026cf32  mov     al, bl
0x18026cf34  mov     rcx, [rbp+var_8]
0x18026cf38  xor     rcx, rsp; StackCookie
0x18026cf3b  call    __security_check_cookie
0x18026cf40  mov     rbx, [rsp+60h+arg_8]
0x18026cf48  add     rsp, 60h
0x18026cf4c  pop     r15
0x18026cf4e  pop     r14
0x18026cf50  pop     r13
0x18026cf52  pop     r12
  ... truncated ...
```
