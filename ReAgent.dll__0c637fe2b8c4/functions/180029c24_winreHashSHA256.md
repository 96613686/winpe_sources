# winreHashSHA256

- ea: `0x180029c24`
- end: `0x180029ede`
- name: `winreHashSHA256`
- size: `698`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, BYTE *pbData)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180023a20`
- `0x180029ee4`

## callees

- `0x180001f94`
- `0x180001fa0`
- `0x1800059fc`
- `0x180029c24`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029c9f`
- `KERNEL32!GetLastError` at `0x180029cc1`
- `KERNEL32!GetLastError` at `0x180029d54`
- `KERNEL32!GetLastError` at `0x180029db1`
- `KERNEL32!GetLastError` at `0x180029dea`
- `KERNEL32!GetLastError` at `0x180029e1c`
- `KERNEL32!GetLastError` at `0x180029e5f`
- `KERNEL32!GetLastError` at `0x180029c9f`
- `KERNEL32!GetLastError` at `0x180029cc1`
- `KERNEL32!GetLastError` at `0x180029d54`
- `KERNEL32!GetLastError` at `0x180029db1`
- `KERNEL32!GetLastError` at `0x180029dea`
- `KERNEL32!GetLastError` at `0x180029e1c`
- `KERNEL32!GetLastError` at `0x180029e5f`
- `KERNEL32!GetFileSizeEx` at `0x180029cb7`
- `KERNEL32!GetFileSizeEx` at `0x180029cb7`
- `KERNEL32!ReadFile` at `0x180029d4a`
- `KERNEL32!ReadFile` at `0x180029d4a`
- `KERNEL32!CreateFileW` at `0x180029c90`
- `KERNEL32!CreateFileW` at `0x180029c90`
- `KERNEL32!CloseHandle` at `0x180029e94`
- `KERNEL32!CloseHandle` at `0x180029e94`
- `ADVAPI32!CryptReleaseContext` at `0x180029eba`
- `ADVAPI32!CryptReleaseContext` at `0x180029eba`
- `ADVAPI32!CryptAcquireContextW` at `0x180029da7`
- `ADVAPI32!CryptAcquireContextW` at `0x180029da7`
- `ADVAPI32!CryptCreateHash` at `0x180029de0`
- `ADVAPI32!CryptCreateHash` at `0x180029de0`
- `ADVAPI32!CryptHashData` at `0x180029e12`
- `ADVAPI32!CryptHashData` at `0x180029e12`
- `ADVAPI32!CryptGetHashParam` at `0x180029e55`
- `ADVAPI32!CryptGetHashParam` at `0x180029e55`
- `ADVAPI32!CryptDestroyHash` at `0x180029ea9`
- `ADVAPI32!CryptDestroyHash` at `0x180029ea9`

## string_xrefs

- `0x180029d5a`: `failed to read file`
- `0x180029cdf`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029d72`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180029df0`: `failed to create hash`

## pseudocode

```c
__int64 __fastcall winreHashSHA256(LPCWSTR lpFileName, BYTE *pbData)
{
  HCRYPTHASH v3; // rcx
  HANDLE FileW; // rax
  void *v6; // rsi
  __int64 LastError; // rbx
  BYTE *v8; // rax
  BYTE *v9; // rdi
  DWORD v10; // eax
  const wchar_t *v11; // r8
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-48h]
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+48h] [rbp-28h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-18h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp-10h] BYREF

  phProv = 0;
  v3 = 0;
  phHash = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  pdwDataLen = 0;
  if ( lpFileName && pbData )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0, 0);
    v6 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LODWORD(LastError) = GetLastError();
LABEL_5:
      v3 = phHash;
      goto LABEL_27;
    }
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      LODWORD(dwFlagsAndAttributes) = 3145;
      LastError = GetLastError();
      UnattendLogW(
        2,
        L"winreHashSHA256 %s (0x%x) in file %S line %d",
        L"failed to get file size",
        LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        dwFlagsAndAttributes);
LABEL_25:
      CloseHandle(v6);
      goto LABEL_5;
    }
    if ( FileSize.HighPart )
    {
      LODWORD(LastError) = 13;
      goto LABEL_25;
    }
    v8 = (BYTE *)operator new[](FileSize.LowPart);
    v9 = v8;
    if ( !v8 )
    {
      LODWORD(LastError) = 14;
      goto LABEL_25;
    }
    memset_0(v8, 0, FileSize.LowPart);
    if ( ReadFile(v6, v9, FileSize.LowPart, &NumberOfBytesRead, 0) )
    {
      if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
      {
        if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
        {
          if ( CryptHashData(phHash, v9, FileSize.LowPart, 0) )
          {
            pdwDataLen = 32;
            if ( CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
            {
              LODWORD(LastError) = pdwDataLen != 32 ? 0x3BC4 : 0;
              goto LABEL_24;
            }
            v10 = GetLastError();
            v11 = L"failed to get hash parameter";
            LODWORD(dwFlagsAndAttributes) = 3197;
          }
          else
          {
            v10 = GetLastError();
            v11 = L"failed to hash data";
            LODWORD(dwFlagsAndAttributes) = 3187;
          }
        }
        else
        {
          v10 = GetLastError();
          v11 = L"failed to create hash";
          LODWORD(dwFlagsAndAttributes) = 3182;
        }
      }
      else
      {
        v10 = GetLastError();
        v11 = L"failed to acquire context";
        LODWORD(dwFlagsAndAttributes) = 3176;
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = L"failed to read file";
      LODWORD(dwFlagsAndAttributes) = 3167;
    }
    LODWORD(LastError) = v10;
    UnattendLogW(
      2,
      L"winreHashSHA256 %s (0x%x) in file %S line %d",
      v11,
      v10,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      dwFlagsAndAttributes);
LABEL_24:
    operator delete(v9);
    goto LABEL_25;
  }
  LODWORD(LastError) = 87;
LABEL_27:
  if ( v3 )
    CryptDestroyHash(v3);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180029c24  mov     [rsp-18h+arg_10], rbx
0x180029c29  push    rbp
0x180029c2a  push    rsi
0x180029c2b  push    rdi
0x180029c2c  mov     rbp, rsp
0x180029c2f  sub     rsp, 70h
0x180029c33  mov     rax, cs:__security_cookie
0x180029c3a  xor     rax, rsp
0x180029c3d  mov     [rbp+var_8], rax
0x180029c41  mov     rax, rcx
0x180029c44  mov     [rbp+phProv], 0
0x180029c4c  xor     ecx, ecx; hHash
0x180029c4e  mov     rbx, rdx
0x180029c51  mov     [rbp+phHash], rcx
0x180029c55  mov     qword ptr [rbp+FileSize], rcx
0x180029c59  mov     [rbp+NumberOfBytesRead], ecx
0x180029c5c  mov     [rbp+pdwDataLen], ecx
0x180029c5f  test    rax, rax
0x180029c62  jz      loc_180029E9F
0x180029c68  test    rdx, rdx
0x180029c6b  jz      loc_180029E9F
0x180029c71  mov     [rsp+70h+hTemplateFile], rcx; hTemplateFile
0x180029c76  xor     r9d, r9d; lpSecurityAttributes
0x180029c79  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x180029c7d  xor     r8d, r8d; dwShareMode
0x180029c80  mov     rcx, rax; lpFileName
0x180029c83  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180029c8b  mov     edx, 80000000h; dwDesiredAccess
0x180029c90  call    cs:__imp_CreateFileW
0x180029c96  mov     rsi, rax
0x180029c99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029c9d  jnz     short loc_180029CB0
0x180029c9f  call    cs:__imp_GetLastError
0x180029ca5  mov     ebx, eax
0x180029ca7  mov     rcx, [rbp+phHash]
0x180029cab  jmp     loc_180029EA4
0x180029cb0  lea     rdx, [rbp+FileSize]; lpFileSize
0x180029cb4  mov     rcx, rsi; hFile
0x180029cb7  call    cs:__imp_GetFileSizeEx
0x180029cbd  test    eax, eax
0x180029cbf  jnz     short loc_180029CFD
0x180029cc1  call    cs:__imp_GetLastError
0x180029cc7  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C49h
0x180029ccf  lea     r8, aFailedToGetFil; "failed to get file size"
0x180029cd6  mov     ebx, eax
0x180029cd8  lea     rdx, aWinrehashsha25; "winreHashSHA256 %s (0x%x) in file %S li"...
0x180029cdf  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029ce6  mov     r9d, ebx
0x180029ce9  mov     ecx, 2
0x180029cee  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180029cf3  call    UnattendLogW
0x180029cf8  jmp     loc_180029E91
0x180029cfd  cmp     dword ptr [rbp+FileSize+4], 0
0x180029d01  jz      short loc_180029D0D
0x180029d03  mov     ebx, 0Dh
0x180029d08  jmp     loc_180029E91
0x180029d0d  mov     ecx, dword ptr [rbp+FileSize]; unsigned __int64
0x180029d10  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029d15  mov     rdi, rax
0x180029d18  test    rax, rax
0x180029d1b  jnz     short loc_180029D25
0x180029d1d  lea     ebx, [rax+0Eh]
0x180029d20  jmp     loc_180029E91
0x180029d25  mov     r8d, dword ptr [rbp+FileSize]; Size
0x180029d29  xor     edx, edx; Val
0x180029d2b  mov     rcx, rdi; void *
0x180029d2e  call    memset_0
0x180029d33  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x180029d37  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180029d3b  mov     rdx, rdi; lpBuffer
0x180029d3e  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180029d47  mov     rcx, rsi; hFile
0x180029d4a  call    cs:__imp_ReadFile
0x180029d50  test    eax, eax
0x180029d52  jnz     short loc_180029D90
0x180029d54  call    cs:__imp_GetLastError
0x180029d5a  lea     r8, aFailedToReadFi; "failed to read file"
0x180029d61  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C5Fh
0x180029d69  mov     ebx, eax
0x180029d6b  lea     rdx, aWinrehashsha25; "winreHashSHA256 %s (0x%x) in file %S li"...
0x180029d72  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180029d79  mov     r9d, ebx
0x180029d7c  mov     ecx, 2
0x180029d81  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180029d86  call    UnattendLogW
0x180029d8b  jmp     loc_180029E89
0x180029d90  mov     r9d, 18h; dwProvType
0x180029d96  mov     [rsp+70h+dwCreationDisposition], 0F0000000h; dwFlags
0x180029d9e  xor     r8d, r8d; szProvider
0x180029da1  lea     rcx, [rbp+phProv]; phProv
0x180029da5  xor     edx, edx; szContainer
0x180029da7  call    cs:__imp_CryptAcquireContextW
0x180029dad  test    eax, eax
0x180029daf  jnz     short loc_180029DC8
0x180029db1  call    cs:__imp_GetLastError
0x180029db7  lea     r8, aFailedToAcquir; "failed to acquire context"
0x180029dbe  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C68h
0x180029dc6  jmp     short loc_180029D69
0x180029dc8  mov     rcx, [rbp+phProv]; hProv
0x180029dcc  lea     rax, [rbp+phHash]
0x180029dd0  xor     r9d, r9d; dwFlags
0x180029dd3  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; phHash
0x180029dd8  xor     r8d, r8d; hKey
0x180029ddb  mov     edx, 800Ch; Algid
0x180029de0  call    cs:__imp_CryptCreateHash
0x180029de6  test    eax, eax
0x180029de8  jnz     short loc_180029E04
0x180029dea  call    cs:__imp_GetLastError
0x180029df0  lea     r8, aFailedToCreate_3; "failed to create hash"
0x180029df7  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C6Eh
0x180029dff  jmp     loc_180029D69
0x180029e04  mov     r8d, dword ptr [rbp+FileSize]; dwDataLen
0x180029e08  xor     r9d, r9d; dwFlags
0x180029e0b  mov     rcx, [rbp+phHash]; hHash
0x180029e0f  mov     rdx, rdi; pbData
0x180029e12  call    cs:__imp_CryptHashData
0x180029e18  test    eax, eax
0x180029e1a  jnz     short loc_180029E36
0x180029e1c  call    cs:__imp_GetLastError
0x180029e22  lea     r8, aFailedToHashDa; "failed to hash data"
0x180029e29  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C73h
0x180029e31  jmp     loc_180029D69
0x180029e36  mov     rcx, [rbp+phHash]; hHash
0x180029e3a  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180029e3e  mov     r8, rbx; pbData
0x180029e41  mov     [rbp+pdwDataLen], 20h ; ' '
0x180029e48  mov     edx, 2; dwParam
0x180029e4d  mov     [rsp+70h+dwCreationDisposition], 0; dwFlags
0x180029e55  call    cs:__imp_CryptGetHashParam
0x180029e5b  test    eax, eax
0x180029e5d  jnz     short loc_180029E79
0x180029e5f  call    cs:__imp_GetLastError
0x180029e65  lea     r8, aFailedToGetHas; "failed to get hash parameter"
0x180029e6c  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 0C7Dh
0x180029e74  jmp     loc_180029D69
0x180029e79  mov     eax, [rbp+pdwDataLen]
0x180029e7c  sub     eax, 20h ; ' '
0x180029e7f  neg     eax
0x180029e81  sbb     ebx, ebx
0x180029e83  and     ebx, 3BC4h
0x180029e89  mov     rcx, rdi; Block
0x180029e8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029e91  mov     rcx, rsi; hObject
0x180029e94  call    cs:__imp_CloseHandle
0x180029e9a  jmp     loc_180029CA7
0x180029e9f  mov     ebx, 57h ; 'W'
0x180029ea4  test    rcx, rcx
0x180029ea7  jz      short loc_180029EAF
0x180029ea9  call    cs:__imp_CryptDestroyHash
0x180029eaf  mov     rcx, [rbp+phProv]; hProv
0x180029eb3  test    rcx, rcx
0x180029eb6  jz      short loc_180029EC0
0x180029eb8  xor     edx, edx; dwFlags
0x180029eba  call    cs:__imp_CryptReleaseContext
0x180029ec0  mov     eax, ebx
0x180029ec2  mov     rcx, [rbp+var_8]
0x180029ec6  xor     rcx, rsp; StackCookie
0x180029ec9  call    __security_check_cookie
0x180029ece  mov     rbx, [rsp+70h+arg_10]
0x180029ed6  add     rsp, 70h
0x180029eda  pop     rdi
0x180029edb  pop     rsi
0x180029edc  pop     rbp
0x180029edd  retn
```
