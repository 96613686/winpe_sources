# CreateSearchWithNewFlags(IShellFolder3 *,AUTOLISTFLAGS,_GUID const &,void * *)

- ea: `0x1800bbcf4`
- end: `0x1800bbf88`
- name: `?CreateSearchWithNewFlags@@YAJPEAUIShellFolder3@@W4AUTOLISTFLAGS@@AEBU_GUID@@PEAPEAX@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bbf90`

## callees

- `0x180005bf0`
- `0x18000ccdc`
- `0x18000e1c0`
- `0x18000e450`
- `0x180015588`
- `0x180021b70`
- `0x180035860`
- `0x18004983c`
- `0x180071dc0`
- `0x180072cf4`
- `0x1800bb7fc`
- `0x1800bbcf4`
- `0x1800bc794`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800bbf10`
- `Windows.Storage!ILFree` at `0x1800bbf10`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800bbec9`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800bbec9`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800bbf03`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800bbf03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbf46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbf50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbf46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbf50`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800bbe41`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800bbe41`

## string_xrefs

- `0x1800bbe7b`: `SecondaryCompare`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CreateSearchWithNewFlags(struct IUnknown *a1, int a2, const IID *a3, void **a4)
{
  HRESULT Object; // ebx
  unsigned int v9; // edx
  HINSTANCE v10; // rcx
  struct IScope *v11; // rax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct IAutoListDescription *v14; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v17; // [rsp+50h] [rbp-B0h] BYREF
  struct IAutoListDescription *v18; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h]
  _BYTE v21[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v22; // [rsp+88h] [rbp-78h] BYREF
  int v23; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+D8h] [rbp-28h]
  LPVOID v25; // [rsp+E8h] [rbp-18h]
  struct IScope *v26; // [rsp+100h] [rbp+0h]
  struct IShellItemArray *v27; // [rsp+108h] [rbp+8h]

  *a4 = 0;
  v14 = 0;
  Object = IUnknown_QueryObject(
             a1,
             &GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82,
             &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
             (void **)&v14);
  if ( Object >= 0 )
  {
    memset_0(v21, 0, 0xB0u);
    Object = GetAUTOLISTINITFromAutoListDescription(v14, 3, v21);
    if ( Object >= 0 )
    {
      v23 |= a2;
      if ( (a2 & 8) == 0 )
        goto LABEL_8;
      ppv = 0;
      Object = MakeAutoListScopeRecursive(v14, (struct IScope **)&ppv);
      if ( Object >= 0 && ppv )
      {
        (*(void (__fastcall **)(struct IScope *))(*(_QWORD *)v26 + 16LL))(v26);
        v11 = (struct IScope *)ppv;
        ppv = 0;
        v26 = v11;
      }
      ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&ppv);
      if ( Object >= 0 )
      {
LABEL_8:
        if ( !v22 )
          GetSearchFolderName(v10, v9, v26, v27, &v22);
        v18 = 0;
        Object = CAutoList::s_CreateInstance(
                   (const struct AUTOLISTINIT *)v21,
                   0,
                   &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                   (void **)&v18);
        if ( Object >= 0 )
        {
          ppv = 0;
          Object = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
          if ( Object >= 0 )
          {
            v19 = 0;
            v20 = 0;
            LOWORD(v19) = 19;
            DWORD2(v19) = a2;
            Object = (*(__int64 (__fastcall **)(void *, const WCHAR *, __int128 *))(*(_QWORD *)ppv + 32LL))(
                       ppv,
                       L"SecondaryCompare",
                       &v19);
            if ( Object >= 0 )
            {
              v17 = 0;
              Object = SHCreateSearchIDListFromAutoList(v18);
              if ( Object >= 0 )
              {
                ppidl = 0;
                Object = SHGetIDListFromObject(a1, &ppidl);
                if ( Object >= 0 )
                {
                  pidl = 0;
                  Object = CloneChildFilters(
                             (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
                             v17,
                             (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
                  if ( Object >= 0 )
                  {
                    Object = SHCreateItemFromIDList(pidl, a3, a4);
                    ILFree((LPITEMIDLIST)pidl);
                  }
                }
                CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppidl);
              }
              CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v17);
            }
          }
          ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&ppv);
        }
        ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v18);
      }
      CoTaskMemFree(pv);
      CoTaskMemFree(v25);
      ClearAutoListInit((struct AUTOLISTINIT *)v21);
    }
  }
  ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(&v14);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x1800bbcf4  push    rbp
0x1800bbcf6  push    rbx
0x1800bbcf7  push    rsi
0x1800bbcf8  push    rdi
0x1800bbcf9  push    r14
0x1800bbcfb  push    r15
0x1800bbcfd  lea     rbp, [rsp-48h]
0x1800bbd02  sub     rsp, 148h
0x1800bbd09  mov     rax, cs:__security_cookie
0x1800bbd10  xor     rax, rsp
0x1800bbd13  mov     [rbp+70h+var_40], rax
0x1800bbd17  mov     r14, r9
0x1800bbd1a  mov     r15, r8
0x1800bbd1d  mov     edi, edx
0x1800bbd1f  mov     rsi, rcx
0x1800bbd22  mov     qword ptr [r9], 0
0x1800bbd29  mov     [rsp+170h+var_138], 0
0x1800bbd32  lea     r9, [rsp+170h+var_138]; void **
0x1800bbd37  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x1800bbd3e  lea     rdx, _GUID_c3be0d61_c82a_4abe_bf10_330f84a45c82; struct _GUID *
0x1800bbd45  call    ?IUnknown_QueryObject@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; IUnknown_QueryObject(IUnknown *,_GUID const &,_GUID const &,void * *)
0x1800bbd4a  mov     ebx, eax
0x1800bbd4c  test    eax, eax
0x1800bbd4e  js      loc_1800BBF60
0x1800bbd54  xor     edx, edx; Val
0x1800bbd56  mov     r8d, 0B0h; Size
0x1800bbd5c  lea     rcx, [rbp+70h+var_F0]; void *
0x1800bbd60  call    memset_0
0x1800bbd65  lea     r8, [rbp+70h+var_F0]
0x1800bbd69  mov     edx, 3
0x1800bbd6e  mov     rcx, [rsp+170h+var_138]
0x1800bbd73  call    ?GetAUTOLISTINITFromAutoListDescription@@YAJPEAUIAutoListDescription@@W4AUTOLISTINIT_FLAGS@@PEAUAUTOLISTINIT@@@Z; GetAUTOLISTINITFromAutoListDescription(IAutoListDescription *,AUTOLISTINIT_FLAGS,AUTOLISTINIT *)
0x1800bbd78  mov     ebx, eax
0x1800bbd7a  test    eax, eax
0x1800bbd7c  js      loc_1800BBF60
0x1800bbd82  or      [rbp+70h+var_D0], edi
0x1800bbd85  test    dil, 8
0x1800bbd89  jz      short loc_1800BBDE5
0x1800bbd8b  mov     [rsp+170h+ppv], 0
0x1800bbd94  lea     rdx, [rsp+170h+ppv]; struct IScope **
0x1800bbd99  mov     rcx, [rsp+170h+var_138]; struct IAutoListDescription *
0x1800bbd9e  call    ?MakeAutoListScopeRecursive@@YAJPEAUIAutoListDescription@@PEAPEAUIScope@@@Z; MakeAutoListScopeRecursive(IAutoListDescription *,IScope * *)
0x1800bbda3  mov     ebx, eax
0x1800bbda5  test    eax, eax
0x1800bbda7  js      short loc_1800BBDD3
0x1800bbda9  cmp     [rsp+170h+ppv], 0
0x1800bbdaf  jz      short loc_1800BBDD3
0x1800bbdb1  mov     rcx, [rbp+70h+var_70]
0x1800bbdb5  mov     rax, [rcx]
0x1800bbdb8  mov     rax, [rax+10h]
0x1800bbdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbdc1  mov     rax, [rsp+170h+ppv]
0x1800bbdc6  mov     [rsp+170h+ppv], 0
0x1800bbdcf  mov     [rbp+70h+var_70], rax
0x1800bbdd3  lea     rcx, [rsp+170h+ppv]
0x1800bbdd8  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800bbddd  test    ebx, ebx
0x1800bbddf  js      loc_1800BBF42
0x1800bbde5  cmp     [rbp+70h+var_E8], 0
0x1800bbdea  jnz     short loc_1800BBE02
0x1800bbdec  lea     rax, [rbp+70h+var_E8]
0x1800bbdf0  mov     [rsp+170h+var_150], rax; unsigned __int16 **
0x1800bbdf5  mov     r9, [rbp+70h+var_68]; struct IShellItemArray *
0x1800bbdf9  mov     r8, [rbp+70h+var_70]; struct IScope *
0x1800bbdfd  call    ?GetSearchFolderName@@YAJPEAUHINSTANCE__@@IPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetSearchFolderName(HINSTANCE__ *,uint,IScope *,IShellItemArray *,ushort * *)
0x1800bbe02  mov     [rsp+170h+var_118], 0
0x1800bbe0b  lea     r9, [rsp+170h+var_118]; void **
0x1800bbe10  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x1800bbe17  xor     edx, edx; struct ICompositionProcessor *
0x1800bbe19  lea     rcx, [rbp+70h+var_F0]; struct AUTOLISTINIT *
0x1800bbe1d  call    ?s_CreateInstance@CAutoList@@SAJPEBUAUTOLISTINIT@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CAutoList::s_CreateInstance(AUTOLISTINIT const *,ICompositionProcessor *,_GUID const &,void * *)
0x1800bbe22  mov     ebx, eax
0x1800bbe24  test    eax, eax
0x1800bbe26  js      loc_1800BBF38
0x1800bbe2c  mov     [rsp+170h+ppv], 0
0x1800bbe35  lea     rdx, [rsp+170h+ppv]; ppv
0x1800bbe3a  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x1800bbe41  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800bbe47  mov     ebx, eax
0x1800bbe49  test    eax, eax
0x1800bbe4b  js      loc_1800BBF2D
0x1800bbe51  mov     rcx, [rsp+170h+ppv]
0x1800bbe56  xorps   xmm0, xmm0
0x1800bbe59  xor     eax, eax
0x1800bbe5b  movups  [rsp+170h+var_110], xmm0
0x1800bbe60  mov     [rsp+170h+var_100], rax
0x1800bbe65  mov     eax, 13h
0x1800bbe6a  mov     word ptr [rsp+170h+var_110], ax
0x1800bbe6f  mov     dword ptr [rsp+170h+var_110+8], edi
0x1800bbe73  mov     rax, [rcx]
0x1800bbe76  lea     r8, [rsp+170h+var_110]
0x1800bbe7b  lea     rdx, aSecondarycompa; "SecondaryCompare"
0x1800bbe82  mov     rax, [rax+20h]
0x1800bbe86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe8b  mov     ebx, eax
0x1800bbe8d  test    eax, eax
0x1800bbe8f  js      loc_1800BBF2D
0x1800bbe95  mov     [rsp+170h+var_120], 0
0x1800bbe9e  lea     r8, [rsp+170h+var_120]
0x1800bbea3  mov     rdx, [rsp+170h+ppv]
0x1800bbea8  mov     rcx, [rsp+170h+var_118]; struct IAutoListDescription *
0x1800bbead  call    SHCreateSearchIDListFromAutoList
0x1800bbeb2  mov     ebx, eax
0x1800bbeb4  test    eax, eax
0x1800bbeb6  js      short loc_1800BBF22
0x1800bbeb8  mov     [rsp+170h+ppidl], 0
0x1800bbec1  lea     rdx, [rsp+170h+ppidl]; ppidl
0x1800bbec6  mov     rcx, rsi; punk
0x1800bbec9  call    cs:__imp_SHGetIDListFromObject
0x1800bbecf  mov     ebx, eax
0x1800bbed1  test    eax, eax
0x1800bbed3  js      short loc_1800BBF17
0x1800bbed5  mov     [rsp+170h+pidl], 0
0x1800bbede  lea     r8, [rsp+170h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1800bbee3  mov     rdx, [rsp+170h+var_120]; struct _ITEMIDLIST_ABSOLUTE *
0x1800bbee8  mov     rcx, [rsp+170h+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800bbeed  call    ?CloneChildFilters@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@0PEAPEAU1@@Z; CloneChildFilters(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800bbef2  mov     ebx, eax
0x1800bbef4  test    eax, eax
0x1800bbef6  js      short loc_1800BBF17
0x1800bbef8  mov     r8, r14; ppv
0x1800bbefb  mov     rdx, r15; riid
0x1800bbefe  mov     rcx, [rsp+170h+pidl]; pidl
0x1800bbf03  call    cs:__imp_SHCreateItemFromIDList
0x1800bbf09  mov     ebx, eax
0x1800bbf0b  mov     rcx, [rsp+170h+pidl]; pidl
0x1800bbf10  call    cs:__imp_ILFree
0x1800bbf16  nop
0x1800bbf17  lea     rcx, [rsp+170h+ppidl]
0x1800bbf1c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800bbf21  nop
0x1800bbf22  lea     rcx, [rsp+170h+var_120]
0x1800bbf27  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800bbf2c  nop
0x1800bbf2d  lea     rcx, [rsp+170h+ppv]
0x1800bbf32  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800bbf37  nop
0x1800bbf38  lea     rcx, [rsp+170h+var_118]
0x1800bbf3d  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800bbf42  mov     rcx, [rbp+70h+pv]; pv
0x1800bbf46  call    cs:__imp_CoTaskMemFree
0x1800bbf4c  mov     rcx, [rbp+70h+var_88]; pv
0x1800bbf50  call    cs:__imp_CoTaskMemFree
0x1800bbf56  lea     rcx, [rbp+70h+var_F0]; struct AUTOLISTINIT *
0x1800bbf5a  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x1800bbf5f  nop
0x1800bbf60  lea     rcx, [rsp+170h+var_138]
0x1800bbf65  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800bbf6a  mov     eax, ebx
0x1800bbf6c  mov     rcx, [rbp+70h+var_40]
0x1800bbf70  xor     rcx, rsp; StackCookie
0x1800bbf73  call    __security_check_cookie
0x1800bbf78  add     rsp, 148h
0x1800bbf7f  pop     r15
0x1800bbf81  pop     r14
0x1800bbf83  pop     rdi
0x1800bbf84  pop     rsi
0x1800bbf85  pop     rbx
0x1800bbf86  pop     rbp
0x1800bbf87  retn
```
