# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::LoadLayoutFromAppData(ushort const *,IStream * *)

- ea: `0x1800c09b4`
- end: `0x1800c0d77`
- name: `?LoadLayoutFromAppData@CuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGPEAPEAUIStream@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics *this, const unsigned __int16 *, struct IStream **)`
- caller_count: `4`
- callee_count: `9`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c0560`
- `0x18021c4d0`
- `0x18021c5f0`
- `0x18021c870`

## callees

- `0x18001aca4`
- `0x18002f1fc`
- `0x1800c09b4`
- `0x1800c172c`
- `0x1800c18c4`
- `0x1800c1900`
- `0x1800c2688`
- `0x1801cdba8`
- `0x180201e50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c0c4a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c0c4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0d0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0d0a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0a6a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0be2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0c72`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0a6a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0be2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800c0c72`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c0a9b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c0c2c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c0a9b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800c0c2c`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x1800c0ac0`
- `USERENV!GetDefaultUserProfileDirectoryW` at `0x1800c0ac0`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c0a14`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800c0a14`

## string_xrefs

- `0x1800c0a2c`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x1800c0bfa`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x1800c0cab`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x1800c0d43`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x1800c0c61`: `%windir%\System32\Layouts`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::LoadLayoutFromAppData(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics *this,
        const unsigned __int16 *a2,
        struct IStream **a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rdx
  HRESULT v8; // eax
  int v9; // ecx
  unsigned __int64 v10; // rbx
  int v11; // eax
  HRESULT v12; // esi
  const WCHAR *v13; // r8
  unsigned __int64 v14; // rsi
  HRESULT v15; // eax
  __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // ecx
  wchar_t *v19; // rax
  const WCHAR *v20; // rax
  int v21; // eax
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics *v22; // rcx
  void *v23; // rbx
  int FileStream; // edi
  int pstmTemplate; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchSize[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszFile[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR v34[264]; // [rsp+690h] [rbp+590h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8E8h] [rbp+7E8h]

  *a3 = 0;
  ppszPath = 0;
  v27 = -1;
  v28 = -1;
  v5 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v5 < 0 )
  {
    v6 = 405;
    goto LABEL_3;
  }
  v5 = PathCchCombine(pszPathOut, 0x104u, ppszPath, a2);
  if ( v5 < 0 )
  {
    v6 = 407;
    goto LABEL_3;
  }
  *a3 = 0;
  v8 = SHCreateStreamOnFileEx(pszPathOut, 0x20u, 0, 0, 0, a3);
  v9 = 0;
  if ( v8 < 0 )
    v9 = v8;
  if ( v9 >= 0 )
    goto LABEL_48;
  cchSize[0] = 260;
  if ( !GetDefaultUserProfileDirectoryW(ProfileDir, cchSize) )
  {
    v5 = -2147024809;
    v6 = 423;
    goto LABEL_3;
  }
  v10 = -1;
  do
    ++v10;
  while ( ProfileDir[v10] );
  v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
          &ppszPath,
          v10);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\l"
                    "ib\\curatedcollectioninitializationstatics.cpp",
      (const char *)(unsigned int)v11,
      pstmTemplate);
    v5 = v12;
    goto LABEL_52;
  }
  StringCchCopyNW(ppszPath, v10 + 1, ProfileDir, v10);
  v13 = ppszPath;
  v27 = v10;
  if ( v10 == -1 )
  {
    if ( ppszPath )
    {
      v10 = -1;
      do
        ++v10;
      while ( ppszPath[v10] );
    }
    else
    {
      v10 = 0;
    }
    v27 = v10;
  }
  if ( v10 < 0x104 )
  {
    v14 = 15;
    if ( 260 - v10 < 0xF )
      v14 = 260 - v10;
    v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           &ppszPath,
           v10 + v14);
    if ( v5 >= 0 )
    {
      StringCchCopyNW(&ppszPath[v27], v14 + 1, L"\\AppData\\Local\\", v14);
      v27 += v14;
LABEL_30:
      v13 = ppszPath;
      goto LABEL_31;
    }
    v6 = 419;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\l"
                    "ib\\curatedcollectioninitializationstatics.cpp",
      (const char *)(unsigned int)v5,
      pstmTemplate);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return (unsigned int)v5;
  }
  if ( v10 > 0x104 )
  {
    v27 = 260;
    ppszPath[260] = 0;
    goto LABEL_30;
  }
LABEL_31:
  v15 = PathCchCombine(pszFile, 0x104u, v13, a2);
  v5 = v15;
  if ( v15 < 0 )
  {
    v16 = 426;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\l"
                    "ib\\curatedcollectioninitializationstatics.cpp",
      (const char *)(unsigned int)v15,
      pstmTemplate);
LABEL_52:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    return (unsigned int)v5;
  }
  *a3 = 0;
  v17 = SHCreateStreamOnFileEx(pszFile, 0x20u, 0, 0, 0, a3);
  v18 = 0;
  if ( v17 < 0 )
    v18 = v17;
  if ( v18 < 0 )
  {
    v19 = wcsrchr(a2, 0x5Cu);
    if ( v19 )
      v20 = v19 + 1;
    else
      v20 = a2;
    v15 = PathCchCombine(v34, 0x104u, L"%windir%\\System32\\Layouts", v20);
    v5 = v15;
    if ( v15 < 0 )
    {
      v16 = 443;
      goto LABEL_33;
    }
    pv = 0;
    v21 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            v34,
            &pv);
    v5 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)(unsigned int)v21,
        pstmTemplate);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      goto LABEL_52;
    }
    v23 = pv;
    FileStream = WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::LoadFileStream(
                   v22,
                   (const unsigned __int16 *)pv,
                   a3);
    if ( FileStream < 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      v5 = FileStream;
      goto LABEL_52;
    }
    if ( v23 )
      CoTaskMemFree(v23);
  }
LABEL_48:
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 0;
}

```

## disassembly

```asm
0x1800c09b4  mov     [rsp-8+arg_0], rbx
0x1800c09b9  push    rbp
0x1800c09ba  push    rsi
0x1800c09bb  push    rdi
0x1800c09bc  push    r12
0x1800c09be  push    r13
0x1800c09c0  push    r14
0x1800c09c2  push    r15
0x1800c09c4  lea     rbp, [rsp-7B0h]
0x1800c09cc  sub     rsp, 8B0h
0x1800c09d3  mov     rax, cs:__security_cookie
0x1800c09da  xor     rax, rsp
0x1800c09dd  mov     [rbp+7E0h+var_40], rax
0x1800c09e4  xor     r12d, r12d
0x1800c09e7  lea     r9, [rsp+8E0h+ppszPath]; ppszPath
0x1800c09ec  mov     [r8], r12
0x1800c09ef  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800c09f6  mov     r15, r8
0x1800c09f9  mov     [rsp+8E0h+ppszPath], r12
0x1800c09fe  mov     r14, rdx
0x1800c0a01  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800c0a05  xor     r8d, r8d; hToken
0x1800c0a08  mov     [rsp+8E0h+var_8A8], rdi
0x1800c0a0d  xor     edx, edx; dwFlags
0x1800c0a0f  mov     [rsp+8E0h+var_8A0], rdi
0x1800c0a14  call    cs:__imp_SHGetKnownFolderPath
0x1800c0a1a  mov     ebx, eax
0x1800c0a1c  test    eax, eax
0x1800c0a1e  jns     short loc_1800C0A52
0x1800c0a20  mov     edx, 195h; void *
0x1800c0a25  mov     rcx, [rbp+7E8h]; this
0x1800c0a2c  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c0a33  mov     r9d, ebx; char *
0x1800c0a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0a3b  mov     rcx, [rsp+8E0h+ppszPath]; pv
0x1800c0a40  test    rcx, rcx
0x1800c0a43  jz      short loc_1800C0A4B
0x1800c0a45  call    cs:__imp_CoTaskMemFree
0x1800c0a4b  mov     eax, ebx
0x1800c0a4d  jmp     loc_1800C0D12
0x1800c0a52  mov     r8, [rsp+8E0h+ppszPath]; pszPathIn
0x1800c0a57  lea     rcx, [rbp+7E0h+pszPathOut]; pszPathOut
0x1800c0a5e  mov     r13d, 104h
0x1800c0a64  mov     r9, r14; pszMore
0x1800c0a67  mov     edx, r13d; cchPathOut
0x1800c0a6a  call    cs:__imp_PathCchCombine
0x1800c0a70  mov     ebx, eax
0x1800c0a72  test    eax, eax
0x1800c0a74  jns     short loc_1800C0A7D
0x1800c0a76  mov     edx, 197h
0x1800c0a7b  jmp     short loc_1800C0A25
0x1800c0a7d  xor     r9d, r9d; fCreate
0x1800c0a80  mov     [rsp+8E0h+ppstm], r15; ppstm
0x1800c0a85  xor     r8d, r8d; dwAttributes
0x1800c0a88  mov     [r15], r12
0x1800c0a8b  lea     rcx, [rbp+7E0h+pszPathOut]; pszFile
0x1800c0a92  mov     [rsp+8E0h+pstmTemplate], r12; int
0x1800c0a97  lea     edx, [r9+20h]; grfMode
0x1800c0a9b  call    cs:__imp_SHCreateStreamOnFileEx
0x1800c0aa1  test    eax, eax
0x1800c0aa3  mov     ecx, r12d
0x1800c0aa6  cmovs   ecx, eax
0x1800c0aa9  test    ecx, ecx
0x1800c0aab  jns     loc_1800C0D00
0x1800c0ab1  lea     rdx, [rsp+8E0h+cchSize]; lpcchSize
0x1800c0ab6  mov     [rsp+8E0h+cchSize], r13d
0x1800c0abb  lea     rcx, [rsp+8E0h+ProfileDir]; lpProfileDir
0x1800c0ac0  call    cs:__imp_GetDefaultUserProfileDirectoryW
0x1800c0ac6  test    eax, eax
0x1800c0ac8  jz      loc_1800C0D68
0x1800c0ace  lea     rax, [rsp+8E0h+ProfileDir]
0x1800c0ad3  mov     rbx, rdi
0x1800c0ad6  inc     rbx
0x1800c0ad9  cmp     [rax+rbx*2], r12w
0x1800c0ade  jnz     short loc_1800C0AD6
0x1800c0ae0  mov     rdx, rbx
0x1800c0ae3  lea     rcx, [rsp+8E0h+ppszPath]
0x1800c0ae8  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800c0aed  mov     esi, eax
0x1800c0aef  test    eax, eax
0x1800c0af1  js      loc_1800C0D3C
0x1800c0af7  mov     rcx, [rsp+8E0h+ppszPath]; unsigned __int16 *
0x1800c0afc  lea     rdx, [rbx+1]; unsigned __int64
0x1800c0b00  mov     r9, rbx; unsigned __int64
0x1800c0b03  lea     r8, [rsp+8E0h+ProfileDir]; unsigned __int16 *
0x1800c0b08  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800c0b0d  mov     r8, [rsp+8E0h+ppszPath]
0x1800c0b12  mov     [rsp+8E0h+var_8A8], rbx
0x1800c0b17  cmp     rbx, rdi
0x1800c0b1a  jnz     short loc_1800C0B38
0x1800c0b1c  test    r8, r8
0x1800c0b1f  jz      short loc_1800C0B30
0x1800c0b21  mov     rbx, rdi
0x1800c0b24  inc     rbx
0x1800c0b27  cmp     [r8+rbx*2], r12w
0x1800c0b2c  jnz     short loc_1800C0B24
0x1800c0b2e  jmp     short loc_1800C0B33
0x1800c0b30  mov     rbx, r12
0x1800c0b33  mov     [rsp+8E0h+var_8A8], rbx
0x1800c0b38  cmp     rbx, r13
0x1800c0b3b  jnb     loc_1800C0BC1
0x1800c0b41  mov     esi, 0Fh
0x1800c0b46  mov     rax, r13
0x1800c0b49  sub     rax, rbx
0x1800c0b4c  cmp     rax, rsi
0x1800c0b4f  cmovb   rsi, rax
0x1800c0b53  cmp     rbx, rdi
0x1800c0b56  jnz     short loc_1800C0B78
0x1800c0b58  test    r8, r8
0x1800c0b5b  jz      short loc_1800C0B6E
0x1800c0b5d  inc     rdi
0x1800c0b60  cmp     [r8+rdi*2], r12w
0x1800c0b65  jnz     short loc_1800C0B5D
0x1800c0b67  mov     [rsp+8E0h+var_8A8], rdi
0x1800c0b6c  jmp     short loc_1800C0B7B
0x1800c0b6e  mov     [rsp+8E0h+var_8A8], r12
0x1800c0b73  mov     rdi, r12
0x1800c0b76  jmp     short loc_1800C0B7B
0x1800c0b78  mov     rdi, rbx
0x1800c0b7b  lea     rdx, [rdi+rsi]
0x1800c0b7f  lea     rcx, [rsp+8E0h+ppszPath]
0x1800c0b84  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800c0b89  mov     ebx, eax
0x1800c0b8b  test    eax, eax
0x1800c0b8d  js      short loc_1800C0BB7
0x1800c0b8f  mov     rcx, [rsp+8E0h+ppszPath]
0x1800c0b94  lea     rdx, [rsi+1]; unsigned __int64
0x1800c0b98  mov     rax, [rsp+8E0h+var_8A8]
0x1800c0b9d  lea     r8, aAppdataLocal; "\\AppData\\Local\\"
0x1800c0ba4  mov     r9, rsi; unsigned __int64
0x1800c0ba7  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800c0bab  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800c0bb0  add     [rsp+8E0h+var_8A8], rsi
0x1800c0bb5  jmp     short loc_1800C0BD0
0x1800c0bb7  mov     edx, 1A3h
0x1800c0bbc  jmp     loc_1800C0A25
0x1800c0bc1  jbe     short loc_1800C0BD5
0x1800c0bc3  mov     [rsp+8E0h+var_8A8], r13
0x1800c0bc8  mov     [r8+208h], r12w
0x1800c0bd0  mov     r8, [rsp+8E0h+ppszPath]; pszPathIn
0x1800c0bd5  mov     r9, r14; pszMore
0x1800c0bd8  lea     rcx, [rbp+7E0h+pszFile]; pszPathOut
0x1800c0bdf  mov     rdx, r13; cchPathOut
0x1800c0be2  call    cs:__imp_PathCchCombine
0x1800c0be8  mov     ebx, eax
0x1800c0bea  test    eax, eax
0x1800c0bec  jns     short loc_1800C0C0E
0x1800c0bee  mov     edx, 1AAh; void *
0x1800c0bf3  mov     rcx, [rbp+7E8h]; this
0x1800c0bfa  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c0c01  mov     r9d, eax; char *
0x1800c0c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0c09  jmp     loc_1800C0D59
0x1800c0c0e  xor     r9d, r9d; fCreate
0x1800c0c11  mov     [rsp+8E0h+ppstm], r15; ppstm
0x1800c0c16  xor     r8d, r8d; dwAttributes
0x1800c0c19  mov     [r15], r12
0x1800c0c1c  lea     rcx, [rbp+7E0h+pszFile]; pszFile
0x1800c0c23  mov     [rsp+8E0h+pstmTemplate], r12; int
0x1800c0c28  lea     edx, [r9+20h]; grfMode
0x1800c0c2c  call    cs:__imp_SHCreateStreamOnFileEx
0x1800c0c32  test    eax, eax
0x1800c0c34  mov     ecx, r12d
0x1800c0c37  cmovs   ecx, eax
0x1800c0c3a  test    ecx, ecx
0x1800c0c3c  jns     loc_1800C0D00
0x1800c0c42  mov     edx, 5Ch ; '\'; Ch
0x1800c0c47  mov     rcx, r14; Str
0x1800c0c4a  call    cs:__imp_wcsrchr
0x1800c0c50  test    rax, rax
0x1800c0c53  jnz     short loc_1800C0C5A
0x1800c0c55  mov     rax, r14
0x1800c0c58  jmp     short loc_1800C0C5E
0x1800c0c5a  add     rax, 2
0x1800c0c5e  mov     r9, rax; pszMore
0x1800c0c61  lea     r8, pszPathIn; "%windir%\\System32\\Layouts"
0x1800c0c68  mov     rdx, r13; cchPathOut
0x1800c0c6b  lea     rcx, [rbp+7E0h+var_250]; pszPathOut
0x1800c0c72  call    cs:__imp_PathCchCombine
0x1800c0c78  mov     ebx, eax
0x1800c0c7a  test    eax, eax
0x1800c0c7c  jns     short loc_1800C0C88
0x1800c0c7e  mov     edx, 1BBh
0x1800c0c83  jmp     loc_1800C0BF3
0x1800c0c88  lea     rdx, [rsp+8E0h+pv]
0x1800c0c8d  mov     [rsp+8E0h+pv], r12
0x1800c0c92  lea     rcx, [rbp+7E0h+var_250]
0x1800c0c99  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800c0c9e  mov     ebx, eax
0x1800c0ca0  test    eax, eax
0x1800c0ca2  jns     short loc_1800C0CCE
0x1800c0ca4  mov     rcx, [rbp+7E8h]; this
0x1800c0cab  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c0cb2  mov     r9d, eax; char *
0x1800c0cb5  mov     edx, 1BDh; void *
0x1800c0cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0cbf  lea     rcx, [rsp+8E0h+pv]
0x1800c0cc4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c0cc9  jmp     loc_1800C0D59
0x1800c0cce  mov     rbx, [rsp+8E0h+pv]
0x1800c0cd3  mov     r8, r15; struct IStream **
0x1800c0cd6  mov     rdx, rbx; unsigned __int16 *
0x1800c0cd9  call    ?LoadFileStream@CuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGPEAPEAUIStream@@@Z; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::LoadFileStream(ushort const *,IStream * *)
0x1800c0cde  mov     edi, eax
0x1800c0ce0  test    eax, eax
0x1800c0ce2  jns     short loc_1800C0CF2
0x1800c0ce4  lea     rcx, [rsp+8E0h+pv]
0x1800c0ce9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c0cee  mov     ebx, edi
0x1800c0cf0  jmp     short loc_1800C0D59
0x1800c0cf2  test    rbx, rbx
0x1800c0cf5  jz      short loc_1800C0D00
0x1800c0cf7  mov     rcx, rbx; pv
0x1800c0cfa  call    cs:__imp_CoTaskMemFree
0x1800c0d00  mov     rcx, [rsp+8E0h+ppszPath]; pv
0x1800c0d05  test    rcx, rcx
0x1800c0d08  jz      short loc_1800C0D10
0x1800c0d0a  call    cs:__imp_CoTaskMemFree
0x1800c0d10  xor     eax, eax
0x1800c0d12  mov     rcx, [rbp+7E0h+var_40]
0x1800c0d19  xor     rcx, rsp; StackCookie
0x1800c0d1c  call    __security_check_cookie
0x1800c0d21  mov     rbx, [rsp+8E0h+arg_0]
0x1800c0d29  add     rsp, 8B0h
0x1800c0d30  pop     r15
0x1800c0d32  pop     r14
0x1800c0d34  pop     r13
0x1800c0d36  pop     r12
0x1800c0d38  pop     rdi
0x1800c0d39  pop     rsi
0x1800c0d3a  pop     rbp
0x1800c0d3b  retn
0x1800c0d3c  mov     rcx, [rbp+7E8h]; this
0x1800c0d43  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1800c0d4a  mov     r9d, esi; char *
0x1800c0d4d  mov     edx, 1A2h; void *
0x1800c0d52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0d57  mov     ebx, esi
0x1800c0d59  lea     rcx, [rsp+8E0h+ppszPath]
0x1800c0d5e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c0d63  jmp     loc_1800C0A4B
0x1800c0d68  mov     ebx, 80070057h
0x1800c0d6d  mov     edx, 1A7h
0x1800c0d72  jmp     loc_1800C0A25
```
