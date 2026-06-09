# CAutoPlayHandlerChooser::TryAddDownloadingHandler(void)

- ea: `0x180195210`
- end: `0x1801959c3`
- name: `?TryAddDownloadingHandler@CAutoPlayHandlerChooser@@MEAAJXZ`
- size: `1971`
- prototype: `__int64 __fastcall(CAutoPlayHandlerChooser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c2560`

## callees

- `0x180009dd0`
- `0x180055128`
- `0x180123ac8`
- `0x180144f2c`
- `0x180144f94`
- `0x180193a88`
- `0x180193bf0`
- `0x180195210`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801957f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801957f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180195822`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180195729`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180195729`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18019523d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18019523d`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1801957db`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x1801957db`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180195835`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180195835`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1801952b8`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1801952b8`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1801956da`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1801956da`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18019557d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1801955ac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18019557d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1801955ac`
- `DUI70!StrToID` at `0x18019556b`
- `DUI70!StrToID` at `0x18019559a`
- `DUI70!StrToID` at `0x18019556b`
- `DUI70!StrToID` at `0x18019559a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180195677`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180195691`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180195677`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180195691`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180195656`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180195656`
- `DUI70!ColorFromEnumI` at `0x1801955e5`
- `DUI70!ColorFromEnumI` at `0x1801955e5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180195514`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180195514`

## pseudocode

```c
__int64 __fastcall CAutoPlayHandlerChooser::TryAddDownloadingHandler(HWND *this)
{
  HRESULT ObjectQuery; // edi
  int ObjectProperties; // eax
  WCHAR *v4; // r15
  WCHAR *v5; // r12
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r10
  __int64 v9; // r11
  __int64 v10; // r15
  __int64 v11; // r12
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r13
  __int64 v17; // rdx
  int *v18; // rdx
  __int64 v19; // r8
  void *p_psz1; // r9
  unsigned int *v21; // rdx
  int v22; // eax
  CAutoPlayHandlerChooser *v23; // rsi
  DirectUI::Element *v24; // rbx
  unsigned __int16 v25; // ax
  DirectUI::Element *Descendent; // r13
  DirectUI::Element *v27; // rbx
  unsigned __int16 v28; // ax
  struct DirectUI::Element *v29; // rax
  struct DirectUI::Element *v30; // r14
  unsigned int v31; // edx
  unsigned __int16 *v32; // rcx
  const unsigned __int16 *v33; // rax
  CAutoPlayHandlerChooser *v34; // rbx
  unsigned int v36; // [rsp+50h] [rbp-29h]
  HRESULT v37; // [rsp+54h] [rbp-25h]
  LPVOID pv; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-19h] BYREF
  __int64 v40; // [rsp+68h] [rbp-11h] BYREF
  PCWSTR psz2; // [rsp+70h] [rbp-9h] BYREF
  PCWSTR psz1; // [rsp+78h] [rbp-1h] BYREF
  __int64 v43; // [rsp+80h] [rbp+7h]
  CAutoPlayHandlerChooser *ppv; // [rsp+E0h] [rbp+67h] BYREF
  char v45; // [rsp+E8h] [rbp+6Fh]
  unsigned int v46; // [rsp+F0h] [rbp+77h] BYREF
  int v47; // [rsp+F8h] [rbp+7Fh]

  ppv = (CAutoPlayHandlerChooser *)this;
  ObjectQuery = 0;
  if ( !IsWindow(this[28]) )
    return (unsigned int)ObjectQuery;
  v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1804CF21C > *(_DWORD *)(v43 + 4) )
  {
    Init_thread_header(&dword_1804CF21C);
    if ( dword_1804CF21C == -1 )
    {
      dword_1804CD2B0 = 12;
      xmmword_1804CD2A0 = DEVPKEY_DeviceSetup_DCA_State;
      dword_1804CD2D0 = 100;
      xmmword_1804CD2C0 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
      dword_1804CD2F0 = 116;
      xmmword_1804CD2E0 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
      dword_1804CD310 = 105;
      xmmword_1804CD300 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
      dword_1804CD330 = 106;
      xmmword_1804CD320 = DEVPKEY_DeviceContainer_DCA_Tile_Background;
      dword_1804CD2B4 = 1;
      qword_1804CD2B8 = 0;
      xmmword_1804CD340 = DEVPKEY_DeviceContainer_DCA_ItemNameDisplay;
      dword_1804CD2D4 = 0;
      qword_1804CD2D8 = 0;
      dword_1804CD2F4 = 0;
      qword_1804CD2F8 = 0;
      dword_1804CD314 = 1;
      qword_1804CD318 = 0;
      dword_1804CD334 = 1;
      qword_1804CD338 = 0;
      dword_1804CD350 = 107;
      dword_1804CD354 = 1;
      qword_1804CD358 = 0;
      Init_thread_footer(&dword_1804CF21C);
    }
  }
  v46 = 0;
  v40 = 0;
  ObjectProperties = DevGetObjectProperties(2, this + 4, 4, 6, &xmmword_1804CD2A0, &v46, &v40);
  ObjectQuery = ObjectProperties;
  if ( ObjectProperties < 0 )
    return (unsigned int)ObjectQuery;
  v4 = 0;
  psz1 = 0;
  v5 = 0;
  psz2 = 0;
  pv = 0;
  v39 = 0;
  if ( v46 != 6 )
  {
    ObjectQuery = -2147418113;
    goto LABEL_74;
  }
  v6 = *((_QWORD *)&DEVPKEY_DeviceSetup_DCA_State + 1);
  v7 = 0;
  v8 = DEVPKEY_DeviceSetup_DCA_State;
  v9 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
  v10 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
  v11 = *((_QWORD *)&DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName + 1);
  v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath + 1);
  v13 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
  v14 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_Background + 1);
  v37 = ObjectProperties;
  v15 = 0;
  v36 = 0;
  v45 = 0;
  v16 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
  v47 = 0;
  do
  {
    v17 = *(unsigned int *)(v40 + 48 * v15 + 16);
    switch ( (_DWORD)v17 )
    {
      case 0xC:
        if ( *(_QWORD *)(v40 + 48 * v15) == v8 && *(_QWORD *)(v40 + 48 * v15 + 8) == v6 )
        {
          v18 = *(int **)(v40 + 48 * v15 + 40);
          if ( v18 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 7 )
              v7 = *v18;
          }
        }
        break;
      case 0x64:
        if ( *(_QWORD *)(v40 + 48 * v15) == v10 && *(_QWORD *)(v40 + 48 * v15 + 8) == v9 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 8210 )
            {
              p_psz1 = &psz1;
LABEL_36:
              _AllocString<CTCoAllocPolicy>(6 * v15, v17, v19, p_psz1);
              v6 = *((_QWORD *)&DEVPKEY_DeviceSetup_DCA_State + 1);
              v8 = DEVPKEY_DeviceSetup_DCA_State;
              v9 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_PackageFamilyName + 1);
              v10 = DEVPKEY_DeviceContainer_DCA_PackageFamilyName;
              v11 = *((_QWORD *)&DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName + 1);
              v16 = DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName;
              v12 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath + 1);
              v13 = DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath;
              v14 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_Tile_Background + 1);
            }
          }
        }
        break;
      case 0x74:
        if ( *(_QWORD *)(v40 + 48 * v15) == v16 && *(_QWORD *)(v40 + 48 * v15 + 8) == v11 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
            {
              p_psz1 = &psz2;
              goto LABEL_36;
            }
          }
        }
        break;
      case 0x6B:
        if ( *(_QWORD *)(v40 + 48 * v15) == (_QWORD)DEVPKEY_DeviceContainer_DCA_ItemNameDisplay )
        {
          v17 = *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_ItemNameDisplay + 1);
          if ( *(_QWORD *)(v40 + 48 * v15 + 8) == *((_QWORD *)&DEVPKEY_DeviceContainer_DCA_ItemNameDisplay + 1) )
          {
            v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
            if ( v19 )
            {
              if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
              {
                p_psz1 = &pv;
                goto LABEL_36;
              }
            }
          }
        }
        break;
      case 0x69:
        if ( *(_QWORD *)(v40 + 48 * v15) == v13 && *(_QWORD *)(v40 + 48 * v15 + 8) == v12 )
        {
          v19 = *(_QWORD *)(v40 + 48 * v15 + 40);
          if ( v19 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 18 )
            {
              p_psz1 = &v39;
              goto LABEL_36;
            }
          }
        }
        break;
      default:
        if ( (_DWORD)v17 == 106
          && *(_QWORD *)(v40 + 48 * v15) == (_QWORD)DEVPKEY_DeviceContainer_DCA_Tile_Background
          && *(_QWORD *)(v40 + 48 * v15 + 8) == v14 )
        {
          v21 = *(unsigned int **)(v40 + 48 * v15 + 40);
          if ( v21 )
          {
            if ( *(_DWORD *)(v40 + 48 * v15 + 32) == 7 )
            {
              v36 = *v21;
              v45 = 1;
            }
          }
        }
        break;
    }
    v15 = (unsigned int)(v47 + 1);
    v47 = v15;
  }
  while ( (unsigned int)v15 < v46 );
  v5 = (WCHAR *)psz2;
  v4 = (WCHAR *)psz1;
  v22 = StrCmpIW(psz1, psz2);
  ObjectQuery = v37;
  v23 = ppv;
  if ( !v22 )
  {
    switch ( v7 )
    {
      case 0:
      case 6:
        if ( dword_1804CF220 > *(_DWORD *)(v43 + 4) )
        {
          Init_thread_header(&dword_1804CF220);
          if ( dword_1804CF220 == -1 )
          {
            dword_1804CD370 = 12;
            xmmword_1804CD360 = DEVPKEY_DeviceSetup_DCA_State;
            dword_1804CD374 = 1;
            qword_1804CD378 = 0;
            Init_thread_footer(&dword_1804CF220);
          }
        }
        ObjectQuery = DevCreateObjectQuery(
                        2,
                        1,
                        1,
                        &xmmword_1804CD360,
                        0,
                        0,
                        CAutoPlayHandlerChooser::DownloadStateChange,
                        v23,
                        (char *)v23 + 288);
        break;
      case 1:
        if ( !*((_DWORD *)ppv + 37) )
        {
          v24 = (DirectUI::Element *)*((_QWORD *)ppv + 29);
          v25 = StrToID(L"eRecommendedGroupTitle");
          Descendent = DirectUI::Element::FindDescendent(v24, v25);
          v27 = (DirectUI::Element *)*((_QWORD *)v23 + 29);
          v28 = StrToID(L"eRecommendedGroupItems");
          v29 = DirectUI::Element::FindDescendent(v27, v28);
          v30 = v29;
          if ( Descendent )
          {
            if ( v29 )
            {
              ppv = 0;
              if ( v45 )
                v31 = v36;
              else
                v31 = ColorFromEnumI(20011);
              v32 = v39;
              if ( !v39 )
                v32 = (unsigned __int16 *)*((_QWORD *)v23 + 38);
              v33 = (const unsigned __int16 *)pv;
              if ( !pv )
                v33 = (const unsigned __int16 *)*((_QWORD *)v23 + 31);
              ObjectQuery = AutoPlayTile::CreateAndInitInProgress(
                              (const struct CDUIResourceManager *)v32,
                              v23,
                              v30,
                              *((const unsigned __int16 **)v23 + 2),
                              *((const unsigned __int16 **)v23 + 3),
                              v33,
                              v32,
                              v31,
                              &ppv);
              if ( ObjectQuery >= 0 )
              {
                v34 = ppv;
                ObjectQuery = DirectUI::Element::Add(v30, ppv);
                if ( ObjectQuery < 0
                  || (*((_QWORD *)v23 + 35) = v34,
                      ObjectQuery = DirectUI::Element::SetLayoutPos(Descendent, 1),
                      ObjectQuery < 0)
                  || (ObjectQuery = DirectUI::Element::SetLayoutPos(v30, 1), ObjectQuery < 0) )
                {
                  if ( v34 )
                  {
                    DirectUI::Element::Destroy(v34, 1);
                    *((_QWORD *)v23 + 35) = 0;
                  }
                }
                else
                {
                  *((_DWORD *)v23 + 37) = 1;
                  CAutoPlayHandlerChooser::TryUpdateManufacturerHeader(v23);
                  (*(void (__fastcall **)(CAutoPlayHandlerChooser *))(*(_QWORD *)v23 + 160LL))(v23);
                }
              }
            }
          }
        }
        break;
      case 4:
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        ObjectQuery = CoCreateInstance(
                        &CLSID_AutoplayHandler,
                        0,
                        3u,
                        &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f,
                        (LPVOID *)&ppv);
        if ( ObjectQuery >= 0 )
        {
          ObjectQuery = (*(__int64 (__fastcall **)(CAutoPlayHandlerChooser *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          *((_QWORD *)v23 + 3));
          if ( ObjectQuery >= 0 )
          {
            ObjectQuery = (*(__int64 (__fastcall **)(CAutoPlayHandlerChooser *, _QWORD))(*(_QWORD *)ppv + 128LL))(
                            ppv,
                            *((_QWORD *)v23 + 2));
            if ( ObjectQuery >= 0 )
              ObjectQuery = CAutoPlayHandlerChooser::AddRecommendedHandler(v23, ppv);
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        break;
    }
  }
LABEL_74:
  CoTaskMemFree(v4);
  CoTaskMemFree(v5);
  CoTaskMemFree(pv);
  CoTaskMemFree(v39);
  DevFreeObjectProperties(v46, v40);
  return (unsigned int)ObjectQuery;
}

```

## disassembly

```asm
0x180195210  mov     [rsp-8+arg_0], rcx
0x180195215  push    rbp
0x180195216  push    rbx
0x180195217  push    rsi
0x180195218  push    rdi
0x180195219  push    r12
0x18019521b  push    r13
0x18019521d  push    r14
0x18019521f  push    r15
0x180195221  lea     rbp, [rsp-1Fh]
0x180195226  sub     rsp, 98h
0x18019522d  mov     rsi, rcx
0x180195230  xor     r13d, r13d
0x180195233  mov     rcx, [rcx+0E0h]; hWnd
0x18019523a  mov     edi, r13d
0x18019523d  call    cs:__imp_IsWindow
0x180195244  nop     dword ptr [rax+rax+00h]
0x180195249  test    eax, eax
0x18019524b  jz      loc_180195841
0x180195251  mov     rax, gs:58h
0x18019525a  lea     ebx, [r13+1]
0x18019525e  mov     edx, cs:_tls_index
0x180195264  mov     ecx, 4
0x180195269  mov     r14, [rax+rdx*8]
0x18019526d  mov     [rbp+57h+var_50], r14
0x180195271  mov     eax, [r14+rcx]
0x180195275  cmp     cs:dword_1804CF21C, eax
0x18019527b  jg      loc_1801958AD
0x180195281  mov     ecx, 2
0x180195286  mov     [rbp+57h+arg_10], r13d
0x18019528a  lea     rax, [rbp+57h+var_68]
0x18019528e  mov     [rbp+57h+var_68], r13
0x180195292  mov     [rsp+0D0h+var_A0], rax
0x180195297  lea     rdx, [rsi+20h]
0x18019529b  lea     rax, [rbp+57h+arg_10]
0x18019529f  mov     [rsp+0D0h+var_A8], rax
0x1801952a4  lea     r9d, [rcx+4]
0x1801952a8  lea     rax, xmmword_1804CD2A0
0x1801952af  lea     r8d, [rcx+2]
0x1801952b3  mov     [rsp+0D0h+ppv], rax
0x1801952b8  call    cs:__imp_DevGetObjectProperties
0x1801952bf  nop     dword ptr [rax+rax+00h]
0x1801952c4  mov     edi, eax
0x1801952c6  test    eax, eax
0x1801952c8  js      loc_180195841
0x1801952ce  cmp     [rbp+57h+arg_10], 6
0x1801952d2  mov     r15, r13
0x1801952d5  mov     [rbp+57h+psz1], r13
0x1801952d9  mov     r12, r13
0x1801952dc  mov     [rbp+57h+psz2], r13
0x1801952e0  mov     [rbp+57h+pv], r13
0x1801952e4  mov     [rbp+57h+var_70], r13
0x1801952e8  jnz     loc_1801957EB
0x1801952ee  mov     r9, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State+8
0x1801952f5  mov     ebx, r13d
0x1801952f8  mov     r10, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State
0x1801952ff  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x180195306  mov     r15, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x18019530d  mov     r12, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName+8
0x180195314  mov     r14, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath+8
0x18019531b  mov     rsi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath
0x180195322  mov     rdi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background+8
0x180195329  mov     [rbp+57h+var_7C], eax
0x18019532c  mov     eax, r13d
0x18019532f  mov     [rbp+57h+var_80], r13d
0x180195333  mov     [rbp+57h+arg_8], r13b
0x180195337  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName
0x18019533e  mov     [rbp+57h+arg_18], eax
0x180195341  lea     rcx, [rax+rax*2]
0x180195345  mov     rax, [rbp+57h+var_68]
0x180195349  add     rcx, rcx
0x18019534c  mov     edx, [rax+rcx*8+10h]
0x180195350  cmp     edx, 0Ch
0x180195353  jnz     short loc_18019538A
0x180195355  cmp     [rax+rcx*8], r10
0x180195359  jnz     loc_1801954F5
0x18019535f  cmp     [rax+rcx*8+8], r9
0x180195364  jnz     loc_1801954F5
0x18019536a  mov     rdx, [rax+rcx*8+28h]
0x18019536f  test    rdx, rdx
0x180195372  jz      loc_1801954F5
0x180195378  cmp     dword ptr [rax+rcx*8+20h], 7
0x18019537d  jnz     loc_1801954F5
0x180195383  mov     ebx, [rdx]
0x180195385  jmp     loc_1801954F5
0x18019538a  cmp     edx, 64h ; 'd'
0x18019538d  jnz     short loc_1801953C9
0x18019538f  cmp     [rax+rcx*8], r15
0x180195393  jnz     loc_1801954F5
0x180195399  cmp     [rax+rcx*8+8], r11
0x18019539e  jnz     loc_1801954F5
0x1801953a4  mov     r8, [rax+rcx*8+28h]
0x1801953a9  test    r8, r8
0x1801953ac  jz      loc_1801954F5
0x1801953b2  cmp     dword ptr [rax+rcx*8+20h], 2012h
0x1801953ba  jnz     loc_1801954F5
0x1801953c0  lea     r9, [rbp+57h+psz1]
0x1801953c4  jmp     loc_18019547C
0x1801953c9  cmp     edx, 74h ; 't'
0x1801953cc  jnz     short loc_180195402
0x1801953ce  cmp     [rax+rcx*8], r13
0x1801953d2  jnz     loc_1801954F5
0x1801953d8  cmp     [rax+rcx*8+8], r12
0x1801953dd  jnz     loc_1801954F5
0x1801953e3  mov     r8, [rax+rcx*8+28h]
0x1801953e8  test    r8, r8
0x1801953eb  jz      loc_1801954F5
0x1801953f1  cmp     dword ptr [rax+rcx*8+20h], 12h
0x1801953f6  jnz     loc_1801954F5
0x1801953fc  lea     r9, [rbp+57h+psz2]
0x180195400  jmp     short loc_18019547C
0x180195402  cmp     edx, 6Bh ; 'k'
0x180195405  jnz     short loc_180195449
0x180195407  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_ItemNameDisplay
0x18019540e  cmp     [rax+rcx*8], rdx
0x180195412  jnz     loc_1801954F5
0x180195418  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_ItemNameDisplay+8
0x18019541f  cmp     [rax+rcx*8+8], rdx
0x180195424  jnz     loc_1801954F5
0x18019542a  mov     r8, [rax+rcx*8+28h]
0x18019542f  test    r8, r8
0x180195432  jz      loc_1801954F5
0x180195438  cmp     dword ptr [rax+rcx*8+20h], 12h
0x18019543d  jnz     loc_1801954F5
0x180195443  lea     r9, [rbp+57h+pv]
0x180195447  jmp     short loc_18019547C
0x180195449  cmp     edx, 69h ; 'i'
0x18019544c  jnz     short loc_1801954C2
0x18019544e  cmp     [rax+rcx*8], rsi
0x180195452  jnz     loc_1801954F5
0x180195458  cmp     [rax+rcx*8+8], r14
0x18019545d  jnz     loc_1801954F5
0x180195463  mov     r8, [rax+rcx*8+28h]
0x180195468  test    r8, r8
0x18019546b  jz      loc_1801954F5
0x180195471  cmp     dword ptr [rax+rcx*8+20h], 12h
0x180195476  jnz     short loc_1801954F5
0x180195478  lea     r9, [rbp+57h+var_70]
0x18019547c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180195481  mov     r9, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State+8
0x180195488  mov     r10, qword ptr cs:DEVPKEY_DeviceSetup_DCA_State
0x18019548f  mov     r11, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName+8
0x180195496  mov     r15, qword ptr cs:DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x18019549d  mov     r12, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName+8
0x1801954a4  mov     r13, qword ptr cs:DEVPKEY_DeviceContainer_AutoPlay_PackageFamilyName
0x1801954ab  mov     r14, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath+8
0x1801954b2  mov     rsi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_KeystoneImagePath
0x1801954b9  mov     rdi, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background+8
0x1801954c0  jmp     short loc_1801954F5
0x1801954c2  cmp     edx, 6Ah ; 'j'
0x1801954c5  jnz     short loc_1801954F5
0x1801954c7  mov     rdx, qword ptr cs:DEVPKEY_DeviceContainer_DCA_Tile_Background
0x1801954ce  cmp     [rax+rcx*8], rdx
0x1801954d2  jnz     short loc_1801954F5
0x1801954d4  cmp     [rax+rcx*8+8], rdi
0x1801954d9  jnz     short loc_1801954F5
0x1801954db  mov     rdx, [rax+rcx*8+28h]
0x1801954e0  test    rdx, rdx
0x1801954e3  jz      short loc_1801954F5
0x1801954e5  cmp     dword ptr [rax+rcx*8+20h], 7
0x1801954ea  jnz     short loc_1801954F5
0x1801954ec  mov     eax, [rdx]
0x1801954ee  mov     [rbp+57h+var_80], eax
0x1801954f1  mov     [rbp+57h+arg_8], 1
0x1801954f5  mov     eax, [rbp+57h+arg_18]
0x1801954f8  inc     eax
0x1801954fa  mov     [rbp+57h+arg_18], eax
0x1801954fd  cmp     eax, [rbp+57h+arg_10]
0x180195500  jb      loc_180195341
0x180195506  mov     r12, [rbp+57h+psz2]
0x18019550a  mov     r15, [rbp+57h+psz1]
0x18019550e  mov     rdx, r12; psz2
0x180195511  mov     rcx, r15; psz1
0x180195514  call    cs:__imp_StrCmpIW
0x18019551b  nop     dword ptr [rax+rax+00h]
0x180195520  mov     edi, [rbp+57h+var_7C]
0x180195523  xor     r13d, r13d
0x180195526  mov     rsi, [rbp+57h+arg_0]
0x18019552a  mov     r14, [rbp+57h+var_50]
0x18019552e  test    eax, eax
0x180195530  jnz     loc_1801957F0
0x180195536  test    ebx, ebx
0x180195538  jz      loc_18019578B
0x18019553e  cmp     ebx, 6
0x180195541  jz      loc_18019578B
0x180195547  cmp     ebx, 1
0x18019554a  jnz     loc_1801956F6
0x180195550  cmp     [rsi+94h], r13d
0x180195557  jnz     loc_1801957F0
0x18019555d  mov     rcx, cs:off_1803F9430; "eRecommendedGroupTitle"
0x180195564  mov     rbx, [rsi+0E8h]
0x18019556b  call    cs:__imp_StrToID
0x180195572  nop     dword ptr [rax+rax+00h]
0x180195577  movzx   edx, ax
0x18019557a  mov     rcx, rbx
0x18019557d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180195584  nop     dword ptr [rax+rax+00h]
0x180195589  mov     rcx, cs:off_1803C4980; "eRecommendedGroupItems"
0x180195590  mov     r13, rax
0x180195593  mov     rbx, [rsi+0E8h]
0x18019559a  call    cs:__imp_StrToID
0x1801955a1  nop     dword ptr [rax+rax+00h]
0x1801955a6  movzx   edx, ax
0x1801955a9  mov     rcx, rbx
0x1801955ac  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1801955b3  nop     dword ptr [rax+rax+00h]
0x1801955b8  mov     r14, rax
0x1801955bb  test    r13, r13
0x1801955be  jz      loc_1801957F0
0x1801955c4  test    rax, rax
0x1801955c7  jz      loc_1801957F0
0x1801955cd  cmp     [rbp+57h+arg_8], 0
0x1801955d1  mov     [rbp+57h+arg_0], 0
0x1801955d9  jz      short loc_1801955E0
0x1801955db  mov     edx, [rbp+57h+var_80]
0x1801955de  jmp     short loc_1801955F3
0x1801955e0  mov     ecx, 4E2Bh
0x1801955e5  call    cs:__imp_ColorFromEnumI
0x1801955ec  nop     dword ptr [rax+rax+00h]
0x1801955f1  mov     edx, eax
0x1801955f3  mov     rcx, [rbp+57h+var_70]
0x1801955f7  test    rcx, rcx
0x1801955fa  jnz     short loc_180195603
0x1801955fc  mov     rcx, [rsi+130h]; struct CDUIResourceManager *
0x180195603  mov     rax, [rbp+57h+pv]
0x180195607  test    rax, rax
0x18019560a  jnz     short loc_180195613
0x18019560c  mov     rax, [rsi+0F8h]
0x180195613  mov     r9, [rsi+10h]; unsigned __int16 *
0x180195617  lea     r8, [rbp+57h+arg_0]
0x18019561b  mov     [rsp+0D0h+var_90], r8; struct DirectUI::Element **
0x180195620  mov     r8, r14; struct DirectUI::Element *
0x180195623  mov     [rsp+0D0h+var_98], edx; unsigned int
0x180195627  mov     rdx, rsi; struct CAutoPlayHandlerChooser *
0x18019562a  mov     [rsp+0D0h+var_A0], rcx; unsigned __int16 *
0x18019562f  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 *
0x180195634  mov     rax, [rsi+18h]
0x180195638  mov     [rsp+0D0h+ppv], rax; unsigned __int16 *
0x18019563d  call    ?CreateAndInitInProgress@AutoPlayTile@@SAJAEBVCDUIResourceManager@@PEAVCAutoPlayHandlerChooser@@PEAVElement@DirectUI@@PEBG333KPEAPEAV45@@Z; AutoPlayTile::CreateAndInitInProgress(CDUIResourceManager const &,CAutoPlayHandlerChooser *,DirectUI::Element *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,DirectUI::Element * *)
0x180195642  mov     edi, eax
0x180195644  test    eax, eax
0x180195646  js      loc_1801957F0
0x18019564c  mov     rbx, [rbp+57h+arg_0]
0x180195650  mov     rcx, r14
0x180195653  mov     rdx, rbx
0x180195656  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18019565d  nop     dword ptr [rax+rax+00h]
0x180195662  mov     edi, eax
0x180195664  test    eax, eax
0x180195666  js      short loc_1801956CC
0x180195668  mov     edx, 1
0x18019566d  mov     [rsi+118h], rbx
0x180195674  mov     rcx, r13
0x180195677  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18019567e  nop     dword ptr [rax+rax+00h]
0x180195683  mov     edi, eax
0x180195685  test    eax, eax
0x180195687  js      short loc_1801956CC
0x180195689  mov     edx, 1
0x18019568e  mov     rcx, r14
0x180195691  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180195698  nop     dword ptr [rax+rax+00h]
0x18019569d  mov     edi, eax
0x18019569f  test    eax, eax
0x1801956a1  js      short loc_1801956CC
0x1801956a3  mov     rcx, rsi; this
0x1801956a6  mov     dword ptr [rsi+94h], 1
0x1801956b0  call    ?TryUpdateManufacturerHeader@CAutoPlayHandlerChooser@@IEAAXXZ; CAutoPlayHandlerChooser::TryUpdateManufacturerHeader(void)
0x1801956b5  mov     rax, [rsi]
0x1801956b8  mov     rcx, rsi
0x1801956bb  mov     rax, [rax+0A0h]
0x1801956c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801956c7  jmp     loc_1801957F0
0x1801956cc  test    rbx, rbx
0x1801956cf  jz      loc_1801957F0
0x1801956d5  mov     dl, 1
0x1801956d7  mov     rcx, rbx
0x1801956da  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1801956e1  nop     dword ptr [rax+rax+00h]
0x1801956e6  mov     qword ptr [rsi+118h], 0
0x1801956f1  jmp     loc_1801957F0
0x1801956f6  cmp     ebx, 4
0x1801956f9  jnz     loc_1801957F0
0x1801956ff  lea     rcx, [rbp+57h+arg_0]
0x180195703  mov     [rbp+57h+arg_0], r13
0x180195707  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18019570c  lea     rax, [rbp+57h+arg_0]
0x180195710  xor     edx, edx; pUnkOuter
0x180195712  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x180195719  mov     [rsp+0D0h+ppv], rax; ppv
0x18019571e  lea     r8d, [rbx-1]; dwClsContext
0x180195722  lea     rcx, CLSID_AutoplayHandler; rclsid
0x180195729  call    cs:__imp_CoCreateInstance
0x180195730  nop     dword ptr [rax+rax+00h]
0x180195735  mov     edi, eax
0x180195737  test    eax, eax
0x180195739  js      short loc_180195780
0x18019573b  mov     rcx, [rbp+57h+arg_0]
0x18019573f  mov     rdx, [rsi+18h]
0x180195743  mov     rax, [rcx]
  ... truncated ...
```
