# Windows::Internal::CPopupWindowImpl::SetAppItem(IShellItem *)

- ea: `0x18008f570`
- end: `0x18008f8c0`
- name: `?SetAppItem@CPopupWindowImpl@Internal@Windows@@UEAAJPEAUIShellItem@@@Z`
- size: `848`
- prototype: `int(Windows::Internal::CPopupWindowImpl *__hidden this, struct IShellItem *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a910`
- `0x180037a1c`
- `0x180050ba0`
- `0x18008ba54`
- `0x18008ba68`
- `0x18008bb24`
- `0x18008d3f8`
- `0x18008e4a4`
- `0x18008f570`
- `0x1800dc814`
- `0x1800dc8d4`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f838`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f7c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f838`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f5d2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f87e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f5d2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18008f87e`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18008f5a0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18008f7f9`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18008f5a0`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18008f7f9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18008f889`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18008f889`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18008f5bc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18008f5bc`
- `DUI70!StrToID` at `0x18008f5b0`
- `DUI70!StrToID` at `0x18008f5b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::CPopupWindowImpl::SetAppItem(
        Windows::Internal::CPopupWindowImpl *this,
        struct IShellItem *a2)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v7; // r8
  DirectUI::Element *v8; // rsi
  int As; // ebx
  unsigned int v10; // eax
  struct DirectUI::Element *v11; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // edx
  CShellItemThumbnailElement *v15; // r14
  unsigned int v17; // [rsp+30h] [rbp-99h] BYREF
  int v18; // [rsp+34h] [rbp-95h] BYREF
  __int64 v19; // [rsp+38h] [rbp-91h] BYREF
  PROPERTYKEY v20; // [rsp+40h] [rbp-89h] BYREF
  __int64 v21; // [rsp+60h] [rbp-69h] BYREF
  __int64 v22; // [rsp+68h] [rbp-61h]
  __int64 v23; // [rsp+70h] [rbp-59h]
  LPVOID pv; // [rsp+78h] [rbp-51h] BYREF
  __int128 v25; // [rsp+80h] [rbp-49h] BYREF
  int v26; // [rsp+90h] [rbp-39h]
  __int128 v27; // [rsp+94h] [rbp-35h]
  int v28; // [rsp+A4h] [rbp-25h]
  __int128 v29; // [rsp+A8h] [rbp-21h]
  int v30; // [rsp+B8h] [rbp-11h]
  __int128 v31; // [rsp+BCh] [rbp-Dh]
  int v32; // [rsp+CCh] [rbp+3h]
  PROPERTYKEY v33; // [rsp+D0h] [rbp+7h]

  Element = DirectUI::NativeHWNDHost::GetElement((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
  v5 = StrToID(L"AppIconContainer");
  Descendent = DirectUI::Element::FindDescendent(Element, v5);
  v8 = Descendent;
  if ( a2 )
  {
    v25 = PKEY_Tile_Background;
    v26 = 4;
    v27 = PKEY_Tile_DisplayNameLanguage;
    v28 = 18;
    v29 = PKEY_Tile_Foreground;
    v30 = 5;
    v31 = PKEY_Tile_LongDisplayName;
    v32 = 11;
    v33 = PKEY_ItemNameDisplay;
    v19 = 0;
    As = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v19, a2, v7, &v25);
    if ( As >= 0 )
    {
      v18 = 0;
      v20.fmtid = (GUID)PKEY_Tile_Foreground;
      v20.pid = 5;
      As = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v19, &v20, &v18);
      if ( As >= 0 )
      {
        v18 |= 0xFF000000;
        v17 = 0;
        v20.fmtid = (GUID)PKEY_Tile_Background;
        v20.pid = 4;
        As = CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(&v19, &v20, &v17);
        if ( As >= 0 )
        {
          v10 = v17 | 0xFF000000;
          v17 |= 0xFF000000;
          if ( (*((_DWORD *)this + 21) & 0x8000000) == 0 )
          {
            v21 = 0;
            v22 = 0;
            v23 = 0;
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
            v22 = -1;
            v23 = -1;
            v20.fmtid = (GUID)PKEY_Tile_LongDisplayName;
            v20.pid = 11;
            if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &v21) >= 0
              || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21),
                  v22 = -1,
                  v23 = -1,
                  v20 = PKEY_ItemNameDisplay,
                  As = CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &v21),
                  As >= 0) )
            {
              As = (*(__int64 (__fastcall **)(Windows::Internal::CPopupWindowImpl *, __int64))(*(_QWORD *)this + 176LL))(
                     this,
                     v21);
              if ( As >= 0 )
              {
                pv = 0;
                CoTaskMemFree(0);
                v20.fmtid = (GUID)PKEY_Tile_DisplayNameLanguage;
                v20.pid = 18;
                if ( (int)CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v19, &v20, &pv) >= 0 )
                {
                  v11 = DirectUI::NativeHWNDHost::GetElement((Windows::Internal::CPopupWindowImpl *)((char *)this - 56));
                  DUI_SetDescendentElementPreferredFont(v11, v12, (const unsigned __int16 *)pv);
                }
                v13 = FindDescendentElement<CShellItemThumbnailElement>(v8);
                v15 = (CShellItemThumbnailElement *)v13;
                if ( v13 )
                {
                  shell::TaskScheduler::RemoveTasks(*(shell::TaskScheduler **)(v13 + 216), v14);
                  As = CShellItemThumbnailElement::_AsyncPopulateListIcon(v15, a2);
                }
                CoTaskMemFree(pv);
              }
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
            if ( As < 0 )
              goto LABEL_19;
            v10 = v17;
          }
          *((_DWORD *)this + 71) = v10;
          *((_DWORD *)this + 66) = v10;
          *((_DWORD *)this + 67) = v18;
          *((_DWORD *)this + 72) = 7;
          if ( v8 )
          {
            DirectUI::Element::SetLayoutPos(v8, *((_DWORD *)this + 84));
            DirectUI::Element::SetVisible(v8, 1);
          }
        }
      }
    }
LABEL_19:
    DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&v19);
    return (unsigned int)As;
  }
  As = 0;
  DirectUI::Element::SetLayoutPos(Descendent, -3);
  return (unsigned int)As;
}

```

## disassembly

```asm
0x18008f570  mov     [rsp-8+arg_10], rbx
0x18008f575  push    rbp
0x18008f576  push    rsi
0x18008f577  push    rdi
0x18008f578  push    r14
0x18008f57a  push    r15
0x18008f57c  lea     rbp, [rsp-37h]
0x18008f581  sub     rsp, 100h
0x18008f588  mov     rax, cs:__security_cookie
0x18008f58f  xor     rax, rsp
0x18008f592  mov     [rbp+57h+var_30], rax
0x18008f596  mov     r15, rdx
0x18008f599  mov     rdi, rcx
0x18008f59c  add     rcx, 0FFFFFFFFFFFFFFC8h
0x18008f5a0  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18008f5a6  mov     rbx, rax
0x18008f5a9  lea     rcx, aAppiconcontain; "AppIconContainer"
0x18008f5b0  call    cs:__imp_StrToID
0x18008f5b6  movzx   edx, ax
0x18008f5b9  mov     rcx, rbx
0x18008f5bc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18008f5c2  mov     rsi, rax
0x18008f5c5  test    r15, r15
0x18008f5c8  jnz     short loc_18008F5DD
0x18008f5ca  xor     ebx, ebx
0x18008f5cc  lea     edx, [rbx-3]
0x18008f5cf  mov     rcx, rax
0x18008f5d2  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18008f5d8  jmp     loc_18008F89B
0x18008f5dd  movups  xmm0, cs:PKEY_Tile_Background
0x18008f5e4  movaps  [rbp+57h+var_A0], xmm0
0x18008f5e8  mov     eax, cs:dword_180101068
0x18008f5ee  mov     [rbp+57h+var_90], eax
0x18008f5f1  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x18008f5f8  movups  [rbp+57h+var_8C], xmm0
0x18008f5fc  mov     eax, cs:dword_180101080
0x18008f602  mov     [rbp+57h+var_7C], eax
0x18008f605  movups  xmm0, cs:PKEY_Tile_Foreground
0x18008f60c  movups  [rbp+57h+var_78], xmm0
0x18008f610  mov     eax, cs:dword_180101098
0x18008f616  mov     [rbp+57h+var_68], eax
0x18008f619  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x18008f620  movups  [rbp+57h+var_64], xmm0
0x18008f624  mov     eax, cs:dword_1801010B0
0x18008f62a  mov     [rbp+57h+var_54], eax
0x18008f62d  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18008f634  movaps  [rbp+57h+var_50], xmm0
0x18008f638  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18008f63e  mov     [rbp+57h+var_40], eax
0x18008f641  mov     [rsp+120h+var_E8], 0
0x18008f64a  lea     r9, [rbp+57h+var_A0]
0x18008f64e  mov     rdx, r15
0x18008f651  lea     rcx, [rsp+120h+var_E8]
0x18008f656  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x18008f65b  mov     ebx, eax
0x18008f65d  test    eax, eax
0x18008f65f  js      loc_18008F890
0x18008f665  mov     [rsp+120h+var_EC], 0
0x18008f66d  movups  xmm0, cs:PKEY_Tile_Foreground
0x18008f674  movaps  [rsp+120h+var_E0], xmm0
0x18008f679  mov     eax, cs:dword_180101098
0x18008f67f  mov     [rbp+57h+var_D0], eax
0x18008f682  lea     r8, [rsp+120h+var_EC]
0x18008f687  lea     rdx, [rsp+120h+var_E0]
0x18008f68c  lea     rcx, [rsp+120h+var_E8]
0x18008f691  call    ??$GetAsUInt32@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x18008f696  mov     ebx, eax
0x18008f698  test    eax, eax
0x18008f69a  js      loc_18008F890
0x18008f6a0  or      [rsp+120h+var_EC], 0FF000000h
0x18008f6a8  mov     [rsp+120h+var_F0], 0
0x18008f6b0  movups  xmm0, cs:PKEY_Tile_Background
0x18008f6b7  movaps  [rsp+120h+var_E0], xmm0
0x18008f6bc  mov     eax, cs:dword_180101068
0x18008f6c2  mov     [rbp+57h+var_D0], eax
0x18008f6c5  lea     r8, [rsp+120h+var_F0]
0x18008f6ca  lea     rdx, [rsp+120h+var_E0]
0x18008f6cf  lea     rcx, [rsp+120h+var_E8]
0x18008f6d4  call    ??$GetAsUInt32@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAK@Z; CPropertyStoreHelperBase<IPropertyStore>::GetAsUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x18008f6d9  mov     ebx, eax
0x18008f6db  test    eax, eax
0x18008f6dd  js      loc_18008F890
0x18008f6e3  mov     eax, [rsp+120h+var_F0]
0x18008f6e7  or      eax, 0FF000000h
0x18008f6ec  mov     [rsp+120h+var_F0], eax
0x18008f6f0  test    dword ptr [rdi+54h], 8000000h
0x18008f6f7  jnz     loc_18008F850
0x18008f6fd  mov     [rbp+57h+var_C0], 0
0x18008f705  mov     [rbp+57h+var_B8], 0
0x18008f70d  mov     [rbp+57h+var_B0], 0
0x18008f715  lea     rcx, [rbp+57h+var_C0]
0x18008f719  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008f71e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008f722  mov     [rbp+57h+var_B8], rbx
0x18008f726  mov     [rbp+57h+var_B0], rbx
0x18008f72a  movups  xmm0, cs:PKEY_Tile_LongDisplayName
0x18008f731  movaps  [rsp+120h+var_E0], xmm0
0x18008f736  mov     eax, cs:dword_1801010B0
0x18008f73c  mov     [rbp+57h+var_D0], eax
0x18008f73f  lea     r8, [rbp+57h+var_C0]
0x18008f743  lea     rdx, [rsp+120h+var_E0]
0x18008f748  lea     rcx, [rsp+120h+var_E8]
0x18008f74d  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18008f752  test    eax, eax
0x18008f754  jns     short loc_18008F799
0x18008f756  lea     rcx, [rbp+57h+var_C0]
0x18008f75a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008f75f  mov     [rbp+57h+var_B8], rbx
0x18008f763  mov     [rbp+57h+var_B0], rbx
0x18008f767  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18008f76e  movaps  [rsp+120h+var_E0], xmm0
0x18008f773  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18008f779  mov     [rbp+57h+var_D0], eax
0x18008f77c  lea     r8, [rbp+57h+var_C0]
0x18008f780  lea     rdx, [rsp+120h+var_E0]
0x18008f785  lea     rcx, [rsp+120h+var_E8]
0x18008f78a  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18008f78f  mov     ebx, eax
0x18008f791  test    eax, eax
0x18008f793  js      loc_18008F83F
0x18008f799  mov     rax, [rdi]
0x18008f79c  mov     rdx, [rbp+57h+var_C0]
0x18008f7a0  mov     rcx, rdi
0x18008f7a3  mov     rax, [rax+0B0h]
0x18008f7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f7af  mov     ebx, eax
0x18008f7b1  test    eax, eax
0x18008f7b3  js      loc_18008F83F
0x18008f7b9  mov     [rbp+57h+pv], 0
0x18008f7c1  xor     ecx, ecx; pv
0x18008f7c3  call    cs:__imp_CoTaskMemFree
0x18008f7c9  movups  xmm0, cs:PKEY_Tile_DisplayNameLanguage
0x18008f7d0  movaps  [rsp+120h+var_E0], xmm0
0x18008f7d5  mov     eax, cs:dword_180101080
0x18008f7db  mov     [rbp+57h+var_D0], eax
0x18008f7de  lea     r8, [rbp+57h+pv]
0x18008f7e2  lea     rdx, [rsp+120h+var_E0]
0x18008f7e7  lea     rcx, [rsp+120h+var_E8]
0x18008f7ec  call    ??$GetString@U_tagpropertykey@@@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEBAJU_tagpropertykey@@PEAPEAG@Z; CPropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18008f7f1  test    eax, eax
0x18008f7f3  js      short loc_18008F80B
0x18008f7f5  lea     rcx, [rdi-38h]
0x18008f7f9  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x18008f7ff  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x18008f803  mov     rcx, rax; struct DirectUI::Element *
0x18008f806  call    ?DUI_SetDescendentElementPreferredFont@@YAJPEAVElement@DirectUI@@PEBG1@Z; DUI_SetDescendentElementPreferredFont(DirectUI::Element *,ushort const *,ushort const *)
0x18008f80b  mov     rcx, rsi
0x18008f80e  call    ??$FindDescendentElement@VCShellItemThumbnailElement@@@@YAPEAVCShellItemThumbnailElement@@PEAVElement@DirectUI@@@Z; FindDescendentElement<CShellItemThumbnailElement>(DirectUI::Element *)
0x18008f813  mov     r14, rax
0x18008f816  test    rax, rax
0x18008f819  jz      short loc_18008F834
0x18008f81b  mov     rcx, [rax+0D8h]; this
0x18008f822  call    ?RemoveTasks@TaskScheduler@shell@@QEAAJH@Z; shell::TaskScheduler::RemoveTasks(int)
0x18008f827  mov     rdx, r15; struct IShellItem *
0x18008f82a  mov     rcx, r14; this
0x18008f82d  call    ?_AsyncPopulateListIcon@CShellItemThumbnailElement@@AEAAJPEAUIShellItem@@@Z; CShellItemThumbnailElement::_AsyncPopulateListIcon(IShellItem *)
0x18008f832  mov     ebx, eax
0x18008f834  mov     rcx, [rbp+57h+pv]; pv
0x18008f838  call    cs:__imp_CoTaskMemFree
0x18008f83e  nop
0x18008f83f  lea     rcx, [rbp+57h+var_C0]
0x18008f843  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18008f848  test    ebx, ebx
0x18008f84a  js      short loc_18008F890
0x18008f84c  mov     eax, [rsp+120h+var_F0]
0x18008f850  mov     [rdi+11Ch], eax
0x18008f856  mov     [rdi+108h], eax
0x18008f85c  mov     eax, [rsp+120h+var_EC]
0x18008f860  mov     [rdi+10Ch], eax
0x18008f866  mov     dword ptr [rdi+120h], 7
0x18008f870  test    rsi, rsi
0x18008f873  jz      short loc_18008F890
0x18008f875  mov     edx, [rdi+150h]
0x18008f87b  mov     rcx, rsi
0x18008f87e  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18008f884  mov     dl, 1
0x18008f886  mov     rcx, rsi
0x18008f889  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18008f88f  nop
0x18008f890  lea     rcx, [rsp+120h+var_E8]; this
0x18008f895  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x18008f89a  nop
0x18008f89b  mov     eax, ebx
0x18008f89d  mov     rcx, [rbp+57h+var_30]
0x18008f8a1  xor     rcx, rsp; StackCookie
0x18008f8a4  call    __security_check_cookie
0x18008f8a9  mov     rbx, [rsp+120h+arg_10]
0x18008f8b1  add     rsp, 100h
0x18008f8b8  pop     r15
0x18008f8ba  pop     r14
0x18008f8bc  pop     rdi
0x18008f8bd  pop     rsi
0x18008f8be  pop     rbp
0x18008f8bf  retn
```
