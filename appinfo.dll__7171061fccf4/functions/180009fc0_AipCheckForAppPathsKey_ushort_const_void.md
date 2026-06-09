# AipCheckForAppPathsKey(ushort const *,void * *)

- ea: `0x180009fc0`
- end: `0x18000a5dd`
- name: `?AipCheckForAppPathsKey@@YAKPEBGPEAPEAX@Z`
- size: `1565`
- prototype: `__int64 __fastcall(wchar_t *Str, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d8fc`

## callees

- `0x180009fc0`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000a042`
- `msvcrt!wcsrchr` at `0x18000a042`
- `msvcrt!wcschr` at `0x18000a08b`
- `msvcrt!wcschr` at `0x18000a2b5`
- `msvcrt!wcschr` at `0x18000a33c`
- `msvcrt!wcschr` at `0x18000a08b`
- `msvcrt!wcschr` at `0x18000a2b5`
- `msvcrt!wcschr` at `0x18000a33c`
- `msvcrt!wcscat_s` at `0x18000a07d`
- `msvcrt!wcscat_s` at `0x18000a2a7`
- `msvcrt!wcscat_s` at `0x18000a32e`
- `msvcrt!wcscat_s` at `0x18000a413`
- `msvcrt!wcscat_s` at `0x18000a450`
- `msvcrt!wcscat_s` at `0x18000a48d`
- `msvcrt!wcscat_s` at `0x18000a546`
- `msvcrt!wcscat_s` at `0x18000a5a0`
- `msvcrt!wcscat_s` at `0x18000a5af`
- `msvcrt!wcscat_s` at `0x18000a07d`
- `msvcrt!wcscat_s` at `0x18000a2a7`
- `msvcrt!wcscat_s` at `0x18000a32e`
- `msvcrt!wcscat_s` at `0x18000a413`
- `msvcrt!wcscat_s` at `0x18000a450`
- `msvcrt!wcscat_s` at `0x18000a48d`
- `msvcrt!wcscat_s` at `0x18000a546`
- `msvcrt!wcscat_s` at `0x18000a5a0`
- `msvcrt!wcscat_s` at `0x18000a5af`
- `msvcrt!wcscpy_s` at `0x18000a06a`
- `msvcrt!wcscpy_s` at `0x18000a292`
- `msvcrt!wcscpy_s` at `0x18000a319`
- `msvcrt!wcscpy_s` at `0x18000a533`
- `msvcrt!wcscpy_s` at `0x18000a06a`
- `msvcrt!wcscpy_s` at `0x18000a292`
- `msvcrt!wcscpy_s` at `0x18000a319`
- `msvcrt!wcscpy_s` at `0x18000a533`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a36c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a2e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a36c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a163`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a1a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a21c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a57e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a163`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a1a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a21c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a38a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a42d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a46a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a38a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a42d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a46a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a22f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a22f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a4c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a1d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a4c8`
- `ntdll!RtlSetEnvironmentVar` at `0x18000a3e5`
- `ntdll!RtlSetEnvironmentVar` at `0x18000a3e5`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a113`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a503`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a113`
- `ntdll!RtlQueryEnvironmentVariable` at `0x18000a503`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a3f5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a513`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a3f5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000a513`

## string_xrefs

- `0x18000a054`: `Software\Microsoft\Windows\CurrentVersion\App Paths`
- `0x18000a135`: `AppendPath`
- `0x18000a27a`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\App Paths`
- `0x18000a301`: `Software\WowAA32Node\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
__int64 __fastcall AipCheckForAppPathsKey(wchar_t *Str, void **a2)
{
  ULONG ValueW; // esi
  HKEY v5; // r15
  const wchar_t *v6; // r12
  wchar_t *v7; // rbx
  wchar_t *v8; // r14
  LSTATUS v9; // edi
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rax
  rsize_t v14; // rdi
  wchar_t *v15; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rax
  NTSTATUS v19; // eax
  __int64 v20; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v26; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v30[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t Source[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  ValueW = 0;
  v5 = 0;
  memset_0(Source, 0, 0x208u);
  pcbData = 0;
  v6 = Source;
  pdwType = 0;
  v7 = 0;
  pvData = 0;
  v24 = 0;
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
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &phkResult);// Path-trust audit: App Paths lookup uses HKLM machine view only (plus Wow6432/WowAA32 fallbacks), not HKCU/HKCR overlay.
  if ( v9 )
  {
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( v9 == 2 )
    {
      v26 = 0;
      wcscpy_s(SubKey, 0x104u, L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\App Paths");
      wcscat_s(SubKey, 0x104u, v8);
      if ( !wcschr(v8, 0x2Eu) )
        wcscat_s(SubKey, 0x104u, L".exe");
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v26) )
      {
        v5 = v26;
        v26 = 0;
        goto LABEL_10;
      }
      if ( v26 )
      {
        RegCloseKey(v26);
        v26 = 0;
      }
      hKey = 0;
      wcscpy_s(v30, 0x104u, L"Software\\WowAA32Node\\Microsoft\\Windows\\CurrentVersion\\App Paths");
      wcscat_s(v30, 0x104u, v8);
      if ( !wcschr(v8, 0x2Eu) )
        wcscat_s(v30, 0x104u, L".exe");
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v30, 0, 0x20019u, &hKey);
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
    }
  }
  else
  {
    v5 = phkResult;
    phkResult = 0;
  }
LABEL_9:
  if ( v9 )
  {
    if ( v9 != 2 )
      ValueW = v9;
    v17 = 0;
    goto LABEL_38;
  }
LABEL_10:
  v10 = RtlQueryEnvironmentVariable(*a2, L"PATH", 4, Source, 260, &v24);
  if ( v10 >= 0 )
  {
LABEL_11:
    v11 = v24;
    goto LABEL_12;
  }
  if ( v10 != -1073741568 )
  {
    if ( v10 != -1073741789 )
      goto LABEL_53;
    v20 = v24;
    v6 = (const wchar_t *)LocalAlloc(0, 2 * v24);
    if ( !v6 )
    {
      ValueW = 8;
      goto LABEL_20;
    }
    v10 = RtlQueryEnvironmentVariable(*a2, L"PATH", 4, v6, v20, &v24);
    if ( v10 < 0 )
    {
LABEL_53:
      ValueW = RtlNtStatusToDosErrorNoTeb(v10);
      goto LABEL_20;
    }
    goto LABEL_11;
  }
  v11 = 0;
  v24 = 0;
LABEL_12:
  v6[v11] = 0;
  v12 = (unsigned int)v24;
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
    if ( pdwType - 1 <= 1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v7[v18] );
      v19 = RtlSetEnvironmentVar(a2, L"PATH", 4, v7, v18);
      if ( v19 < 0 )
        ValueW = RtlNtStatusToDosErrorNoTeb(v19);
    }
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
0x180009fc0  mov     [rsp-8+arg_10], rbx
0x180009fc5  push    rbp
0x180009fc6  push    rsi
0x180009fc7  push    rdi
0x180009fc8  push    r12
0x180009fca  push    r13
0x180009fcc  push    r14
0x180009fce  push    r15
0x180009fd0  lea     rbp, [rsp-7C0h]
0x180009fd8  sub     rsp, 8C0h
0x180009fdf  mov     rax, cs:__security_cookie
0x180009fe6  xor     rax, rsp
0x180009fe9  mov     [rbp+7F0h+var_40], rax
0x180009ff0  mov     r13, rdx
0x180009ff3  mov     rdi, rcx
0x180009ff6  xor     r14d, r14d
0x180009ff9  lea     rcx, [rbp+7F0h+Source]; void *
0x18000a000  xor     edx, edx; Val
0x18000a002  mov     r8d, 208h; Size
0x18000a008  mov     esi, r14d
0x18000a00b  mov     r15d, r14d
0x18000a00e  call    memset_0
0x18000a013  mov     [rsp+8F0h+var_8B0], r14d
0x18000a018  lea     r12, [rbp+7F0h+Source]
0x18000a01f  mov     [rsp+8F0h+pdwType], r14d
0x18000a024  mov     ebx, r14d
0x18000a027  mov     [rsp+8F0h+var_8AC], r14d
0x18000a02c  mov     [rsp+8F0h+var_8A0], r14
0x18000a031  test    rdi, rdi
0x18000a034  jz      loc_18000A22C
0x18000a03a  mov     edx, 5Ch ; '\'; Ch
0x18000a03f  mov     rcx, rdi; Str
0x18000a042  call    cs:__imp_wcsrchr
0x18000a048  mov     r14, rax
0x18000a04b  test    rax, rax
0x18000a04e  jz      loc_18000A22C
0x18000a054  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a05b  mov     [rsp+8F0h+var_898], rsi
0x18000a060  mov     edx, 104h; SizeInWords
0x18000a065  lea     rcx, [rsp+8F0h+Destination]; Destination
0x18000a06a  call    cs:__imp_wcscpy_s
0x18000a070  mov     r8, r14; Source
0x18000a073  lea     rcx, [rsp+8F0h+Destination]; Destination
0x18000a078  mov     edx, 104h; SizeInWords
0x18000a07d  call    cs:__imp_wcscat_s
0x18000a083  mov     edx, 2Eh ; '.'; Ch
0x18000a088  mov     rcx, r14; Str
0x18000a08b  call    cs:__imp_wcschr
0x18000a091  test    rax, rax
0x18000a094  jz      loc_18000A402
0x18000a09a  lea     rax, [rsp+8F0h+var_898]
0x18000a09f  mov     r9d, 20019h; samDesired
0x18000a0a5  xor     r8d, r8d; ulOptions
0x18000a0a8  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18000a0ad  lea     rdx, [rsp+8F0h+Destination]; lpSubKey
0x18000a0b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a0b9  call    cs:__imp_RegOpenKeyExW
0x18000a0bf  mov     edi, eax; Path-trust audit: App Paths lookup uses HKLM machine view only (plus Wow6432/WowAA32 fallbacks), not HKCU/HKCR overlay.
0x18000a0c1  test    eax, eax
0x18000a0c3  jz      loc_18000A41E
0x18000a0c9  mov     rcx, [rsp+8F0h+var_898]; hKey
0x18000a0ce  test    rcx, rcx
0x18000a0d1  jnz     loc_18000A42D
0x18000a0d7  cmp     edi, 2
0x18000a0da  jz      loc_18000A27A
0x18000a0e0  test    edi, edi
0x18000a0e2  jnz     loc_18000A39A
0x18000a0e8  mov     rcx, [r13+0]
0x18000a0ec  lea     rax, [rsp+8F0h+var_8A0]
0x18000a0f1  mov     [rsp+8F0h+pvData], rax
0x18000a0f6  lea     r9, [rbp+7F0h+Source]
0x18000a0fd  mov     r8d, 4
0x18000a103  mov     [rsp+8F0h+phkResult], 104h
0x18000a10c  lea     rdx, aPath; "PATH"
0x18000a113  call    cs:__imp_RtlQueryEnvironmentVariable
0x18000a119  test    eax, eax
0x18000a11b  js      loc_18000A4A2
0x18000a121  mov     rcx, [rsp+8F0h+var_8A0]
0x18000a126  mov     [r12+rcx*2], si
0x18000a12b  lea     rax, [rsp+8F0h+var_8B0]
0x18000a130  mov     r14d, dword ptr [rsp+8F0h+var_8A0]
0x18000a135  lea     r8, Value; "AppendPath"
0x18000a13c  mov     [rsp+8F0h+pcbData], rax; pcbData
0x18000a141  mov     r9d, 10h; dwFlags
0x18000a147  lea     rax, [rsp+8F0h+var_8AC]
0x18000a14c  mov     [rsp+8F0h+var_8B0], 4
0x18000a154  mov     [rsp+8F0h+pvData], rax; pvData
0x18000a159  xor     edx, edx; lpSubKey
0x18000a15b  mov     rcx, r15; hkey
0x18000a15e  mov     [rsp+8F0h+phkResult], rsi; pdwType
0x18000a163  call    cs:__imp_RegGetValueW
0x18000a169  test    eax, eax
0x18000a16b  jz      short loc_18000A171
0x18000a16d  mov     [rsp+8F0h+var_8AC], esi
0x18000a171  lea     rax, [rsp+8F0h+var_8B0]
0x18000a176  mov     [rsp+8F0h+var_8B0], esi
0x18000a17a  mov     [rsp+8F0h+pcbData], rax; pcbData
0x18000a17f  lea     r8, aPath_0; "Path"
0x18000a186  lea     rax, [rsp+8F0h+pdwType]
0x18000a18b  mov     [rsp+8F0h+pvData], rsi; pvData
0x18000a190  mov     r9d, 0FFFFh; dwFlags
0x18000a196  mov     [rsp+8F0h+phkResult], rax; pdwType
0x18000a19b  xor     edx, edx; lpSubKey
0x18000a19d  mov     rcx, r15; hkey
0x18000a1a0  call    cs:__imp_RegGetValueW
0x18000a1a6  mov     esi, eax
0x18000a1a8  test    eax, eax
0x18000a1aa  jnz     loc_18000A5BA
0x18000a1b0  mov     eax, [rsp+8F0h+pdwType]
0x18000a1b4  dec     eax
0x18000a1b6  cmp     eax, 1
0x18000a1b9  ja      short loc_18000A22C
0x18000a1bb  mov     eax, [rsp+8F0h+var_8B0]
0x18000a1bf  cmp     eax, 2
0x18000a1c2  jbe     short loc_18000A22C
0x18000a1c4  shr     eax, 1
0x18000a1c6  mov     ecx, 40h ; '@'; uFlags
0x18000a1cb  inc     eax
0x18000a1cd  add     eax, r14d
0x18000a1d0  mov     edi, eax
0x18000a1d2  lea     rdx, [rax+rax]; uBytes
0x18000a1d6  call    cs:__imp_LocalAlloc
0x18000a1dc  mov     rbx, rax
0x18000a1df  test    rax, rax
0x18000a1e2  jz      loc_18000A520
0x18000a1e8  cmp     [rsp+8F0h+var_8AC], esi
0x18000a1ec  jnz     loc_18000A52A
0x18000a1f2  lea     rax, [rsp+8F0h+var_8B0]
0x18000a1f7  mov     r9d, 0FFFFh; dwFlags
0x18000a1fd  mov     [rsp+8F0h+pcbData], rax; pcbData
0x18000a202  lea     r8, aPath_0; "Path"
0x18000a209  mov     [rsp+8F0h+pvData], rbx; pvData
0x18000a20e  xor     edx, edx; lpSubKey
0x18000a210  mov     rcx, r15; hkey
0x18000a213  mov     [rsp+8F0h+phkResult], 0; pdwType
0x18000a21c  call    cs:__imp_RegGetValueW
0x18000a222  mov     esi, eax
0x18000a224  test    eax, eax
0x18000a226  jz      loc_18000A593
0x18000a22c  mov     rcx, rbx; hMem
0x18000a22f  call    cs:__imp_LocalFree
0x18000a235  lea     rax, [rbp+7F0h+Source]
0x18000a23c  cmp     r12, rax
0x18000a23f  jnz     loc_18000A5C7
0x18000a245  test    r15, r15
0x18000a248  jnz     loc_18000A5CF
0x18000a24e  mov     eax, esi
0x18000a250  mov     rcx, [rbp+7F0h+var_40]
0x18000a257  xor     rcx, rsp; StackCookie
0x18000a25a  call    __security_check_cookie
0x18000a25f  mov     rbx, [rsp+8F0h+arg_10]
0x18000a267  add     rsp, 8C0h
0x18000a26e  pop     r15
0x18000a270  pop     r14
0x18000a272  pop     r13
0x18000a274  pop     r12
0x18000a276  pop     rdi
0x18000a277  pop     rsi
0x18000a278  pop     rbp
0x18000a279  retn
0x18000a27a  lea     r8, aSoftwareWow643; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x18000a281  mov     [rsp+8F0h+var_890], rsi
0x18000a286  mov     edx, 104h; SizeInWords
0x18000a28b  lea     rcx, [rbp+7F0h+SubKey]; Destination
0x18000a292  call    cs:__imp_wcscpy_s
0x18000a298  mov     r8, r14; Source
0x18000a29b  lea     rcx, [rbp+7F0h+SubKey]; Destination
0x18000a2a2  mov     edx, 104h; SizeInWords
0x18000a2a7  call    cs:__imp_wcscat_s
0x18000a2ad  mov     edx, 2Eh ; '.'; Ch
0x18000a2b2  mov     rcx, r14; Str
0x18000a2b5  call    cs:__imp_wcschr
0x18000a2bb  test    rax, rax
0x18000a2be  jz      loc_18000A43D
0x18000a2c4  lea     rax, [rsp+8F0h+var_890]
0x18000a2c9  mov     r9d, 20019h; samDesired
0x18000a2cf  xor     r8d, r8d; ulOptions
0x18000a2d2  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18000a2d7  lea     rdx, [rbp+7F0h+SubKey]; lpSubKey
0x18000a2de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a2e5  call    cs:__imp_RegOpenKeyExW
0x18000a2eb  test    eax, eax
0x18000a2ed  jz      loc_18000A45B
0x18000a2f3  mov     rcx, [rsp+8F0h+var_890]; hKey
0x18000a2f8  test    rcx, rcx
0x18000a2fb  jnz     loc_18000A46A
0x18000a301  lea     r8, aSoftwareWowaa3; "Software\\WowAA32Node\\Microsoft\\Windo"...
0x18000a308  mov     [rsp+8F0h+hKey], rsi
0x18000a30d  mov     edx, 104h; SizeInWords
0x18000a312  lea     rcx, [rbp+7F0h+var_460]; Destination
0x18000a319  call    cs:__imp_wcscpy_s
0x18000a31f  mov     r8, r14; Source
0x18000a322  lea     rcx, [rbp+7F0h+var_460]; Destination
0x18000a329  mov     edx, 104h; SizeInWords
0x18000a32e  call    cs:__imp_wcscat_s
0x18000a334  mov     edx, 2Eh ; '.'; Ch
0x18000a339  mov     rcx, r14; Str
0x18000a33c  call    cs:__imp_wcschr
0x18000a342  test    rax, rax
0x18000a345  jz      loc_18000A47A
0x18000a34b  lea     rax, [rsp+8F0h+hKey]
0x18000a350  mov     r9d, 20019h; samDesired
0x18000a356  xor     r8d, r8d; ulOptions
0x18000a359  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18000a35e  lea     rdx, [rbp+7F0h+var_460]; lpSubKey
0x18000a365  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a36c  call    cs:__imp_RegOpenKeyExW
0x18000a372  mov     edi, eax
0x18000a374  test    eax, eax
0x18000a376  jz      loc_18000A498
0x18000a37c  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18000a381  test    rcx, rcx
0x18000a384  jz      loc_18000A0E0
0x18000a38a  call    cs:__imp_RegCloseKey
0x18000a390  mov     [rsp+8F0h+hKey], rsi
0x18000a395  jmp     loc_18000A0E0
0x18000a39a  cmp     edi, 2
0x18000a39d  cmovnz  esi, edi
0x18000a3a0  xor     ecx, ecx; hMem
0x18000a3a2  call    cs:__imp_LocalFree
0x18000a3a8  jmp     loc_18000A245
0x18000a3ad  mov     eax, [rsp+8F0h+pdwType]
0x18000a3b1  dec     eax
0x18000a3b3  cmp     eax, 1
0x18000a3b6  ja      loc_18000A22C
0x18000a3bc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a3c3  inc     rax
0x18000a3c6  cmp     word ptr [rbx+rax*2], 0
0x18000a3cb  jnz     short loc_18000A3C3
0x18000a3cd  mov     r9, rbx
0x18000a3d0  mov     [rsp+8F0h+phkResult], rax
0x18000a3d5  mov     r8d, 4
0x18000a3db  lea     rdx, aPath; "PATH"
0x18000a3e2  mov     rcx, r13
0x18000a3e5  call    cs:__imp_RtlSetEnvironmentVar
0x18000a3eb  test    eax, eax
0x18000a3ed  jns     loc_18000A22C
0x18000a3f3  mov     ecx, eax; Status
0x18000a3f5  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a3fb  mov     esi, eax
0x18000a3fd  jmp     loc_18000A22C
0x18000a402  lea     r8, aExe; ".exe"
0x18000a409  mov     edx, 104h; SizeInWords
0x18000a40e  lea     rcx, [rsp+8F0h+Destination]; Destination
0x18000a413  call    cs:__imp_wcscat_s
0x18000a419  jmp     loc_18000A09A
0x18000a41e  mov     r15, [rsp+8F0h+var_898]
0x18000a423  mov     [rsp+8F0h+var_898], rsi
0x18000a428  jmp     loc_18000A0E0
0x18000a42d  call    cs:__imp_RegCloseKey
0x18000a433  mov     [rsp+8F0h+var_898], rsi
0x18000a438  jmp     loc_18000A0D7
0x18000a43d  lea     r8, aExe; ".exe"
0x18000a444  mov     edx, 104h; SizeInWords
0x18000a449  lea     rcx, [rbp+7F0h+SubKey]; Destination
0x18000a450  call    cs:__imp_wcscat_s
0x18000a456  jmp     loc_18000A2C4
0x18000a45b  mov     r15, [rsp+8F0h+var_890]
0x18000a460  mov     [rsp+8F0h+var_890], rsi
0x18000a465  jmp     loc_18000A0E8
0x18000a46a  call    cs:__imp_RegCloseKey
0x18000a470  mov     [rsp+8F0h+var_890], rsi
0x18000a475  jmp     loc_18000A301
0x18000a47a  lea     r8, aExe; ".exe"
0x18000a481  mov     edx, 104h; SizeInWords
0x18000a486  lea     rcx, [rbp+7F0h+var_460]; Destination
0x18000a48d  call    cs:__imp_wcscat_s
0x18000a493  jmp     loc_18000A34B
0x18000a498  mov     r15, [rsp+8F0h+hKey]
0x18000a49d  jmp     loc_18000A390
0x18000a4a2  cmp     eax, 0C0000100h
0x18000a4a7  jnz     short loc_18000A4B6
0x18000a4a9  mov     rcx, rsi
0x18000a4ac  mov     [rsp+8F0h+var_8A0], rcx
0x18000a4b1  jmp     loc_18000A126
0x18000a4b6  cmp     eax, 0C0000023h
0x18000a4bb  jnz     short loc_18000A511
0x18000a4bd  mov     rdi, [rsp+8F0h+var_8A0]
0x18000a4c2  xor     ecx, ecx; uFlags
0x18000a4c4  lea     rdx, [rdi+rdi]; uBytes
0x18000a4c8  call    cs:__imp_LocalAlloc
0x18000a4ce  mov     r12, rax
0x18000a4d1  test    rax, rax
0x18000a4d4  jnz     short loc_18000A4E0
0x18000a4d6  mov     esi, 8
0x18000a4db  jmp     loc_18000A22C
0x18000a4e0  mov     rcx, [r13+0]
0x18000a4e4  lea     rax, [rsp+8F0h+var_8A0]
0x18000a4e9  mov     [rsp+8F0h+pvData], rax
0x18000a4ee  lea     rdx, aPath; "PATH"
0x18000a4f5  mov     r9, r12
0x18000a4f8  mov     [rsp+8F0h+phkResult], rdi
0x18000a4fd  mov     r8d, 4
0x18000a503  call    cs:__imp_RtlQueryEnvironmentVariable
0x18000a509  test    eax, eax
0x18000a50b  jns     loc_18000A121
0x18000a511  mov     ecx, eax; Status
0x18000a513  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000a519  mov     esi, eax
0x18000a51b  jmp     loc_18000A22C
  ... truncated ...
```
