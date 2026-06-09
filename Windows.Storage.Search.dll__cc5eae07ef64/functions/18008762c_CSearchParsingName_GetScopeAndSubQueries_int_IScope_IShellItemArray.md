# CSearchParsingName::GetScopeAndSubQueries(int,IScope * *,IShellItemArray * *)

- ea: `0x18008762c`
- end: `0x1800877ae`
- name: `?GetScopeAndSubQueries@CSearchParsingName@@QEAAJHPEAPEAUIScope@@PEAPEAUIShellItemArray@@@Z`
- size: `386`
- prototype: `int(CSearchParsingName *__hidden this, int, struct IScope **, struct IShellItemArray **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180084594`
- `0x18008d408`

## callees

- `0x18003c4c0`
- `0x180071dc0`
- `0x18008762c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180087721`
- `SHCORE!SHStrDupW` at `0x180087721`
- `Windows.Storage!ILFree` at `0x18008776f`
- `Windows.Storage!ILFree` at `0x18008776f`
- `Windows.Storage!SHCreateShellItemArrayFromShellItem` at `0x180087795`
- `Windows.Storage!SHCreateShellItemArrayFromShellItem` at `0x180087795`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180087762`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180087762`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x18008767d`
- `Windows.Storage!SHCreateShellItemArrayFromIDLists` at `0x18008767d`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x180087741`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x180087741`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180087712`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180087712`
- `ext-ms-win-search-folder-l1-1-0!s_GetStartMenuFilesScope` at `0x1800876ea`
- `ext-ms-win-search-folder-l1-1-0!s_GetStartMenuFilesScope` at `0x1800876ea`

## pseudocode

```c
__int64 __fastcall CSearchParsingName::GetScopeAndSubQueries(
        CSearchParsingName *this,
        int a2,
        struct IScope **a3,
        struct IShellItemArray **a4)
{
  __int64 v6; // rdx
  HRESULT StartMenuFilesScope; // ebx
  struct IScope *v10; // rcx
  void (*v11)(void); // rax
  HINSTANCE v13; // rcx
  LPITEMIDLIST ppidl; // [rsp+20h] [rbp-248h] BYREF
  void *ppv; // [rsp+28h] [rbp-240h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  *a3 = 0;
  *a4 = 0;
  v6 = *((_QWORD *)this + 7);
  if ( v6 && *(_DWORD *)v6 )
  {
    StartMenuFilesScope = SHCreateShellItemArrayFromIDLists(*(_DWORD *)v6, *(LPCITEMIDLIST **)(v6 + 8), a4);
    if ( StartMenuFilesScope < 0 )
      return (unsigned int)StartMenuFilesScope;
    goto LABEL_4;
  }
  StartMenuFilesScope = 0;
  if ( *((_QWORD *)this + 4) )
  {
LABEL_4:
    v10 = (struct IScope *)*((_QWORD *)this + 4);
    if ( v10 )
    {
      *a3 = v10;
      v11 = *(void (**)(void))(*(_QWORD *)v10 + 8LL);
LABEL_6:
      v11();
      return (unsigned int)StartMenuFilesScope;
    }
    return (unsigned int)StartMenuFilesScope;
  }
  if ( !a2 )
  {
    ppv = 0;
    if ( (unsigned int)IsMSSearchEnabled(0, 0) )
    {
      ppidl = 0;
      StartMenuFilesScope = SHGetKnownFolderIDList(&FOLDERID_UsersLibraries, 0, 0, &ppidl);
      if ( StartMenuFilesScope < 0 )
        return (unsigned int)StartMenuFilesScope;
      StartMenuFilesScope = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      ILFree(ppidl);
    }
    else
    {
      StartMenuFilesScope = s_GetStartMenuFilesScope(0, a3);
      if ( StartMenuFilesScope < 0 )
        return (unsigned int)StartMenuFilesScope;
      v13 = g_hinst;
      *((_DWORD *)this + 24) |= 0x100u;
      LoadStringW(v13, 0x7775u, Buffer, 260);
      StartMenuFilesScope = SHStrDupW(Buffer, (LPWSTR *)this + 10);
    }
    if ( StartMenuFilesScope >= 0 && ppv )
    {
      StartMenuFilesScope = SHCreateShellItemArrayFromShellItem(
                              (IShellItem *)ppv,
                              &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                              (void **)a4);
      v11 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
      goto LABEL_6;
    }
  }
  return (unsigned int)StartMenuFilesScope;
}

```

## disassembly

```asm
0x18008762c  mov     [rsp+arg_8], rbx
0x180087631  push    rsi
0x180087632  push    rdi
0x180087633  push    r14
0x180087635  sub     rsp, 250h
0x18008763c  mov     rax, cs:__security_cookie
0x180087643  xor     rax, rsp
0x180087646  mov     [rsp+268h+var_28], rax
0x18008764e  mov     qword ptr [r8], 0
0x180087655  mov     eax, edx
0x180087657  mov     qword ptr [r9], 0
0x18008765e  mov     r14, r9
0x180087661  mov     rdx, [rcx+38h]
0x180087665  mov     rsi, r8
0x180087668  mov     rdi, rcx
0x18008766b  test    rdx, rdx
0x18008766e  jz      short loc_1800876C7
0x180087670  mov     ecx, [rdx]; cidl
0x180087672  test    ecx, ecx
0x180087674  jz      short loc_1800876C7
0x180087676  mov     rdx, [rdx+8]; rgpidl
0x18008767a  mov     r8, r9; ppsiItemArray
0x18008767d  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180087683  mov     ebx, eax
0x180087685  test    eax, eax
0x180087687  js      short loc_1800876A1
0x180087689  mov     rcx, [rdi+20h]
0x18008768d  test    rcx, rcx
0x180087690  jz      short loc_1800876A1
0x180087692  mov     [rsi], rcx
0x180087695  mov     rax, [rcx]
0x180087698  mov     rax, [rax+8]
0x18008769c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876a1  mov     eax, ebx
0x1800876a3  mov     rcx, [rsp+268h+var_28]
0x1800876ab  xor     rcx, rsp; StackCookie
0x1800876ae  call    __security_check_cookie
0x1800876b3  mov     rbx, [rsp+268h+arg_8]
0x1800876bb  add     rsp, 250h
0x1800876c2  pop     r14
0x1800876c4  pop     rdi
0x1800876c5  pop     rsi
0x1800876c6  retn
0x1800876c7  xor     ebx, ebx
0x1800876c9  cmp     [rdi+20h], rbx
0x1800876cd  jnz     short loc_180087689
0x1800876cf  test    eax, eax
0x1800876d1  jnz     short loc_1800876A1
0x1800876d3  xor     edx, edx
0x1800876d5  mov     [rsp+268h+ppv], rbx
0x1800876da  xor     ecx, ecx
0x1800876dc  call    IsMSSearchEnabled
0x1800876e1  test    eax, eax
0x1800876e3  jnz     short loc_18008772B
0x1800876e5  mov     rdx, rsi
0x1800876e8  xor     ecx, ecx
0x1800876ea  call    cs:__imp_s_GetStartMenuFilesScope
0x1800876f0  mov     ebx, eax
0x1800876f2  test    eax, eax
0x1800876f4  js      short loc_1800876A1
0x1800876f6  mov     rcx, cs:g_hinst; hInstance
0x1800876fd  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180087702  bts     dword ptr [rdi+60h], 8
0x180087707  mov     r9d, 104h; cchBufferMax
0x18008770d  mov     edx, 7775h; uID
0x180087712  call    cs:__imp_LoadStringW
0x180087718  lea     rdx, [rdi+50h]; ppwsz
0x18008771c  lea     rcx, [rsp+268h+Buffer]; psz
0x180087721  call    cs:__imp_SHStrDupW
0x180087727  mov     ebx, eax
0x180087729  jmp     short loc_180087775
0x18008772b  lea     r9, [rsp+268h+ppidl]; ppidl
0x180087730  mov     [rsp+268h+ppidl], rbx
0x180087735  xor     r8d, r8d; hToken
0x180087738  lea     rcx, FOLDERID_UsersLibraries; rfid
0x18008773f  xor     edx, edx; dwFlags
0x180087741  call    cs:__imp_SHGetKnownFolderIDList
0x180087747  mov     ebx, eax
0x180087749  test    eax, eax
0x18008774b  js      loc_1800876A1
0x180087751  mov     rcx, [rsp+268h+ppidl]; pidl
0x180087756  lea     r8, [rsp+268h+ppv]; ppv
0x18008775b  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180087762  call    cs:__imp_SHCreateItemFromIDList
0x180087768  mov     rcx, [rsp+268h+ppidl]; pidl
0x18008776d  mov     ebx, eax
0x18008776f  call    cs:__imp_ILFree
0x180087775  test    ebx, ebx
0x180087777  js      loc_1800876A1
0x18008777d  mov     rcx, [rsp+268h+ppv]; psi
0x180087782  test    rcx, rcx
0x180087785  jz      loc_1800876A1
0x18008778b  mov     r8, r14; ppv
0x18008778e  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180087795  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x18008779b  mov     rcx, [rsp+268h+ppv]
0x1800877a0  mov     ebx, eax
0x1800877a2  mov     rax, [rcx]
0x1800877a5  mov     rax, [rax+10h]
0x1800877a9  jmp     loc_18008769C
```
