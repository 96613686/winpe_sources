# CDBFolderDataObject::_InitializeDataObj(uint,_ITEMID_CHILD const * const *)

- ea: `0x18008279c`
- end: `0x1800828c3`
- name: `?_InitializeDataObj@CDBFolderDataObject@@AEAAJIPEBQEFBU_ITEMID_CHILD@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(struct IDataObject *this, unsigned int, LPCITEMIDLIST *apidl)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800828cc`

## callees

- `0x180080d98`
- `0x18008279c`
- `0x1800bf60c`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800828a8`
- `Windows.Storage!ILFree` at `0x1800828a8`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008284d`
- `Windows.Storage!SHGetIDListFromObject` at `0x18008284d`
- `Windows.Storage!SHCreateDataObject` at `0x18008287b`
- `Windows.Storage!SHCreateDataObject` at `0x18008287b`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827ca`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827de`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827f2`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180082806`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x18008281a`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827ca`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827de`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x1800827f2`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x180082806`
- `api-ms-win-rtcore-ntuser-clipboard-l1-1-0!RegisterClipboardFormatW` at `0x18008281a`

## string_xrefs

- `0x18008280c`: `FileGroupDescriptorW`
- `0x1800827f8`: `FileGroupDescriptor`

## pseudocode

```c
__int64 __fastcall CDBFolderDataObject::_InitializeDataObj(struct IDataObject *this, UINT a2, LPCITEMIDLIST *apidl)
{
  HRESULT v6; // ebx
  struct IDataObjectVtbl *lpVtbl; // rcx
  unsigned int v8; // r9d
  int riid; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+50h] [rbp+8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+68h] [rbp+20h] BYREF

  if ( !g_cfPreferredDropEffect )
  {
    g_cfPreferredDropEffect = RegisterClipboardFormatW(L"Preferred DropEffect");
    g_cfHIDA = RegisterClipboardFormatW(L"Shell IDList Array");
    g_cfFileContents = RegisterClipboardFormatW(L"FileContents");
    g_cfFileGroupDescriptorA = RegisterClipboardFormatW(L"FileGroupDescriptor");
    g_cfFileGroupDescriptorW = RegisterClipboardFormatW(L"FileGroupDescriptorW");
  }
  v6 = CloneIDListArray(a2);
  if ( v6 >= 0 )
  {
    lpVtbl = this[3].lpVtbl;
    ppidl = 0;
    v6 = SHGetIDListFromObject((IUnknown *)lpVtbl, &ppidl);
    if ( v6 >= 0 )
    {
      v6 = SHCreateDataObject(ppidl, a2, apidl, 0, &GUID_0000010e_0000_0000_c000_000000000046, (void **)&this[7].lpVtbl);
      if ( v6 >= 0 )
      {
        v11 = 1;
        DataObj_SetBlobWithIndex(this, g_cfPreferredDropEffect, &v11, v8, riid);
      }
      ILFree(ppidl);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18008279c  mov     [rsp+arg_8], rbx
0x1800827a1  mov     [rsp+arg_10], rbp
0x1800827a6  push    rsi
0x1800827a7  push    rdi
0x1800827a8  push    r14
0x1800827aa  sub     rsp, 30h
0x1800827ae  xor     r14d, r14d
0x1800827b1  mov     rsi, r8
0x1800827b4  cmp     cs:?g_cfPreferredDropEffect@@3GA, r14w; ushort g_cfPreferredDropEffect
0x1800827bc  mov     ebp, edx
0x1800827be  mov     rdi, rcx
0x1800827c1  jnz     short loc_180082827
0x1800827c3  lea     rcx, aPreferredDrope; "Preferred DropEffect"
0x1800827ca  call    cs:__imp_RegisterClipboardFormatW
0x1800827d0  lea     rcx, aShellIdlistArr; "Shell IDList Array"
0x1800827d7  mov     cs:?g_cfPreferredDropEffect@@3GA, ax; ushort g_cfPreferredDropEffect
0x1800827de  call    cs:__imp_RegisterClipboardFormatW
0x1800827e4  lea     rcx, aFilecontents; "FileContents"
0x1800827eb  mov     cs:?g_cfHIDA@@3GA, ax; ushort g_cfHIDA
0x1800827f2  call    cs:__imp_RegisterClipboardFormatW
0x1800827f8  lea     rcx, aFilegroupdescr_0; "FileGroupDescriptor"
0x1800827ff  mov     cs:?g_cfFileContents@@3GA, ax; ushort g_cfFileContents
0x180082806  call    cs:__imp_RegisterClipboardFormatW
0x18008280c  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180082813  mov     cs:?g_cfFileGroupDescriptorA@@3GA, ax; ushort g_cfFileGroupDescriptorA
0x18008281a  call    cs:__imp_RegisterClipboardFormatW
0x180082820  mov     cs:?g_cfFileGroupDescriptorW@@3GA, ax; ushort g_cfFileGroupDescriptorW
0x180082827  lea     r9, [rdi+28h]
0x18008282b  mov     rdx, rsi
0x18008282e  lea     r8, [rdi+20h]
0x180082832  mov     ecx, ebp; unsigned __int64
0x180082834  call    CloneIDListArray
0x180082839  mov     ebx, eax
0x18008283b  test    eax, eax
0x18008283d  js      short loc_1800828AE
0x18008283f  mov     rcx, [rdi+18h]; punk
0x180082843  lea     rdx, [rsp+48h+ppidl]; ppidl
0x180082848  mov     [rsp+48h+ppidl], r14
0x18008284d  call    cs:__imp_SHGetIDListFromObject
0x180082853  mov     ebx, eax
0x180082855  test    eax, eax
0x180082857  js      short loc_1800828AE
0x180082859  mov     rcx, [rsp+48h+ppidl]; pidlFolder
0x18008285e  lea     rax, [rdi+38h]
0x180082862  mov     [rsp+48h+ppv], rax; ppv
0x180082867  xor     r9d, r9d; pdtInner
0x18008286a  lea     rax, _GUID_0000010e_0000_0000_c000_000000000046
0x180082871  mov     r8, rsi; apidl
0x180082874  mov     edx, ebp; cidl
0x180082876  mov     [rsp+48h+riid], rax; int
0x18008287b  call    cs:__imp_SHCreateDataObject
0x180082881  mov     ebx, eax
0x180082883  test    eax, eax
0x180082885  js      short loc_1800828A3
0x180082887  movzx   edx, cs:?g_cfPreferredDropEffect@@3GA; unsigned int
0x18008288e  lea     r8, [rsp+48h+arg_0]; void *
0x180082893  mov     rcx, rdi; struct IDataObject *
0x180082896  mov     [rsp+48h+arg_0], 1
0x18008289e  call    ?DataObj_SetBlobWithIndex@@YAJPEAUIDataObject@@IPEBXIJ@Z; DataObj_SetBlobWithIndex(IDataObject *,uint,void const *,uint,long)
0x1800828a3  mov     rcx, [rsp+48h+ppidl]; pidl
0x1800828a8  call    cs:__imp_ILFree
0x1800828ae  mov     rbp, [rsp+48h+arg_10]
0x1800828b3  mov     eax, ebx
0x1800828b5  mov     rbx, [rsp+48h+arg_8]
0x1800828ba  add     rsp, 30h
0x1800828be  pop     r14
0x1800828c0  pop     rdi
0x1800828c1  pop     rsi
0x1800828c2  retn
```
