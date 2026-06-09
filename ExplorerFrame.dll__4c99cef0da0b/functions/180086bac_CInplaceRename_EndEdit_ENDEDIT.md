# CInplaceRename::_EndEdit(ENDEDIT)

- ea: `0x180086bac`
- end: `0x1800870c9`
- name: `?_EndEdit@CInplaceRename@@AEAAXW4ENDEDIT@@@Z`
- size: `1309`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800846ac`
- `0x180088518`
- `0x1800aa860`
- `0x1801069b0`
- `0x1801f7ef0`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x1800218ac`
- `0x180026424`
- `0x180033370`
- `0x18003c21c`
- `0x18003f6f0`
- `0x18007f150`
- `0x180086bac`
- `0x1800870d0`
- `0x1800872a4`
- `0x180087310`
- `0x18008a204`
- `0x1800b2c28`
- `0x1800cfa2c`
- `0x18010183c`
- `0x180104ab0`
- `0x180124710`
- `0x18012e288`
- `0x1801e2cec`
- `0x1801f7fe0`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180086e4e`
- `SHCORE!IUnknown_QueryService` at `0x180086e4e`
- `SHELL32!__imp_SHLimitInputEndSubclass` at `0x180086c85`
- `SHELL32!__imp_SHLimitInputEndSubclass` at `0x180086c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087066`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180086dd2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180086dd2`
- `GDI32!DeleteObject` at `0x180086cfe`
- `GDI32!DeleteObject` at `0x180086cfe`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180087052`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180087052`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180086fe3`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18008700a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180086fe3`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18008700a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180086d3f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180086d3f`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180086c2e`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180086c2e`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x180086c18`
- `DUI70!?HasContent@Element@DirectUI@@QEAA_NXZ` at `0x180086c18`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CInplaceRename::_EndEdit(__int64 a1, int a2)
{
  const WCHAR *ContentString; // rsi
  UIItemsView *v5; // rcx
  HWND v6; // rax
  __int64 v7; // rax
  CInplaceRename *v8; // rcx
  struct DirectUI::Element *v9; // rdx
  DirectUI::Element *v10; // rcx
  void *v11; // rcx
  DirectUI::Value *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  UIItemsView *v15; // rbx
  void **v16; // rax
  __int64 v17; // r8
  void *v18; // rcx
  __int64 v19; // rdx
  IUnknown *v20; // rcx
  __int64 v21; // rbx
  DirectUI::Element *NameProperty; // rax
  DirectUI::Element *Descendent; // rax
  __int64 v24; // rdx
  struct IListControlHost *v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  struct DirectUI::Value *v27; // [rsp+50h] [rbp-10h] BYREF
  void *ppvOut; // [rsp+A0h] [rbp+40h] BYREF
  IUnknown *punk; // [rsp+B0h] [rbp+50h] BYREF
  struct IItem *v30; // [rsp+B8h] [rbp+58h] BYREF

  if ( *(_DWORD *)(a1 + 200) != 3 )
  {
    if ( (unsigned int)CInplaceRename::_IsDBCSorIMEEnabled((CInplaceRename *)a1) )
      CInplaceRename::_EndComposition((CInplaceRename *)a1);
    *(_DWORD *)(a1 + 200) = 3;
    if ( *(_QWORD *)(a1 + 168) )
      CSafeElementListenerPtr<DirectUI::Element>::ReleaseListener();
    ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v25);
    ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&v30);
    v27 = 0;
    if ( DirectUI::Element::HasContent(*(DirectUI::Element **)(a1 + 48)) )
      ContentString = DirectUI::Element::GetContentString(*(DirectUI::Element **)(a1 + 48), &v27);
    else
      ContentString = &WindowName;
    v5 = *(UIItemsView **)(a1 + 136);
    if ( v5 )
    {
      if ( (int)UIItemsView::GetListControlHost(v5, &v25) >= 0 )
      {
        v13 = *(_QWORD *)(a1 + 104);
        if ( v13 )
          (*(void (__fastcall **)(__int64, struct IItem **))(*(_QWORD *)v13 + 440LL))(v13, &v30);
      }
    }
    v6 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 360LL))(*(_QWORD *)(a1 + 48));
    RemoveWindowSubclass(v6, CInplaceRename::s_EditSubclassProc, 1u);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 360LL))(*(_QWORD *)(a1 + 48));
    SHLimitInputEndSubclass(v7);
    CInplaceRename::_HookMouse((CInplaceRename *)a1, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( a2 == 1 && v30 && ContentString && CompareStringOrdinal(*(LPCWCH *)(a1 + 224), -1, ContentString, -1, 0) != 2 )
    {
      if ( v25 )
      {
        if ( *(_BYTE *)(a1 + 240) )
        {
          punk = 0;
          v15 = *(UIItemsView **)(a1 + 136);
          if ( v15
            && (Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&punk),
                UIItemsView::GetSite(v15, &punk),
                punk) )
          {
            ppvOut = 0;
            Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&ppvOut);
            if ( IUnknown_QueryService(punk, &IID_IFolderView, &GUID_831d1dff_7f57_4720_87e4_cb57d6214428, &ppvOut) >= 0 )
              (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppvOut + 32LL))(ppvOut, 13);
            v26 = 0;
            v16 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&v26);
            IItem_QIorBind(v30, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v16);
            _Fire_CommandHandlerInvokeTelemetry(12357, 0, v17, 2, v26, punk, 1);
            v18 = ppvOut;
            if ( ppvOut )
            {
              (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 32LL))(ppvOut, 0);
              v18 = ppvOut;
            }
            v19 = v26;
            if ( v26 )
            {
              v26 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              v18 = ppvOut;
            }
            if ( v18 )
            {
              ppvOut = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
            }
          }
          else
          {
            _Fire_CommandHandlerInvokeTelemetry(12357, 13, v14, 2, 0, 0, 0);
          }
          v20 = punk;
          if ( punk )
          {
            punk = 0;
            ((void (__fastcall *)(IUnknown *))v20->lpVtbl->Release)(v20);
          }
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 176LL))(*(_QWORD *)(a1 + 192));
        v21 = ATL::CComPtrBase<IUICommandHandler>::operator->(&v25);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 224LL))(v21);
        (*(void (__fastcall **)(__int64, struct IItem *, const WCHAR *, _QWORD))(*(_QWORD *)v21 + 104LL))(
          v21,
          v30,
          ContentString,
          *(unsigned int *)(a1 + 256));
      }
    }
    else
    {
      v8 = v25;
      if ( v25 )
        (*(void (__fastcall **)(struct IListControlHost *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v25 + 104LL))(
          v25,
          0,
          0,
          *(unsigned int *)(a1 + 256));
    }
    *(_BYTE *)(a1 + 240) = 0;
    *(_DWORD *)(a1 + 256) = 0;
    v9 = *(struct DirectUI::Element **)(a1 + 104);
    if ( v9 )
    {
      NameProperty = CInplaceRename::_FindNameProperty(v8, v9);
      DirectUI::Element::SetVisible(NameProperty, 1);
      *(_DWORD *)(*(_QWORD *)(a1 + 104) + 244LL) = 1;
      Descendent = (DirectUI::Element *)FindDescendentElement<UITilesPropertyCollection>(*(_QWORD *)(a1 + 104));
      if ( Descendent )
        DirectUI::Element::SetVisible(Descendent, 1);
      if ( GetUIItemsView(*(struct DirectUI::Element **)(a1 + 104)) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 168LL))(*(_QWORD *)(a1 + 104));
        CSafeElementListenerPtr<UIRenameTextElement>::ReleaseListener(a1 + 96);
      }
      else
      {
        UIItemsView::RestoreListFocus(*(UIItemsView **)(a1 + 136));
      }
    }
    v10 = *(DirectUI::Element **)(a1 + 48);
    if ( v10 )
    {
      DirectUI::Element::Destroy(v10, 1);
      CSafeElementListenerPtr<UIRenameTextElement>::ReleaseListener(a1 + 40);
    }
    *(_DWORD *)(a1 + 200) = 0;
    v11 = *(void **)(a1 + 224);
    if ( v11 )
    {
      CoTaskMemFree(v11);
      *(_QWORD *)(a1 + 224) = 0;
    }
    DeleteObject(*(HGDIOBJ *)(a1 + 72));
    *(_QWORD *)(a1 + 72) = 0;
    if ( a2 == 1 )
      *(_DWORD *)(a1 + 248) = 1;
    if ( *(_QWORD *)(a1 + 136) )
    {
      ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&ppvOut);
      ATL::CComPtrBase<IEventQueue>::CopyTo(v24 + 648, &ppvOut);
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 80LL))(ppvOut, 0);
      *(_DWORD *)(a1 + 236) = 0;
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&ppvOut);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    v12 = v27;
    if ( v27 )
    {
      v27 = 0;
      DirectUI::Value::Release(v12);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v30);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v25);
  }
}

```

## disassembly

```asm
0x180086bac  push    rbp
0x180086bae  push    rbx
0x180086baf  push    rsi
0x180086bb0  push    rdi
0x180086bb1  push    r12
0x180086bb3  push    r14
0x180086bb5  push    r15
0x180086bb7  mov     rbp, rsp
0x180086bba  sub     rsp, 60h
0x180086bbe  mov     r15d, edx
0x180086bc1  mov     rdi, rcx
0x180086bc4  cmp     dword ptr [rcx+0C8h], 3
0x180086bcb  jz      loc_180086D59
0x180086bd1  call    ?_IsDBCSorIMEEnabled@CInplaceRename@@AEAAHXZ; CInplaceRename::_IsDBCSorIMEEnabled(void)
0x180086bd6  xor     r12d, r12d
0x180086bd9  test    eax, eax
0x180086bdb  jnz     loc_180086F97
0x180086be1  mov     dword ptr [rdi+0C8h], 3
0x180086beb  lea     rcx, [rdi+0A0h]
0x180086bf2  cmp     [rcx+8], r12
0x180086bf6  jnz     loc_180086FA4
0x180086bfc  lea     rcx, [rbp+var_20]; void *
0x180086c00  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180086c05  nop
0x180086c06  lea     rcx, [rbp+arg_18]; void *
0x180086c0a  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180086c0f  nop
0x180086c10  mov     [rbp+var_10], r12
0x180086c14  mov     rcx, [rdi+30h]
0x180086c18  call    cs:__imp_?HasContent@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasContent(void)
0x180086c1e  test    al, al
0x180086c20  jz      loc_180086D68
0x180086c26  lea     rdx, [rbp+var_10]
0x180086c2a  mov     rcx, [rdi+30h]
0x180086c2e  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x180086c34  mov     rsi, rax
0x180086c37  mov     rcx, [rdi+88h]; this
0x180086c3e  test    rcx, rcx
0x180086c41  jnz     loc_180086D74
0x180086c47  mov     rcx, [rdi+30h]
0x180086c4b  mov     rax, [rcx]
0x180086c4e  mov     rax, [rax+168h]
0x180086c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c5a  mov     rcx, rax; hWnd
0x180086c5d  mov     r8d, 1; uIdSubclass
0x180086c63  lea     rdx, ?s_EditSubclassProc@CInplaceRename@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x180086c6a  call    RemoveWindowSubclass
0x180086c6f  mov     rcx, [rdi+30h]
0x180086c73  mov     rax, [rcx]
0x180086c76  mov     rax, [rax+168h]
0x180086c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c82  mov     rcx, rax
0x180086c85  call    cs:__imp_SHLimitInputEndSubclass
0x180086c8b  xor     edx, edx; int
0x180086c8d  mov     rcx, rdi; this
0x180086c90  call    ?_HookMouse@CInplaceRename@@AEAAHH@Z; CInplaceRename::_HookMouse(int)
0x180086c95  mov     rax, [rdi]
0x180086c98  mov     rcx, rdi
0x180086c9b  mov     rax, [rax+8]
0x180086c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ca4  cmp     r15d, 1
0x180086ca8  jz      loc_180086DAA
0x180086cae  mov     rcx, [rbp+var_20]; this
0x180086cb2  test    rcx, rcx
0x180086cb5  jnz     loc_180086FC8
0x180086cbb  mov     [rdi+0F0h], r12b
0x180086cc2  mov     [rdi+100h], r12d
0x180086cc9  mov     rdx, [rdi+68h]; struct DirectUI::Element *
0x180086ccd  test    rdx, rdx
0x180086cd0  jnz     loc_180086FD9
0x180086cd6  mov     rcx, [rdi+30h]
0x180086cda  test    rcx, rcx
0x180086cdd  jnz     loc_180087050
0x180086ce3  mov     [rdi+0C8h], r12d
0x180086cea  mov     rcx, [rdi+0E0h]; pv
0x180086cf1  test    rcx, rcx
0x180086cf4  jnz     loc_180087066
0x180086cfa  mov     rcx, [rdi+48h]; ho
0x180086cfe  call    cs:__imp_DeleteObject
0x180086d04  mov     [rdi+48h], r12
0x180086d08  cmp     r15d, 1
0x180086d0c  jz      loc_180087078
0x180086d12  mov     rdx, [rdi+88h]
0x180086d19  test    rdx, rdx
0x180086d1c  jnz     loc_180087087
0x180086d22  mov     rax, [rdi]
0x180086d25  mov     rcx, rdi
0x180086d28  mov     rax, [rax+10h]
0x180086d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086d31  nop
0x180086d32  mov     rcx, [rbp+var_10]
0x180086d36  test    rcx, rcx
0x180086d39  jz      short loc_180086D46
0x180086d3b  mov     [rbp+var_10], r12
0x180086d3f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180086d45  nop
0x180086d46  lea     rcx, [rbp+arg_18]; void *
0x180086d4a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180086d4f  nop
0x180086d50  lea     rcx, [rbp+var_20]; void *
0x180086d54  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180086d59  add     rsp, 60h
0x180086d5d  pop     r15
0x180086d5f  pop     r14
0x180086d61  pop     r12
0x180086d63  pop     rdi
0x180086d64  pop     rsi
0x180086d65  pop     rbx
0x180086d66  pop     rbp
0x180086d67  retn
0x180086d68  lea     rsi, WindowName
0x180086d6f  jmp     loc_180086C37
0x180086d74  lea     rdx, [rbp+var_20]; struct IListControlHost **
0x180086d78  call    ?GetListControlHost@UIItemsView@@QEAAJPEAPEAUIListControlHost@@@Z; UIItemsView::GetListControlHost(IListControlHost * *)
0x180086d7d  test    eax, eax
0x180086d7f  js      loc_180086C47
0x180086d85  mov     rcx, [rdi+68h]
0x180086d89  test    rcx, rcx
0x180086d8c  jz      loc_180086C47
0x180086d92  mov     rax, [rcx]
0x180086d95  lea     rdx, [rbp+arg_18]
0x180086d99  mov     rax, [rax+1B8h]
0x180086da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086da5  jmp     loc_180086C47
0x180086daa  cmp     [rbp+arg_18], r12
0x180086dae  jz      loc_180086CAE
0x180086db4  test    rsi, rsi
0x180086db7  jz      loc_180086CAE
0x180086dbd  mov     [rsp+60h+bIgnoreCase], r12d; bIgnoreCase
0x180086dc2  or      edx, 0FFFFFFFFh; cchCount1
0x180086dc5  mov     r9d, edx; cchCount2
0x180086dc8  mov     r8, rsi; lpString2
0x180086dcb  mov     rcx, [rdi+0E0h]; lpString1
0x180086dd2  call    cs:__imp_CompareStringOrdinal
0x180086dd8  cmp     eax, 2
0x180086ddb  jz      loc_180086CAE
0x180086de1  cmp     [rbp+var_20], r12
0x180086de5  jz      loc_180086CBB
0x180086deb  cmp     [rdi+0F0h], r12b
0x180086df2  jz      loc_180086F03
0x180086df8  mov     [rbp+punk], r12
0x180086dfc  mov     rbx, [rdi+88h]
0x180086e03  test    rbx, rbx
0x180086e06  jz      loc_180086F70
0x180086e0c  lea     rcx, [rbp+punk]
0x180086e10  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180086e15  lea     rdx, [rbp+punk]; struct IUnknown **
0x180086e19  mov     rcx, rbx; this
0x180086e1c  call    ?GetSite@UIItemsView@@QEAAJPEAPEAUIUnknown@@@Z; UIItemsView::GetSite(IUnknown * *)
0x180086e21  cmp     [rbp+punk], r12
0x180086e25  jz      loc_180086F70
0x180086e2b  mov     [rbp+ppvOut], r12
0x180086e2f  lea     rcx, [rbp+ppvOut]
0x180086e33  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x180086e38  lea     r9, [rbp+ppvOut]; ppvOut
0x180086e3c  lea     r8, _GUID_831d1dff_7f57_4720_87e4_cb57d6214428; riid
0x180086e43  lea     rdx, IID_IFolderView; guidService
0x180086e4a  mov     rcx, [rbp+punk]; punk
0x180086e4e  call    cs:__imp_IUnknown_QueryService
0x180086e54  test    eax, eax
0x180086e56  jns     loc_180086FAE
0x180086e5c  mov     [rbp+var_18], r12
0x180086e60  lea     rcx, [rbp+var_18]
0x180086e64  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x180086e69  mov     r8, rax; void **
0x180086e6c  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x180086e73  mov     rcx, [rbp+arg_18]; struct IItem *
0x180086e77  call    ?IItem_QIorBind@@YAJPEAUIItem@@AEBU_GUID@@PEAPEAX@Z; IItem_QIorBind(IItem *,_GUID const &,void * *)
0x180086e7c  mov     [rsp+60h+var_30], 1
0x180086e84  mov     rax, [rbp+punk]
0x180086e88  mov     [rsp+60h+var_38], rax
0x180086e8d  mov     rax, [rbp+var_18]
0x180086e91  mov     qword ptr [rsp+60h+bIgnoreCase], rax
0x180086e96  xor     edx, edx
0x180086e98  mov     ecx, 3045h
0x180086e9d  lea     r9d, [rdx+2]
0x180086ea1  call    ?_Fire_CommandHandlerInvokeTelemetry@@YAXW4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_INVOCATION_LOCATION@@W4RIBBON_VISIBILITY@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIShellItem@@PEAUIUnknown@@K@Z; _Fire_CommandHandlerInvokeTelemetry(EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_INVOCATION_LOCATION,RIBBON_VISIBILITY,EXPLORER_COMMAND_SQM_SELECTED_STATE,IShellItem *,IUnknown *,ulong)
0x180086ea6  mov     rcx, [rbp+ppvOut]
0x180086eaa  test    rcx, rcx
0x180086ead  jnz     loc_180086F59
0x180086eb3  mov     rdx, [rbp+var_18]
0x180086eb7  test    rdx, rdx
0x180086eba  jz      short loc_180086ED3
0x180086ebc  mov     [rbp+var_18], r12
0x180086ec0  mov     rax, [rdx]
0x180086ec3  mov     rcx, rdx
0x180086ec6  mov     rax, [rax+10h]
0x180086eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ecf  mov     rcx, [rbp+ppvOut]
0x180086ed3  test    rcx, rcx
0x180086ed6  jz      short loc_180086EE9
0x180086ed8  mov     [rbp+ppvOut], r12
0x180086edc  mov     rax, [rcx]
0x180086edf  mov     rax, [rax+10h]
0x180086ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ee8  nop
0x180086ee9  mov     rcx, [rbp+punk]
0x180086eed  test    rcx, rcx
0x180086ef0  jz      short loc_180086F03
0x180086ef2  mov     [rbp+punk], r12
0x180086ef6  mov     rax, [rcx]
0x180086ef9  mov     rax, [rax+10h]
0x180086efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f02  nop
0x180086f03  mov     rcx, [rdi+0C0h]
0x180086f0a  mov     rax, [rcx]
0x180086f0d  mov     rax, [rax+0B0h]
0x180086f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f19  lea     rcx, [rbp+var_20]
0x180086f1d  call    ??C?$CComPtrBase@UIUICommandHandler@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUICommandHandler@@@1@XZ; ATL::CComPtrBase<IUICommandHandler>::operator->(void)
0x180086f22  mov     rbx, rax
0x180086f25  mov     rcx, [rax]
0x180086f28  mov     rax, [rcx+0E0h]
0x180086f2f  mov     rcx, rbx
0x180086f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f37  mov     rcx, [rbx]
0x180086f3a  mov     rax, [rcx+68h]
0x180086f3e  mov     r8, rsi
0x180086f41  mov     rdx, [rbp+arg_18]
0x180086f45  mov     rcx, rbx
0x180086f48  mov     r9d, [rdi+100h]
0x180086f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f54  jmp     loc_180086CBB
0x180086f59  mov     rax, [rcx]
0x180086f5c  xor     edx, edx
0x180086f5e  mov     rax, [rax+20h]
0x180086f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f67  mov     rcx, [rbp+ppvOut]
0x180086f6b  jmp     loc_180086EB3
0x180086f70  mov     [rsp+60h+var_30], r12d
0x180086f75  mov     [rsp+60h+var_38], r12
0x180086f7a  mov     qword ptr [rsp+60h+bIgnoreCase], r12
0x180086f7f  mov     edx, 0Dh
0x180086f84  mov     ecx, 3045h
0x180086f89  lea     r9d, [rdx-0Bh]
0x180086f8d  call    ?_Fire_CommandHandlerInvokeTelemetry@@YAXW4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_INVOCATION_LOCATION@@W4RIBBON_VISIBILITY@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIShellItem@@PEAUIUnknown@@K@Z; _Fire_CommandHandlerInvokeTelemetry(EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_INVOCATION_LOCATION,RIBBON_VISIBILITY,EXPLORER_COMMAND_SQM_SELECTED_STATE,IShellItem *,IUnknown *,ulong)
0x180086f92  jmp     loc_180086EE9
0x180086f97  mov     rcx, rdi; this
0x180086f9a  call    ?_EndComposition@CInplaceRename@@AEAAXXZ; CInplaceRename::_EndComposition(void)
0x180086f9f  jmp     loc_180086BE1
0x180086fa4  call    ?ReleaseListener@?$CSafeElementListenerPtr@VElement@DirectUI@@@@QEAAXXZ; CSafeElementListenerPtr<DirectUI::Element>::ReleaseListener(void)
0x180086fa9  jmp     loc_180086BFC
0x180086fae  mov     rcx, [rbp+ppvOut]
0x180086fb2  mov     rax, [rcx]
0x180086fb5  mov     edx, 0Dh
0x180086fba  mov     rax, [rax+20h]
0x180086fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086fc3  jmp     loc_180086E5C
0x180086fc8  mov     rax, [rcx]
0x180086fcb  xor     r8d, r8d
0x180086fce  xor     edx, edx
0x180086fd0  mov     rax, [rax+68h]
0x180086fd4  jmp     loc_180086F48
0x180086fd9  call    ?_FindNameProperty@CInplaceRename@@AEAAPEAVUIProperty@@PEAVElement@DirectUI@@@Z; CInplaceRename::_FindNameProperty(DirectUI::Element *)
0x180086fde  mov     dl, 1
0x180086fe0  mov     rcx, rax
0x180086fe3  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180086fe9  mov     rax, [rdi+68h]
0x180086fed  mov     dword ptr [rax+0F4h], 1
0x180086ff7  mov     rcx, [rdi+68h]
0x180086ffb  call    ??$FindDescendentElement@VUITilesPropertyCollection@@@@YAPEAVUITilesPropertyCollection@@PEAVElement@DirectUI@@@Z; FindDescendentElement<UITilesPropertyCollection>(DirectUI::Element *)
0x180087000  test    rax, rax
0x180087003  jz      short loc_180087010
0x180087005  mov     dl, 1
0x180087007  mov     rcx, rax
0x18008700a  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180087010  mov     rcx, [rdi+68h]; struct DirectUI::Element *
0x180087014  call    ?GetUIItemsView@@YAPEAVUIItemsView@@PEAVElement@DirectUI@@@Z; GetUIItemsView(DirectUI::Element *)
0x180087019  test    rax, rax
0x18008701c  jz      short loc_18008703F
0x18008701e  mov     rcx, [rdi+68h]
0x180087022  mov     rax, [rcx]
0x180087025  mov     rax, [rax+0A8h]
0x18008702c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087031  lea     rcx, [rdi+60h]
0x180087035  call    ?ReleaseListener@?$CSafeElementListenerPtr@VUIRenameTextElement@@@@QEAAXXZ; CSafeElementListenerPtr<UIRenameTextElement>::ReleaseListener(void)
0x18008703a  jmp     loc_180086CD6
0x18008703f  mov     rcx, [rdi+88h]; this
0x180087046  call    ?RestoreListFocus@UIItemsView@@QEAAJXZ; UIItemsView::RestoreListFocus(void)
0x18008704b  jmp     loc_180086CD6
0x180087050  mov     dl, 1
0x180087052  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180087058  lea     rcx, [rdi+28h]
0x18008705c  call    ?ReleaseListener@?$CSafeElementListenerPtr@VUIRenameTextElement@@@@QEAAXXZ; CSafeElementListenerPtr<UIRenameTextElement>::ReleaseListener(void)
0x180087061  jmp     loc_180086CE3
0x180087066  call    cs:__imp_CoTaskMemFree
0x18008706c  mov     [rdi+0E0h], r12
0x180087073  jmp     loc_180086CFA
0x180087078  mov     dword ptr [rdi+0F8h], 1
0x180087082  jmp     loc_180086D12
0x180087087  lea     rcx, [rbp+ppvOut]; void *
0x18008708b  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180087090  nop
0x180087091  lea     rcx, [rdx+288h]
0x180087098  lea     rdx, [rbp+ppvOut]
0x18008709c  call    ?CopyTo@?$CComPtrBase@VIEventQueue@@@ATL@@QEAAJPEAPEAVIEventQueue@@@Z; ATL::CComPtrBase<IEventQueue>::CopyTo(IEventQueue * *)
0x1800870a1  mov     rcx, [rbp+ppvOut]
0x1800870a5  mov     rax, [rcx]
0x1800870a8  xor     edx, edx
0x1800870aa  mov     rax, [rax+50h]
  ... truncated ...
```
