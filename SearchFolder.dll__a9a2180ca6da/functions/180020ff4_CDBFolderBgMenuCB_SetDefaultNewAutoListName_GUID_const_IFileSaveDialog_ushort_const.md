# CDBFolderBgMenuCB::_SetDefaultNewAutoListName(_GUID const &,IFileSaveDialog *,ushort const *)

- ea: `0x180020ff4`
- end: `0x18002112a`
- name: `?_SetDefaultNewAutoListName@CDBFolderBgMenuCB@@AEAAJAEBU_GUID@@PEAUIFileSaveDialog@@PEBG@Z`
- size: `310`
- prototype: `int(CDBFolderBgMenuCB *__hidden this, const struct _GUID *, struct IFileSaveDialog *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e834`

## callees

- `0x180006900`
- `0x18000ebd0`
- `0x18000ecc4`
- `0x180020ff4`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18002103f`
- `SHELL32!SHGetKnownFolderPath` at `0x18002103f`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x1800210c0`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x1800210c0`
- `SHLWAPI!PathFindFileNameW` at `0x1800210e5`
- `SHLWAPI!PathFindFileNameW` at `0x1800210e5`
- `SHLWAPI!PathRemoveExtensionW` at `0x1800210d1`
- `SHLWAPI!PathRemoveExtensionW` at `0x1800210d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021100`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021099`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180021099`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_SetDefaultNewAutoListName(
        CDBFolderBgMenuCB *this,
        const struct _GUID *a2,
        struct IFileSaveDialog *a3,
        const unsigned __int16 *a4)
{
  HRESULT v6; // ebx
  HRESULT (__stdcall *SetFileName)(IFileSaveDialog *, LPCWSTR); // rbx
  LPWSTR FileNameW; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszMore[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszUniqueName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR pszPathOut[264]; // [rsp+450h] [rbp+350h] BYREF

  ppszPath = 0;
  v6 = SHGetKnownFolderPath(&FOLDERID_SavedSearches, 0x1000u, 0, &ppszPath);
  if ( v6 >= 0 )
  {
    v6 = StringCchCopyW(pszMore, 0x104u, a4);
    if ( v6 >= 0 )
    {
      v6 = StringCchCatW(pszMore, 0x104u, L".search-ms");
      if ( v6 >= 0 )
      {
        v6 = PathCchCombine(pszPathOut, 0x104u, ppszPath, pszMore);
        if ( v6 >= 0 )
        {
          v6 = -2147467259;
          if ( PathYetAnotherMakeUniqueName(pszUniqueName, pszPathOut, 0, pszMore) )
          {
            PathRemoveExtensionW(pszUniqueName);
            SetFileName = a3->lpVtbl->SetFileName;
            FileNameW = PathFindFileNameW(pszUniqueName);
            v6 = ((__int64 (__fastcall *)(struct IFileSaveDialog *, LPWSTR))SetFileName)(a3, FileNameW);
          }
        }
      }
    }
    CoTaskMemFree(ppszPath);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020ff4  mov     [rsp-8+arg_0], rbx
0x180020ff9  push    rbp
0x180020ffa  push    rsi
0x180020ffb  push    rdi
0x180020ffc  lea     rbp, [rsp-570h]
0x180021004  sub     rsp, 670h
0x18002100b  mov     rax, cs:__security_cookie
0x180021012  xor     rax, rsp
0x180021015  mov     [rbp+580h+var_20], rax
0x18002101c  mov     rdi, r9
0x18002101f  mov     [rsp+680h+ppszPath], 0
0x180021028  mov     rsi, r8
0x18002102b  lea     r9, [rsp+680h+ppszPath]; ppszPath
0x180021030  xor     r8d, r8d; hToken
0x180021033  lea     rcx, FOLDERID_SavedSearches; rfid
0x18002103a  mov     edx, 1000h; dwFlags
0x18002103f  call    cs:__imp_SHGetKnownFolderPath
0x180021045  mov     ebx, eax
0x180021047  test    eax, eax
0x180021049  js      loc_180021106
0x18002104f  mov     r8, rdi; unsigned __int16 *
0x180021052  lea     rcx, [rsp+680h+pszMore]; unsigned __int16 *
0x180021057  mov     edi, 104h
0x18002105c  mov     edx, edi; unsigned __int64
0x18002105e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021063  mov     ebx, eax
0x180021065  test    eax, eax
0x180021067  js      loc_1800210FB
0x18002106d  lea     r8, aSearchMs_1; ".search-ms"
0x180021074  mov     edx, edi; unsigned __int64
0x180021076  lea     rcx, [rsp+680h+pszMore]; unsigned __int16 *
0x18002107b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021080  mov     ebx, eax
0x180021082  test    eax, eax
0x180021084  js      short loc_1800210FB
0x180021086  mov     r8, [rsp+680h+ppszPath]; pszPathIn
0x18002108b  lea     r9, [rsp+680h+pszMore]; pszMore
0x180021090  mov     edx, edi; cchPathOut
0x180021092  lea     rcx, [rbp+580h+pszPathOut]; pszPathOut
0x180021099  call    cs:__imp_PathCchCombine
0x18002109f  mov     ebx, eax
0x1800210a1  test    eax, eax
0x1800210a3  js      short loc_1800210FB
0x1800210a5  lea     r9, [rsp+680h+pszMore]; pszFileSpec
0x1800210aa  xor     r8d, r8d; pszShort
0x1800210ad  lea     rdx, [rbp+580h+pszPathOut]; pszPath
0x1800210b4  mov     ebx, 80004005h
0x1800210b9  lea     rcx, [rbp+580h+pszUniqueName]; pszUniqueName
0x1800210c0  call    cs:__imp_PathYetAnotherMakeUniqueName
0x1800210c6  test    eax, eax
0x1800210c8  jz      short loc_1800210FB
0x1800210ca  lea     rcx, [rbp+580h+pszUniqueName]; pszPath
0x1800210d1  call    cs:__imp_PathRemoveExtensionW
0x1800210d7  mov     rax, [rsi]
0x1800210da  lea     rcx, [rbp+580h+pszUniqueName]; pszPath
0x1800210e1  mov     rbx, [rax+78h]
0x1800210e5  call    cs:__imp_PathFindFileNameW
0x1800210eb  mov     rdx, rax
0x1800210ee  mov     rcx, rsi
0x1800210f1  mov     rax, rbx
0x1800210f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210f9  mov     ebx, eax
0x1800210fb  mov     rcx, [rsp+680h+ppszPath]; pv
0x180021100  call    cs:__imp_CoTaskMemFree
0x180021106  mov     eax, ebx
0x180021108  mov     rcx, [rbp+580h+var_20]
0x18002110f  xor     rcx, rsp; StackCookie
0x180021112  call    __security_check_cookie
0x180021117  mov     rbx, [rsp+680h+arg_0]
0x18002111f  add     rsp, 670h
0x180021126  pop     rdi
0x180021127  pop     rsi
0x180021128  pop     rbp
0x180021129  retn
```
