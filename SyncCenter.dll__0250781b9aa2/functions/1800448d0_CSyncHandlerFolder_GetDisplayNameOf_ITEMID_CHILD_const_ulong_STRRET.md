# CSyncHandlerFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x1800448d0`
- end: `0x180044a56`
- name: `?GetDisplayNameOf@CSyncHandlerFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `390`
- prototype: `int(CSyncHandlerFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180028d84`
- `0x18003482c`
- `0x180041808`
- `0x18004255c`
- `0x1800448d0`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180044a33`
- `SHLWAPI!SHStrDupW` at `0x180044a33`
- `SHLWAPI!PathAddBackslashW` at `0x180044964`
- `SHLWAPI!PathAddBackslashW` at `0x180044964`

## pseudocode

```c
HRESULT __fastcall CSyncHandlerFolder::GetDisplayNameOf(
        CSyncHandlerFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  CSyncFolderBase *v4; // rsi
  HRESULT result; // eax
  unsigned int v9; // r9d
  unsigned __int64 v10; // r9
  unsigned __int16 *v11; // r8
  unsigned int *v12; // [rsp+20h] [rbp-E0h]
  _BYTE v13[276]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v14[542]; // [rsp+144h] [rbp+44h] BYREF
  unsigned __int16 v15[64]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR pszPath[264]; // [rsp+600h] [rbp+500h] BYREF

  v4 = (CSyncHandlerFolder *)((char *)this - 16);
  result = (*(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, unsigned __int16 *, __int64))(*((_QWORD *)this - 2) + 264LL))(
             (char *)this - 16,
             a2,
             v15,
             64);
  if ( result >= 0 )
  {
    pszPath[0] = 0;
    if ( (a3 & 0x8000) != 0 )
    {
      if ( (a3 & 1) == 0 )
      {
        result = SHGetNameAndFlagsW(*((LPCITEMIDLIST *)this + 8), a3, pszPath, v9, v12);
        if ( result < 0 )
          return result;
        PathAddBackslashW(pszPath);
      }
      if ( (a3 & 0x4000) != 0 )
      {
        memset_0(v13, 0, 0x550u);
        result = CSyncFolderBase::GetFolderItemInfoForIDs(
                   v4,
                   (const unsigned __int16 *)this + 94,
                   v15,
                   (struct SYNCMGR_FOLDERITEMINFO *)v13);
        if ( result < 0 )
          return result;
        v10 = 128;
        v11 = v14;
      }
      else
      {
        v10 = 64;
        v11 = v15;
      }
      result = StringCchCatNW(pszPath, 0x104u, v11, v10);
    }
    else
    {
      memset_0(v13, 0, 0x550u);
      result = CSyncFolderBase::GetFolderItemInfoForIDs(
                 v4,
                 (const unsigned __int16 *)this + 94,
                 v15,
                 (struct SYNCMGR_FOLDERITEMINFO *)v13);
      if ( result < 0 )
        return result;
      result = StringCchCopyNW(pszPath, 0x104u, v14, 0x80u);
    }
    if ( result >= 0 )
    {
      a4->uType = 0;
      return SHStrDupW(pszPath, &a4->pOleStr);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800448d0  push    rbp
0x1800448d2  push    rbx
0x1800448d3  push    rsi
0x1800448d4  push    rdi
0x1800448d5  push    r14
0x1800448d7  lea     rbp, [rsp-720h]
0x1800448df  sub     rsp, 820h
0x1800448e6  mov     rax, cs:__security_cookie
0x1800448ed  xor     rax, rsp
0x1800448f0  mov     [rbp+740h+var_30], rax
0x1800448f7  lea     rsi, [rcx-10h]
0x1800448fb  mov     r14, r9
0x1800448fe  mov     rax, [rsi]
0x180044901  mov     ebx, r8d
0x180044904  mov     rdi, rcx
0x180044907  lea     r8, [rbp+740h+var_2C0]
0x18004490e  mov     r9d, 40h ; '@'
0x180044914  mov     rcx, rsi
0x180044917  mov     rax, [rax+108h]
0x18004491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044923  test    eax, eax
0x180044925  js      loc_180044A39
0x18004492b  xor     eax, eax
0x18004492d  mov     [rbp+740h+pszPath], ax
0x180044934  bt      ebx, 0Fh
0x180044938  jnb     loc_1800449D1
0x18004493e  test    bl, 1
0x180044941  jnz     short loc_18004496A
0x180044943  mov     rcx, [rdi+40h]; pidl
0x180044947  lea     r8, [rbp+740h+pszPath]; unsigned __int16 *
0x18004494e  mov     edx, ebx; unsigned int
0x180044950  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x180044955  test    eax, eax
0x180044957  js      loc_180044A39
0x18004495d  lea     rcx, [rbp+740h+pszPath]; pszPath
0x180044964  call    cs:__imp_PathAddBackslashW
0x18004496a  bt      ebx, 0Eh
0x18004496e  jnb     short loc_1800449B1
0x180044970  xor     edx, edx; Val
0x180044972  lea     rcx, [rsp+840h+var_810]; void *
0x180044977  mov     r8d, 550h; Size
0x18004497d  call    memset_0
0x180044982  lea     rdx, [rdi+0BCh]; unsigned __int16 *
0x180044989  mov     rcx, rsi; this
0x18004498c  lea     r9, [rsp+840h+var_810]; struct SYNCMGR_FOLDERITEMINFO *
0x180044991  lea     r8, [rbp+740h+var_2C0]; unsigned __int16 *
0x180044998  call    ?GetFolderItemInfoForIDs@CSyncFolderBase@@IEBAJPEBG0PEAUSYNCMGR_FOLDERITEMINFO@@@Z; CSyncFolderBase::GetFolderItemInfoForIDs(ushort const *,ushort const *,SYNCMGR_FOLDERITEMINFO *)
0x18004499d  test    eax, eax
0x18004499f  js      loc_180044A39
0x1800449a5  mov     r9d, 80h
0x1800449ab  lea     r8, [rbp+740h+var_6FC]
0x1800449af  jmp     short loc_1800449BE
0x1800449b1  mov     r9d, 40h ; '@'; unsigned __int64
0x1800449b7  lea     r8, [rbp+740h+var_2C0]; unsigned __int16 *
0x1800449be  mov     edx, 104h; unsigned __int64
0x1800449c3  lea     rcx, [rbp+740h+pszPath]; unsigned __int16 *
0x1800449ca  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800449cf  jmp     short loc_180044A1D
0x1800449d1  xor     edx, edx; Val
0x1800449d3  lea     rcx, [rsp+840h+var_810]; void *
0x1800449d8  mov     r8d, 550h; Size
0x1800449de  call    memset_0
0x1800449e3  lea     rdx, [rdi+0BCh]; unsigned __int16 *
0x1800449ea  mov     rcx, rsi; this
0x1800449ed  lea     r9, [rsp+840h+var_810]; struct SYNCMGR_FOLDERITEMINFO *
0x1800449f2  lea     r8, [rbp+740h+var_2C0]; unsigned __int16 *
0x1800449f9  call    ?GetFolderItemInfoForIDs@CSyncFolderBase@@IEBAJPEBG0PEAUSYNCMGR_FOLDERITEMINFO@@@Z; CSyncFolderBase::GetFolderItemInfoForIDs(ushort const *,ushort const *,SYNCMGR_FOLDERITEMINFO *)
0x1800449fe  test    eax, eax
0x180044a00  js      short loc_180044A39
0x180044a02  mov     r9d, 80h; unsigned __int64
0x180044a08  lea     r8, [rbp+740h+var_6FC]; unsigned __int16 *
0x180044a0c  mov     edx, 104h; unsigned __int64
0x180044a11  lea     rcx, [rbp+740h+pszPath]; unsigned __int16 *
0x180044a18  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180044a1d  test    eax, eax
0x180044a1f  js      short loc_180044A39
0x180044a21  lea     rdx, [r14+8]; ppwsz
0x180044a25  mov     dword ptr [r14], 0
0x180044a2c  lea     rcx, [rbp+740h+pszPath]; psz
0x180044a33  call    cs:__imp_SHStrDupW
0x180044a39  mov     rcx, [rbp+740h+var_30]
0x180044a40  xor     rcx, rsp; StackCookie
0x180044a43  call    __security_check_cookie
0x180044a48  add     rsp, 820h
0x180044a4f  pop     r14
0x180044a51  pop     rdi
0x180044a52  pop     rsi
0x180044a53  pop     rbx
0x180044a54  pop     rbp
0x180044a55  retn
```
