# CNetworkExplorerFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180003950`
- end: `0x180003c86`
- name: `?GetUIObjectOf@CNetworkExplorerFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `822`
- prototype: `int(CNetworkExplorerFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001b54`
- `0x180002720`
- `0x180002b48`
- `0x180003950`
- `0x180004010`
- `0x1800040b0`
- `0x18000e120`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003c38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003c38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bce`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180003a08`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180003a08`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180003b97`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180003b97`
- `SHELL32!SHCreateDataObject` at `0x180003b2a`
- `SHELL32!SHCreateDataObject` at `0x180003b2a`

## string_xrefs

- `0x180003c18`: `networkexplorer.dll`
- `0x180003c4a`: `networkexplorer.dll`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        UINT a3,
        const struct _ITEMIDLIST_RELATIVE **a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **hKey)
{
  void **v7; // r12
  const struct _GUID *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  HRESULT v14; // ebx
  CNetworkExplorerFolder *v15; // rcx
  int IsComputer; // eax
  CNetworkExplorerFolder *v17; // rcx
  const struct _ITEMIDLIST_RELATIVE *v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  __int64 v22; // rax
  int v23; // ebx
  __int64 i; // r15
  int IconFromDeviceCategory; // ebx
  const struct _ITEMIDLIST_RELATIVE *v27; // rcx
  PROPVARIANT pvar; // [rsp+30h] [rbp-51h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+50h] [rbp-31h] BYREF
  void *ppv; // [rsp+E8h] [rbp+67h] BYREF

  v7 = hKey;
  *hKey = 0;
  if ( a4 )
  {
    v10 = riid;
    v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
      v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
    if ( v11 )
    {
      v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
        v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
      if ( v12 )
      {
        v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
          v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
        if ( !v13 )
        {
          if ( a3 == 1 )
          {
            ppv = 0;
            v14 = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, &ppv);
            if ( v14 < 0 )
              return (unsigned int)v14;
            v14 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 2);
            if ( v14 < 0 )
              goto LABEL_20;
            IsComputer = CNetworkExplorerFolder::_IsComputer(v15, *a4);
            v18 = *a4;
            if ( IsComputer )
            {
              if ( (unsigned int)CNetworkExplorerFolder::_IsTree(v17, v18) )
                v19 = 41;
              else
                v19 = 15;
              v20 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 0, v19);
LABEL_18:
              v14 = v20;
              if ( v20 >= 0 )
LABEL_19:
                v14 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(ppv, v10, v7);
LABEL_20:
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
              return (unsigned int)v14;
            }
            hKey = 0;
            if ( (int)CNetworkExplorerFolder::_OpenHKeyForItemIcon(v17, v18, (HKEY *)&hKey) < 0 )
            {
              v27 = *a4;
              memset(&pvar, 0, sizeof(pvar));
              if ( (int)CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(
                          v27,
                          &PKEY_PNPX_DeviceCategory,
                          &pvar) < 0 )
              {
LABEL_46:
                v20 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64))(*(_QWORD *)ppv + 40LL))(
                        ppv,
                        L"networkexplorer.dll",
                        4294967194LL);
                goto LABEL_18;
              }
              LODWORD(hKey) = 0;
              IconFromDeviceCategory = GetIconFromDeviceCategory(&pvar, (int *)&hKey);
              if ( IconFromDeviceCategory >= 0 )
                IconFromDeviceCategory = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 40LL))(
                                           ppv,
                                           L"networkexplorer.dll",
                                           (unsigned int)-(int)hKey);
              PropVariantClear(&pvar);
            }
            else
            {
              IconFromDeviceCategory = (*(__int64 (__fastcall **)(void *, void **))(*(_QWORD *)ppv + 32LL))(ppv, hKey);
              RegCloseKey((HKEY)hKey);
            }
            if ( IconFromDeviceCategory >= 0 )
              goto LABEL_19;
            goto LABEL_46;
          }
          return (unsigned int)-2147024809;
        }
        v14 = -2147467262;
        v22 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
          v22 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
        if ( v22 )
          return (unsigned int)v14;
        v23 = 1;
        if ( a3 != 1 )
        {
          if ( !a3 )
            return (unsigned int)-2147024809;
          for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
          {
            if ( !(unsigned int)CNetworkExplorerFolder::_IsComputer((CNetworkExplorerFolder *)this, a4[i]) )
            {
              v23 = 0;
              break;
            }
          }
          if ( !v23 )
            return (unsigned int)-2147024809;
        }
        return (unsigned int)CNetworkExplorerFolder::_AssocCreate((CNetworkExplorerFolder *)this, *a4, v10, v7);
      }
      else
      {
        pdcm.hwnd = a2;
        if ( this == (LPCITEMIDLIST *)32 )
        {
          memset(&pdcm.pcmcb, 0, 24);
        }
        else
        {
          pdcm.pidlFolder = 0;
          pdcm.pcmcb = (IContextMenuCB *)(this + 2);
          pdcm.psf = (IShellFolder *)this;
        }
        pdcm.cidl = a3;
        *(&pdcm.cidl + 1) = 0;
        memset(&pdcm.punkAssociationInfo, 0, 24);
        pdcm.apidl = (LPCITEMIDLIST *)a4;
        return (unsigned int)SHCreateDefaultContextMenu(&pdcm, riid, v7);
      }
    }
    else
    {
      return (unsigned int)SHCreateDataObject(this[9], a3, (LPCITEMIDLIST *)a4, 0, riid, v7);
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180003950  mov     [rsp-8+arg_0], rbx
0x180003955  mov     [rsp-8+arg_8], rsi
0x18000395a  push    rbp
0x18000395b  push    rdi
0x18000395c  push    r12
0x18000395e  push    r14
0x180003960  push    r15
0x180003962  lea     rbp, [rsp-1Fh]
0x180003967  sub     rsp, 0A0h
0x18000396e  mov     r12, [rbp+3Fh+hKey]
0x180003972  mov     rsi, r9
0x180003975  mov     r14d, r8d
0x180003978  mov     qword ptr [r12], 0
0x180003980  test    r9, r9
0x180003983  jz      loc_180003B37
0x180003989  mov     rdi, [rbp+3Fh+arg_20]
0x18000398d  mov     rax, [rdi]
0x180003990  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180003997  jnz     short loc_1800039A4
0x180003999  mov     rax, [rdi+8]
0x18000399d  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800039a4  test    rax, rax
0x1800039a7  jz      loc_180003B13
0x1800039ad  mov     rax, [rdi]
0x1800039b0  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800039b7  jnz     short loc_1800039C4
0x1800039b9  mov     rax, [rdi+8]
0x1800039bd  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800039c4  test    rax, rax
0x1800039c7  jz      loc_180003B41
0x1800039cd  mov     rax, [rdi]
0x1800039d0  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x1800039d7  jnz     short loc_1800039E4
0x1800039d9  mov     rax, [rdi+8]
0x1800039dd  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x1800039e4  test    rax, rax
0x1800039e7  jnz     loc_180003AB0
0x1800039ed  lea     ebx, [rax+1]
0x1800039f0  cmp     r14d, ebx
0x1800039f3  jnz     loc_180003C7C
0x1800039f9  lea     rdx, [rbp+3Fh+ppv]; ppv
0x1800039fd  mov     [rbp+3Fh+ppv], rax
0x180003a01  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x180003a08  call    cs:__imp_SHCreateDefaultExtractIcon
0x180003a0e  mov     ebx, eax
0x180003a10  test    eax, eax
0x180003a12  js      short loc_180003A92
0x180003a14  mov     rcx, [rbp+3Fh+ppv]
0x180003a18  mov     edx, 2
0x180003a1d  mov     rax, [rcx]
0x180003a20  mov     rax, [rax+18h]
0x180003a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a29  mov     ebx, eax
0x180003a2b  test    eax, eax
0x180003a2d  js      short loc_180003A82
0x180003a2f  mov     rdx, [rsi]; struct _ITEMIDLIST_RELATIVE *
0x180003a32  call    ?_IsComputer@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CNetworkExplorerFolder::_IsComputer(_ITEMIDLIST_RELATIVE const *)
0x180003a37  mov     rdx, [rsi]; struct _ITEMID_CHILD *
0x180003a3a  test    eax, eax
0x180003a3c  jz      loc_180003B9F
0x180003a42  call    ?_IsTree@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CNetworkExplorerFolder::_IsTree(_ITEMIDLIST_RELATIVE const *)
0x180003a47  mov     rcx, [rbp+3Fh+ppv]
0x180003a4b  xor     edx, edx
0x180003a4d  test    eax, eax
0x180003a4f  mov     rax, [rcx]
0x180003a52  mov     rax, [rax+28h]
0x180003a56  jnz     loc_180003B08
0x180003a5c  lea     r8d, [rdx+0Fh]
0x180003a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a65  mov     ebx, eax
0x180003a67  test    eax, eax
0x180003a69  js      short loc_180003A82
0x180003a6b  mov     rcx, [rbp+3Fh+ppv]
0x180003a6f  mov     r8, r12
0x180003a72  mov     rdx, rdi
0x180003a75  mov     rax, [rcx]
0x180003a78  mov     rax, [rax]
0x180003a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a80  mov     ebx, eax
0x180003a82  mov     rcx, [rbp+3Fh+ppv]
0x180003a86  mov     rax, [rcx]
0x180003a89  mov     rax, [rax+10h]
0x180003a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a92  mov     eax, ebx
0x180003a94  lea     r11, [rsp+0C0h+var_20]
0x180003a9c  mov     rbx, [r11+30h]
0x180003aa0  mov     rsi, [r11+38h]
0x180003aa4  mov     rsp, r11
0x180003aa7  pop     r15
0x180003aa9  pop     r14
0x180003aab  pop     r12
0x180003aad  pop     rdi
0x180003aae  pop     rbp
0x180003aaf  retn
0x180003ab0  mov     rax, [rdi]
0x180003ab3  mov     ebx, 80004002h
0x180003ab8  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180003abf  jnz     short loc_180003ACC
0x180003ac1  mov     rax, [rdi+8]
0x180003ac5  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180003acc  test    rax, rax
0x180003acf  jnz     short loc_180003A92
0x180003ad1  lea     ebx, [rax+1]
0x180003ad4  cmp     r14d, ebx
0x180003ad7  jz      loc_180003C69
0x180003add  test    r14d, r14d
0x180003ae0  jz      loc_180003C7C
0x180003ae6  xor     r15d, r15d
0x180003ae9  cmp     r15d, r14d
0x180003aec  jnb     loc_180003C65
0x180003af2  mov     rdx, [rsi+r15*8]; struct _ITEMIDLIST_RELATIVE *
0x180003af6  call    ?_IsComputer@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CNetworkExplorerFolder::_IsComputer(_ITEMIDLIST_RELATIVE const *)
0x180003afb  test    eax, eax
0x180003afd  jz      loc_180003C63
0x180003b03  add     r15d, ebx
0x180003b06  jmp     short loc_180003AE9
0x180003b08  mov     r8d, 29h ; ')'
0x180003b0e  jmp     loc_180003A60
0x180003b13  mov     rcx, [rcx+48h]; pidlFolder
0x180003b17  xor     r9d, r9d; pdtInner
0x180003b1a  mov     [rsp+0C0h+var_98], r12; ppv
0x180003b1f  mov     r8, rsi; apidl
0x180003b22  mov     edx, r14d; cidl
0x180003b25  mov     [rsp+0C0h+riid], rdi; riid
0x180003b2a  call    cs:__imp_SHCreateDataObject
0x180003b30  mov     ebx, eax
0x180003b32  jmp     loc_180003A92
0x180003b37  mov     eax, 80070057h
0x180003b3c  jmp     loc_180003A94
0x180003b41  lea     rax, [rcx-20h]
0x180003b45  mov     [rbp+3Fh+pdcm.hwnd], rdx
0x180003b49  test    rax, rax
0x180003b4c  jz      short loc_180003B64
0x180003b4e  lea     rax, [rcx+10h]
0x180003b52  mov     [rbp+3Fh+pdcm.pidlFolder], 0
0x180003b5a  mov     [rbp+3Fh+pdcm.pcmcb], rax
0x180003b5e  mov     [rbp+3Fh+pdcm.psf], rcx
0x180003b62  jmp     short loc_180003B74
0x180003b64  xorps   xmm0, xmm0
0x180003b67  mov     [rbp+3Fh+pdcm.pcmcb], 0
0x180003b6f  movdqa  xmmword ptr [rbp+3Fh+pdcm.pidlFolder], xmm0
0x180003b74  xor     eax, eax
0x180003b76  mov     [rbp+3Fh+pdcm.cidl], r14d
0x180003b7a  mov     r8, r12; ppv
0x180003b7d  mov     dword ptr [rbp+3Fh+pdcm+24h], eax
0x180003b80  mov     rdx, rdi; riid
0x180003b83  mov     [rbp+3Fh+pdcm.punkAssociationInfo], rax
0x180003b87  lea     rcx, [rbp+3Fh+pdcm]; pdcm
0x180003b8b  mov     qword ptr [rbp+3Fh+pdcm.cKeys], rax
0x180003b8f  mov     [rbp+3Fh+pdcm.aKeys], rax
0x180003b93  mov     [rbp+3Fh+pdcm.apidl], rsi
0x180003b97  call    cs:__imp_SHCreateDefaultContextMenu
0x180003b9d  jmp     short loc_180003B30
0x180003b9f  lea     r8, [rbp+3Fh+hKey]; HKEY *
0x180003ba3  mov     [rbp+3Fh+hKey], 0
0x180003bab  call    ?_OpenHKeyForItemIcon@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAUHKEY__@@@Z; CNetworkExplorerFolder::_OpenHKeyForItemIcon(_ITEMID_CHILD const *,HKEY__ * *)
0x180003bb0  test    eax, eax
0x180003bb2  js      short loc_180003BD6
0x180003bb4  mov     rcx, [rbp+3Fh+ppv]
0x180003bb8  mov     rdx, [rbp+3Fh+hKey]
0x180003bbc  mov     rax, [rcx]
0x180003bbf  mov     rax, [rax+20h]
0x180003bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bc8  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180003bcc  mov     ebx, eax
0x180003bce  call    cs:__imp_RegCloseKey
0x180003bd4  jmp     short loc_180003C3E
0x180003bd6  mov     rcx, [rsi]
0x180003bd9  lea     r8, [rbp+3Fh+pvar]
0x180003bdd  xorps   xmm0, xmm0
0x180003be0  lea     rdx, PKEY_PNPX_DeviceCategory
0x180003be7  xor     eax, eax
0x180003be9  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x180003bed  mov     qword ptr [rbp+3Fh+pvar+10h], rax
0x180003bf1  call    ?GetPropertyFromIDList@?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<DSPROFILEITEM,999534523>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x180003bf6  test    eax, eax
0x180003bf8  js      short loc_180003C46
0x180003bfa  lea     rdx, [rbp+3Fh+hKey]; int *
0x180003bfe  mov     dword ptr [rbp+3Fh+hKey], 0
0x180003c05  lea     rcx, [rbp+3Fh+pvar]; struct tagPROPVARIANT *
0x180003c09  call    ?GetIconFromDeviceCategory@@YAJAEBUtagPROPVARIANT@@PEAH@Z; GetIconFromDeviceCategory(tagPROPVARIANT const &,int *)
0x180003c0e  mov     ebx, eax
0x180003c10  test    eax, eax
0x180003c12  js      short loc_180003C34
0x180003c14  mov     rcx, [rbp+3Fh+ppv]
0x180003c18  lea     rdx, aNetworkexplore_0; "networkexplorer.dll"
0x180003c1f  mov     r8d, dword ptr [rbp+3Fh+hKey]
0x180003c23  neg     r8d
0x180003c26  mov     rax, [rcx]
0x180003c29  mov     rax, [rax+28h]
0x180003c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c32  mov     ebx, eax
0x180003c34  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180003c38  call    cs:__imp_PropVariantClear
0x180003c3e  test    ebx, ebx
0x180003c40  jns     loc_180003A6B
0x180003c46  mov     rcx, [rbp+3Fh+ppv]
0x180003c4a  lea     rdx, aNetworkexplore_0; "networkexplorer.dll"
0x180003c51  mov     r8d, 0FFFFFF9Ah
0x180003c57  mov     rax, [rcx]
0x180003c5a  mov     rax, [rax+28h]
0x180003c5e  jmp     loc_180003A60
0x180003c63  xor     ebx, ebx
0x180003c65  test    ebx, ebx
0x180003c67  jz      short loc_180003C7C
0x180003c69  mov     rdx, [rsi]; struct _ITEMID_CHILD *
0x180003c6c  mov     r9, r12; void **
0x180003c6f  mov     r8, rdi; struct _GUID *
0x180003c72  call    ?_AssocCreate@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CNetworkExplorerFolder::_AssocCreate(_ITEMID_CHILD const *,_GUID const &,void * *)
0x180003c77  jmp     loc_180003B30
0x180003c7c  mov     ebx, 80070057h
0x180003c81  jmp     loc_180003A92
```
