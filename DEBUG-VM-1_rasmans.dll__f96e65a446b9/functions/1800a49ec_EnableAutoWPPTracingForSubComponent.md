# EnableAutoWPPTracingForSubComponent

- ea: `0x1800a49ec`
- end: `0x1800a4d03`
- name: `EnableAutoWPPTracingForSubComponent`
- size: `791`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180021e70`
- `0x1800c945c`
- `0x1800d4f20`
- `0x1800de2d8`

## callees

- `0x18000e564`
- `0x180053974`
- `0x1800a49ec`
- `0x1800a52cc`
- `0x1800a5b38`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_wfopen_s` at `0x1800a4cb5`
- `msvcrt!_wfopen_s` at `0x1800a4cb5`
- `msvcrt!fclose` at `0x1800a4cc5`
- `msvcrt!fclose` at `0x1800a4cc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4cd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4b5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4b9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4b5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4b9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4aa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4add`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4aa7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4add`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4b1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4bd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4b1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4bd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4b13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4bcc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4b13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4c89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4c89`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a4c94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a4c94`

## string_xrefs

- `0x1800a4a60`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
LSTATUS __fastcall EnableAutoWPPTracingForSubComponent(int a1)
{
  __int64 v1; // rdi
  LSTATUS result; // eax
  HKEY v3; // rcx
  wchar_t *TracingDir; // rbx
  __int64 v5; // rcx
  wchar_t *v6; // rax
  wchar_t *v7; // rdx
  __int64 v8; // r9
  wchar_t *v9; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v11; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[2]; // [rsp+270h] [rbp+170h] BYREF
  char v18[524]; // [rsp+274h] [rbp+174h] BYREF

  v1 = a1;
  hKey = 0;
  *(_DWORD *)SubKey = 0;
  memset_0(v18, 0, 0x206u);
  *(_DWORD *)v13 = 0;
  *(_DWORD *)Data = 0;
  v11 = 4;
  StringCchPrintfW(
    SubKey,
    0x105u,
    L"%s%s",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
    &WPP_COMPONENT_INFO[274 * v1]);
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
  if ( result == 2 )
  {
    TraceEnableDisableWPPComponent(1, (unsigned int)v1);
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
    if ( result )
      return result;
    *(_DWORD *)Data = 1;
    RegSetValueExW(hKey, L"AutoActive", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
    return 0;
  }
  if ( result )
    return result;
  v11 = 4;
  RegQueryValueExW(hKey, L"Active", 0, 0, v13, &v11);
  v3 = hKey;
  if ( *(_DWORD *)v13 )
  {
    v11 = 4;
    if ( RegQueryValueExW(hKey, L"AutoActive", 0, 0, Data, &v11) != 2 )
      goto LABEL_10;
    v3 = hKey;
    *(_DWORD *)Data = 0;
  }
  else
  {
    *(_DWORD *)Data = 1;
  }
  RegSetValueExW(v3, L"AutoActive", 0, 4u, Data, 4u);
LABEL_10:
  RegCloseKey(hKey);
  if ( !*(_DWORD *)v13 )
  {
    hObject[0] = (HANDLE)-1LL;
    TracingDir = (wchar_t *)GetTracingDir(hObject);
    if ( !TracingDir )
      return 3;
    v5 = 2147483646;
    v6 = pszDest;
    v7 = TracingDir;
    v8 = 261;
    do
    {
      if ( !v5 )
        break;
      if ( !*v7 )
        break;
      *v6++ = *v7++;
      --v5;
      --v8;
    }
    while ( v8 );
    v9 = v6 - 1;
    if ( v8 )
      v9 = v6;
    *v9 = 0;
    StringCchCatW(pszDest, 0x105u, L"\\");
    StringCchCatW(pszDest, 0x105u, &WPP_COMPONENT_INFO[274 * v1]);
    StringCchCatW(pszDest, 0x105u, L".BIN");
    LocalFree(TracingDir);
    if ( GetFileAttributesW(pszDest) != -1 )
    {
      Stream = 0;
      _wfopen_s(&Stream, pszDest, L"w");
      if ( Stream )
        fclose(Stream);
    }
    CloseHandle(hObject[0]);
    TraceEnableDisableWPPComponent(1, (unsigned int)v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a49ec  push    rbp
0x1800a49ee  push    rbx
0x1800a49ef  push    rsi
0x1800a49f0  push    rdi
0x1800a49f1  push    r14
0x1800a49f3  push    r15
0x1800a49f5  lea     rbp, [rsp-398h]
0x1800a49fd  sub     rsp, 498h
0x1800a4a04  mov     rax, cs:__security_cookie
0x1800a4a0b  xor     rax, rsp
0x1800a4a0e  mov     [rbp+3C0h+var_40], rax
0x1800a4a15  movsxd  rdi, ecx
0x1800a4a18  xor     r14d, r14d
0x1800a4a1b  lea     rcx, [rbp+3C0h+var_24C]; void *
0x1800a4a22  mov     [rsp+4C0h+hKey], r14
0x1800a4a27  xor     edx, edx; Val
0x1800a4a29  mov     dword ptr [rbp+3C0h+SubKey], r14d
0x1800a4a30  mov     r8d, 206h; Size
0x1800a4a36  call    memset_0
0x1800a4a3b  lea     rax, WPP_COMPONENT_INFO; "RASMAN"
0x1800a4a42  mov     dword ptr [rsp+4C0h+var_480], r14d
0x1800a4a47  imul    rsi, rdi, 224h
0x1800a4a4e  mov     r15d, 105h
0x1800a4a54  mov     dword ptr [rsp+4C0h+Data], r14d
0x1800a4a59  add     rsi, rax
0x1800a4a5c  lea     ebx, [r14+4]
0x1800a4a60  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800a4a67  mov     [rsp+4C0h+phkResult], rsi
0x1800a4a6c  lea     r8, aSS_3; "%s%s"
0x1800a4a73  mov     [rsp+4C0h+var_48C], ebx
0x1800a4a77  mov     edx, r15d; unsigned __int64
0x1800a4a7a  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x1800a4a81  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4a86  lea     rax, [rsp+4C0h+hKey]
0x1800a4a8b  mov     r9d, 2011Fh; samDesired
0x1800a4a91  xor     r8d, r8d; ulOptions
0x1800a4a94  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800a4a99  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800a4aa0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a4aa7  call    cs:__imp_RegOpenKeyExW
0x1800a4aad  cmp     eax, 2
0x1800a4ab0  jnz     short loc_1800A4B29
0x1800a4ab2  mov     edx, edi
0x1800a4ab4  lea     ecx, [rbx-3]
0x1800a4ab7  call    TraceEnableDisableWPPComponent
0x1800a4abc  lea     rax, [rsp+4C0h+hKey]
0x1800a4ac1  mov     r9d, 2011Fh; samDesired
0x1800a4ac7  xor     r8d, r8d; ulOptions
0x1800a4aca  mov     [rsp+4C0h+phkResult], rax; phkResult
0x1800a4acf  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x1800a4ad6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a4add  call    cs:__imp_RegOpenKeyExW
0x1800a4ae3  test    eax, eax
0x1800a4ae5  jnz     loc_1800A4CE4
0x1800a4aeb  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4af0  lea     rax, [rsp+4C0h+Data]
0x1800a4af5  mov     [rsp+4C0h+cbData], ebx; cbData
0x1800a4af9  lea     rdx, aAutoactive; "AutoActive"
0x1800a4b00  mov     r9d, ebx; dwType
0x1800a4b03  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800a4b08  xor     r8d, r8d; Reserved
0x1800a4b0b  mov     dword ptr [rsp+4C0h+Data], 1
0x1800a4b13  call    cs:__imp_RegSetValueExW
0x1800a4b19  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4b1e  call    cs:__imp_RegCloseKey
0x1800a4b24  jmp     loc_1800A4CE2
0x1800a4b29  test    eax, eax
0x1800a4b2b  jnz     loc_1800A4CE4
0x1800a4b31  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4b36  lea     rax, [rsp+4C0h+var_48C]
0x1800a4b3b  mov     qword ptr [rsp+4C0h+cbData], rax; lpcbData
0x1800a4b40  lea     rdx, aActive_0; "Active"
0x1800a4b47  lea     rax, [rsp+4C0h+var_480]
0x1800a4b4c  mov     [rsp+4C0h+var_48C], ebx
0x1800a4b50  xor     r9d, r9d; lpType
0x1800a4b53  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800a4b58  xor     r8d, r8d; lpReserved
0x1800a4b5b  call    cs:__imp_RegQueryValueExW
0x1800a4b61  lea     rdx, aAutoactive; "AutoActive"
0x1800a4b68  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4b6d  cmp     dword ptr [rsp+4C0h+var_480], r14d
0x1800a4b72  jnz     short loc_1800A4B7E
0x1800a4b74  mov     dword ptr [rsp+4C0h+Data], 1
0x1800a4b7c  jmp     short loc_1800A4BB8
0x1800a4b7e  lea     rax, [rsp+4C0h+var_48C]
0x1800a4b83  mov     [rsp+4C0h+var_48C], ebx
0x1800a4b87  mov     qword ptr [rsp+4C0h+cbData], rax; lpcbData
0x1800a4b8c  xor     r9d, r9d; lpType
0x1800a4b8f  lea     rax, [rsp+4C0h+Data]
0x1800a4b94  xor     r8d, r8d; lpReserved
0x1800a4b97  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800a4b9c  call    cs:__imp_RegQueryValueExW
0x1800a4ba2  cmp     eax, 2
0x1800a4ba5  jnz     short loc_1800A4BD2
0x1800a4ba7  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4bac  lea     rdx, aAutoactive; "AutoActive"
0x1800a4bb3  mov     dword ptr [rsp+4C0h+Data], r14d
0x1800a4bb8  lea     rax, [rsp+4C0h+Data]
0x1800a4bbd  mov     [rsp+4C0h+cbData], ebx; cbData
0x1800a4bc1  mov     r9d, ebx; dwType
0x1800a4bc4  mov     [rsp+4C0h+phkResult], rax; lpData
0x1800a4bc9  xor     r8d, r8d; Reserved
0x1800a4bcc  call    cs:__imp_RegSetValueExW
0x1800a4bd2  mov     rcx, [rsp+4C0h+hKey]; hKey
0x1800a4bd7  call    cs:__imp_RegCloseKey
0x1800a4bdd  cmp     dword ptr [rsp+4C0h+var_480], r14d
0x1800a4be2  jnz     loc_1800A4CE2
0x1800a4be8  mov     [rsp+4C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800a4bf1  lea     rcx, [rsp+4C0h+hObject]
0x1800a4bf6  call    GetTracingDir
0x1800a4bfb  mov     rbx, rax
0x1800a4bfe  test    rax, rax
0x1800a4c01  jnz     short loc_1800A4C0B
0x1800a4c03  lea     eax, [rbx+3]
0x1800a4c06  jmp     loc_1800A4CE4
0x1800a4c0b  mov     ecx, 7FFFFFFEh
0x1800a4c10  lea     rax, [rsp+4C0h+pszDest]
0x1800a4c15  mov     rdx, rbx
0x1800a4c18  mov     r9, r15
0x1800a4c1b  test    rcx, rcx
0x1800a4c1e  jz      short loc_1800A4C3F
0x1800a4c20  movzx   r8d, word ptr [rdx]
0x1800a4c24  test    r8w, r8w
0x1800a4c28  jz      short loc_1800A4C3F
0x1800a4c2a  mov     [rax], r8w
0x1800a4c2e  add     rdx, 2
0x1800a4c32  add     rax, 2
0x1800a4c36  dec     rcx
0x1800a4c39  sub     r9, 1
0x1800a4c3d  jnz     short loc_1800A4C1B
0x1800a4c3f  test    r9, r9
0x1800a4c42  lea     rcx, [rax-2]
0x1800a4c46  lea     r8, Source; "\\"
0x1800a4c4d  mov     rdx, r15; cchDest
0x1800a4c50  cmovnz  rcx, rax
0x1800a4c54  mov     [rcx], r14w
0x1800a4c58  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800a4c5d  call    StringCchCatW
0x1800a4c62  mov     r8, rsi; pszSrc
0x1800a4c65  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800a4c6a  mov     rdx, r15; cchDest
0x1800a4c6d  call    StringCchCatW
0x1800a4c72  lea     r8, aBin; ".BIN"
0x1800a4c79  mov     rdx, r15; cchDest
0x1800a4c7c  lea     rcx, [rsp+4C0h+pszDest]; pszDest
0x1800a4c81  call    StringCchCatW
0x1800a4c86  mov     rcx, rbx; hMem
0x1800a4c89  call    cs:__imp_LocalFree
0x1800a4c8f  lea     rcx, [rsp+4C0h+pszDest]; lpFileName
0x1800a4c94  call    cs:__imp_GetFileAttributesW
0x1800a4c9a  cmp     eax, 0FFFFFFFFh
0x1800a4c9d  jz      short loc_1800A4CCB
0x1800a4c9f  lea     r8, aW; "w"
0x1800a4ca6  mov     [rsp+4C0h+Stream], r14
0x1800a4cab  lea     rdx, [rsp+4C0h+pszDest]; FileName
0x1800a4cb0  lea     rcx, [rsp+4C0h+Stream]; Stream
0x1800a4cb5  call    cs:__imp__wfopen_s
0x1800a4cbb  mov     rcx, [rsp+4C0h+Stream]; Stream
0x1800a4cc0  test    rcx, rcx
0x1800a4cc3  jz      short loc_1800A4CCB
0x1800a4cc5  call    cs:__imp_fclose
0x1800a4ccb  mov     rcx, [rsp+4C0h+hObject]; hObject
0x1800a4cd0  call    cs:__imp_CloseHandle
0x1800a4cd6  mov     edx, edi
0x1800a4cd8  mov     ecx, 1
0x1800a4cdd  call    TraceEnableDisableWPPComponent
0x1800a4ce2  xor     eax, eax
0x1800a4ce4  mov     rcx, [rbp+3C0h+var_40]
0x1800a4ceb  xor     rcx, rsp; StackCookie
0x1800a4cee  call    __security_check_cookie
0x1800a4cf3  add     rsp, 498h
0x1800a4cfa  pop     r15
0x1800a4cfc  pop     r14
0x1800a4cfe  pop     rdi
0x1800a4cff  pop     rsi
0x1800a4d00  pop     rbx
0x1800a4d01  pop     rbp
0x1800a4d02  retn
```
