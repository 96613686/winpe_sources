# Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::WriteFileToStorage(void const *,ulong,winrt::hstring const &)

- ea: `0x1801c3f2c`
- end: `0x1801c40d9`
- name: `?WriteFileToStorage@DownloaderUtils@Utils@Downloader@Cloud@Storage@Internal@Windows@@SA_NPEBXKAEBUhstring@winrt@@@Z`
- size: `429`
- prototype: `bool __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, const struct winrt::hstring *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800c69f8`
- `0x180142390`
- `0x1801c40e0`

## callees

- `0x180016cf4`
- `0x1800320d4`
- `0x1800ac3a4`
- `0x1801441d0`
- `0x180178038`
- `0x1801c3f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c3f7d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c3f69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c3f69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801c4002`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801c407a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801c4002`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801c407a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::Storage::Cloud::Downloader::Utils::DownloaderUtils::WriteFileToStorage(
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        const struct winrt::hstring *this)
{
  const WCHAR *v5; // rax
  HANDLE FileW; // rbx
  const char *v7; // r9
  const char *v9; // r9
  const char *v10; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  _QWORD v13[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+20h] BYREF

  v5 = winrt::hstring::c_str(this);
  FileW = CreateFileW(v5, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v13[0] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() - 2 > 1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
        v7);
    std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(v13);
    return 0;
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer>::GetImpl'::`2'::impl) )
    {
      if ( lpBuffer && nNumberOfBytesToWrite )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xD5,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
            v9);
        if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
            (const char *)0x8007001DLL,
            dwCreationDisposition);
      }
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
          v10);
      if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\downloader\\lib\\downloaderutils.cpp",
          (const char *)0x8007001DLL,
          dwCreationDispositiona);
    }
    std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(v13);
    return 1;
  }
}

```

## disassembly

```asm
0x1801c3f2c  push    rbx
0x1801c3f2e  push    rbp
0x1801c3f2f  push    rsi
0x1801c3f30  push    rdi
0x1801c3f31  sub     rsp, 58h
0x1801c3f35  mov     edi, edx
0x1801c3f37  mov     rsi, rcx
0x1801c3f3a  mov     rcx, r8; this
0x1801c3f3d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801c3f42  mov     rcx, rax; lpFileName
0x1801c3f45  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1801c3f4e  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801c3f56  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x1801c3f5e  xor     r9d, r9d; lpSecurityAttributes
0x1801c3f61  xor     r8d, r8d; dwShareMode
0x1801c3f64  mov     edx, 40000000h; dwDesiredAccess
0x1801c3f69  call    cs:__imp_CreateFileW
0x1801c3f6f  mov     rbx, rax
0x1801c3f72  mov     [rsp+78h+var_38], rax
0x1801c3f77  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801c3f7b  jnz     short loc_1801C3FB3
0x1801c3f7d  call    cs:__imp_GetLastError
0x1801c3f83  add     eax, 0FFFFFFFEh
0x1801c3f86  cmp     eax, 1
0x1801c3f89  jbe     short loc_1801C3FA2
0x1801c3f8b  mov     rcx, [rsp+78h]; this
0x1801c3f90  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1801c3f97  mov     edx, 0C7h; void *
0x1801c3f9c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c3fa2  lea     rcx, [rsp+78h+var_38]
0x1801c3fa7  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1801c3fac  xor     al, al
0x1801c3fae  jmp     loc_1801C40D0
0x1801c3fb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer> `wil::Feature<__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer>::GetImpl(void)'::`2'::impl
0x1801c3fba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteEmptyFileIfEmptyAssetResponseFromServer>::__private_IsEnabled(void)
0x1801c3fbf  test    al, al
0x1801c3fc1  jz      loc_1801C4050
0x1801c3fc7  test    rsi, rsi
0x1801c3fca  jz      loc_1801C40C4
0x1801c3fd0  test    edi, edi
0x1801c3fd2  jz      loc_1801C40C4
0x1801c3fd8  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1801c3fe3  mov     rbp, [rsp+78h]
0x1801c3fe8  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; int
0x1801c3ff1  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801c3ff9  mov     r8d, edi; nNumberOfBytesToWrite
0x1801c3ffc  mov     rdx, rsi; lpBuffer
0x1801c3fff  mov     rcx, rbx; hFile
0x1801c4002  call    cs:__imp_WriteFile
0x1801c4008  test    eax, eax
0x1801c400a  jnz     short loc_1801C4021
0x1801c400c  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1801c4013  mov     edx, 0D5h; void *
0x1801c4018  mov     rcx, rbp; this
0x1801c401b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c4021  cmp     [rsp+78h+NumberOfBytesWritten], edi
0x1801c4028  setz    al
0x1801c402b  mov     rcx, [rsp+78h]; this
0x1801c4030  test    al, al
0x1801c4032  jnz     loc_1801C40C4
0x1801c4038  mov     r9d, 8007001Dh; char *
0x1801c403e  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1801c4045  mov     edx, 0D7h; void *
0x1801c404a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801c4050  mov     [rsp+78h+NumberOfBytesWritten], 0
0x1801c405b  mov     rbp, [rsp+78h]
0x1801c4060  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; int
0x1801c4069  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801c4071  mov     r8d, edi; nNumberOfBytesToWrite
0x1801c4074  mov     rdx, rsi; lpBuffer
0x1801c4077  mov     rcx, rbx; hFile
0x1801c407a  call    cs:__imp_WriteFile
0x1801c4080  test    eax, eax
0x1801c4082  jnz     short loc_1801C4099
0x1801c4084  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1801c408b  mov     edx, 0DEh; void *
0x1801c4090  mov     rcx, rbp; this
0x1801c4093  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801c4099  cmp     [rsp+78h+NumberOfBytesWritten], edi
0x1801c40a0  setz    al
0x1801c40a3  mov     rcx, [rsp+78h]; this
0x1801c40a8  test    al, al
0x1801c40aa  jnz     short loc_1801C40C4
0x1801c40ac  mov     r9d, 8007001Dh; char *
0x1801c40b2  lea     r8, aOnecoreuapShel_38; "onecoreuap\\shell\\cloudstore\\download"...
0x1801c40b9  mov     edx, 0E0h; void *
0x1801c40be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801c40c4  lea     rcx, [rsp+78h+var_38]
0x1801c40c9  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x1801c40ce  mov     al, 1
0x1801c40d0  add     rsp, 58h
0x1801c40d4  pop     rdi
0x1801c40d5  pop     rsi
0x1801c40d6  pop     rbp
0x1801c40d7  pop     rbx
0x1801c40d8  retn
```
