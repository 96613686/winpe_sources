# CARPFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x1800136f0`
- end: `0x1800139e4`
- name: `?GetDetailsEx@CARPFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct IShellFolder2 *this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180007960`
- `0x180008cf8`
- `0x1800136f0`
- `0x180013e58`
- `0x180018744`
- `0x180019e50`
- `0x18001a738`
- `0x180044c08`
- `0x1800555dc`
- `0x1800582e0`

## import_xrefs

- `PROPSYS!PropVariantToVariant` at `0x1800139b0`
- `PROPSYS!PropVariantToVariant` at `0x1800139b0`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180013968`
- `SHELL32!AssocGetDetailsOfPropKey` at `0x180013968`
- `OLEAUT32!__imp_SysAllocString` at `0x1800138c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800138c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800138d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800139bd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800139bd`

## pseudocode

```c
__int64 __fastcall CARPFolder::GetDetailsEx(
        struct IShellFolder2 *this,
        const ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  DWORD pid; // ecx
  __int64 v9; // rax
  int v10; // eax
  int v11; // edx
  int DetailsOfPropKey; // ebx
  __int64 v13; // rax
  int IsItemAppUpdatesFolder; // eax
  int v15; // edx
  bool v16; // zf
  __int64 v17; // rax
  BOOL *pfFoundPropKey; // [rsp+20h] [rbp-E0h]
  BOOL v20; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  struct IShellFolder2 *v22; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pPropVar[3]; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR psz[256]; // [rsp+60h] [rbp-A0h] BYREF

  pid = a3->pid;
  if ( pid != 999 )
    goto LABEL_13;
  v9 = PKEY_Software_NullPreview_Title - *(_QWORD *)&a3->fmtid.Data1;
  if ( PKEY_Software_NullPreview_Title == *(_QWORD *)&a3->fmtid.Data1 )
    v9 = 0x6DB3FABF1BE84789LL - *(_QWORD *)a3->fmtid.Data4;
  if ( v9 )
  {
LABEL_13:
    if ( pid != 998 )
      goto LABEL_31;
    v13 = PKEY_Software_NullPreview_Subtitle - *(_QWORD *)&a3->fmtid.Data1;
    if ( PKEY_Software_NullPreview_Subtitle == *(_QWORD *)&a3->fmtid.Data1 )
      v13 = 0x6DB3FABF1BE84789LL - *(_QWORD *)a3->fmtid.Data4;
    if ( v13 )
    {
LABEL_31:
      if ( pid != 997 )
        goto LABEL_37;
      v17 = PKEY_Software_NullPreview_TotalSize - *(_QWORD *)&a3->fmtid.Data1;
      if ( PKEY_Software_NullPreview_TotalSize == *(_QWORD *)&a3->fmtid.Data1 )
        v17 = 0x6DB3FABF1BE84789LL - *(_QWORD *)a3->fmtid.Data4;
      if ( v17 )
      {
LABEL_37:
        v20 = 0;
        DetailsOfPropKey = AssocGetDetailsOfPropKey((IShellFolder *)this, a2, a3, a4, &v20);
        if ( DetailsOfPropKey < 0 && !v20 )
        {
          LOWORD(pPropVar[0]) = a4->vt;
          *(_OWORD *)((char *)pPropVar + 2) = 0;
          pPropVar[2] = 0;
          DetailsOfPropKey = CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(a2, a3, pPropVar);
          if ( DetailsOfPropKey >= 0 )
          {
            DetailsOfPropKey = PropVariantToVariant(pPropVar, a4);
            PropVariantClear(pPropVar);
          }
        }
      }
      else if ( LODWORD(this[16].lpVtbl)
             || (unsigned int)CARPFolder::_IsItemAppUpdatesFolder(
                                (CARPFolder *)this,
                                (const struct _ITEMIDLIST_RELATIVE *)a2) )
      {
        a4->vt = 0;
        return 0;
      }
      else
      {
        pv = 0;
        DetailsOfPropKey = CARPFolder::_AddupItemSize((CARPFolder *)this, (union _ULARGE_INTEGER *)&pv);
        if ( DetailsOfPropKey >= 0 )
        {
          a4->llVal = (LONGLONG)pv;
          a4->vt = 21;
        }
      }
    }
    else
    {
      if ( LODWORD(this[16].lpVtbl)
        || (IsItemAppUpdatesFolder = CARPFolder::_IsItemAppUpdatesFolder(
                                       (CARPFolder *)this,
                                       (const struct _ITEMIDLIST_RELATIVE *)a2),
            v15 = 201,
            IsItemAppUpdatesFolder) )
      {
        v15 = 203;
      }
      pv = 0;
      DetailsOfPropKey = TResourceStringAllocCopyEx<unsigned short *>(
                           (int)g_hinst,
                           v15,
                           (int)a3,
                           (int)ResourceStringAllocCopyExCoAlloc,
                           pfFoundPropKey,
                           &pv);
      if ( DetailsOfPropKey >= 0 )
      {
        v16 = LODWORD(this[16].lpVtbl) == 0;
        v20 = 0;
        if ( v16
          && (unsigned int)CARPFolder::_IsItemAppUpdatesFolder(
                             (CARPFolder *)this,
                             (const struct _ITEMIDLIST_RELATIVE *)a2) )
        {
          v22 = 0;
          DetailsOfPropKey = CARPFolder::_GetChildInstalledUpdates(
                               (CARPFolder *)this,
                               (const struct _ITEMIDLIST_RELATIVE *)a2,
                               &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                               (void **)&v22);
          if ( DetailsOfPropKey >= 0 )
            DetailsOfPropKey = CalcItemCount(v22, (unsigned int *)&v20);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
        }
        else
        {
          DetailsOfPropKey = CalcItemCount(this, (unsigned int *)&v20);
        }
        if ( DetailsOfPropKey >= 0 )
        {
          DetailsOfPropKey = StringCchPrintfW(psz, 0x100u, (const unsigned __int16 *)pv, v20);
          if ( DetailsOfPropKey >= 0 )
          {
            a4->vt = 8;
            a4->llVal = (LONGLONG)SysAllocString(psz);
          }
        }
        CoTaskMemFree(pv);
      }
    }
  }
  else
  {
    if ( LODWORD(this[16].lpVtbl)
      || (v10 = CARPFolder::_IsItemAppUpdatesFolder((CARPFolder *)this, (const struct _ITEMIDLIST_RELATIVE *)a2),
          v11 = 200,
          v10) )
    {
      v11 = 202;
    }
    pv = 0;
    DetailsOfPropKey = TResourceStringAllocCopyEx<unsigned short *>(
                         (int)g_hinst,
                         v11,
                         (int)a3,
                         (int)ResourceStringAllocCopyExSysAlloc,
                         pfFoundPropKey,
                         &pv);
    if ( DetailsOfPropKey >= 0 )
    {
      a4->llVal = (LONGLONG)pv;
      a4->vt = 8;
    }
  }
  return (unsigned int)DetailsOfPropKey;
}

```

## disassembly

```asm
0x1800136f0  push    rbp
0x1800136f2  push    rbx
0x1800136f3  push    rsi
0x1800136f4  push    rdi
0x1800136f5  push    r14
0x1800136f7  push    r15
0x1800136f9  lea     rbp, [rsp-178h]
0x180013701  sub     rsp, 278h
0x180013708  mov     rax, cs:__security_cookie
0x18001370f  xor     rax, rsp
0x180013712  mov     [rbp+1A0h+var_40], rax
0x180013719  mov     rdi, rcx
0x18001371c  mov     rsi, r9
0x18001371f  mov     ecx, [r8+10h]
0x180013723  mov     r14, r8
0x180013726  cmp     cs:dword_180062350, ecx
0x18001372c  mov     r15, rdx
0x18001372f  jnz     short loc_1800137AE
0x180013731  mov     rax, cs:PKEY_Software_NullPreview_Title
0x180013738  sub     rax, [r8]
0x18001373b  jnz     short loc_180013748
0x18001373d  mov     rax, cs:qword_180062348
0x180013744  sub     rax, [r8+8]
0x180013748  test    rax, rax
0x18001374b  jnz     short loc_1800137AE
0x18001374d  cmp     [rdi+80h], eax
0x180013753  jnz     short loc_180013766
0x180013755  mov     rcx, rdi; this
0x180013758  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x18001375d  mov     edx, 0C8h
0x180013762  test    eax, eax
0x180013764  jz      short loc_18001376B
0x180013766  mov     edx, 0CAh; int
0x18001376b  mov     rcx, cs:g_hinst; int
0x180013772  lea     rax, [rsp+2A0h+pv]
0x180013777  lea     r9, _ResourceStringAllocCopyExSysAlloc; int
0x18001377e  mov     [rsp+2A0h+var_278], rax; void *
0x180013783  mov     [rsp+2A0h+pv], 0
0x18001378c  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180013791  mov     ebx, eax
0x180013793  test    eax, eax
0x180013795  js      loc_1800139C3
0x18001379b  mov     rcx, [rsp+2A0h+pv]
0x1800137a0  mov     [rsi+8], rcx
0x1800137a4  mov     word ptr [rsi], 8
0x1800137a9  jmp     loc_1800139C3
0x1800137ae  cmp     cs:dword_180062338, ecx
0x1800137b4  jnz     loc_1800138E1
0x1800137ba  mov     rax, cs:PKEY_Software_NullPreview_Subtitle
0x1800137c1  sub     rax, [r8]
0x1800137c4  jnz     short loc_1800137D1
0x1800137c6  mov     rax, cs:qword_180062330
0x1800137cd  sub     rax, [r8+8]
0x1800137d1  test    rax, rax
0x1800137d4  jnz     loc_1800138E1
0x1800137da  cmp     [rdi+80h], eax
0x1800137e0  jnz     short loc_1800137F3
0x1800137e2  mov     rcx, rdi; this
0x1800137e5  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x1800137ea  mov     edx, 0C9h
0x1800137ef  test    eax, eax
0x1800137f1  jz      short loc_1800137F8
0x1800137f3  mov     edx, 0CBh; int
0x1800137f8  mov     rcx, cs:g_hinst; int
0x1800137ff  lea     rax, [rsp+2A0h+pv]
0x180013804  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18001380b  mov     [rsp+2A0h+var_278], rax; void *
0x180013810  mov     [rsp+2A0h+pv], 0
0x180013819  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18001381e  mov     ebx, eax
0x180013820  test    eax, eax
0x180013822  js      loc_1800139C3
0x180013828  cmp     dword ptr [rdi+80h], 0
0x18001382f  mov     [rsp+2A0h+var_270], 0
0x180013837  jnz     short loc_18001388B
0x180013839  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18001383c  mov     rcx, rdi; this
0x18001383f  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x180013844  test    eax, eax
0x180013846  jz      short loc_18001388B
0x180013848  lea     r9, [rsp+2A0h+var_260]; void **
0x18001384d  mov     [rsp+2A0h+var_260], 0
0x180013856  lea     r8, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; struct _GUID *
0x18001385d  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x180013860  mov     rcx, rdi; this
0x180013863  call    ?_GetChildInstalledUpdates@CARPFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CARPFolder::_GetChildInstalledUpdates(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x180013868  mov     ebx, eax
0x18001386a  test    eax, eax
0x18001386c  js      short loc_18001387F
0x18001386e  mov     rcx, [rsp+2A0h+var_260]; struct IShellFolder2 *
0x180013873  lea     rdx, [rsp+2A0h+var_270]; unsigned int *
0x180013878  call    ?CalcItemCount@@YAJPEAUIShellFolder2@@PEAI@Z; CalcItemCount(IShellFolder2 *,uint *)
0x18001387d  mov     ebx, eax
0x18001387f  lea     rcx, [rsp+2A0h+var_260]
0x180013884  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013889  jmp     short loc_18001389A
0x18001388b  lea     rdx, [rsp+2A0h+var_270]; unsigned int *
0x180013890  mov     rcx, rdi; struct IShellFolder2 *
0x180013893  call    ?CalcItemCount@@YAJPEAUIShellFolder2@@PEAI@Z; CalcItemCount(IShellFolder2 *,uint *)
0x180013898  mov     ebx, eax
0x18001389a  test    ebx, ebx
0x18001389c  js      short loc_1800138D1
0x18001389e  mov     r9d, [rsp+2A0h+var_270]
0x1800138a3  lea     rcx, [rsp+2A0h+psz]; unsigned __int16 *
0x1800138a8  mov     r8, [rsp+2A0h+pv]; unsigned __int16 *
0x1800138ad  mov     edx, 100h; unsigned __int64
0x1800138b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800138b7  mov     ebx, eax
0x1800138b9  test    eax, eax
0x1800138bb  js      short loc_1800138D1
0x1800138bd  lea     rcx, [rsp+2A0h+psz]; psz
0x1800138c2  mov     word ptr [rsi], 8
0x1800138c7  call    cs:__imp_SysAllocString
0x1800138cd  mov     [rsi+8], rax
0x1800138d1  mov     rcx, [rsp+2A0h+pv]; pv
0x1800138d6  call    cs:__imp_CoTaskMemFree
0x1800138dc  jmp     loc_1800139C3
0x1800138e1  cmp     cs:dword_180062368, ecx
0x1800138e7  jnz     short loc_180013953
0x1800138e9  mov     rax, cs:PKEY_Software_NullPreview_TotalSize
0x1800138f0  sub     rax, [r8]
0x1800138f3  jnz     short loc_180013900
0x1800138f5  mov     rax, cs:qword_180062360
0x1800138fc  sub     rax, [r8+8]
0x180013900  test    rax, rax
0x180013903  jnz     short loc_180013953
0x180013905  cmp     [rdi+80h], eax
0x18001390b  jnz     short loc_180013949
0x18001390d  mov     rcx, rdi; this
0x180013910  call    ?_IsItemAppUpdatesFolder@CARPFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; CARPFolder::_IsItemAppUpdatesFolder(_ITEMIDLIST_RELATIVE const *)
0x180013915  test    eax, eax
0x180013917  jnz     short loc_180013949
0x180013919  lea     rdx, [rsp+2A0h+pv]; union _ULARGE_INTEGER *
0x18001391e  mov     [rsp+2A0h+pv], 0
0x180013927  mov     rcx, rdi; this
0x18001392a  call    ?_AddupItemSize@CARPFolder@@AEAAJPEAT_ULARGE_INTEGER@@@Z; CARPFolder::_AddupItemSize(_ULARGE_INTEGER *)
0x18001392f  mov     ebx, eax
0x180013931  test    eax, eax
0x180013933  js      loc_1800139C3
0x180013939  mov     rax, [rsp+2A0h+pv]
0x18001393e  mov     [rsi+8], rax
0x180013942  mov     word ptr [rsi], 15h
0x180013947  jmp     short loc_1800139C3
0x180013949  xor     eax, eax
0x18001394b  mov     [r9], ax
0x18001394f  xor     ebx, ebx
0x180013951  jmp     short loc_1800139C3
0x180013953  lea     rax, [rsp+2A0h+var_270]
0x180013958  mov     [rsp+2A0h+var_270], 0
0x180013960  mov     rcx, rdi; psf
0x180013963  mov     [rsp+2A0h+pfFoundPropKey], rax; pfFoundPropKey
0x180013968  call    cs:__imp_AssocGetDetailsOfPropKey
0x18001396e  mov     ebx, eax
0x180013970  test    eax, eax
0x180013972  jns     short loc_1800139C3
0x180013974  cmp     [rsp+2A0h+var_270], 0
0x180013979  jnz     short loc_1800139C3
0x18001397b  movzx   eax, word ptr [rsi]
0x18001397e  lea     r8, [rsp+2A0h+pPropVar]
0x180013983  mov     word ptr [rsp+2A0h+pPropVar], ax
0x180013988  xorps   xmm0, xmm0
0x18001398b  xor     eax, eax
0x18001398d  mov     rdx, r14
0x180013990  movups  xmmword ptr [rsp+2A0h+pPropVar+2], xmm0
0x180013995  mov     rcx, r15
0x180013998  mov     qword ptr [rsp+2A0h+pPropVar+10h], rax
0x18001399d  call    ?GetPropertyFromIDList@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<tagARPITEM,1230000705>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x1800139a2  mov     ebx, eax
0x1800139a4  test    eax, eax
0x1800139a6  js      short loc_1800139C3
0x1800139a8  mov     rdx, rsi; pVar
0x1800139ab  lea     rcx, [rsp+2A0h+pPropVar]; pPropVar
0x1800139b0  call    cs:__imp_PropVariantToVariant
0x1800139b6  lea     rcx, [rsp+2A0h+pPropVar]; pvar
0x1800139bb  mov     ebx, eax
0x1800139bd  call    cs:__imp_PropVariantClear
0x1800139c3  mov     eax, ebx
0x1800139c5  mov     rcx, [rbp+1A0h+var_40]
0x1800139cc  xor     rcx, rsp; StackCookie
0x1800139cf  call    __security_check_cookie
0x1800139d4  add     rsp, 278h
0x1800139db  pop     r15
0x1800139dd  pop     r14
0x1800139df  pop     rdi
0x1800139e0  pop     rsi
0x1800139e1  pop     rbx
0x1800139e2  pop     rbp
0x1800139e3  retn
```
