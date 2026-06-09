# CAppListTileElement::InitializeElement(IShellItem *,IPropertyStore *)

- ea: `0x18026fd10`
- end: `0x180270262`
- name: `?InitializeElement@CAppListTileElement@@QEAAJPEAUIShellItem@@PEAUIPropertyStore@@@Z`
- size: `1362`
- prototype: `__int64 __fastcall(CAppListTileElement *__hidden this, struct IShellItem *, struct IPropertyStore *)`
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18026e310`
- `0x18026ef3c`

## callees

- `0x18000aa70`
- `0x180031d20`
- `0x180090bc8`
- `0x1800a03d0`
- `0x1800a0884`
- `0x1800aa9a0`
- `0x1800bfa60`
- `0x180142e10`
- `0x1801e6f3c`
- `0x18026f480`
- `0x18026f724`
- `0x18026fcb4`
- `0x18026fd10`
- `0x180270af4`
- `0x180270ec4`
- `0x180270fc0`
- `0x1802740cc`
- `0x180384b98`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026fed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ffc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802700ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026fed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ff5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18026ffc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180270096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802700ec`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802700db`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1802700db`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18026fe54`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180270115`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18026fe54`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180270115`
- `DUI70!StrToID` at `0x18026fe42`
- `DUI70!StrToID` at `0x180270103`
- `DUI70!StrToID` at `0x18026fe42`
- `DUI70!StrToID` at `0x180270103`
- `DUI70!?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x1802701f1`
- `DUI70!?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z` at `0x1802701f1`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18026ffad`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18026ffad`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x18026feb3`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x18026feb3`

## pseudocode

```c
__int64 __fastcall CAppListTileElement::InitializeElement(
        CAppListTileElement *this,
        struct IShellItem *a2,
        struct IPropertyStore *a3)
{
  struct IShellItem **v6; // r15
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rbx
  __int64 v8; // rax
  int inited; // ebx
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned int Color; // eax
  struct IShellItem *v13; // rdi
  HRESULT (__stdcall *GetDisplayName)(IShellItem *, SIGDN, LPWSTR *); // rbx
  const unsigned __int16 *v15; // rdx
  int v16; // r9d
  HINSTANCE v17; // r8
  const unsigned __int16 *v18; // rdx
  unsigned __int16 v19; // ax
  struct DirectUI::Element *v20; // rax
  int TileStyle; // eax
  int v22; // ecx
  char *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  CShellItemThumbnailElement *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  bool *v31; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  CShellItemThumbnailElement *v33; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  PROPERTYKEY v35; // [rsp+50h] [rbp-B0h] BYREF
  char v36; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+94h] [rbp-6Ch]
  int v40; // [rsp+A4h] [rbp-5Ch]
  __int128 v41; // [rsp+A8h] [rbp-58h]
  int v42; // [rsp+B8h] [rbp-48h]
  PROPERTYKEY v43; // [rsp+BCh] [rbp-44h]
  PROPERTYKEY v44; // [rsp+D0h] [rbp-30h]
  __int128 v45; // [rsp+E4h] [rbp-1Ch]
  int v46; // [rsp+F4h] [rbp-Ch]

  if ( a2 )
  {
    v6 = (struct IShellItem **)((char *)this + 424);
    QueryInterface = a2->lpVtbl->QueryInterface;
    v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>((char *)this + 424);
    inited = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64))QueryInterface)(
               a2,
               &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
               v8);
    if ( inited < 0 )
      return (unsigned int)inited;
    v34[0] = a3;
    if ( a3 )
    {
      ((void (__fastcall *)(struct IPropertyStore *))a3->lpVtbl->AddRef)(a3);
    }
    else
    {
      v38 = 4;
      v37 = PKEY_Tile_Background;
      v40 = 11;
      v39 = PKEY_Tile_LongDisplayName;
      v42 = 18;
      v43 = PKEY_ItemNameDisplay;
      v41 = PKEY_Tile_DisplayNameLanguage;
      v44 = PKEY_AppUserModel_ID;
      v46 = 2;
      v45 = PKEY_ShareTarget_Description;
      inited = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(
                 (unsigned int)v34,
                 (_DWORD)a2,
                 8,
                 (unsigned int)&v37,
                 6);
      if ( inited < 0 )
        goto LABEL_25;
    }
    v10 = StrToID(L"IconBackground");
    LODWORD(pv) = 0;
    Descendent = DirectUI::Element::FindDescendent(this, v10);
    Color = CImmersiveColor::GetColor(10);
    v35.pid = 4;
    v35.fmtid = (GUID)PKEY_Tile_Background;
    if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(v34, &v35, Color, &pv) < 0
      || (inited = DirectUI::Element::SetBackgroundColor(Descendent, (unsigned int)pv | 0xFF000000), inited >= 0) )
    {
      pv = 0;
      CoTaskMemFree(0);
      v35.pid = 11;
      v35.fmtid = (GUID)PKEY_Tile_LongDisplayName;
      if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v34, &v35, &pv) >= 0
        || (CoTaskMemFree(pv),
            v35 = PKEY_ItemNameDisplay,
            (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v34, &v35, &pv) >= 0)
        || (v13 = *v6,
            GetDisplayName = (*v6)->lpVtbl->GetDisplayName,
            CoTaskMemFree(pv),
            inited = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, LPVOID *))GetDisplayName)(v13, 0, &pv),
            inited >= 0) )
      {
        inited = DUI_SetDescendentElementText(this, L"DisplayName", (const unsigned __int16 *)pv, 0);
        if ( inited >= 0 )
        {
          DirectUI::Element::SetAccName(this, (const unsigned __int16 *)pv);
          v33 = 0;
          CoTaskMemFree(0);
          v35.pid = 18;
          v35.fmtid = (GUID)PKEY_Tile_DisplayNameLanguage;
          if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v34, &v35, &v33) >= 0 )
            DUI_SetDescendentElementPreferredFontWithMinimumHeight(this, v15, (const unsigned __int16 *)v33, v16, v31);
          CoTaskMemFree(v33);
          if ( (unsigned int)CAppListTileElement::GetTileStyle(this) == 8 )
          {
            v33 = 0;
            CoTaskMemFree(0);
            v35.pid = 2;
            v35.fmtid = (GUID)PKEY_ShareTarget_Description;
            if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v34, &v35, &v33) >= 0 )
              CAppListTileElement::SetDescription(this, (const unsigned __int16 *)v33, v17);
            CoTaskMemFree(v33);
          }
          CoTaskMemFree(*((LPVOID *)this + 55));
          v35 = PKEY_AppUserModel_ID;
          if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(v34, &v35, (char *)this + 440) < 0 )
            v18 = (const unsigned __int16 *)pv;
          else
            v18 = (const unsigned __int16 *)*((_QWORD *)this + 55);
          DirectUI::Element::SetID(this, v18);
        }
      }
      CoTaskMemFree(pv);
      if ( inited >= 0 )
      {
        v19 = StrToID(L"Icon");
        v20 = DirectUI::Element::FindDescendent(this, v19);
        v33 = 0;
        inited = ElementCast<CShellItemThumbnailElement>(v20, &v33);
        if ( inited >= 0 )
          inited = CShellItemThumbnailElement::SetShellItem(v33, *v6);
      }
    }
LABEL_25:
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v34);
    if ( inited < 0 )
      return (unsigned int)inited;
  }
  TileStyle = CAppListTileElement::GetTileStyle(this);
  v22 = 27;
  if ( TileStyle != 6 )
    v22 = 3;
  LODWORD(pv) = v22;
  v23 = (char *)Microsoft::WRL::Details::Make<CTileActivateBehavior,enum ACTIVATION_TRIGGER_FLAGS &>(&v33, &pv);
  v24 = 0;
  if ( &v36 != v23 )
  {
    v24 = *(_QWORD *)v23;
    *(_QWORD *)v23 = 0;
  }
  v25 = *((_QWORD *)this + 49);
  *((_QWORD *)this + 49) = v24;
  if ( v25 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(v25);
  v26 = v33;
  if ( v33 )
  {
    v33 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(v26);
  }
  v27 = *((_QWORD *)this + 49);
  if ( v27 )
  {
    *(_BYTE *)(v27 + 28) = 1;
    inited = DirectUI::Element::AddBehavior(this, *((struct IDuiBehavior **)this + 49));
    if ( inited >= 0 )
    {
      inited = CAppListTileElement::_InitializeRearrange(this);
      if ( inited >= 0 )
      {
        if ( (v28 = CAppListTileElement::GetTileStyle(this)) != 0 && (v29 = v28 - 1) != 0 && v29 != 7
          || (inited = CAppListTileElement::_InitContextMenu(this), inited >= 0) )
        {
          *((_BYTE *)this + 456) = 1;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18026fd10  mov     [rsp-8+arg_10], rbx
0x18026fd15  push    rbp
0x18026fd16  push    rsi
0x18026fd17  push    rdi
0x18026fd18  push    r14
0x18026fd1a  push    r15
0x18026fd1c  lea     rbp, [rsp-10h]
0x18026fd21  sub     rsp, 110h
0x18026fd28  mov     rax, cs:__security_cookie
0x18026fd2f  xor     rax, rsp
0x18026fd32  mov     [rbp+30h+var_30], rax
0x18026fd36  mov     rdi, r8
0x18026fd39  mov     r14, rdx
0x18026fd3c  mov     rsi, rcx
0x18026fd3f  test    rdx, rdx
0x18026fd42  jz      loc_18027015E
0x18026fd48  mov     rax, [rdx]
0x18026fd4b  lea     r15, [rcx+1A8h]
0x18026fd52  mov     rcx, r15
0x18026fd55  mov     rbx, [rax]
0x18026fd58  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18026fd5d  mov     r8, rax
0x18026fd60  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18026fd67  mov     rax, rbx
0x18026fd6a  mov     rcx, r14
0x18026fd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026fd72  mov     ebx, eax
0x18026fd74  test    eax, eax
0x18026fd76  js      loc_18027023C
0x18026fd7c  mov     [rsp+130h+var_F0], rdi
0x18026fd81  test    rdi, rdi
0x18026fd84  jz      short loc_18026FD9A
0x18026fd86  mov     rax, [rdi]
0x18026fd89  mov     rcx, rdi
0x18026fd8c  mov     rax, [rax+8]
0x18026fd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026fd95  jmp     loc_18026FE3B
0x18026fd9a  movups  xmm0, cs:PKEY_Tile_Background
0x18026fda1  mov     eax, cs:dword_180409FD0
0x18026fda7  lea     r9, [rbp+30h+var_B0]
0x18026fdab  mov     [rbp+30h+var_A0], eax
0x18026fdae  lea     rcx, [rsp+130h+var_F0]
0x18026fdb3  mov     eax, cs:dword_180421D20
0x18026fdb9  mov     r8d, 8
0x18026fdbf  movaps  [rbp+30h+var_B0], xmm0
0x18026fdc3  mov     rdx, r14
0x18026fdc6  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x18026fdcd  mov     [rbp+30h+var_8C], eax
0x18026fdd0  mov     eax, cs:dword_180421DE8
0x18026fdd6  movups  [rbp+30h+var_9C], xmm0
0x18026fdda  mov     [rbp+30h+var_78], eax
0x18026fddd  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x18026fde4  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18026fdea  mov     [rbp+30h+var_64], eax
0x18026fded  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x18026fdf3  movups  [rbp+30h+var_88], xmm0
0x18026fdf7  mov     [rbp+30h+var_50], eax
0x18026fdfa  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18026fe01  mov     eax, cs:dword_180421D70
0x18026fe07  mov     [rbp+30h+var_3C], eax
0x18026fe0a  movups  [rbp+30h+var_74], xmm0
0x18026fe0e  mov     dword ptr [rsp+130h+var_110], 6; bool *
0x18026fe16  movups  xmm0, xmmword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x18026fe1d  movaps  [rbp+30h+var_60], xmm0
0x18026fe21  movups  xmm0, cs:PKEY_ShareTarget_Description
0x18026fe28  movups  [rbp+30h+var_4C], xmm0
0x18026fe2c  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x18026fe31  mov     ebx, eax
0x18026fe33  test    eax, eax
0x18026fe35  js      loc_18027014C
0x18026fe3b  lea     rcx, aIconbackground; "IconBackground"
0x18026fe42  call    cs:__imp_StrToID
0x18026fe49  nop     dword ptr [rax+rax+00h]
0x18026fe4e  movzx   edx, ax
0x18026fe51  mov     rcx, rsi
0x18026fe54  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18026fe5b  nop     dword ptr [rax+rax+00h]
0x18026fe60  mov     ecx, 0Ah
0x18026fe65  mov     dword ptr [rsp+130h+pv], 0
0x18026fe6d  mov     rbx, rax
0x18026fe70  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x18026fe75  mov     ecx, cs:dword_180409FD0
0x18026fe7b  lea     r9, [rsp+130h+pv]
0x18026fe80  movups  xmm0, cs:PKEY_Tile_Background
0x18026fe87  mov     [rsp+130h+var_D0], ecx
0x18026fe8b  lea     rdx, [rsp+130h+var_E0]
0x18026fe90  mov     r8d, eax
0x18026fe93  lea     rcx, [rsp+130h+var_F0]
0x18026fe98  movaps  [rsp+130h+var_E0], xmm0
0x18026fe9d  call    ??$GetAsUInt32WithDefault@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@KPEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32WithDefault<_tagpropertykey>(_tagpropertykey,ulong,ulong *)
0x18026fea2  test    eax, eax
0x18026fea4  js      short loc_18026FEC9
0x18026fea6  mov     edx, dword ptr [rsp+130h+pv]
0x18026feaa  mov     rcx, rbx
0x18026fead  or      edx, 0FF000000h
0x18026feb3  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x18026feba  nop     dword ptr [rax+rax+00h]
0x18026febf  mov     ebx, eax
0x18026fec1  test    eax, eax
0x18026fec3  js      loc_18027014C
0x18026fec9  xor     ecx, ecx; pv
0x18026fecb  mov     [rsp+130h+pv], 0
0x18026fed4  call    cs:__imp_CoTaskMemFree
0x18026fedb  nop     dword ptr [rax+rax+00h]
0x18026fee0  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x18026fee7  mov     eax, cs:dword_180421D20
0x18026feed  lea     r8, [rsp+130h+pv]
0x18026fef2  lea     rdx, [rsp+130h+var_E0]
0x18026fef7  mov     [rsp+130h+var_D0], eax
0x18026fefb  lea     rcx, [rsp+130h+var_F0]
0x18026ff00  movaps  [rsp+130h+var_E0], xmm0
0x18026ff05  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18026ff0a  test    eax, eax
0x18026ff0c  jns     short loc_18026FF84
0x18026ff0e  mov     rcx, [rsp+130h+pv]; pv
0x18026ff13  call    cs:__imp_CoTaskMemFree
0x18026ff1a  nop     dword ptr [rax+rax+00h]
0x18026ff1f  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18026ff26  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18026ff2c  lea     r8, [rsp+130h+pv]
0x18026ff31  lea     rdx, [rsp+130h+var_E0]
0x18026ff36  mov     [rsp+130h+var_D0], eax
0x18026ff3a  lea     rcx, [rsp+130h+var_F0]
0x18026ff3f  movaps  [rsp+130h+var_E0], xmm0
0x18026ff44  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18026ff49  test    eax, eax
0x18026ff4b  jns     short loc_18026FF84
0x18026ff4d  mov     rdi, [r15]
0x18026ff50  mov     rcx, [rsp+130h+pv]; pv
0x18026ff55  mov     rax, [rdi]
0x18026ff58  mov     rbx, [rax+28h]
0x18026ff5c  call    cs:__imp_CoTaskMemFree
0x18026ff63  nop     dword ptr [rax+rax+00h]
0x18026ff68  lea     r8, [rsp+130h+pv]
0x18026ff6d  xor     edx, edx
0x18026ff6f  mov     rcx, rdi
0x18026ff72  mov     rax, rbx
0x18026ff75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ff7a  mov     ebx, eax
0x18026ff7c  test    eax, eax
0x18026ff7e  js      loc_1802700E7
0x18026ff84  mov     r8, [rsp+130h+pv]; unsigned __int16 *
0x18026ff89  lea     rdx, aDisplayname; "DisplayName"
0x18026ff90  xor     r9d, r9d; HINSTANCE
0x18026ff93  mov     rcx, rsi; struct DirectUI::Element *
0x18026ff96  call    ?DUI_SetDescendentElementText@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementText(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x18026ff9b  mov     ebx, eax
0x18026ff9d  test    eax, eax
0x18026ff9f  js      loc_1802700E7
0x18026ffa5  mov     rdx, [rsp+130h+pv]
0x18026ffaa  mov     rcx, rsi
0x18026ffad  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18026ffb4  nop     dword ptr [rax+rax+00h]
0x18026ffb9  xor     ecx, ecx; pv
0x18026ffbb  mov     [rsp+130h+var_F8], 0
0x18026ffc4  call    cs:__imp_CoTaskMemFree
0x18026ffcb  nop     dword ptr [rax+rax+00h]
0x18026ffd0  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x18026ffd7  mov     eax, cs:dword_180421DE8
0x18026ffdd  lea     r8, [rsp+130h+var_F8]
0x18026ffe2  lea     rdx, [rsp+130h+var_E0]
0x18026ffe7  mov     [rsp+130h+var_D0], eax
0x18026ffeb  lea     rcx, [rsp+130h+var_F0]
0x18026fff0  movaps  [rsp+130h+var_E0], xmm0
0x18026fff5  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18026fffa  test    eax, eax
0x18026fffc  js      short loc_18027000B
0x18026fffe  mov     r8, [rsp+130h+var_F8]; unsigned __int16 *
0x180270003  mov     rcx, rsi; struct DirectUI::Element *
0x180270006  call    ?DUI_SetDescendentElementPreferredFontWithMinimumHeight@@YAJPEAVElement@DirectUI@@PEBG1HPEA_N@Z; DUI_SetDescendentElementPreferredFontWithMinimumHeight(DirectUI::Element *,ushort const *,ushort const *,int,bool *)
0x18027000b  mov     rcx, [rsp+130h+var_F8]; pv
0x180270010  call    cs:__imp_CoTaskMemFree
0x180270017  nop     dword ptr [rax+rax+00h]
0x18027001c  mov     rcx, rsi
0x18027001f  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x180270024  cmp     eax, 8
0x180270027  jnz     short loc_18027008C
0x180270029  xor     ecx, ecx; pv
0x18027002b  mov     [rsp+130h+var_F8], 0
0x180270034  call    cs:__imp_CoTaskMemFree
0x18027003b  nop     dword ptr [rax+rax+00h]
0x180270040  movups  xmm0, cs:PKEY_ShareTarget_Description
0x180270047  mov     eax, cs:dword_180421D70
0x18027004d  lea     r8, [rsp+130h+var_F8]
0x180270052  lea     rdx, [rsp+130h+var_E0]
0x180270057  mov     [rsp+130h+var_D0], eax
0x18027005b  lea     rcx, [rsp+130h+var_F0]
0x180270060  movaps  [rsp+130h+var_E0], xmm0
0x180270065  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18027006a  test    eax, eax
0x18027006c  js      short loc_18027007B
0x18027006e  mov     rdx, [rsp+130h+var_F8]; unsigned __int16 *
0x180270073  mov     rcx, rsi; this
0x180270076  call    ?SetDescription@CAppListTileElement@@QEAAJPEBGPEAUHINSTANCE__@@@Z; CAppListTileElement::SetDescription(ushort const *,HINSTANCE__ *)
0x18027007b  mov     rcx, [rsp+130h+var_F8]; pv
0x180270080  call    cs:__imp_CoTaskMemFree
0x180270087  nop     dword ptr [rax+rax+00h]
0x18027008c  lea     rdi, [rsi+1B8h]
0x180270093  mov     rcx, [rdi]; pv
0x180270096  call    cs:__imp_CoTaskMemFree
0x18027009d  nop     dword ptr [rax+rax+00h]
0x1802700a2  movups  xmm0, xmmword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x1802700a9  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x1802700af  lea     rdx, [rsp+130h+var_E0]
0x1802700b4  mov     r8, rdi
0x1802700b7  mov     [rsp+130h+var_D0], eax
0x1802700bb  lea     rcx, [rsp+130h+var_F0]
0x1802700c0  movaps  [rsp+130h+var_E0], xmm0
0x1802700c5  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x1802700ca  mov     rcx, rsi
0x1802700cd  test    eax, eax
0x1802700cf  js      short loc_1802700D6
0x1802700d1  mov     rdx, [rdi]
0x1802700d4  jmp     short loc_1802700DB
0x1802700d6  mov     rdx, [rsp+130h+pv]
0x1802700db  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1802700e2  nop     dword ptr [rax+rax+00h]
0x1802700e7  mov     rcx, [rsp+130h+pv]; pv
0x1802700ec  call    cs:__imp_CoTaskMemFree
0x1802700f3  nop     dword ptr [rax+rax+00h]
0x1802700f8  test    ebx, ebx
0x1802700fa  js      short loc_18027014C
0x1802700fc  lea     rcx, aIcon; "Icon"
0x180270103  call    cs:__imp_StrToID
0x18027010a  nop     dword ptr [rax+rax+00h]
0x18027010f  movzx   edx, ax
0x180270112  mov     rcx, rsi
0x180270115  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18027011c  nop     dword ptr [rax+rax+00h]
0x180270121  lea     rdx, [rsp+130h+var_F8]
0x180270126  mov     [rsp+130h+var_F8], 0
0x18027012f  mov     rcx, rax
0x180270132  call    ??$ElementCast@VCShellItemThumbnailElement@@@@YAJPEAVElement@DirectUI@@PEAPEAVCShellItemThumbnailElement@@@Z; ElementCast<CShellItemThumbnailElement>(DirectUI::Element *,CShellItemThumbnailElement * *)
0x180270137  mov     ebx, eax
0x180270139  test    eax, eax
0x18027013b  js      short loc_18027014C
0x18027013d  mov     rdx, [r15]; struct IShellItem *
0x180270140  mov     rcx, [rsp+130h+var_F8]; this
0x180270145  call    ?SetShellItem@CShellItemThumbnailElement@@QEAAJPEAUIShellItem@@@Z; CShellItemThumbnailElement::SetShellItem(IShellItem *)
0x18027014a  mov     ebx, eax
0x18027014c  lea     rcx, [rsp+130h+var_F0]; this
0x180270151  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x180270156  test    ebx, ebx
0x180270158  js      loc_18027023C
0x18027015e  mov     rcx, rsi
0x180270161  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x180270166  mov     ecx, 1Bh
0x18027016b  cmp     eax, 6
0x18027016e  lea     edx, [rcx-18h]
0x180270171  cmovnz  ecx, edx
0x180270174  lea     rdx, [rsp+130h+pv]
0x180270179  mov     dword ptr [rsp+130h+pv], ecx
0x18027017d  lea     rcx, [rsp+130h+var_F8]
0x180270182  call    ??$Make@VCTileActivateBehavior@@AEAW4ACTIVATION_TRIGGER_FLAGS@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCTileActivateBehavior@@@12@AEAW4ACTIVATION_TRIGGER_FLAGS@@@Z; Microsoft::WRL::Details::Make<CTileActivateBehavior,ACTIVATION_TRIGGER_FLAGS &>(ACTIVATION_TRIGGER_FLAGS &)
0x180270187  xor     ecx, ecx
0x180270189  lea     rdx, [rsp+130h+var_C0]
0x18027018e  cmp     rdx, rax
0x180270191  jz      short loc_18027019D
0x180270193  mov     rcx, [rax]
0x180270196  mov     qword ptr [rax], 0
0x18027019d  mov     rax, [rsi+188h]
0x1802701a4  mov     [rsi+188h], rcx
0x1802701ab  test    rax, rax
0x1802701ae  jz      short loc_1802701B8
0x1802701b0  mov     rcx, rax
0x1802701b3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehavior@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(void)
0x1802701b8  mov     rcx, [rsp+130h+var_F8]
0x1802701bd  test    rcx, rcx
0x1802701c0  jz      short loc_1802701D0
0x1802701c2  mov     [rsp+130h+var_F8], 0
0x1802701cb  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDuiBehavior@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDuiBehavior>::Release(void)
0x1802701d0  mov     rax, [rsi+188h]
0x1802701d7  test    rax, rax
0x1802701da  jnz     short loc_1802701E3
0x1802701dc  mov     ebx, 8007000Eh
0x1802701e1  jmp     short loc_18027023C
0x1802701e3  mov     byte ptr [rax+1Ch], 1
0x1802701e7  mov     rcx, rsi
0x1802701ea  mov     rdx, [rsi+188h]
0x1802701f1  call    cs:__imp_?AddBehavior@Element@DirectUI@@UEAAJPEAUIDuiBehavior@@@Z; DirectUI::Element::AddBehavior(IDuiBehavior *)
0x1802701f8  nop     dword ptr [rax+rax+00h]
0x1802701fd  mov     ebx, eax
0x1802701ff  test    eax, eax
0x180270201  js      short loc_18027023C
0x180270203  mov     rcx, rsi; this
0x180270206  call    ?_InitializeRearrange@CAppListTileElement@@AEAAJXZ; CAppListTileElement::_InitializeRearrange(void)
0x18027020b  mov     ebx, eax
0x18027020d  test    eax, eax
0x18027020f  js      short loc_18027023C
0x180270211  mov     rcx, rsi
0x180270214  call    ?GetTileStyle@CAppListTileElement@@QEAA?AW4TILE_STYLE@@XZ; CAppListTileElement::GetTileStyle(void)
0x180270219  test    eax, eax
0x18027021b  jz      short loc_180270227
0x18027021d  sub     eax, 1
0x180270220  jz      short loc_180270227
0x180270222  cmp     eax, 7
0x180270225  jnz     short loc_180270235
0x180270227  mov     rcx, rsi; this
0x18027022a  call    ?_InitContextMenu@CAppListTileElement@@AEAAJXZ; CAppListTileElement::_InitContextMenu(void)
0x18027022f  mov     ebx, eax
  ... truncated ...
```
