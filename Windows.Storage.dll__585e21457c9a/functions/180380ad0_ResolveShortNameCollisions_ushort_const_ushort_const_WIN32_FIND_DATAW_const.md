# ResolveShortNameCollisions(ushort const *,ushort const *,_WIN32_FIND_DATAW const *)

- ea: `0x180380ad0`
- end: `0x180380d85`
- name: `?ResolveShortNameCollisions@@YAHPEBG0PEBU_WIN32_FIND_DATAW@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, LPCWSTR lpString1, const struct _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18035c634`

## callees

- `0x1800aa710`
- `0x1801acc30`
- `0x180380ad0`
- `0x180380d8c`
- `0x180380e20`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180380d3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180380d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180380c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180380c47`
- `ntdll!RtlGetLastNtStatus` at `0x180380cdf`
- `ntdll!RtlGetLastNtStatus` at `0x180380d26`
- `ntdll!RtlGetLastNtStatus` at `0x180380cdf`
- `ntdll!RtlGetLastNtStatus` at `0x180380d26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180380b12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180380b27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180380b12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180380b27`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180380c14`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180380c14`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180380d11`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180380d11`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180380baa`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180380baa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180380cfa`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180380cfa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380cd5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380d1e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380cd5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180380d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380c91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380c91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180380d75`
- `SHCORE!__imp_IsNotifySuspended` at `0x180380c23`
- `SHCORE!__imp_IsNotifySuspended` at `0x180380d42`
- `SHCORE!__imp_IsNotifySuspended` at `0x180380c23`
- `SHCORE!__imp_IsNotifySuspended` at `0x180380d42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResolveShortNameCollisions(
        LPCWSTR lpPathName,
        LPCWSTR lpString1,
        const struct _WIN32_FIND_DATAW *a3)
{
  WCHAR *cAlternateFileName; // r14
  WCHAR *v7; // rcx
  void *v8; // rcx
  LONG v9; // edi
  void *v10; // rbx
  WCHAR *v11; // rsi
  HANDLE FileW; // r14
  NTSTATUS LastNtStatus; // eax
  DWORD FileAttributesW; // eax
  BOOL v16; // edi
  NTSTATUS v17; // eax
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  cAlternateFileName = a3->cAlternateFileName;
  if ( lstrcmpiW(lpString1, a3->cAlternateFileName) || !lstrcmpiW(cAlternateFileName, a3->cFileName) )
    return 0;
  lpFileName = 0;
  if ( (int)PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
              lpPathName,
              lpString1,
              &lpFileName) < 0 )
  {
LABEL_4:
    v7 = (WCHAR *)lpFileName;
    if ( !lpFileName )
      return 0;
LABEL_21:
    CoTaskMemFree(v7);
    return 0;
  }
  pv = 0;
  if ( (int)PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
              lpPathName,
              a3->cFileName,
              &pv) < 0 )
  {
    v8 = pv;
    if ( !pv )
      goto LABEL_4;
    goto LABEL_8;
  }
  GetTempFileNameW(lpPathName, &c_szNULL, 1u, TempFileName);
  v9 = (a3->dwFileAttributes & 0x10) != 0 ? 0x20000 : 1;
  v10 = pv;
  if ( !(unsigned int)SHMoveFile(pv, TempFileName, v9) )
  {
    if ( !v10 )
      goto LABEL_4;
    v8 = v10;
LABEL_8:
    CoTaskMemFree(v8);
    goto LABEL_4;
  }
  v11 = (WCHAR *)lpFileName;
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 2u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_17:
    SHMoveFile(TempFileName, v10, v9);
    if ( v10 )
      CoTaskMemFree(v10);
    if ( !v11 )
      return 0;
    v7 = v11;
    goto LABEL_21;
  }
  if ( !(unsigned int)IsNotifySuspended() )
    SHChangeNotify(2, 5u, v11, 0);
  CloseHandle(FileW);
  if ( !(unsigned int)SHMoveFile(TempFileName, v10, v9) )
  {
    DeleteFileWithRetry(v11);
    goto LABEL_17;
  }
  SHChangeNotify(0x2000, 5u, v10, 0);
  if ( DeleteFileW(v11) )
    goto LABEL_41;
  LastNtStatus = RtlGetLastNtStatus();
  if ( LastNtStatus == -1073741738 )
    goto LABEL_41;
  if ( LastNtStatus != -1073741535 )
    goto LABEL_34;
  FileAttributesW = GetFileAttributesW(v11);
  if ( FileAttributesW == -1 || (FileAttributesW & 1) == 0 || !SetFileAttributesW(v11, FileAttributesW & 0xFFFFFFFE) )
    goto LABEL_31;
  v16 = DeleteFileW(v11);
  v17 = RtlGetLastNtStatus();
  if ( v16 )
  {
LABEL_41:
    if ( !(unsigned int)IsNotifySuspended() )
      SHChangeNotify(4, 5u, v11, 0);
    goto LABEL_34;
  }
  if ( v17 == -1073741535 )
LABEL_31:
    SetLastError(0x20u);
LABEL_34:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v11 )
    CoTaskMemFree(v11);
  return 1;
}

```

## disassembly

```asm
0x180380ad0  mov     [rsp-8+arg_18], rbx
0x180380ad5  push    rbp
0x180380ad6  push    rsi
0x180380ad7  push    rdi
0x180380ad8  push    r14
0x180380ada  push    r15
0x180380adc  lea     rbp, [rsp-170h]
0x180380ae4  sub     rsp, 270h
0x180380aeb  mov     rax, cs:__security_cookie
0x180380af2  xor     rax, rsp
0x180380af5  mov     [rbp+190h+var_30], rax
0x180380afc  mov     rsi, r8
0x180380aff  mov     r15, rdx
0x180380b02  mov     rdi, rcx
0x180380b05  lea     r14, [r8+234h]
0x180380b0c  mov     rdx, r14; lpString2
0x180380b0f  mov     rcx, r15; lpString1
0x180380b12  call    cs:__imp_lstrcmpiW
0x180380b18  test    eax, eax
0x180380b1a  jnz     loc_180380C97
0x180380b20  lea     rdx, [rsi+2Ch]; lpString2
0x180380b24  mov     rcx, r14; lpString1
0x180380b27  call    cs:__imp_lstrcmpiW
0x180380b2d  test    eax, eax
0x180380b2f  jz      loc_180380C97
0x180380b35  mov     [rsp+290h+lpFileName], 0
0x180380b3e  lea     r8, [rsp+290h+lpFileName]
0x180380b43  mov     rdx, r15
0x180380b46  mov     rcx, rdi
0x180380b49  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180380b4e  test    eax, eax
0x180380b50  jns     short loc_180380B65
0x180380b52  mov     rcx, [rsp+290h+lpFileName]
0x180380b57  test    rcx, rcx
0x180380b5a  jz      loc_180380C97
0x180380b60  jmp     loc_180380C91
0x180380b65  mov     [rsp+290h+pv], 0
0x180380b6e  lea     r8, [rsp+290h+pv]
0x180380b73  lea     rdx, [rsi+2Ch]
0x180380b77  mov     rcx, rdi
0x180380b7a  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180380b7f  test    eax, eax
0x180380b81  jns     short loc_180380B95
0x180380b83  mov     rcx, [rsp+290h+pv]; pv
0x180380b88  test    rcx, rcx
0x180380b8b  jz      short loc_180380B52
0x180380b8d  call    cs:__imp_CoTaskMemFree
0x180380b93  jmp     short loc_180380B52
0x180380b95  lea     r9, [rsp+290h+TempFileName]; lpTempFileName
0x180380b9a  mov     r8d, 1; uUnique
0x180380ba0  lea     rdx, c_szNULL; lpPrefixString
0x180380ba7  mov     rcx, rdi; lpPathName
0x180380baa  call    cs:__imp_GetTempFileNameW
0x180380bb0  mov     eax, [rsi]
0x180380bb2  and     al, 10h
0x180380bb4  neg     al
0x180380bb6  sbb     edi, edi
0x180380bb8  and     edi, 1FFFFh
0x180380bbe  inc     edi
0x180380bc0  mov     r8d, edi; wEventId
0x180380bc3  lea     rdx, [rsp+290h+TempFileName]; dwItem2
0x180380bc8  mov     rbx, [rsp+290h+pv]
0x180380bcd  mov     rcx, rbx; dwItem1
0x180380bd0  call    SHMoveFile
0x180380bd5  test    eax, eax
0x180380bd7  jnz     short loc_180380BE7
0x180380bd9  test    rbx, rbx
0x180380bdc  jz      loc_180380B52
0x180380be2  mov     rcx, rbx
0x180380be5  jmp     short loc_180380B8D
0x180380be7  mov     rsi, [rsp+290h+lpFileName]
0x180380bec  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x180380bf5  mov     [rsp+290h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180380bfd  mov     [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x180380c05  xor     r9d, r9d; lpSecurityAttributes
0x180380c08  mov     edx, 0C0000000h; dwDesiredAccess
0x180380c0d  lea     r8d, [r9+3]; dwShareMode
0x180380c11  mov     rcx, rsi; lpFileName
0x180380c14  call    cs:__imp_CreateFileW
0x180380c1a  mov     r14, rax
0x180380c1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180380c21  jz      short loc_180380C69
0x180380c23  call    cs:__imp_IsNotifySuspended
0x180380c29  mov     r15d, 5
0x180380c2f  test    eax, eax
0x180380c31  jnz     short loc_180380C44
0x180380c33  xor     r9d, r9d; dwItem2
0x180380c36  mov     r8, rsi; dwItem1
0x180380c39  mov     edx, r15d; uFlags
0x180380c3c  lea     ecx, [rax+2]; wEventId
0x180380c3f  call    SHChangeNotify
0x180380c44  mov     rcx, r14; hObject
0x180380c47  call    cs:__imp_CloseHandle
0x180380c4d  mov     r8d, edi; wEventId
0x180380c50  mov     rdx, rbx; dwItem2
0x180380c53  lea     rcx, [rsp+290h+TempFileName]; dwItem1
0x180380c58  call    SHMoveFile
0x180380c5d  test    eax, eax
0x180380c5f  jnz     short loc_180380CBF
0x180380c61  mov     rcx, rsi; lpFileName
0x180380c64  call    ?DeleteFileWithRetry@@YA_NPEBG@Z; DeleteFileWithRetry(ushort const *)
0x180380c69  mov     r8d, edi; wEventId
0x180380c6c  mov     rdx, rbx; dwItem2
0x180380c6f  lea     rcx, [rsp+290h+TempFileName]; dwItem1
0x180380c74  call    SHMoveFile
0x180380c79  nop
0x180380c7a  test    rbx, rbx
0x180380c7d  jz      short loc_180380C89
0x180380c7f  mov     rcx, rbx; pv
0x180380c82  call    cs:__imp_CoTaskMemFree
0x180380c88  nop
0x180380c89  test    rsi, rsi
0x180380c8c  jz      short loc_180380C97
0x180380c8e  mov     rcx, rsi; pv
0x180380c91  call    cs:__imp_CoTaskMemFree
0x180380c97  xor     eax, eax
0x180380c99  mov     rcx, [rbp+190h+var_30]
0x180380ca0  xor     rcx, rsp; StackCookie
0x180380ca3  call    __security_check_cookie
0x180380ca8  mov     rbx, [rsp+290h+arg_18]
0x180380cb0  add     rsp, 270h
0x180380cb7  pop     r15
0x180380cb9  pop     r14
0x180380cbb  pop     rdi
0x180380cbc  pop     rsi
0x180380cbd  pop     rbp
0x180380cbe  retn
0x180380cbf  xor     r9d, r9d; dwItem2
0x180380cc2  mov     r8, rbx; dwItem1
0x180380cc5  mov     edx, r15d; uFlags
0x180380cc8  mov     ecx, 2000h; wEventId
0x180380ccd  call    SHChangeNotify
0x180380cd2  mov     rcx, rsi; lpFileName
0x180380cd5  call    cs:__imp_DeleteFileW
0x180380cdb  test    eax, eax
0x180380cdd  jnz     short loc_180380D42
0x180380cdf  call    cs:__imp_RtlGetLastNtStatus
0x180380ce5  cmp     eax, 0C0000056h
0x180380cea  jz      short loc_180380D42
0x180380cec  mov     r14d, 0C0000121h
0x180380cf2  cmp     eax, r14d
0x180380cf5  jnz     short loc_180380D5E
0x180380cf7  mov     rcx, rsi; lpFileName
0x180380cfa  call    cs:__imp_GetFileAttributesW
0x180380d00  cmp     eax, 0FFFFFFFFh
0x180380d03  jz      short loc_180380D35
0x180380d05  test    al, 1
0x180380d07  jz      short loc_180380D35
0x180380d09  and     eax, 0FFFFFFFEh
0x180380d0c  mov     edx, eax; dwFileAttributes
0x180380d0e  mov     rcx, rsi; lpFileName
0x180380d11  call    cs:__imp_SetFileAttributesW
0x180380d17  test    eax, eax
0x180380d19  jz      short loc_180380D35
0x180380d1b  mov     rcx, rsi; lpFileName
0x180380d1e  call    cs:__imp_DeleteFileW
0x180380d24  mov     edi, eax
0x180380d26  call    cs:__imp_RtlGetLastNtStatus
0x180380d2c  test    edi, edi
0x180380d2e  jnz     short loc_180380D42
0x180380d30  cmp     eax, r14d
0x180380d33  jnz     short loc_180380D5E
0x180380d35  mov     ecx, 20h ; ' '; dwErrCode
0x180380d3a  call    cs:__imp_SetLastError
0x180380d40  jmp     short loc_180380D5E
0x180380d42  call    cs:__imp_IsNotifySuspended
0x180380d48  test    eax, eax
0x180380d4a  jnz     short loc_180380D5E
0x180380d4c  xor     r9d, r9d; dwItem2
0x180380d4f  mov     r8, rsi; dwItem1
0x180380d52  mov     edx, r15d; uFlags
0x180380d55  lea     ecx, [rax+4]; wEventId
0x180380d58  call    SHChangeNotify
0x180380d5d  nop
0x180380d5e  test    rbx, rbx
0x180380d61  jz      short loc_180380D6D
0x180380d63  mov     rcx, rbx; pv
0x180380d66  call    cs:__imp_CoTaskMemFree
0x180380d6c  nop
0x180380d6d  test    rsi, rsi
0x180380d70  jz      short loc_180380D7B
0x180380d72  mov     rcx, rsi; pv
0x180380d75  call    cs:__imp_CoTaskMemFree
0x180380d7b  mov     eax, 1
0x180380d80  jmp     loc_180380C99
```
