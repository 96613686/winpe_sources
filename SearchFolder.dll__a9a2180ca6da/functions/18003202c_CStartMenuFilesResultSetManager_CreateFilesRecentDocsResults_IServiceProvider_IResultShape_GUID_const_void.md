# CStartMenuFilesResultSetManager::_CreateFilesRecentDocsResults(IServiceProvider *,IResultShape *,_GUID const &,void * *)

- ea: `0x18003202c`
- end: `0x18003225a`
- name: `?_CreateFilesRecentDocsResults@CStartMenuFilesResultSetManager@@AEAAJPEAUIServiceProvider@@PEAUIResultShape@@AEBU_GUID@@PEAPEAX@Z`
- size: `558`
- prototype: `__int64 __fastcall(CStartMenuFilesResultSetManager *__hidden this, struct IServiceProvider *, struct IResultShape *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180033cfc`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x1800129f8`
- `0x180013638`
- `0x1800289c8`
- `0x180029bb0`
- `0x18002cd68`
- `0x18003202c`
- `0x18003a980`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x1800320da`
- `SHELL32!__imp_SHRestricted` at `0x1800320da`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1800320c9`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x1800320c9`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180032156`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180032156`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x18003210f`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x18003210f`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x1800321b7`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x1800321b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CStartMenuFilesResultSetManager::_CreateFilesRecentDocsResults(
        CStartMenuFilesResultSetManager *this,
        struct IServiceProvider *a2,
        struct IResultShape *a3,
        const struct _GUID *a4,
        void **a5)
{
  struct IScope *v8; // rcx
  int SingleVisibleInList; // ebx
  void **v10; // rax
  struct INamedPropertyStore *v11; // rdx
  const struct _GUID *v12; // r8
  __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  struct IAutoListDescription *v16[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v19[20]; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+A4h] [rbp-5Ch]
  int v21; // [rsp+A8h] [rbp-58h]
  int v22; // [rsp+ACh] [rbp-54h]
  int v23; // [rsp+B0h] [rbp-50h]
  _BYTE v24[8]; // [rsp+F8h] [rbp-8h] BYREF
  struct IScope *v25[6]; // [rsp+100h] [rbp+0h] BYREF

  *a5 = 0;
  memset_0(v17, 0, 0xB0u);
  v20 = 0x40000000;
  v21 = 2;
  v22 = 1;
  v23 = 16;
  v8 = (struct IScope *)*((_QWORD *)this + 8);
  v25[2] = v8;
  if ( v8 )
    (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)v8 + 8LL))(v8);
  s_InitFolderTypeFromPropertyStore(*((_QWORD *)this + 9), v19);
  SingleVisibleInList = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v25);
  if ( SingleVisibleInList >= 0 )
  {
    if ( SHRestricted(REST_NOCOMMONGROUPS)
      || (SingleVisibleInList = AddKnownFolderToScope(v25[0], &FOLDERID_Recent, 0), SingleVisibleInList >= 0) )
    {
      SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v24);
      if ( SingleVisibleInList >= 0 )
        SingleVisibleInList = GetStartMenuSearchFolderName(L"files", v25[0], (struct IShellItemArray *)v25[1], &v18);
    }
  }
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v16);
  if ( SingleVisibleInList >= 0 )
    SingleVisibleInList = SHCreateAutoList(v17, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, v16);
  ClearAutoListInit((struct AUTOLISTINIT *)v17);
  if ( SingleVisibleInList >= 0 )
  {
    v15 = 0;
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
    v10 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v14);
    SingleVisibleInList = CreateSearchItemFromAutoList(v16[0], v11, v12, v10);
    if ( SingleVisibleInList >= 0 )
      SingleVisibleInList = CreateResultSetFactory(
                              v14,
                              PKEY_StartMenu_ResultSourceId,
                              &GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b,
                              &v15);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
    if ( SingleVisibleInList >= 0 )
      SingleVisibleInList = (*(__int64 (__fastcall **)(__int64, struct IServiceProvider *, struct IResultShape *, _QWORD, const PROPERTYKEY *, _QWORD, _QWORD, _DWORD, GUID *, void **))(*(_QWORD *)v15 + 32LL))(
                              v15,
                              a2,
                              a3,
                              0,
                              &PKEY_Null,
                              *((_QWORD *)this + 10),
                              0,
                              0,
                              &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                              a5);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v16);
  return (unsigned int)SingleVisibleInList;
}

```

## disassembly

```asm
0x18003202c  mov     [rsp-8+arg_18], rbx
0x180032031  push    rbp
0x180032032  push    rsi
0x180032033  push    rdi
0x180032034  push    r14
0x180032036  push    r15
0x180032038  lea     rbp, [rsp-40h]
0x18003203d  sub     rsp, 140h
0x180032044  mov     rax, cs:__security_cookie
0x18003204b  xor     rax, rsp
0x18003204e  mov     [rbp+60h+var_30], rax
0x180032052  mov     r15, r8
0x180032055  mov     r14, rdx
0x180032058  mov     rdi, rcx
0x18003205b  mov     rsi, [rbp+60h+arg_20]
0x180032062  mov     qword ptr [rsi], 0
0x180032069  xor     edx, edx; Val
0x18003206b  mov     r8d, 0B0h; Size
0x180032071  lea     rcx, [rbp+60h+var_E0]; void *
0x180032075  call    memset_0
0x18003207a  mov     [rbp+60h+var_BC], 40000000h
0x180032081  mov     [rbp+60h+var_B8], 2
0x180032088  mov     [rbp+60h+var_B4], 1
0x18003208f  mov     [rbp+60h+var_B0], 10h
0x180032096  mov     rcx, [rdi+40h]
0x18003209a  mov     [rbp+60h+var_50], rcx
0x18003209e  test    rcx, rcx
0x1800320a1  jz      short loc_1800320AF
0x1800320a3  mov     rax, [rcx]
0x1800320a6  mov     rax, [rax+8]
0x1800320aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320af  lea     rdx, [rbp+60h+var_D0]
0x1800320b3  mov     rcx, [rdi+48h]
0x1800320b7  call    s_InitFolderTypeFromPropertyStore
0x1800320bc  lea     r8, [rbp+60h+var_60]
0x1800320c0  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x1800320c7  xor     ecx, ecx
0x1800320c9  call    cs:__imp_SHCreateScope
0x1800320cf  mov     ebx, eax
0x1800320d1  test    eax, eax
0x1800320d3  js      short loc_180032135
0x1800320d5  mov     ecx, 400000h; rest
0x1800320da  call    cs:__imp_SHRestricted
0x1800320e0  test    eax, eax
0x1800320e2  jnz     short loc_1800320FD
0x1800320e4  xor     r8d, r8d
0x1800320e7  lea     rdx, FOLDERID_Recent
0x1800320ee  mov     rcx, [rbp+60h+var_60]
0x1800320f2  call    ?AddKnownFolderToScope@@YAJPEAUIScope@@AEBU_GUID@@W4SCOPE_ITEM_FLAGS@@@Z; AddKnownFolderToScope(IScope *,_GUID const &,SCOPE_ITEM_FLAGS)
0x1800320f7  mov     ebx, eax
0x1800320f9  test    eax, eax
0x1800320fb  js      short loc_180032135
0x1800320fd  lea     r8, [rbp+60h+var_68]
0x180032101  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180032108  lea     rcx, aItem; "item"
0x18003210f  call    cs:__imp_CreateSingleVisibleInList
0x180032115  mov     ebx, eax
0x180032117  test    eax, eax
0x180032119  js      short loc_180032135
0x18003211b  lea     r9, [rbp+60h+var_D8]; unsigned __int16 **
0x18003211f  mov     r8, [rbp+60h+var_58]; struct IShellItemArray *
0x180032123  mov     rdx, [rbp+60h+var_60]; struct IScope *
0x180032127  lea     rcx, aFiles; "files"
0x18003212e  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x180032133  mov     ebx, eax
0x180032135  lea     rcx, [rsp+160h+var_F0]; void *
0x18003213a  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003213f  nop
0x180032140  test    ebx, ebx
0x180032142  js      short loc_18003215E
0x180032144  lea     r9, [rsp+160h+var_F0]
0x180032149  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180032150  xor     edx, edx
0x180032152  lea     rcx, [rbp+60h+var_E0]
0x180032156  call    cs:__imp_SHCreateAutoList
0x18003215c  mov     ebx, eax
0x18003215e  lea     rcx, [rbp+60h+var_E0]; struct AUTOLISTINIT *
0x180032162  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180032167  test    ebx, ebx
0x180032169  js      loc_18003222B
0x18003216f  mov     [rsp+160h+var_F8], 0
0x180032178  lea     rcx, [rsp+160h+var_100]; void *
0x18003217d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032182  lea     rcx, [rsp+160h+var_100]
0x180032187  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003218c  mov     r9, rax; void **
0x18003218f  mov     rcx, [rsp+160h+var_F0]; struct IAutoListDescription *
0x180032194  call    ?CreateSearchItemFromAutoList@@YAJPEAUIAutoListDescription@@PEAUINamedPropertyStore@@AEBU_GUID@@PEAPEAX@Z; CreateSearchItemFromAutoList(IAutoListDescription *,INamedPropertyStore *,_GUID const &,void * *)
0x180032199  mov     ebx, eax
0x18003219b  test    eax, eax
0x18003219d  js      short loc_1800321BF
0x18003219f  lea     r9, [rsp+160h+var_F8]
0x1800321a4  lea     r8, _GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b
0x1800321ab  lea     rdx, PKEY_StartMenu_ResultSourceId
0x1800321b2  mov     rcx, [rsp+160h+var_100]
0x1800321b7  call    cs:__imp_CreateResultSetFactory
0x1800321bd  mov     ebx, eax
0x1800321bf  lea     rcx, [rsp+160h+var_100]
0x1800321c4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800321c9  test    ebx, ebx
0x1800321cb  js      short loc_180032220
0x1800321cd  mov     rcx, [rsp+160h+var_F8]
0x1800321d2  mov     rax, [rcx]
0x1800321d5  mov     [rsp+160h+var_118], rsi
0x1800321da  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x1800321e1  mov     [rsp+160h+var_120], rdx
0x1800321e6  mov     [rsp+160h+var_128], 0
0x1800321ee  mov     [rsp+160h+var_130], 0
0x1800321f7  mov     r9, [rdi+50h]
0x1800321fb  mov     [rsp+160h+var_138], r9
0x180032200  lea     rdx, PKEY_Null
0x180032207  mov     [rsp+160h+var_140], rdx
0x18003220c  xor     r9d, r9d
0x18003220f  mov     r8, r15
0x180032212  mov     rdx, r14
0x180032215  mov     rax, [rax+20h]
0x180032219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003221e  mov     ebx, eax
0x180032220  lea     rcx, [rsp+160h+var_F8]
0x180032225  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003222a  nop
0x18003222b  lea     rcx, [rsp+160h+var_F0]
0x180032230  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180032235  mov     eax, ebx
0x180032237  mov     rcx, [rbp+60h+var_30]
0x18003223b  xor     rcx, rsp; StackCookie
0x18003223e  call    __security_check_cookie
0x180032243  mov     rbx, [rsp+160h+arg_18]
0x18003224b  add     rsp, 140h
0x180032252  pop     r15
0x180032254  pop     r14
0x180032256  pop     rdi
0x180032257  pop     rsi
0x180032258  pop     rbp
0x180032259  retn
```
