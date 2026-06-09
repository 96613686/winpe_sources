# CabUtils::CreateCabFile(ushort const *,uchar *,ulong)

- ea: `0x18003dcf8`
- end: `0x18003de5f`
- name: `?CreateCabFile@CabUtils@@SAJPEBGPEAEK@Z`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18003ccf0`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18002407c`
- `0x1800240b8`
- `0x18003c1d8`
- `0x18003dcf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003dd57`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18003dd57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ddcb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003ddcb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003de13`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003de13`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003de25`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18003de25`

## string_xrefs

- `0x18003dd74`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003dde5`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
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
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
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
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow(Str[0], v10);
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
                (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
LABEL_16:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x18003dcf8  mov     [rsp-18h+arg_0], rbx
0x18003dcfd  mov     [rsp-18h+arg_8], rsi
0x18003dd02  push    rbp
0x18003dd03  push    rdi
0x18003dd04  push    r14
0x18003dd06  mov     rbp, rsp
0x18003dd09  sub     rsp, 60h
0x18003dd0d  mov     r14, rdx
0x18003dd10  mov     [rbp+Str], 0
0x18003dd18  mov     rdx, rcx
0x18003dd1b  mov     [rbp+var_18], 0
0x18003dd23  mov     esi, r8d
0x18003dd26  mov     [rbp+var_10], 0
0x18003dd2e  mov     rdi, rcx
0x18003dd31  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003dd35  lea     rcx, [rbp+Str]
0x18003dd39  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003dd3e  mov     ebx, eax
0x18003dd40  test    eax, eax
0x18003dd42  jns     short loc_18003DD4E
0x18003dd44  mov     r9d, eax
0x18003dd47  mov     edx, 18h
0x18003dd4c  jmp     short loc_18003DD70
0x18003dd4e  mov     rcx, [rbp+Str]; Str
0x18003dd52  mov     edx, 5Ch ; '\'; Ch
0x18003dd57  call    cs:__imp_wcsrchr
0x18003dd5d  mov     rcx, rax
0x18003dd60  test    rax, rax
0x18003dd63  jnz     short loc_18003DD85
0x18003dd65  mov     ebx, 80070057h
0x18003dd6a  lea     edx, [rax+1Ah]; void *
0x18003dd6d  mov     r9d, ebx; char *
0x18003dd70  mov     rcx, [rbp+18h]; this
0x18003dd74  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003dd7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dd80  jmp     loc_18003DE3F
0x18003dd85  xor     eax, eax
0x18003dd87  mov     [rcx], ax
0x18003dd8a  mov     rcx, [rbp+Str]; this
0x18003dd8e  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18003dd93  mov     ebx, eax
0x18003dd95  test    eax, eax
0x18003dd97  jns     short loc_18003DDA3
0x18003dd99  mov     r9d, eax
0x18003dd9c  mov     edx, 1Dh
0x18003dda1  jmp     short loc_18003DD70
0x18003dda3  xor     r9d, r9d; lpSecurityAttributes
0x18003dda6  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18003ddaf  mov     [rsp+60h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x18003ddb7  mov     edx, 120116h; dwDesiredAccess
0x18003ddbc  mov     rcx, rdi; lpFileName
0x18003ddbf  mov     [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x18003ddc7  lea     r8d, [r9+1]; dwShareMode
0x18003ddcb  call    cs:__imp_CreateFileW
0x18003ddd1  mov     [rbp+arg_18], rax
0x18003ddd5  mov     rbx, rax
0x18003ddd8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003dddc  jnz     short loc_18003DDFE
0x18003ddde  lea     edx, [rax+2Ah]; void *
0x18003dde1  mov     rcx, [rbp+18h]; this
0x18003dde5  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ddec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ddf1  lea     rcx, [rbp+arg_18]
0x18003ddf5  mov     ebx, eax
0x18003ddf7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003ddfc  jmp     short loc_18003DE3F
0x18003ddfe  xor     r9d, r9d; lpNumberOfBytesWritten
0x18003de01  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x18003de0a  mov     r8d, esi; nNumberOfBytesToWrite
0x18003de0d  mov     rdx, r14; lpBuffer
0x18003de10  mov     rcx, rbx; hFile
0x18003de13  call    cs:__imp_WriteFile
0x18003de19  test    eax, eax
0x18003de1b  jnz     short loc_18003DE22
0x18003de1d  lea     edx, [rax+30h]
0x18003de20  jmp     short loc_18003DDE1
0x18003de22  mov     rcx, rbx; hFile
0x18003de25  call    cs:__imp_FlushFileBuffers
0x18003de2b  test    eax, eax
0x18003de2d  jnz     short loc_18003DE34
0x18003de2f  lea     edx, [rax+32h]
0x18003de32  jmp     short loc_18003DDE1
0x18003de34  lea     rcx, [rbp+arg_18]
0x18003de38  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003de3d  xor     ebx, ebx
0x18003de3f  lea     rcx, [rbp+Str]
0x18003de43  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003de48  lea     r11, [rsp+60h+var_s0]
0x18003de4d  mov     eax, ebx
0x18003de4f  mov     rbx, [r11+20h]
0x18003de53  mov     rsi, [r11+28h]
0x18003de57  mov     rsp, r11
0x18003de5a  pop     r14
0x18003de5c  pop     rdi
0x18003de5d  pop     rbp
0x18003de5e  retn
```
