# CStartMenuControlPanelResultSetManager::_CreateControlPanelTasksResults(IServiceProvider *,IResultShape *,ICondition *,INamedPropertyStore *,IShellItem * *,_GUID const &,void * *)

- ea: `0x1800319f8`
- end: `0x180031d81`
- name: `?_CreateControlPanelTasksResults@CStartMenuControlPanelResultSetManager@@AEAAJPEAUIServiceProvider@@PEAUIResultShape@@PEAUICondition@@PEAUINamedPropertyStore@@PEAPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `905`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct IServiceProvider *, struct IUnknown *, IUnknown *, struct INamedPropertyStore *, struct IShellItem **, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800335dc`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x180013638`
- `0x1800284f8`
- `0x180029bb0`
- `0x18002cd68`
- `0x1800313ac`
- `0x1800319f8`
- `0x18003a980`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180031a8f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180031a8f`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180031c33`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180031c33`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x180031aa2`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x180031aa2`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180031b1e`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180031b1e`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180031ad5`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180031ad5`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180031b72`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateResultSetFactory` at `0x180031b72`

## pseudocode

```c
__int64 __fastcall CStartMenuControlPanelResultSetManager::_CreateControlPanelTasksResults(
        const unsigned __int16 **this,
        struct IServiceProvider *a2,
        struct IUnknown *a3,
        IUnknown *a4,
        struct INamedPropertyStore *a5,
        struct IShellItem **a6,
        const struct _GUID *a7,
        void **a8)
{
  CStartMenuControlPanelResultSetManager *v12; // rcx
  HRESULT SingleVisibleInList; // ebx
  const unsigned __int16 *v14; // r8
  struct INamedPropertyStore *v15; // rdx
  const struct _GUID *v16; // r8
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v19; // [rsp+68h] [rbp-98h] BYREF
  void *v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  struct IAutoListDescription *v24[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v26; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[20]; // [rsp+B0h] [rbp-50h] BYREF
  int v28; // [rsp+C4h] [rbp-3Ch]
  int v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+CCh] [rbp-34h]
  int v31; // [rsp+D0h] [rbp-30h]
  _BYTE v32[8]; // [rsp+118h] [rbp+18h] BYREF
  struct IScope *v33[2]; // [rsp+120h] [rbp+20h] BYREF
  IUnknown *ppunk; // [rsp+130h] [rbp+30h] BYREF

  *a6 = 0;
  *a8 = 0;
  memset_0(v25, 0, 0xB0u);
  v28 = 0x40000000;
  v29 = 2;
  v30 = 1;
  v31 = 16;
  s_InitFolderTypeFromPropertyStore(a5, v27);
  IUnknown_Set(&ppunk, a4);
  SingleVisibleInList = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v33);
  if ( SingleVisibleInList >= 0 )
  {
    SingleVisibleInList = CStartMenuControlPanelResultSetManager::_AddShellFolderStringToScope(
                            v12,
                            v33[0],
                            v14,
                            this[12]);
    if ( SingleVisibleInList >= 0 )
    {
      SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v32);
      if ( SingleVisibleInList >= 0 )
        SingleVisibleInList = GetStartMenuSearchFolderName(
                                L"control panel",
                                v33[0],
                                (struct IShellItemArray *)v33[1],
                                &v26);
    }
  }
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(v24);
  if ( SingleVisibleInList >= 0 )
  {
    SingleVisibleInList = SHCreateAutoList(v25, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, v24);
    if ( SingleVisibleInList >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v20);
      SingleVisibleInList = CreateSearchItemFromAutoList(v24[0], v15, v16, &v20);
      if ( SingleVisibleInList < 0 )
      {
LABEL_24:
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v20);
        goto LABEL_25;
      }
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v23);
      SingleVisibleInList = CreateResultSetFactory(
                              v20,
                              PKEY_StartMenu_ResultSourceId,
                              &GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b,
                              &v23);
      if ( SingleVisibleInList < 0 )
      {
LABEL_23:
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v23);
        goto LABEL_24;
      }
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v19);
      if ( a3 )
      {
        if ( ((unsigned int (__fastcall *)(struct IUnknown *))a3->lpVtbl[3].QueryInterface)(a3) )
        {
          ATL::CComPtr<IShellItem>::operator=(&v19, a3);
        }
        else
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v21);
          SingleVisibleInList = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a3->lpVtbl[1].QueryInterface)(
                                  a3,
                                  &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                  &v22);
          if ( SingleVisibleInList >= 0 )
          {
            SingleVisibleInList = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a3->lpVtbl[1].AddRef)(
                                    a3,
                                    &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b,
                                    &v21);
            if ( SingleVisibleInList >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
              SingleVisibleInList = SHCoCreateInstance(
                                      0,
                                      &CLSID_ResultShape,
                                      0,
                                      &GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94,
                                      &ppv);
              if ( SingleVisibleInList >= 0 )
              {
                SingleVisibleInList = (*(__int64 (__fastcall **)(void *, __int64, __int64, _QWORD, const PROPERTYKEY *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                                        ppv,
                                        v22,
                                        v21,
                                        0,
                                        &PKEY_Null,
                                        0,
                                        0);
                if ( SingleVisibleInList >= 0 )
                  SingleVisibleInList = (**(__int64 (__fastcall ***)(void *, GUID *, struct IUnknown **))ppv)(
                                          ppv,
                                          &GUID_6bc63938_8254_4965_9680_565933185060,
                                          &v19);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v21);
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
          if ( SingleVisibleInList < 0 )
            goto LABEL_22;
        }
      }
      SingleVisibleInList = (*(__int64 (__fastcall **)(__int64, struct IServiceProvider *, struct IUnknown *, _QWORD, const PROPERTYKEY *, const unsigned __int16 *, _QWORD, _DWORD, GUID *, void **))(*(_QWORD *)v23 + 32LL))(
                              v23,
                              a2,
                              v19,
                              0,
                              &PKEY_Null,
                              this[10],
                              0,
                              0,
                              &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
                              a8);
      if ( SingleVisibleInList >= 0 )
        *a6 = (struct IShellItem *)ATL::CComPtrBase<IScope>::Detach(&v20);
LABEL_22:
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v19);
      goto LABEL_23;
    }
  }
LABEL_25:
  ClearAutoListInit((struct AUTOLISTINIT *)v25);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)v24);
  return (unsigned int)SingleVisibleInList;
}

```

## disassembly

```asm
0x1800319f8  push    rbp
0x1800319fa  push    rbx
0x1800319fb  push    rsi
0x1800319fc  push    rdi
0x1800319fd  push    r12
0x1800319ff  push    r13
0x180031a01  push    r14
0x180031a03  push    r15
0x180031a05  lea     rbp, [rsp-68h]
0x180031a0a  sub     rsp, 168h
0x180031a11  mov     rax, cs:__security_cookie
0x180031a18  xor     rax, rsp
0x180031a1b  mov     [rbp+0A0h+var_50], rax
0x180031a1f  mov     rdi, r9
0x180031a22  mov     rsi, r8
0x180031a25  mov     r13, rdx
0x180031a28  mov     r14, rcx
0x180031a2b  mov     rbx, [rbp+0A0h+arg_20]
0x180031a32  mov     r15, [rbp+0A0h+arg_28]
0x180031a39  mov     r12, [rbp+0A0h+arg_38]
0x180031a40  mov     qword ptr [r15], 0
0x180031a47  mov     qword ptr [r12], 0
0x180031a4f  xor     edx, edx; Val
0x180031a51  mov     r8d, 0B0h; Size
0x180031a57  lea     rcx, [rbp+0A0h+var_100]; void *
0x180031a5b  call    memset_0
0x180031a60  mov     [rbp+0A0h+var_DC], 40000000h
0x180031a67  mov     [rbp+0A0h+var_D8], 2
0x180031a6e  mov     [rbp+0A0h+var_D4], 1
0x180031a75  mov     [rbp+0A0h+var_D0], 10h
0x180031a7c  lea     rdx, [rbp+0A0h+var_F0]
0x180031a80  mov     rcx, rbx
0x180031a83  call    s_InitFolderTypeFromPropertyStore
0x180031a88  mov     rdx, rdi; punk
0x180031a8b  lea     rcx, [rbp+0A0h+ppunk]; ppunk
0x180031a8f  call    cs:__imp_IUnknown_Set
0x180031a95  lea     r8, [rbp+0A0h+var_80]
0x180031a99  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180031aa0  xor     ecx, ecx
0x180031aa2  call    cs:__imp_SHCreateScope
0x180031aa8  mov     ebx, eax
0x180031aaa  xor     edi, edi
0x180031aac  test    eax, eax
0x180031aae  js      short loc_180031AFB
0x180031ab0  mov     r9, [r14+60h]; unsigned __int16 *
0x180031ab4  mov     rdx, [rbp+0A0h+var_80]; struct IScope *
0x180031ab8  call    ?_AddShellFolderStringToScope@CStartMenuControlPanelResultSetManager@@AEAAJPEAUIScope@@PEBG1@Z; CStartMenuControlPanelResultSetManager::_AddShellFolderStringToScope(IScope *,ushort const *,ushort const *)
0x180031abd  mov     ebx, eax
0x180031abf  test    eax, eax
0x180031ac1  js      short loc_180031AFB
0x180031ac3  lea     r8, [rbp+0A0h+var_88]
0x180031ac7  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180031ace  lea     rcx, aItem; "item"
0x180031ad5  call    cs:__imp_CreateSingleVisibleInList
0x180031adb  mov     ebx, eax
0x180031add  test    eax, eax
0x180031adf  js      short loc_180031AFB
0x180031ae1  lea     r9, [rbp+0A0h+var_F8]; unsigned __int16 **
0x180031ae5  mov     r8, [rbp+0A0h+var_78]; struct IShellItemArray *
0x180031ae9  mov     rdx, [rbp+0A0h+var_80]; struct IScope *
0x180031aed  lea     rcx, pszStr1; "control panel"
0x180031af4  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x180031af9  mov     ebx, eax
0x180031afb  lea     rcx, [rbp+0A0h+var_110]; void *
0x180031aff  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031b04  nop
0x180031b05  test    ebx, ebx
0x180031b07  js      loc_180031D4C
0x180031b0d  lea     r9, [rbp+0A0h+var_110]
0x180031b11  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180031b18  xor     edx, edx
0x180031b1a  lea     rcx, [rbp+0A0h+var_100]
0x180031b1e  call    cs:__imp_SHCreateAutoList
0x180031b24  mov     ebx, eax
0x180031b26  test    eax, eax
0x180031b28  js      loc_180031D4C
0x180031b2e  lea     rcx, [rsp+1A0h+var_130]; void *
0x180031b33  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031b38  nop
0x180031b39  lea     r9, [rsp+1A0h+var_130]; void **
0x180031b3e  mov     rcx, [rbp+0A0h+var_110]; struct IAutoListDescription *
0x180031b42  call    ?CreateSearchItemFromAutoList@@YAJPEAUIAutoListDescription@@PEAUINamedPropertyStore@@AEBU_GUID@@PEAPEAX@Z; CreateSearchItemFromAutoList(IAutoListDescription *,INamedPropertyStore *,_GUID const &,void * *)
0x180031b47  mov     ebx, eax
0x180031b49  test    eax, eax
0x180031b4b  js      loc_180031D42
0x180031b51  lea     rcx, [rbp+0A0h+var_118]; void *
0x180031b55  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031b5a  nop
0x180031b5b  lea     r9, [rbp+0A0h+var_118]
0x180031b5f  lea     r8, _GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b
0x180031b66  lea     rdx, PKEY_StartMenu_ResultSourceId
0x180031b6d  mov     rcx, [rsp+1A0h+var_130]
0x180031b72  call    cs:__imp_CreateResultSetFactory
0x180031b78  mov     ebx, eax
0x180031b7a  test    eax, eax
0x180031b7c  js      loc_180031D38
0x180031b82  lea     rcx, [rsp+1A0h+var_138]; void *
0x180031b87  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031b8c  nop
0x180031b8d  test    rsi, rsi
0x180031b90  jz      loc_180031CD0
0x180031b96  mov     rax, [rsi]
0x180031b99  mov     rcx, rsi
0x180031b9c  mov     rax, [rax+48h]
0x180031ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ba5  test    eax, eax
0x180031ba7  jnz     loc_180031CC3
0x180031bad  lea     rcx, [rbp+0A0h+var_120]; void *
0x180031bb1  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031bb6  nop
0x180031bb7  lea     rcx, [rsp+1A0h+var_128]; void *
0x180031bbc  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031bc1  nop
0x180031bc2  mov     rax, [rsi]
0x180031bc5  lea     r8, [rbp+0A0h+var_120]
0x180031bc9  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180031bd0  mov     rcx, rsi
0x180031bd3  mov     rax, [rax+18h]
0x180031bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bdc  mov     ebx, eax
0x180031bde  test    eax, eax
0x180031be0  js      loc_180031CA2
0x180031be6  mov     rax, [rsi]
0x180031be9  lea     r8, [rsp+1A0h+var_128]
0x180031bee  lea     rdx, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180031bf5  mov     rcx, rsi
0x180031bf8  mov     rax, [rax+20h]
0x180031bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c01  mov     ebx, eax
0x180031c03  test    eax, eax
0x180031c05  js      loc_180031CA2
0x180031c0b  lea     rcx, [rsp+1A0h+var_140]; void *
0x180031c10  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180031c15  nop
0x180031c16  lea     rax, [rsp+1A0h+var_140]
0x180031c1b  mov     [rsp+1A0h+ppv], rax; ppv
0x180031c20  lea     r9, _GUID_42c9f529_ac7b_45d3_a320_c2f23f250b94; riid
0x180031c27  xor     r8d, r8d; pUnkOuter
0x180031c2a  lea     rdx, CLSID_ResultShape; pclsid
0x180031c31  xor     ecx, ecx; pszCLSID
0x180031c33  call    cs:__imp_SHCoCreateInstance
0x180031c39  mov     ebx, eax
0x180031c3b  lea     rsi, PKEY_Null
0x180031c42  test    eax, eax
0x180031c44  js      short loc_180031C96
0x180031c46  mov     rcx, [rsp+1A0h+var_140]
0x180031c4b  mov     rax, [rcx]
0x180031c4e  mov     [rsp+1A0h+var_170], rdi
0x180031c53  mov     [rsp+1A0h+var_178], rdi
0x180031c58  mov     [rsp+1A0h+ppv], rsi
0x180031c5d  xor     r9d, r9d
0x180031c60  mov     r8, [rsp+1A0h+var_128]
0x180031c65  mov     rdx, [rbp+0A0h+var_120]
0x180031c69  mov     rax, [rax+18h]
0x180031c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c72  mov     ebx, eax
0x180031c74  test    eax, eax
0x180031c76  js      short loc_180031C96
0x180031c78  mov     rcx, [rsp+1A0h+var_140]
0x180031c7d  mov     rax, [rcx]
0x180031c80  lea     r8, [rsp+1A0h+var_138]
0x180031c85  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180031c8c  mov     rax, [rax]
0x180031c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c94  mov     ebx, eax
0x180031c96  lea     rcx, [rsp+1A0h+var_140]
0x180031c9b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031ca0  jmp     short loc_180031CA9
0x180031ca2  lea     rsi, PKEY_Null
0x180031ca9  lea     rcx, [rsp+1A0h+var_128]
0x180031cae  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031cb3  nop
0x180031cb4  lea     rcx, [rbp+0A0h+var_120]
0x180031cb8  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031cbd  test    ebx, ebx
0x180031cbf  jns     short loc_180031CD7
0x180031cc1  jmp     short loc_180031D2D
0x180031cc3  mov     rdx, rsi
0x180031cc6  lea     rcx, [rsp+1A0h+var_138]
0x180031ccb  call    ??4?$CComPtr@UIShellItem@@@ATL@@QEAAPEAUIShellItem@@PEAU2@@Z; ATL::CComPtr<IShellItem>::operator=(IShellItem *)
0x180031cd0  lea     rsi, PKEY_Null
0x180031cd7  mov     rcx, [rbp+0A0h+var_118]
0x180031cdb  mov     rax, [rcx]
0x180031cde  mov     [rsp+1A0h+var_158], r12
0x180031ce3  lea     rdx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x180031cea  mov     [rsp+1A0h+var_160], rdx
0x180031cef  mov     [rsp+1A0h+var_168], edi
0x180031cf3  mov     [rsp+1A0h+var_170], rdi
0x180031cf8  mov     r9, [r14+50h]
0x180031cfc  mov     [rsp+1A0h+var_178], r9
0x180031d01  mov     [rsp+1A0h+ppv], rsi
0x180031d06  xor     r9d, r9d
0x180031d09  mov     r8, [rsp+1A0h+var_138]
0x180031d0e  mov     rdx, r13
0x180031d11  mov     rax, [rax+20h]
0x180031d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d1a  mov     ebx, eax
0x180031d1c  test    eax, eax
0x180031d1e  js      short loc_180031D2D
0x180031d20  lea     rcx, [rsp+1A0h+var_130]
0x180031d25  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x180031d2a  mov     [r15], rax
0x180031d2d  lea     rcx, [rsp+1A0h+var_138]
0x180031d32  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031d37  nop
0x180031d38  lea     rcx, [rbp+0A0h+var_118]
0x180031d3c  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031d41  nop
0x180031d42  lea     rcx, [rsp+1A0h+var_130]
0x180031d47  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031d4c  lea     rcx, [rbp+0A0h+var_100]; struct AUTOLISTINIT *
0x180031d50  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180031d55  nop
0x180031d56  lea     rcx, [rbp+0A0h+var_110]
0x180031d5a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180031d5f  mov     eax, ebx
0x180031d61  mov     rcx, [rbp+0A0h+var_50]
0x180031d65  xor     rcx, rsp; StackCookie
0x180031d68  call    __security_check_cookie
0x180031d6d  add     rsp, 168h
0x180031d74  pop     r15
0x180031d76  pop     r14
0x180031d78  pop     r13
0x180031d7a  pop     r12
0x180031d7c  pop     rdi
0x180031d7d  pop     rsi
0x180031d7e  pop     rbx
0x180031d7f  pop     rbp
0x180031d80  retn
```
