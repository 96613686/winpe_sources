# ResolveInitialBrowserLocation(HWND__ *,IETHREADPARAM *,int *)

- ea: `0x18008f508`
- end: `0x18008f7dd`
- name: `?ResolveInitialBrowserLocation@@YAJPEAUHWND__@@PEAUIETHREADPARAM@@PEAH@Z`
- size: `725`
- prototype: `__int64 __fastcall(HWND, struct IETHREADPARAM *, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801143f8`
- `0x180191640`

## callees

- `0x1800218ac`
- `0x1800243b0`
- `0x18002cb14`
- `0x18008f508`
- `0x18008f7e4`
- `0x18008fa14`
- `0x1800903fc`
- `0x18013f7d0`
- `0x180192054`
- `0x18019d304`
- `0x1802086a0`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x18008f5ac`
- `SHELL32!SHGetIDListFromObject` at `0x18008f5ac`
- `SHELL32!SHCreateItemFromIDList` at `0x18008f574`
- `SHELL32!SHCreateItemFromIDList` at `0x18008f574`
- `SHELL32!__imp_ILClone` at `0x18008f6cf`
- `SHELL32!__imp_ILClone` at `0x18008f6cf`
- `SHELL32!__imp_ILFree` at `0x18008f5ca`
- `SHELL32!__imp_ILFree` at `0x18008f6f0`
- `SHELL32!__imp_ILFree` at `0x18008f7b4`
- `SHELL32!__imp_ILFree` at `0x18008f7d1`
- `SHELL32!__imp_ILFree` at `0x18008f5ca`
- `SHELL32!__imp_ILFree` at `0x18008f6f0`
- `SHELL32!__imp_ILFree` at `0x18008f7b4`
- `SHELL32!__imp_ILFree` at `0x18008f7d1`
- `SHLWAPI!PathStripToRootW` at `0x18008f77b`
- `SHLWAPI!PathStripToRootW` at `0x18008f77b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008f770`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008f770`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008f75c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008f75c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f647`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ResolveInitialBrowserLocation(HWND a1, struct IETHREADPARAM *a2, int *a3)
{
  HRESULT v5; // ebx
  const struct _ITEMIDLIST_ABSOLUTE **v6; // rdi
  const struct _ITEMIDLIST_ABSOLUTE *v7; // rcx
  const struct _GUID *v8; // r8
  const struct _ITEMIDLIST_ABSOLUTE *v9; // rcx
  void *v10; // rcx
  int v12; // eax
  int v13; // edi
  WCHAR v14; // ax
  const ITEMIDLIST *v15; // rcx
  HMODULE ModuleHandleW; // rax
  LPITEMIDLIST ppidl; // [rsp+20h] [rbp-E0h] BYREF
  void *ppv[2]; // [rsp+28h] [rbp-D8h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[2088]; // [rsp+40h] [rbp-C0h] BYREF

  if ( *((_DWORD *)a2 + 50) || (v12 = *((_DWORD *)a2 + 44), (v12 & 0x10) != 0) )
  {
    v5 = 0;
    v6 = (const struct _ITEMIDLIST_ABSOLUTE **)((char *)a2 + 40);
    goto LABEL_3;
  }
  ppidl = 0;
  v13 = 0;
  if ( (v12 & 2) == 0 )
    LOBYTE(v13) = *((_QWORD *)a2 + 4) == 0;
  if ( (v12 & 0x40) == 0 || *((_QWORD *)a2 + 4) )
  {
    v5 = 0;
    v14 = 0;
    Filename[0] = 0;
    if ( *(_QWORD *)a2 )
    {
      v5 = StringCchCopyW(Filename, 0x824u, *(const unsigned __int16 **)a2);
      v14 = Filename[0];
    }
    if ( v5 >= 0 )
    {
      v15 = (const ITEMIDLIST *)*((_QWORD *)a2 + 5);
      if ( v15 )
      {
        ppidl = ILClone(v15);
      }
      else if ( v14 )
      {
        v5 = DetectSpecialUrlHacks(Filename);
        if ( v5 >= 0 )
          v5 = ConvertOutsideLocationToPidl(a1, Filename, &ppidl);
      }
    }
    if ( ppidl || !v13 )
      goto LABEL_30;
  }
  Filename[0] = 0;
  ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x824u);
  PathStripToRootW(Filename);
  v5 = ConvertOutsideLocationToPidl(a1, Filename, &ppidl);
  if ( v5 >= 0 )
  {
LABEL_30:
    if ( v5 >= 0 )
    {
      v6 = (const struct _ITEMIDLIST_ABSOLUTE **)((char *)a2 + 40);
      ILFree(*((LPITEMIDLIST *)a2 + 5));
      *((_QWORD *)a2 + 5) = ppidl;
      *((_DWORD *)a2 + 50) = 1;
LABEL_3:
      v7 = *v6;
      if ( !*v6 )
        goto LABEL_10;
      ppv[0] = 0;
      if ( SHCreateItemFromIDList((LPCITEMIDLIST)v7, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, ppv) < 0 )
        goto LABEL_10;
      punk = 0;
      v5 = _ConvertToViewResultItem((IUnknown *)ppv[0], 1, v8, (void **)&punk);
      if ( v5 >= 0 )
      {
        ppidl = 0;
        v5 = SHGetIDListFromObject(punk, &ppidl);
        if ( v5 >= 0 )
        {
          Pidl_Set(v6, ppidl);
          ILFree(ppidl);
        }
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      if ( v5 >= 0 )
      {
LABEL_10:
        v9 = *v6;
        if ( *v6 )
        {
          ppidl = 0;
          if ( (int)ConvertTopViewIDList(v9, (const unsigned __int16 *)a2, (struct _ITEMIDLIST_ABSOLUTE **)&ppidl) >= 0 )
          {
            Pidl_Set(v6, ppidl);
            ILFree(ppidl);
          }
          *(_OWORD *)ppv = 0;
          if ( !(unsigned int)CKnownFoldersFilter::RedirectKnownFolder(
                                (CKnownFoldersFilter *)ppv,
                                *v6,
                                (struct _ITEMIDLIST_ABSOLUTE **)&ppidl) )
          {
            Pidl_Set(v6, ppidl);
            ILFree(ppidl);
          }
          v10 = ppv[1];
          ppv[1] = 0;
          if ( v10 )
            CoTaskMemFree(v10);
          Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(ppv);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008f508  mov     [rsp-8+arg_10], rbx
0x18008f50d  push    rbp
0x18008f50e  push    rsi
0x18008f50f  push    rdi
0x18008f510  push    r14
0x18008f512  push    r15
0x18008f514  lea     rbp, [rsp-0FA0h]
0x18008f51c  mov     eax, 10A0h
0x18008f521  call    _alloca_probe
0x18008f526  sub     rsp, rax
0x18008f529  mov     rax, cs:__security_cookie
0x18008f530  xor     rax, rsp
0x18008f533  mov     [rbp+0FC0h+var_30], rax
0x18008f53a  mov     rsi, rdx
0x18008f53d  mov     r14, rcx
0x18008f540  xor     r15d, r15d
0x18008f543  cmp     [rdx+0C8h], r15d
0x18008f54a  jz      loc_18008F67F
0x18008f550  mov     ebx, r15d
0x18008f553  lea     rdi, [rdx+28h]
0x18008f557  mov     rcx, [rdi]; pidl
0x18008f55a  test    rcx, rcx
0x18008f55d  jz      loc_18008F5F6
0x18008f563  mov     [rsp+10C0h+ppv], r15
0x18008f568  lea     r8, [rsp+10C0h+ppv]; ppv
0x18008f56d  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18008f574  call    cs:__imp_SHCreateItemFromIDList
0x18008f57a  test    eax, eax
0x18008f57c  js      short loc_18008F5F6
0x18008f57e  mov     [rsp+10C0h+punk], r15
0x18008f583  lea     r9, [rsp+10C0h+punk]; void **
0x18008f588  mov     edx, 1; int
0x18008f58d  mov     rcx, [rsp+10C0h+ppv]; punk
0x18008f592  call    ?_ConvertToViewResultItem@@YAJPEAUIShellItem@@HAEBU_GUID@@PEAPEAX@Z; _ConvertToViewResultItem(IShellItem *,int,_GUID const &,void * *)
0x18008f597  mov     ebx, eax
0x18008f599  test    eax, eax
0x18008f59b  js      short loc_18008F5E1
0x18008f59d  mov     [rsp+10C0h+ppidl], r15
0x18008f5a2  lea     rdx, [rsp+10C0h+ppidl]; ppidl
0x18008f5a7  mov     rcx, [rsp+10C0h+punk]; punk
0x18008f5ac  call    cs:__imp_SHGetIDListFromObject
0x18008f5b2  mov     ebx, eax
0x18008f5b4  test    eax, eax
0x18008f5b6  js      short loc_18008F5D0
0x18008f5b8  mov     rdx, [rsp+10C0h+ppidl]
0x18008f5bd  mov     rcx, rdi
0x18008f5c0  call    Pidl_Set
0x18008f5c5  mov     rcx, [rsp+10C0h+ppidl]; pidl
0x18008f5ca  call    cs:__imp_ILFree
0x18008f5d0  mov     rcx, [rsp+10C0h+punk]
0x18008f5d5  mov     rax, [rcx]
0x18008f5d8  mov     rax, [rax+10h]
0x18008f5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f5e1  mov     rcx, [rsp+10C0h+ppv]
0x18008f5e6  mov     rax, [rcx]
0x18008f5e9  mov     rax, [rax+10h]
0x18008f5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f5f2  test    ebx, ebx
0x18008f5f4  js      short loc_18008F657
0x18008f5f6  mov     rcx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x18008f5f9  test    rcx, rcx
0x18008f5fc  jz      short loc_18008F657
0x18008f5fe  mov     [rsp+10C0h+ppidl], r15
0x18008f603  lea     r8, [rsp+10C0h+ppidl]; struct _ITEMIDLIST_ABSOLUTE **
0x18008f608  call    ?ConvertTopViewIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGPEAPEAU1@@Z; ConvertTopViewIDList(_ITEMIDLIST_ABSOLUTE const *,ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x18008f60d  test    eax, eax
0x18008f60f  jns     loc_18008F7A2
0x18008f615  xorps   xmm0, xmm0
0x18008f618  movdqu  xmmword ptr [rsp+10C0h+ppv], xmm0
0x18008f61e  lea     r8, [rsp+10C0h+ppidl]; struct _ITEMIDLIST_ABSOLUTE **
0x18008f623  mov     rdx, [rdi]; struct _ITEMIDLIST_ABSOLUTE *
0x18008f626  lea     rcx, [rsp+10C0h+ppv]; this
0x18008f62b  call    ?RedirectKnownFolder@CKnownFoldersFilter@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAU2@@Z; CKnownFoldersFilter::RedirectKnownFolder(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18008f630  test    eax, eax
0x18008f632  jz      loc_18008F7BF
0x18008f638  mov     rcx, [rsp+10C0h+ppv+8]; pv
0x18008f63d  mov     [rsp+10C0h+ppv+8], r15
0x18008f642  test    rcx, rcx
0x18008f645  jz      short loc_18008F64D
0x18008f647  call    cs:__imp_CoTaskMemFree
0x18008f64d  lea     rcx, [rsp+10C0h+ppv]
0x18008f652  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x18008f657  mov     eax, ebx
0x18008f659  mov     rcx, [rbp+0FC0h+var_30]
0x18008f660  xor     rcx, rsp; StackCookie
0x18008f663  call    __security_check_cookie
0x18008f668  mov     rbx, [rsp+10C0h+arg_10]
0x18008f670  add     rsp, 10A0h
0x18008f677  pop     r15
0x18008f679  pop     r14
0x18008f67b  pop     rdi
0x18008f67c  pop     rsi
0x18008f67d  pop     rbp
0x18008f67e  retn
0x18008f67f  mov     eax, [rdx+0B0h]
0x18008f685  test    al, 10h
0x18008f687  jnz     loc_18008F550
0x18008f68d  mov     [rsp+10C0h+ppidl], r15
0x18008f692  mov     edi, r15d
0x18008f695  test    al, 2
0x18008f697  jnz     short loc_18008F6A1
0x18008f699  cmp     [rdx+20h], r15
0x18008f69d  setz    dil
0x18008f6a1  test    al, 40h
0x18008f6a3  jz      short loc_18008F6AF
0x18008f6a5  cmp     [rdx+20h], r15
0x18008f6a9  jz      loc_18008F754
0x18008f6af  mov     ebx, r15d
0x18008f6b2  mov     eax, r15d
0x18008f6b5  mov     [rsp+10C0h+Filename], ax
0x18008f6ba  mov     r8, [rdx]; unsigned __int16 *
0x18008f6bd  test    r8, r8
0x18008f6c0  jnz     short loc_18008F70D
0x18008f6c2  test    ebx, ebx
0x18008f6c4  js      short loc_18008F6DA
0x18008f6c6  mov     rcx, [rsi+28h]; pidl
0x18008f6ca  test    rcx, rcx
0x18008f6cd  jz      short loc_18008F725
0x18008f6cf  call    cs:__imp_ILClone
0x18008f6d5  mov     [rsp+10C0h+ppidl], rax
0x18008f6da  cmp     [rsp+10C0h+ppidl], r15
0x18008f6df  jz      short loc_18008F750
0x18008f6e1  test    ebx, ebx
0x18008f6e3  js      loc_18008F657
0x18008f6e9  lea     rdi, [rsi+28h]
0x18008f6ed  mov     rcx, [rdi]; pidl
0x18008f6f0  call    cs:__imp_ILFree
0x18008f6f6  mov     rax, [rsp+10C0h+ppidl]
0x18008f6fb  mov     [rdi], rax
0x18008f6fe  mov     dword ptr [rsi+0C8h], 1
0x18008f708  jmp     loc_18008F557
0x18008f70d  mov     edx, 824h; unsigned __int64
0x18008f712  lea     rcx, [rsp+10C0h+Filename]; unsigned __int16 *
0x18008f717  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008f71c  mov     ebx, eax
0x18008f71e  movzx   eax, [rsp+10C0h+Filename]
0x18008f723  jmp     short loc_18008F6C2
0x18008f725  test    ax, ax
0x18008f728  jz      short loc_18008F6DA
0x18008f72a  lea     rcx, [rsp+10C0h+Filename]; pszFirst
0x18008f72f  call    ?DetectSpecialUrlHacks@@YAJPEBG@Z; DetectSpecialUrlHacks(ushort const *)
0x18008f734  mov     ebx, eax
0x18008f736  test    eax, eax
0x18008f738  js      short loc_18008F6DA
0x18008f73a  lea     r8, [rsp+10C0h+ppidl]
0x18008f73f  lea     rdx, [rsp+10C0h+Filename]
0x18008f744  mov     rcx, r14
0x18008f747  call    ConvertOutsideLocationToPidl
0x18008f74c  mov     ebx, eax
0x18008f74e  jmp     short loc_18008F6DA
0x18008f750  test    edi, edi
0x18008f752  jz      short loc_18008F6E1
0x18008f754  mov     [rsp+10C0h+Filename], r15w
0x18008f75a  xor     ecx, ecx; lpModuleName
0x18008f75c  call    cs:__imp_GetModuleHandleW
0x18008f762  mov     rcx, rax; hModule
0x18008f765  mov     r8d, 824h; nSize
0x18008f76b  lea     rdx, [rsp+10C0h+Filename]; lpFilename
0x18008f770  call    cs:__imp_GetModuleFileNameW
0x18008f776  lea     rcx, [rsp+10C0h+Filename]; pszPath
0x18008f77b  call    cs:__imp_PathStripToRootW
0x18008f781  lea     r8, [rsp+10C0h+ppidl]
0x18008f786  lea     rdx, [rsp+10C0h+Filename]
0x18008f78b  mov     rcx, r14
0x18008f78e  call    ConvertOutsideLocationToPidl
0x18008f793  mov     ebx, eax
0x18008f795  test    eax, eax
0x18008f797  js      loc_18008F657
0x18008f79d  jmp     loc_18008F6E1
0x18008f7a2  mov     rdx, [rsp+10C0h+ppidl]
0x18008f7a7  mov     rcx, rdi
0x18008f7aa  call    Pidl_Set
0x18008f7af  mov     rcx, [rsp+10C0h+ppidl]; pidl
0x18008f7b4  call    cs:__imp_ILFree
0x18008f7ba  jmp     loc_18008F615
0x18008f7bf  mov     rdx, [rsp+10C0h+ppidl]
0x18008f7c4  mov     rcx, rdi
0x18008f7c7  call    Pidl_Set
0x18008f7cc  mov     rcx, [rsp+10C0h+ppidl]; pidl
0x18008f7d1  call    cs:__imp_ILFree
0x18008f7d7  jmp     loc_18008F638
```
