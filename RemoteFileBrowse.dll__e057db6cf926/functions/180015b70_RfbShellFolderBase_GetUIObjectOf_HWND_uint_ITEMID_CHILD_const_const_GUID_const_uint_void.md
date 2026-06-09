# RfbShellFolderBase::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180015b70`
- end: `0x180015d5e`
- name: `?GetUIObjectOf@RfbShellFolderBase@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `494`
- prototype: `__int64 __fastcall(LPCITEMIDLIST *this, HWND, UINT, LPCITEMIDLIST *, const struct _GUID *riid, unsigned int *, void **ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800070cc`
- `0x180015b70`
- `0x180019010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180015cbc`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180015cbc`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180015bee`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180015bee`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RfbShellFolderBase::GetUIObjectOf(
        LPCITEMIDLIST *this,
        HWND a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *riid,
        unsigned int *a6,
        void **ppv)
{
  HRESULT v7; // eax
  unsigned int v8; // edi
  IDataObject *v9; // rcx
  __int64 result; // rax
  HRESULT v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-78h]
  IDataObject *ppdtobj; // [rsp+30h] [rbp-68h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    if ( a3 && a4 && ppv )
    {
      *ppv = 0;
      if ( *(_OWORD *)&IID_IDataObject == *(_OWORD *)riid )
      {
        ppdtobj = 0;
        v7 = CIDLData_CreateFromIDArray(this[6], a3, a4, &ppdtobj);
        v8 = v7;
        if ( v7 >= 0 )
        {
          *ppv = ppdtobj;
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x306,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
            (const char *)(unsigned int)v7,
            v13);
          v9 = ppdtobj;
          if ( ppdtobj )
          {
            ppdtobj = 0;
            ((void (__fastcall *)(IDataObject *))v9->lpVtbl->Release)(v9);
          }
          result = v8;
        }
      }
      else if ( *(_QWORD *)&IID_IContextMenu.Data1 == *(_QWORD *)&riid->Data1
             && *(_QWORD *)IID_IContextMenu.Data4 == *(_QWORD *)riid->Data4 )
      {
        pdcm.hwnd = a2;
        pdcm.pcmcb = 0;
        pdcm.pidlFolder = this[6];
        pdcm.psf = (IShellFolder *)((unsigned __int64)this & -(__int64)(this != (LPCITEMIDLIST *)8));
        pdcm.cidl = a3;
        *(&pdcm.cidl + 1) = 0;
        pdcm.apidl = a4;
        memset(&pdcm.punkAssociationInfo, 0, 24);
        v11 = SHCreateDefaultContextMenu(&pdcm, riid, ppv);
        v12 = v11;
        if ( v11 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30D,
            (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
            (const char *)(unsigned int)v11,
            v13);
        result = v12;
      }
      else if ( *(_QWORD *)&IID_IExtractIconA.Data1 == *(_QWORD *)&riid->Data1
             && *(_QWORD *)IID_IExtractIconA.Data4 == *(_QWORD *)riid->Data4
             || *(_QWORD *)&IID_IExtractIconW.Data1 == *(_QWORD *)&riid->Data1
             && *(_QWORD *)IID_IExtractIconW.Data4 == *(_QWORD *)riid->Data4 )
      {
        (*(void (__fastcall **)(char *, LPCITEMIDLIST, const struct _GUID *, void **))&(*(this - 1))[24].mkid.cb)(
          (char *)this - 8,
          *a4,
          riid,
          ppv);
        result = 0;
      }
      else
      {
        result = 2147500034LL;
      }
    }
    else
    {
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x31C,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                           (const char *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x180015b70  mov     [rsp+arg_0], rbx
0x180015b75  push    rdi
0x180015b76  sub     rsp, 90h
0x180015b7d  mov     r10, r9
0x180015b80  mov     edi, r8d
0x180015b83  mov     r8, rdx
0x180015b86  mov     r11, rcx
0x180015b89  test    edi, edi
0x180015b8b  jz      loc_180015D47
0x180015b91  test    r9, r9
0x180015b94  jz      loc_180015D47
0x180015b9a  mov     rbx, [rsp+98h+ppv]
0x180015ba2  test    rbx, rbx
0x180015ba5  jz      loc_180015D47
0x180015bab  mov     qword ptr [rbx], 0
0x180015bb2  mov     rdx, [rsp+98h+riid]; riid
0x180015bba  mov     rax, qword ptr cs:IID_IDataObject.Data1
0x180015bc1  cmp     rax, [rdx]
0x180015bc4  jnz     loc_180015C4D
0x180015bca  mov     rax, qword ptr cs:IID_IDataObject.Data4
0x180015bd1  cmp     rax, [rdx+8]
0x180015bd5  jnz     short loc_180015C4D
0x180015bd7  mov     [rsp+98h+ppdtobj], 0
0x180015be0  lea     r9, [rsp+98h+ppdtobj]; ppdtobj
0x180015be5  mov     r8, r10; apidl
0x180015be8  mov     edx, edi; cidl
0x180015bea  mov     rcx, [rcx+30h]; pidlFolder
0x180015bee  call    cs:__imp_CIDLData_CreateFromIDArray
0x180015bf4  mov     edi, eax
0x180015bf6  test    eax, eax
0x180015bf8  jns     short loc_180015C3E
0x180015bfa  mov     rcx, [rsp+98h]; this
0x180015c02  mov     r9d, eax; char *
0x180015c05  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180015c0c  mov     edx, 306h; void *
0x180015c11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c16  nop
0x180015c17  mov     rcx, [rsp+98h+ppdtobj]
0x180015c1c  test    rcx, rcx
0x180015c1f  jz      short loc_180015C37
0x180015c21  mov     [rsp+98h+ppdtobj], 0
0x180015c2a  mov     rax, [rcx]
0x180015c2d  mov     rax, [rax+10h]
0x180015c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c36  nop
0x180015c37  mov     eax, edi
0x180015c39  jmp     loc_180015D4C
0x180015c3e  mov     rax, [rsp+98h+ppdtobj]
0x180015c43  mov     [rbx], rax
0x180015c46  xor     eax, eax
0x180015c48  jmp     loc_180015D4C
0x180015c4d  mov     rax, qword ptr cs:IID_IContextMenu.Data1
0x180015c54  cmp     rax, [rdx]
0x180015c57  jnz     loc_180015CE8
0x180015c5d  mov     rax, qword ptr cs:IID_IContextMenu.Data4
0x180015c64  cmp     rax, [rdx+8]
0x180015c68  jnz     short loc_180015CE8
0x180015c6a  mov     [rsp+98h+pdcm.hwnd], r8
0x180015c6f  mov     [rsp+98h+pdcm.pcmcb], 0
0x180015c78  mov     rax, [rcx+30h]
0x180015c7c  mov     [rsp+98h+pdcm.pidlFolder], rax
0x180015c81  lea     rax, [rcx-8]
0x180015c85  neg     rax
0x180015c88  sbb     rcx, rcx
0x180015c8b  and     rcx, r11
0x180015c8e  mov     [rsp+98h+pdcm.psf], rcx
0x180015c93  mov     [rsp+98h+pdcm.cidl], edi
0x180015c97  xor     eax, eax
0x180015c99  mov     dword ptr [rsp+98h+pdcm+24h], eax
0x180015c9d  mov     [rsp+98h+pdcm.apidl], r10
0x180015ca2  mov     [rsp+98h+pdcm.punkAssociationInfo], rax
0x180015ca7  mov     qword ptr [rsp+98h+pdcm.cKeys], rax
0x180015cac  mov     [rsp+98h+pdcm.aKeys], rax
0x180015cb4  mov     r8, rbx; ppv
0x180015cb7  lea     rcx, [rsp+98h+pdcm]; pdcm
0x180015cbc  call    cs:__imp_SHCreateDefaultContextMenu
0x180015cc2  mov     ebx, eax
0x180015cc4  test    eax, eax
0x180015cc6  jns     short loc_180015CE4
0x180015cc8  mov     rcx, [rsp+98h]; this
0x180015cd0  mov     r9d, eax; char *
0x180015cd3  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180015cda  mov     edx, 30Dh; void *
0x180015cdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ce4  mov     eax, ebx
0x180015ce6  jmp     short loc_180015D4C
0x180015ce8  mov     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180015cef  cmp     rax, [rdx]
0x180015cf2  jnz     short loc_180015D01
0x180015cf4  mov     rax, qword ptr cs:IID_IExtractIconA.Data4
0x180015cfb  cmp     rax, [rdx+8]
0x180015cff  jz      short loc_180015D1A
0x180015d01  mov     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180015d08  cmp     rax, [rdx]
0x180015d0b  jnz     short loc_180015D37
0x180015d0d  mov     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180015d14  cmp     rax, [rdx+8]
0x180015d18  jnz     short loc_180015D37
0x180015d1a  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180015d1e  mov     rax, [rcx]
0x180015d21  mov     r9, rbx
0x180015d24  mov     r8, rdx
0x180015d27  mov     rdx, [r10]
0x180015d2a  mov     rax, [rax+48h]
0x180015d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d33  xor     eax, eax
0x180015d35  jmp     short loc_180015D4C
0x180015d37  mov     eax, 80004002h
0x180015d3c  jmp     short loc_180015D4C
0x180015d3e  mov     eax, [rsp+98h+arg_10]
0x180015d45  jmp     short loc_180015D4C
0x180015d47  mov     eax, 80070057h
0x180015d4c  mov     rbx, [rsp+98h+arg_0]
0x180015d54  add     rsp, 90h
0x180015d5b  pop     rdi
0x180015d5c  retn
```
