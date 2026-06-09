# CHandlerFolderBase::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180041060`
- end: `0x1800412c6`
- name: `?GetUIObjectOf@CHandlerFolderBase@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `614`
- prototype: `int(CHandlerFolderBase *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002ef60`

## callees

- `0x180041060`
- `0x180041b08`
- `0x180042634`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x18004129c`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18004129c`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180041103`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180041103`

## pseudocode

```c
__int64 __fastcall CHandlerFolderBase::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        IDataObject **ppdtobj)
{
  CSyncFolderBase *v7; // r14
  int v11; // edi
  __int64 v12; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  LPCITEMIDLIST v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  HWND v22; // [rsp+38h] [rbp-C8h]
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v24[64]; // [rsp+90h] [rbp-70h] BYREF

  v7 = (CSyncFolderBase *)(this - 16);
  v22 = a2;
  *ppdtobj = 0;
  v11 = (*(__int64 (__fastcall **)(unsigned __int64, LPCITEMIDLIST, unsigned __int16 *, __int64))(*(_QWORD *)(this - 16)
                                                                                                + 264LL))(
          this - 16,
          *a4,
          v24,
          64);
  if ( v11 >= 0 )
  {
    v12 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
      v12 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
    if ( !v12 )
      return (unsigned int)CIDLData_CreateFromIDArray(*(LPCITEMIDLIST *)(this + 64), a3, a4, ppdtobj);
    v14 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
      v14 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
    if ( !v14 )
      return (unsigned int)CSyncFolderBase::AssocCreate(
                             v7,
                             (const struct _ITEMID_CHILD *)*a4,
                             a3,
                             *(_BYTE *)(this + 152),
                             riid,
                             (void **)ppdtobj);
    v15 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v15 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( !v15 )
    {
      pdcm.hwnd = v22;
      if ( v7 )
        pdcm.pcmcb = (IContextMenuCB *)(this + 88);
      else
        pdcm.pcmcb = 0;
      pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
      memset(&pdcm.punkAssociationInfo, 0, 24);
      pdcm.psf = (IShellFolder *)(this & -(__int64)(v7 != 0));
      *(&pdcm.cidl + 1) = 0;
      pdcm.cidl = a3;
      pdcm.apidl = a4;
      return (unsigned int)SHCreateDefaultContextMenu(&pdcm, riid, (void **)ppdtobj);
    }
    if ( a3 == 1 )
    {
      v16 = *(_QWORD *)this;
      v17 = *a4;
      v21 = 0;
      v11 = (*(__int64 (__fastcall **)(unsigned __int64, LPCITEMIDLIST, _QWORD, GUID *, __int64 *))(v16 + 40))(
              this,
              v17,
              0,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &v21);
      if ( v11 < 0
        || (v11 = (*(__int64 (__fastcall **)(__int64, HWND, const struct _GUID *, IDataObject **))(*(_QWORD *)v21 + 64LL))(
                    v21,
                    v22,
                    riid,
                    ppdtobj),
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21),
            v11 < 0) )
      {
        v18 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
          v18 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
        if ( !v18 )
          return (unsigned int)CSyncFolderBase::GetHandlerExtractIconInterface(v7, 0, v24, riid, (void **)ppdtobj);
        v19 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
          v19 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
        if ( !v19 )
          return (unsigned int)CSyncFolderBase::GetHandlerExtractIconInterface(v7, 0, v24, riid, (void **)ppdtobj);
      }
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180041060  push    rbp
0x180041062  push    rbx
0x180041063  push    rsi
0x180041064  push    rdi
0x180041065  push    r12
0x180041067  push    r13
0x180041069  push    r14
0x18004106b  push    r15
0x18004106d  lea     rbp, [rsp-28h]
0x180041072  sub     rsp, 128h
0x180041079  mov     rax, cs:__security_cookie
0x180041080  xor     rax, rsp
0x180041083  mov     [rbp+60h+var_50], rax
0x180041087  mov     r15, [rbp+60h+ppdtobj]
0x18004108e  lea     r14, [rcx-10h]
0x180041092  mov     rbx, [rbp+60h+riid]
0x180041099  mov     r13, r9
0x18004109c  mov     r12d, r8d
0x18004109f  mov     [rsp+160h+var_128], rdx
0x1800410a4  mov     rsi, rcx
0x1800410a7  lea     r8, [rbp+60h+var_D0]
0x1800410ab  mov     qword ptr [r15], 0
0x1800410b2  mov     r9d, 40h ; '@'
0x1800410b8  mov     rax, [r14]
0x1800410bb  mov     rcx, r14
0x1800410be  mov     rdx, [r13+0]
0x1800410c2  mov     rax, [rax+108h]
0x1800410c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800410ce  xor     ecx, ecx
0x1800410d0  mov     edi, eax
0x1800410d2  test    eax, eax
0x1800410d4  js      loc_1800412A4
0x1800410da  mov     rax, [rbx]
0x1800410dd  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x1800410e4  jnz     short loc_1800410F1
0x1800410e6  mov     rax, [rbx+8]
0x1800410ea  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800410f1  test    rax, rax
0x1800410f4  jnz     short loc_18004110E
0x1800410f6  mov     rcx, [rsi+40h]; pidlFolder
0x1800410fa  mov     r9, r15; ppdtobj
0x1800410fd  mov     r8, r13; apidl
0x180041100  mov     edx, r12d; cidl
0x180041103  call    cs:__imp_CIDLData_CreateFromIDArray
0x180041109  jmp     loc_1800412A2
0x18004110e  mov     rax, [rbx]
0x180041111  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180041118  jnz     short loc_180041125
0x18004111a  mov     rax, [rbx+8]
0x18004111e  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180041125  test    rax, rax
0x180041128  jnz     short loc_18004114F
0x18004112a  mov     r9b, [rsi+98h]; bool
0x180041131  mov     r8d, r12d; unsigned int
0x180041134  mov     rdx, [r13+0]; struct _ITEMID_CHILD *
0x180041138  mov     rcx, r14; this
0x18004113b  mov     [rsp+160h+var_138], r15; void **
0x180041140  mov     [rsp+160h+var_140], rbx; struct _GUID *
0x180041145  call    ?AssocCreate@CSyncFolderBase@@IEAAJPEFBU_ITEMID_CHILD@@I_NAEBU_GUID@@PEAPEAX@Z; CSyncFolderBase::AssocCreate(_ITEMID_CHILD const *,uint,bool,_GUID const &,void * *)
0x18004114a  jmp     loc_1800412A2
0x18004114f  mov     rax, [rbx]
0x180041152  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180041159  jnz     short loc_180041166
0x18004115b  mov     rax, [rbx+8]
0x18004115f  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180041166  test    rax, rax
0x180041169  jz      loc_18004123D
0x18004116f  cmp     r12d, 1
0x180041173  jnz     loc_180041236
0x180041179  mov     rax, [rsi]
0x18004117c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x180041183  mov     rdx, [r13+0]
0x180041187  xor     r8d, r8d
0x18004118a  mov     [rsp+160h+var_130], rcx
0x18004118f  lea     rcx, [rsp+160h+var_130]
0x180041194  mov     [rsp+160h+var_140], rcx
0x180041199  mov     rcx, rsi
0x18004119c  mov     rax, [rax+28h]
0x1800411a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411a5  mov     edi, eax
0x1800411a7  test    eax, eax
0x1800411a9  js      short loc_1800411E2
0x1800411ab  mov     rcx, [rsp+160h+var_130]
0x1800411b0  mov     r9, r15
0x1800411b3  mov     rdx, [rsp+160h+var_128]
0x1800411b8  mov     r8, rbx
0x1800411bb  mov     rax, [rcx]
0x1800411be  mov     rax, [rax+40h]
0x1800411c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411c7  mov     rcx, [rsp+160h+var_130]
0x1800411cc  mov     edi, eax
0x1800411ce  mov     rax, [rcx]
0x1800411d1  mov     rax, [rax+10h]
0x1800411d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411da  test    edi, edi
0x1800411dc  jns     loc_1800412A4
0x1800411e2  mov     rax, [rbx]
0x1800411e5  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x1800411ec  jnz     short loc_1800411F9
0x1800411ee  mov     rax, [rbx+8]
0x1800411f2  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x1800411f9  test    rax, rax
0x1800411fc  jz      short loc_18004121E
0x1800411fe  mov     rax, [rbx]
0x180041201  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180041208  jnz     short loc_180041215
0x18004120a  mov     rax, [rbx+8]
0x18004120e  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180041215  test    rax, rax
0x180041218  jnz     loc_1800412A4
0x18004121e  mov     r9, rbx; struct _GUID *
0x180041221  mov     [rsp+160h+var_140], r15; void **
0x180041226  lea     r8, [rbp+60h+var_D0]; unsigned __int16 *
0x18004122a  xor     edx, edx; struct _GUID *
0x18004122c  mov     rcx, r14; this
0x18004122f  call    ?GetHandlerExtractIconInterface@CSyncFolderBase@@IEAAJPEBU_GUID@@PEBGAEBU2@PEAPEAX@Z; CSyncFolderBase::GetHandlerExtractIconInterface(_GUID const *,ushort const *,_GUID const &,void * *)
0x180041234  jmp     short loc_1800412A2
0x180041236  mov     edi, 80004002h
0x18004123b  jmp     short loc_1800412A4
0x18004123d  mov     rdx, [rsp+160h+var_128]
0x180041242  mov     [rsp+160h+pdcm.hwnd], rdx
0x180041247  test    r14, r14
0x18004124a  jz      short loc_180041257
0x18004124c  lea     rax, [rsi+58h]
0x180041250  mov     [rsp+160h+pdcm.pcmcb], rax
0x180041255  jmp     short loc_18004125C
0x180041257  mov     [rsp+160h+pdcm.pcmcb], rcx
0x18004125c  mov     rax, [rsi+40h]
0x180041260  neg     r14
0x180041263  mov     [rsp+160h+pdcm.pidlFolder], rax
0x180041268  mov     r8, r15; ppv
0x18004126b  sbb     rax, rax
0x18004126e  mov     [rsp+160h+pdcm.punkAssociationInfo], rcx
0x180041273  and     rax, rsi
0x180041276  mov     qword ptr [rsp+160h+pdcm.cKeys], rcx
0x18004127b  mov     [rsp+160h+pdcm.psf], rax
0x180041280  mov     rdx, rbx; riid
0x180041283  xor     eax, eax
0x180041285  mov     [rbp+60h+pdcm.aKeys], rcx
0x180041289  lea     rcx, [rsp+160h+pdcm]; pdcm
0x18004128e  mov     dword ptr [rsp+160h+pdcm+24h], eax
0x180041292  mov     [rsp+160h+pdcm.cidl], r12d
0x180041297  mov     [rsp+160h+pdcm.apidl], r13
0x18004129c  call    cs:__imp_SHCreateDefaultContextMenu
0x1800412a2  mov     edi, eax
0x1800412a4  mov     eax, edi
0x1800412a6  mov     rcx, [rbp+60h+var_50]
0x1800412aa  xor     rcx, rsp; StackCookie
0x1800412ad  call    __security_check_cookie
0x1800412b2  add     rsp, 128h
0x1800412b9  pop     r15
0x1800412bb  pop     r14
0x1800412bd  pop     r13
0x1800412bf  pop     r12
0x1800412c1  pop     rdi
0x1800412c2  pop     rsi
0x1800412c3  pop     rbx
0x1800412c4  pop     rbp
0x1800412c5  retn
```
