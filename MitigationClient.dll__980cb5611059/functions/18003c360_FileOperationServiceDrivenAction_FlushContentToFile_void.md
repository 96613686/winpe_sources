# FileOperationServiceDrivenAction::FlushContentToFile(void)

- ea: `0x18003c360`
- end: `0x18003c4c9`
- name: `?FlushContentToFile@FileOperationServiceDrivenAction@@AEAAJXZ`
- size: `361`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18003c7a0`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18002407c`
- `0x18002480c`
- `0x18003c1d8`
- `0x18003c360`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003c3b0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003c3b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c427`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c427`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003c47e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003c47e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003c492`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003c492`

## string_xrefs

- `0x18003c3cf`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c443`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`

## pseudocode

```c
__int64 __fastcall FileOperationServiceDrivenAction::FlushContentToFile(LPCWSTR *this)
{
  int v2; // eax
  unsigned int LastError; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  const unsigned __int16 *v6; // rdx
  wchar_t *v7; // rcx
  int DirectoryDeepNoThrow; // eax
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rbx
  __int64 v12; // rdx
  DWORD v13; // r8d
  LPCWSTR v14; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  wchar_t *Str[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF
  HANDLE v20; // [rsp+88h] [rbp+28h] BYREF

  memset(Str, 0, 24);
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(Str);
  LastError = v2;
  if ( v2 < 0 )
  {
    v4 = (unsigned int)v2;
    v5 = 137;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
      (const char *)v4,
      dwCreationDisposition);
    goto LABEL_16;
  }
  v7 = wcsrchr(Str[0], 0x5Cu);
  if ( !v7 )
  {
    LastError = -2147024809;
    v5 = 140;
    v4 = 2147942487LL;
    goto LABEL_5;
  }
  *v7 = 0;
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(Str[0], v6);
  LastError = DirectoryDeepNoThrow;
  if ( DirectoryDeepNoThrow < 0 )
  {
    v4 = (unsigned int)DirectoryDeepNoThrow;
    v5 = 143;
    goto LABEL_5;
  }
  FileW = CreateFileW(this[7], 0x120116u, 1u, 0, 2u, 0x80u, 0);
  v20 = FileW;
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v12 = 154;
  }
  else
  {
    v13 = *((_DWORD *)this + 32);
    v14 = this[15];
    NumberOfBytesWritten = 0;
    if ( WriteFile(FileW, v14, v13, &NumberOfBytesWritten, 0) )
    {
      if ( FlushFileBuffers(v11) )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
        LastError = 0;
        goto LABEL_16;
      }
      v12 = 164;
    }
    else
    {
      v12 = 162;
    }
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v12,
                (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
                v10);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
LABEL_16:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x18003c360  mov     [rsp-18h+arg_10], rbx
0x18003c365  push    rbp
0x18003c366  push    rsi
0x18003c367  push    rdi
0x18003c368  mov     rbp, rsp
0x18003c36b  sub     rsp, 60h
0x18003c36f  mov     rdi, rcx
0x18003c372  mov     [rbp+Str], 0
0x18003c37a  lea     rdx, [rcx+38h]
0x18003c37e  mov     [rbp+var_18], 0
0x18003c386  lea     rcx, [rbp+Str]
0x18003c38a  mov     [rbp+var_10], 0
0x18003c392  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18003c397  mov     ebx, eax
0x18003c399  test    eax, eax
0x18003c39b  jns     short loc_18003C3A7
0x18003c39d  mov     r9d, eax
0x18003c3a0  mov     edx, 89h
0x18003c3a5  jmp     short loc_18003C3CB
0x18003c3a7  mov     rcx, [rbp+Str]; Str
0x18003c3ab  mov     edx, 5Ch ; '\'; Ch
0x18003c3b0  call    cs:__imp_wcsrchr
0x18003c3b6  mov     rcx, rax
0x18003c3b9  test    rax, rax
0x18003c3bc  jnz     short loc_18003C3E0
0x18003c3be  mov     ebx, 80070057h
0x18003c3c3  mov     edx, 8Ch; void *
0x18003c3c8  mov     r9d, ebx; char *
0x18003c3cb  mov     rcx, [rbp+18h]; this
0x18003c3cf  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c3d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3db  jmp     loc_18003C4AE
0x18003c3e0  xor     eax, eax
0x18003c3e2  mov     [rcx], ax
0x18003c3e5  mov     rcx, [rbp+Str]; this
0x18003c3e9  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003c3ee  mov     ebx, eax
0x18003c3f0  test    eax, eax
0x18003c3f2  jns     short loc_18003C3FE
0x18003c3f4  mov     r9d, eax
0x18003c3f7  mov     edx, 8Fh
0x18003c3fc  jmp     short loc_18003C3CB
0x18003c3fe  mov     rcx, [rdi+38h]; lpFileName
0x18003c402  xor     r9d, r9d; lpSecurityAttributes
0x18003c405  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18003c40e  mov     edx, 120116h; dwDesiredAccess
0x18003c413  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c41b  mov     [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x18003c423  lea     r8d, [r9+1]; dwShareMode
0x18003c427  call    cs:__imp_CreateFileW
0x18003c42d  mov     [rbp+arg_8], rax
0x18003c431  mov     rbx, rax
0x18003c434  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c438  jnz     short loc_18003C45C
0x18003c43a  mov     edx, 9Ah; void *
0x18003c43f  mov     rcx, [rbp+18h]; this
0x18003c443  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c44a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c44f  lea     rcx, [rbp+arg_8]
0x18003c453  mov     ebx, eax
0x18003c455  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003c45a  jmp     short loc_18003C4AE
0x18003c45c  mov     r8d, [rdi+80h]; nNumberOfBytesToWrite
0x18003c463  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003c467  mov     rdx, [rdi+78h]; lpBuffer
0x18003c46b  mov     rcx, rbx; hFile
0x18003c46e  mov     [rbp+NumberOfBytesWritten], 0
0x18003c475  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x18003c47e  call    cs:__imp_WriteFile
0x18003c484  test    eax, eax
0x18003c486  jnz     short loc_18003C48F
0x18003c488  mov     edx, 0A2h
0x18003c48d  jmp     short loc_18003C43F
0x18003c48f  mov     rcx, rbx; hFile
0x18003c492  call    cs:__imp_FlushFileBuffers
0x18003c498  test    eax, eax
0x18003c49a  jnz     short loc_18003C4A3
0x18003c49c  mov     edx, 0A4h
0x18003c4a1  jmp     short loc_18003C43F
0x18003c4a3  lea     rcx, [rbp+arg_8]
0x18003c4a7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003c4ac  xor     ebx, ebx
0x18003c4ae  lea     rcx, [rbp+Str]
0x18003c4b2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003c4b7  mov     eax, ebx
0x18003c4b9  mov     rbx, [rsp+60h+arg_10]
0x18003c4c1  add     rsp, 60h
0x18003c4c5  pop     rdi
0x18003c4c6  pop     rsi
0x18003c4c7  pop     rbp
0x18003c4c8  retn
```
