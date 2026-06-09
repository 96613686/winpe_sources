# CARPFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x1800141b0`
- end: `0x18001445f`
- name: `?GetUIObjectOf@CARPFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `687`
- prototype: `__int64 __usercall@<rax>(CARPFolder *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, const struct _ITEMID_CHILD *const *@<r9>, IID *riid, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000791c`
- `0x18000b2dc`
- `0x180010c48`
- `0x180013e58`
- `0x1800141b0`
- `0x18001887c`
- `0x18001a738`
- `0x180059010`

## import_xrefs

- `PROPSYS!PropVariantToStringWithDefault` at `0x180014388`
- `PROPSYS!PropVariantToStringWithDefault` at `0x180014388`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800143ae`
- `PROPSYS!PropVariantToInt32WithDefault` at `0x1800143ae`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180014292`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180014292`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001443b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014445`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001443b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014445`

## string_xrefs

- `0x1800143f2`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CARPFolder::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        int a3,
        const struct _ITEMIDLIST_RELATIVE **a4,
        IID *riid,
        unsigned int *a6,
        void **ppv)
{
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int64 v13; // rdx
  CARPItemContextMenu *v15; // rax
  CARPItemContextMenu *v16; // rax
  CARPItemContextMenu *v17; // rsi
  __int64 v18; // rax
  const struct _ITEMIDLIST_RELATIVE *v19; // rcx
  const unsigned __int16 *v20; // rbx
  LONG v21; // r14d
  unsigned __int64 v22; // rdx
  char *v23; // rax
  _DWORD *v24; // rsi
  unsigned __int16 *v25; // rcx
  PROPVARIANT propvarIn[2]; // [rsp+30h] [rbp-71h] BYREF
  __int64 v28; // [rsp+40h] [rbp-61h]
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-59h] BYREF
  __int64 v30; // [rsp+58h] [rbp-49h]
  DEFCONTEXTMENU pdcm; // [rsp+60h] [rbp-41h] BYREF

  v10 = -2147467262;
  *ppv = 0;
  if ( a3 && a4 )
  {
    v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
      v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
    if ( v11 )
    {
      v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
        v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
      if ( v12 )
      {
        v18 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
          v18 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
        if ( !v18 && !(unsigned int)CARPFolder::_IsItemAppUpdatesFolder((CARPFolder *)this, *a4) )
          return (unsigned int)CARPFolder::_AssocCreate((CARPFolder *)this, riid, ppv);
      }
      else if ( a3 == 1 )
      {
        if ( (unsigned int)CARPFolder::_IsItemAppUpdatesFolder((CARPFolder *)this, *a4) )
        {
          pdcm.pidlFolder = this[15];
          pdcm.hwnd = a2;
          pdcm.pcmcb = 0;
          pdcm.psf = (IShellFolder *)this;
          *(_QWORD *)&pdcm.cidl = 1;
          pdcm.apidl = (LPCITEMIDLIST *)a4;
          memset(&pdcm.punkAssociationInfo, 0, 24);
          return (unsigned int)SHCreateDefaultContextMenu(&pdcm, riid, ppv);
        }
        v15 = (CARPItemContextMenu *)DirectUI::HAllocAndZero((DirectUI *)0x658, v13);
        if ( v15
          && (v16 = CARPItemContextMenu::CARPItemContextMenu(
                      v15,
                      a2,
                      (struct CARPFolder *)this,
                      (struct _ITEMIDLIST_ABSOLUTE *)this[15],
                      *a4),
              (v17 = v16) != 0) )
        {
          v10 = (**(__int64 (__fastcall ***)(CARPItemContextMenu *, IID *, void **))v16)(v16, riid, ppv);
          (*(void (__fastcall **)(CARPItemContextMenu *))(*(_QWORD *)v17 + 16LL))(v17);
        }
        else
        {
          *ppv = 0;
          return (unsigned int)-2147024882;
        }
      }
    }
    else
    {
      v19 = *a4;
      v28 = 0;
      v30 = 0;
      *(_OWORD *)propvarIn = 0;
      v20 = 0;
      v21 = 0;
      *(_OWORD *)pvar = 0;
      if ( (int)CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(v19, PKEY_IconPath, propvarIn) >= 0 )
      {
        v20 = PropVariantToStringWithDefault(propvarIn, 0);
        if ( (int)CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(*a4, PKEY_IconIndex, pvar) >= 0 )
          v21 = PropVariantToInt32WithDefault(pvar, 0);
      }
      v23 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x218, v22);
      v24 = v23;
      if ( v23 )
      {
        *((_DWORD *)v23 + 2) = 1;
        *(_QWORD *)v23 = &CARPExtractIcon::`vftable';
        v25 = (unsigned __int16 *)(v23 + 12);
        if ( v20 )
        {
          StringCchCopyW(v25, 0x104u, v20);
        }
        else
        {
          StringCchCopyW(v25, 0x104u, L"imageres.dll");
          v21 = -15;
        }
        v24[133] = v21;
        v10 = (**(__int64 (__fastcall ***)(_DWORD *, IID *, void **))v24)(v24, riid, ppv);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v24 + 16LL))(v24);
      }
      else
      {
        v10 = -2147024882;
      }
      PropVariantClear(propvarIn);
      PropVariantClear(pvar);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800141b0  push    rbp
0x1800141b2  push    rbx
0x1800141b3  push    rsi
0x1800141b4  push    rdi
0x1800141b5  push    r12
0x1800141b7  push    r14
0x1800141b9  push    r15
0x1800141bb  lea     rbp, [rsp-0Fh]
0x1800141c0  sub     rsp, 0B0h
0x1800141c7  mov     r15, [rbp+3Fh+ppv]
0x1800141cb  mov     rsi, r9
0x1800141ce  mov     r12, rdx
0x1800141d1  mov     r14, rcx
0x1800141d4  mov     ebx, 80004002h
0x1800141d9  mov     qword ptr [r15], 0
0x1800141e0  test    r8d, r8d
0x1800141e3  jz      loc_18001444B
0x1800141e9  test    r9, r9
0x1800141ec  jz      loc_18001444B
0x1800141f2  mov     rdi, [rbp+3Fh+riid]
0x1800141f6  mov     rax, [rdi]
0x1800141f9  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180014200  jnz     short loc_18001420D
0x180014202  mov     rax, [rdi+8]
0x180014206  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x18001420d  test    rax, rax
0x180014210  jz      loc_18001434E
0x180014216  mov     rax, [rdi]
0x180014219  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180014220  jnz     short loc_18001422D
0x180014222  mov     rax, [rdi+8]
0x180014226  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18001422d  test    rax, rax
0x180014230  jnz     loc_18001430B
0x180014236  cmp     r8d, 1
0x18001423a  jnz     loc_18001444B
0x180014240  mov     rdx, [r9]; struct _ITEMIDLIST_RELATIVE *
0x180014243  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x180014248  test    eax, eax
0x18001424a  jz      short loc_18001429F
0x18001424c  mov     rax, [r14+78h]
0x180014250  lea     rcx, [rbp+3Fh+pdcm]; pdcm
0x180014254  mov     r8, r15; ppv
0x180014257  mov     [rbp+3Fh+pdcm.pidlFolder], rax
0x18001425b  mov     rdx, rdi; riid
0x18001425e  mov     [rbp+3Fh+pdcm.hwnd], r12
0x180014262  mov     [rbp+3Fh+pdcm.pcmcb], 0
0x18001426a  mov     [rbp+3Fh+pdcm.psf], r14
0x18001426e  mov     qword ptr [rbp+3Fh+pdcm.cidl], 1
0x180014276  mov     [rbp+3Fh+pdcm.apidl], rsi
0x18001427a  mov     [rbp+3Fh+pdcm.punkAssociationInfo], 0
0x180014282  mov     qword ptr [rbp+3Fh+pdcm.cKeys], 0
0x18001428a  mov     [rbp+3Fh+pdcm.aKeys], 0
0x180014292  call    cs:__imp_SHCreateDefaultContextMenu
0x180014298  mov     ebx, eax
0x18001429a  jmp     loc_18001444B
0x18001429f  mov     ecx, 658h; this
0x1800142a4  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800142a9  test    rax, rax
0x1800142ac  jz      short loc_1800142FA
0x1800142ae  mov     rcx, [rsi]
0x1800142b1  mov     r8, r14; struct CARPFolder *
0x1800142b4  mov     r9, [r14+78h]; struct _ITEMIDLIST_ABSOLUTE *
0x1800142b8  mov     rdx, r12; HWND
0x1800142bb  mov     [rsp+0E0h+var_C0], rcx; struct _ITEMID_CHILD *
0x1800142c0  mov     rcx, rax; this
0x1800142c3  call    ??0CARPItemContextMenu@@QEAA@PEAUHWND__@@PEAVCARPFolder@@PEAU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@@Z; CARPItemContextMenu::CARPItemContextMenu(HWND__ *,CARPFolder *,_ITEMIDLIST_ABSOLUTE *,_ITEMID_CHILD const *)
0x1800142c8  mov     rsi, rax
0x1800142cb  test    rax, rax
0x1800142ce  jz      short loc_1800142FA
0x1800142d0  mov     rcx, [rax]
0x1800142d3  mov     r8, r15
0x1800142d6  mov     rdx, rdi
0x1800142d9  mov     rax, [rcx]
0x1800142dc  mov     rcx, rsi
0x1800142df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e4  mov     rcx, [rsi]
0x1800142e7  mov     ebx, eax
0x1800142e9  mov     rax, [rcx+10h]
0x1800142ed  mov     rcx, rsi
0x1800142f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142f5  jmp     loc_18001444B
0x1800142fa  mov     qword ptr [r15], 0
0x180014301  mov     ebx, 8007000Eh
0x180014306  jmp     loc_18001444B
0x18001430b  mov     rax, [rdi]
0x18001430e  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180014315  jnz     short loc_180014322
0x180014317  mov     rax, [rdi+8]
0x18001431b  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180014322  test    rax, rax
0x180014325  jnz     loc_18001444B
0x18001432b  mov     rdx, [r9]; struct _ITEMIDLIST_RELATIVE *
0x18001432e  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x180014333  test    eax, eax
0x180014335  jnz     loc_18001444B
0x18001433b  mov     r8, r15; void **
0x18001433e  mov     rdx, rdi; struct _GUID *
0x180014341  mov     rcx, r14; this
0x180014344  call    ?_AssocCreate@CARPFolder@@AEAAJAEBU_GUID@@PEAPEAX@Z; CARPFolder::_AssocCreate(_GUID const &,void * *)
0x180014349  jmp     loc_180014298
0x18001434e  mov     rcx, [r9]
0x180014351  lea     r8, [rbp+3Fh+propvarIn]
0x180014355  xor     eax, eax
0x180014357  lea     rdx, PKEY_IconPath
0x18001435e  xorps   xmm0, xmm0
0x180014361  mov     [rbp+3Fh+var_A0], rax
0x180014365  xorps   xmm1, xmm1
0x180014368  mov     [rbp+3Fh+var_88], rax
0x18001436c  movups  xmmword ptr [rbp+3Fh+propvarIn], xmm0
0x180014370  xor     ebx, ebx
0x180014372  xor     r14d, r14d
0x180014375  movups  xmmword ptr [rbp+3Fh+pvar], xmm1
0x180014379  call    ?GetPropertyFromIDList@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18001437e  test    eax, eax
0x180014380  js      short loc_1800143B7
0x180014382  xor     edx, edx; pszDefault
0x180014384  lea     rcx, [rbp+3Fh+propvarIn]; propvarIn
0x180014388  call    cs:__imp_PropVariantToStringWithDefault
0x18001438e  mov     rcx, [rsi]
0x180014391  lea     r8, [rbp+3Fh+pvar]
0x180014395  lea     rdx, PKEY_IconIndex
0x18001439c  mov     rbx, rax
0x18001439f  call    ?GetPropertyFromIDList@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x1800143a4  test    eax, eax
0x1800143a6  js      short loc_1800143B7
0x1800143a8  xor     edx, edx; lDefault
0x1800143aa  lea     rcx, [rbp+3Fh+pvar]; propvarIn
0x1800143ae  call    cs:__imp_PropVariantToInt32WithDefault
0x1800143b4  mov     r14d, eax
0x1800143b7  mov     ecx, 218h; this
0x1800143bc  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800143c1  mov     rsi, rax
0x1800143c4  test    rax, rax
0x1800143c7  jz      short loc_180014432
0x1800143c9  mov     dword ptr [rsi+8], 1
0x1800143d0  lea     rax, ??_7CARPExtractIcon@@6B@; const CARPExtractIcon::`vftable'
0x1800143d7  mov     [rsi], rax
0x1800143da  lea     rcx, [rsi+0Ch]; unsigned __int16 *
0x1800143de  mov     edx, 104h; unsigned __int64
0x1800143e3  test    rbx, rbx
0x1800143e6  jz      short loc_1800143F2
0x1800143e8  mov     r8, rbx; unsigned __int16 *
0x1800143eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800143f0  jmp     short loc_180014404
0x1800143f2  lea     r8, LibFileName; "imageres.dll"
0x1800143f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800143fe  mov     r14d, 0FFFFFFF1h
0x180014404  mov     [rsi+214h], r14d
0x18001440b  mov     r8, r15
0x18001440e  mov     rax, [rsi]
0x180014411  mov     rdx, rdi
0x180014414  mov     rcx, rsi
0x180014417  mov     rax, [rax]
0x18001441a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001441f  mov     ebx, eax
0x180014421  mov     rcx, rsi
0x180014424  mov     rax, [rsi]
0x180014427  mov     rax, [rax+10h]
0x18001442b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014430  jmp     short loc_180014437
0x180014432  mov     ebx, 8007000Eh
0x180014437  lea     rcx, [rbp+3Fh+propvarIn]; pvar
0x18001443b  call    cs:__imp_PropVariantClear
0x180014441  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180014445  call    cs:__imp_PropVariantClear
0x18001444b  mov     eax, ebx
0x18001444d  add     rsp, 0B0h
0x180014454  pop     r15
0x180014456  pop     r14
0x180014458  pop     r12
0x18001445a  pop     rdi
0x18001445b  pop     rsi
0x18001445c  pop     rbx
0x18001445d  pop     rbp
0x18001445e  retn
```
