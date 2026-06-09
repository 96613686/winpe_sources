# CFilteredItemFactory::_CreateSearchOnItem(IShellItem *,_GUID const &,void * *)

- ea: `0x1800beab0`
- end: `0x1800becad`
- name: `?_CreateSearchOnItem@CFilteredItemFactory@@AEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `509`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d2f0`

## callees

- `0x180005bf0`
- `0x180035860`
- `0x180040c30`
- `0x180055bf4`
- `0x18005c1a0`
- `0x180071dc0`
- `0x180072cf4`
- `0x1800bd480`
- `0x1800beab0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800bec3a`
- `Windows.Storage!ILFree` at `0x1800bec81`
- `Windows.Storage!ILFree` at `0x1800bec3a`
- `Windows.Storage!ILFree` at `0x1800bec81`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800beaf6`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800beaf6`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800bec2d`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800bec2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bec66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bec66`

## pseudocode

```c
__int64 __fastcall CFilteredItemFactory::_CreateSearchOnItem(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int Instance; // ebx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  struct IAutoListDescription *v9; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v13; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+8Ch] [rbp-74h]
  int v15; // [rsp+90h] [rbp-70h]
  __int64 v16; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v17[6]; // [rsp+E0h] [rbp-20h] BYREF

  *a4 = 0;
  ppidl[0] = 0;
  Instance = SHGetIDListFromObject(a2, ppidl);
  if ( Instance >= 0 )
  {
    memset_0(v11, 0, 0xB0u);
    Instance = SHCreateScopeFromIDListsEx(
                 1,
                 (unsigned int)ppidl,
                 1,
                 1,
                 1,
                 (__int64)&GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
                 (__int64)v17);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPVOID *))a2->lpVtbl[1].Release)(a2, 0, &pv);
      if ( Instance >= 0 )
      {
        Instance = CreateSingleVisibleInList(L"item", &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495, &v16);
        if ( Instance >= 0 )
        {
          v14 = -1;
          v15 = -1;
          if ( (int)GetScopeFolderType(v17[0], &v13) < 0 )
            v13 = FOLDERTYPEID_GenericSearchResults;
          AdjustFolderType(&v13, L"SearchResults", 1, &v13);
          v9 = 0;
          Instance = CAutoList::s_CreateInstance(
                       (const struct AUTOLISTINIT *)v11,
                       0,
                       &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                       (void **)&v9);
          if ( Instance >= 0 )
          {
            pidl = 0;
            Instance = SHCreateSearchIDListFromAutoList(v9, 0, (LPITEMIDLIST *)&pidl);
            if ( Instance >= 0 )
            {
              Instance = SHCreateItemFromIDList(pidl, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, a4);
              ILFree((LPITEMIDLIST)pidl);
            }
            (*(void (__fastcall **)(struct IAutoListDescription *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17[0] + 16LL))(v17[0]);
    }
    ILFree(ppidl[0]);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800beab0  mov     [rsp-8+arg_0], rbx
0x1800beab5  mov     [rsp-8+arg_10], rsi
0x1800beaba  push    rbp
0x1800beabb  push    rdi
0x1800beabc  push    r15
0x1800beabe  lea     rbp, [rsp-20h]
0x1800beac3  sub     rsp, 120h
0x1800beaca  mov     rax, cs:__security_cookie
0x1800bead1  xor     rax, rsp
0x1800bead4  mov     [rbp+30h+var_20], rax
0x1800bead8  mov     rdi, rdx
0x1800beadb  mov     qword ptr [r9], 0
0x1800beae2  mov     rcx, rdi; punk
0x1800beae5  mov     [rsp+130h+ppidl], 0
0x1800beaee  lea     rdx, [rsp+130h+ppidl]; ppidl
0x1800beaf3  mov     rsi, r9
0x1800beaf6  call    cs:__imp_SHGetIDListFromObject
0x1800beafc  mov     ebx, eax
0x1800beafe  test    eax, eax
0x1800beb00  js      loc_1800BEC87
0x1800beb06  xor     edx, edx; Val
0x1800beb08  lea     rcx, [rsp+130h+var_D0]; void *
0x1800beb0d  mov     r8d, 0B0h; Size
0x1800beb13  call    memset_0
0x1800beb18  mov     r15d, 1
0x1800beb1e  lea     rax, [rbp+30h+var_50]
0x1800beb22  mov     [rsp+130h+var_100], rax
0x1800beb27  lea     rdx, [rsp+130h+ppidl]
0x1800beb2c  lea     rax, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x1800beb33  mov     r9d, r15d
0x1800beb36  mov     [rsp+130h+var_108], rax
0x1800beb3b  mov     r8d, r15d
0x1800beb3e  mov     ecx, r15d
0x1800beb41  mov     [rsp+130h+var_110], r15d
0x1800beb46  call    SHCreateScopeFromIDListsEx
0x1800beb4b  mov     ebx, eax
0x1800beb4d  test    eax, eax
0x1800beb4f  js      loc_1800BEC7C
0x1800beb55  mov     rax, [rdi]
0x1800beb58  lea     r8, [rsp+130h+pv]
0x1800beb5d  xor     edx, edx
0x1800beb5f  mov     rcx, rdi
0x1800beb62  mov     rax, [rax+28h]
0x1800beb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb6b  mov     ebx, eax
0x1800beb6d  test    eax, eax
0x1800beb6f  js      loc_1800BEC6C
0x1800beb75  lea     r8, [rbp+30h+var_58]
0x1800beb79  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x1800beb80  lea     rcx, aItem; "item"
0x1800beb87  call    CreateSingleVisibleInList
0x1800beb8c  mov     ebx, eax
0x1800beb8e  test    eax, eax
0x1800beb90  js      loc_1800BEC61
0x1800beb96  mov     rcx, [rbp+30h+var_50]
0x1800beb9a  lea     rdx, [rsp+130h+var_C0]
0x1800beb9f  or      eax, 0FFFFFFFFh
0x1800beba2  mov     [rbp+30h+var_A4], eax
0x1800beba5  mov     [rbp+30h+var_A0], eax
0x1800beba8  call    GetScopeFolderType
0x1800bebad  test    eax, eax
0x1800bebaf  jns     short loc_1800BEBBE
0x1800bebb1  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_GenericSearchResults.Data1
0x1800bebb8  movdqu  xmmword ptr [rsp+130h+var_C0.Data1], xmm0
0x1800bebbe  lea     r9, [rsp+130h+var_C0]; struct _GUID *
0x1800bebc3  mov     r8d, r15d; int
0x1800bebc6  lea     rdx, aSearchresults; "SearchResults"
0x1800bebcd  lea     rcx, [rsp+130h+var_C0]; struct _GUID *
0x1800bebd2  call    ?AdjustFolderType@@YAXAEBU_GUID@@PEBGHPEAU1@@Z; AdjustFolderType(_GUID const &,ushort const *,int,_GUID *)
0x1800bebd7  lea     r9, [rsp+130h+var_E8]; void **
0x1800bebdc  mov     [rsp+130h+var_E8], 0
0x1800bebe5  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456; struct _GUID *
0x1800bebec  xor     edx, edx; struct ICompositionProcessor *
0x1800bebee  lea     rcx, [rsp+130h+var_D0]; struct AUTOLISTINIT *
0x1800bebf3  call    ?s_CreateInstance@CAutoList@@SAJPEBUAUTOLISTINIT@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CAutoList::s_CreateInstance(AUTOLISTINIT const *,ICompositionProcessor *,_GUID const &,void * *)
0x1800bebf8  mov     ebx, eax
0x1800bebfa  test    eax, eax
0x1800bebfc  js      short loc_1800BEC51
0x1800bebfe  mov     rcx, [rsp+130h+var_E8]; struct IAutoListDescription *
0x1800bec03  lea     r8, [rsp+130h+pidl]
0x1800bec08  xor     edx, edx
0x1800bec0a  mov     [rsp+130h+pidl], 0
0x1800bec13  call    SHCreateSearchIDListFromAutoList
0x1800bec18  mov     ebx, eax
0x1800bec1a  test    eax, eax
0x1800bec1c  js      short loc_1800BEC40
0x1800bec1e  mov     rcx, [rsp+130h+pidl]; pidl
0x1800bec23  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236; riid
0x1800bec2a  mov     r8, rsi; ppv
0x1800bec2d  call    cs:__imp_SHCreateItemFromIDList
0x1800bec33  mov     rcx, [rsp+130h+pidl]; pidl
0x1800bec38  mov     ebx, eax
0x1800bec3a  call    cs:__imp_ILFree
0x1800bec40  mov     rcx, [rsp+130h+var_E8]
0x1800bec45  mov     rax, [rcx]
0x1800bec48  mov     rax, [rax+10h]
0x1800bec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec51  mov     rcx, [rbp+30h+var_58]
0x1800bec55  mov     rax, [rcx]
0x1800bec58  mov     rax, [rax+10h]
0x1800bec5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec61  mov     rcx, [rsp+130h+pv]; pv
0x1800bec66  call    cs:__imp_CoTaskMemFree
0x1800bec6c  mov     rcx, [rbp+30h+var_50]
0x1800bec70  mov     rax, [rcx]
0x1800bec73  mov     rax, [rax+10h]
0x1800bec77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec7c  mov     rcx, [rsp+130h+ppidl]; pidl
0x1800bec81  call    cs:__imp_ILFree
0x1800bec87  mov     eax, ebx
0x1800bec89  mov     rcx, [rbp+30h+var_20]
0x1800bec8d  xor     rcx, rsp; StackCookie
0x1800bec90  call    __security_check_cookie
0x1800bec95  lea     r11, [rsp+130h+var_10]
0x1800bec9d  mov     rbx, [r11+20h]
0x1800beca1  mov     rsi, [r11+30h]
0x1800beca5  mov     rsp, r11
0x1800beca8  pop     r15
0x1800becaa  pop     rdi
0x1800becab  pop     rbp
0x1800becac  retn
```
