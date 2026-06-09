# CARPFolder::_GetDisplayNameOfAppUpdates(ulong,_STRRET *)

- ea: `0x180019f54`
- end: `0x18001a022`
- name: `?_GetDisplayNameOfAppUpdates@CARPFolder@@AEAAJKPEAU_STRRET@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(CARPFolder *__hidden this, unsigned int, struct _STRRET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callers

- `0x180013a70`

## callees

- `0x180016edc`
- `0x180017128`
- `0x180019f54`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x18001a003`
- `SHCORE!SHStrDupW` at `0x18001a003`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019fe1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019fe1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180019fc3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180019fc3`

## pseudocode

```c
int __fastcall CARPFolder::_GetDisplayNameOfAppUpdates(
        LPCITEMIDLIST *this,
        __int16 a2,
        struct _STRRET *a3,
        unsigned int a4)
{
  union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *p_pOleStr; // rdx
  WCHAR *v6; // rcx
  int result; // eax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( (a2 & 0x8000) == 0 || (a2 & 0x4000) != 0 )
  {
    if ( LoadStringW(g_hinst, 0x9Du, pszPath, 260) )
    {
LABEL_10:
      v6 = pszPath;
      a3->uType = 0;
      p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)&a3->pOleStr;
      return SHStrDupW(v6, &p_pOleStr->pOleStr);
    }
    result = ResultFromKnownLastError();
LABEL_9:
    if ( result < 0 )
      return result;
    goto LABEL_10;
  }
  if ( (a2 & 1) == 0 )
  {
    result = SHGetNameAndFlagsW(this[15], a2, pszPath, a4, 0);
    if ( result < 0 )
      return result;
    result = PathCchAppend(pszPath, 0x104u, L"::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}");
    goto LABEL_9;
  }
  a3->uType = 0;
  p_pOleStr = (union _STRRET::$CBA4CBE4EE73FCDBDFD08B2527F2F26D *)&a3->pOleStr;
  v6 = (WCHAR *)L"::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}";
  return SHStrDupW(v6, &p_pOleStr->pOleStr);
}

```

## disassembly

```asm
0x180019f54  push    rbx
0x180019f56  sub     rsp, 250h
0x180019f5d  mov     rax, cs:__security_cookie
0x180019f64  xor     rax, rsp
0x180019f67  mov     [rsp+258h+var_18], rax
0x180019f6f  mov     rbx, r8
0x180019f72  bt      edx, 0Fh
0x180019f76  jnb     short loc_180019FCB
0x180019f78  bt      edx, 0Eh
0x180019f7c  jb      short loc_180019FCB
0x180019f7e  test    dl, 1
0x180019f81  jz      short loc_180019F97
0x180019f83  mov     dword ptr [r8], 0
0x180019f8a  lea     rdx, [r8+8]; unsigned int
0x180019f8e  lea     rcx, pszMore; "::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd"...
0x180019f95  jmp     short loc_18001A003
0x180019f97  mov     rcx, [rcx+78h]; pidl
0x180019f9b  lea     r8, [rsp+258h+pszPath]; unsigned __int16 *
0x180019fa0  mov     [rsp+258h+var_238], 0; unsigned int *
0x180019fa9  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x180019fae  test    eax, eax
0x180019fb0  js      short loc_18001A009
0x180019fb2  lea     r8, pszMore; "::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd"...
0x180019fb9  mov     edx, 104h; cchPath
0x180019fbe  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180019fc3  call    cs:__imp_PathCchAppend
0x180019fc9  jmp     short loc_180019FF0
0x180019fcb  mov     rcx, cs:g_hinst; hInstance
0x180019fd2  lea     r8, [rsp+258h+pszPath]; lpBuffer
0x180019fd7  mov     r9d, 104h; cchBufferMax
0x180019fdd  lea     edx, [r9-67h]; uID
0x180019fe1  call    cs:__imp_LoadStringW
0x180019fe7  test    eax, eax
0x180019fe9  jnz     short loc_180019FF4
0x180019feb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019ff0  test    eax, eax
0x180019ff2  js      short loc_18001A009
0x180019ff4  lea     rcx, [rsp+258h+pszPath]; psz
0x180019ff9  mov     dword ptr [rbx], 0
0x180019fff  lea     rdx, [rbx+8]; ppwsz
0x18001a003  call    cs:__imp_SHStrDupW
0x18001a009  mov     rcx, [rsp+258h+var_18]
0x18001a011  xor     rcx, rsp; StackCookie
0x18001a014  call    __security_check_cookie
0x18001a019  add     rsp, 250h
0x18001a020  pop     rbx
0x18001a021  retn
```
