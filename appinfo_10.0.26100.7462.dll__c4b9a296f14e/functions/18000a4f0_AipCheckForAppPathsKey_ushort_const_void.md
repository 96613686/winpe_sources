# AipCheckForAppPathsKey(ushort const *,void * *)

- ea: `0x18000a4f0`
- end: `0x18000abdc`
- name: `?AipCheckForAppPathsKey@@YAKPEBGPEAPEAX@Z`
- size: `1772`
- prototype: `unsigned int __fastcall(wchar_t *Str, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x18000a4f0`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000a571`
- `msvcrt!wcsrchr` at `0x18000a571`
- `msvcrt!wcschr` at `0x18000a5c8`
- `msvcrt!wcschr` at `0x18000a82a`
- `msvcrt!wcschr` at `0x18000a8c9`
- `msvcrt!wcschr` at `0x18000a5c8`
- `msvcrt!wcschr` at `0x18000a82a`
- `msvcrt!wcschr` at `0x18000a8c9`
- `msvcrt!wcscat_s` at `0x18000a5b6`
- `msvcrt!wcscat_s` at `0x18000a816`
- `msvcrt!wcscat_s` at `0x18000a8b5`
- `msvcrt!wcscat_s` at `0x18000a9cb`
- `msvcrt!wcscat_s` at `0x18000aa14`
- `msvcrt!wcscat_s` at `0x18000aa5d`
- `msvcrt!wcscat_s` at `0x18000ab28`
- `msvcrt!wcscat_s` at `0x18000ab8c`
- `msvcrt!wcscat_s` at `0x18000aba1`
- `msvcrt!wcscat_s` at `0x18000a5b6`
- `msvcrt!wcscat_s` at `0x18000a816`
- `msvcrt!wcscat_s` at `0x18000a8b5`
- `msvcrt!wcscat_s` at `0x18000a9cb`
- `msvcrt!wcscat_s` at `0x18000aa14`
- `msvcrt!wcscat_s` at `0x18000aa5d`
- `msvcrt!wcscat_s` at `0x18000ab28`
- `msvcrt!wcscat_s` at `0x18000ab8c`
- `msvcrt!wcscat_s` at `0x18000aba1`
- `msvcrt!wcscpy_s` at `0x18000a59e`
- `msvcrt!wcscpy_s` at `0x18000a7fb`
- `msvcrt!wcscpy_s` at `0x18000a89a`
- `msvcrt!wcscpy_s` at `0x18000ab0f`
- `msvcrt!wcscpy_s` at `0x18000a59e`
- `msvcrt!wcscpy_s` at `0x18000a7fb`
- `msvcrt!wcscpy_s` at `0x18000a89a`
- `msvcrt!wcscpy_s` at `0x18000ab0f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a778`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ab64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a778`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ab64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a5fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a860`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a8ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a5fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a860`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a8ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a923`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a923`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a791`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a72e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aaa2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a72e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aaa2`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a65b`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000aae1`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a65b`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000aae1`
- `ntdll!RtlSetEnvironmentVar` at `0x18000a992`
- `ntdll!RtlSetEnvironmentVar` at `0x18000a992`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a9a8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a9a8`

## string_xrefs

- `0x18000a589`: `Software\Microsoft\Windows\CurrentVersion\App Paths`
- `0x18000a679`: `AppendPath`
- `0x18000a7e3`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\App Paths`
- `0x18000a882`: `Software\WowAA32Node\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
__int64 __fastcall AipCheckForAppPathsKey(wchar_t *Str, void **a2)
{
  ULONG ValueW; // edi
  HKEY v5; // r15
  const wchar_t *v6; // r12
  wchar_t *v7; // rbx
  wchar_t *v8; // r14
  LSTATUS v9; // esi
  NTSTATUS v10; // eax
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // rax
  rsize_t v14; // rsi
  wchar_t *v15; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v25; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t SubKey[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v29[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t Source[264]; // [rsp+6B0h] [rbp+5B0h] BYREF

  ValueW = 0;
  v5 = 0;
  memset_0(Source, 0, 0x208u);
  pcbData = 0;
  v6 = Source;
  pdwType = 0;
  v7 = 0;
  pvData = 0;
  v23 = 0;
  if ( !Str )
    goto LABEL_20;
  v8 = wcsrchr(Str, 0x5Cu);
  if ( !v8 )
    goto LABEL_20;
  phkResult = 0;
  wcscpy_s(Destination, 0x104u, L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths");
  wcscat_s(Destination, 0x104u, v8);
  if ( !wcschr(v8, 0x2Eu) )
    wcscat_s(Destination, 0x104u, L".exe");
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &phkResult);
  if ( !v9 )
  {
    v5 = phkResult;
    phkResult = 0;
    goto LABEL_10;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v9 != 2 )
    goto LABEL_9;
  v25 = 0;
  wcscpy_s(SubKey, 0x104u, L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\App Paths");
  wcscat_s(SubKey, 0x104u, v8);
  if ( !wcschr(v8, 0x2Eu) )
    wcscat_s(SubKey, 0x104u, L".exe");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v25) )
  {
    v5 = v25;
    v25 = 0;
    goto LABEL_10;
  }
  if ( v25 )
  {
    RegCloseKey(v25);
    v25 = 0;
  }
  hKey = 0;
  wcscpy_s(v29, 0x104u, L"Software\\WowAA32Node\\Microsoft\\Windows\\CurrentVersion\\App Paths");
  wcscat_s(v29, 0x104u, v8);
  if ( !wcschr(v8, 0x2Eu) )
    wcscat_s(v29, 0x104u, L".exe");
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v29, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    if ( !hKey )
      goto LABEL_9;
    RegCloseKey(hKey);
  }
  else
  {
    v5 = hKey;
  }
  hKey = 0;
LABEL_9:
  if ( v9 )
  {
    if ( v9 != 2 )
      ValueW = v9;
    v17 = 0;
    goto LABEL_38;
  }
LABEL_10:
  v10 = RtlQueryEnvironmentVariable(*a2, L"PATH", 4, Source, 260, &v23);
  if ( v10 >= 0 )
  {
LABEL_11:
    v11 = v23;
    goto LABEL_12;
  }
  if ( v10 != -1073741568 )
  {
    if ( v10 != -1073741789 )
      goto LABEL_43;
    v19 = v23;
    v6 = (const wchar_t *)LocalAlloc(0, 2 * v23);
    if ( !v6 )
    {
      ValueW = 8;
      goto LABEL_20;
    }
    v10 = RtlQueryEnvironmentVariable(*a2, L"PATH", 4, v6, v19, &v23);
    if ( v10 < 0 )
      goto LABEL_43;
    goto LABEL_11;
  }
  v11 = 0;
  v23 = 0;
LABEL_12:
  v6[v11] = 0;
  v12 = (unsigned int)v23;
  pcbData = 4;
  if ( RegGetValueW(v5, 0, L"AppendPath", 0x10u, 0, &pvData, &pcbData) )
    pvData = 0;
  pcbData = 0;
  ValueW = RegGetValueW(v5, 0, L"Path", 0xFFFFu, &pdwType, 0, &pcbData);
  if ( ValueW )
  {
    if ( ValueW == 2 )
      ValueW = 0;
    goto LABEL_20;
  }
  if ( pdwType - 1 <= 1 && pcbData > 2 )
  {
    v13 = (unsigned int)v12 + (pcbData >> 1) + 1;
    v14 = (unsigned int)v13;
    v15 = (wchar_t *)LocalAlloc(0x40u, 2 * v13);
    v7 = v15;
    if ( !v15 )
    {
      ValueW = 8;
      goto LABEL_20;
    }
    if ( pvData )
    {
      wcscpy_s(v15, v14, v6);
      wcscat_s(v7, v14, L";");
      ValueW = RegGetValueW(v5, 0, L"Path", 0xFFFFu, 0, &v7[v12 + 1], &pcbData);
      if ( ValueW )
        goto LABEL_20;
    }
    else
    {
      ValueW = RegGetValueW(v5, 0, L"Path", 0xFFFFu, 0, v15, &pcbData);
      if ( ValueW )
        goto LABEL_20;
      wcscat_s(v7, v14, L";");
      wcscat_s(v7, v14, v6);
    }
    if ( pdwType - 1 > 1 )
      goto LABEL_20;
    v18 = -1;
    do
      ++v18;
    while ( v7[v18] );
    v10 = RtlSetEnvironmentVar(a2, L"PATH", 4, v7, v18);
    if ( v10 >= 0 )
      goto LABEL_20;
LABEL_43:
    ValueW = RtlNtStatusToDosErrorNoTeb(v10);
  }
LABEL_20:
  LocalFree(v7);
  if ( v6 == Source )
    goto LABEL_21;
  v17 = (wchar_t *)v6;
LABEL_38:
  LocalFree(v17);
LABEL_21:
  if ( v5 )
    RegCloseKey(v5);
  return ValueW;
}

```

## disassembly

```asm
0x18000a4f0  mov     [rsp-8+arg_10], rbx
0x18000a4f5  push    rbp
0x18000a4f6  push    rsi
0x18000a4f7  push    rdi
0x18000a4f8  push    r12
0x18000a4fa  push    r13
0x18000a4fc  push    r14
0x18000a4fe  push    r15
0x18000a500  lea     rbp, [rsp-7D0h]
0x18000a508  sub     rsp, 8D0h
0x18000a50f  mov     rax, cs:__security_cookie
0x18000a516  xor     rax, rsp
0x18000a519  mov     [rbp+800h+var_40], rax
0x18000a520  mov     r13, rdx
0x18000a523  mov     rsi, rcx
0x18000a526  xor     r14d, r14d
0x18000a529  lea     rcx, [rbp+800h+Source]; void *
0x18000a530  xor     edx, edx; Val
0x18000a532  mov     r8d, 208h; Size
0x18000a538  mov     edi, r14d
0x18000a53b  mov     r15d, r14d
0x18000a53e  call    memset_0
0x18000a543  mov     [rsp+900h+var_8C0], r14d
0x18000a548  lea     r12, [rbp+800h+Source]
0x18000a54f  mov     [rsp+900h+pdwType], r14d
0x18000a554  mov     ebx, r14d
0x18000a557  mov     [rsp+900h+var_8BC], r14d
0x18000a55c  mov     [rsp+900h+var_8B0], r14
0x18000a561  test    rsi, rsi
0x18000a564  jz      loc_18000A78E
0x18000a56a  lea     edx, [r14+5Ch]; Ch
0x18000a56e  mov     rcx, rsi; Str
0x18000a571  call    cs:__imp_wcsrchr
0x18000a578  nop     dword ptr [rax+rax+00h]
0x18000a57d  mov     r14, rax
0x18000a580  test    rax, rax
0x18000a583  jz      loc_18000A78E
0x18000a589  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a590  mov     [rsp+900h+var_8A8], rdi
0x18000a595  mov     edx, 104h; SizeInWords
0x18000a59a  lea     rcx, [rbp+800h+Destination]; Destination
0x18000a59e  call    cs:__imp_wcscpy_s
0x18000a5a5  nop     dword ptr [rax+rax+00h]
0x18000a5aa  mov     r8, r14; Source
0x18000a5ad  lea     rcx, [rbp+800h+Destination]; Destination
0x18000a5b1  mov     edx, 104h; SizeInWords
0x18000a5b6  call    cs:__imp_wcscat_s
0x18000a5bd  nop     dword ptr [rax+rax+00h]
0x18000a5c2  lea     edx, [rbx+2Eh]; Ch
0x18000a5c5  mov     rcx, r14; Str
0x18000a5c8  call    cs:__imp_wcschr
0x18000a5cf  nop     dword ptr [rax+rax+00h]
0x18000a5d4  test    rax, rax
0x18000a5d7  jz      loc_18000A9BB
0x18000a5dd  lea     rax, [rsp+900h+var_8A8]
0x18000a5e2  mov     r9d, 20019h; samDesired
0x18000a5e8  xor     r8d, r8d; ulOptions
0x18000a5eb  mov     [rsp+900h+phkResult], rax; phkResult
0x18000a5f0  lea     rdx, [rbp+800h+Destination]; lpSubKey
0x18000a5f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a5fb  call    cs:__imp_RegOpenKeyExW
0x18000a602  nop     dword ptr [rax+rax+00h]
0x18000a607  mov     esi, eax
0x18000a609  test    eax, eax
0x18000a60b  jz      loc_18000A9DC
0x18000a611  mov     rcx, [rsp+900h+var_8A8]; hKey
0x18000a616  test    rcx, rcx
0x18000a619  jnz     loc_18000A9EB
0x18000a61f  cmp     esi, 2
0x18000a622  jz      loc_18000A7E3
0x18000a628  test    esi, esi
0x18000a62a  jnz     loc_18000A939
0x18000a630  mov     rcx, [r13+0]
0x18000a634  lea     rax, [rsp+900h+var_8B0]
0x18000a639  mov     [rsp+900h+pvData], rax
0x18000a63e  lea     r9, [rbp+800h+Source]
0x18000a645  mov     r8d, 4
0x18000a64b  mov     [rsp+900h+phkResult], 104h
0x18000a654  lea     rdx, aPath; "PATH"
0x18000a65b  call    cs:__imp_RtlQueryEnvironmentVariable
0x18000a662  nop     dword ptr [rax+rax+00h]
0x18000a667  test    eax, eax
0x18000a669  js      loc_18000AA78
0x18000a66f  mov     rax, [rsp+900h+var_8B0]
0x18000a674  mov     [r12+rax*2], di
0x18000a679  lea     r8, Value; "AppendPath"
0x18000a680  mov     r14d, dword ptr [rsp+900h+var_8B0]
0x18000a685  lea     rax, [rsp+900h+var_8C0]
0x18000a68a  mov     [rsp+900h+pcbData], rax; pcbData
0x18000a68f  mov     r9d, 10h; dwFlags
0x18000a695  lea     rax, [rsp+900h+var_8BC]
0x18000a69a  mov     [rsp+900h+var_8C0], 4
0x18000a6a2  mov     [rsp+900h+pvData], rax; pvData
0x18000a6a7  xor     edx, edx; lpSubKey
0x18000a6a9  mov     rcx, r15; hkey
0x18000a6ac  mov     [rsp+900h+phkResult], rdi; pdwType
0x18000a6b1  call    cs:__imp_RegGetValueW
0x18000a6b8  nop     dword ptr [rax+rax+00h]
0x18000a6bd  test    eax, eax
0x18000a6bf  jz      short loc_18000A6C5
0x18000a6c1  mov     [rsp+900h+var_8BC], edi
0x18000a6c5  lea     rax, [rsp+900h+var_8C0]
0x18000a6ca  mov     [rsp+900h+var_8C0], edi
0x18000a6ce  mov     [rsp+900h+pcbData], rax; pcbData
0x18000a6d3  lea     r8, aPath_0; "Path"
0x18000a6da  lea     rax, [rsp+900h+pdwType]
0x18000a6df  mov     [rsp+900h+pvData], rdi; pvData
0x18000a6e4  mov     r9d, 0FFFFh; dwFlags
0x18000a6ea  mov     [rsp+900h+phkResult], rax; pdwType
0x18000a6ef  xor     edx, edx; lpSubKey
0x18000a6f1  mov     rcx, r15; hkey
0x18000a6f4  call    cs:__imp_RegGetValueW
0x18000a6fb  nop     dword ptr [rax+rax+00h]
0x18000a700  mov     edi, eax
0x18000a702  test    eax, eax
0x18000a704  jnz     loc_18000ABB2
0x18000a70a  mov     eax, [rsp+900h+pdwType]
0x18000a70e  dec     eax
0x18000a710  cmp     eax, 1
0x18000a713  ja      short loc_18000A78E
0x18000a715  mov     eax, [rsp+900h+var_8C0]
0x18000a719  cmp     eax, 2
0x18000a71c  jbe     short loc_18000A78E
0x18000a71e  shr     eax, 1
0x18000a720  lea     ecx, [rdi+40h]; uFlags
0x18000a723  inc     eax
0x18000a725  add     eax, r14d
0x18000a728  mov     esi, eax
0x18000a72a  lea     rdx, [rax+rax]; uBytes
0x18000a72e  call    cs:__imp_LocalAlloc
0x18000a735  nop     dword ptr [rax+rax+00h]
0x18000a73a  mov     rbx, rax
0x18000a73d  test    rax, rax
0x18000a740  jz      loc_18000AAFC
0x18000a746  cmp     [rsp+900h+var_8BC], edi
0x18000a74a  jnz     loc_18000AB06
0x18000a750  lea     rax, [rsp+900h+var_8C0]
0x18000a755  mov     r9d, 0FFFFh; dwFlags
0x18000a75b  mov     [rsp+900h+pcbData], rax; pcbData
0x18000a760  lea     r8, aPath_0; "Path"
0x18000a767  xor     eax, eax
0x18000a769  mov     [rsp+900h+pvData], rbx; pvData
0x18000a76e  xor     edx, edx; lpSubKey
0x18000a770  mov     [rsp+900h+phkResult], rax; pdwType
0x18000a775  mov     rcx, r15; hkey
0x18000a778  call    cs:__imp_RegGetValueW
0x18000a77f  nop     dword ptr [rax+rax+00h]
0x18000a784  mov     edi, eax
0x18000a786  test    eax, eax
0x18000a788  jz      loc_18000AB7F
0x18000a78e  mov     rcx, rbx; hMem
0x18000a791  call    cs:__imp_LocalFree
0x18000a798  nop     dword ptr [rax+rax+00h]
0x18000a79d  lea     rax, [rbp+800h+Source]
0x18000a7a4  cmp     r12, rax
0x18000a7a7  jnz     loc_18000ABC0
0x18000a7ad  test    r15, r15
0x18000a7b0  jnz     loc_18000ABC8
0x18000a7b6  mov     eax, edi
0x18000a7b8  mov     rcx, [rbp+800h+var_40]
0x18000a7bf  xor     rcx, rsp; StackCookie
0x18000a7c2  call    __security_check_cookie
0x18000a7c7  mov     rbx, [rsp+900h+arg_10]
0x18000a7cf  add     rsp, 8D0h
0x18000a7d6  pop     r15
0x18000a7d8  pop     r14
0x18000a7da  pop     r13
0x18000a7dc  pop     r12
0x18000a7de  pop     rdi
0x18000a7df  pop     rsi
0x18000a7e0  pop     rbp
0x18000a7e1  retn
0x18000a7e3  lea     r8, aSoftwareWow643; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x18000a7ea  mov     [rsp+900h+var_8A0], rdi
0x18000a7ef  mov     edx, 104h; SizeInWords
0x18000a7f4  lea     rcx, [rbp+800h+SubKey]; Destination
0x18000a7fb  call    cs:__imp_wcscpy_s
0x18000a802  nop     dword ptr [rax+rax+00h]
0x18000a807  mov     r8, r14; Source
0x18000a80a  lea     rcx, [rbp+800h+SubKey]; Destination
0x18000a811  mov     edx, 104h; SizeInWords
0x18000a816  call    cs:__imp_wcscat_s
0x18000a81d  nop     dword ptr [rax+rax+00h]
0x18000a822  mov     edx, 2Eh ; '.'; Ch
0x18000a827  mov     rcx, r14; Str
0x18000a82a  call    cs:__imp_wcschr
0x18000a831  nop     dword ptr [rax+rax+00h]
0x18000a836  test    rax, rax
0x18000a839  jz      loc_18000AA01
0x18000a83f  lea     rax, [rsp+900h+var_8A0]
0x18000a844  mov     r9d, 20019h; samDesired
0x18000a84a  xor     r8d, r8d; ulOptions
0x18000a84d  mov     [rsp+900h+phkResult], rax; phkResult
0x18000a852  lea     rdx, [rbp+800h+SubKey]; lpSubKey
0x18000a859  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a860  call    cs:__imp_RegOpenKeyExW
0x18000a867  nop     dword ptr [rax+rax+00h]
0x18000a86c  test    eax, eax
0x18000a86e  jz      loc_18000AA25
0x18000a874  mov     rcx, [rsp+900h+var_8A0]; hKey
0x18000a879  test    rcx, rcx
0x18000a87c  jnz     loc_18000AA34
0x18000a882  lea     r8, aSoftwareWowaa3; "Software\\WowAA32Node\\Microsoft\\Windo"...
0x18000a889  mov     [rsp+900h+hKey], rdi
0x18000a88e  mov     edx, 104h; SizeInWords
0x18000a893  lea     rcx, [rbp+800h+var_460]; Destination
0x18000a89a  call    cs:__imp_wcscpy_s
0x18000a8a1  nop     dword ptr [rax+rax+00h]
0x18000a8a6  mov     r8, r14; Source
0x18000a8a9  lea     rcx, [rbp+800h+var_460]; Destination
0x18000a8b0  mov     edx, 104h; SizeInWords
0x18000a8b5  call    cs:__imp_wcscat_s
0x18000a8bc  nop     dword ptr [rax+rax+00h]
0x18000a8c1  mov     edx, 2Eh ; '.'; Ch
0x18000a8c6  mov     rcx, r14; Str
0x18000a8c9  call    cs:__imp_wcschr
0x18000a8d0  nop     dword ptr [rax+rax+00h]
0x18000a8d5  test    rax, rax
0x18000a8d8  jz      loc_18000AA4A
0x18000a8de  lea     rax, [rsp+900h+hKey]
0x18000a8e3  mov     r9d, 20019h; samDesired
0x18000a8e9  xor     r8d, r8d; ulOptions
0x18000a8ec  mov     [rsp+900h+phkResult], rax; phkResult
0x18000a8f1  lea     rdx, [rbp+800h+var_460]; lpSubKey
0x18000a8f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a8ff  call    cs:__imp_RegOpenKeyExW
0x18000a906  nop     dword ptr [rax+rax+00h]
0x18000a90b  mov     esi, eax
0x18000a90d  test    eax, eax
0x18000a90f  jz      loc_18000AA6E
0x18000a915  mov     rcx, [rsp+900h+hKey]; hKey
0x18000a91a  test    rcx, rcx
0x18000a91d  jz      loc_18000A628
0x18000a923  call    cs:__imp_RegCloseKey
0x18000a92a  nop     dword ptr [rax+rax+00h]
0x18000a92f  mov     [rsp+900h+hKey], rdi
0x18000a934  jmp     loc_18000A628
0x18000a939  cmp     esi, 2
0x18000a93c  cmovnz  edi, esi
0x18000a93f  xor     ecx, ecx; hMem
0x18000a941  call    cs:__imp_LocalFree
0x18000a948  nop     dword ptr [rax+rax+00h]
0x18000a94d  jmp     loc_18000A7AD
0x18000a952  mov     eax, [rsp+900h+pdwType]
0x18000a956  dec     eax
0x18000a958  cmp     eax, 1
0x18000a95b  ja      loc_18000A78E
0x18000a961  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a968  nop     dword ptr [rax+rax+00000000h]
0x18000a970  inc     rax
0x18000a973  cmp     word ptr [rbx+rax*2], 0
0x18000a978  jnz     short loc_18000A970
0x18000a97a  mov     r9, rbx
0x18000a97d  mov     [rsp+900h+phkResult], rax
0x18000a982  mov     r8d, 4
0x18000a988  lea     rdx, aPath; "PATH"
0x18000a98f  mov     rcx, r13
0x18000a992  call    cs:__imp_RtlSetEnvironmentVar
0x18000a999  nop     dword ptr [rax+rax+00h]
0x18000a99e  test    eax, eax
0x18000a9a0  jns     loc_18000A78E
0x18000a9a6  mov     ecx, eax; Status
0x18000a9a8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a9af  nop     dword ptr [rax+rax+00h]
0x18000a9b4  mov     edi, eax
0x18000a9b6  jmp     loc_18000A78E
0x18000a9bb  lea     r8, aExe; ".exe"
0x18000a9c2  mov     edx, 104h; SizeInWords
0x18000a9c7  lea     rcx, [rbp+800h+Destination]; Destination
0x18000a9cb  call    cs:__imp_wcscat_s
0x18000a9d2  nop     dword ptr [rax+rax+00h]
0x18000a9d7  jmp     loc_18000A5DD
0x18000a9dc  mov     r15, [rsp+900h+var_8A8]
0x18000a9e1  mov     [rsp+900h+var_8A8], rdi
0x18000a9e6  jmp     loc_18000A630
0x18000a9eb  call    cs:__imp_RegCloseKey
0x18000a9f2  nop     dword ptr [rax+rax+00h]
0x18000a9f7  mov     [rsp+900h+var_8A8], rdi
0x18000a9fc  jmp     loc_18000A61F
0x18000aa01  lea     r8, aExe; ".exe"
0x18000aa08  mov     edx, 104h; SizeInWords
0x18000aa0d  lea     rcx, [rbp+800h+SubKey]; Destination
0x18000aa14  call    cs:__imp_wcscat_s
0x18000aa1b  nop     dword ptr [rax+rax+00h]
0x18000aa20  jmp     loc_18000A83F
0x18000aa25  mov     r15, [rsp+900h+var_8A0]
0x18000aa2a  mov     [rsp+900h+var_8A0], rdi
0x18000aa2f  jmp     loc_18000A630
0x18000aa34  call    cs:__imp_RegCloseKey
0x18000aa3b  nop     dword ptr [rax+rax+00h]
0x18000aa40  mov     [rsp+900h+var_8A0], rdi
0x18000aa45  jmp     loc_18000A882
0x18000aa4a  lea     r8, aExe; ".exe"
0x18000aa51  mov     edx, 104h; SizeInWords
0x18000aa56  lea     rcx, [rbp+800h+var_460]; Destination
0x18000aa5d  call    cs:__imp_wcscat_s
0x18000aa64  nop     dword ptr [rax+rax+00h]
0x18000aa69  jmp     loc_18000A8DE
0x18000aa6e  mov     r15, [rsp+900h+hKey]
0x18000aa73  jmp     loc_18000A92F
  ... truncated ...
```
