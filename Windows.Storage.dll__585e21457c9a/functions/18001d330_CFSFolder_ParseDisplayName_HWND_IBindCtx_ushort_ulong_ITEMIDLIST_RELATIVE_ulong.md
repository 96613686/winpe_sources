# CFSFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x18001d330`
- end: `0x18001e2af`
- name: `?ParseDisplayName@CFSFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `3967`
- prototype: `int(CFSFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001cc70`
- `0x18001d330`
- `0x18001e2c0`
- `0x18001e350`
- `0x18001e41c`
- `0x18001e5c0`
- `0x18001f3d0`
- `0x180040290`
- `0x1800432f0`
- `0x180068330`
- `0x18007c3ac`
- `0x18007e930`
- `0x18008e240`
- `0x1800a3080`
- `0x1800ceea0`
- `0x1800d0990`
- `0x1800d13a0`
- `0x1800d2dc0`
- `0x1800d4cc0`
- `0x1800d7800`
- `0x1800d8af0`
- `0x1800da5f0`
- `0x1801279b0`
- `0x1801464f8`
- `0x18016cd40`
- `0x1801d8550`
- `0x1801f3570`
- `0x180222370`
- `0x180222d0c`
- `0x180222f94`
- `0x1802d5380`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18001d539`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18001d539`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d50e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d50e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dbea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e13b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dbea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e13b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001dfce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001dfce`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001d649`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001d649`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18001e292`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18001e292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e05d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063e3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063e4a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d9d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001db10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e05d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e127`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063e3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18063e4a4`
- `MPR!WNetUseConnectionW` at `0x18001e0c3`
- `MPR!WNetUseConnectionW` at `0x18001e184`
- `MPR!WNetUseConnectionW` at `0x18001e0c3`
- `MPR!WNetUseConnectionW` at `0x18001e184`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d42f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d449`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d463`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d47d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d48c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d42f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d449`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d463`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d47d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18001d48c`

## string_xrefs

- `0x18001df5c`: `FindDataFullPath`
- `0x18063e3ad`: `FindDataFullPath`
- `0x18001deb4`: `Don't Force Create`
- `0x18001da45`: `ParseAndCreateItem`
- `0x18001d3c2`: `ItemCacheContext`
- `0x18001d439`: `FSFolder_ConvertToSidString`
- `0x18001d41c`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::ParseDisplayName(
        IUnknown **this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  struct IBindCtx *v8; // r14
  LPVOID *v10; // r12
  unsigned int *v11; // rbx
  int v12; // ebx
  int v13; // eax
  int IDListFromName; // esi
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // r13
  PWSTR v18; // rax
  PWSTR v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // r8
  unsigned __int16 v23; // ax
  unsigned __int16 *v24; // rcx
  PWSTR v25; // r15
  int v26; // r12d
  CFSFolder *v27; // rbx
  const WCHAR *v28; // rcx
  HRESULT v29; // eax
  unsigned int v30; // esi
  int v31; // ebx
  int v32; // ebx
  int DataForPathWithTimeout; // eax
  BOOL v34; // eax
  char v35; // bl
  unsigned int v36; // esi
  enum FOLDER_ENUM_MODE FolderEnumMode; // eax
  HWND v38; // rdi
  IUnknown *v39; // rcx
  void *v40; // r14
  struct _ITEMIDLIST_RELATIVE *v41; // r15
  struct _ITEMIDLIST_RELATIVE *v42; // rdx
  unsigned int v43; // esi
  int v44; // r8d
  __int64 v45; // rcx
  size_t v46; // rbx
  unsigned __int16 *v47; // rdx
  __int64 v48; // rcx
  struct _ITEMIDLIST_RELATIVE *v49; // rax
  struct _ITEMIDLIST_RELATIVE *v50; // rdi
  struct _ITEMIDLIST_RELATIVE *v51; // rdi
  int v52; // ebx
  IShellFolder *v53; // rbx
  ITEMIDLIST *v54; // r15
  HRESULT v55; // ebx
  unsigned __int16 v56; // ax
  struct _ITEMIDLIST_RELATIVE *v57; // rdx
  unsigned __int16 *v58; // rcx
  __int64 v60; // rcx
  unsigned __int16 *v61; // rdx
  unsigned __int16 *v62; // r8
  unsigned __int16 v63; // ax
  _WORD *v64; // rcx
  unsigned __int16 **v65; // rax
  int FolderPath; // eax
  DWORD TickCount; // eax
  signed int v68; // eax
  signed int v69; // eax
  int FileSystemBindData; // eax
  struct tagWIN32_FIND_DATA_EX *v71; // rbx
  unsigned __int16 **v72; // rax
  int v73; // edi
  struct tagWIN32_FIND_DATA_EX *v74; // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  int lpAccessName; // [rsp+28h] [rbp-D8h]
  IUnknown **lpBufferSize; // [rsp+30h] [rbp-D0h]
  char lpBufferSizea; // [rsp+30h] [rbp-D0h]
  CFSFolder *v79; // [rsp+50h] [rbp-B0h]
  PWSTR ppszPathOut; // [rsp+68h] [rbp-98h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v83; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  _NETRESOURCEW NetResource; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  struct tagWIN32_FIND_DATA_EX *v87[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v88[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v89[624]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v8 = a3;
  Src = this;
  v10 = (LPVOID *)a6;
  v11 = a7;
  v83 = a7;
  if ( a6 )
  {
    *a6 = 0;
    if ( a4 )
    {
      if ( *a4 )
      {
        punk = 0;
        pv = 0;
        if ( a3
          && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a3->lpVtbl->GetObjectParam)(
               a3,
               L"ItemCacheContext",
               &pv) >= 0 )
        {
          v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))pv)(
                  pv,
                  &GUID_0000000e_0000_0000_c000_000000000046,
                  &punk);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( v12 >= 0 )
          {
            this[37] = (IUnknown *)L"FSFolder_ResolveSidToUserName";
            IUnknown_Set(this + 35, punk);
            this[40] = (IUnknown *)L"FSFolder_ConvertToSidString";
            IUnknown_Set(this + 38, punk);
            this[43] = (IUnknown *)L"FSFolder_InplaceShareEngine";
            IUnknown_Set(this + 41, punk);
            this[46] = (IUnknown *)L"FSFolder_SmbShareEngine";
            IUnknown_Set(this + 44, punk);
            IUnknown_Set(this + 47, punk);
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          }
          v11 = v83;
        }
        v79 = (CFSFolder *)(this - 6);
        v13 = CFSFolder::TrySimpleParse((CFSFolder *)(this - 6), a4, v8, a6);
        IDListFromName = v13;
        if ( v13 )
        {
          if ( v13 != 1 )
            goto LABEL_119;
          v15 = -1;
          do
            ++v15;
          while ( a4[v15] );
          v16 = v15 + 1;
          v88[0] = 0;
          if ( !is_mul_ok(v16, 2u) )
          {
            IDListFromName = -2147024362;
            goto LABEL_92;
          }
          v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
          if ( !v17 )
          {
            IDListFromName = -2147024882;
            goto LABEL_92;
          }
          *v17 = 0;
          v18 = StrChrW(a4, 0x5Cu);
          v19 = v18;
          if ( v18 )
          {
            if ( v18 <= a4 )
            {
LABEL_129:
              IDListFromName = -2147024809;
              goto LABEL_118;
            }
            if ( v16 )
            {
              if ( v16 > 0x7FFFFFFF )
              {
                *v17 = 0;
              }
              else
              {
                v20 = (int)(v18 - a4);
                if ( v20 > 0x7FFFFFFE )
                {
                  *v17 = 0;
                }
                else
                {
                  v21 = a4;
                  v22 = v17;
                  do
                  {
                    if ( !v20 )
                      break;
                    v23 = *v21;
                    if ( !*v21 )
                      break;
                    ++v21;
                    *v22++ = v23;
                    --v20;
                    --v16;
                  }
                  while ( v16 );
                  v24 = v22 - 1;
                  if ( v16 )
                    v24 = v22;
                  *v24 = 0;
                }
              }
            }
            v25 = 0;
            if ( v19[1] )
              v25 = v19 + 1;
          }
          else
          {
            if ( v16 )
            {
              if ( v16 > 0x7FFFFFFF )
              {
LABEL_128:
                *v17 = 0;
                goto LABEL_129;
              }
              v60 = 2147483646;
              v61 = a4;
              v62 = v17;
              do
              {
                if ( !v60 )
                  break;
                v63 = *v61;
                if ( !*v61 )
                  break;
                ++v61;
                *v62++ = v63;
                --v60;
                --v16;
              }
              while ( v16 );
              v58 = v62 - 1;
              if ( v16 )
                v58 = v62;
              *v58 = 0;
              IDListFromName = -2147024774;
              if ( v16 )
                IDListFromName = 0;
            }
            else
            {
              IDListFromName = -2147024809;
            }
            v25 = 0;
            if ( IDListFromName < 0 )
            {
LABEL_118:
              LocalFree(v17);
LABEL_119:
              if ( IDListFromName >= 0 )
                return (unsigned int)IDListFromName;
LABEL_92:
              if ( *v10 )
              {
                CoTaskMemFree(*v10);
                *v10 = 0;
              }
              return (unsigned int)IDListFromName;
            }
          }
          if ( (unsigned int)ValidPathSegment(v17) )
          {
            punk = 0;
            v88[0] = 0;
            if ( v25 )
            {
              v26 = 0;
              if ( (*((_BYTE *)Src + 488) & 0x20) != 0 )
              {
                v27 = v79;
                IDListFromName = CFSFolder::_CreateIDListFromName(
                                   v79,
                                   v17,
                                   0x10u,
                                   0,
                                   v8,
                                   (struct _ITEMID_CHILD **)&punk);
LABEL_62:
                if ( (unsigned int)(IDListFromName + 2147024894) <= 1 )
                {
                  if ( (unsigned int)BindCtx_ContainsObject(v8, L"FindDataFullPath") )
                  {
                    IDListFromName = -2147024891;
                    goto LABEL_138;
                  }
                  v87[0] = 0;
                  if ( (int)CFSFolder::_GetFindDataByHandleFromName(v27, a4, v87) >= 0 )
                  {
                    ppszPathOut = 0;
                    FileSystemBindData = CreateFileSystemBindData(
                                           &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
                                           (void **)&ppszPathOut);
                    IDListFromName = FileSystemBindData;
                    v71 = v87[0];
                    if ( FileSystemBindData >= 0 )
                    {
                      IDListFromName = (*(__int64 (__fastcall **)(PWSTR, struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)ppszPathOut + 24LL))(
                                         ppszPathOut,
                                         v87[0]);
                      if ( IDListFromName >= 0 )
                      {
                        IDListFromName = (*(__int64 (__fastcall **)(PWSTR, _QWORD))(*(_QWORD *)ppszPathOut + 40LL))(
                                           ppszPathOut,
                                           *((_QWORD *)v71 + 74));
                        if ( IDListFromName >= 0 )
                        {
                          IDListFromName = BindCtx_RegisterObjectParam(v8, L"FindDataFullPath", ppszPathOut, v88);
                          if ( IDListFromName >= 0 )
                          {
                            v8 = (struct IBindCtx *)v88[0];
                            IDListFromName = -2147024891;
                          }
                        }
                      }
                      (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPathOut + 16LL))(ppszPathOut);
                    }
                    CoTaskMemFree(v71);
                    v27 = v79;
                  }
                }
LABEL_63:
                if ( IDListFromName > -2147023584 )
                {
                  if ( IDListFromName != -2147023106 && IDListFromName != -2147023570 && IDListFromName != -2147023499 )
                    goto LABEL_70;
                }
                else if ( IDListFromName != -2147023584
                       && IDListFromName != -2147024891
                       && IDListFromName != -2147024810
                       && IDListFromName != -2147024672
                       && IDListFromName != -2147023652 )
                {
                  if ( (unsigned int)(IDListFromName + 2147024894) <= 1
                    && !v25
                    && (BindCtx_GetMode(v8, 0) & 0x1000) != 0
                    && !(unsigned int)BindCtx_ContainsObject(v8, L"Don't Force Create") )
                  {
                    IDListFromName = CFSFolder::_CreateIDListFromName(
                                       v27,
                                       v17,
                                       0x80u,
                                       v26,
                                       v8,
                                       (struct _ITEMID_CHILD **)&punk);
                  }
                  goto LABEL_70;
                }
LABEL_138:
                if ( v26 )
                {
                  if ( (*((_BYTE *)v27 + 536) & 0x20) != 0 )
                  {
                    pv = 0;
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                      &pv,
                      0);
                    if ( (int)CFSFolder::GetPathForFileAccess(v27, v17, (PWSTR *)&pv) >= 0 && PathIsUNCW((LPCWSTR)pv) )
                    {
                      memset(&NetResource, 0, 24);
                      *(_OWORD *)&NetResource.lpComment = 0;
                      NetResource.lpRemoteName = (LPWSTR)pv;
                      v87[0] = 0;
                      v38 = a2;
                      v68 = WNetUseConnectionW(a2, &NetResource, 0, 0, a2 != 0 ? 8 : 0, 0, 0, 0);
                      IDListFromName = v68;
                      if ( v68 > 0 )
                        IDListFromName = (unsigned __int16)v68 | 0x80070000;
                      if ( IDListFromName == -2147024629 || IDListFromName == -2147024843 )
                      {
                        v72 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v87);
                        if ( CFSFolder::GetFolderPath(v79, v72) >= 0 )
                        {
                          memset(&NetResource, 0, 24);
                          *(_OWORD *)&NetResource.lpComment = 0;
                          NetResource.lpRemoteName = (LPWSTR)v87[0];
                          v69 = WNetUseConnectionW(a2, &NetResource, 0, 0, a2 != 0 ? 8 : 0, 0, 0, 0);
                          IDListFromName = v69;
                          if ( v69 > 0 )
                            IDListFromName = (unsigned __int16)v69 | 0x80070000;
                        }
                      }
                      v27 = v79;
                      if ( IDListFromName >= 0 )
                        IDListFromName = CFSFolder::_CreateIDListFromName(
                                           v79,
                                           v17,
                                           0xFFFFFFFF,
                                           v26,
                                           v8,
                                           (struct _ITEMID_CHILD **)&punk);
                      if ( v87[0] )
                        CoTaskMemFree(v87[0]);
                    }
                    else
                    {
                      v38 = a2;
                    }
                    if ( pv )
                      LocalFree(pv);
                    goto LABEL_71;
                  }
                  v73 = 1;
                  if ( !(unsigned int)SHSkipJunctionBinding(v8, 0) )
                    v73 = 7;
                  v87[0] = 0;
                  if ( (int)GetFindDataFromBindCtx(v8, v87) >= 0
                    || (int)CFSFolder::_GetFindDataByHandleFromName(v27, v17, v87) >= 0 )
                  {
                    v74 = v87[0];
                    StringCchCopyW((unsigned __int16 *)v87[0] + 22, 0x104u, v17);
                    lpBufferSize = &punk;
                    lpAccessName = v73;
                    IDListFromName = CFSFolder::_CreateIDListWithBindCtx(v79, v74, 0, 0);
                    CoTaskMemFree(v74);
                    v27 = v79;
                  }
                }
                else
                {
                  IDListFromName = CFSFolder::_CreateIDListFromName(
                                     v27,
                                     v17,
                                     0x10u,
                                     0,
                                     v8,
                                     (struct _ITEMID_CHILD **)&punk);
                }
LABEL_70:
                v38 = a2;
LABEL_71:
                v39 = punk;
                v10 = (LPVOID *)a6;
                *a6 = (struct _ITEMIDLIST_RELATIVE *)punk;
                if ( IDListFromName >= 0 )
                {
                  if ( v25 )
                  {
                    v87[0] = 0;
                    IDListFromName = (*(__int64 (__fastcall **)(void *, IUnknown *, struct IBindCtx *, GUID *, struct tagWIN32_FIND_DATA_EX **, int, IUnknown **))(*(_QWORD *)Src + 40LL))(
                                       Src,
                                       v39,
                                       v8,
                                       &GUID_000214e6_0000_0000_c000_000000000046,
                                       v87,
                                       lpAccessName,
                                       lpBufferSize);
                    if ( IDListFromName >= 0 )
                    {
                      Src = 0;
                      IDListFromName = (*(__int64 (__fastcall **)(struct tagWIN32_FIND_DATA_EX *, HWND, struct IBindCtx *, PWSTR, _QWORD, void **, unsigned int *))(*(_QWORD *)v87[0] + 24LL))(
                                         v87[0],
                                         v38,
                                         v8,
                                         v25,
                                         0,
                                         &Src,
                                         v83);
                      if ( IDListFromName >= 0 )
                      {
                        v40 = Src;
                        v41 = *a6;
                        if ( Src && v41 )
                        {
                          v42 = *a6;
                          v43 = 2;
                          v44 = 2;
                          do
                          {
                            v45 = *(unsigned __int16 *)v42;
                            if ( !(_WORD)v45 )
                              break;
                            v44 += v45;
                            v42 = (struct _ITEMIDLIST_RELATIVE *)((char *)v42 + v45);
                          }
                          while ( v42 );
                          v46 = (unsigned int)(v44 - 2);
                          v47 = (unsigned __int16 *)Src;
                          do
                          {
                            v48 = *v47;
                            if ( !(_WORD)v48 )
                              break;
                            v43 += v48;
                            v47 = (unsigned __int16 *)((char *)v47 + v48);
                          }
                          while ( v47 );
                          v49 = (struct _ITEMIDLIST_RELATIVE *)ILCreate(v43 + (unsigned int)v46);
                          v50 = v49;
                          if ( v49 )
                          {
                            memcpy_0(v49, v41, v46);
                            memcpy_0((char *)v50 + v46, v40, v43);
                          }
                          *a6 = v50;
                          IDListFromName = 0;
                          if ( !v50 )
                            IDListFromName = -2147024882;
                          CoTaskMemFree(v41);
                          CoTaskMemFree(v40);
                        }
                        else
                        {
                          IDListFromName = 0;
                          if ( !v41 )
                          {
                            if ( Src )
                              *a6 = (struct _ITEMIDLIST_RELATIVE *)Src;
                            else
                              IDListFromName = -2147024809;
                          }
                        }
                      }
                      (*(void (__fastcall **)(struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)v87[0] + 16LL))(v87[0]);
                    }
                  }
                  else
                  {
                    if ( v83 && *v83 )
                    {
                      (*(void (__fastcall **)(void *, __int64, IUnknown **))(*(_QWORD *)Src + 72LL))(Src, 1, &punk);
                      v39 = punk;
                    }
                    CFSFolder::_SetParseAndCreateItem(v27, v8, (const struct _ITEMIDLIST_RELATIVE *)v39);
                  }
                }
                if ( v88[0] )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v88[0] + 16LL))(v88[0]);
                goto LABEL_118;
              }
            }
            else
            {
              v26 = 1;
            }
            memset_0(v89, 0, 0x268u);
            if ( (unsigned int)PathIsInvalidW(v17) )
            {
              IDListFromName = -2147023696;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x901,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)0x800704B0LL,
                ppv);
              v27 = v79;
              goto LABEL_61;
            }
            ppszPathOut = 0;
            pv = 0;
            v27 = v79;
            v28 = (const WCHAR *)*((_QWORD *)v79 + 56);
            if ( !v28 )
            {
              v65 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
              FolderPath = CFSFolder::GetFolderPath(v79, v65);
              IDListFromName = FolderPath;
              if ( FolderPath < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4E6,
                  (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                  (const char *)(unsigned int)FolderPath,
                  ppv);
                if ( pv )
                  CoTaskMemFree(pv);
                goto LABEL_140;
              }
              v28 = (const WCHAR *)pv;
            }
            v29 = PathAllocCombine(v28, v17, 1u, &ppszPathOut);
            IDListFromName = v29;
            if ( v29 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x4EB,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v29,
                ppv);
            if ( pv )
              CoTaskMemFree(pv);
            if ( IDListFromName >= 0 )
            {
              v30 = 0;
              v87[0] = 0;
              v31 = -2147467262;
              pv = 0;
              if ( v8
                && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))v8->lpVtbl->GetObjectParam)(
                     v8,
                     L"bind context timeout value",
                     &pv) >= 0 )
              {
                v32 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct tagWIN32_FIND_DATA_EX **))pv)(
                        pv,
                        &GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000,
                        v87);
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                if ( v32 < 0 )
                  goto LABEL_43;
                pv = 0;
                v31 = (*(__int64 (__fastcall **)(struct tagWIN32_FIND_DATA_EX *, LPVOID *, __int64, __int64))(*(_QWORD *)v87[0] + 48LL))(
                        v87[0],
                        &pv,
                        1,
                        8);
                if ( v31 >= 0 )
                {
                  TickCount = GetTickCount();
                  if ( TickCount - (unsigned int)pv <= HIDWORD(pv) )
                    v30 = HIDWORD(pv) - TickCount + (_DWORD)pv - 1;
                }
                (*(void (__fastcall **)(struct tagWIN32_FIND_DATA_EX *))(*(_QWORD *)v87[0] + 16LL))(v87[0]);
              }
              if ( v31 >= 0 )
              {
                v27 = v79;
                if ( (unsigned int)CFSFolder::_IsNetFolder(v79) )
                {
                  DataForPathWithTimeout = GetFindDataForPathWithTimeout(
                                             ppszPathOut,
                                             v26,
                                             v30,
                                             (struct tagWIN32_FIND_DATA_EX *)v89);
LABEL_45:
                  IDListFromName = DataForPathWithTimeout;
                  if ( DataForPathWithTimeout >= 0 )
                  {
                    if ( ppszPathOut )
                      LocalFree(ppszPathOut);
                    v34 = 0;
                    if ( v8 )
                    {
                      v87[0] = (struct tagWIN32_FIND_DATA_EX *)16;
                      v87[1] = 0;
                      v34 = ((int (__fastcall *)(struct IBindCtx *, struct tagWIN32_FIND_DATA_EX **))v8->lpVtbl->GetBindOptions)(
                              v8,
                              v87) >= 0
                         && HIDWORD(v87[0]) == 2;
                    }
                    v35 = 1;
                    if ( !v34 )
                      v35 = 7;
                    ppszPathOut = 0;
                    v36 = -1091633152;
                    if ( (v89[0] & 0x10) == 0 && v8 )
                    {
                      if ( (int)_BindCtx_GetValue<unsigned short *>(v8, L"ExplicitProgid", &ppszPathOut) >= 0 )
                      {
                        v36 = -1091633126;
                        pv = 0;
                        goto LABEL_56;
                      }
                      ppszPathOut = 0;
                      if ( (int)_BindCtx_GetValue<unsigned short *>(v8, L"ExplicitAssociationApp", &ppszPathOut) >= 0 )
                      {
                        v36 = -1091633125;
                        pv = 0;
                        goto LABEL_56;
                      }
                    }
                    pv = 0;
                    if ( !v8 )
                    {
LABEL_58:
                      FolderEnumMode = BindCtx_GetFolderEnumMode(v8);
                      lpBufferSizea = v35;
                      v27 = v79;
                      IDListFromName = CFSFolder::_CreateIDList(
                                         v79,
                                         (__int64)v89,
                                         0,
                                         0,
                                         (__int64)ppszPathOut,
                                         v36,
                                         lpBufferSizea,
                                         FolderEnumMode,
                                         &punk);
                      if ( IDListFromName >= 0 )
                      {
                        if ( ppszPathOut )
                        {
                          IDListFromName = _BindCtx_SetValue<int>(v8, L"ExplicitAssociationSuccessful", 1);
                          if ( IDListFromName < 0 )
                          {
                            CoTaskMemFree(punk);
                            punk = 0;
                          }
                        }
                      }
                      CoTaskMemFree(ppszPathOut);
                      goto LABEL_61;
                    }
LABEL_56:
                    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))v8->lpVtbl->GetObjectParam)(
                           v8,
                           L"Win7FileSystemIdList",
                           &pv) >= 0 )
                    {
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                      v35 |= 8u;
                    }
                    goto LABEL_58;
                  }
LABEL_141:
                  if ( ppszPathOut )
                    LocalFree(ppszPathOut);
LABEL_61:
                  if ( v26 )
                    goto LABEL_63;
                  goto LABEL_62;
                }
LABEL_44:
                DataForPathWithTimeout = GetFindDataForPath(ppszPathOut);
                goto LABEL_45;
              }
LABEL_43:
              v27 = v79;
              goto LABEL_44;
            }
LABEL_140:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x906,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)IDListFromName,
              ppv);
            goto LABEL_141;
          }
          goto LABEL_128;
        }
        if ( v11 && *v11 )
        {
          v88[0] = ILFindLastID((LPCITEMIDLIST)*a6);
          ((void (__fastcall *)(IUnknown **, __int64, _QWORD *, unsigned int *))(*this)[9].lpVtbl)(this, 1, v88, v11);
        }
        v51 = *a6;
        ppszPathOut = 0;
        v88[0] = 0;
        if ( v8
          && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, _QWORD *))v8->lpVtbl->GetObjectParam)(
               v8,
               L"Parse Translate Aliases",
               v88) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v88[0] + 16LL))(v88[0]);
          return (unsigned int)IDListFromName;
        }
        ppszPathOut = 0;
        v83 = 0;
        if ( !v8 )
          return (unsigned int)IDListFromName;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, unsigned int **))v8->lpVtbl->GetObjectParam)(
               v8,
               L"ParseAndCreateItem",
               &v83) < 0 )
          return (unsigned int)IDListFromName;
        v52 = (**(__int64 (__fastcall ***)(unsigned int *, GUID *, PWSTR *))v83)(
                v83,
                &GUID_67efed0e_e827_4408_b493_78f3982b685c,
                &ppszPathOut);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
        if ( v52 < 0 )
          return (unsigned int)IDListFromName;
        punk = 0;
        if ( ((int (__fastcall *)(char *, GUID *, IUnknown **))(*(this - 6))->lpVtbl)(
               (char *)this - 48,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &punk) < 0 )
        {
LABEL_112:
          (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPathOut + 16LL))(ppszPathOut);
          return (unsigned int)IDListFromName;
        }
        pv = 0;
        if ( v51 )
        {
          v53 = (IShellFolder *)punk;
          if ( punk )
          {
            if ( !*(_WORD *)v51 || (v64 = (_WORD *)((char *)v51 + *(unsigned __int16 *)v51)) == 0 || !*v64 )
            {
              v55 = ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))punk->lpVtbl->QueryInterface)(
                      punk,
                      &GUID_ff314a1e_06fa_4f3a_84be_7aa1c6be2470,
                      &pv);
LABEL_105:
              if ( v55 >= 0 )
              {
                v56 = *(_WORD *)v51;
                if ( *(_WORD *)v51 )
                {
                  do
                  {
                    v57 = v51;
                    v51 = (struct _ITEMIDLIST_RELATIVE *)((char *)v51 + v56);
                    v56 = *(_WORD *)v51;
                  }
                  while ( *(_WORD *)v51 );
                }
                else
                {
                  v57 = v51;
                }
                v83 = 0;
                if ( (*(int (__fastcall **)(LPVOID, struct _ITEMIDLIST_RELATIVE *, GUID *, unsigned int **))(*(_QWORD *)pv + 24LL))(
                       pv,
                       v57,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &v83) >= 0 )
                {
                  (*(void (__fastcall **)(PWSTR, unsigned int *))(*(_QWORD *)ppszPathOut + 24LL))(ppszPathOut, v83);
                  (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v83 + 16LL))(v83);
                }
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
              }
              goto LABEL_111;
            }
          }
          v54 = (ITEMIDLIST *)ILCloneParent(v51);
          if ( v54 )
          {
            v55 = SHBindToObject(v53, v54, v8, &GUID_ff314a1e_06fa_4f3a_84be_7aa1c6be2470, &pv);
            CoTaskMemFree(v54);
            goto LABEL_105;
          }
        }
LABEL_111:
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        goto LABEL_112;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d330  push    rbp
0x18001d332  push    rbx
0x18001d333  push    rsi
0x18001d334  push    rdi
0x18001d335  push    r12
0x18001d337  push    r13
0x18001d339  push    r14
0x18001d33b  push    r15
0x18001d33d  lea     rbp, [rsp-268h]
0x18001d345  sub     rsp, 368h
0x18001d34c  mov     rax, cs:__security_cookie
0x18001d353  xor     rax, rsp
0x18001d356  mov     [rbp+2A0h+var_50], rax
0x18001d35d  mov     rdi, r9
0x18001d360  mov     r14, r8
0x18001d363  mov     [rsp+3A0h+hwndOwner], rdx
0x18001d368  mov     r13, rcx
0x18001d36b  mov     [rbp+2A0h+Src], rcx
0x18001d36f  mov     r12, [rbp+2A0h+arg_28]
0x18001d376  mov     [rsp+3A0h+var_340], r12
0x18001d37b  mov     rbx, [rbp+2A0h+arg_30]
0x18001d382  mov     [rsp+3A0h+var_328], rbx
0x18001d387  test    r12, r12
0x18001d38a  jz      loc_18001DC80
0x18001d390  xor     eax, eax
0x18001d392  mov     [r12], rax
0x18001d396  test    r9, r9
0x18001d399  jz      loc_18001DC80
0x18001d39f  cmp     [r9], ax
0x18001d3a3  jz      loc_18001DC80
0x18001d3a9  mov     [rsp+3A0h+punk], rax
0x18001d3ae  mov     [rbp+2A0h+pv], rax
0x18001d3b2  test    r8, r8
0x18001d3b5  jz      loc_18001D4A8
0x18001d3bb  mov     rax, [r8]
0x18001d3be  lea     r8, [rbp+2A0h+pv]
0x18001d3c2  lea     rdx, aItemcacheconte; "ItemCacheContext"
0x18001d3c9  mov     rcx, r14
0x18001d3cc  mov     rax, [rax+50h]
0x18001d3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3d5  test    eax, eax
0x18001d3d7  js      loc_18001D4A8
0x18001d3dd  mov     rcx, [rbp+2A0h+pv]
0x18001d3e1  mov     rax, [rcx]
0x18001d3e4  lea     r8, [rsp+3A0h+punk]
0x18001d3e9  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x18001d3f0  mov     rax, [rax]
0x18001d3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3f8  mov     ebx, eax
0x18001d3fa  mov     rdx, [rbp+2A0h+pv]
0x18001d3fe  mov     rcx, [rdx]
0x18001d401  mov     rax, [rcx+10h]
0x18001d405  mov     rcx, rdx
0x18001d408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d40d  test    ebx, ebx
0x18001d40f  js      loc_18001D4A3
0x18001d415  lea     rbx, [r13+118h]
0x18001d41c  lea     rax, aFsfolderResolv; "FSFolder_ResolveSidToUserName"
0x18001d423  mov     [rbx+10h], rax
0x18001d427  mov     rdx, [rsp+3A0h+punk]; punk
0x18001d42c  mov     rcx, rbx; ppunk
0x18001d42f  call    cs:__imp_IUnknown_Set
0x18001d435  lea     rcx, [rbx+18h]; ppunk
0x18001d439  lea     rax, aFsfolderConver; "FSFolder_ConvertToSidString"
0x18001d440  mov     [rcx+10h], rax
0x18001d444  mov     rdx, [rsp+3A0h+punk]; punk
0x18001d449  call    cs:__imp_IUnknown_Set
0x18001d44f  lea     rcx, [rbx+30h]; ppunk
0x18001d453  lea     rax, aFsfolderInplac; "FSFolder_InplaceShareEngine"
0x18001d45a  mov     [rcx+10h], rax
0x18001d45e  mov     rdx, [rsp+3A0h+punk]; punk
0x18001d463  call    cs:__imp_IUnknown_Set
0x18001d469  lea     rcx, [rbx+48h]; ppunk
0x18001d46d  lea     rax, aFsfolderSmbsha; "FSFolder_SmbShareEngine"
0x18001d474  mov     [rcx+10h], rax
0x18001d478  mov     rdx, [rsp+3A0h+punk]; punk
0x18001d47d  call    cs:__imp_IUnknown_Set
0x18001d483  lea     rcx, [rbx+60h]; ppunk
0x18001d487  mov     rdx, [rsp+3A0h+punk]; punk
0x18001d48c  call    cs:__imp_IUnknown_Set
0x18001d492  mov     rcx, [rsp+3A0h+punk]
0x18001d497  mov     rax, [rcx]
0x18001d49a  mov     rax, [rax+10h]
0x18001d49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a3  mov     rbx, [rsp+3A0h+var_328]
0x18001d4a8  lea     r15, [r13-30h]
0x18001d4ac  mov     [rsp+3A0h+var_350], r15
0x18001d4b1  mov     r9, r12; struct _ITEMIDLIST_RELATIVE **
0x18001d4b4  mov     r8, r14; struct IBindCtx *
0x18001d4b7  mov     rdx, rdi; pszStart
0x18001d4ba  mov     rcx, r15; this
0x18001d4bd  call    ?TrySimpleParse@CFSFolder@@IEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::TrySimpleParse(ushort const *,IBindCtx *,_ITEMIDLIST_RELATIVE * *)
0x18001d4c2  mov     esi, eax
0x18001d4c4  test    eax, eax
0x18001d4c6  jz      loc_18001D9EA
0x18001d4cc  cmp     eax, 1
0x18001d4cf  jnz     loc_18001DBF0
0x18001d4d5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001d4dc  nop     dword ptr [rax+00h]
0x18001d4e0  inc     rbx
0x18001d4e3  cmp     word ptr [rdi+rbx*2], 0
0x18001d4e8  jnz     short loc_18001D4E0
0x18001d4ea  inc     rbx
0x18001d4ed  mov     [rbp+2A0h+var_2D0], 0
0x18001d4f5  mov     eax, 2
0x18001d4fa  mul     rbx
0x18001d4fd  test    rdx, rdx
0x18001d500  jnz     loc_18001D9C5
0x18001d506  mov     rdx, rax; uBytes
0x18001d509  mov     ecx, 40h ; '@'; uFlags
0x18001d50e  call    cs:__imp_LocalAlloc
0x18001d514  mov     r13, rax
0x18001d517  xor     esi, esi
0x18001d519  mov     eax, 8007000Eh
0x18001d51e  test    r13, r13
0x18001d521  cmovz   esi, eax
0x18001d524  jz      loc_18001D9CA
0x18001d52a  xor     eax, eax
0x18001d52c  mov     [r13+0], ax
0x18001d531  mov     edx, 5Ch ; '\'; wMatch
0x18001d536  mov     rcx, rdi; pszStart
0x18001d539  call    cs:__imp_StrChrW
0x18001d53f  mov     r9, rax
0x18001d542  test    rax, rax
0x18001d545  jz      loc_18001DC1D
0x18001d54b  cmp     rax, rdi
0x18001d54e  jbe     loc_18001DC76
0x18001d554  test    rbx, rbx
0x18001d557  jz      short loc_18001D5B5
0x18001d559  cmp     rbx, 7FFFFFFFh
0x18001d560  ja      loc_18001E1A2
0x18001d566  sub     rax, rdi
0x18001d569  sar     rax, 1
0x18001d56c  movsxd  rdx, eax
0x18001d56f  mov     ecx, 7FFFFFFEh
0x18001d574  cmp     rdx, rcx
0x18001d577  ja      loc_18001E1AE
0x18001d57d  mov     rcx, rdi
0x18001d580  mov     r8, r13
0x18001d583  test    rdx, rdx
0x18001d586  jz      short loc_18001D5A5
0x18001d588  movzx   eax, word ptr [rcx]
0x18001d58b  test    ax, ax
0x18001d58e  jz      short loc_18001D5A5
0x18001d590  add     rcx, 2
0x18001d594  mov     [r8], ax
0x18001d598  add     r8, 2
0x18001d59c  dec     rdx
0x18001d59f  sub     rbx, 1
0x18001d5a3  jnz     short loc_18001D583
0x18001d5a5  lea     rcx, [r8-2]
0x18001d5a9  test    rbx, rbx
0x18001d5ac  cmovnz  rcx, r8
0x18001d5b0  xor     eax, eax
0x18001d5b2  mov     [rcx], ax
0x18001d5b5  lea     rax, [r9+2]
0x18001d5b9  xor     r15d, r15d
0x18001d5bc  cmp     [rax], r15w
0x18001d5c0  cmovnz  r15, rax
0x18001d5c4  mov     rcx, r13; unsigned __int16 *
0x18001d5c7  call    ?ValidPathSegment@@YAHPEBG@Z; ValidPathSegment(ushort const *)
0x18001d5cc  test    eax, eax
0x18001d5ce  jz      loc_18001DC6F
0x18001d5d4  xor     ebx, ebx
0x18001d5d6  mov     [rsp+3A0h+punk], rbx
0x18001d5db  mov     [rbp+2A0h+var_2D0], rbx
0x18001d5df  test    r15, r15
0x18001d5e2  jz      loc_18001DD4C
0x18001d5e8  mov     r12d, ebx
0x18001d5eb  mov     rax, [rbp+2A0h+Src]
0x18001d5ef  test    byte ptr [rax+1E8h], 20h
0x18001d5f6  jnz     loc_18001E1D4
0x18001d5fc  xor     edx, edx; Val
0x18001d5fe  mov     r8d, 268h; Size
0x18001d604  lea     rcx, [rbp+2A0h+var_2C0]; void *
0x18001d608  call    memset_0
0x18001d60d  mov     rcx, r13; unsigned __int16 *
0x18001d610  call    PathIsInvalidW
0x18001d615  test    eax, eax
0x18001d617  jnz     loc_18001E203
0x18001d61d  mov     [rsp+3A0h+ppszPathOut], rbx
0x18001d622  mov     [rbp+2A0h+pv], rbx
0x18001d626  mov     rbx, [rsp+3A0h+var_350]
0x18001d62b  mov     rcx, [rbx+1C0h]; pszPathIn
0x18001d632  test    rcx, rcx
0x18001d635  jz      loc_18001DF35
0x18001d63b  lea     r9, [rsp+3A0h+ppszPathOut]; ppszPathOut
0x18001d640  mov     r8d, 1; dwFlags
0x18001d646  mov     rdx, r13; pszMore
0x18001d649  call    cs:__imp_PathAllocCombine
0x18001d64f  mov     esi, eax
0x18001d651  test    eax, eax
0x18001d653  js      loc_18001E22D
0x18001d659  mov     rcx, [rbp+2A0h+pv]; pv
0x18001d65d  test    rcx, rcx
0x18001d660  jz      short loc_18001D668
0x18001d662  call    cs:__imp_CoTaskMemFree
0x18001d668  test    esi, esi
0x18001d66a  js      loc_18001DD18
0x18001d670  xor     eax, eax
0x18001d672  mov     esi, eax
0x18001d674  mov     [rbp+2A0h+var_2E0], rax
0x18001d678  mov     ebx, 80004002h
0x18001d67d  mov     [rbp+2A0h+pv], rax
0x18001d681  test    r14, r14
0x18001d684  jz      loc_18001DE59
0x18001d68a  mov     rax, [r14]
0x18001d68d  lea     r8, [rbp+2A0h+pv]
0x18001d691  lea     rdx, aBindContextTim; "bind context timeout value"
0x18001d698  mov     rcx, r14
0x18001d69b  mov     rax, [rax+50h]
0x18001d69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6a4  test    eax, eax
0x18001d6a6  js      loc_18001DE59
0x18001d6ac  mov     rcx, [rbp+2A0h+pv]
0x18001d6b0  mov     rax, [rcx]
0x18001d6b3  lea     r8, [rbp+2A0h+var_2E0]
0x18001d6b7  lea     rdx, _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000
0x18001d6be  mov     rax, [rax]
0x18001d6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c6  mov     ebx, eax
0x18001d6c8  mov     rcx, [rbp+2A0h+pv]
0x18001d6cc  mov     rax, [rcx]
0x18001d6cf  mov     rax, [rax+10h]
0x18001d6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6d8  test    ebx, ebx
0x18001d6da  jns     loc_18001DE1B
0x18001d6e0  mov     rbx, [rsp+3A0h+var_350]
0x18001d6e5  lea     r8, [rbp+2A0h+var_2C0]
0x18001d6e9  mov     edx, r12d
0x18001d6ec  mov     rcx, [rsp+3A0h+ppszPathOut]; Src
0x18001d6f1  call    GetFindDataForPath
0x18001d6f6  mov     esi, eax
0x18001d6f8  test    eax, eax
0x18001d6fa  js      loc_18001DD33
0x18001d700  mov     rcx, [rsp+3A0h+ppszPathOut]; hMem
0x18001d705  test    rcx, rcx
0x18001d708  jnz     loc_18001DD76
0x18001d70e  xor     esi, esi
0x18001d710  mov     eax, esi
0x18001d712  test    r14, r14
0x18001d715  jz      short loc_18001D74D
0x18001d717  mov     [rbp+2A0h+var_2E0], 10h
0x18001d71f  mov     [rbp+2A0h+var_2D8], rax
0x18001d723  mov     rax, [r14]
0x18001d726  lea     rdx, [rbp+2A0h+var_2E0]
0x18001d72a  mov     rcx, r14
0x18001d72d  mov     rax, [rax+38h]
0x18001d731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d736  test    eax, eax
0x18001d738  js      loc_18001DD57
0x18001d73e  cmp     dword ptr [rbp+2A0h+var_2E0+4], 2
0x18001d742  jnz     loc_18001DD57
0x18001d748  mov     eax, 1
0x18001d74d  mov     ebx, 1
0x18001d752  test    eax, eax
0x18001d754  mov     eax, 7
0x18001d759  cmovz   ebx, eax
0x18001d75c  mov     [rsp+3A0h+ppszPathOut], rsi
0x18001d761  mov     esi, 0BEEF0000h
0x18001d766  test    [rbp+2A0h+var_2C0], 10h
0x18001d76a  jz      loc_18001DD81
0x18001d770  mov     [rbp+2A0h+pv], 0
0x18001d778  test    r14, r14
0x18001d77b  jz      short loc_18001D79F
0x18001d77d  mov     rax, [r14]
0x18001d780  lea     r8, [rbp+2A0h+pv]
0x18001d784  lea     rdx, aWin7filesystem; "Win7FileSystemIdList"
0x18001d78b  mov     rcx, r14
0x18001d78e  mov     rax, [rax+50h]
0x18001d792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d797  test    eax, eax
0x18001d799  jns     loc_18001DD5E
0x18001d79f  mov     rcx, r14; struct IBindCtx *
0x18001d7a2  call    ?BindCtx_GetFolderEnumMode@@YA?AW4FOLDER_ENUM_MODE@@PEAUIBindCtx@@@Z; BindCtx_GetFolderEnumMode(IBindCtx *)
0x18001d7a7  mov     rcx, [rsp+3A0h+ppszPathOut]
0x18001d7ac  lea     rdx, [rsp+3A0h+punk]
0x18001d7b1  mov     [rsp+3A0h+var_360], rdx
0x18001d7b6  mov     dword ptr [rsp+3A0h+lpResult], eax
0x18001d7ba  mov     dword ptr [rsp+3A0h+lpBufferSize], ebx
0x18001d7be  mov     dword ptr [rsp+3A0h+lpAccessName], esi
0x18001d7c2  mov     [rsp+3A0h+ppv], rcx
0x18001d7c7  xor     r9d, r9d
0x18001d7ca  xor     r8d, r8d
0x18001d7cd  lea     rdx, [rbp+2A0h+var_2C0]
0x18001d7d1  mov     rbx, [rsp+3A0h+var_350]
0x18001d7d6  mov     rcx, rbx
0x18001d7d9  call    ?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x18001d7de  mov     esi, eax
0x18001d7e0  test    eax, eax
0x18001d7e2  js      short loc_18001D7F0
0x18001d7e4  cmp     [rsp+3A0h+ppszPathOut], 0
0x18001d7ea  jnz     loc_18001E039
0x18001d7f0  mov     rcx, [rsp+3A0h+ppszPathOut]; pv
0x18001d7f5  call    cs:__imp_CoTaskMemFree
0x18001d7fb  test    r12d, r12d
0x18001d7fe  jnz     short loc_18001D80F
0x18001d800  lea     eax, [rsi+7FF8FFFEh]
0x18001d806  cmp     eax, 1
0x18001d809  jbe     loc_18001DF5C
  ... truncated ...
```
