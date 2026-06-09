# CStartMenuTopRowset::_CreateGroupQueryItem(ushort const *,_GUID const &,void * *)

- ea: `0x180032260`
- end: `0x180032517`
- name: `?_CreateGroupQueryItem@CStartMenuTopRowset@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `695`
- prototype: `__int64 __fastcall(CStartMenuTopRowset *this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037dec`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x18000e4fc`
- `0x180013638`
- `0x18002cd68`
- `0x18002fa40`
- `0x180032260`
- `0x18003a980`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800323a1`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800323a1`
- `SHELL32!SHParseDisplayName` at `0x180032378`
- `SHELL32!SHParseDisplayName` at `0x180032378`
- `SHELL32!SHCreateItemFromIDList` at `0x1800324ba`
- `SHELL32!SHCreateItemFromIDList` at `0x1800324ba`
- `SHELL32!__imp_ILFree` at `0x1800323ca`
- `SHELL32!__imp_ILFree` at `0x1800323ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032347`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180032347`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800322db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003243c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800322db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003243c`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromShellItemArray` at `0x1800323bd`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromShellItemArray` at `0x1800323bd`

## pseudocode

```c
__int64 __fastcall CStartMenuTopRowset::_CreateGroupQueryItem(
        CStartMenuTopRowset *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT Instance; // ebx
  const struct _GUID *v8; // rdx
  const unsigned __int16 *v9; // rcx
  struct IRichChunk *v11; // [rsp+28h] [rbp-D8h]
  struct IRichChunk *v12; // [rsp+30h] [rbp-D0h]
  struct IRichChunk *v13; // [rsp+38h] [rbp-C8h]
  const struct _GUID *v14; // [rsp+48h] [rbp-B8h]
  LPITEMIDLIST ppidl; // [rsp+60h] [rbp-A0h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+68h] [rbp-98h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h] BYREF
  struct IConditionFactory2 *ppv; // [rsp+78h] [rbp-88h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[8]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v21; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v22[28]; // [rsp+B0h] [rbp-50h] BYREF
  int v23; // [rsp+CCh] [rbp-34h]
  int v24; // [rsp+D0h] [rbp-30h]
  void *v25; // [rsp+118h] [rbp+18h] BYREF
  struct IScope *v26[2]; // [rsp+120h] [rbp+20h] BYREF
  void *v27; // [rsp+130h] [rbp+30h] BYREF

  memset_0(v20, 0, 0xB0u);
  v23 = -1;
  v24 = -1;
  s_InitFolderTypeFromPropertyStore(*((_QWORD *)this + 15), v22);
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
  Instance = CoCreateInstance(
               &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
               0,
               1u,
               &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    *(_QWORD *)&pvar.vt = 31;
    *(_OWORD *)&pvar.decVal.Lo32 = (unsigned __int64)a2;
    Instance = SHCreateLeafConditionEx(&PKEY_StartMenu_Group, COP_EQUAL, &pvar, 0, &psz, v11, v12, v13, ppv, v14, &v27);
    pvar.vt = 0;
    PropVariantClear((PROPVARIANT *)&pvar);
    if ( Instance >= 0 )
    {
      ppidl = 0;
      Instance = SHParseDisplayName(L"shell:::{daf95313-e44d-46af-be1b-cbacea2c3065}", 0, &ppidl, 0, 0);
      if ( Instance >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppsiItemArray);
        Instance = SHCreateShellItemArrayFromIDLists(1u, (LPCITEMIDLIST *)&ppidl, &ppsiItemArray);
        if ( Instance >= 0 )
          Instance = SHCreateScopeFromShellItemArray(ppsiItemArray, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v26);
        ILFree(ppidl);
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppsiItemArray);
        if ( Instance >= 0 )
        {
          Instance = GetStartMenuSearchFolderName(a2, v26[0], (struct IShellItemArray *)v26[1], &v21);
          if ( Instance >= 0 )
          {
            Instance = SHCreateSingleKindList(v9, v8, &v25);
            if ( Instance >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppidl);
              Instance = CoCreateInstance(
                           &GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d,
                           0,
                           1u,
                           &GUID_c0a6c367_c264_4385_a704_9088bdc3640e,
                           (LPVOID *)&ppidl);
              if ( Instance >= 0 )
              {
                ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v17);
                Instance = (*(__int64 (__fastcall **)(LPITEMIDLIST, _BYTE *, GUID *, __int64 *))(*(_QWORD *)&ppidl->mkid.cb
                                                                                               + 24LL))(
                             ppidl,
                             v20,
                             &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                             &v17);
                if ( Instance >= 0 )
                {
                  ppsiItemArray = 0;
                  Instance = (*(__int64 (__fastcall **)(LPITEMIDLIST, __int64, _QWORD, IShellItemArray **))(*(_QWORD *)&ppidl->mkid.cb + 40LL))(
                               ppidl,
                               v17,
                               0,
                               &ppsiItemArray);
                  if ( Instance >= 0 )
                    Instance = SHCreateItemFromIDList(
                                 (LPCITEMIDLIST)ppsiItemArray,
                                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                 a4);
                  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppsiItemArray);
                }
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v17);
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppidl);
            }
          }
        }
      }
    }
  }
  ClearAutoListInit((struct AUTOLISTINIT *)v20);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032260  mov     [rsp-8+arg_10], rbx
0x180032265  push    rbp
0x180032266  push    rsi
0x180032267  push    rdi
0x180032268  lea     rbp, [rsp-60h]
0x18003226d  sub     rsp, 160h
0x180032274  mov     rax, cs:__security_cookie
0x18003227b  xor     rax, rsp
0x18003227e  mov     [rbp+70h+var_20], rax
0x180032282  mov     rsi, r9
0x180032285  mov     rdi, rdx
0x180032288  mov     rbx, rcx
0x18003228b  xor     edx, edx; Val
0x18003228d  mov     r8d, 0B0h; Size
0x180032293  lea     rcx, [rbp+70h+var_D0]; void *
0x180032297  call    memset_0
0x18003229c  or      eax, 0FFFFFFFFh
0x18003229f  mov     [rbp+70h+var_A4], eax
0x1800322a2  mov     [rbp+70h+var_A0], eax
0x1800322a5  lea     rdx, [rbp+70h+var_C0]
0x1800322a9  mov     rcx, [rbx+78h]
0x1800322ad  call    s_InitFolderTypeFromPropertyStore
0x1800322b2  lea     rcx, [rsp+170h+var_F8]; void *
0x1800322b7  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800322bc  nop
0x1800322bd  lea     rax, [rsp+170h+var_F8]
0x1800322c2  mov     [rsp+170h+ppv], rax; ppv
0x1800322c7  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x1800322ce  xor     edx, edx; pUnkOuter
0x1800322d0  lea     r8d, [rdx+1]; dwClsContext
0x1800322d4  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x1800322db  call    cs:__imp_CoCreateInstance
0x1800322e1  mov     ebx, eax
0x1800322e3  test    eax, eax
0x1800322e5  js      loc_1800324E2
0x1800322eb  xorps   xmm0, xmm0
0x1800322ee  xor     eax, eax
0x1800322f0  movups  xmmword ptr [rbp+70h+pvar], xmm0
0x1800322f4  mov     [rbp+70h+var_E0], rax
0x1800322f8  mov     eax, 1Fh
0x1800322fd  mov     word ptr [rbp+70h+pvar], ax
0x180032301  mov     [rbp+70h+pvar+8], rdi
0x180032305  mov     rax, [rsp+170h+var_F8]
0x18003230a  lea     rcx, [rbp+70h+var_40]
0x18003230e  mov     [rsp+170h+var_120], rcx; void **
0x180032313  mov     [rsp+170h+var_130], rax; struct IConditionFactory2 *
0x180032318  lea     rax, psz
0x18003231f  mov     [rsp+170h+ppv], rax; unsigned __int16 *
0x180032324  xor     r9d, r9d; unsigned __int16 *
0x180032327  lea     r8, [rbp+70h+pvar]; struct tagPROPVARIANT *
0x18003232b  lea     edx, [r9+1]; enum tagCONDITION_OPERATION
0x18003232f  lea     rcx, PKEY_StartMenu_Group; struct _tagpropertykey *
0x180032336  call    ?SHCreateLeafConditionEx@@YAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@AEBUtagPROPVARIANT@@PEBG3PEAUIRichChunk@@44PEAUIConditionFactory2@@AEBU_GUID@@PEAPEAX@Z; SHCreateLeafConditionEx(_tagpropertykey const &,tagCONDITION_OPERATION,tagPROPVARIANT const &,ushort const *,ushort const *,IRichChunk *,IRichChunk *,IRichChunk *,IConditionFactory2 *,_GUID const &,void * *)
0x18003233b  mov     ebx, eax
0x18003233d  xor     eax, eax
0x18003233f  mov     word ptr [rbp+70h+pvar], ax
0x180032343  lea     rcx, [rbp+70h+pvar]; pvar
0x180032347  call    cs:__imp_PropVariantClear
0x18003234d  test    ebx, ebx
0x18003234f  js      loc_1800324E2
0x180032355  mov     [rsp+170h+ppidl], 0
0x18003235e  mov     [rsp+170h+ppv], 0; psfgaoOut
0x180032367  xor     r9d, r9d; sfgaoIn
0x18003236a  lea     r8, [rsp+170h+ppidl]; ppidl
0x18003236f  xor     edx, edx; pbc
0x180032371  lea     rcx, pszPath; "shell:::{daf95313-e44d-46af-be1b-cbacea"...
0x180032378  call    cs:__imp_SHParseDisplayName
0x18003237e  mov     ebx, eax
0x180032380  test    eax, eax
0x180032382  js      loc_1800324E2
0x180032388  lea     rcx, [rsp+170h+ppsiItemArray]; void *
0x18003238d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032392  lea     r8, [rsp+170h+ppsiItemArray]; ppsiItemArray
0x180032397  lea     rdx, [rsp+170h+ppidl]; rgpidl
0x18003239c  mov     ecx, 1; cidl
0x1800323a1  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x1800323a7  mov     ebx, eax
0x1800323a9  test    eax, eax
0x1800323ab  js      short loc_1800323C5
0x1800323ad  lea     r8, [rbp+70h+var_50]
0x1800323b1  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x1800323b8  mov     rcx, [rsp+170h+ppsiItemArray]
0x1800323bd  call    cs:__imp_SHCreateScopeFromShellItemArray
0x1800323c3  mov     ebx, eax
0x1800323c5  mov     rcx, [rsp+170h+ppidl]; pidl
0x1800323ca  call    cs:__imp_ILFree
0x1800323d0  lea     rcx, [rsp+170h+ppsiItemArray]
0x1800323d5  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800323da  test    ebx, ebx
0x1800323dc  js      loc_1800324E2
0x1800323e2  lea     r9, [rbp+70h+var_C8]; unsigned __int16 **
0x1800323e6  mov     r8, [rbp+70h+var_48]; struct IShellItemArray *
0x1800323ea  mov     rdx, [rbp+70h+var_50]; struct IScope *
0x1800323ee  mov     rcx, rdi; unsigned __int16 *
0x1800323f1  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x1800323f6  mov     ebx, eax
0x1800323f8  test    eax, eax
0x1800323fa  js      loc_1800324E2
0x180032400  lea     r8, [rbp+70h+var_58]; void **
0x180032404  call    ?SHCreateSingleKindList@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHCreateSingleKindList(ushort const *,_GUID const &,void * *)
0x180032409  mov     ebx, eax
0x18003240b  test    eax, eax
0x18003240d  js      loc_1800324E2
0x180032413  lea     rcx, [rsp+170h+ppidl]; void *
0x180032418  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003241d  nop
0x18003241e  lea     rax, [rsp+170h+ppidl]
0x180032423  mov     [rsp+170h+ppv], rax; ppv
0x180032428  lea     r9, _GUID_c0a6c367_c264_4385_a704_9088bdc3640e; riid
0x18003242f  xor     edx, edx; pUnkOuter
0x180032431  lea     r8d, [rdx+1]; dwClsContext
0x180032435  lea     rcx, _GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d; rclsid
0x18003243c  call    cs:__imp_CoCreateInstance
0x180032442  mov     ebx, eax
0x180032444  test    eax, eax
0x180032446  js      loc_1800324D8
0x18003244c  lea     rcx, [rsp+170h+var_100]; void *
0x180032451  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180032456  nop
0x180032457  mov     rcx, [rsp+170h+ppidl]
0x18003245c  mov     rax, [rcx]
0x18003245f  lea     r9, [rsp+170h+var_100]
0x180032464  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18003246b  lea     rdx, [rbp+70h+var_D0]
0x18003246f  mov     rax, [rax+18h]
0x180032473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032478  mov     ebx, eax
0x18003247a  test    eax, eax
0x18003247c  js      short loc_1800324CD
0x18003247e  mov     [rsp+170h+ppsiItemArray], 0
0x180032487  mov     rcx, [rsp+170h+ppidl]
0x18003248c  mov     rax, [rcx]
0x18003248f  lea     r9, [rsp+170h+ppsiItemArray]
0x180032494  xor     r8d, r8d
0x180032497  mov     rdx, [rsp+170h+var_100]
0x18003249c  mov     rax, [rax+28h]
0x1800324a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a5  mov     ebx, eax
0x1800324a7  test    eax, eax
0x1800324a9  js      short loc_1800324C2
0x1800324ab  mov     r8, rsi; ppv
0x1800324ae  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800324b5  mov     rcx, [rsp+170h+ppsiItemArray]; pidl
0x1800324ba  call    cs:__imp_SHCreateItemFromIDList
0x1800324c0  mov     ebx, eax
0x1800324c2  lea     rcx, [rsp+170h+ppsiItemArray]; void *
0x1800324c7  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800324cc  nop
0x1800324cd  lea     rcx, [rsp+170h+var_100]
0x1800324d2  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800324d7  nop
0x1800324d8  lea     rcx, [rsp+170h+ppidl]
0x1800324dd  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800324e2  lea     rcx, [rbp+70h+var_D0]; struct AUTOLISTINIT *
0x1800324e6  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1800324eb  nop
0x1800324ec  lea     rcx, [rsp+170h+var_F8]
0x1800324f1  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800324f6  mov     eax, ebx
0x1800324f8  mov     rcx, [rbp+70h+var_20]
0x1800324fc  xor     rcx, rsp; StackCookie
0x1800324ff  call    __security_check_cookie
0x180032504  mov     rbx, [rsp+170h+arg_10]
0x18003250c  add     rsp, 160h
0x180032513  pop     rdi
0x180032514  pop     rsi
0x180032515  pop     rbp
0x180032516  retn
```
