# RDPEncryptionTraceLogging_GetServerPolicies

- ea: `0x180044b28`
- end: `0x180044d82`
- name: `RDPEncryptionTraceLogging_GetServerPolicies`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044a98`

## callees

- `0x180044b28`
- `0x18007e9e0`
- `0x18007f42c`
- `0x18019b280`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044cb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044ccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044cb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044ccb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044d31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044d31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044c54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044c54`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180044c6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180044c6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044c37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044c37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c04`

## string_xrefs

- `0x180044c4b`: `RegApi.dll`
- `0x180044c1d`: `SessionDirectoryActive`
- `0x180044cbe`: `RegWinstationQuerySecurityConfig_Machine`

## pseudocode

```c
__int64 __fastcall RDPEncryptionTraceLogging_GetServerPolicies(__int64 a1)
{
  BYTE *v2; // r12
  HMODULE Library; // rax
  HMODULE v4; // rsi
  int v5; // edi
  FARPROC ProcAddress; // r15
  FARPROC v8; // r14
  unsigned int v9; // ecx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v13; // [rsp+158h] [rbp+58h]
  unsigned __int8 v14; // [rsp+15Ah] [rbp+5Ah]
  _BYTE v15[288]; // [rsp+160h] [rbp+60h] BYREF
  _DWORD v16[3]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int8 v17; // [rsp+28Ch] [rbp+18Ch]
  char v18; // [rsp+290h] [rbp+190h]
  unsigned __int8 v19; // [rsp+2A4h] [rbp+1A4h]
  int v20; // [rsp+6B4h] [rbp+5B4h]

  hKey = 0;
  cbData = 0;
  if ( !a1 )
    return 2147942487LL;
  *(_QWORD *)(a1 + 44) = 0;
  v2 = (BYTE *)(a1 + 52);
  *(_DWORD *)(a1 + 36) = -1;
  *(_DWORD *)(a1 + 40) = -1;
  *(_DWORD *)(a1 + 32) = -1;
  *(_DWORD *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 52) = 0;
  memset_0(v16, 0, 0x1678u);
  memset_0(v15, 0, sizeof(v15));
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"SessionDirectoryActive", 0, 0, v2, &cbData);
    RegCloseKey(hKey);
  }
  Library = LoadLibraryExW(L"RegApi.dll", 0, 0);
  v4 = Library;
  v5 = 1;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RegGetMachinePolicyNew");
    v8 = GetProcAddress(v4, "RegWinstationQuerySecurityConfig_Machine");
    if ( ProcAddress )
    {
      ((void (__fastcall *)(_DWORD *))ProcAddress)(v16);
      if ( (v18 & 1) != 0 )
        *(_DWORD *)(a1 + 36) = v17;
      v9 = v16[0];
      if ( (v16[0] & 0x20000) != 0 )
        *(_DWORD *)v2 = v20;
      *(_DWORD *)(a1 + 28) = (v9 >> 8) & 1;
      if ( (v9 & 0x80u) != 0 )
        *(_DWORD *)(a1 + 32) = v19;
    }
    if ( v8 && !((unsigned int (__fastcall *)(const wchar_t *, _BYTE *))v8)(L"rdp-tcp", v15) )
      *(_DWORD *)(a1 + 40) = v15[0];
    FreeLibrary(v4);
  }
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( (v13 & 0x10) == 0 || (v13 & 0x100) != 0 )
      v5 = 0;
    *(_DWORD *)(a1 + 44) = v14;
    *(_DWORD *)(a1 + 48) = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180044b28  mov     [rsp-8+arg_8], rbx
0x180044b2d  mov     [rsp-8+arg_10], rsi
0x180044b32  push    rbp
0x180044b33  push    rdi
0x180044b34  push    r12
0x180044b36  push    r14
0x180044b38  push    r15
0x180044b3a  lea     rbp, [rsp-1810h]
0x180044b42  mov     eax, 1910h
0x180044b47  call    _alloca_probe
0x180044b4c  sub     rsp, rax
0x180044b4f  mov     rax, cs:__security_cookie
0x180044b56  xor     rax, rsp
0x180044b59  mov     [rbp+1830h+var_30], rax
0x180044b60  mov     [rsp+1930h+hKey], 0
0x180044b69  mov     rbx, rcx
0x180044b6c  mov     [rsp+1930h+cbData], 0
0x180044b74  test    rcx, rcx
0x180044b77  jz      loc_180044CA7
0x180044b7d  or      eax, 0FFFFFFFFh
0x180044b80  mov     qword ptr [rcx+2Ch], 0
0x180044b88  lea     r12, [rcx+34h]
0x180044b8c  mov     [rcx+24h], eax
0x180044b8f  mov     [rcx+28h], eax
0x180044b92  xor     edx, edx; Val
0x180044b94  mov     [rcx+20h], eax
0x180044b97  mov     r8d, 1678h; Size
0x180044b9d  mov     dword ptr [rcx+1Ch], 0
0x180044ba4  lea     rcx, [rbp+1830h+var_16B0]; void *
0x180044bab  mov     dword ptr [r12], 0
0x180044bb3  call    memset_0
0x180044bb8  xor     edx, edx; Val
0x180044bba  lea     rcx, [rbp+1830h+var_17D0]; void *
0x180044bbe  mov     r8d, 120h; Size
0x180044bc4  call    memset_0
0x180044bc9  xor     edx, edx; Val
0x180044bcb  lea     rcx, [rsp+1930h+VersionInformation.dwMajorVersion]; void *
0x180044bd0  mov     r8d, 118h; Size
0x180044bd6  call    memset_0
0x180044bdb  lea     rax, [rsp+1930h+hKey]
0x180044be0  mov     [rsp+1930h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180044be8  mov     r9d, 20019h; samDesired
0x180044bee  mov     [rsp+1930h+phkResult], rax; phkResult
0x180044bf3  xor     r8d, r8d; ulOptions
0x180044bf6  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180044bfd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044c04  call    cs:__imp_RegOpenKeyExW
0x180044c0a  test    eax, eax
0x180044c0c  jnz     short loc_180044C48
0x180044c0e  mov     rcx, [rsp+1930h+hKey]; hKey
0x180044c13  lea     rax, [rsp+1930h+cbData]
0x180044c18  mov     [rsp+1930h+lpcbData], rax; lpcbData
0x180044c1d  lea     rdx, ValueName; "SessionDirectoryActive"
0x180044c24  xor     r9d, r9d; lpType
0x180044c27  mov     [rsp+1930h+phkResult], r12; lpData
0x180044c2c  xor     r8d, r8d; lpReserved
0x180044c2f  mov     [rsp+1930h+cbData], 4
0x180044c37  call    cs:__imp_RegQueryValueExW
0x180044c3d  mov     rcx, [rsp+1930h+hKey]; hKey
0x180044c42  call    cs:__imp_RegCloseKey
0x180044c48  xor     r8d, r8d; dwFlags
0x180044c4b  lea     rcx, LibFileName; "RegApi.dll"
0x180044c52  xor     edx, edx; hFile
0x180044c54  call    cs:__imp_LoadLibraryExW
0x180044c5a  mov     rsi, rax
0x180044c5d  mov     edi, 1
0x180044c62  test    rax, rax
0x180044c65  jnz     short loc_180044CAE
0x180044c67  lea     rcx, [rsp+1930h+VersionInformation]; lpVersionInformation
0x180044c6c  call    cs:__imp_GetVersionExW
0x180044c72  test    eax, eax
0x180044c74  jnz     loc_180044D60
0x180044c7a  xor     eax, eax
0x180044c7c  mov     rcx, [rbp+1830h+var_30]
0x180044c83  xor     rcx, rsp; StackCookie
0x180044c86  call    __security_check_cookie
0x180044c8b  lea     r11, [rsp+1930h+var_20]
0x180044c93  mov     rbx, [r11+38h]
0x180044c97  mov     rsi, [r11+40h]
0x180044c9b  mov     rsp, r11
0x180044c9e  pop     r15
0x180044ca0  pop     r14
0x180044ca2  pop     r12
0x180044ca4  pop     rdi
0x180044ca5  pop     rbp
0x180044ca6  retn
0x180044ca7  mov     eax, 80070057h
0x180044cac  jmp     short loc_180044C7C
0x180044cae  lea     rdx, aReggetmachinep; "RegGetMachinePolicyNew"
0x180044cb5  mov     rcx, rsi; hModule
0x180044cb8  call    cs:__imp_GetProcAddress
0x180044cbe  lea     rdx, aRegwinstationq; "RegWinstationQuerySecurityConfig_Machin"...
0x180044cc5  mov     rcx, rsi; hModule
0x180044cc8  mov     r15, rax
0x180044ccb  call    cs:__imp_GetProcAddress
0x180044cd1  mov     r14, rax
0x180044cd4  test    r15, r15
0x180044cd7  jz      short loc_180044D0B
0x180044cd9  lea     rcx, [rbp+1830h+var_16B0]
0x180044ce0  mov     rax, r15
0x180044ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ce8  test    [rbp+1830h+var_16A0], dil
0x180044cef  jnz     short loc_180044D3C
0x180044cf1  mov     ecx, [rbp+1830h+var_16B0]
0x180044cf7  bt      ecx, 11h
0x180044cfb  jb      short loc_180044D48
0x180044cfd  mov     eax, ecx
0x180044cff  shr     eax, 8
0x180044d02  and     eax, edi
0x180044d04  mov     [rbx+1Ch], eax
0x180044d07  test    cl, cl
0x180044d09  js      short loc_180044D54
0x180044d0b  test    r14, r14
0x180044d0e  jz      short loc_180044D2E
0x180044d10  lea     rdx, [rbp+1830h+var_17D0]
0x180044d14  mov     rax, r14
0x180044d17  lea     rcx, aRdpTcp; "rdp-tcp"
0x180044d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d23  test    eax, eax
0x180044d25  jnz     short loc_180044D2E
0x180044d27  movzx   eax, [rbp+1830h+var_17D0]
0x180044d2b  mov     [rbx+28h], eax
0x180044d2e  mov     rcx, rsi; hLibModule
0x180044d31  call    cs:__imp_FreeLibrary
0x180044d37  jmp     loc_180044C67
0x180044d3c  movzx   ecx, [rbp+1830h+var_16A4]
0x180044d43  mov     [rbx+24h], ecx
0x180044d46  jmp     short loc_180044CF1
0x180044d48  mov     eax, [rbp+1830h+var_127C]
0x180044d4e  mov     [r12], eax
0x180044d52  jmp     short loc_180044CFD
0x180044d54  movzx   eax, [rbp+1830h+var_168C]
0x180044d5b  mov     [rbx+20h], eax
0x180044d5e  jmp     short loc_180044D0B
0x180044d60  test    byte ptr [rbp+1830h+var_17D8], 10h
0x180044d64  jz      short loc_180044D71
0x180044d66  mov     eax, 100h
0x180044d6b  test    [rbp+1830h+var_17D8], ax
0x180044d6f  jz      short loc_180044D73
0x180044d71  xor     edi, edi
0x180044d73  movzx   eax, [rbp+1830h+var_17D6]
0x180044d77  mov     [rbx+2Ch], eax
0x180044d7a  mov     [rbx+30h], edi
0x180044d7d  jmp     loc_180044C7A
```
