# SearchMultipleFolders(IShellItemArray *)

- ea: `0x1800bcd9c`
- end: `0x1800bcf91`
- name: `?SearchMultipleFolders@@YAJPEAUIShellItemArray@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bda40`

## callees

- `0x180006ca8`
- `0x18000de74`
- `0x18001173c`
- `0x180015910`
- `0x180016278`
- `0x180016d1c`
- `0x18002d4a8`
- `0x18006bb28`
- `0x180071dc0`
- `0x1800bc638`
- `0x1800bcd9c`
- `0x1800bcfc0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800bcf28`
- `Windows.Storage!ILFree` at `0x1800bcf28`
- `Windows.Storage!SHParseDisplayName` at `0x1800bcf0d`
- `Windows.Storage!SHParseDisplayName` at `0x1800bcf0d`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x1800bce4f`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x1800bce4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bcf32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bcf32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SearchMultipleFolders(struct IUnknown *a1)
{
  HRESULT ParsingName; // ebx
  struct IShellItemArray *v3; // r8
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-59h] BYREF
  __int64 v6; // [rsp+38h] [rbp-51h] BYREF
  void *v7; // [rsp+40h] [rbp-49h] BYREF
  PCWSTR pszName; // [rsp+48h] [rbp-41h] BYREF
  IShellItemArray *ppsiItemArray[2]; // [rsp+50h] [rbp-39h] BYREF
  PROPERTYKEY v10; // [rsp+60h] [rbp-29h] BYREF
  __int64 v11; // [rsp+74h] [rbp-15h]
  __int128 v12; // [rsp+80h] [rbp-9h]
  __int128 v13; // [rsp+90h] [rbp+7h]
  __int128 v14; // [rsp+A0h] [rbp+17h]
  __int64 v15; // [rsp+B0h] [rbp+27h]
  __int64 v16; // [rsp+B8h] [rbp+2Fh]
  int v17; // [rsp+C0h] [rbp+37h]

  v7 = 0;
  ParsingName = CScope_CreateInstance(a1, 0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v7);
  if ( ParsingName >= 0 )
  {
    v6 = 0;
    if ( (unsigned int)CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::Create(
                         &v6,
                         8) )
    {
      LODWORD(ppidl) = 0;
      ParsingName = SplitItemsIntoScopeAndQueries(a1, v7, &ppidl, &v6);
      if ( ParsingName >= 0 )
      {
        v3 = 0;
        ppsiItemArray[0] = 0;
        if ( v6 && *(_DWORD *)v6 )
        {
          ParsingName = SHCreateShellItemArrayFromIDLists(*(_DWORD *)v6, *(LPCITEMIDLIST **)(v6 + 8), ppsiItemArray);
          v3 = ppsiItemArray[0];
        }
        if ( ParsingName >= 0 )
        {
          v10 = PKEY_Null;
          v11 = 0;
          v12 = 0;
          v13 = 0;
          v14 = 0;
          v15 = 0;
          v16 = 67109888;
          v17 = 0;
          ParsingName = CSearchParsingName::SetScopeAndSubQueries(
                          (CSearchParsingName *)&v10,
                          (struct IScope *)((unsigned __int64)v7 & -(__int64)((_DWORD)ppidl != 0)),
                          v3);
          if ( ParsingName >= 0 )
          {
            HIDWORD(v16) = 2;
            pszName = 0;
            ParsingName = CSearchParsingName::GetParsingName(
                            (CSearchParsingName *)&v10,
                            L"search-ms",
                            (unsigned __int16 **)&pszName);
            if ( ParsingName >= 0 )
            {
              ppidl = 0;
              ParsingName = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
              if ( ParsingName >= 0 )
              {
                ParsingName = InvokeSearchIDList((const struct _ITEMIDLIST_ABSOLUTE *)ppidl);
                ILFree(ppidl);
              }
              CoTaskMemFree((LPVOID)pszName);
            }
          }
          SafeRelease<IShellItemArray>((__int64 *)ppsiItemArray);
          CSearchParsingName::~CSearchParsingName((CSearchParsingName *)&v10);
        }
      }
      CDPA<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyUnOwned<_ITEMIDLIST_ABSOLUTE>>::DestroyCallback(&v6);
    }
    else
    {
      ParsingName = -2147024882;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
    CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::~CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>(&v6);
  }
  return (unsigned int)ParsingName;
}

```

## disassembly

```asm
0x1800bcd9c  mov     [rsp-8+arg_8], rbx
0x1800bcda1  mov     [rsp-8+arg_10], rdi
0x1800bcda6  push    rbp
0x1800bcda7  lea     rbp, [rsp-57h]
0x1800bcdac  sub     rsp, 0E0h
0x1800bcdb3  mov     rax, cs:__security_cookie
0x1800bcdba  xor     rax, rsp
0x1800bcdbd  mov     [rbp+57h+var_10], rax
0x1800bcdc1  mov     rdi, rcx
0x1800bcdc4  mov     [rbp+57h+var_A0], 0
0x1800bcdcc  lea     r9, [rbp+57h+var_A0]; void **
0x1800bcdd0  lea     r8, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798; struct _GUID *
0x1800bcdd7  xor     edx, edx; struct ICompositionProcessor *
0x1800bcdd9  call    ?CScope_CreateInstance@@YAJPEAUIUnknown@@PEAUICompositionProcessor@@AEBU_GUID@@PEAPEAX@Z; CScope_CreateInstance(IUnknown *,ICompositionProcessor *,_GUID const &,void * *)
0x1800bcdde  mov     ebx, eax
0x1800bcde0  test    eax, eax
0x1800bcde2  js      loc_1800BCF6E
0x1800bcde8  mov     [rbp+57h+var_A8], 0
0x1800bcdf0  mov     edx, 8
0x1800bcdf5  lea     rcx, [rbp+57h+var_A8]
0x1800bcdf9  call    ?Create@?$CDPA_Base@VCResultRange@CResultArray@@V?$CTContainer_PolicyUnOwned@VCResultRange@CResultArray@@@@@@QEAAHH@Z; CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::Create(int)
0x1800bcdfe  test    eax, eax
0x1800bce00  jnz     short loc_1800BCE0C
0x1800bce02  mov     ebx, 8007000Eh
0x1800bce07  jmp     loc_1800BCF54
0x1800bce0c  mov     dword ptr [rbp+57h+ppidl], 0
0x1800bce13  lea     r9, [rbp+57h+var_A8]
0x1800bce17  lea     r8, [rbp+57h+ppidl]
0x1800bce1b  mov     rdx, [rbp+57h+var_A0]
0x1800bce1f  mov     rcx, rdi
0x1800bce22  call    ?SplitItemsIntoScopeAndQueries@@YAJPEAUIShellItemArray@@PEAUIScope@@PEAHPEAV?$CDPA@U_ITEMIDLIST_ABSOLUTE@@V?$CTContainer_PolicyUnOwned@U_ITEMIDLIST_ABSOLUTE@@@@@@@Z; SplitItemsIntoScopeAndQueries(IShellItemArray *,IScope *,int *,CDPA<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyUnOwned<_ITEMIDLIST_ABSOLUTE>> *)
0x1800bce27  mov     ebx, eax
0x1800bce29  test    eax, eax
0x1800bce2b  js      loc_1800BCF4B
0x1800bce31  xor     r8d, r8d
0x1800bce34  mov     [rbp+57h+ppsiItemArray], r8
0x1800bce38  mov     rdx, [rbp+57h+var_A8]
0x1800bce3c  test    rdx, rdx
0x1800bce3f  jz      short loc_1800BCE5B
0x1800bce41  mov     ecx, [rdx]; cidl
0x1800bce43  test    ecx, ecx
0x1800bce45  jz      short loc_1800BCE5B
0x1800bce47  lea     r8, [rbp+57h+ppsiItemArray]; ppsiItemArray
0x1800bce4b  mov     rdx, [rdx+8]; rgpidl
0x1800bce4f  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x1800bce55  mov     ebx, eax
0x1800bce57  mov     r8, [rbp+57h+ppsiItemArray]; struct IShellItemArray *
0x1800bce5b  test    ebx, ebx
0x1800bce5d  js      loc_1800BCF4B
0x1800bce63  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800bce6a  movaps  [rbp+57h+var_80], xmm0
0x1800bce6e  mov     eax, cs:PKEY_Null.pid
0x1800bce74  mov     [rbp+57h+var_70], eax
0x1800bce77  mov     [rbp+57h+var_6C], 0
0x1800bce7f  xorps   xmm0, xmm0
0x1800bce82  movdqa  [rbp+57h+var_60], xmm0
0x1800bce87  xorps   xmm1, xmm1
0x1800bce8a  movdqa  [rbp+57h+var_50], xmm1
0x1800bce8f  movdqa  [rbp+57h+var_40], xmm0
0x1800bce94  mov     [rbp+57h+var_30], 0
0x1800bce9c  mov     [rbp+57h+var_28], 4000400h
0x1800bcea4  mov     [rbp+57h+var_20], 0
0x1800bceab  mov     eax, dword ptr [rbp+57h+ppidl]
0x1800bceae  neg     eax
0x1800bceb0  sbb     rdx, rdx
0x1800bceb3  and     rdx, [rbp+57h+var_A0]; struct IScope *
0x1800bceb7  lea     rcx, [rbp+57h+var_80]; this
0x1800bcebb  call    ?SetScopeAndSubQueries@CSearchParsingName@@QEAAJPEAUIScope@@PEAUIShellItemArray@@@Z; CSearchParsingName::SetScopeAndSubQueries(IScope *,IShellItemArray *)
0x1800bcec0  mov     ebx, eax
0x1800bcec2  test    eax, eax
0x1800bcec4  js      short loc_1800BCF38
0x1800bcec6  mov     dword ptr [rbp+57h+var_28+4], 2
0x1800bcecd  mov     [rbp+57h+pszName], 0
0x1800bced5  lea     r8, [rbp+57h+pszName]; unsigned __int16 **
0x1800bced9  lea     rdx, aSearchMs_0; "search-ms"
0x1800bcee0  lea     rcx, [rbp+57h+var_80]; this
0x1800bcee4  call    ?GetParsingName@CSearchParsingName@@QEAAJPEBGPEAPEAG@Z; CSearchParsingName::GetParsingName(ushort const *,ushort * *)
0x1800bcee9  mov     ebx, eax
0x1800bceeb  test    eax, eax
0x1800bceed  js      short loc_1800BCF38
0x1800bceef  mov     [rbp+57h+ppidl], 0
0x1800bcef7  mov     [rsp+0E0h+psfgaoOut], 0; psfgaoOut
0x1800bcf00  xor     r9d, r9d; sfgaoIn
0x1800bcf03  lea     r8, [rbp+57h+ppidl]; ppidl
0x1800bcf07  xor     edx, edx; pbc
0x1800bcf09  mov     rcx, [rbp+57h+pszName]; pszName
0x1800bcf0d  call    cs:__imp_SHParseDisplayName
0x1800bcf13  mov     ebx, eax
0x1800bcf15  test    eax, eax
0x1800bcf17  js      short loc_1800BCF2E
0x1800bcf19  mov     rcx, [rbp+57h+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800bcf1d  call    ?InvokeSearchIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; InvokeSearchIDList(_ITEMIDLIST_ABSOLUTE const *)
0x1800bcf22  mov     ebx, eax
0x1800bcf24  mov     rcx, [rbp+57h+ppidl]; pidl
0x1800bcf28  call    cs:__imp_ILFree
0x1800bcf2e  mov     rcx, [rbp+57h+pszName]; pv
0x1800bcf32  call    cs:__imp_CoTaskMemFree
0x1800bcf38  lea     rcx, [rbp+57h+ppsiItemArray]
0x1800bcf3c  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800bcf41  nop
0x1800bcf42  lea     rcx, [rbp+57h+var_80]; this
0x1800bcf46  call    ??1CSearchParsingName@@QEAA@XZ; CSearchParsingName::~CSearchParsingName(void)
0x1800bcf4b  lea     rcx, [rbp+57h+var_A8]
0x1800bcf4f  call    ?DestroyCallback@?$CDPA@U_ITEMIDLIST_ABSOLUTE@@V?$CTContainer_PolicyUnOwned@U_ITEMIDLIST_ABSOLUTE@@@@@@QEAAXP6AHPEAU_ITEMIDLIST_ABSOLUTE@@PEAX@Z1@Z; CDPA<_ITEMIDLIST_ABSOLUTE,CTContainer_PolicyUnOwned<_ITEMIDLIST_ABSOLUTE>>::DestroyCallback(int (*)(_ITEMIDLIST_ABSOLUTE *,void *),void *)
0x1800bcf54  mov     rcx, [rbp+57h+var_A0]
0x1800bcf58  mov     rax, [rcx]
0x1800bcf5b  mov     rax, [rax+10h]
0x1800bcf5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcf64  nop
0x1800bcf65  lea     rcx, [rbp+57h+var_A8]
0x1800bcf69  call    ??1?$CDPA_Base@VCResultRange@CResultArray@@V?$CTContainer_PolicyUnOwned@VCResultRange@CResultArray@@@@@@QEAA@XZ; CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>::~CDPA_Base<CResultArray::CResultRange,CTContainer_PolicyUnOwned<CResultArray::CResultRange>>(void)
0x1800bcf6e  mov     eax, ebx
0x1800bcf70  mov     rcx, [rbp+57h+var_10]
0x1800bcf74  xor     rcx, rsp; StackCookie
0x1800bcf77  call    __security_check_cookie
0x1800bcf7c  lea     r11, [rsp+0E0h+var_s0]
0x1800bcf84  mov     rbx, [r11+18h]
0x1800bcf88  mov     rdi, [r11+20h]
0x1800bcf8c  mov     rsp, r11
0x1800bcf8f  pop     rbp
0x1800bcf90  retn
```
