# CSettingsManager::DeleteLocalHistory(void)

- ea: `0x1801c4a28`
- end: `0x1801c4d24`
- name: `?DeleteLocalHistory@CSettingsManager@@QEAAJXZ`
- size: `764`
- prototype: `__int64 __fastcall(CSettingsManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801ab050`

## callees

- `0x180009dd0`
- `0x180024ffc`
- `0x180025710`
- `0x18002fc18`
- `0x180041f54`
- `0x180142e10`
- `0x180143a7c`
- `0x1801b69d8`
- `0x1801c4a28`
- `0x1801c5148`
- `0x1801c5e98`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c4af1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c4b83`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c4af1`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801c4b83`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801c4be4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801c4be4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801c4bcd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801c4bcd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801c4b48`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801c4b48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801c4b9a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801c4b9a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801c4c34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801c4c34`
- `WININET!DeleteUrlCacheGroup` at `0x1801c4cb0`
- `WININET!DeleteUrlCacheGroup` at `0x1801c4cb0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1801c4c6b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1801c4c6b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801c4ac3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801c4ac3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801c4bab`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801c4bab`

## pseudocode

```c
__int64 __fastcall CSettingsManager::DeleteLocalHistory(CSettingsManager *this, __int64 a2, __int64 a3)
{
  HRESULT Instance; // ebx
  HANDLE FirstFile; // rax
  int v5; // eax
  const struct _GUID *v6; // rcx
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFindFile[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      ConnectedSearch_DeleteLocalHistorySettingEntry,
      a3,
      1,
      hFindFile);
  ppszPath = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  v9 = -1;
  v10 = -1;
  Instance = SHGetKnownFolderPath(&FOLDERID_SearchHistory, 0x8000u, 0, &ppszPath);
  if ( Instance >= 0 )
  {
    Instance = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.lnk");
    if ( Instance >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      hFindFile[0] = 0;
      FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
      v5 = ResultFromWin32Handle(FirstFile, hFindFile);
      Instance = v5;
      if ( v5 < 0 )
      {
        if ( v5 != -2147024894 )
        {
          hFindFile[0] = 0;
          goto LABEL_20;
        }
      }
      else
      {
        do
        {
          if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, FindFileData.cFileName) >= 0 )
            DeleteFileW(pszPathOut);
          PathRemoveExtensionW(FindFileData.cFileName);
          UADeleteEntry(v6, FindFileData.cFileName);
        }
        while ( FindNextFileW(hFindFile[0], &FindFileData) );
        FindClose(hFindFile[0]);
      }
      hFindFile[0] = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(hFindFile);
      Instance = CoCreateInstance(
                   &CLSID_TypeAheadSearchHistorySettings,
                   0,
                   1u,
                   &GUID_1d90776b_4df7_442b_b4e5_f4bd8ba98c39,
                   hFindFile);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(HANDLE, _QWORD))(*(_QWORD *)hFindFile[0] + 40LL))(hFindFile[0], 0);
      SHDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\RunMRU");
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(hFindFile);
    }
  }
  hFindFile[0] = 0;
  if ( Instance >= 0 && FindSearchVisitedGroupId((__int64 *)hFindFile) )
  {
    if ( DeleteUrlCacheGroup((GROUPID)hFindFile[0], 2u, 0) )
      Instance = 0;
    else
      Instance = ResultFromKnownLastError();
  }
LABEL_20:
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      ConnectedSearch_DeleteLocalHistory,
      (unsigned int)Instance);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801c4a28  mov     [rsp-8+arg_0], rbx
0x1801c4a2d  push    rbp
0x1801c4a2e  lea     rbp, [rsp-3D0h]
0x1801c4a36  sub     rsp, 4D0h
0x1801c4a3d  mov     rax, cs:__security_cookie
0x1801c4a44  xor     rax, rsp
0x1801c4a47  mov     [rbp+3D0h+var_10], rax
0x1801c4a4e  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801c4a55  jz      short loc_1801C4A7C
0x1801c4a57  lea     rax, [rbp+3D0h+hFindFile]
0x1801c4a5e  mov     r9d, 1
0x1801c4a64  lea     rdx, ConnectedSearch_DeleteLocalHistorySettingEntry
0x1801c4a6b  mov     [rsp+4D0h+lpSearchFilter], rax
0x1801c4a70  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801c4a77  call    McGenEventWrite_EventWriteTransfer
0x1801c4a7c  lea     rcx, [rsp+4D0h+ppszPath]
0x1801c4a81  mov     [rsp+4D0h+ppszPath], 0
0x1801c4a8a  mov     [rsp+4D0h+var_498], 0
0x1801c4a93  mov     [rsp+4D0h+var_490], 0
0x1801c4a9c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801c4aa1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801c4aa5  lea     r9, [rsp+4D0h+ppszPath]; ppszPath
0x1801c4aaa  xor     r8d, r8d; hToken
0x1801c4aad  mov     [rsp+4D0h+var_498], rax
0x1801c4ab2  mov     edx, 8000h; dwFlags
0x1801c4ab7  mov     [rsp+4D0h+var_490], rax
0x1801c4abc  lea     rcx, FOLDERID_SearchHistory; rfid
0x1801c4ac3  call    cs:__imp_SHGetKnownFolderPath
0x1801c4aca  nop     dword ptr [rax+rax+00h]
0x1801c4acf  mov     ebx, eax
0x1801c4ad1  test    eax, eax
0x1801c4ad3  js      loc_1801C4C83
0x1801c4ad9  mov     r8, [rsp+4D0h+ppszPath]; pszPathIn
0x1801c4ade  lea     r9, aLnk; "*.lnk"
0x1801c4ae5  mov     edx, 104h; cchPathOut
0x1801c4aea  lea     rcx, [rbp+3D0h+pszPathOut]; pszPathOut
0x1801c4af1  call    cs:__imp_PathCchCombine
0x1801c4af8  nop     dword ptr [rax+rax+00h]
0x1801c4afd  mov     ebx, eax
0x1801c4aff  test    eax, eax
0x1801c4b01  js      loc_1801C4C83
0x1801c4b07  xor     edx, edx; Val
0x1801c4b09  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x1801c4b0e  mov     r8d, 250h; Size
0x1801c4b14  call    memset_0
0x1801c4b19  xor     r9d, r9d; fSearchOp
0x1801c4b1c  mov     [rsp+4D0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1801c4b24  lea     r8, [rsp+4D0h+FindFileData]; lpFindFileData
0x1801c4b29  mov     [rbp+3D0h+hFindFile], 0
0x1801c4b34  lea     rcx, [rbp+3D0h+pszPathOut]; lpFileName
0x1801c4b3b  mov     [rsp+4D0h+lpSearchFilter], 0; lpSearchFilter
0x1801c4b44  lea     edx, [r9+1]; fInfoLevelId
0x1801c4b48  call    cs:__imp_FindFirstFileExW
0x1801c4b4f  nop     dword ptr [rax+rax+00h]
0x1801c4b54  mov     rcx, rax; void *
0x1801c4b57  lea     rdx, [rbp+3D0h+hFindFile]; void **
0x1801c4b5e  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801c4b63  mov     ebx, eax
0x1801c4b65  test    eax, eax
0x1801c4b67  js      loc_1801C4BF2
0x1801c4b6d  mov     r8, [rsp+4D0h+ppszPath]; pszPathIn
0x1801c4b72  lea     r9, [rsp+4D0h+pszMore]; pszMore
0x1801c4b77  mov     edx, 104h; cchPathOut
0x1801c4b7c  lea     rcx, [rbp+3D0h+pszPathOut]; pszPathOut
0x1801c4b83  call    cs:__imp_PathCchCombine
0x1801c4b8a  nop     dword ptr [rax+rax+00h]
0x1801c4b8f  test    eax, eax
0x1801c4b91  js      short loc_1801C4BA6
0x1801c4b93  lea     rcx, [rbp+3D0h+pszPathOut]; lpFileName
0x1801c4b9a  call    cs:__imp_DeleteFileW
0x1801c4ba1  nop     dword ptr [rax+rax+00h]
0x1801c4ba6  lea     rcx, [rsp+4D0h+pszMore]; pszPath
0x1801c4bab  call    cs:__imp_PathRemoveExtensionW
0x1801c4bb2  nop     dword ptr [rax+rax+00h]
0x1801c4bb7  lea     rdx, [rsp+4D0h+pszMore]; unsigned __int16 *
0x1801c4bbc  call    ?UADeleteEntry@@YAJPEBU_GUID@@PEBG@Z; UADeleteEntry(_GUID const *,ushort const *)
0x1801c4bc1  mov     rcx, [rbp+3D0h+hFindFile]; hFindFile
0x1801c4bc8  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1801c4bcd  call    cs:__imp_FindNextFileW
0x1801c4bd4  nop     dword ptr [rax+rax+00h]
0x1801c4bd9  test    eax, eax
0x1801c4bdb  jnz     short loc_1801C4B6D
0x1801c4bdd  mov     rcx, [rbp+3D0h+hFindFile]; hFindFile
0x1801c4be4  call    cs:__imp_FindClose
0x1801c4beb  nop     dword ptr [rax+rax+00h]
0x1801c4bf0  jmp     short loc_1801C4BFD
0x1801c4bf2  cmp     eax, 80070002h
0x1801c4bf7  jnz     loc_1801C4CC4
0x1801c4bfd  lea     rcx, [rbp+3D0h+hFindFile]
0x1801c4c04  mov     [rbp+3D0h+hFindFile], 0
0x1801c4c0f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c4c14  xor     edx, edx; pUnkOuter
0x1801c4c16  lea     rax, [rbp+3D0h+hFindFile]
0x1801c4c1d  lea     r9, _GUID_1d90776b_4df7_442b_b4e5_f4bd8ba98c39; riid
0x1801c4c24  mov     [rsp+4D0h+lpSearchFilter], rax; ppv
0x1801c4c29  lea     rcx, CLSID_TypeAheadSearchHistorySettings; rclsid
0x1801c4c30  lea     r8d, [rdx+1]; dwClsContext
0x1801c4c34  call    cs:__imp_CoCreateInstance
0x1801c4c3b  nop     dword ptr [rax+rax+00h]
0x1801c4c40  mov     ebx, eax
0x1801c4c42  test    eax, eax
0x1801c4c44  js      short loc_1801C4C5D
0x1801c4c46  mov     rcx, [rbp+3D0h+hFindFile]
0x1801c4c4d  xor     edx, edx
0x1801c4c4f  mov     rax, [rcx]
0x1801c4c52  mov     rax, [rax+28h]
0x1801c4c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4c5b  mov     ebx, eax
0x1801c4c5d  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801c4c64  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1801c4c6b  call    cs:__imp_SHDeleteKeyW
0x1801c4c72  nop     dword ptr [rax+rax+00h]
0x1801c4c77  lea     rcx, [rbp+3D0h+hFindFile]
0x1801c4c7e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801c4c83  mov     [rbp+3D0h+hFindFile], 0
0x1801c4c8e  test    ebx, ebx
0x1801c4c90  js      short loc_1801C4CD8
0x1801c4c92  lea     rcx, [rbp+3D0h+hFindFile]; __int64 *
0x1801c4c99  call    ?FindSearchVisitedGroupId@@YA_NPEA_J@Z; FindSearchVisitedGroupId(__int64 *)
0x1801c4c9e  test    al, al
0x1801c4ca0  jz      short loc_1801C4CD8
0x1801c4ca2  mov     rcx, [rbp+3D0h+hFindFile]; GroupId
0x1801c4ca9  xor     r8d, r8d; lpReserved
0x1801c4cac  lea     edx, [r8+2]; dwFlags
0x1801c4cb0  call    cs:__imp_DeleteUrlCacheGroup
0x1801c4cb7  nop     dword ptr [rax+rax+00h]
0x1801c4cbc  test    eax, eax
0x1801c4cbe  jz      short loc_1801C4CD1
0x1801c4cc0  xor     ebx, ebx
0x1801c4cc2  jmp     short loc_1801C4CD8
0x1801c4cc4  mov     [rbp+3D0h+hFindFile], 0
0x1801c4ccf  jmp     short loc_1801C4CD8
0x1801c4cd1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801c4cd6  mov     ebx, eax
0x1801c4cd8  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801c4cdf  jz      short loc_1801C4CF7
0x1801c4ce1  mov     r8d, ebx
0x1801c4ce4  lea     rdx, ConnectedSearch_DeleteLocalHistory
0x1801c4ceb  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x1801c4cf2  call    McTemplateU0q_EventWriteTransfer
0x1801c4cf7  lea     rcx, [rsp+4D0h+ppszPath]
0x1801c4cfc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801c4d01  mov     eax, ebx
0x1801c4d03  mov     rcx, [rbp+3D0h+var_10]
0x1801c4d0a  xor     rcx, rsp; StackCookie
0x1801c4d0d  call    __security_check_cookie
0x1801c4d12  mov     rbx, [rsp+4D0h+arg_0]
0x1801c4d1a  add     rsp, 4D0h
0x1801c4d21  pop     rbp
0x1801c4d22  retn
```
