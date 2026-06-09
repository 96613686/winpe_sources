# GetLocalManagedApplications

- ea: `0x180042f80`
- end: `0x180043240`
- name: `GetLocalManagedApplications`
- size: `704`
- prototype: `DWORD __stdcall(BOOL bUserApps, LPDWORD pdwApps, PLOCALMANAGEDAPPLICATION *prgLocalApps)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180025af0`
- `0x180042f80`
- `0x18004357c`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180043088`
- `KERNELBASE!LocalAlloc` at `0x180043088`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180042fdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180042fdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004306e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004306e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043125`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043125`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043014`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800430e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043014`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800430e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043029`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004317e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043029`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004317e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043211`
- `KERNEL32!LocalFree` at `0x1800431ce`
- `KERNEL32!LocalFree` at `0x1800431d9`
- `KERNEL32!LocalFree` at `0x1800431e4`
- `KERNEL32!LocalFree` at `0x1800431f6`
- `KERNEL32!LocalFree` at `0x1800431ce`
- `KERNEL32!LocalFree` at `0x1800431d9`
- `KERNEL32!LocalFree` at `0x1800431e4`
- `KERNEL32!LocalFree` at `0x1800431f6`

## pseudocode

```c
DWORD __stdcall GetLocalManagedApplications(BOOL bUserApps, LPDWORD pdwApps, PLOCALMANAGEDAPPLICATION *prgLocalApps)
{
  DWORD v3; // r14d
  DWORD result; // eax
  HKEY v8; // rcx
  LSTATUS v9; // ebx
  LSTATUS Value; // edi
  struct _LOCALMANAGEDAPPLICATION *v11; // rsi
  DWORD v12; // eax
  DWORD v13; // ebx
  struct _LOCALMANAGEDAPPLICATION *v14; // r14
  __int64 v15; // rbx
  DWORD cSubKeys; // [rsp+60h] [rbp-79h] BYREF
  HKEY v17; // [rsp+68h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-61h] BYREF
  DWORD cbData[4]; // [rsp+80h] [rbp-59h] BYREF
  WCHAR Name[48]; // [rsp+90h] [rbp-49h] BYREF

  v3 = 0;
  *pdwApps = 0;
  *prgLocalApps = 0;
  phkResult = 0;
  hKey = 0;
  v17 = 0;
  cbData[0] = 0;
  cSubKeys = 0;
  if ( bUserApps )
  {
    result = RegOpenCurrentUser(0x20019u, &phkResult);
    if ( result )
      return result;
    v8 = phkResult;
  }
  else
  {
    v8 = HKEY_LOCAL_MACHINE;
    phkResult = HKEY_LOCAL_MACHINE;
  }
  v9 = RegOpenKeyExW(v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Appmgmt", 0, 0x20019u, &hKey);
  if ( v9 )
  {
    if ( bUserApps )
      RegCloseKey(phkResult);
    return v9;
  }
  else
  {
    Value = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( Value || (v11 = (struct _LOCALMANAGEDAPPLICATION *)LocalAlloc(0x40u, 32LL * cSubKeys)) == 0 )
    {
      RegCloseKey(hKey);
      if ( bUserApps )
        RegCloseKey(phkResult);
      return 0;
    }
    else
    {
      v12 = cSubKeys;
      v13 = 0;
      if ( cSubKeys )
      {
        while ( 1 )
        {
          Value = RegEnumKeyW(hKey, v13, Name, 0x2Cu);
          if ( Value )
            break;
          Value = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v17);
          if ( Value )
            break;
          v14 = &v11[v13];
          cbData[0] = 4;
          Value = RegQueryValueExW(v17, L"AppState", 0, 0, (LPBYTE)&v14->dwState, cbData);
          if ( !Value )
          {
            Value = ReadStringValue(v17, L"Deployment Name", &v14->pszDeploymentName);
            if ( !Value )
            {
              Value = ReadStringValue(v17, L"GPO Name", &v14->pszPolicyName);
              if ( !Value )
                Value = ReadStringValue(v17, L"Product ID", &v14->pszProductId);
            }
          }
          RegCloseKey(v17);
          v3 = 0;
          if ( Value )
            break;
          v12 = cSubKeys;
          if ( ++v13 >= cSubKeys )
            goto LABEL_20;
        }
        if ( cSubKeys )
        {
          do
          {
            v15 = v3;
            LocalFree(v11[v15].pszDeploymentName);
            LocalFree(v11[v15].pszPolicyName);
            LocalFree(v11[v15].pszProductId);
            ++v3;
          }
          while ( v3 < cSubKeys );
        }
        LocalFree(v11);
      }
      else
      {
LABEL_20:
        *prgLocalApps = v11;
        *pdwApps = v12;
      }
      RegCloseKey(hKey);
      if ( bUserApps )
        RegCloseKey(phkResult);
      return Value;
    }
  }
}

```

## disassembly

```asm
0x180042f80  mov     [rsp-8+arg_0], rbx
0x180042f85  push    rbp
0x180042f86  push    rsi
0x180042f87  push    rdi
0x180042f88  push    r12
0x180042f8a  push    r13
0x180042f8c  push    r14
0x180042f8e  push    r15
0x180042f90  lea     rbp, [rsp-27h]
0x180042f95  sub     rsp, 100h
0x180042f9c  mov     rax, cs:__security_cookie
0x180042fa3  xor     rax, rsp
0x180042fa6  mov     [rbp+57h+var_40], rax
0x180042faa  xor     r14d, r14d
0x180042fad  mov     r13, r8
0x180042fb0  mov     [rdx], r14d
0x180042fb3  mov     r12, rdx
0x180042fb6  mov     [r8], r14
0x180042fb9  mov     r15d, ecx
0x180042fbc  mov     [rbp+57h+phkResult], r14
0x180042fc0  mov     ebx, 20019h
0x180042fc5  mov     [rbp+57h+hKey], r14
0x180042fc9  mov     [rbp+57h+var_C8], r14
0x180042fcd  mov     [rbp+57h+cbData], r14d
0x180042fd1  mov     [rbp+57h+cSubKeys], r14d
0x180042fd5  test    ecx, ecx
0x180042fd7  jz      short loc_180042FF3
0x180042fd9  lea     rdx, [rbp+57h+phkResult]; phkResult
0x180042fdd  mov     ecx, ebx; samDesired
0x180042fdf  call    cs:__imp_RegOpenCurrentUser
0x180042fe5  test    eax, eax
0x180042fe7  jnz     loc_180043219
0x180042fed  mov     rcx, [rbp+57h+phkResult]
0x180042ff1  jmp     short loc_180042FFE
0x180042ff3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042ffa  mov     [rbp+57h+phkResult], rcx
0x180042ffe  lea     rax, [rbp+57h+hKey]
0x180043002  mov     r9d, ebx; samDesired
0x180043005  xor     r8d, r8d; ulOptions
0x180043008  mov     [rsp+130h+var_110], rax; phkResult
0x18004300d  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180043014  call    cs:__imp_RegOpenKeyExW
0x18004301a  mov     ebx, eax
0x18004301c  test    eax, eax
0x18004301e  jz      short loc_180043036
0x180043020  test    r15d, r15d
0x180043023  jz      short loc_18004302F
0x180043025  mov     rcx, [rbp+57h+phkResult]; hKey
0x180043029  call    cs:__imp_RegCloseKey
0x18004302f  mov     eax, ebx
0x180043031  jmp     loc_180043219
0x180043036  mov     rcx, [rbp+57h+hKey]; hKey
0x18004303a  lea     rax, [rbp+57h+cSubKeys]
0x18004303e  mov     [rsp+130h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180043043  xor     r9d, r9d; lpReserved
0x180043046  mov     [rsp+130h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18004304b  xor     r8d, r8d; lpcchClass
0x18004304e  mov     [rsp+130h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180043053  xor     edx, edx; lpClass
0x180043055  mov     [rsp+130h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18004305a  mov     [rsp+130h+lpcValues], r14; lpcValues
0x18004305f  mov     [rsp+130h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180043064  mov     [rsp+130h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180043069  mov     [rsp+130h+var_110], rax; lpcSubKeys
0x18004306e  call    cs:__imp_RegQueryInfoKeyW
0x180043074  mov     edi, eax
0x180043076  test    eax, eax
0x180043078  jnz     loc_1800431FE
0x18004307e  mov     edx, [rbp+57h+cSubKeys]
0x180043081  lea     ecx, [rax+40h]; uFlags
0x180043084  shl     rdx, 5; uBytes
0x180043088  call    cs:__imp_LocalAlloc
0x18004308e  mov     rsi, rax
0x180043091  test    rax, rax
0x180043094  jz      loc_1800431FE
0x18004309a  mov     eax, [rbp+57h+cSubKeys]
0x18004309d  mov     ebx, r14d
0x1800430a0  test    eax, eax
0x1800430a2  jz      loc_180043198
0x1800430a8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800430ac  lea     r8, [rbp+57h+Name]; lpName
0x1800430b0  mov     r9d, 2Ch ; ','; cchName
0x1800430b6  mov     edx, ebx; dwIndex
0x1800430b8  call    RegEnumKeyW
0x1800430bd  mov     edi, eax
0x1800430bf  test    eax, eax
0x1800430c1  jnz     loc_1800431BD
0x1800430c7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800430cb  lea     rax, [rbp+57h+var_C8]
0x1800430cf  mov     r9d, 20019h; samDesired
0x1800430d5  mov     [rsp+130h+var_110], rax; phkResult
0x1800430da  xor     r8d, r8d; ulOptions
0x1800430dd  lea     rdx, [rbp+57h+Name]; lpSubKey
0x1800430e1  call    cs:__imp_RegOpenKeyExW
0x1800430e7  mov     edi, eax
0x1800430e9  test    eax, eax
0x1800430eb  jnz     loc_1800431BD
0x1800430f1  lea     rcx, [rbp+57h+cbData]
0x1800430f5  mov     r14d, ebx
0x1800430f8  mov     [rsp+130h+lpcbMaxSubKeyLen], rcx; lpcbData
0x1800430fd  lea     rdx, aAppstate; "AppState"
0x180043104  mov     rcx, [rbp+57h+var_C8]; hKey
0x180043108  xor     r9d, r9d; lpType
0x18004310b  shl     r14, 5
0x18004310f  xor     r8d, r8d; lpReserved
0x180043112  add     r14, rsi
0x180043115  mov     [rbp+57h+cbData], 4
0x18004311c  lea     rax, [r14+18h]
0x180043120  mov     [rsp+130h+var_110], rax; lpData
0x180043125  call    cs:__imp_RegQueryValueExW
0x18004312b  mov     edi, eax
0x18004312d  test    eax, eax
0x18004312f  jnz     short loc_18004317A
0x180043131  mov     rcx, [rbp+57h+var_C8]; hKey
0x180043135  lea     rdx, aDeploymentName; "Deployment Name"
0x18004313c  mov     r8, r14; unsigned __int16 **
0x18004313f  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180043144  mov     edi, eax
0x180043146  test    eax, eax
0x180043148  jnz     short loc_18004317A
0x18004314a  mov     rcx, [rbp+57h+var_C8]; hKey
0x18004314e  lea     r8, [r14+8]; unsigned __int16 **
0x180043152  lea     rdx, aGpoName; "GPO Name"
0x180043159  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x18004315e  mov     edi, eax
0x180043160  test    eax, eax
0x180043162  jnz     short loc_18004317A
0x180043164  mov     rcx, [rbp+57h+var_C8]; hKey
0x180043168  lea     r8, [r14+10h]; unsigned __int16 **
0x18004316c  lea     rdx, aProductId; "Product ID"
0x180043173  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180043178  mov     edi, eax
0x18004317a  mov     rcx, [rbp+57h+var_C8]; hKey
0x18004317e  call    cs:__imp_RegCloseKey
0x180043184  xor     r14d, r14d
0x180043187  test    edi, edi
0x180043189  jnz     short loc_1800431BD
0x18004318b  mov     eax, [rbp+57h+cSubKeys]
0x18004318e  inc     ebx
0x180043190  cmp     ebx, eax
0x180043192  jb      loc_1800430A8
0x180043198  mov     [r13+0], rsi
0x18004319c  mov     [r12], eax
0x1800431a0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800431a4  call    cs:__imp_RegCloseKey
0x1800431aa  test    r15d, r15d
0x1800431ad  jz      short loc_1800431B9
0x1800431af  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800431b3  call    cs:__imp_RegCloseKey
0x1800431b9  mov     eax, edi
0x1800431bb  jmp     short loc_180043219
0x1800431bd  cmp     [rbp+57h+cSubKeys], 0
0x1800431c1  jbe     short loc_1800431F3
0x1800431c3  mov     ebx, r14d
0x1800431c6  shl     rbx, 5
0x1800431ca  mov     rcx, [rbx+rsi]; hMem
0x1800431ce  call    cs:__imp_LocalFree
0x1800431d4  mov     rcx, [rbx+rsi+8]; hMem
0x1800431d9  call    cs:__imp_LocalFree
0x1800431df  mov     rcx, [rbx+rsi+10h]; hMem
0x1800431e4  call    cs:__imp_LocalFree
0x1800431ea  inc     r14d
0x1800431ed  cmp     r14d, [rbp+57h+cSubKeys]
0x1800431f1  jb      short loc_1800431C3
0x1800431f3  mov     rcx, rsi; hMem
0x1800431f6  call    cs:__imp_LocalFree
0x1800431fc  jmp     short loc_1800431A0
0x1800431fe  mov     rcx, [rbp+57h+hKey]; hKey
0x180043202  call    cs:__imp_RegCloseKey
0x180043208  test    r15d, r15d
0x18004320b  jz      short loc_180043217
0x18004320d  mov     rcx, [rbp+57h+phkResult]; hKey
0x180043211  call    cs:__imp_RegCloseKey
0x180043217  xor     eax, eax
0x180043219  mov     rcx, [rbp+57h+var_40]
0x18004321d  xor     rcx, rsp; StackCookie
0x180043220  call    __security_check_cookie
0x180043225  mov     rbx, [rsp+130h+arg_0]
0x18004322d  add     rsp, 100h
0x180043234  pop     r15
0x180043236  pop     r14
0x180043238  pop     r13
0x18004323a  pop     r12
0x18004323c  pop     rdi
0x18004323d  pop     rsi
0x18004323e  pop     rbp
0x18004323f  retn
```
