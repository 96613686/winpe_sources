# CreateSearchWithNewFlags(IShellFolder3 *,AUTOLISTFLAGS,_GUID const &,void * *)

- ea: `0x180013e0c`
- end: `0x18001408f`
- name: `?CreateSearchWithNewFlags@@YAJPEAUIShellFolder3@@W4AUTOLISTFLAGS@@AEBU_GUID@@PEAPEAX@Z`
- size: `643`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800200ec`

## callees

- `0x180004a50`
- `0x180005460`
- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x180013638`
- `0x1800136e8`
- `0x180013e0c`
- `0x18001479c`
- `0x180019218`
- `0x18001ab60`
- `0x18003d86c`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x180013fc8`
- `SHELL32!SHGetIDListFromObject` at `0x180013fc8`
- `SHELL32!SHCreateItemFromIDList` at `0x180014006`
- `SHELL32!SHCreateItemFromIDList` at `0x180014006`
- `SHELL32!__imp_ILFree` at `0x180014013`
- `SHELL32!__imp_ILFree` at `0x180014013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014053`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180013f3b`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x180013f3b`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x180013fab`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x180013fab`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180013f62`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180013f62`

## string_xrefs

- `0x180013f78`: `SecondaryCompare`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CreateSearchWithNewFlags(struct IUnknown *a1, __int64 a2, __int64 a3, void **a4)
{
  HRESULT Object; // ebx
  unsigned int v7; // edx
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct IAutoListDescription *v10; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+80h] [rbp-80h]
  LPVOID pv; // [rsp+B8h] [rbp-48h]
  LPVOID v19; // [rsp+C8h] [rbp-38h]
  struct IScope *v20; // [rsp+E0h] [rbp-20h]
  struct IShellItemArray *v21; // [rsp+E8h] [rbp-18h]

  *a4 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v10);
  Object = IUnknown_QueryObject(
             a1,
             &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
             &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
             (void **)&v10);
  if ( Object >= 0 )
  {
    memset_0(v15, 0, 0xB0u);
    Object = GetAUTOLISTINITFromAutoListDescription(v10, 3, v15);
    if ( Object >= 0 )
    {
      v17 |= 8u;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
      Object = MakeAutoListScopeRecursive(v10, (struct IScope **)&ppv);
      if ( Object >= 0 && ppv )
      {
        (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)v20 + 16LL))(v20);
        v20 = (struct IScope *)ATL::CComPtrBase<IScope>::Detach(&ppv);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
      if ( Object >= 0 )
      {
        if ( !v16 )
          GetSearchFolderName(g_hinst, v7, v20, v21, &v16);
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
        Object = SHCreateAutoList(v15, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v14);
        if ( Object >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
          Object = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
          if ( Object >= 0 )
          {
            Object = INamedPropertyStore_SetUInt32(ppv, L"SecondaryCompare", 8);
            if ( Object >= 0 )
            {
              v13 = 0;
              Object = SHCreateSearchIDListFromAutoList(v14, ppv, &v13);
              if ( Object >= 0 )
              {
                ppidl = 0;
                Object = SHGetIDListFromObject(a1, &ppidl);
                if ( Object >= 0 )
                {
                  pidl = 0;
                  Object = CloneChildFilters(
                             (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
                             v13,
                             (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
                  if ( Object >= 0 )
                  {
                    Object = SHCreateItemFromIDList(pidl, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, a4);
                    ILFree((LPITEMIDLIST)pidl);
                  }
                }
                CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&ppidl);
              }
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v13);
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
      }
      CoTaskMemFree(pv);
      CoTaskMemFree(v19);
      ClearAutoListInit((struct AUTOLISTINIT *)v15);
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v10);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180013e0c  mov     [rsp-8+arg_8], rbx
0x180013e11  push    rbp
0x180013e12  push    rsi
0x180013e13  push    rdi
0x180013e14  lea     rbp, [rsp-20h]
0x180013e19  sub     rsp, 120h
0x180013e20  mov     rax, cs:__security_cookie
0x180013e27  xor     rax, rsp
0x180013e2a  mov     [rbp+30h+var_20], rax
0x180013e2e  mov     rsi, r9
0x180013e31  mov     rdi, rcx
0x180013e34  mov     qword ptr [r9], 0
0x180013e3b  lea     rcx, [rsp+130h+var_F8]; void *
0x180013e40  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180013e45  nop
0x180013e46  lea     r9, [rsp+130h+var_F8]; void **
0x180013e4b  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x180013e52  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x180013e59  mov     rcx, rdi; struct IUnknown *
0x180013e5c  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x180013e61  mov     ebx, eax
0x180013e63  test    eax, eax
0x180013e65  js      loc_180014064
0x180013e6b  xor     edx, edx; Val
0x180013e6d  mov     r8d, 0B0h; Size
0x180013e73  lea     rcx, [rsp+130h+var_D0]; void *
0x180013e78  call    memset_0
0x180013e7d  lea     r8, [rsp+130h+var_D0]
0x180013e82  mov     edx, 3
0x180013e87  mov     rcx, [rsp+130h+var_F8]
0x180013e8c  call    ?GetAUTOLISTINITFromAutoListDescription@@YAJPEAUIAutoListDescription@@W4AUTOLISTINIT_FLAGS@@PEAUAUTOLISTINIT@@@Z; GetAUTOLISTINITFromAutoListDescription(IAutoListDescription *,AUTOLISTINIT_FLAGS,AUTOLISTINIT *)
0x180013e91  mov     ebx, eax
0x180013e93  test    eax, eax
0x180013e95  js      loc_180014064
0x180013e9b  or      [rbp+30h+var_B0], 8
0x180013e9f  lea     rcx, [rsp+130h+ppv]; void *
0x180013ea4  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180013ea9  nop
0x180013eaa  lea     rdx, [rsp+130h+ppv]; struct IScope **
0x180013eaf  mov     rcx, [rsp+130h+var_F8]; struct IAutoListDescription *
0x180013eb4  call    ?MakeAutoListScopeRecursive@@YAJPEAUIAutoListDescription@@PEAPEAUIScope@@@Z; MakeAutoListScopeRecursive(IAutoListDescription *,IScope * *)
0x180013eb9  mov     ebx, eax
0x180013ebb  test    eax, eax
0x180013ebd  js      short loc_180013EE5
0x180013ebf  cmp     [rsp+130h+ppv], 0
0x180013ec5  jz      short loc_180013EE5
0x180013ec7  mov     rcx, [rbp+30h+var_50]
0x180013ecb  mov     rax, [rcx]
0x180013ece  mov     rax, [rax+10h]
0x180013ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ed7  lea     rcx, [rsp+130h+ppv]
0x180013edc  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x180013ee1  mov     [rbp+30h+var_50], rax
0x180013ee5  lea     rcx, [rsp+130h+ppv]
0x180013eea  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180013eef  test    ebx, ebx
0x180013ef1  js      loc_180014045
0x180013ef7  cmp     [rsp+130h+var_C8], 0
0x180013efd  jnz     short loc_180013F1D
0x180013eff  lea     rax, [rsp+130h+var_C8]
0x180013f04  mov     [rsp+130h+var_110], rax; unsigned __int16 **
0x180013f09  mov     r9, [rbp+30h+var_48]; struct IShellItemArray *
0x180013f0d  mov     r8, [rbp+30h+var_50]; struct IScope *
0x180013f11  mov     rcx, cs:g_hinst; hInstance
0x180013f18  call    ?GetSearchFolderName@@YAJPEAUHINSTANCE__@@IPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetSearchFolderName(HINSTANCE__ *,uint,IScope *,IShellItemArray *,ushort * *)
0x180013f1d  lea     rcx, [rsp+130h+var_D8]; void *
0x180013f22  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180013f27  nop
0x180013f28  lea     r9, [rsp+130h+var_D8]
0x180013f2d  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x180013f34  xor     edx, edx
0x180013f36  lea     rcx, [rsp+130h+var_D0]
0x180013f3b  call    cs:__imp_SHCreateAutoList
0x180013f41  mov     ebx, eax
0x180013f43  test    eax, eax
0x180013f45  js      loc_18001403B
0x180013f4b  lea     rcx, [rsp+130h+ppv]; void *
0x180013f50  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180013f55  nop
0x180013f56  lea     rdx, [rsp+130h+ppv]; ppv
0x180013f5b  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180013f62  call    cs:__imp_PSCreateMemoryPropertyStore
0x180013f68  mov     ebx, eax
0x180013f6a  test    eax, eax
0x180013f6c  js      loc_180014030
0x180013f72  mov     r8d, 8
0x180013f78  lea     rdx, aSecondarycompa; "SecondaryCompare"
0x180013f7f  mov     rcx, [rsp+130h+ppv]
0x180013f84  call    INamedPropertyStore_SetUInt32
0x180013f89  mov     ebx, eax
0x180013f8b  test    eax, eax
0x180013f8d  js      loc_180014030
0x180013f93  mov     [rsp+130h+var_E0], 0
0x180013f9c  lea     r8, [rsp+130h+var_E0]
0x180013fa1  mov     rdx, [rsp+130h+ppv]
0x180013fa6  mov     rcx, [rsp+130h+var_D8]
0x180013fab  call    cs:__imp_SHCreateSearchIDListFromAutoList
0x180013fb1  mov     ebx, eax
0x180013fb3  test    eax, eax
0x180013fb5  js      short loc_180014025
0x180013fb7  mov     [rsp+130h+ppidl], 0
0x180013fc0  lea     rdx, [rsp+130h+ppidl]; ppidl
0x180013fc5  mov     rcx, rdi; punk
0x180013fc8  call    cs:__imp_SHGetIDListFromObject
0x180013fce  mov     ebx, eax
0x180013fd0  test    eax, eax
0x180013fd2  js      short loc_18001401A
0x180013fd4  mov     [rsp+130h+pidl], 0
0x180013fdd  lea     r8, [rsp+130h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180013fe2  mov     rdx, [rsp+130h+var_E0]; struct _ITEMIDLIST_ABSOLUTE *
0x180013fe7  mov     rcx, [rsp+130h+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180013fec  call    ?CloneChildFilters@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@0PEAPEAU1@@Z; CloneChildFilters(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x180013ff1  mov     ebx, eax
0x180013ff3  test    eax, eax
0x180013ff5  js      short loc_18001401A
0x180013ff7  mov     r8, rsi; ppv
0x180013ffa  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236; riid
0x180014001  mov     rcx, [rsp+130h+pidl]; pidl
0x180014006  call    cs:__imp_SHCreateItemFromIDList
0x18001400c  mov     ebx, eax
0x18001400e  mov     rcx, [rsp+130h+pidl]; pidl
0x180014013  call    cs:__imp_ILFree
0x180014019  nop
0x18001401a  lea     rcx, [rsp+130h+ppidl]; void *
0x18001401f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180014024  nop
0x180014025  lea     rcx, [rsp+130h+var_E0]; void *
0x18001402a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001402f  nop
0x180014030  lea     rcx, [rsp+130h+ppv]
0x180014035  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001403a  nop
0x18001403b  lea     rcx, [rsp+130h+var_D8]
0x180014040  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180014045  mov     rcx, [rbp+30h+pv]; pv
0x180014049  call    cs:__imp_CoTaskMemFree
0x18001404f  mov     rcx, [rbp+30h+var_68]; pv
0x180014053  call    cs:__imp_CoTaskMemFree
0x180014059  lea     rcx, [rsp+130h+var_D0]; struct AUTOLISTINIT *
0x18001405e  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x180014063  nop
0x180014064  lea     rcx, [rsp+130h+var_F8]
0x180014069  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18001406e  mov     eax, ebx
0x180014070  mov     rcx, [rbp+30h+var_20]
0x180014074  xor     rcx, rsp; StackCookie
0x180014077  call    __security_check_cookie
0x18001407c  mov     rbx, [rsp+130h+arg_8]
0x180014084  add     rsp, 120h
0x18001408b  pop     rdi
0x18001408c  pop     rsi
0x18001408d  pop     rbp
0x18001408e  retn
```
