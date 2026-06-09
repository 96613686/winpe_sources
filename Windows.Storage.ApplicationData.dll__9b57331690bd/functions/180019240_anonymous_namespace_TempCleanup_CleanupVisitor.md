# _anonymous_namespace_::TempCleanup::CleanupVisitor

- ea: `0x180019240`
- end: `0x180019346`
- name: `_anonymous_namespace_::TempCleanup::CleanupVisitor`
- size: `262`
- prototype: `__int64 __fastcall(void *pContext, const wchar_t *wzPath, const _WIN32_FIND_DATAW *findData)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180019240`
- `0x18001934c`
- `0x180019500`
- `0x180040abc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019294`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800192f8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800192f8`
- `ntdll!NtSetInformationFile` at `0x1800192ec`
- `ntdll!NtSetInformationFile` at `0x1800192ec`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001925f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001925f`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180019275`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180019275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001932e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001932e`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::TempCleanup::CleanupVisitor(
        void *pContext,
        const wchar_t *wzPath,
        const _WIN32_FIND_DATAW *findData)
{
  DWORD LastError; // eax
  int v7; // eax
  char *m_ptr; // rdi
  ULONG v9; // edx
  int v10; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > hFile; // [rsp+50h] [rbp+8h] BYREF

  if ( CompareFileTime(&findData->ftLastAccessTime, (const FILETIME *)pContext) >= 0 )
    return 0;
  if ( (findData->dwFileAttributes & 0x10) != 0 )
  {
    if ( !RemoveDirectoryW(wzPath) && GetLastError() != 145 )
    {
      LastError = GetLastError();
      Windows::Storage::StateABIHelpers::Logging::LogDeleteDirectoryError(wzPath, LastError);
    }
    return 0;
  }
  hFile.m_ptr = (void *)-1LL;
  v7 = wil::CreateFileAndEnsureNotLinked(wzPath, &hFile);
  m_ptr = (char *)hFile.m_ptr;
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v7;
  }
  else
  {
    IoStatusBlock = 0;
    v10 = NtSetInformationFile(hFile.m_ptr, &IoStatusBlock, &dword_18004D5B4, 1u, FileDispositionInformation);
    if ( v10 >= 0 )
      goto LABEL_12;
    v9 = RtlNtStatusToDosErrorNoTeb(v10);
  }
  Windows::Storage::StateABIHelpers::Logging::LogDeleteFileError(wzPath, v9, *((_BYTE *)pContext + 8));
  *((_BYTE *)pContext + 8) = 1;
LABEL_12:
  if ( (unsigned __int64)(m_ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(m_ptr);
  return 0;
}

```

## disassembly

```asm
0x180019240  mov     [rsp+arg_8], rbx
0x180019245  mov     [rsp+arg_10], rsi
0x18001924a  push    rdi
0x18001924b  sub     rsp, 40h
0x18001924f  mov     rsi, pContext
0x180019252  mov     rbx, wzPath
0x180019255  mov     wzPath, rsi; lpFileTime2
0x180019258  lea     pContext, [findData+0Ch]; lpFileTime1
0x18001925c  mov     rdi, findData
0x18001925f  call    cs:__imp_CompareFileTime
0x180019265  test    eax, eax
0x180019267  jns     loc_180019334
0x18001926d  test    byte ptr [rdi], 10h
0x180019270  mov     pContext, rbx; path
0x180019273  jz      short loc_1800192A9
0x180019275  call    cs:__imp_RemoveDirectoryW
0x18001927b  test    eax, eax
0x18001927d  jnz     loc_180019334
0x180019283  call    cs:__imp_GetLastError
0x180019289  cmp     eax, 91h
0x18001928e  jz      loc_180019334
0x180019294  call    cs:__imp_GetLastError
0x18001929a  mov     edx, eax; errorCode
0x18001929c  mov     pContext, rbx; filename
0x18001929f  call    ?LogDeleteDirectoryError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogDeleteDirectoryError(ushort const *,long)
0x1800192a4  jmp     loc_180019334
0x1800192a9  lea     wzPath, [rsp+48h+hFile]; fileHandle
0x1800192ae  mov     [rsp+48h+hFile.m_ptr], 0FFFFFFFFFFFFFFFFh
0x1800192b7  call    ?CreateFileAndEnsureNotLinked@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::CreateFileAndEnsureNotLinked(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800192bc  mov     rdi, [rsp+48h+hFile.m_ptr]
0x1800192c1  mov     edx, eax
0x1800192c3  test    eax, eax
0x1800192c5  js      short loc_180019302
0x1800192c7  xorps   xmm0, xmm0
0x1800192ca  mov     [rsp+48h+FileInformationClass], 0Dh; FileInformationClass
0x1800192d2  mov     r9d, 1; Length
0x1800192d8  lea     findData, dword_18004D5B4; FileInformation
0x1800192df  lea     wzPath, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x1800192e4  mov     pContext, rdi; FileHandle
0x1800192e7  movups  xmmword ptr [rsp+48h+IoStatusBlock.___u0], xmm0
0x1800192ec  call    cs:__imp_NtSetInformationFile
0x1800192f2  test    eax, eax
0x1800192f4  jns     short loc_180019321
0x1800192f6  mov     ecx, eax; Status
0x1800192f8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800192fe  mov     edx, eax
0x180019300  jmp     short loc_180019311
0x180019302  and     eax, 1FFF0000h
0x180019307  cmp     eax, 70000h
0x18001930c  jnz     short loc_180019311
0x18001930e  movzx   edx, dx; errorCode
0x180019311  mov     r8b, [rsi+8]; skipTelemetry
0x180019315  mov     pContext, rbx; filename
0x180019318  call    ?LogDeleteFileError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ_N@Z; Windows::Storage::StateABIHelpers::Logging::LogDeleteFileError(ushort const *,long,bool)
0x18001931d  mov     byte ptr [rsi+8], 1
0x180019321  lea     rax, [rdi-1]
0x180019325  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019329  ja      short loc_180019334
0x18001932b  mov     pContext, rdi; hObject
0x18001932e  call    cs:__imp_CloseHandle
0x180019334  mov     rbx, [rsp+48h+arg_8]
0x180019339  xor     eax, eax
0x18001933b  mov     rsi, [rsp+48h+arg_10]
0x180019340  add     rsp, 40h
0x180019344  pop     rdi
0x180019345  retn
```
