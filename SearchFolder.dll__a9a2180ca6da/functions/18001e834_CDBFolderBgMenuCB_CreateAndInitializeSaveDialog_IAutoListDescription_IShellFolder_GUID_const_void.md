# CDBFolderBgMenuCB::_CreateAndInitializeSaveDialog(IAutoListDescription *,IShellFolder *,_GUID const &,void * *)

- ea: `0x18001e834`
- end: `0x18001ea9d`
- name: `?_CreateAndInitializeSaveDialog@CDBFolderBgMenuCB@@AEAAJPEAUIAutoListDescription@@PEAUIShellFolder@@AEBU_GUID@@PEAPEAX@Z`
- size: `617`
- prototype: `__int64 __fastcall(CDBFolderBgMenuCB *this, struct IAutoListDescription *, struct IShellFolder *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020cf4`

## callees

- `0x180006900`
- `0x18001e834`
- `0x18001f8ec`
- `0x18001f990`
- `0x180020ff4`
- `0x180021130`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemInKnownFolder` at `0x18001ea0a`
- `SHELL32!SHCreateItemInKnownFolder` at `0x18001ea0a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e8c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001e8c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e9db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e89e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e89e`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_CreateAndInitializeSaveDialog(
        CDBFolderBgMenuCB *this,
        struct IAutoListDescription *a2,
        struct IShellFolder *a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT Instance; // ebx
  struct IFileSaveDialog *v9; // rbx
  const struct _GUID *v10; // rdx
  CDBFolderBgMenuCB *v11; // rcx
  CDBFolderBgMenuCB *v12; // rcx
  struct IFileSaveDialog *ppv; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  void *v17; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  ppv = 0;
  *a5 = 0;
  Instance = CoCreateInstance(&CLSID_FileSaveDialog, 0, 1u, &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    LoadStringW(g_hinst, 0x233Fu, Buffer, 260);
    v18[0] = Buffer;
    v18[1] = L"*.search-ms";
    Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, __int64, _QWORD *))ppv->lpVtbl->SetFileTypes)(
                 ppv,
                 1,
                 v18);
    if ( Instance >= 0 )
    {
      Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, const wchar_t *))ppv->lpVtbl->SetDefaultExtension)(
                   ppv,
                   L"search-ms");
      if ( Instance >= 0 )
      {
        v15 = 0;
        Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, int *))ppv->lpVtbl->GetOptions)(ppv, &v15);
        if ( Instance >= 0 )
        {
          Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, _QWORD))ppv->lpVtbl->SetOptions)(ppv, v15 | 4u);
          if ( Instance >= 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, _QWORD, __int64))ppv->lpVtbl->SetCollectedProperties)(
                         ppv,
                         0,
                         1);
            if ( Instance >= 0 )
            {
              v9 = ppv;
              pv = 0;
              if ( (int)CDBFolderBgMenuCB::_GetNameFromTextFilter(this, (unsigned __int16 **)&pv) >= 0
                || CDBFolderBgMenuCB::_GetNameFromFolder(v11, a3, (unsigned __int16 **)&pv) >= 0 )
              {
                CDBFolderBgMenuCB::_SetDefaultNewAutoListName(v11, v10, v9, (const unsigned __int16 *)pv);
                CoTaskMemFree(pv);
              }
              v17 = 0;
              if ( SHCreateItemInKnownFolder(
                     &FOLDERID_SavedSearches,
                     0x8000u,
                     0,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     &v17) >= 0 )
              {
                ((void (__fastcall *)(struct IFileSaveDialog *, void *))ppv->lpVtbl->SetFolder)(ppv, v17);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
              }
              CDBFolderBgMenuCB::_SetPropertiesForNewAutoList(v12, a2, ppv);
              Instance = ((__int64 (__fastcall *)(struct IFileSaveDialog *, GUID *, void **))ppv->lpVtbl->QueryInterface)(
                           ppv,
                           &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab,
                           a5);
            }
          }
        }
      }
    }
    ((void (__fastcall *)(struct IFileSaveDialog *))ppv->lpVtbl->Release)(ppv);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001e834  mov     [rsp-8+arg_18], rbx
0x18001e839  push    rbp
0x18001e83a  push    rsi
0x18001e83b  push    rdi
0x18001e83c  push    r14
0x18001e83e  push    r15
0x18001e840  lea     rbp, [rsp-180h]
0x18001e848  sub     rsp, 280h
0x18001e84f  mov     rax, cs:__security_cookie
0x18001e856  xor     rax, rsp
0x18001e859  mov     [rbp+1A0h+var_30], rax
0x18001e860  mov     r14, [rbp+1A0h+arg_20]
0x18001e867  lea     rax, [rsp+2A0h+var_270]
0x18001e86c  mov     r15, rdx
0x18001e86f  mov     [rsp+2A0h+var_270], 0
0x18001e878  xor     edx, edx; pUnkOuter
0x18001e87a  mov     [rsp+2A0h+ppv], rax; ppv
0x18001e87f  mov     rsi, r8
0x18001e882  lea     r9, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab; riid
0x18001e889  mov     rdi, rcx
0x18001e88c  mov     qword ptr [r14], 0
0x18001e893  lea     rcx, CLSID_FileSaveDialog; rclsid
0x18001e89a  lea     r8d, [rdx+1]; dwClsContext
0x18001e89e  call    cs:__imp_CoCreateInstance
0x18001e8a4  mov     ebx, eax
0x18001e8a6  test    eax, eax
0x18001e8a8  js      loc_18001EA75
0x18001e8ae  mov     rcx, cs:g_hinst; hInstance
0x18001e8b5  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x18001e8ba  mov     r9d, 104h; cchBufferMax
0x18001e8c0  mov     edx, 233Fh; uID
0x18001e8c5  call    cs:__imp_LoadStringW
0x18001e8cb  mov     rcx, [rsp+2A0h+var_270]
0x18001e8d0  lea     rax, [rsp+2A0h+Buffer]
0x18001e8d5  mov     [rsp+2A0h+var_250], rax
0x18001e8da  lea     r8, [rsp+2A0h+var_250]
0x18001e8df  lea     rax, aSearchMs; "*.search-ms"
0x18001e8e6  mov     edx, 1
0x18001e8eb  mov     [rsp+2A0h+var_248], rax
0x18001e8f0  mov     rax, [rcx]
0x18001e8f3  mov     rax, [rax+20h]
0x18001e8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8fc  mov     ebx, eax
0x18001e8fe  test    eax, eax
0x18001e900  js      loc_18001EA64
0x18001e906  mov     rcx, [rsp+2A0h+var_270]
0x18001e90b  lea     rdx, aSearchMs_2; "search-ms"
0x18001e912  mov     rax, [rcx]
0x18001e915  mov     rax, [rax+0B0h]
0x18001e91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e921  mov     ebx, eax
0x18001e923  test    eax, eax
0x18001e925  js      loc_18001EA64
0x18001e92b  mov     rcx, [rsp+2A0h+var_270]
0x18001e930  lea     rdx, [rsp+2A0h+var_268]
0x18001e935  mov     [rsp+2A0h+var_268], 0
0x18001e93d  mov     rax, [rcx]
0x18001e940  mov     rax, [rax+50h]
0x18001e944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e949  mov     ebx, eax
0x18001e94b  test    eax, eax
0x18001e94d  js      loc_18001EA64
0x18001e953  mov     rcx, [rsp+2A0h+var_270]
0x18001e958  mov     edx, [rsp+2A0h+var_268]
0x18001e95c  or      edx, 4
0x18001e95f  mov     rax, [rcx]
0x18001e962  mov     rax, [rax+48h]
0x18001e966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e96b  mov     ebx, eax
0x18001e96d  test    eax, eax
0x18001e96f  js      loc_18001EA64
0x18001e975  mov     rcx, [rsp+2A0h+var_270]
0x18001e97a  xor     edx, edx
0x18001e97c  mov     rax, [rcx]
0x18001e97f  lea     r8d, [rdx+1]
0x18001e983  mov     rax, [rax+0E8h]
0x18001e98a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e98f  mov     ebx, eax
0x18001e991  test    eax, eax
0x18001e993  js      loc_18001EA64
0x18001e999  mov     rbx, [rsp+2A0h+var_270]
0x18001e99e  lea     rdx, [rsp+2A0h+pv]; unsigned __int16 **
0x18001e9a3  mov     rcx, rdi; this
0x18001e9a6  mov     [rsp+2A0h+pv], 0
0x18001e9af  call    ?_GetNameFromTextFilter@CDBFolderBgMenuCB@@AEAAJPEAPEAG@Z; CDBFolderBgMenuCB::_GetNameFromTextFilter(ushort * *)
0x18001e9b4  test    eax, eax
0x18001e9b6  jns     short loc_18001E9C9
0x18001e9b8  lea     r8, [rsp+2A0h+pv]; unsigned __int16 **
0x18001e9bd  mov     rdx, rsi; struct IShellFolder *
0x18001e9c0  call    ?_GetNameFromFolder@CDBFolderBgMenuCB@@AEAAJPEAUIShellFolder@@PEAPEAG@Z; CDBFolderBgMenuCB::_GetNameFromFolder(IShellFolder *,ushort * *)
0x18001e9c5  test    eax, eax
0x18001e9c7  js      short loc_18001E9E1
0x18001e9c9  mov     r9, [rsp+2A0h+pv]; unsigned __int16 *
0x18001e9ce  mov     r8, rbx; struct IFileSaveDialog *
0x18001e9d1  call    ?_SetDefaultNewAutoListName@CDBFolderBgMenuCB@@AEAAJAEBU_GUID@@PEAUIFileSaveDialog@@PEBG@Z; CDBFolderBgMenuCB::_SetDefaultNewAutoListName(_GUID const &,IFileSaveDialog *,ushort const *)
0x18001e9d6  mov     rcx, [rsp+2A0h+pv]; pv
0x18001e9db  call    cs:__imp_CoTaskMemFree
0x18001e9e1  lea     rax, [rsp+2A0h+var_258]
0x18001e9e6  mov     [rsp+2A0h+var_258], 0
0x18001e9ef  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001e9f6  mov     [rsp+2A0h+ppv], rax; ppv
0x18001e9fb  xor     r8d, r8d; pszItem
0x18001e9fe  lea     rcx, FOLDERID_SavedSearches; kfid
0x18001ea05  mov     edx, 8000h; dwKFFlags
0x18001ea0a  call    cs:__imp_SHCreateItemInKnownFolder
0x18001ea10  test    eax, eax
0x18001ea12  js      short loc_18001EA3B
0x18001ea14  mov     rcx, [rsp+2A0h+var_270]
0x18001ea19  mov     rdx, [rsp+2A0h+var_258]
0x18001ea1e  mov     rax, [rcx]
0x18001ea21  mov     rax, [rax+60h]
0x18001ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea2a  mov     rcx, [rsp+2A0h+var_258]
0x18001ea2f  mov     rax, [rcx]
0x18001ea32  mov     rax, [rax+10h]
0x18001ea36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea3b  mov     r8, [rsp+2A0h+var_270]; struct IFileSaveDialog *
0x18001ea40  mov     rdx, r15; struct IAutoListDescription *
0x18001ea43  call    ?_SetPropertiesForNewAutoList@CDBFolderBgMenuCB@@AEAAJPEAUIAutoListDescription@@PEAUIFileSaveDialog@@@Z; CDBFolderBgMenuCB::_SetPropertiesForNewAutoList(IAutoListDescription *,IFileSaveDialog *)
0x18001ea48  mov     rcx, [rsp+2A0h+var_270]
0x18001ea4d  lea     rdx, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab
0x18001ea54  mov     r8, r14
0x18001ea57  mov     rax, [rcx]
0x18001ea5a  mov     rax, [rax]
0x18001ea5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea62  mov     ebx, eax
0x18001ea64  mov     rcx, [rsp+2A0h+var_270]
0x18001ea69  mov     rax, [rcx]
0x18001ea6c  mov     rax, [rax+10h]
0x18001ea70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea75  mov     eax, ebx
0x18001ea77  mov     rcx, [rbp+1A0h+var_30]
0x18001ea7e  xor     rcx, rsp; StackCookie
0x18001ea81  call    __security_check_cookie
0x18001ea86  mov     rbx, [rsp+2A0h+arg_18]
0x18001ea8e  add     rsp, 280h
0x18001ea95  pop     r15
0x18001ea97  pop     r14
0x18001ea99  pop     rdi
0x18001ea9a  pop     rsi
0x18001ea9b  pop     rbp
0x18001ea9c  retn
```
