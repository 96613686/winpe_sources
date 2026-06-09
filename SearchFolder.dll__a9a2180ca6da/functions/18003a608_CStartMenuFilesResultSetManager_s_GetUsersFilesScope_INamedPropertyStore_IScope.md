# CStartMenuFilesResultSetManager::s_GetUsersFilesScope(INamedPropertyStore *,IScope * *)

- ea: `0x18003a608`
- end: `0x18003a77e`
- name: `?s_GetUsersFilesScope@CStartMenuFilesResultSetManager@@SAJPEAUINamedPropertyStore@@PEAPEAUIScope@@@Z`
- size: `374`
- prototype: `static int(struct INamedPropertyStore *, struct IScope **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a5e0`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x1800076dc`
- `0x180013638`
- `0x1800289c8`
- `0x180029bb0`
- `0x18002cd68`
- `0x18003a4e4`
- `0x18003a608`
- `0x18003a980`

## import_xrefs

- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003a680`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003a680`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18003a708`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18003a708`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x18003a6bf`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x18003a6bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStartMenuFilesResultSetManager::s_GetUsersFilesScope(
        struct INamedPropertyStore *a1,
        struct IScope **a2)
{
  int SingleVisibleInList; // ebx
  struct INamedPropertyStore *v5; // rdx
  const struct _GUID *v6; // r8
  struct IShellItem *v8; // [rsp+20h] [rbp-79h] BYREF
  struct IAutoListDescription *v9; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v12[20]; // [rsp+40h] [rbp-59h] BYREF
  int v13; // [rsp+54h] [rbp-45h]
  int v14; // [rsp+58h] [rbp-41h]
  int v15; // [rsp+5Ch] [rbp-3Dh]
  int v16; // [rsp+60h] [rbp-39h]
  _BYTE v17[8]; // [rsp+A8h] [rbp+Fh] BYREF
  struct IScope *v18[6]; // [rsp+B0h] [rbp+17h] BYREF

  *a2 = 0;
  memset_0(v10, 0, 0xB0u);
  v13 = 0x40000000;
  v14 = 2;
  v15 = 1;
  v16 = 16;
  s_InitFolderTypeFromPropertyStore(a1, v12);
  SingleVisibleInList = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v18);
  if ( SingleVisibleInList >= 0 )
  {
    SingleVisibleInList = AddKnownFolderToScope(v18[0], &FOLDERID_UsersFiles, 0);
    if ( SingleVisibleInList >= 0 )
    {
      SingleVisibleInList = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, v17);
      if ( SingleVisibleInList >= 0 )
      {
        SingleVisibleInList = GetStartMenuSearchFolderName(L"files", v18[0], (struct IShellItemArray *)v18[1], &v11);
        if ( SingleVisibleInList >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v9);
          SingleVisibleInList = SHCreateAutoList(v10, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v9);
          if ( SingleVisibleInList >= 0 )
          {
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v8);
            SingleVisibleInList = CreateSearchItemFromAutoList(v9, v5, v6, (void **)&v8);
            if ( SingleVisibleInList >= 0 )
              SingleVisibleInList = CStartMenuFilesResultSetManager::s_GetScopeFromAutoList(v8, a2);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v8);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v9);
        }
      }
    }
  }
  ClearAutoListInit((struct AUTOLISTINIT *)v10);
  return (unsigned int)SingleVisibleInList;
}

```

## disassembly

```asm
0x18003a608  mov     [rsp-8+arg_10], rbx
0x18003a60d  mov     [rsp-8+arg_18], rdi
0x18003a612  push    rbp
0x18003a613  lea     rbp, [rsp-57h]
0x18003a618  sub     rsp, 0F0h
0x18003a61f  mov     rax, cs:__security_cookie
0x18003a626  xor     rax, rsp
0x18003a629  mov     [rbp+57h+var_10], rax
0x18003a62d  mov     rdi, rdx
0x18003a630  mov     rbx, rcx
0x18003a633  mov     qword ptr [rdx], 0
0x18003a63a  xor     edx, edx; Val
0x18003a63c  mov     r8d, 0B0h; Size
0x18003a642  lea     rcx, [rbp+57h+var_C0]; void *
0x18003a646  call    memset_0
0x18003a64b  mov     [rbp+57h+var_9C], 40000000h
0x18003a652  mov     [rbp+57h+var_98], 2
0x18003a659  mov     [rbp+57h+var_94], 1
0x18003a660  mov     [rbp+57h+var_90], 10h
0x18003a667  lea     rdx, [rbp+57h+var_B0]
0x18003a66b  mov     rcx, rbx
0x18003a66e  call    s_InitFolderTypeFromPropertyStore
0x18003a673  lea     r8, [rbp+57h+var_40]
0x18003a677  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003a67e  xor     ecx, ecx
0x18003a680  call    cs:__imp_SHCreateScope
0x18003a686  mov     ebx, eax
0x18003a688  test    eax, eax
0x18003a68a  js      loc_18003A752
0x18003a690  xor     r8d, r8d
0x18003a693  lea     rdx, FOLDERID_UsersFiles
0x18003a69a  mov     rcx, [rbp+57h+var_40]
0x18003a69e  call    ?AddKnownFolderToScope@@YAJPEAUIScope@@AEBU_GUID@@W4SCOPE_ITEM_FLAGS@@@Z; AddKnownFolderToScope(IScope *,_GUID const &,SCOPE_ITEM_FLAGS)
0x18003a6a3  mov     ebx, eax
0x18003a6a5  test    eax, eax
0x18003a6a7  js      loc_18003A752
0x18003a6ad  lea     r8, [rbp+57h+var_48]
0x18003a6b1  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x18003a6b8  lea     rcx, aItem; "item"
0x18003a6bf  call    cs:__imp_CreateSingleVisibleInList
0x18003a6c5  mov     ebx, eax
0x18003a6c7  test    eax, eax
0x18003a6c9  js      loc_18003A752
0x18003a6cf  lea     r9, [rbp+57h+var_B8]; unsigned __int16 **
0x18003a6d3  mov     r8, [rbp+57h+var_38]; struct IShellItemArray *
0x18003a6d7  mov     rdx, [rbp+57h+var_40]; struct IScope *
0x18003a6db  lea     rcx, aFiles; "files"
0x18003a6e2  call    ?GetStartMenuSearchFolderName@@YAJPEBGPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetStartMenuSearchFolderName(ushort const *,IScope *,IShellItemArray *,ushort * *)
0x18003a6e7  mov     ebx, eax
0x18003a6e9  test    eax, eax
0x18003a6eb  js      short loc_18003A752
0x18003a6ed  lea     rcx, [rbp+57h+var_C8]; void *
0x18003a6f1  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003a6f6  nop
0x18003a6f7  lea     r9, [rbp+57h+var_C8]
0x18003a6fb  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18003a702  xor     edx, edx
0x18003a704  lea     rcx, [rbp+57h+var_C0]
0x18003a708  call    cs:__imp_SHCreateAutoList
0x18003a70e  mov     ebx, eax
0x18003a710  test    eax, eax
0x18003a712  js      short loc_18003A749
0x18003a714  lea     rcx, [rbp+57h+var_D0]; void *
0x18003a718  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003a71d  nop
0x18003a71e  lea     r9, [rbp+57h+var_D0]; void **
0x18003a722  mov     rcx, [rbp+57h+var_C8]; struct IAutoListDescription *
0x18003a726  call    ?CreateSearchItemFromAutoList@@YAJPEAUIAutoListDescription@@PEAUINamedPropertyStore@@AEBU_GUID@@PEAPEAX@Z; CreateSearchItemFromAutoList(IAutoListDescription *,INamedPropertyStore *,_GUID const &,void * *)
0x18003a72b  mov     ebx, eax
0x18003a72d  test    eax, eax
0x18003a72f  js      short loc_18003A73F
0x18003a731  mov     rdx, rdi; struct IScope **
0x18003a734  mov     rcx, [rbp+57h+var_D0]; struct IShellItem *
0x18003a738  call    ?s_GetScopeFromAutoList@CStartMenuFilesResultSetManager@@SAJPEAUIShellItem@@PEAPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_GetScopeFromAutoList(IShellItem *,IScope * *)
0x18003a73d  mov     ebx, eax
0x18003a73f  lea     rcx, [rbp+57h+var_D0]
0x18003a743  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003a748  nop
0x18003a749  lea     rcx, [rbp+57h+var_C8]
0x18003a74d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003a752  lea     rcx, [rbp+57h+var_C0]; struct AUTOLISTINIT *
0x18003a756  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18003a75b  mov     eax, ebx
0x18003a75d  mov     rcx, [rbp+57h+var_10]
0x18003a761  xor     rcx, rsp; StackCookie
0x18003a764  call    __security_check_cookie
0x18003a769  lea     r11, [rsp+0F0h+var_s0]
0x18003a771  mov     rbx, [r11+20h]
0x18003a775  mov     rdi, [r11+28h]
0x18003a779  mov     rsp, r11
0x18003a77c  pop     rbp
0x18003a77d  retn
```
