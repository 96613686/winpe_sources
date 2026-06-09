# CreateSearchOnAnyFolder

- ea: `0x18003ceec`
- end: `0x18003d220`
- name: `CreateSearchOnAnyFolder`
- size: `820`
- prototype: `__int64 __usercall@<rax>(struct _ITEMIDLIST_ABSOLUTE *@<rcx>, struct _GUID *@<rdx>, int, int, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800200ec`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x180011f3c`
- `0x1800129c0`
- `0x1800136e8`
- `0x180019218`
- `0x180019310`
- `0x1800224d0`
- `0x180022da0`
- `0x18002fa40`
- `0x18003cb40`
- `0x18003cdd0`
- `0x18003ce0c`
- `0x18003ceec`
- `0x18003d228`
- `0x18003d3ac`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18003cf69`
- `SHELL32!SHCreateItemFromIDList` at `0x18003cf69`
- `SHELL32!__imp_ILFree` at `0x18003d178`
- `SHELL32!__imp_ILFree` at `0x18003d1f5`
- `SHELL32!__imp_ILFree` at `0x18003d178`
- `SHELL32!__imp_ILFree` at `0x18003d1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d0e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d0e4`

## pseudocode

```c
__int64 __fastcall CreateSearchOnAnyFolder(
        struct _ITEMIDLIST_ABSOLUTE *a1,
        struct _GUID *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        struct _ITEMIDLIST_ABSOLUTE **a7)
{
  HINSTANCE v7; // r14
  HRESULT NonFilteredRoot; // ebx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // edx
  const unsigned __int16 *v14; // rdx
  int v15; // r8d
  const struct _GUID *v16; // rdx
  const unsigned __int16 *v17; // rcx
  HRESULT appended; // eax
  LPITEMIDLIST v20; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v29; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+9Ch] [rbp-64h]
  int v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+C4h] [rbp-3Ch]
  const struct _GUID *v34; // [rsp+C8h] [rbp-38h]
  void *v35; // [rsp+E8h] [rbp-18h] BYREF
  struct IScope *v36[6]; // [rsp+F0h] [rbp-10h] BYREF

  v7 = g_hinst;
  pidl = 0;
  *a7 = 0;
  NonFilteredRoot = GetNonFilteredRoot(a1, 1, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  if ( NonFilteredRoot >= 0 )
  {
    ppv = 0;
    NonFilteredRoot = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( NonFilteredRoot >= 0 )
    {
      v23 = 0;
      NonFilteredRoot = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          0,
                          &BHID_SFObject,
                          &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                          &v23);
      if ( NonFilteredRoot >= 0 )
      {
        v22 = 0;
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v23)(
          v23,
          &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
          &v22);
        memset_0(v27, 0, 0xB0u);
        v30 = (unsigned int)FolderMustForceFullText(v22) != 0 ? 2 : 0;
        if ( !(unsigned int)IsAdvancedQuerySyntaxLocation(v23) )
          v30 |= 0x20u;
        v31 = -1;
        v32 = -1;
        v11 = ((unsigned int)GetSearchOptionValue(3u) != 0) + 32;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::GetImpl'::`2'::impl) )
          v11 |= 0x800u;
        NonFilteredRoot = GetScopeForSearch(ppv, v12, v11, v36);
        if ( NonFilteredRoot >= 0 )
        {
          NonFilteredRoot = GetSearchFolderName(v7, v13, v36[0], 0, (unsigned __int16 **)&pv);
          if ( NonFilteredRoot >= 0 )
          {
            AdjustFolderType(a2, v14, v15, &v29);
            if ( !(unsigned int)operator==(&PKEY_Null, &PKEY_Null) )
            {
              v33 = 1;
              v34 = v16;
            }
            NonFilteredRoot = SHCreateSingleKindList(v17, v16, &v35);
            if ( NonFilteredRoot >= 0 )
            {
              v21 = 0;
              NonFilteredRoot = CoCreateInstance(
                                  &GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d,
                                  0,
                                  1u,
                                  &GUID_c0a6c367_c264_4385_a704_9088bdc3640e,
                                  &v21);
              if ( NonFilteredRoot >= 0 )
              {
                v25 = 0;
                NonFilteredRoot = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, GUID *, __int64 *))(*(_QWORD *)v21 + 24LL))(
                                    v21,
                                    v27,
                                    &GUID_607c87f7_0696_4558_a368_de5e59cfe456,
                                    &v25);
                if ( NonFilteredRoot >= 0 )
                {
                  v20 = 0;
                  NonFilteredRoot = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, LPITEMIDLIST *))(*(_QWORD *)v21 + 40LL))(
                                      v21,
                                      v25,
                                      0,
                                      &v20);
                  if ( NonFilteredRoot >= 0 )
                  {
                    if ( v22 )
                      appended = CloneChildFilters(a1, (const struct _ITEMIDLIST_ABSOLUTE *)v20, a7);
                    else
                      appended = AppendFolderFiltersToIDList(a1, v20, a7);
                    NonFilteredRoot = appended;
                    ILFree(v20);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
            }
            CoTaskMemFree(pv);
          }
          SafeRelease<IShellItemArray>((__int64 *)v36);
        }
        SafeRelease<IShellItemArray>(&v22);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ILFree((LPITEMIDLIST)pidl);
  }
  return (unsigned int)NonFilteredRoot;
}

```

## disassembly

```asm
0x18003ceec  mov     [rsp-8+arg_10], rbx
0x18003cef1  push    rbp
0x18003cef2  push    rsi
0x18003cef3  push    rdi
0x18003cef4  push    r14
0x18003cef6  push    r15
0x18003cef8  lea     rbp, [rsp-30h]
0x18003cefd  sub     rsp, 130h
0x18003cf04  mov     rax, cs:__security_cookie
0x18003cf0b  xor     rax, rsp
0x18003cf0e  mov     [rbp+50h+var_30], rax
0x18003cf12  mov     rsi, [rbp+50h+arg_30]
0x18003cf19  lea     r8, [rsp+150h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x18003cf1e  mov     r14, cs:g_hinst
0x18003cf25  mov     r15, rdx
0x18003cf28  mov     edx, 1; int
0x18003cf2d  mov     [rsp+150h+pidl], 0
0x18003cf36  mov     rdi, rcx
0x18003cf39  mov     qword ptr [rsi], 0
0x18003cf40  call    ?GetNonFilteredRoot@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@HPEAPEAU1@@Z; GetNonFilteredRoot(_ITEMIDLIST_ABSOLUTE const *,int,_ITEMIDLIST_ABSOLUTE * *)
0x18003cf45  mov     ebx, eax
0x18003cf47  test    eax, eax
0x18003cf49  js      loc_18003D1FB
0x18003cf4f  mov     rcx, [rsp+150h+pidl]; pidl
0x18003cf54  lea     r8, [rsp+150h+ppv]; ppv
0x18003cf59  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003cf60  mov     [rsp+150h+ppv], 0
0x18003cf69  call    cs:__imp_SHCreateItemFromIDList
0x18003cf6f  mov     ebx, eax
0x18003cf71  test    eax, eax
0x18003cf73  js      loc_18003D1F0
0x18003cf79  mov     rcx, [rsp+150h+ppv]
0x18003cf7e  lea     rdx, [rsp+150h+var_108]
0x18003cf83  mov     [rsp+150h+var_108], 0
0x18003cf8c  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18003cf93  mov     [rsp+150h+var_130], rdx
0x18003cf98  lea     r8, BHID_SFObject
0x18003cf9f  xor     edx, edx
0x18003cfa1  mov     rax, [rcx]
0x18003cfa4  mov     rax, [rax+18h]
0x18003cfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfad  mov     ebx, eax
0x18003cfaf  test    eax, eax
0x18003cfb1  js      loc_18003D1DF
0x18003cfb7  mov     rcx, [rsp+150h+var_108]
0x18003cfbc  lea     r8, [rsp+150h+var_110]
0x18003cfc1  mov     [rsp+150h+var_110], 0
0x18003cfca  lea     rdx, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x18003cfd1  mov     rax, [rcx]
0x18003cfd4  mov     rax, [rax]
0x18003cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfdc  xor     edx, edx; Val
0x18003cfde  lea     rcx, [rsp+150h+var_E0]; void *
0x18003cfe3  mov     r8d, 0B0h; Size
0x18003cfe9  call    memset_0
0x18003cfee  mov     rcx, [rsp+150h+var_110]
0x18003cff3  call    FolderMustForceFullText
0x18003cff8  neg     eax
0x18003cffa  sbb     ecx, ecx
0x18003cffc  and     ecx, 2
0x18003cfff  mov     [rbp+50h+var_C0], ecx
0x18003d002  mov     rcx, [rsp+150h+var_108]
0x18003d007  call    IsAdvancedQuerySyntaxLocation
0x18003d00c  test    eax, eax
0x18003d00e  jnz     short loc_18003D014
0x18003d010  or      [rbp+50h+var_C0], 20h
0x18003d014  or      eax, 0FFFFFFFFh
0x18003d017  mov     [rbp+50h+var_B4], eax
0x18003d01a  mov     [rbp+50h+var_B0], eax
0x18003d01d  lea     ecx, [rax+4]; unsigned int
0x18003d020  call    ?GetSearchOptionValue@@YAHK@Z; GetSearchOptionValue(ulong)
0x18003d025  neg     eax
0x18003d027  sbb     ebx, ebx
0x18003d029  neg     ebx
0x18003d02b  add     ebx, 20h ; ' '
0x18003d02e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::GetImpl(void)'::`2'::impl
0x18003d035  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FileExplorer_FederatedSearchOptIn>::__private_IsEnabled(void)
0x18003d03a  test    al, al
0x18003d03c  jz      short loc_18003D042
0x18003d03e  bts     ebx, 0Bh
0x18003d042  mov     rcx, [rsp+150h+ppv]
0x18003d047  lea     r9, [rbp+50h+var_60]
0x18003d04b  mov     r8d, ebx
0x18003d04e  call    ?GetScopeForSearch@@YAJPEAUIShellItem@@W4SCOPE_ITEM_DEPTH@@W4SCOPE_ITEM_FLAGS@@PEAPEAUIScope@@@Z; GetScopeForSearch(IShellItem *,SCOPE_ITEM_DEPTH,SCOPE_ITEM_FLAGS,IScope * *)
0x18003d053  mov     ebx, eax
0x18003d055  test    eax, eax
0x18003d057  js      loc_18003D1C4
0x18003d05d  mov     r8, [rbp+50h+var_60]; struct IScope *
0x18003d061  lea     rax, [rsp+150h+pv]
0x18003d066  xor     r9d, r9d; struct IShellItemArray *
0x18003d069  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x18003d06e  mov     rcx, r14; hInstance
0x18003d071  call    ?GetSearchFolderName@@YAJPEAUHINSTANCE__@@IPEAUIScope@@PEAUIShellItemArray@@PEAPEAG@Z; GetSearchFolderName(HINSTANCE__ *,uint,IScope *,IShellItemArray *,ushort * *)
0x18003d076  mov     ebx, eax
0x18003d078  test    eax, eax
0x18003d07a  js      loc_18003D1BB
0x18003d080  lea     r9, [rbp+50h+var_D0]; struct _GUID *
0x18003d084  mov     rcx, r15; struct _GUID *
0x18003d087  call    ?AdjustFolderType@@YAXAEBU_GUID@@PEBGHPEAU1@@Z; AdjustFolderType(_GUID const &,ushort const *,int,_GUID *)
0x18003d08c  lea     rdx, PKEY_Null
0x18003d093  mov     rcx, rdx
0x18003d096  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18003d09b  test    eax, eax
0x18003d09d  jnz     short loc_18003D0AA
0x18003d09f  mov     [rbp+50h+var_8C], 1
0x18003d0a6  mov     [rbp+50h+var_88], rdx
0x18003d0aa  lea     r8, [rbp+50h+var_68]; void **
0x18003d0ae  call    ?SHCreateSingleKindList@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHCreateSingleKindList(ushort const *,_GUID const &,void * *)
0x18003d0b3  mov     ebx, eax
0x18003d0b5  test    eax, eax
0x18003d0b7  js      loc_18003D1B0
0x18003d0bd  xor     edx, edx; pUnkOuter
0x18003d0bf  mov     [rsp+150h+var_118], 0
0x18003d0c8  lea     rax, [rsp+150h+var_118]
0x18003d0cd  lea     r9, _GUID_c0a6c367_c264_4385_a704_9088bdc3640e; riid
0x18003d0d4  mov     [rsp+150h+var_130], rax; ppv
0x18003d0d9  lea     rcx, _GUID_6e682784_1eca_4cf2_988d_96b6e89e9a4d; rclsid
0x18003d0e0  lea     r8d, [rdx+1]; dwClsContext
0x18003d0e4  call    cs:__imp_CoCreateInstance
0x18003d0ea  mov     ebx, eax
0x18003d0ec  test    eax, eax
0x18003d0ee  js      loc_18003D1A0
0x18003d0f4  mov     rcx, [rsp+150h+var_118]
0x18003d0f9  lea     r9, [rsp+150h+var_F8]
0x18003d0fe  mov     [rsp+150h+var_F8], 0
0x18003d107  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18003d10e  lea     rdx, [rsp+150h+var_E0]
0x18003d113  mov     rax, [rcx]
0x18003d116  mov     rax, [rax+18h]
0x18003d11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d11f  mov     ebx, eax
0x18003d121  test    eax, eax
0x18003d123  js      short loc_18003D18F
0x18003d125  mov     rcx, [rsp+150h+var_118]
0x18003d12a  lea     r9, [rsp+150h+var_120]
0x18003d12f  mov     rdx, [rsp+150h+var_F8]
0x18003d134  xor     r8d, r8d
0x18003d137  mov     [rsp+150h+var_120], 0
0x18003d140  mov     rax, [rcx]
0x18003d143  mov     rax, [rax+28h]
0x18003d147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d14c  mov     ebx, eax
0x18003d14e  test    eax, eax
0x18003d150  js      short loc_18003D17E
0x18003d152  cmp     [rsp+150h+var_110], 0
0x18003d158  mov     r8, rsi; struct _ITEMIDLIST_ABSOLUTE **
0x18003d15b  mov     rdx, [rsp+150h+var_120]; struct _ITEMIDLIST_ABSOLUTE *
0x18003d160  mov     rcx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x18003d163  jz      short loc_18003D16C
0x18003d165  call    ?CloneChildFilters@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@0PEAPEAU1@@Z; CloneChildFilters(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18003d16a  jmp     short loc_18003D171
0x18003d16c  call    AppendFolderFiltersToIDList
0x18003d171  mov     rcx, [rsp+150h+var_120]; pidl
0x18003d176  mov     ebx, eax
0x18003d178  call    cs:__imp_ILFree
0x18003d17e  mov     rcx, [rsp+150h+var_F8]
0x18003d183  mov     rax, [rcx]
0x18003d186  mov     rax, [rax+10h]
0x18003d18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d18f  mov     rcx, [rsp+150h+var_118]
0x18003d194  mov     rax, [rcx]
0x18003d197  mov     rax, [rax+10h]
0x18003d19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a0  mov     rcx, [rbp+50h+var_68]
0x18003d1a4  mov     rax, [rcx]
0x18003d1a7  mov     rax, [rax+10h]
0x18003d1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1b0  mov     rcx, [rsp+150h+pv]; pv
0x18003d1b5  call    cs:__imp_CoTaskMemFree
0x18003d1bb  lea     rcx, [rbp+50h+var_60]
0x18003d1bf  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18003d1c4  lea     rcx, [rsp+150h+var_110]
0x18003d1c9  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18003d1ce  mov     rcx, [rsp+150h+var_108]
0x18003d1d3  mov     rax, [rcx]
0x18003d1d6  mov     rax, [rax+10h]
0x18003d1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1df  mov     rcx, [rsp+150h+ppv]
0x18003d1e4  mov     rax, [rcx]
0x18003d1e7  mov     rax, [rax+10h]
0x18003d1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1f0  mov     rcx, [rsp+150h+pidl]; pidl
0x18003d1f5  call    cs:__imp_ILFree
0x18003d1fb  mov     eax, ebx
0x18003d1fd  mov     rcx, [rbp+50h+var_30]
0x18003d201  xor     rcx, rsp; StackCookie
0x18003d204  call    __security_check_cookie
0x18003d209  mov     rbx, [rsp+150h+arg_10]
0x18003d211  add     rsp, 130h
0x18003d218  pop     r15
0x18003d21a  pop     r14
0x18003d21c  pop     rdi
0x18003d21d  pop     rsi
0x18003d21e  pop     rbp
0x18003d21f  retn
```
