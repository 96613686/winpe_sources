# WaasMedic::CreateHashFromFile(ushort const *,uchar *,ulong)

- ea: `0x18002cc10`
- end: `0x18002cea3`
- name: `?CreateHashFromFile@WaasMedic@@YAJPEBGPEAEK@Z`
- size: `659`
- prototype: `int(WaasMedic *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002da64`

## callees

- `0x180009a34`
- `0x18002cc10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ccb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ccb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cc4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cc4e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002cd6a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002cd6a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002cdc4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18002cdc4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cde6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002cde6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cd0e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002ce44`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002cd0e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18002ce44`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002cd23`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002ce59`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002cd23`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002ce59`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002ce27`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18002ce27`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002cd98`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18002cd98`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002cd36`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002cdfe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002ce6c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002cd36`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002cdfe`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002ce6c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002cce1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002cce1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002cc8a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002cc8a`

## pseudocode

```c
__int64 __fastcall WaasMedic::CreateHashFromFile(const WCHAR *this, BYTE *a2, unsigned __int8 *a3)
{
  HANDLE FileW; // rax
  const char *v5; // r9
  void *v6; // rbx
  HANDLE FileMappingW; // rax
  const char *v9; // r9
  void *v10; // rdi
  unsigned int LastError; // edi
  const char *v12; // r9
  __int64 v13; // rdx
  unsigned int v14; // esi
  DWORD FileSize; // esi
  DWORD pdwDataLen; // [rsp+40h] [rbp-28h] BYREF
  HCRYPTPROV hProv; // [rsp+48h] [rbp-20h] BYREF
  HCRYPTHASH hHash; // [rsp+50h] [rbp-18h] BYREF
  LPCVOID lpBaseAddress; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  pdwDataLen = 32;
  FileW = CreateFileW(this, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( !FileW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x72,
             (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
             v5);
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v10 = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7A,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
                  v9);
    if ( v6 != (void *)-1LL )
      CloseHandle(v6);
    return LastError;
  }
  hProv = 0;
  hHash = 0;
  lpBaseAddress = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( !lpBaseAddress )
  {
    v13 = 127;
LABEL_9:
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\waasdownloaderhelper.cpp",
            v12);
    if ( hHash )
    {
      CryptDestroyHash(hHash);
      hHash = 0;
    }
    if ( hProv )
    {
      CryptReleaseContext(hProv, 0);
      hProv = 0;
    }
    if ( lpBaseAddress )
    {
      UnmapViewOfFile(lpBaseAddress);
      lpBaseAddress = 0;
    }
    if ( v10 != (void *)-1LL )
      CloseHandle(v10);
    if ( v6 != (void *)-1LL )
      CloseHandle(v6);
    return v14;
  }
  FileSize = GetFileSize(v6, 0);
  if ( FileSize == -1 )
  {
    v13 = 130;
    goto LABEL_9;
  }
  if ( !CryptAcquireContextW(&hProv, 0, 0, 0x18u, 0xF0000000) )
  {
    v13 = 136;
    goto LABEL_9;
  }
  if ( !CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash) )
  {
    v13 = 142;
    goto LABEL_9;
  }
  if ( !CryptHashData(hHash, (const BYTE *)lpBaseAddress, FileSize, 0) )
  {
    v13 = 143;
    goto LABEL_9;
  }
  if ( !UnmapViewOfFile(lpBaseAddress) )
  {
    v13 = 145;
    goto LABEL_9;
  }
  if ( !CryptGetHashParam(hHash, 2u, a2, &pdwDataLen, 0) )
  {
    v13 = 147;
    goto LABEL_9;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( lpBaseAddress )
  {
    UnmapViewOfFile(lpBaseAddress);
    lpBaseAddress = 0;
  }
  if ( v10 != (void *)-1LL )
    CloseHandle(v10);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  return 0;
}

```

## disassembly

```asm
0x18002cc10  push    rbp
0x18002cc12  push    rbx
0x18002cc13  push    rsi
0x18002cc14  push    rdi
0x18002cc15  push    r14
0x18002cc17  push    r15
0x18002cc19  mov     rbp, rsp
0x18002cc1c  sub     rsp, 68h
0x18002cc20  xor     r15d, r15d
0x18002cc23  mov     [rbp+pdwDataLen], 20h ; ' '
0x18002cc2a  mov     r14, rdx
0x18002cc2d  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x18002cc32  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002cc3a  xor     r9d, r9d; lpSecurityAttributes
0x18002cc3d  mov     edx, 80000000h; dwDesiredAccess
0x18002cc42  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002cc4a  lea     r8d, [r15+1]; dwShareMode
0x18002cc4e  call    cs:__imp_CreateFileW
0x18002cc54  mov     rbx, rax
0x18002cc57  test    rax, rax
0x18002cc5a  jnz     short loc_18002CC74
0x18002cc5c  mov     rcx, [rbp+30h]; this
0x18002cc60  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002cc67  lea     edx, [rax+72h]; void *
0x18002cc6a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cc6f  jmp     loc_18002CE96
0x18002cc74  xor     r9d, r9d; dwMaximumSizeHigh
0x18002cc77  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r15; lpName
0x18002cc7c  xor     edx, edx; lpFileMappingAttributes
0x18002cc7e  mov     [rsp+68h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18002cc83  mov     rcx, rbx; hFile
0x18002cc86  lea     r8d, [r9+2]; flProtect
0x18002cc8a  call    cs:__imp_CreateFileMappingW
0x18002cc90  mov     rdi, rax
0x18002cc93  test    rax, rax
0x18002cc96  jnz     short loc_18002CCC3
0x18002cc98  mov     rcx, [rbp+30h]; this
0x18002cc9c  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002cca3  lea     edx, [rax+7Ah]; void *
0x18002cca6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ccab  mov     edi, eax
0x18002ccad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ccb1  jz      short loc_18002CCBC
0x18002ccb3  mov     rcx, rbx; hObject
0x18002ccb6  call    cs:__imp_CloseHandle
0x18002ccbc  mov     eax, edi
0x18002ccbe  jmp     loc_18002CE96
0x18002ccc3  xor     r9d, r9d; dwFileOffsetLow
0x18002ccc6  mov     [rbp+lpBaseAddress], r15
0x18002ccca  xor     r8d, r8d; dwFileOffsetHigh
0x18002cccd  mov     [rbp+hProv], r15
0x18002ccd1  mov     rcx, rdi; hFileMappingObject
0x18002ccd4  mov     [rbp+hHash], r15
0x18002ccd8  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x18002ccdd  lea     edx, [r9+4]; dwDesiredAccess
0x18002cce1  call    cs:__imp_MapViewOfFile
0x18002cce7  mov     [rbp+lpBaseAddress], rax
0x18002cceb  test    rax, rax
0x18002ccee  jnz     short loc_18002CD65
0x18002ccf0  lea     edx, [rax+7Fh]; void *
0x18002ccf3  mov     rcx, [rbp+30h]; this
0x18002ccf7  lea     r8, aOnecoreEnduser_25; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002ccfe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002cd03  mov     rcx, [rbp+hHash]; hHash
0x18002cd07  mov     esi, eax
0x18002cd09  test    rcx, rcx
0x18002cd0c  jz      short loc_18002CD18
0x18002cd0e  call    cs:__imp_CryptDestroyHash
0x18002cd14  mov     [rbp+hHash], r15
0x18002cd18  mov     rcx, [rbp+hProv]; hProv
0x18002cd1c  test    rcx, rcx
0x18002cd1f  jz      short loc_18002CD2D
0x18002cd21  xor     edx, edx; dwFlags
0x18002cd23  call    cs:__imp_CryptReleaseContext
0x18002cd29  mov     [rbp+hProv], r15
0x18002cd2d  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002cd31  test    rcx, rcx
0x18002cd34  jz      short loc_18002CD40
0x18002cd36  call    cs:__imp_UnmapViewOfFile
0x18002cd3c  mov     [rbp+lpBaseAddress], r15
0x18002cd40  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002cd44  jz      short loc_18002CD4F
0x18002cd46  mov     rcx, rdi; hObject
0x18002cd49  call    cs:__imp_CloseHandle
0x18002cd4f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002cd53  jz      short loc_18002CD5E
0x18002cd55  mov     rcx, rbx; hObject
0x18002cd58  call    cs:__imp_CloseHandle
0x18002cd5e  mov     eax, esi
0x18002cd60  jmp     loc_18002CE96
0x18002cd65  xor     edx, edx; lpFileSizeHigh
0x18002cd67  mov     rcx, rbx; hFile
0x18002cd6a  call    cs:__imp_GetFileSize
0x18002cd70  mov     esi, eax
0x18002cd72  cmp     eax, 0FFFFFFFFh
0x18002cd75  jnz     short loc_18002CD81
0x18002cd77  mov     edx, 82h
0x18002cd7c  jmp     loc_18002CCF3
0x18002cd81  mov     r9d, 18h; dwProvType
0x18002cd87  mov     [rsp+68h+dwCreationDisposition], 0F0000000h; dwFlags
0x18002cd8f  xor     r8d, r8d; szProvider
0x18002cd92  lea     rcx, [rbp+hProv]; phProv
0x18002cd96  xor     edx, edx; szContainer
0x18002cd98  call    cs:__imp_CryptAcquireContextW
0x18002cd9e  test    eax, eax
0x18002cda0  jnz     short loc_18002CDAC
0x18002cda2  mov     edx, 88h
0x18002cda7  jmp     loc_18002CCF3
0x18002cdac  mov     rcx, [rbp+hProv]; hProv
0x18002cdb0  lea     rax, [rbp+hHash]
0x18002cdb4  xor     r9d, r9d; dwFlags
0x18002cdb7  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; phHash
0x18002cdbc  xor     r8d, r8d; hKey
0x18002cdbf  mov     edx, 800Ch; Algid
0x18002cdc4  call    cs:__imp_CryptCreateHash
0x18002cdca  test    eax, eax
0x18002cdcc  jnz     short loc_18002CDD8
0x18002cdce  mov     edx, 8Eh
0x18002cdd3  jmp     loc_18002CCF3
0x18002cdd8  mov     rdx, [rbp+lpBaseAddress]; pbData
0x18002cddc  xor     r9d, r9d; dwFlags
0x18002cddf  mov     rcx, [rbp+hHash]; hHash
0x18002cde3  mov     r8d, esi; dwDataLen
0x18002cde6  call    cs:__imp_CryptHashData
0x18002cdec  test    eax, eax
0x18002cdee  jnz     short loc_18002CDFA
0x18002cdf0  mov     edx, 8Fh
0x18002cdf5  jmp     loc_18002CCF3
0x18002cdfa  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002cdfe  call    cs:__imp_UnmapViewOfFile
0x18002ce04  test    eax, eax
0x18002ce06  jnz     short loc_18002CE12
0x18002ce08  mov     edx, 91h
0x18002ce0d  jmp     loc_18002CCF3
0x18002ce12  mov     rcx, [rbp+hHash]; hHash
0x18002ce16  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18002ce1a  mov     r8, r14; pbData
0x18002ce1d  mov     [rsp+68h+dwCreationDisposition], r15d; dwFlags
0x18002ce22  mov     edx, 2; dwParam
0x18002ce27  call    cs:__imp_CryptGetHashParam
0x18002ce2d  test    eax, eax
0x18002ce2f  jnz     short loc_18002CE3B
0x18002ce31  mov     edx, 93h
0x18002ce36  jmp     loc_18002CCF3
0x18002ce3b  mov     rcx, [rbp+hHash]; hHash
0x18002ce3f  test    rcx, rcx
0x18002ce42  jz      short loc_18002CE4E
0x18002ce44  call    cs:__imp_CryptDestroyHash
0x18002ce4a  mov     [rbp+hHash], r15
0x18002ce4e  mov     rcx, [rbp+hProv]; hProv
0x18002ce52  test    rcx, rcx
0x18002ce55  jz      short loc_18002CE63
0x18002ce57  xor     edx, edx; dwFlags
0x18002ce59  call    cs:__imp_CryptReleaseContext
0x18002ce5f  mov     [rbp+hProv], r15
0x18002ce63  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18002ce67  test    rcx, rcx
0x18002ce6a  jz      short loc_18002CE76
0x18002ce6c  call    cs:__imp_UnmapViewOfFile
0x18002ce72  mov     [rbp+lpBaseAddress], r15
0x18002ce76  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002ce7a  jz      short loc_18002CE85
0x18002ce7c  mov     rcx, rdi; hObject
0x18002ce7f  call    cs:__imp_CloseHandle
0x18002ce85  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ce89  jz      short loc_18002CE94
0x18002ce8b  mov     rcx, rbx; hObject
0x18002ce8e  call    cs:__imp_CloseHandle
0x18002ce94  xor     eax, eax
0x18002ce96  add     rsp, 68h
0x18002ce9a  pop     r15
0x18002ce9c  pop     r14
0x18002ce9e  pop     rdi
0x18002ce9f  pop     rsi
0x18002cea0  pop     rbx
0x18002cea1  pop     rbp
0x18002cea2  retn
```
