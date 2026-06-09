# CleanupHistoryItems(bool)

- ea: `0x180380848`
- end: `0x180380af8`
- name: `?CleanupHistoryItems@@YAJ_N@Z`
- size: `688`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180381e80`

## callees

- `0x180009dd0`
- `0x18000edd4`
- `0x180041f54`
- `0x180142e10`
- `0x180143a7c`
- `0x1801c5e98`
- `0x180380430`
- `0x1803805ac`
- `0x180380848`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x180380a61`
- `api-ms-win-core-path-l1-1-0!PathCchAddExtension` at `0x180380a61`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803808e8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180380a36`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1803808e8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180380a36`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803809ec`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803809ec`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1803809d5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1803809d5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180380942`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180380942`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380a78`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380abe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380abe`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1803808ba`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1803808ba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180380963`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x180380963`

## pseudocode

```c
__int64 __fastcall CleanupHistoryItems()
{
  HRESULT v0; // ebx
  _QWORD *v1; // rsi
  unsigned __int64 v2; // r14
  HANDLE FirstFile; // rdi
  __int64 v4; // rdx
  __int32 v5; // edi
  unsigned __int64 v6; // r15
  const unsigned __int16 *v7; // r12
  const struct _GUID *v8; // rcx
  unsigned __int64 i; // rdi
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPathOut[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  ppszPath = 0;
  v14 = 0;
  v15 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  v14 = -1;
  v15 = -1;
  v0 = SHGetKnownFolderPath(&FOLDERID_SearchHistory, 0x8000u, 0, &ppszPath);
  if ( v0 < 0 )
    goto LABEL_22;
  v0 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"*.lnk");
  if ( v0 < 0 )
    goto LABEL_22;
  v1 = 0;
  v2 = 0;
  pv = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = FindFirstFileExW(pszPathOut, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  if ( FirstFile == (HANDLE)-1LL )
    goto LABEL_9;
  do
  {
    v11 = 0;
    PathRemoveExtensionW(FindFileData.cFileName);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v11);
    v0 = Microsoft::WRL::Details::MakeAndInitialize<CHistoryItem,CHistoryItem,unsigned short (&)[260],_FILETIME &>(
           &v11,
           FindFileData.cFileName,
           &FindFileData.ftCreationTime);
    if ( v0 >= 0 )
    {
      v12 = v11;
      Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v12);
      v0 = CTSimpleArray<Microsoft::WRL::ComPtr<CHistoryItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CHistoryItem>>>::_AddSortedEx<CCompareHistoryItems,Microsoft::WRL::ComPtr<CHistoryItem> &&>(
             &pv,
             v4,
             &v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v11);
  }
  while ( v0 >= 0 && FindNextFileW(FirstFile, &FindFileData) );
  FindClose(FirstFile);
  v2 = v17;
  v1 = pv;
  if ( v0 >= 0 )
  {
LABEL_9:
    v5 = v2;
    v6 = 950;
    if ( v2 <= 0x3B6 )
    {
      if ( v2 < 0x3B6 )
      {
LABEL_17:
        _InterlockedExchange(&dword_1804CEF20, v5);
        goto LABEL_18;
      }
    }
    else
    {
      do
      {
        v7 = *(const unsigned __int16 **)(v1[v6] + 24LL);
        if ( PathCchCombine(pszPathOut, 0x104u, ppszPath, v7) >= 0 )
        {
          UADeleteEntry(v8, v7);
          if ( PathCchAddExtension(pszPathOut, 0x104u, L".lnk") >= 0 )
            DeleteFileW(pszPathOut);
        }
        ++v6;
      }
      while ( v6 < v2 );
    }
    v5 = 950;
    goto LABEL_17;
  }
LABEL_18:
  if ( v1 )
  {
    for ( i = 0; i < v2; ++i )
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v1[i]);
    CoTaskMemFree(v1);
  }
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180380848  push    rbp
0x18038084a  push    rbx
0x18038084b  push    rsi
0x18038084c  push    rdi
0x18038084d  push    r12
0x18038084f  push    r14
0x180380851  push    r15
0x180380853  lea     rbp, [rsp-3F0h]
0x18038085b  sub     rsp, 4F0h
0x180380862  mov     rax, cs:__security_cookie
0x180380869  xor     rax, rsp
0x18038086c  mov     [rbp+420h+var_40], rax
0x180380873  lea     rcx, [rsp+520h+ppszPath]
0x180380878  mov     [rsp+520h+ppszPath], 0
0x180380881  mov     [rsp+520h+var_4D8], 0
0x18038088a  mov     [rsp+520h+var_4D0], 0
0x180380893  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180380898  or      r15, 0FFFFFFFFFFFFFFFFh
0x18038089c  lea     r9, [rsp+520h+ppszPath]; ppszPath
0x1803808a1  xor     r8d, r8d; hToken
0x1803808a4  mov     [rsp+520h+var_4D8], r15
0x1803808a9  mov     edx, 8000h; dwFlags
0x1803808ae  mov     [rsp+520h+var_4D0], r15
0x1803808b3  lea     rcx, FOLDERID_SearchHistory; rfid
0x1803808ba  call    cs:__imp_SHGetKnownFolderPath
0x1803808c1  nop     dword ptr [rax+rax+00h]
0x1803808c6  mov     ebx, eax
0x1803808c8  test    eax, eax
0x1803808ca  js      loc_180380ACA
0x1803808d0  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x1803808d5  lea     r9, aLnk; "*.lnk"
0x1803808dc  mov     edx, 104h; cchPathOut
0x1803808e1  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x1803808e8  call    cs:__imp_PathCchCombine
0x1803808ef  nop     dword ptr [rax+rax+00h]
0x1803808f4  mov     ebx, eax
0x1803808f6  test    eax, eax
0x1803808f8  js      loc_180380ACA
0x1803808fe  xor     esi, esi
0x180380900  lea     rcx, [rbp+420h+FindFileData]; void *
0x180380904  xor     r14d, r14d
0x180380907  mov     [rsp+520h+pv], rsi
0x18038090c  xor     edx, edx; Val
0x18038090e  mov     [rsp+520h+var_4C0], r14
0x180380913  mov     r8d, 250h; Size
0x180380919  mov     [rsp+520h+var_4B8], rsi
0x18038091e  mov     [rsp+520h+var_4B0], rsi
0x180380923  call    memset_0
0x180380928  xor     r9d, r9d; fSearchOp
0x18038092b  mov     [rsp+520h+dwAdditionalFlags], esi; dwAdditionalFlags
0x18038092f  lea     r8, [rbp+420h+FindFileData]; lpFindFileData
0x180380933  mov     [rsp+520h+lpSearchFilter], rsi; lpSearchFilter
0x180380938  lea     edx, [rsi+1]; fInfoLevelId
0x18038093b  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x180380942  call    cs:__imp_FindFirstFileExW
0x180380949  nop     dword ptr [rax+rax+00h]
0x18038094e  mov     rdi, rax
0x180380951  cmp     rax, r15
0x180380954  jz      loc_180380A0A
0x18038095a  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18038095e  mov     [rsp+520h+var_4F0], rsi
0x180380963  call    cs:__imp_PathRemoveExtensionW
0x18038096a  nop     dword ptr [rax+rax+00h]
0x18038096f  lea     rcx, [rsp+520h+var_4F0]
0x180380974  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180380979  lea     r8, [rbp+420h+var_49C]
0x18038097d  lea     rdx, [rbp+420h+pszPath]
0x180380981  lea     rcx, [rsp+520h+var_4F0]
0x180380986  call    ??$MakeAndInitialize@VCHistoryItem@@V1@AEAY0BAE@GAEAU_FILETIME@@@Details@WRL@Microsoft@@YAJPEAPEAVCHistoryItem@@AEAY0BAE@GAEAU_FILETIME@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CHistoryItem,CHistoryItem,ushort (&)[260],_FILETIME &>(CHistoryItem * *,ushort (&)[260],_FILETIME &)
0x18038098b  mov     ebx, eax
0x18038098d  test    eax, eax
0x18038098f  js      short loc_1803809C0
0x180380991  mov     rax, [rsp+520h+var_4F0]
0x180380996  lea     rcx, [rsp+520h+var_4E8]
0x18038099b  mov     [rsp+520h+var_4E8], rax
0x1803809a0  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1803809a5  lea     r8, [rsp+520h+var_4E8]
0x1803809aa  lea     rcx, [rsp+520h+pv]
0x1803809af  call    ??$_AddSortedEx@VCCompareHistoryItems@@$$QEAV?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@?$CTSimpleArray@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@@@@@QEAAJAEBVCCompareHistoryItems@@$$QEAV?$ComPtr@VCHistoryItem@@@WRL@Microsoft@@PEA_K@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CHistoryItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CHistoryItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CHistoryItem>>>::_AddSortedEx<CCompareHistoryItems,Microsoft::WRL::ComPtr<CHistoryItem> &&>(CCompareHistoryItems const &,Microsoft::WRL::ComPtr<CHistoryItem> &&,unsigned __int64 *)
0x1803809b4  lea     rcx, [rsp+520h+var_4E8]
0x1803809b9  mov     ebx, eax
0x1803809bb  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803809c0  lea     rcx, [rsp+520h+var_4F0]
0x1803809c5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803809ca  test    ebx, ebx
0x1803809cc  js      short loc_1803809E9
0x1803809ce  lea     rdx, [rbp+420h+FindFileData]; lpFindFileData
0x1803809d2  mov     rcx, rdi; hFindFile
0x1803809d5  call    cs:__imp_FindNextFileW
0x1803809dc  nop     dword ptr [rax+rax+00h]
0x1803809e1  test    eax, eax
0x1803809e3  jnz     loc_18038095A
0x1803809e9  mov     rcx, rdi; hFindFile
0x1803809ec  call    cs:__imp_FindClose
0x1803809f3  nop     dword ptr [rax+rax+00h]
0x1803809f8  mov     r14, [rsp+520h+var_4C0]
0x1803809fd  mov     rsi, [rsp+520h+pv]
0x180380a02  test    ebx, ebx
0x180380a04  js      loc_180380A9E
0x180380a0a  mov     eax, 3B6h
0x180380a0f  mov     rdi, r14
0x180380a12  mov     r15d, eax
0x180380a15  cmp     r14, rax
0x180380a18  jbe     short loc_180380A93
0x180380a1a  mov     rax, [rsi+r15*8]
0x180380a1e  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x180380a25  mov     r8, [rsp+520h+ppszPath]; pszPathIn
0x180380a2a  mov     edx, 104h; cchPathOut
0x180380a2f  mov     r12, [rax+18h]
0x180380a33  mov     r9, r12; pszMore
0x180380a36  call    cs:__imp_PathCchCombine
0x180380a3d  nop     dword ptr [rax+rax+00h]
0x180380a42  test    eax, eax
0x180380a44  js      short loc_180380A84
0x180380a46  mov     rdx, r12; unsigned __int16 *
0x180380a49  call    ?UADeleteEntry@@YAJPEBU_GUID@@PEBG@Z; UADeleteEntry(_GUID const *,ushort const *)
0x180380a4e  lea     r8, aLnk_0; ".lnk"
0x180380a55  mov     edx, 104h; cchPath
0x180380a5a  lea     rcx, [rbp+420h+pszPathOut]; pszPath
0x180380a61  call    cs:__imp_PathCchAddExtension
0x180380a68  nop     dword ptr [rax+rax+00h]
0x180380a6d  test    eax, eax
0x180380a6f  js      short loc_180380A84
0x180380a71  lea     rcx, [rbp+420h+pszPathOut]; lpFileName
0x180380a78  call    cs:__imp_DeleteFileW
0x180380a7f  nop     dword ptr [rax+rax+00h]
0x180380a84  inc     r15
0x180380a87  cmp     r15, r14
0x180380a8a  jb      short loc_180380A1A
0x180380a8c  mov     eax, 3B6h
0x180380a91  jmp     short loc_180380A95
0x180380a93  jb      short loc_180380A98
0x180380a95  mov     rdi, rax
0x180380a98  xchg    edi, cs:dword_1804CEF20
0x180380a9e  test    rsi, rsi
0x180380aa1  jz      short loc_180380ACA
0x180380aa3  xor     edi, edi
0x180380aa5  test    r14, r14
0x180380aa8  jz      short loc_180380ABB
0x180380aaa  lea     rcx, [rsi+rdi*8]
0x180380aae  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180380ab3  inc     rdi
0x180380ab6  cmp     rdi, r14
0x180380ab9  jb      short loc_180380AAA
0x180380abb  mov     rcx, rsi; pv
0x180380abe  call    cs:__imp_CoTaskMemFree
0x180380ac5  nop     dword ptr [rax+rax+00h]
0x180380aca  lea     rcx, [rsp+520h+ppszPath]
0x180380acf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180380ad4  mov     eax, ebx
0x180380ad6  mov     rcx, [rbp+420h+var_40]
0x180380add  xor     rcx, rsp; StackCookie
0x180380ae0  call    __security_check_cookie
0x180380ae5  add     rsp, 4F0h
0x180380aec  pop     r15
0x180380aee  pop     r14
0x180380af0  pop     r12
0x180380af2  pop     rdi
0x180380af3  pop     rsi
0x180380af4  pop     rbx
0x180380af5  pop     rbp
0x180380af6  retn
```
