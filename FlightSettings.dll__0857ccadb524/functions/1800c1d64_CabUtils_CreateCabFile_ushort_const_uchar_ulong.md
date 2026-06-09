# CabUtils::CreateCabFile(ushort const *,uchar *,ulong)

- ea: `0x1800c1d64`
- end: `0x1800c1ecb`
- name: `?CreateCabFile@CabUtils@@SAJPEBGPEAEK@Z`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9cd0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x1800a61b0`
- `0x1800c1d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c1dc3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c1dc3`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800c1e91`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800c1e91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1e37`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1e37`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1e7f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1e7f`

## string_xrefs

- `0x1800c1de0`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c1e51`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CabUtils::CreateCabFile(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rdx
  wchar_t *v11; // rcx
  int DirectoryDeepNoThrow; // eax
  HANDLE FileW; // rax
  const char *v14; // r9
  void *v15; // rbx
  __int64 v16; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  wchar_t *Str[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HANDLE v21; // [rsp+98h] [rbp+38h] BYREF

  memset(Str, 0, 24);
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         Str,
         lpFileName,
         -1);
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 24;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
      (const char *)v8,
      dwCreationDisposition);
    goto LABEL_16;
  }
  v11 = wcsrchr(Str[0], 0x5Cu);
  if ( !v11 )
  {
    LastError = -2147024809;
    v9 = 26;
    v8 = 2147942487LL;
    goto LABEL_5;
  }
  *v11 = 0;
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Str[0], v10);
  LastError = DirectoryDeepNoThrow;
  if ( DirectoryDeepNoThrow < 0 )
  {
    v8 = (unsigned int)DirectoryDeepNoThrow;
    v9 = 29;
    goto LABEL_5;
  }
  FileW = CreateFileW(lpFileName, 0x120116u, 1u, 0, 2u, 0x100u, 0);
  v21 = FileW;
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v16 = 41;
  }
  else if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, 0, 0) )
  {
    if ( FlushFileBuffers(v15) )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
      LastError = 0;
      goto LABEL_16;
    }
    v16 = 50;
  }
  else
  {
    v16 = 48;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v16,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
                v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
LABEL_16:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x1800c1d64  mov     [rsp-18h+arg_0], rbx
0x1800c1d69  mov     [rsp-18h+arg_8], rsi
0x1800c1d6e  push    rbp
0x1800c1d6f  push    rdi
0x1800c1d70  push    r14
0x1800c1d72  mov     rbp, rsp
0x1800c1d75  sub     rsp, 60h
0x1800c1d79  mov     r14, rdx
0x1800c1d7c  mov     [rbp+Str], 0
0x1800c1d84  mov     rdx, rcx
0x1800c1d87  mov     [rbp+var_18], 0
0x1800c1d8f  mov     esi, r8d
0x1800c1d92  mov     [rbp+var_10], 0
0x1800c1d9a  mov     rdi, rcx
0x1800c1d9d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c1da1  lea     rcx, [rbp+Str]
0x1800c1da5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800c1daa  mov     ebx, eax
0x1800c1dac  test    eax, eax
0x1800c1dae  jns     short loc_1800C1DBA
0x1800c1db0  mov     r9d, eax
0x1800c1db3  mov     edx, 18h
0x1800c1db8  jmp     short loc_1800C1DDC
0x1800c1dba  mov     rcx, [rbp+Str]; Str
0x1800c1dbe  mov     edx, 5Ch ; '\'; Ch
0x1800c1dc3  call    cs:__imp_wcsrchr
0x1800c1dc9  mov     rcx, rax
0x1800c1dcc  test    rax, rax
0x1800c1dcf  jnz     short loc_1800C1DF1
0x1800c1dd1  mov     ebx, 80070057h
0x1800c1dd6  lea     edx, [rax+1Ah]; void *
0x1800c1dd9  mov     r9d, ebx; char *
0x1800c1ddc  mov     rcx, [rbp+18h]; this
0x1800c1de0  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c1de7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1dec  jmp     loc_1800C1EAB
0x1800c1df1  xor     eax, eax
0x1800c1df3  mov     [rcx], ax
0x1800c1df6  mov     rcx, [rbp+Str]; this
0x1800c1dfa  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800c1dff  mov     ebx, eax
0x1800c1e01  test    eax, eax
0x1800c1e03  jns     short loc_1800C1E0F
0x1800c1e05  mov     r9d, eax
0x1800c1e08  mov     edx, 1Dh
0x1800c1e0d  jmp     short loc_1800C1DDC
0x1800c1e0f  xor     r9d, r9d; lpSecurityAttributes
0x1800c1e12  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x1800c1e1b  mov     [rsp+60h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x1800c1e23  mov     edx, 120116h; dwDesiredAccess
0x1800c1e28  mov     rcx, rdi; lpFileName
0x1800c1e2b  mov     [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c1e33  lea     r8d, [r9+1]; dwShareMode
0x1800c1e37  call    cs:__imp_CreateFileW
0x1800c1e3d  mov     [rbp+arg_18], rax
0x1800c1e41  mov     rbx, rax
0x1800c1e44  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c1e48  jnz     short loc_1800C1E6A
0x1800c1e4a  lea     edx, [rax+2Ah]; void *
0x1800c1e4d  mov     rcx, [rbp+18h]; this
0x1800c1e51  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c1e58  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c1e5d  lea     rcx, [rbp+arg_18]
0x1800c1e61  mov     ebx, eax
0x1800c1e63  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c1e68  jmp     short loc_1800C1EAB
0x1800c1e6a  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800c1e6d  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x1800c1e76  mov     r8d, esi; nNumberOfBytesToWrite
0x1800c1e79  mov     rdx, r14; lpBuffer
0x1800c1e7c  mov     rcx, rbx; hFile
0x1800c1e7f  call    cs:__imp_WriteFile
0x1800c1e85  test    eax, eax
0x1800c1e87  jnz     short loc_1800C1E8E
0x1800c1e89  lea     edx, [rax+30h]
0x1800c1e8c  jmp     short loc_1800C1E4D
0x1800c1e8e  mov     rcx, rbx; hFile
0x1800c1e91  call    cs:__imp_FlushFileBuffers
0x1800c1e97  test    eax, eax
0x1800c1e99  jnz     short loc_1800C1EA0
0x1800c1e9b  lea     edx, [rax+32h]
0x1800c1e9e  jmp     short loc_1800C1E4D
0x1800c1ea0  lea     rcx, [rbp+arg_18]
0x1800c1ea4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c1ea9  xor     ebx, ebx
0x1800c1eab  lea     rcx, [rbp+Str]
0x1800c1eaf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c1eb4  lea     r11, [rsp+60h+var_s0]
0x1800c1eb9  mov     eax, ebx
0x1800c1ebb  mov     rbx, [r11+20h]
0x1800c1ebf  mov     rsi, [r11+28h]
0x1800c1ec3  mov     rsp, r11
0x1800c1ec6  pop     r14
0x1800c1ec8  pop     rdi
0x1800c1ec9  pop     rbp
0x1800c1eca  retn
```
