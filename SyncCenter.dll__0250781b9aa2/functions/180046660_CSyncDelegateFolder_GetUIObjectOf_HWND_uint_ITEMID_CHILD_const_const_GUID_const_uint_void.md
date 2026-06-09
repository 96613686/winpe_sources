# CSyncDelegateFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180046660`
- end: `0x180046835`
- name: `?GetUIObjectOf@CSyncDelegateFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `469`
- prototype: `int(CSyncDelegateFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180024dd0`
- `0x180046660`
- `0x180046b9c`
- `0x180052950`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180046813`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180046813`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x1800466be`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x1800466be`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x18004676b`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x18004676b`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800466f1`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800466f1`

## pseudocode

```c
__int64 __fastcall CSyncDelegateFolder::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        IDataObject **ppdtobj)
{
  __int64 v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rax
  LPCITEMIDLIST *v16; // rcx
  DEFCONTEXTMENU pdcm; // [rsp+30h] [rbp-41h] BYREF

  *ppdtobj = 0;
  v8 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v8 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v8 )
    return (unsigned int)CIDLData_CreateFromIDArray(*(LPCITEMIDLIST *)(this + 40), a3, a4, ppdtobj);
  v10 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
    v10 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
  if ( !v10 )
  {
    SHStringFromGUIDW(this + 72, &pdcm, 39);
    return (unsigned int)AssocCreateForString((const unsigned __int16 *)&pdcm, riid, (void **)ppdtobj);
  }
  v11 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v11 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v11 )
  {
    pdcm.hwnd = a2;
    v16 = (LPCITEMIDLIST *)(this - 8);
    if ( v16 )
      pdcm.pcmcb = (IContextMenuCB *)(this + 48);
    else
      pdcm.pcmcb = 0;
    pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 40);
    memset(&pdcm.punkAssociationInfo, 0, 24);
    pdcm.psf = (IShellFolder *)(this & -(__int64)(v16 != 0));
    *(&pdcm.cidl + 1) = 0;
    pdcm.cidl = a3;
    pdcm.apidl = a4;
    return (unsigned int)SHCreateDefaultContextMenu(&pdcm, riid, (void **)ppdtobj);
  }
  v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryInfo.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1 )
    v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryInfo.Data4;
  if ( !v12 )
    return (unsigned int)CreateInfoTipFromItem2(
                           this & -(__int64)(this != 8),
                           *a4,
                           &PKEY_PropList_InfoTip,
                           0,
                           riid,
                           ppdtobj);
  v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
    v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
  if ( !v13 )
    return (unsigned int)CSyncDelegateFolder::_GetExtractIcon((CSyncDelegateFolder *)(this - 8), riid, (void **)ppdtobj);
  v14 = -2147467262;
  v15 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
  if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
    v15 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
  if ( !v15 )
    return (unsigned int)CSyncDelegateFolder::_GetExtractIcon((CSyncDelegateFolder *)(this - 8), riid, (void **)ppdtobj);
  return v14;
}

```

## disassembly

```asm
0x180046660  push    rbp
0x180046662  push    rbx
0x180046663  push    rsi
0x180046664  push    rdi
0x180046665  lea     rbp, [rsp-27h]
0x18004666a  sub     rsp, 98h
0x180046671  mov     rax, cs:__security_cookie
0x180046678  xor     rax, rsp
0x18004667b  mov     [rbp+3Fh+var_30], rax
0x18004667f  mov     rdi, [rbp+3Fh+ppdtobj]
0x180046683  mov     esi, r8d
0x180046686  mov     rbx, [rbp+3Fh+riid]
0x18004668a  xor     r8d, r8d
0x18004668d  mov     r11, r9
0x180046690  mov     r10, rcx
0x180046693  mov     [rdi], r8
0x180046696  mov     rax, [rbx]
0x180046699  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x1800466a0  jnz     short loc_1800466AD
0x1800466a2  mov     rax, [rbx+8]
0x1800466a6  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800466ad  test    rax, rax
0x1800466b0  jnz     short loc_1800466C9
0x1800466b2  mov     rcx, [rcx+28h]; pidlFolder
0x1800466b6  mov     r9, rdi; ppdtobj
0x1800466b9  mov     r8, r11; apidl
0x1800466bc  mov     edx, esi; cidl
0x1800466be  call    cs:__imp_CIDLData_CreateFromIDArray
0x1800466c4  jmp     loc_180046819
0x1800466c9  mov     rax, [rbx]
0x1800466cc  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x1800466d3  jnz     short loc_1800466E0
0x1800466d5  mov     rax, [rbx+8]
0x1800466d9  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x1800466e0  test    rax, rax
0x1800466e3  jnz     short loc_18004670B
0x1800466e5  add     rcx, 48h ; 'H'
0x1800466e9  lea     r8d, [rax+27h]
0x1800466ed  lea     rdx, [rbp+3Fh+pdcm]
0x1800466f1  call    cs:__imp_SHStringFromGUIDW
0x1800466f7  mov     r8, rdi; void **
0x1800466fa  lea     rcx, [rbp+3Fh+pdcm]; unsigned __int16 *
0x1800466fe  mov     rdx, rbx; struct _GUID *
0x180046701  call    ?AssocCreateForString@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; AssocCreateForString(ushort const *,_GUID const &,void * *)
0x180046706  jmp     loc_180046819
0x18004670b  mov     rax, [rbx]
0x18004670e  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180046715  jnz     short loc_180046722
0x180046717  mov     rax, [rbx+8]
0x18004671b  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180046722  test    rax, rax
0x180046725  jz      loc_1800467C4
0x18004672b  mov     rax, [rbx]
0x18004672e  sub     rax, qword ptr cs:IID_IQueryInfo.Data1
0x180046735  jnz     short loc_180046742
0x180046737  mov     rax, [rbx+8]
0x18004673b  sub     rax, qword ptr cs:IID_IQueryInfo.Data4
0x180046742  test    rax, rax
0x180046745  jnz     short loc_180046776
0x180046747  mov     rdx, [r11]
0x18004674a  lea     rax, [rcx-8]
0x18004674e  neg     rax
0x180046751  mov     [rsp+0B0h+var_88], rdi
0x180046756  lea     r8, PKEY_PropList_InfoTip
0x18004675d  mov     [rsp+0B0h+var_90], rbx
0x180046762  sbb     rcx, rcx
0x180046765  xor     r9d, r9d
0x180046768  and     rcx, r10
0x18004676b  call    cs:__imp_CreateInfoTipFromItem2
0x180046771  jmp     loc_180046819
0x180046776  mov     rax, [rbx]
0x180046779  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180046780  jnz     short loc_18004678D
0x180046782  mov     rax, [rbx+8]
0x180046786  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x18004678d  test    rax, rax
0x180046790  jz      short loc_1800467B3
0x180046792  mov     rax, [rbx]
0x180046795  mov     ecx, 80004002h
0x18004679a  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x1800467a1  jnz     short loc_1800467AE
0x1800467a3  mov     rax, [rbx+8]
0x1800467a7  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x1800467ae  test    rax, rax
0x1800467b1  jnz     short loc_18004681B
0x1800467b3  lea     rcx, [r10-8]; this
0x1800467b7  mov     r8, rdi; void **
0x1800467ba  mov     rdx, rbx; struct _GUID *
0x1800467bd  call    ?_GetExtractIcon@CSyncDelegateFolder@@AEAAJAEBU_GUID@@PEAPEAX@Z; CSyncDelegateFolder::_GetExtractIcon(_GUID const &,void * *)
0x1800467c2  jmp     short loc_180046819
0x1800467c4  mov     [rbp+3Fh+pdcm.hwnd], rdx
0x1800467c8  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800467cc  jz      short loc_1800467D8
0x1800467ce  lea     rax, [r10+30h]
0x1800467d2  mov     [rbp+3Fh+pdcm.pcmcb], rax
0x1800467d6  jmp     short loc_1800467DC
0x1800467d8  mov     [rbp+3Fh+pdcm.pcmcb], r8
0x1800467dc  mov     rax, [r10+28h]
0x1800467e0  neg     rcx
0x1800467e3  mov     [rbp+3Fh+pdcm.pidlFolder], rax
0x1800467e7  lea     rcx, [rbp+3Fh+pdcm]; pdcm
0x1800467eb  sbb     rax, rax
0x1800467ee  mov     [rbp+3Fh+pdcm.punkAssociationInfo], r8
0x1800467f2  and     rax, r10
0x1800467f5  mov     qword ptr [rbp+3Fh+pdcm.cKeys], r8
0x1800467f9  mov     [rbp+3Fh+pdcm.psf], rax
0x1800467fd  mov     rdx, rbx; riid
0x180046800  xor     eax, eax
0x180046802  mov     [rbp+3Fh+pdcm.aKeys], r8
0x180046806  mov     r8, rdi; ppv
0x180046809  mov     dword ptr [rbp+3Fh+pdcm+24h], eax
0x18004680c  mov     [rbp+3Fh+pdcm.cidl], esi
0x18004680f  mov     [rbp+3Fh+pdcm.apidl], r11
0x180046813  call    cs:__imp_SHCreateDefaultContextMenu
0x180046819  mov     ecx, eax
0x18004681b  mov     eax, ecx
0x18004681d  mov     rcx, [rbp+3Fh+var_30]
0x180046821  xor     rcx, rsp; StackCookie
0x180046824  call    __security_check_cookie
0x180046829  add     rsp, 98h
0x180046830  pop     rdi
0x180046831  pop     rsi
0x180046832  pop     rbx
0x180046833  pop     rbp
0x180046834  retn
```
