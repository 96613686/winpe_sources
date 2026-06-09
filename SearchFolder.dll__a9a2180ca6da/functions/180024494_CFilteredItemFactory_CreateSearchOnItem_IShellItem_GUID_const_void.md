# CFilteredItemFactory::_CreateSearchOnItem(IShellItem *,_GUID const &,void * *)

- ea: `0x180024494`
- end: `0x18002467c`
- name: `?_CreateSearchOnItem@CFilteredItemFactory@@AEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `488`
- prototype: `__int64 __fastcall(CFilteredItemFactory *this, IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022660`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x1800224d0`
- `0x180024494`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x1800244d4`
- `SHELL32!SHGetIDListFromObject` at `0x1800244d4`
- `SHELL32!SHCreateItemFromIDList` at `0x180024601`
- `SHELL32!SHCreateItemFromIDList` at `0x180024601`
- `SHELL32!__imp_ILFree` at `0x18002460e`
- `SHELL32!__imp_ILFree` at `0x180024655`
- `SHELL32!__imp_ILFree` at `0x18002460e`
- `SHELL32!__imp_ILFree` at `0x180024655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002463a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002463a`
- `api-ms-win-winrt-search-folder-l1-1-0!GetScopeFolderType` at `0x180024583`
- `api-ms-win-winrt-search-folder-l1-1-0!GetScopeFolderType` at `0x180024583`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x1800245c5`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x1800245c5`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180024561`
- `api-ms-win-winrt-search-folder-l1-1-0!CreateSingleVisibleInList` at `0x180024561`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromIDListsEx` at `0x18002451f`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromIDListsEx` at `0x18002451f`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x1800245e6`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateSearchIDListFromAutoList` at `0x1800245e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFilteredItemFactory::_CreateSearchOnItem(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v6; // ebx
  const unsigned __int16 *v7; // rdx
  int v8; // r8d
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v15; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+8Ch] [rbp-74h]
  int v17; // [rsp+90h] [rbp-70h]
  __int64 v18; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v19[6]; // [rsp+E0h] [rbp-20h] BYREF

  *a4 = 0;
  ppidl[0] = 0;
  v6 = SHGetIDListFromObject(a2, ppidl);
  if ( v6 >= 0 )
  {
    memset_0(v13, 0, 0xB0u);
    v6 = SHCreateScopeFromIDListsEx(1, ppidl, 1, 1, 1, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v19);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPVOID *))a2->lpVtbl[1].Release)(a2, 0, &pv);
      if ( v6 >= 0 )
      {
        v6 = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, &v18);
        if ( v6 >= 0 )
        {
          v16 = -1;
          v17 = -1;
          if ( (int)GetScopeFolderType(v19[0], &v15) < 0 )
            v15 = FOLDERTYPEID_GenericSearchResults;
          AdjustFolderType(&v15, v7, v8, &v15);
          v11 = 0;
          v6 = SHCreateAutoList(v13, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v11);
          if ( v6 >= 0 )
          {
            pidl = 0;
            v6 = SHCreateSearchIDListFromAutoList(v11, 0, &pidl);
            if ( v6 >= 0 )
            {
              v6 = SHCreateItemFromIDList(pidl, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, a4);
              ILFree((LPITEMIDLIST)pidl);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
    }
    ILFree(ppidl[0]);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180024494  mov     [rsp-8+arg_0], rbx
0x180024499  push    rbp
0x18002449a  push    rsi
0x18002449b  push    rdi
0x18002449c  lea     rbp, [rsp-20h]
0x1800244a1  sub     rsp, 120h
0x1800244a8  mov     rax, cs:__security_cookie
0x1800244af  xor     rax, rsp
0x1800244b2  mov     [rbp+30h+var_20], rax
0x1800244b6  mov     rdi, rdx
0x1800244b9  mov     qword ptr [r9], 0
0x1800244c0  mov     rcx, rdi; punk
0x1800244c3  mov     [rsp+130h+ppidl], 0
0x1800244cc  lea     rdx, [rsp+130h+ppidl]; ppidl
0x1800244d1  mov     rsi, r9
0x1800244d4  call    cs:__imp_SHGetIDListFromObject
0x1800244da  mov     ebx, eax
0x1800244dc  test    eax, eax
0x1800244de  js      loc_18002465B
0x1800244e4  xor     edx, edx; Val
0x1800244e6  lea     rcx, [rsp+130h+var_D0]; void *
0x1800244eb  mov     r8d, 0B0h; Size
0x1800244f1  call    memset_0
0x1800244f6  mov     ecx, 1
0x1800244fb  lea     rax, [rbp+30h+var_50]
0x1800244ff  mov     [rsp+130h+var_100], rax
0x180024504  lea     rdx, [rsp+130h+ppidl]
0x180024509  lea     rax, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180024510  mov     r9d, ecx
0x180024513  mov     [rsp+130h+var_108], rax
0x180024518  mov     r8d, ecx
0x18002451b  mov     [rsp+130h+var_110], ecx
0x18002451f  call    cs:__imp_SHCreateScopeFromIDListsEx
0x180024525  mov     ebx, eax
0x180024527  test    eax, eax
0x180024529  js      loc_180024650
0x18002452f  mov     rax, [rdi]
0x180024532  lea     r8, [rsp+130h+pv]
0x180024537  xor     edx, edx
0x180024539  mov     rcx, rdi
0x18002453c  mov     rax, [rax+28h]
0x180024540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024545  mov     ebx, eax
0x180024547  test    eax, eax
0x180024549  js      loc_180024640
0x18002454f  lea     r8, [rbp+30h+var_58]
0x180024553  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x18002455a  lea     rcx, aItem; "item"
0x180024561  call    cs:__imp_CreateSingleVisibleInList
0x180024567  mov     ebx, eax
0x180024569  test    eax, eax
0x18002456b  js      loc_180024635
0x180024571  mov     rcx, [rbp+30h+var_50]
0x180024575  lea     rdx, [rsp+130h+var_C0]
0x18002457a  or      eax, 0FFFFFFFFh
0x18002457d  mov     [rbp+30h+var_A4], eax
0x180024580  mov     [rbp+30h+var_A0], eax
0x180024583  call    cs:__imp_GetScopeFolderType
0x180024589  test    eax, eax
0x18002458b  jns     short loc_18002459A
0x18002458d  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_GenericSearchResults.Data1
0x180024594  movdqu  xmmword ptr [rsp+130h+var_C0.Data1], xmm0
0x18002459a  lea     r9, [rsp+130h+var_C0]; struct _GUID *
0x18002459f  lea     rcx, [rsp+130h+var_C0]; struct _GUID *
0x1800245a4  call    ?AdjustFolderType@@YAXAEBU_GUID@@PEBGHPEAU1@@Z; AdjustFolderType(_GUID const &,ushort const *,int,_GUID *)
0x1800245a9  lea     r9, [rsp+130h+var_E8]
0x1800245ae  mov     [rsp+130h+var_E8], 0
0x1800245b7  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x1800245be  xor     edx, edx
0x1800245c0  lea     rcx, [rsp+130h+var_D0]
0x1800245c5  call    cs:__imp_SHCreateAutoList
0x1800245cb  mov     ebx, eax
0x1800245cd  test    eax, eax
0x1800245cf  js      short loc_180024625
0x1800245d1  mov     rcx, [rsp+130h+var_E8]
0x1800245d6  lea     r8, [rsp+130h+pidl]
0x1800245db  xor     edx, edx
0x1800245dd  mov     [rsp+130h+pidl], 0
0x1800245e6  call    cs:__imp_SHCreateSearchIDListFromAutoList
0x1800245ec  mov     ebx, eax
0x1800245ee  test    eax, eax
0x1800245f0  js      short loc_180024614
0x1800245f2  mov     rcx, [rsp+130h+pidl]; pidl
0x1800245f7  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236; riid
0x1800245fe  mov     r8, rsi; ppv
0x180024601  call    cs:__imp_SHCreateItemFromIDList
0x180024607  mov     rcx, [rsp+130h+pidl]; pidl
0x18002460c  mov     ebx, eax
0x18002460e  call    cs:__imp_ILFree
0x180024614  mov     rcx, [rsp+130h+var_E8]
0x180024619  mov     rax, [rcx]
0x18002461c  mov     rax, [rax+10h]
0x180024620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024625  mov     rcx, [rbp+30h+var_58]
0x180024629  mov     rax, [rcx]
0x18002462c  mov     rax, [rax+10h]
0x180024630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024635  mov     rcx, [rsp+130h+pv]; pv
0x18002463a  call    cs:__imp_CoTaskMemFree
0x180024640  mov     rcx, [rbp+30h+var_50]
0x180024644  mov     rax, [rcx]
0x180024647  mov     rax, [rax+10h]
0x18002464b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024650  mov     rcx, [rsp+130h+ppidl]; pidl
0x180024655  call    cs:__imp_ILFree
0x18002465b  mov     eax, ebx
0x18002465d  mov     rcx, [rbp+30h+var_20]
0x180024661  xor     rcx, rsp; StackCookie
0x180024664  call    __security_check_cookie
0x180024669  mov     rbx, [rsp+130h+arg_0]
0x180024671  add     rsp, 120h
0x180024678  pop     rdi
0x180024679  pop     rsi
0x18002467a  pop     rbp
0x18002467b  retn
```
