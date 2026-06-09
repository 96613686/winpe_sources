# CStartMenuLibraryResultSetManager::s_CreateChildResultSetManager(IServiceProvider *,IRowset *,IProviderConfig *,IResultShape *,ICondition *,INamedPropertyStore *,ushort const *,IScope *,IObjectArray *,IResultSetManager * *)

- ea: `0x180038848`
- end: `0x180038bb8`
- name: `?s_CreateChildResultSetManager@CStartMenuLibraryResultSetManager@@SAJPEAUIServiceProvider@@PEAUIRowset@@PEAUIProviderConfig@@PEAUIResultShape@@PEAUICondition@@PEAUINamedPropertyStore@@PEBGPEAUIScope@@PEAUIObjectArray@@PEAPEAUIResultSetManager@@@Z`
- size: `880`
- prototype: `__int64 __fastcall(struct IServiceProvider *, struct IRowset *, struct IProviderConfig *, struct IResultShape *, struct ICondition *, struct INamedPropertyStore *, const unsigned __int16 *, struct IScope *, struct IObjectArray *, struct IResultSetManager **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180033764`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x180013638`
- `0x180029bb0`
- `0x18002cd68`
- `0x180038848`
- `0x180038bc0`
- `0x18003a980`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180038b00`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180038b00`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180038964`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180038964`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180038920`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180038920`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x1800389d9`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x1800389d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CStartMenuLibraryResultSetManager::s_CreateChildResultSetManager(
        struct IServiceProvider *a1,
        struct IRowset *a2,
        struct IProviderConfig *a3,
        struct IResultShape *a4,
        struct ICondition *a5,
        struct INamedPropertyStore *a6,
        const unsigned __int16 *a7,
        struct IScope *a8,
        struct IObjectArray *a9,
        struct IResultSetManager **a10)
{
  HRESULT SingleVisibleInList; // ebx
  struct INamedPropertyStore *v14; // rdx
  const struct _GUID *v15; // r8
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  void *v21; // [rsp+80h] [rbp-80h] BYREF
  struct IAutoListDescription *v22; // [rsp+88h] [rbp-78h] BYREF
  struct IProviderConfig *v23; // [rsp+90h] [rbp-70h]
  struct IResultSetManager **v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v26; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[20]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+C4h] [rbp-3Ch]
  int v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+CCh] [rbp-34h]
  int v31; // [rsp+D0h] [rbp-30h]
  _BYTE v32[8]; // [rsp+118h] [rbp+18h] BYREF
  struct IScope *v33; // [rsp+120h] [rbp+20h]
  struct IShellItemArray *v34; // [rsp+128h] [rbp+28h]
  struct ICondition *v35; // [rsp+130h] [rbp+30h]

  v23 = a3;
  v24 = a10;
  memset_0(v25, 0, 0xB0u);
  v28 = 0x40000000;
  v29 = 2;
  v30 = 1;
  v31 = 16;
  v35 = a5;
  if ( a5 )
    ((void (__fastcall *)(struct ICondition *))a5->lpVtbl->AddRef)(a5);
  s_InitFolderTypeFromPropertyStore(a6, v27);
  v33 = a8;
  if ( a8 )
    (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)a8 + 8LL))(a8);
  SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v32);
  if ( SingleVisibleInList >= 0 )
    SingleVisibleInList = GetStartMenuSearchFolderName(0, v33, v34, &v26);
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
  if ( SingleVisibleInList >= 0 )
  {
    SingleVisibleInList = SHCreateAutoList(v25, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v22);
    if ( SingleVisibleInList >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v21);
      SingleVisibleInList = CreateSearchItemFromAutoList(v22, v14, v15, &v21);
      if ( SingleVisibleInList >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v18);
        SingleVisibleInList = s_CreateChildShape(a4, &v18);
        if ( SingleVisibleInList >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v20);
          SingleVisibleInList = CreateResultSetFactory(
                                  v21,
                                  PKEY_StartMenu_ResultSourceId,
                                  &GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b,
                                  &v20);
          if ( SingleVisibleInList >= 0 )
          {
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v19);
            if ( a2 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
              SingleVisibleInList = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v20)(
                                      v20,
                                      &GUID_aa64c263_b6df_4050_b3b9_38e1b89e2998,
                                      &ppv);
              if ( SingleVisibleInList >= 0 )
                SingleVisibleInList = (*(__int64 (__fastcall **)(void *, struct IRowset *, struct IProviderConfig *, struct IServiceProvider *, __int64, _QWORD, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 32LL))(
                                        ppv,
                                        a2,
                                        v23,
                                        a1,
                                        v18,
                                        0,
                                        0,
                                        0,
                                        &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                        &v19);
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
            }
            else
            {
              SingleVisibleInList = (*(__int64 (__fastcall **)(__int64, struct IServiceProvider *, __int64, _QWORD, const PROPERTYKEY *, struct IObjectArray *, _QWORD, _DWORD, GUID *, __int64 *))(*(_QWORD *)v20 + 32LL))(
                                      v20,
                                      a1,
                                      v18,
                                      0,
                                      &PKEY_Null,
                                      a9,
                                      0,
                                      0,
                                      &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                                      &v19);
            }
            if ( SingleVisibleInList >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
              SingleVisibleInList = SHCoCreateInstance(
                                      0,
                                      &CLSID_ResultSetManager,
                                      0,
                                      &GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8,
                                      &ppv);
              if ( SingleVisibleInList >= 0 )
              {
                SingleVisibleInList = (*(__int64 (__fastcall **)(void *, __int64, __int64, void *))(*(_QWORD *)ppv + 24LL))(
                                        ppv,
                                        v19,
                                        v18,
                                        v21);
                if ( SingleVisibleInList >= 0 )
                  SingleVisibleInList = (**(__int64 (__fastcall ***)(void *, GUID *, struct IResultSetManager **))ppv)(
                                          ppv,
                                          &GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330,
                                          v24);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
            }
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v19);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v20);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v18);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v21);
    }
  }
  ClearAutoListInit((struct AUTOLISTINIT *)v25);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
  return (unsigned int)SingleVisibleInList;
}

```

## disassembly

```asm
0x180038848  push    rbp
0x18003884a  push    rbx
0x18003884b  push    rsi
0x18003884c  push    rdi
0x18003884d  push    r12
0x18003884f  push    r13
0x180038851  push    r14
0x180038853  push    r15
0x180038855  lea     rbp, [rsp-68h]
0x18003885a  sub     rsp, 168h
0x180038861  mov     rax, cs:__security_cookie
0x180038868  xor     rax, rsp
0x18003886b  mov     [rbp+0A0h+var_50], rax
0x18003886f  mov     r15, r9
0x180038872  mov     [rbp+0A0h+var_110], r8
0x180038876  mov     r14, rdx
0x180038879  mov     r12, rcx
0x18003887c  mov     rdi, [rbp+0A0h+arg_20]
0x180038883  mov     rsi, [rbp+0A0h+arg_28]
0x18003888a  mov     rbx, [rbp+0A0h+arg_38]
0x180038891  mov     r13, [rbp+0A0h+arg_40]
0x180038898  mov     rax, [rbp+0A0h+arg_48]
0x18003889f  mov     [rbp+0A0h+var_108], rax
0x1800388a3  xor     edx, edx; Val
0x1800388a5  mov     r8d, 0B0h; Size
0x1800388ab  lea     rcx, [rbp+0A0h+var_100]; void *
0x1800388af  call    memset_0
0x1800388b4  mov     [rbp+0A0h+var_DC], 40000000h
0x1800388bb  mov     [rbp+0A0h+var_D8], 2
0x1800388c2  mov     [rbp+0A0h+var_D4], 1
0x1800388c9  mov     [rbp+0A0h+var_D0], 10h
0x1800388d0  mov     [rbp+0A0h+var_70], rdi
0x1800388d4  test    rdi, rdi
0x1800388d7  jz      short loc_1800388E8
0x1800388d9  mov     rax, [rdi]
0x1800388dc  mov     rcx, rdi
0x1800388df  mov     rax, [rax+8]
0x1800388e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388e8  lea     rdx, [rbp+0A0h+var_F0]
0x1800388ec  mov     rcx, rsi
0x1800388ef  call    s_InitFolderTypeFromPropertyStore
0x1800388f4  mov     [rbp+0A0h+var_80], rbx
0x1800388f8  xor     edi, edi
0x1800388fa  test    rbx, rbx
0x1800388fd  jz      short loc_18003890E
0x1800388ff  mov     rax, [rbx]
0x180038902  mov     rcx, rbx
0x180038905  mov     rax, [rax+8]
0x180038909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003890e  lea     r8, [rbp+0A0h+var_88]
0x180038912  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180038919  lea     rcx, aItem; "item"
0x180038920  call    cs:__imp_CreateSingleVisibleInList
0x180038926  mov     ebx, eax
0x180038928  test    eax, eax
0x18003892a  js      short loc_180038941
0x18003892c  lea     r9, [rbp+0A0h+var_F8]; unsigned __int16 **
0x180038930  mov     r8, [rbp+0A0h+var_78]; struct IShellItemArray *
0x180038934  mov     rdx, [rbp+0A0h+var_80]; struct IScope *
0x180038938  xor     ecx, ecx; unsigned __int16 *
0x18003893a  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x18003893f  mov     ebx, eax
0x180038941  lea     rcx, [rbp+0A0h+var_118]; void *
0x180038945  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003894a  nop
0x18003894b  test    ebx, ebx
0x18003894d  js      loc_180038B83
0x180038953  lea     r9, [rbp+0A0h+var_118]
0x180038957  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18003895e  xor     edx, edx
0x180038960  lea     rcx, [rbp+0A0h+var_100]
0x180038964  call    cs:__imp_SHCreateAutoList
0x18003896a  mov     ebx, eax
0x18003896c  test    eax, eax
0x18003896e  js      loc_180038B83
0x180038974  lea     rcx, [rbp+0A0h+var_120]; void *
0x180038978  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003897d  nop
0x18003897e  lea     r9, [rbp+0A0h+var_120]; void **
0x180038982  mov     rcx, [rbp+0A0h+var_118]; struct IAutoListDescription *
0x180038986  call    ?CreateSearchItemFromAutoList@@YAJPEAUIAutoListDescription@@PEAUINamedPropertyStore@@AEBU_GUID@@PEAPEAX@Z; CreateSearchItemFromAutoList(IAutoListDescription *,INamedPropertyStore *,_GUID const &,void * *)
0x18003898b  mov     ebx, eax
0x18003898d  test    eax, eax
0x18003898f  js      loc_180038B7A
0x180038995  lea     rcx, [rsp+1A0h+var_138]; void *
0x18003899a  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003899f  nop
0x1800389a0  lea     rdx, [rsp+1A0h+var_138]
0x1800389a5  mov     rcx, r15
0x1800389a8  call    s_CreateChildShape
0x1800389ad  mov     ebx, eax
0x1800389af  test    eax, eax
0x1800389b1  js      loc_180038B6F
0x1800389b7  lea     rcx, [rsp+1A0h+var_128]; void *
0x1800389bc  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800389c1  nop
0x1800389c2  lea     r9, [rsp+1A0h+var_128]
0x1800389c7  lea     r8, _GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b
0x1800389ce  lea     rdx, PKEY_StartMenu_ResultSourceId
0x1800389d5  mov     rcx, [rbp+0A0h+var_120]
0x1800389d9  call    cs:__imp_CreateResultSetFactory
0x1800389df  mov     ebx, eax
0x1800389e1  test    eax, eax
0x1800389e3  js      loc_180038B64
0x1800389e9  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800389ee  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800389f3  nop
0x1800389f4  test    r14, r14
0x1800389f7  jz      loc_180038A82
0x1800389fd  lea     rcx, [rsp+1A0h+var_140]; void *
0x180038a02  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038a07  nop
0x180038a08  mov     rcx, [rsp+1A0h+var_128]
0x180038a0d  mov     rax, [rcx]
0x180038a10  lea     r8, [rsp+1A0h+var_140]
0x180038a15  lea     rdx, _GUID_aa64c263_b6df_4050_b3b9_38e1b89e2998
0x180038a1c  mov     rax, [rax]
0x180038a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a24  mov     ebx, eax
0x180038a26  test    eax, eax
0x180038a28  js      short loc_180038A76
0x180038a2a  mov     rcx, [rsp+1A0h+var_140]
0x180038a2f  mov     r10, [rsp+1A0h+var_138]
0x180038a34  mov     rax, [rcx]
0x180038a37  lea     rdx, [rsp+1A0h+var_130]
0x180038a3c  mov     [rsp+1A0h+var_158], rdx
0x180038a41  lea     r11, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x180038a48  mov     [rsp+1A0h+var_160], r11
0x180038a4d  mov     [rsp+1A0h+var_168], rdi
0x180038a52  mov     [rsp+1A0h+var_170], rdi
0x180038a57  mov     [rsp+1A0h+var_178], rdi
0x180038a5c  mov     [rsp+1A0h+ppv], r10
0x180038a61  mov     r9, r12
0x180038a64  mov     r8, [rbp+0A0h+var_110]
0x180038a68  mov     rdx, r14
0x180038a6b  mov     rax, [rax+20h]
0x180038a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a74  mov     ebx, eax
0x180038a76  lea     rcx, [rsp+1A0h+var_140]
0x180038a7b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038a80  jmp     short loc_180038AD0
0x180038a82  mov     rcx, [rsp+1A0h+var_128]
0x180038a87  mov     rax, [rcx]
0x180038a8a  lea     rdx, [rsp+1A0h+var_130]
0x180038a8f  mov     [rsp+1A0h+var_158], rdx
0x180038a94  lea     r11, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x180038a9b  mov     [rsp+1A0h+var_160], r11
0x180038aa0  mov     dword ptr [rsp+1A0h+var_168], edi
0x180038aa4  mov     [rsp+1A0h+var_170], rdi
0x180038aa9  mov     [rsp+1A0h+var_178], r13
0x180038aae  lea     rdx, PKEY_Null
0x180038ab5  mov     [rsp+1A0h+ppv], rdx
0x180038aba  xor     r9d, r9d
0x180038abd  mov     r8, [rsp+1A0h+var_138]
0x180038ac2  mov     rdx, r12
0x180038ac5  mov     rax, [rax+20h]
0x180038ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ace  mov     ebx, eax
0x180038ad0  test    ebx, ebx
0x180038ad2  js      loc_180038B59
0x180038ad8  lea     rcx, [rsp+1A0h+var_140]; void *
0x180038add  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180038ae2  nop
0x180038ae3  lea     rax, [rsp+1A0h+var_140]
0x180038ae8  mov     [rsp+1A0h+ppv], rax; ppv
0x180038aed  lea     r9, _GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8; riid
0x180038af4  xor     r8d, r8d; pUnkOuter
0x180038af7  lea     rdx, CLSID_ResultSetManager; pclsid
0x180038afe  xor     ecx, ecx; pszCLSID
0x180038b00  call    cs:__imp_SHCoCreateInstance
0x180038b06  mov     ebx, eax
0x180038b08  test    eax, eax
0x180038b0a  js      short loc_180038B4E
0x180038b0c  mov     rcx, [rsp+1A0h+var_140]
0x180038b11  mov     rax, [rcx]
0x180038b14  mov     r9, [rbp+0A0h+var_120]
0x180038b18  mov     r8, [rsp+1A0h+var_138]
0x180038b1d  mov     rdx, [rsp+1A0h+var_130]
0x180038b22  mov     rax, [rax+18h]
0x180038b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b2b  mov     ebx, eax
0x180038b2d  test    eax, eax
0x180038b2f  js      short loc_180038B4E
0x180038b31  mov     rcx, [rsp+1A0h+var_140]
0x180038b36  mov     rax, [rcx]
0x180038b39  mov     r8, [rbp+0A0h+var_108]
0x180038b3d  lea     rdx, _GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330
0x180038b44  mov     rax, [rax]
0x180038b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b4c  mov     ebx, eax
0x180038b4e  lea     rcx, [rsp+1A0h+var_140]
0x180038b53  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b58  nop
0x180038b59  lea     rcx, [rsp+1A0h+var_130]
0x180038b5e  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b63  nop
0x180038b64  lea     rcx, [rsp+1A0h+var_128]
0x180038b69  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b6e  nop
0x180038b6f  lea     rcx, [rsp+1A0h+var_138]
0x180038b74  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b79  nop
0x180038b7a  lea     rcx, [rbp+0A0h+var_120]
0x180038b7e  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b83  lea     rcx, [rbp+0A0h+var_100]; struct AUTOLISTINIT *
0x180038b87  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180038b8c  nop
0x180038b8d  lea     rcx, [rbp+0A0h+var_118]
0x180038b91  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180038b96  mov     eax, ebx
0x180038b98  mov     rcx, [rbp+0A0h+var_50]
0x180038b9c  xor     rcx, rsp; StackCookie
0x180038b9f  call    __security_check_cookie
0x180038ba4  add     rsp, 168h
0x180038bab  pop     r15
0x180038bad  pop     r14
0x180038baf  pop     r13
0x180038bb1  pop     r12
0x180038bb3  pop     rdi
0x180038bb4  pop     rsi
0x180038bb5  pop     rbx
0x180038bb6  pop     rbp
0x180038bb7  retn
```
