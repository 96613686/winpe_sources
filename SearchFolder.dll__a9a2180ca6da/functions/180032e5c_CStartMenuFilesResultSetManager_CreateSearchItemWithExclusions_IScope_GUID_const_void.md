# CStartMenuFilesResultSetManager::_CreateSearchItemWithExclusions(IScope *,_GUID const &,void * *)

- ea: `0x180032e5c`
- end: `0x180032f19`
- name: `?_CreateSearchItemWithExclusions@CStartMenuFilesResultSetManager@@AEAAJPEAUIScope@@AEBU_GUID@@PEAPEAX@Z`
- size: `189`
- prototype: `__int64 __fastcall(CStartMenuFilesResultSetManager *this, struct IScope *, const ITEMIDLIST *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180031e68`

## callees

- `0x180005460`
- `0x180032e5c`
- `0x18003435c`
- `0x180039b1c`
- `0x180039b70`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180032efb`
- `SHELL32!SHCreateItemFromIDList` at `0x180032efb`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateTransientVFolderIDList` at `0x180032ee0`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateTransientVFolderIDList` at `0x180032ee0`

## pseudocode

```c
__int64 __fastcall CStartMenuFilesResultSetManager::_CreateSearchItemWithExclusions(
        CStartMenuFilesResultSetManager *this,
        struct IScope *a2,
        const ITEMIDLIST *a3,
        void **a4)
{
  __int64 v7; // rcx
  HRESULT v8; // ebx
  __int64 v9; // rcx
  LPCITEMIDLIST pidl; // [rsp+60h] [rbp+18h] BYREF

  pidl = a3;
  *a4 = 0;
  v8 = CStartMenuFilesResultSetManager::s_ExcludePublicFolders(a2);
  if ( v8 >= 0 )
  {
    v8 = CStartMenuFilesResultSetManager::_ExcludeLibraryScopes(v7, a2, 0, *((_QWORD *)this + 20));
    if ( v8 >= 0 )
    {
      v8 = CStartMenuFilesResultSetManager::_ExcludeLibraryScopes(v9, a2, 1, *((_QWORD *)this + 21));
      if ( v8 >= 0 )
      {
        v8 = CStartMenuFilesResultSetManager::s_ExcludeProgramsScopes(a2);
        if ( v8 >= 0 )
        {
          pidl = 0;
          v8 = SHCreateTransientVFolderIDList(a2, 0, &pidl);
          if ( v8 >= 0 )
            v8 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a4);
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180032e5c  mov     [rsp+pidl], r8
0x180032e61  push    rbx
0x180032e62  push    rsi
0x180032e63  push    rdi
0x180032e64  push    r14
0x180032e66  sub     rsp, 28h
0x180032e6a  mov     rsi, rcx
0x180032e6d  mov     qword ptr [r9], 0
0x180032e74  mov     rcx, rdx; struct IScope *
0x180032e77  mov     r14, r9
0x180032e7a  mov     rdi, rdx
0x180032e7d  call    ?s_ExcludePublicFolders@CStartMenuFilesResultSetManager@@SAJPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_ExcludePublicFolders(IScope *)
0x180032e82  mov     ebx, eax
0x180032e84  test    eax, eax
0x180032e86  js      loc_180032F0D
0x180032e8c  mov     r9, [rsi+0A0h]
0x180032e93  xor     r8d, r8d
0x180032e96  mov     rdx, rdi
0x180032e99  call    ?_ExcludeLibraryScopes@CStartMenuFilesResultSetManager@@AEAAJPEAUIScope@@W4_LIBRARY_EXCLUDE_TYPE@@PEAV?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@@Z; CStartMenuFilesResultSetManager::_ExcludeLibraryScopes(IScope *,_LIBRARY_EXCLUDE_TYPE,CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>> *)
0x180032e9e  mov     ebx, eax
0x180032ea0  test    eax, eax
0x180032ea2  js      short loc_180032F0D
0x180032ea4  mov     r9, [rsi+0A8h]
0x180032eab  mov     r8d, 1
0x180032eb1  mov     rdx, rdi
0x180032eb4  call    ?_ExcludeLibraryScopes@CStartMenuFilesResultSetManager@@AEAAJPEAUIScope@@W4_LIBRARY_EXCLUDE_TYPE@@PEAV?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@@Z; CStartMenuFilesResultSetManager::_ExcludeLibraryScopes(IScope *,_LIBRARY_EXCLUDE_TYPE,CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>> *)
0x180032eb9  mov     ebx, eax
0x180032ebb  test    eax, eax
0x180032ebd  js      short loc_180032F0D
0x180032ebf  mov     rcx, rdi; struct IScope *
0x180032ec2  call    ?s_ExcludeProgramsScopes@CStartMenuFilesResultSetManager@@SAJPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_ExcludeProgramsScopes(IScope *)
0x180032ec7  mov     ebx, eax
0x180032ec9  test    eax, eax
0x180032ecb  js      short loc_180032F0D
0x180032ecd  lea     r8, [rsp+48h+pidl]
0x180032ed2  mov     [rsp+48h+pidl], 0
0x180032edb  xor     edx, edx
0x180032edd  mov     rcx, rdi
0x180032ee0  call    cs:__imp_SHCreateTransientVFolderIDList
0x180032ee6  mov     ebx, eax
0x180032ee8  test    eax, eax
0x180032eea  js      short loc_180032F03
0x180032eec  mov     rcx, [rsp+48h+pidl]; pidl
0x180032ef1  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180032ef8  mov     r8, r14; ppv
0x180032efb  call    cs:__imp_SHCreateItemFromIDList
0x180032f01  mov     ebx, eax
0x180032f03  lea     rcx, [rsp+48h+pidl]; void *
0x180032f08  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180032f0d  mov     eax, ebx
0x180032f0f  add     rsp, 28h
0x180032f13  pop     r14
0x180032f15  pop     rdi
0x180032f16  pop     rsi
0x180032f17  pop     rbx
0x180032f18  retn
```
