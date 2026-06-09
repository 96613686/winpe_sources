# CSyncHandlerFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180044be0`
- end: `0x180044e3a`
- name: `?GetUIObjectOf@CSyncHandlerFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `602`
- prototype: `int(CSyncHandlerFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180041b08`
- `0x180042908`
- `0x180044be0`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180044e14`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180044e14`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180044c7e`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180044c7e`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x180044d21`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x180044d21`

## pseudocode

```c
int __fastcall CSyncHandlerFolder::GetUIObjectOf(
        unsigned __int64 this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppdtobj)
{
  CSyncFolderBase *v7; // rsi
  int result; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  DEFCONTEXTMENU pdcm; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v20[64]; // [rsp+80h] [rbp-80h] BYREF

  v7 = (CSyncFolderBase *)(this - 16);
  *ppdtobj = 0;
  result = (*(__int64 (__fastcall **)(unsigned __int64, LPCITEMIDLIST, unsigned __int16 *, __int64))(*(_QWORD *)(this - 16) + 264LL))(
             this - 16,
             *a4,
             v20,
             64);
  if ( result >= 0 )
  {
    v13 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
    if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
      v13 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IDataObject.Data4;
    if ( v13 )
    {
      v14 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryAssociations.Data1;
      if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryAssociations.Data1 )
        v14 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryAssociations.Data4;
      if ( v14 )
      {
        v15 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
        if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
          v15 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
        if ( v15 )
        {
          v16 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IQueryInfo.Data1;
          if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IQueryInfo.Data1 )
            v16 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IQueryInfo.Data4;
          if ( v16 )
          {
            result = -2147467262;
            if ( a3 == 1 )
            {
              v17 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
              if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
                v17 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
              if ( !v17 )
                goto LABEL_24;
              v18 = *(_QWORD *)&riid->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
              if ( *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
                v18 = *(_QWORD *)riid->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
              if ( !v18 )
              {
LABEL_24:
                result = CSyncFolderBase::GetItemExtractIconInterface(
                           v7,
                           (const struct _GUID *)(this + 172),
                           (const unsigned __int16 *)(this + 188),
                           v20,
                           riid,
                           ppdtobj);
                if ( result < 0 )
                  return (*(__int64 (__fastcall **)(unsigned __int64, HWND, const struct _GUID *, void **))(*(_QWORD *)this + 64LL))(
                           this,
                           a2,
                           riid,
                           ppdtobj);
              }
            }
          }
          else
          {
            return CreateInfoTipFromItem2(this & -(__int64)(v7 != 0), *a4, &PKEY_PropList_InfoTip, 0, riid, ppdtobj);
          }
        }
        else
        {
          pdcm.hwnd = a2;
          if ( v7 )
            pdcm.pcmcb = (IContextMenuCB *)(this + 88);
          else
            pdcm.pcmcb = 0;
          pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
          memset(&pdcm.punkAssociationInfo, 0, 24);
          pdcm.psf = (IShellFolder *)(this & -(__int64)(v7 != 0));
          pdcm.cidl = a3;
          *(&pdcm.cidl + 1) = 0;
          pdcm.apidl = a4;
          return SHCreateDefaultContextMenu(&pdcm, riid, ppdtobj);
        }
      }
      else
      {
        return CSyncFolderBase::AssocCreate(v7, (const struct _ITEMID_CHILD *)*a4, a3, 0, riid, ppdtobj);
      }
    }
    else
    {
      return CIDLData_CreateFromIDArray(*(LPCITEMIDLIST *)(this + 64), a3, a4, (IDataObject **)ppdtobj);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180044be0  push    rbp
0x180044be2  push    rbx
0x180044be3  push    rsi
0x180044be4  push    rdi
0x180044be5  push    r12
0x180044be7  push    r13
0x180044be9  push    r14
0x180044beb  push    r15
0x180044bed  lea     rbp, [rsp-18h]
0x180044bf2  sub     rsp, 118h
0x180044bf9  mov     rax, cs:__security_cookie
0x180044c00  xor     rax, rsp
0x180044c03  mov     [rbp+50h+var_50], rax
0x180044c07  mov     r14, [rbp+50h+ppdtobj]
0x180044c0e  lea     rsi, [rcx-10h]
0x180044c12  mov     rbx, [rbp+50h+riid]
0x180044c19  mov     r15, r9
0x180044c1c  mov     r12d, r8d
0x180044c1f  mov     r13, rdx
0x180044c22  mov     rdi, rcx
0x180044c25  lea     r8, [rbp+50h+var_D0]
0x180044c29  mov     qword ptr [r14], 0
0x180044c30  mov     r9d, 40h ; '@'
0x180044c36  mov     rax, [rsi]
0x180044c39  mov     rcx, rsi
0x180044c3c  mov     rdx, [r15]
0x180044c3f  mov     rax, [rax+108h]
0x180044c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c4b  xor     edx, edx
0x180044c4d  test    eax, eax
0x180044c4f  js      loc_180044E1A
0x180044c55  mov     rax, [rbx]
0x180044c58  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180044c5f  jnz     short loc_180044C6C
0x180044c61  mov     rax, [rbx+8]
0x180044c65  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180044c6c  test    rax, rax
0x180044c6f  jnz     short loc_180044C89
0x180044c71  mov     rcx, [rdi+40h]; pidlFolder
0x180044c75  mov     r9, r14; ppdtobj
0x180044c78  mov     r8, r15; apidl
0x180044c7b  mov     edx, r12d; cidl
0x180044c7e  call    cs:__imp_CIDLData_CreateFromIDArray
0x180044c84  jmp     loc_180044E1A
0x180044c89  mov     rax, [rbx]
0x180044c8c  sub     rax, qword ptr cs:IID_IQueryAssociations.Data1
0x180044c93  jnz     short loc_180044CA0
0x180044c95  mov     rax, [rbx+8]
0x180044c99  sub     rax, qword ptr cs:IID_IQueryAssociations.Data4
0x180044ca0  test    rax, rax
0x180044ca3  jnz     short loc_180044CC5
0x180044ca5  mov     rdx, [r15]; struct _ITEMID_CHILD *
0x180044ca8  xor     r9d, r9d; bool
0x180044cab  mov     [rsp+150h+var_128], r14; void **
0x180044cb0  mov     r8d, r12d; unsigned int
0x180044cb3  mov     rcx, rsi; this
0x180044cb6  mov     [rsp+150h+var_130], rbx; struct _GUID *
0x180044cbb  call    ?AssocCreate@CSyncFolderBase@@IEAAJPEFBU_ITEMID_CHILD@@I_NAEBU_GUID@@PEAPEAX@Z; CSyncFolderBase::AssocCreate(_ITEMID_CHILD const *,uint,bool,_GUID const &,void * *)
0x180044cc0  jmp     loc_180044E1A
0x180044cc5  mov     rax, [rbx]
0x180044cc8  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180044ccf  jnz     short loc_180044CDC
0x180044cd1  mov     rax, [rbx+8]
0x180044cd5  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180044cdc  test    rax, rax
0x180044cdf  jz      loc_180044DB9
0x180044ce5  mov     rax, [rbx]
0x180044ce8  sub     rax, qword ptr cs:IID_IQueryInfo.Data1
0x180044cef  jnz     short loc_180044CFC
0x180044cf1  mov     rax, [rbx+8]
0x180044cf5  sub     rax, qword ptr cs:IID_IQueryInfo.Data4
0x180044cfc  test    rax, rax
0x180044cff  jnz     short loc_180044D2C
0x180044d01  mov     rdx, [r15]
0x180044d04  lea     r8, PKEY_PropList_InfoTip
0x180044d0b  neg     rsi
0x180044d0e  mov     [rsp+150h+var_128], r14
0x180044d13  mov     [rsp+150h+var_130], rbx
0x180044d18  sbb     rcx, rcx
0x180044d1b  xor     r9d, r9d
0x180044d1e  and     rcx, rdi
0x180044d21  call    cs:__imp_CreateInfoTipFromItem2
0x180044d27  jmp     loc_180044E1A
0x180044d2c  mov     eax, 80004002h
0x180044d31  cmp     r12d, 1
0x180044d35  jnz     loc_180044E1A
0x180044d3b  mov     rcx, [rbx]
0x180044d3e  sub     rcx, qword ptr cs:IID_IExtractIconA.Data1
0x180044d45  jnz     short loc_180044D52
0x180044d47  mov     rcx, [rbx+8]
0x180044d4b  sub     rcx, qword ptr cs:IID_IExtractIconA.Data4
0x180044d52  test    rcx, rcx
0x180044d55  jz      short loc_180044D77
0x180044d57  mov     rcx, [rbx]
0x180044d5a  sub     rcx, qword ptr cs:IID_IExtractIconW.Data1
0x180044d61  jnz     short loc_180044D6E
0x180044d63  mov     rcx, [rbx+8]
0x180044d67  sub     rcx, qword ptr cs:IID_IExtractIconW.Data4
0x180044d6e  test    rcx, rcx
0x180044d71  jnz     loc_180044E1A
0x180044d77  lea     r8, [rdi+0BCh]; unsigned __int16 *
0x180044d7e  mov     [rsp+150h+var_128], r14; void **
0x180044d83  lea     rdx, [rdi+0ACh]; struct _GUID *
0x180044d8a  mov     [rsp+150h+var_130], rbx; struct _GUID *
0x180044d8f  lea     r9, [rbp+50h+var_D0]; unsigned __int16 *
0x180044d93  mov     rcx, rsi; this
0x180044d96  call    ?GetItemExtractIconInterface@CSyncFolderBase@@IEAAJAEBU_GUID@@PEBG10PEAPEAX@Z; CSyncFolderBase::GetItemExtractIconInterface(_GUID const &,ushort const *,ushort const *,_GUID const &,void * *)
0x180044d9b  test    eax, eax
0x180044d9d  jns     short loc_180044E1A
0x180044d9f  mov     rax, [rdi]
0x180044da2  mov     r9, r14
0x180044da5  mov     r8, rbx
0x180044da8  mov     rdx, r13
0x180044dab  mov     rcx, rdi
0x180044dae  mov     rax, [rax+40h]
0x180044db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044db7  jmp     short loc_180044E1A
0x180044db9  mov     [rsp+150h+pdcm.hwnd], r13
0x180044dbe  test    rsi, rsi
0x180044dc1  jz      short loc_180044DCE
0x180044dc3  lea     rax, [rdi+58h]
0x180044dc7  mov     [rsp+150h+pdcm.pcmcb], rax
0x180044dcc  jmp     short loc_180044DD3
0x180044dce  mov     [rsp+150h+pdcm.pcmcb], rdx
0x180044dd3  mov     rax, [rdi+40h]
0x180044dd7  lea     rcx, [rsp+150h+pdcm]; pdcm
0x180044ddc  mov     [rsp+150h+pdcm.pidlFolder], rax
0x180044de1  neg     rsi
0x180044de4  mov     [rsp+150h+pdcm.punkAssociationInfo], rdx
0x180044de9  mov     r8, r14; ppv
0x180044dec  sbb     rax, rax
0x180044def  mov     qword ptr [rsp+150h+pdcm.cKeys], rdx
0x180044df4  and     rax, rdi
0x180044df7  mov     [rsp+150h+pdcm.aKeys], rdx
0x180044dfc  mov     [rsp+150h+pdcm.psf], rax
0x180044e01  mov     rdx, rbx; riid
0x180044e04  xor     eax, eax
0x180044e06  mov     [rsp+150h+pdcm.cidl], r12d
0x180044e0b  mov     dword ptr [rsp+150h+pdcm+24h], eax
0x180044e0f  mov     [rsp+150h+pdcm.apidl], r15
0x180044e14  call    cs:__imp_SHCreateDefaultContextMenu
0x180044e1a  mov     rcx, [rbp+50h+var_50]
0x180044e1e  xor     rcx, rsp; StackCookie
0x180044e21  call    __security_check_cookie
0x180044e26  add     rsp, 118h
0x180044e2d  pop     r15
0x180044e2f  pop     r14
0x180044e31  pop     r13
0x180044e33  pop     r12
0x180044e35  pop     rdi
0x180044e36  pop     rsi
0x180044e37  pop     rbx
0x180044e38  pop     rbp
0x180044e39  retn
```
