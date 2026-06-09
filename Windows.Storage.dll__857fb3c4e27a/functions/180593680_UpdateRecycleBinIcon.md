# UpdateRecycleBinIcon

- ea: `0x180593680`
- end: `0x180593beb`
- name: `UpdateRecycleBinIcon`
- size: `1387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180593078`

## callees

- `0x1800a3080`
- `0x1800aa710`
- `0x1803a4cb0`
- `0x180591b90`
- `0x180592eb8`
- `0x180593680`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180593b64`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180593b64`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x180593b52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRChrW` at `0x180593b52`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805937ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593869`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805938ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805939a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593a80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593b24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805937ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593869`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805938ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1805939a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593a80`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180593b24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180593bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180593bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180593bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180593bc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805937a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593824`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805938a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18059392b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593965`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593a00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593a3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593ae7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805937a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593824`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1805938a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18059392b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593965`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593a00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593a3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180593ae7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180593aa8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180593aa8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180593b3b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180593b3b`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805936f0`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180593720`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180593761`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1805936f0`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180593720`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x180593761`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x180593b7c`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_LookupBackIconIndex` at `0x180593b7c`

## pseudocode

```c
void __fastcall UpdateRecycleBinIcon(int a1)
{
  __int64 v2; // rbx
  const WCHAR *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  PWSTR v9; // rax
  PWSTR v10; // rdi
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // eax
  HKEY handle; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 Data[260]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+258h] [rbp+158h]
  WCHAR pszStart[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR String2[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR String1[264]; // [rsp+680h] [rbp+580h] BYREF

  cbData = 0;
  Type[0] = 0;
  hKey = 0;
  handle = 0;
  if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 0, 0, 1, &hKey) >= 0 )
  {
    v2 = -1;
    v3 = L"Full";
    if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 1, 0, 3, &handle) < 0 )
    {
      if ( (int)SHRegGetCLSIDKey(&CLSID_RecycleBin, L"DefaultIcon", 1, 1, 3, &handle) < 0 )
        goto LABEL_33;
      _SetLowRightsSACL(handle);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v4 = -1;
      do
        ++v4;
      while ( Data[v4] );
      RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v4 + 2);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, L"Full", 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v5 = -1;
      do
        ++v5;
      while ( Data[v5] );
      RegSetValueExW(handle, L"Full", 0, Type[0], (const BYTE *)Data, 2 * v5 + 2);
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, L"Empty", 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v6 = -1;
      do
        ++v6;
      while ( Data[v6] );
      RegSetValueExW(handle, L"Empty", 0, Type[0], (const BYTE *)Data, 2 * v6 + 2);
    }
    cbData = 520;
    v19 = 0;
    if ( RegQueryValueExW(handle, 0, 0, Type, (LPBYTE)Data, &cbData) )
    {
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v7 = -1;
      do
        ++v7;
      while ( Data[v7] );
      RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v7 + 2);
    }
    StringCchCopyW(String2, 0x105u, Data);
    cbData = 520;
    v19 = 0;
    if ( !a1 )
      v3 = L"Empty";
    if ( RegQueryValueExW(handle, v3, 0, Type, (LPBYTE)Data, &cbData) )
    {
      cbData = 520;
      v19 = 0;
      if ( RegQueryValueExW(hKey, v3, 0, Type, (LPBYTE)Data, &cbData) )
        goto LABEL_33;
      v8 = -1;
      do
        ++v8;
      while ( Data[v8] );
      RegSetValueExW(handle, v3, 0, Type[0], (const BYTE *)Data, 2 * v8 + 2);
    }
    StringCchCopyW(String1, 0x105u, Data);
    if ( lstrcmpiW(String1, String2) )
    {
      cbData = 520;
      v19 = 0;
      if ( !RegQueryValueExW(handle, v3, 0, Type, (LPBYTE)Data, &cbData) )
      {
        do
          ++v2;
        while ( Data[v2] );
        RegSetValueExW(handle, 0, 0, Type[0], (const BYTE *)Data, 2 * v2 + 2);
      }
      if ( (unsigned int)SHExpandEnvironmentStringsW(String2, pszStart, 261) )
      {
        v9 = StrRChrW(pszStart, 0, 0x2Cu);
        v10 = v9;
        if ( v9 )
        {
          v11 = StrToIntW(v9 + 1);
          *v10 = 0;
          v12 = v11;
          v13 = SHELL32_LookupBackIconIndex(pszStart, v11, 0);
          SHUpdateImageW(pszStart, v12, 0, v13);
          SHChangeNotify(0, 0x1000u, 0, 0);
        }
      }
    }
  }
LABEL_33:
  if ( hKey )
    RegCloseKey(hKey);
  if ( handle )
    RegCloseKey(handle);
}

```

## disassembly

```asm
0x180593680  push    rbp
0x180593682  push    rbx
0x180593683  push    rsi
0x180593684  push    rdi
0x180593685  push    r12
0x180593687  push    r13
0x180593689  push    r14
0x18059368b  push    r15
0x18059368d  lea     rbp, [rsp-7A8h]
0x180593695  sub     rsp, 8A8h
0x18059369c  mov     rax, cs:__security_cookie
0x1805936a3  xor     rax, rsp
0x1805936a6  mov     [rbp+7E0h+var_50], rax
0x1805936ad  xor     r14d, r14d
0x1805936b0  lea     rax, [rsp+8E0h+hKey]
0x1805936b5  mov     esi, ecx
0x1805936b7  mov     [rsp+8E0h+lpcbData], rax
0x1805936bc  lea     r13, c_szDefaultIcon; "DefaultIcon"
0x1805936c3  mov     [rsp+8E0h+cbData], r14d
0x1805936c8  xor     r9d, r9d
0x1805936cb  mov     [rsp+8E0h+Type], r14d
0x1805936d0  lea     r15d, [r14+1]
0x1805936d4  mov     [rsp+8E0h+hKey], r14
0x1805936d9  xor     r8d, r8d
0x1805936dc  mov     dword ptr [rsp+8E0h+lpData], r15d
0x1805936e1  mov     rdx, r13
0x1805936e4  mov     [rsp+8E0h+handle], r14
0x1805936e9  lea     rcx, CLSID_RecycleBin
0x1805936f0  call    cs:__imp_SHRegGetCLSIDKey
0x1805936f6  test    eax, eax
0x1805936f8  js      loc_180593BA8
0x1805936fe  lea     rax, [rsp+8E0h+handle]
0x180593703  xor     r9d, r9d
0x180593706  mov     [rsp+8E0h+lpcbData], rax
0x18059370b  lea     rcx, CLSID_RecycleBin
0x180593712  mov     r8d, r15d
0x180593715  mov     dword ptr [rsp+8E0h+lpData], 3
0x18059371d  mov     rdx, r13
0x180593720  call    cs:__imp_SHRegGetCLSIDKey
0x180593726  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18059372a  lea     rdi, aFull; "Full"
0x180593731  mov     r12d, 208h
0x180593737  test    eax, eax
0x180593739  jns     loc_1805938F4
0x18059373f  lea     rax, [rsp+8E0h+handle]
0x180593744  mov     r9d, r15d
0x180593747  mov     [rsp+8E0h+lpcbData], rax
0x18059374c  lea     rcx, CLSID_RecycleBin
0x180593753  mov     r8d, r15d
0x180593756  mov     dword ptr [rsp+8E0h+lpData], 3
0x18059375e  mov     rdx, r13
0x180593761  call    cs:__imp_SHRegGetCLSIDKey
0x180593767  test    eax, eax
0x180593769  js      loc_180593BA8
0x18059376f  mov     rcx, [rsp+8E0h+handle]; handle
0x180593774  call    ?_SetLowRightsSACL@@YAJPEAUHKEY__@@@Z; _SetLowRightsSACL(HKEY__ *)
0x180593779  mov     rcx, [rsp+8E0h+hKey]; hKey
0x18059377e  lea     rax, [rsp+8E0h+cbData]
0x180593783  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x180593788  lea     r9, [rsp+8E0h+Type]; lpType
0x18059378d  lea     rax, [rsp+8E0h+Data]
0x180593792  mov     [rsp+8E0h+cbData], r12d
0x180593797  xor     r8d, r8d; lpReserved
0x18059379a  mov     [rsp+8E0h+lpData], rax; lpData
0x18059379f  xor     edx, edx; lpValueName
0x1805937a1  mov     [rbp+7E0h+var_688], r14w
0x1805937a9  call    cs:__imp_RegQueryValueExW
0x1805937af  test    eax, eax
0x1805937b1  jnz     loc_180593BA8
0x1805937b7  lea     rcx, [rsp+8E0h+Data]
0x1805937bc  mov     rax, rbx
0x1805937bf  inc     rax
0x1805937c2  cmp     [rcx+rax*2], r14w
0x1805937c7  jnz     short loc_1805937BF
0x1805937c9  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805937ce  lea     eax, ds:2[rax*2]
0x1805937d5  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805937da  xor     r8d, r8d; Reserved
0x1805937dd  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805937e1  xor     edx, edx; lpValueName
0x1805937e3  lea     rax, [rsp+8E0h+Data]
0x1805937e8  mov     [rsp+8E0h+lpData], rax; lpData
0x1805937ed  call    cs:__imp_RegSetValueExW
0x1805937f3  mov     rcx, [rsp+8E0h+hKey]; hKey
0x1805937f8  lea     rax, [rsp+8E0h+cbData]
0x1805937fd  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x180593802  lea     r9, [rsp+8E0h+Type]; lpType
0x180593807  lea     rax, [rsp+8E0h+Data]
0x18059380c  mov     [rsp+8E0h+cbData], r12d
0x180593811  xor     r8d, r8d; lpReserved
0x180593814  mov     [rsp+8E0h+lpData], rax; lpData
0x180593819  mov     rdx, rdi; lpValueName
0x18059381c  mov     [rbp+7E0h+var_688], r14w
0x180593824  call    cs:__imp_RegQueryValueExW
0x18059382a  test    eax, eax
0x18059382c  jnz     loc_180593BA8
0x180593832  lea     rcx, [rsp+8E0h+Data]
0x180593837  mov     rax, rbx
0x18059383a  inc     rax
0x18059383d  cmp     [rcx+rax*2], r14w
0x180593842  jnz     short loc_18059383A
0x180593844  mov     r9d, [rsp+8E0h+Type]; dwType
0x180593849  lea     eax, ds:2[rax*2]
0x180593850  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593855  xor     r8d, r8d; Reserved
0x180593858  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x18059385c  mov     rdx, rdi; lpValueName
0x18059385f  lea     rax, [rsp+8E0h+Data]
0x180593864  mov     [rsp+8E0h+lpData], rax; lpData
0x180593869  call    cs:__imp_RegSetValueExW
0x18059386f  mov     rcx, [rsp+8E0h+hKey]; hKey
0x180593874  lea     rax, [rsp+8E0h+cbData]
0x180593879  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x18059387e  lea     r13, aEmpty_0; "Empty"
0x180593885  lea     rax, [rsp+8E0h+Data]
0x18059388a  mov     [rsp+8E0h+cbData], r12d
0x18059388f  lea     r9, [rsp+8E0h+Type]; lpType
0x180593894  mov     [rsp+8E0h+lpData], rax; lpData
0x180593899  xor     r8d, r8d; lpReserved
0x18059389c  mov     [rbp+7E0h+var_688], r14w
0x1805938a4  mov     rdx, r13; lpValueName
0x1805938a7  call    cs:__imp_RegQueryValueExW
0x1805938ad  test    eax, eax
0x1805938af  jnz     loc_180593BA8
0x1805938b5  lea     rcx, [rsp+8E0h+Data]
0x1805938ba  mov     rax, rbx
0x1805938bd  inc     rax
0x1805938c0  cmp     [rcx+rax*2], r14w
0x1805938c5  jnz     short loc_1805938BD
0x1805938c7  mov     r9d, [rsp+8E0h+Type]; dwType
0x1805938cc  lea     eax, ds:2[rax*2]
0x1805938d3  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805938d8  xor     r8d, r8d; Reserved
0x1805938db  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x1805938df  mov     rdx, r13; lpValueName
0x1805938e2  lea     rax, [rsp+8E0h+Data]
0x1805938e7  mov     [rsp+8E0h+lpData], rax; lpData
0x1805938ec  call    cs:__imp_RegSetValueExW
0x1805938f2  jmp     short loc_1805938FB
0x1805938f4  lea     r13, aEmpty_0; "Empty"
0x1805938fb  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593900  lea     rax, [rsp+8E0h+cbData]
0x180593905  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x18059390a  lea     r9, [rsp+8E0h+Type]; lpType
0x18059390f  lea     rax, [rsp+8E0h+Data]
0x180593914  mov     [rsp+8E0h+cbData], r12d
0x180593919  xor     r8d, r8d; lpReserved
0x18059391c  mov     [rsp+8E0h+lpData], rax; lpData
0x180593921  xor     edx, edx; lpValueName
0x180593923  mov     [rbp+7E0h+var_688], r14w
0x18059392b  call    cs:__imp_RegQueryValueExW
0x180593931  test    eax, eax
0x180593933  jz      short loc_1805939AF
0x180593935  mov     rcx, [rsp+8E0h+hKey]; hKey
0x18059393a  lea     rax, [rsp+8E0h+cbData]
0x18059393f  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x180593944  lea     r9, [rsp+8E0h+Type]; lpType
0x180593949  lea     rax, [rsp+8E0h+Data]
0x18059394e  mov     [rsp+8E0h+cbData], r12d
0x180593953  xor     r8d, r8d; lpReserved
0x180593956  mov     [rsp+8E0h+lpData], rax; lpData
0x18059395b  xor     edx, edx; lpValueName
0x18059395d  mov     [rbp+7E0h+var_688], r14w
0x180593965  call    cs:__imp_RegQueryValueExW
0x18059396b  test    eax, eax
0x18059396d  jnz     loc_180593BA8
0x180593973  lea     rcx, [rsp+8E0h+Data]
0x180593978  mov     rax, rbx
0x18059397b  inc     rax
0x18059397e  cmp     [rcx+rax*2], r14w
0x180593983  jnz     short loc_18059397B
0x180593985  mov     r9d, [rsp+8E0h+Type]; dwType
0x18059398a  lea     eax, ds:2[rax*2]
0x180593991  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593996  xor     r8d, r8d; Reserved
0x180593999  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x18059399d  xor     edx, edx; lpValueName
0x18059399f  lea     rax, [rsp+8E0h+Data]
0x1805939a4  mov     [rsp+8E0h+lpData], rax; lpData
0x1805939a9  call    cs:__imp_RegSetValueExW
0x1805939af  mov     r15d, 105h
0x1805939b5  lea     r8, [rsp+8E0h+Data]; unsigned __int16 *
0x1805939ba  mov     edx, r15d; unsigned __int64
0x1805939bd  lea     rcx, [rbp+7E0h+String2]; unsigned __int16 *
0x1805939c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805939c9  mov     rcx, [rsp+8E0h+handle]; hKey
0x1805939ce  lea     rax, [rsp+8E0h+cbData]
0x1805939d3  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x1805939d8  lea     r9, [rsp+8E0h+Type]; lpType
0x1805939dd  lea     rax, [rsp+8E0h+Data]
0x1805939e2  mov     [rsp+8E0h+cbData], r12d
0x1805939e7  test    esi, esi
0x1805939e9  mov     [rbp+7E0h+var_688], r14w
0x1805939f1  mov     [rsp+8E0h+lpData], rax; lpData
0x1805939f6  cmovz   rdi, r13
0x1805939fa  xor     r8d, r8d; lpReserved
0x1805939fd  mov     rdx, rdi; lpValueName
0x180593a00  call    cs:__imp_RegQueryValueExW
0x180593a06  test    eax, eax
0x180593a08  jz      short loc_180593A86
0x180593a0a  mov     rcx, [rsp+8E0h+hKey]; hKey
0x180593a0f  lea     rax, [rsp+8E0h+cbData]
0x180593a14  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x180593a19  lea     r9, [rsp+8E0h+Type]; lpType
0x180593a1e  lea     rax, [rsp+8E0h+Data]
0x180593a23  mov     [rsp+8E0h+cbData], r12d
0x180593a28  xor     r8d, r8d; lpReserved
0x180593a2b  mov     [rsp+8E0h+lpData], rax; lpData
0x180593a30  mov     rdx, rdi; lpValueName
0x180593a33  mov     [rbp+7E0h+var_688], r14w
0x180593a3b  call    cs:__imp_RegQueryValueExW
0x180593a41  test    eax, eax
0x180593a43  jnz     loc_180593BA8
0x180593a49  lea     rcx, [rsp+8E0h+Data]
0x180593a4e  mov     rax, rbx
0x180593a51  inc     rax
0x180593a54  cmp     [rcx+rax*2], r14w
0x180593a59  jnz     short loc_180593A51
0x180593a5b  mov     r9d, [rsp+8E0h+Type]; dwType
0x180593a60  lea     eax, ds:2[rax*2]
0x180593a67  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593a6c  xor     r8d, r8d; Reserved
0x180593a6f  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x180593a73  mov     rdx, rdi; lpValueName
0x180593a76  lea     rax, [rsp+8E0h+Data]
0x180593a7b  mov     [rsp+8E0h+lpData], rax; lpData
0x180593a80  call    cs:__imp_RegSetValueExW
0x180593a86  lea     r8, [rsp+8E0h+Data]; unsigned __int16 *
0x180593a8b  mov     rdx, r15; unsigned __int64
0x180593a8e  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x180593a95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180593a9a  lea     rdx, [rbp+7E0h+String2]; lpString2
0x180593aa1  lea     rcx, [rbp+7E0h+String1]; lpString1
0x180593aa8  call    cs:__imp_lstrcmpiW
0x180593aae  test    eax, eax
0x180593ab0  jz      loc_180593BA8
0x180593ab6  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593abb  lea     rax, [rsp+8E0h+cbData]
0x180593ac0  mov     [rsp+8E0h+lpcbData], rax; lpcbData
0x180593ac5  lea     r9, [rsp+8E0h+Type]; lpType
0x180593aca  lea     rax, [rsp+8E0h+Data]
0x180593acf  mov     [rsp+8E0h+cbData], r12d
0x180593ad4  xor     r8d, r8d; lpReserved
0x180593ad7  mov     [rsp+8E0h+lpData], rax; lpData
0x180593adc  mov     rdx, rdi; lpValueName
0x180593adf  mov     [rbp+7E0h+var_688], r14w
0x180593ae7  call    cs:__imp_RegQueryValueExW
0x180593aed  test    eax, eax
0x180593aef  jnz     short loc_180593B2A
0x180593af1  lea     rax, [rsp+8E0h+Data]
0x180593af6  inc     rbx
0x180593af9  cmp     [rax+rbx*2], r14w
0x180593afe  jnz     short loc_180593AF6
0x180593b00  mov     r9d, [rsp+8E0h+Type]; dwType
0x180593b05  lea     eax, ds:2[rbx*2]
0x180593b0c  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593b11  xor     r8d, r8d; Reserved
0x180593b14  mov     dword ptr [rsp+8E0h+lpcbData], eax; cbData
0x180593b18  xor     edx, edx; lpValueName
0x180593b1a  lea     rax, [rsp+8E0h+Data]
0x180593b1f  mov     [rsp+8E0h+lpData], rax; lpData
0x180593b24  call    cs:__imp_RegSetValueExW
0x180593b2a  mov     r8d, r15d
0x180593b2d  lea     rdx, [rbp+7E0h+pszStart]
0x180593b34  lea     rcx, [rbp+7E0h+String2]
0x180593b3b  call    cs:__imp_SHExpandEnvironmentStringsW
0x180593b41  test    eax, eax
0x180593b43  jz      short loc_180593BA8
0x180593b45  xor     edx, edx; pszEnd
0x180593b47  lea     rcx, [rbp+7E0h+pszStart]; pszStart
0x180593b4e  lea     r8d, [rdx+2Ch]; wMatch
0x180593b52  call    cs:__imp_StrRChrW
0x180593b58  mov     rdi, rax
0x180593b5b  test    rax, rax
0x180593b5e  jz      short loc_180593BA8
0x180593b60  lea     rcx, [rax+2]; pszSrc
0x180593b64  call    cs:__imp_StrToIntW
0x180593b6a  xor     r8d, r8d
0x180593b6d  mov     [rdi], r14w
0x180593b71  mov     edx, eax
0x180593b73  lea     rcx, [rbp+7E0h+pszStart]
0x180593b7a  mov     ebx, eax
0x180593b7c  call    cs:__imp_SHELL32_LookupBackIconIndex
0x180593b82  xor     r8d, r8d; uFlags
0x180593b85  lea     rcx, [rbp+7E0h+pszStart]; pszHashItem
0x180593b8c  mov     r9d, eax; iImageIndex
0x180593b8f  mov     edx, ebx; iIndex
0x180593b91  call    SHUpdateImageW
0x180593b96  xor     r9d, r9d; dwItem2
0x180593b99  xor     r8d, r8d; dwItem1
0x180593b9c  mov     edx, 1000h; uFlags
0x180593ba1  xor     ecx, ecx; wEventId
0x180593ba3  call    SHChangeNotify
0x180593ba8  mov     rcx, [rsp+8E0h+hKey]; hKey
0x180593bad  test    rcx, rcx
0x180593bb0  jz      short loc_180593BB8
0x180593bb2  call    cs:__imp_RegCloseKey
0x180593bb8  mov     rcx, [rsp+8E0h+handle]; hKey
0x180593bbd  test    rcx, rcx
0x180593bc0  jz      short loc_180593BC8
  ... truncated ...
```
