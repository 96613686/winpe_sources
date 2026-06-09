# CTemplateDownloader::_CleanupDownloadedTemplates(void)

- ea: `0x1801b7170`
- end: `0x1801b748c`
- name: `?_CleanupDownloadedTemplates@CTemplateDownloader@@AEAAXXZ`
- size: `796`
- prototype: `void __fastcall(CTemplateDownloader *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801b4140`

## callees

- `0x180009dd0`
- `0x18000edd4`
- `0x180041f54`
- `0x18006a010`
- `0x180076bec`
- `0x18008a384`
- `0x180142e10`
- `0x180143a7c`
- `0x1801b3acc`
- `0x1801b3ba4`
- `0x1801b6944`
- `0x1801b69d8`
- `0x1801b7170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1801b71af`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1801b71af`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b7261`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b7395`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b7261`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801b7395`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b735c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801b735c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801b7343`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801b7343`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801b72a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1801b72a5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b73c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801b73c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7440`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801b722c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801b722c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801b72cf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801b72cf`

## string_xrefs

- `0x1801b724a`: `*.dll`

## pseudocode

```c
void __fastcall CTemplateDownloader::_CleanupDownloadedTemplates(RTL_SRWLOCK *this)
{
  _QWORD *v2; // rbx
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rsi
  HANDLE FirstFile; // rax
  int v6; // ebx
  __int64 v7; // rdx
  bool v8; // sf
  unsigned __int64 v9; // r14
  const unsigned __int16 *v10; // r8
  unsigned __int64 i; // rsi
  HANDLE hFindFile; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v18 = (unsigned __int64)&this[20] & -(__int64)(TryAcquireSRWLockExclusive(this + 20) != 0);
  if ( v18 )
  {
    v2 = 0;
    ppszPath = 0;
    v3 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v16 = 0;
    v17 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    v16 = -1;
    v17 = -1;
    v4 = 1000;
    if ( SHGetKnownFolderPath(&FOLDERID_SearchTemplates, 0x8000u, 0, &ppszPath) >= 0
      && PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.dll") >= 0 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      hFindFile = 0;
      FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
      if ( (int)ResultFromWin32Handle(FirstFile, &hFindFile) >= 0 )
      {
        do
        {
          v13 = 0;
          PathRemoveExtensionW(FindFileData.cFileName);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v13);
          v6 = Microsoft::WRL::Details::MakeAndInitialize<CTemplateFile,CTemplateFile,unsigned short (&)[260],_FILETIME &>(
                 &v13,
                 FindFileData.cFileName,
                 &FindFileData.ftLastWriteTime);
          if ( v6 >= 0 )
          {
            v14 = v13;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v14);
            v6 = CTSimpleArray<Microsoft::WRL::ComPtr<CTemplateFile>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CTemplateFile>>>::_AddSortedEx<CCompareTemplatesByTime,Microsoft::WRL::ComPtr<CTemplateFile> &&>(
                   &v19,
                   v7,
                   &v14);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v14);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v13);
        }
        while ( v6 >= 0 && FindNextFileW(hFindFile, &FindFileData) );
        FindClose(hFindFile);
        v3 = v20;
        v8 = v6 < 0;
        v2 = v19;
        if ( !v8 )
        {
          v9 = 1000;
          if ( v20 > 0x3E8 )
          {
            do
            {
              if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, *(PCWSTR *)(v2[v9] + 16LL)) >= 0
                && StringCchCatW(pszPathOut, 0x104u, L".dll") >= 0 )
              {
                DeleteFileW(pszPathOut);
              }
              ++v9;
            }
            while ( v9 < v3 );
          }
        }
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v18);
    wil::AcquireSRWLockExclusive(&hFindFile, &this[21]);
    if ( v3 > 0x3E8 )
    {
      do
        TemplateDownloadHelpers::RemoveTemplateFromArray(
          (TemplateDownloadHelpers *)&this[22],
          *(struct CSimpleCaseInsensitiveOrdinalStringArray **)(v2[v4++] + 16LL),
          v10);
      while ( v4 < v3 );
    }
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&hFindFile);
    if ( v2 )
    {
      for ( i = 0; i < v3; ++i )
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v2[i]);
      CoTaskMemFree(v2);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v18);
}

```

## disassembly

```asm
0x1801b7170  mov     [rsp-8+arg_8], rbx
0x1801b7175  mov     [rsp-8+arg_10], rsi
0x1801b717a  push    rbp
0x1801b717b  push    rdi
0x1801b717c  push    r13
0x1801b717e  push    r14
0x1801b7180  push    r15
0x1801b7182  lea     rbp, [rsp-400h]
0x1801b718a  sub     rsp, 500h
0x1801b7191  mov     rax, cs:__security_cookie
0x1801b7198  xor     rax, rsp
0x1801b719b  mov     [rbp+420h+var_30], rax
0x1801b71a2  lea     rbx, [rcx+0A0h]
0x1801b71a9  mov     r15, rcx
0x1801b71ac  mov     rcx, rbx; SRWLock
0x1801b71af  call    cs:__imp_TryAcquireSRWLockExclusive
0x1801b71b6  nop     dword ptr [rax+rax+00h]
0x1801b71bb  neg     al
0x1801b71bd  sbb     rdx, rdx
0x1801b71c0  and     rdx, rbx
0x1801b71c3  mov     [rsp+520h+var_4C0], rdx
0x1801b71c8  jz      loc_1801B7456
0x1801b71ce  xor     ebx, ebx
0x1801b71d0  mov     [rsp+520h+ppszPath], 0
0x1801b71d9  xor     edi, edi
0x1801b71db  mov     [rsp+520h+var_4B8], rbx
0x1801b71e0  lea     rcx, [rsp+520h+ppszPath]
0x1801b71e5  mov     [rsp+520h+var_4B0], rdi
0x1801b71ea  mov     [rsp+520h+var_4A8], rbx
0x1801b71ef  mov     [rbp+420h+var_4A0], rbx
0x1801b71f3  mov     [rsp+520h+var_4D0], 0
0x1801b71fc  mov     [rsp+520h+var_4C8], 0
0x1801b7205  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b720a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801b720e  lea     r9, [rsp+520h+ppszPath]; ppszPath
0x1801b7213  xor     r8d, r8d; hToken
0x1801b7216  mov     [rsp+520h+var_4D0], rax
0x1801b721b  mov     edx, 8000h; dwFlags
0x1801b7220  mov     [rsp+520h+var_4C8], rax
0x1801b7225  lea     rcx, FOLDERID_SearchTemplates; rfid
0x1801b722c  call    cs:__imp_SHGetKnownFolderPath
0x1801b7233  nop     dword ptr [rax+rax+00h]
0x1801b7238  mov     esi, 3E8h
0x1801b723d  test    eax, eax
0x1801b723f  js      loc_1801B73DA
0x1801b7245  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1801b724a  lea     r9, aDll; "*.dll"
0x1801b7251  mov     r13d, 104h
0x1801b7257  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1801b725e  mov     edx, r13d; cchPathOut
0x1801b7261  call    cs:__imp_PathCchCombine
0x1801b7268  nop     dword ptr [rax+rax+00h]
0x1801b726d  test    eax, eax
0x1801b726f  js      loc_1801B73DA
0x1801b7275  xor     edx, edx; Val
0x1801b7277  lea     rcx, [rbp+420h+FindFileData]; void *
0x1801b727b  mov     r8d, 250h; Size
0x1801b7281  call    memset_0
0x1801b7286  xor     r9d, r9d; fSearchOp
0x1801b7289  mov     [rsp+520h+dwAdditionalFlags], ebx; dwAdditionalFlags
0x1801b728d  lea     r8, [rbp+420h+FindFileData]; lpFindFileData
0x1801b7291  mov     [rsp+520h+hFindFile], rbx
0x1801b7296  lea     edx, [rbx+1]; fInfoLevelId
0x1801b7299  mov     [rsp+520h+lpSearchFilter], rbx; lpSearchFilter
0x1801b729e  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x1801b72a5  call    cs:__imp_FindFirstFileExW
0x1801b72ac  nop     dword ptr [rax+rax+00h]
0x1801b72b1  mov     rcx, rax; void *
0x1801b72b4  lea     rdx, [rsp+520h+hFindFile]; void **
0x1801b72b9  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1801b72be  test    eax, eax
0x1801b72c0  js      loc_1801B73DA
0x1801b72c6  lea     rcx, [rbp+420h+pszPath]; pszPath
0x1801b72ca  mov     [rsp+520h+var_4E8], rdi
0x1801b72cf  call    cs:__imp_PathRemoveExtensionW
0x1801b72d6  nop     dword ptr [rax+rax+00h]
0x1801b72db  lea     rcx, [rsp+520h+var_4E8]
0x1801b72e0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801b72e5  lea     r8, [rbp+420h+var_47C]
0x1801b72e9  lea     rdx, [rbp+420h+pszPath]
0x1801b72ed  lea     rcx, [rsp+520h+var_4E8]
0x1801b72f2  call    ??$MakeAndInitialize@VCTemplateFile@@V1@AEAY0BAE@GAEAU_FILETIME@@@Details@WRL@Microsoft@@YAJPEAPEAVCTemplateFile@@AEAY0BAE@GAEAU_FILETIME@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CTemplateFile,CTemplateFile,ushort (&)[260],_FILETIME &>(CTemplateFile * *,ushort (&)[260],_FILETIME &)
0x1801b72f7  mov     ebx, eax
0x1801b72f9  test    eax, eax
0x1801b72fb  js      short loc_1801B732C
0x1801b72fd  mov     rax, [rsp+520h+var_4E8]
0x1801b7302  lea     rcx, [rsp+520h+var_4E0]
0x1801b7307  mov     [rsp+520h+var_4E0], rax
0x1801b730c  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1801b7311  lea     r8, [rsp+520h+var_4E0]
0x1801b7316  lea     rcx, [rsp+520h+var_4B8]
0x1801b731b  call    ??$_AddSortedEx@VCCompareTemplatesByTime@@$$QEAV?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@@@@@QEAAJAEBVCCompareTemplatesByTime@@$$QEAV?$ComPtr@VCTemplateFile@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CTemplateFile>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CTemplateFile>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CTemplateFile>>>::_AddSortedEx<CCompareTemplatesByTime,Microsoft::WRL::ComPtr<CTemplateFile> &&>(CCompareTemplatesByTime const &,Microsoft::WRL::ComPtr<CTemplateFile> &&,unsigned __int64 *)
0x1801b7320  lea     rcx, [rsp+520h+var_4E0]
0x1801b7325  mov     ebx, eax
0x1801b7327  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801b732c  lea     rcx, [rsp+520h+var_4E8]
0x1801b7331  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801b7336  test    ebx, ebx
0x1801b7338  js      short loc_1801B7357
0x1801b733a  mov     rcx, [rsp+520h+hFindFile]; hFindFile
0x1801b733f  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x1801b7343  call    cs:__imp_FindNextFileW
0x1801b734a  nop     dword ptr [rax+rax+00h]
0x1801b734f  test    eax, eax
0x1801b7351  jnz     loc_1801B72C6
0x1801b7357  mov     rcx, [rsp+520h+hFindFile]; hFindFile
0x1801b735c  call    cs:__imp_FindClose
0x1801b7363  nop     dword ptr [rax+rax+00h]
0x1801b7368  mov     rdi, [rsp+520h+var_4B0]
0x1801b736d  test    ebx, ebx
0x1801b736f  mov     rbx, [rsp+520h+var_4B8]
0x1801b7374  js      short loc_1801B73DA
0x1801b7376  mov     r14, rsi
0x1801b7379  cmp     rdi, rsi
0x1801b737c  jbe     short loc_1801B73DA
0x1801b737e  mov     r9, [rbx+r14*8]
0x1801b7382  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1801b7389  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1801b738e  mov     rdx, r13; cchPathOut
0x1801b7391  mov     r9, [r9+10h]; pszMore
0x1801b7395  call    cs:__imp_PathCchCombine
0x1801b739c  nop     dword ptr [rax+rax+00h]
0x1801b73a1  test    eax, eax
0x1801b73a3  js      short loc_1801B73D2
0x1801b73a5  lea     r8, aDll_0; ".dll"
0x1801b73ac  mov     rdx, r13; unsigned __int64
0x1801b73af  lea     rcx, [rbp+420h+pszPathOut]; unsigned __int16 *
0x1801b73b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801b73bb  test    eax, eax
0x1801b73bd  js      short loc_1801B73D2
0x1801b73bf  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x1801b73c6  call    cs:__imp_DeleteFileW
0x1801b73cd  nop     dword ptr [rax+rax+00h]
0x1801b73d2  inc     r14
0x1801b73d5  cmp     r14, rdi
0x1801b73d8  jb      short loc_1801B737E
0x1801b73da  lea     rcx, [rsp+520h+var_4C0]; this
0x1801b73df  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b73e4  lea     rdx, [r15+0A8h]
0x1801b73eb  lea     rcx, [rsp+520h+hFindFile]
0x1801b73f0  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b73f5  cmp     rdi, rsi
0x1801b73f8  jbe     short loc_1801B7416
0x1801b73fa  mov     rdx, [rbx+rsi*8]
0x1801b73fe  lea     rcx, [r15+0B0h]; this
0x1801b7405  mov     rdx, [rdx+10h]; struct CSimpleCaseInsensitiveOrdinalStringArray *
0x1801b7409  call    ?RemoveTemplateFromArray@TemplateDownloadHelpers@@YAJAEAVCSimpleCaseInsensitiveOrdinalStringArray@@PEBG@Z; TemplateDownloadHelpers::RemoveTemplateFromArray(CSimpleCaseInsensitiveOrdinalStringArray &,ushort const *)
0x1801b740e  inc     rsi
0x1801b7411  cmp     rsi, rdi
0x1801b7414  jb      short loc_1801B73FA
0x1801b7416  lea     rcx, [rsp+520h+hFindFile]; this
0x1801b741b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b7420  test    rbx, rbx
0x1801b7423  jz      short loc_1801B744C
0x1801b7425  xor     esi, esi
0x1801b7427  test    rdi, rdi
0x1801b742a  jz      short loc_1801B743D
0x1801b742c  lea     rcx, [rbx+rsi*8]
0x1801b7430  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801b7435  inc     rsi
0x1801b7438  cmp     rsi, rdi
0x1801b743b  jb      short loc_1801B742C
0x1801b743d  mov     rcx, rbx; pv
0x1801b7440  call    cs:__imp_CoTaskMemFree
0x1801b7447  nop     dword ptr [rax+rax+00h]
0x1801b744c  lea     rcx, [rsp+520h+ppszPath]
0x1801b7451  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b7456  lea     rcx, [rsp+520h+var_4C0]; this
0x1801b745b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b7460  mov     rcx, [rbp+420h+var_30]
0x1801b7467  xor     rcx, rsp; StackCookie
0x1801b746a  call    __security_check_cookie
0x1801b746f  lea     r11, [rsp+520h+var_20]
0x1801b7477  mov     rbx, [r11+38h]
0x1801b747b  mov     rsi, [r11+40h]
0x1801b747f  mov     rsp, r11
0x1801b7482  pop     r15
0x1801b7484  pop     r14
0x1801b7486  pop     r13
0x1801b7488  pop     rdi
0x1801b7489  pop     rbp
0x1801b748a  retn
```
