# GetLocalManagedApplications

- ea: `0x180048410`
- end: `0x180048737`
- name: `GetLocalManagedApplications`
- size: `807`
- prototype: `DWORD __stdcall(BOOL bUserApps, LPDWORD pdwApps, PLOCALMANAGEDAPPLICATION *prgLocalApps)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180027f00`
- `0x180048410`
- `0x180048b00`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180048530`
- `KERNELBASE!LocalAlloc` at `0x180048530`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004846f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18004846f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048510`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048510`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800485d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800485d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800484aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004858f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800484aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004858f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800484c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048638`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800486ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048701`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800484c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048638`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800486ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048701`
- `KERNEL32!LocalFree` at `0x18004869d`
- `KERNEL32!LocalFree` at `0x1800486ae`
- `KERNEL32!LocalFree` at `0x1800486bf`
- `KERNEL32!LocalFree` at `0x1800486d7`
- `KERNEL32!LocalFree` at `0x18004869d`
- `KERNEL32!LocalFree` at `0x1800486ae`
- `KERNEL32!LocalFree` at `0x1800486bf`
- `KERNEL32!LocalFree` at `0x1800486d7`

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
0x180048410  mov     [rsp-8+arg_0], rbx
0x180048415  push    rbp
0x180048416  push    rsi
0x180048417  push    rdi
0x180048418  push    r12
0x18004841a  push    r13
0x18004841c  push    r14
0x18004841e  push    r15
0x180048420  lea     rbp, [rsp-27h]
0x180048425  sub     rsp, 100h
0x18004842c  mov     rax, cs:__security_cookie
0x180048433  xor     rax, rsp
0x180048436  mov     [rbp+57h+var_40], rax
0x18004843a  xor     r14d, r14d
0x18004843d  mov     r13, r8
0x180048440  mov     [rdx], r14d
0x180048443  mov     r12, rdx
0x180048446  mov     [r8], r14
0x180048449  mov     r15d, ecx
0x18004844c  mov     [rbp+57h+phkResult], r14
0x180048450  mov     ebx, 20019h
0x180048455  mov     [rbp+57h+hKey], r14
0x180048459  mov     [rbp+57h+var_C8], r14
0x18004845d  mov     [rbp+57h+cbData], r14d
0x180048461  mov     [rbp+57h+cSubKeys], r14d
0x180048465  test    ecx, ecx
0x180048467  jz      short loc_180048489
0x180048469  lea     rdx, [rbp+57h+phkResult]; phkResult
0x18004846d  mov     ecx, ebx; samDesired
0x18004846f  call    cs:__imp_RegOpenCurrentUser
0x180048476  nop     dword ptr [rax+rax+00h]
0x18004847b  test    eax, eax
0x18004847d  jnz     loc_18004870F
0x180048483  mov     rcx, [rbp+57h+phkResult]
0x180048487  jmp     short loc_180048494
0x180048489  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048490  mov     [rbp+57h+phkResult], rcx
0x180048494  lea     rax, [rbp+57h+hKey]
0x180048498  mov     r9d, ebx; samDesired
0x18004849b  xor     r8d, r8d; ulOptions
0x18004849e  mov     [rsp+130h+var_110], rax; phkResult
0x1800484a3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800484aa  call    cs:__imp_RegOpenKeyExW
0x1800484b1  nop     dword ptr [rax+rax+00h]
0x1800484b6  mov     ebx, eax
0x1800484b8  test    eax, eax
0x1800484ba  jz      short loc_1800484D8
0x1800484bc  test    r15d, r15d
0x1800484bf  jz      short loc_1800484D1
0x1800484c1  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800484c5  call    cs:__imp_RegCloseKey
0x1800484cc  nop     dword ptr [rax+rax+00h]
0x1800484d1  mov     eax, ebx
0x1800484d3  jmp     loc_18004870F
0x1800484d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800484dc  lea     rax, [rbp+57h+cSubKeys]
0x1800484e0  mov     [rsp+130h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800484e5  xor     r9d, r9d; lpReserved
0x1800484e8  mov     [rsp+130h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800484ed  xor     r8d, r8d; lpcchClass
0x1800484f0  mov     [rsp+130h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800484f5  xor     edx, edx; lpClass
0x1800484f7  mov     [rsp+130h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800484fc  mov     [rsp+130h+lpcValues], r14; lpcValues
0x180048501  mov     [rsp+130h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180048506  mov     [rsp+130h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18004850b  mov     [rsp+130h+var_110], rax; lpcSubKeys
0x180048510  call    cs:__imp_RegQueryInfoKeyW
0x180048517  nop     dword ptr [rax+rax+00h]
0x18004851c  mov     edi, eax
0x18004851e  test    eax, eax
0x180048520  jnz     loc_1800486E8
0x180048526  mov     edx, [rbp+57h+cSubKeys]
0x180048529  lea     ecx, [rax+40h]; uFlags
0x18004852c  shl     rdx, 5; uBytes
0x180048530  call    cs:__imp_LocalAlloc
0x180048537  nop     dword ptr [rax+rax+00h]
0x18004853c  mov     rsi, rax
0x18004853f  test    rax, rax
0x180048542  jz      loc_1800486E8
0x180048548  mov     eax, [rbp+57h+cSubKeys]
0x18004854b  mov     ebx, r14d
0x18004854e  test    eax, eax
0x180048550  jz      loc_180048658
0x180048556  mov     rcx, [rbp+57h+hKey]; hKey
0x18004855a  lea     r8, [rbp+57h+Name]; lpName
0x18004855e  mov     r9d, 2Ch ; ','; cchName
0x180048564  mov     edx, ebx; dwIndex
0x180048566  call    RegEnumKeyW
0x18004856b  mov     edi, eax
0x18004856d  test    eax, eax
0x18004856f  jnz     loc_18004868C
0x180048575  mov     rcx, [rbp+57h+hKey]; hKey
0x180048579  lea     rax, [rbp+57h+var_C8]
0x18004857d  mov     r9d, 20019h; samDesired
0x180048583  mov     [rsp+130h+var_110], rax; phkResult
0x180048588  xor     r8d, r8d; ulOptions
0x18004858b  lea     rdx, [rbp+57h+Name]; lpSubKey
0x18004858f  call    cs:__imp_RegOpenKeyExW
0x180048596  nop     dword ptr [rax+rax+00h]
0x18004859b  mov     edi, eax
0x18004859d  test    eax, eax
0x18004859f  jnz     loc_18004868C
0x1800485a5  lea     rcx, [rbp+57h+cbData]
0x1800485a9  mov     r14d, ebx
0x1800485ac  mov     [rsp+130h+lpcbMaxSubKeyLen], rcx; lpcbData
0x1800485b1  lea     rdx, aAppstate; "AppState"
0x1800485b8  mov     rcx, [rbp+57h+var_C8]; hKey
0x1800485bc  xor     r9d, r9d; lpType
0x1800485bf  shl     r14, 5
0x1800485c3  xor     r8d, r8d; lpReserved
0x1800485c6  add     r14, rsi
0x1800485c9  mov     [rbp+57h+cbData], 4
0x1800485d0  lea     rax, [r14+18h]
0x1800485d4  mov     [rsp+130h+var_110], rax; lpData
0x1800485d9  call    cs:__imp_RegQueryValueExW
0x1800485e0  nop     dword ptr [rax+rax+00h]
0x1800485e5  mov     edi, eax
0x1800485e7  test    eax, eax
0x1800485e9  jnz     short loc_180048634
0x1800485eb  mov     rcx, [rbp+57h+var_C8]; hKey
0x1800485ef  lea     rdx, aDeploymentName; "Deployment Name"
0x1800485f6  mov     r8, r14; unsigned __int16 **
0x1800485f9  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x1800485fe  mov     edi, eax
0x180048600  test    eax, eax
0x180048602  jnz     short loc_180048634
0x180048604  mov     rcx, [rbp+57h+var_C8]; hKey
0x180048608  lea     r8, [r14+8]; unsigned __int16 **
0x18004860c  lea     rdx, aGpoName; "GPO Name"
0x180048613  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180048618  mov     edi, eax
0x18004861a  test    eax, eax
0x18004861c  jnz     short loc_180048634
0x18004861e  mov     rcx, [rbp+57h+var_C8]; hKey
0x180048622  lea     r8, [r14+10h]; unsigned __int16 **
0x180048626  lea     rdx, aProductId; "Product ID"
0x18004862d  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180048632  mov     edi, eax
0x180048634  mov     rcx, [rbp+57h+var_C8]; hKey
0x180048638  call    cs:__imp_RegCloseKey
0x18004863f  nop     dword ptr [rax+rax+00h]
0x180048644  xor     r14d, r14d
0x180048647  test    edi, edi
0x180048649  jnz     short loc_18004868C
0x18004864b  mov     eax, [rbp+57h+cSubKeys]
0x18004864e  inc     ebx
0x180048650  cmp     ebx, eax
0x180048652  jb      loc_180048556
0x180048658  mov     [r13+0], rsi
0x18004865c  mov     [r12], eax
0x180048660  mov     rcx, [rbp+57h+hKey]; hKey
0x180048664  call    cs:__imp_RegCloseKey
0x18004866b  nop     dword ptr [rax+rax+00h]
0x180048670  test    r15d, r15d
0x180048673  jz      short loc_180048685
0x180048675  mov     rcx, [rbp+57h+phkResult]; hKey
0x180048679  call    cs:__imp_RegCloseKey
0x180048680  nop     dword ptr [rax+rax+00h]
0x180048685  mov     eax, edi
0x180048687  jmp     loc_18004870F
0x18004868c  cmp     [rbp+57h+cSubKeys], 0
0x180048690  jbe     short loc_1800486D4
0x180048692  mov     ebx, r14d
0x180048695  shl     rbx, 5
0x180048699  mov     rcx, [rbx+rsi]; hMem
0x18004869d  call    cs:__imp_LocalFree
0x1800486a4  nop     dword ptr [rax+rax+00h]
0x1800486a9  mov     rcx, [rbx+rsi+8]; hMem
0x1800486ae  call    cs:__imp_LocalFree
0x1800486b5  nop     dword ptr [rax+rax+00h]
0x1800486ba  mov     rcx, [rbx+rsi+10h]; hMem
0x1800486bf  call    cs:__imp_LocalFree
0x1800486c6  nop     dword ptr [rax+rax+00h]
0x1800486cb  inc     r14d
0x1800486ce  cmp     r14d, [rbp+57h+cSubKeys]
0x1800486d2  jb      short loc_180048692
0x1800486d4  mov     rcx, rsi; hMem
0x1800486d7  call    cs:__imp_LocalFree
0x1800486de  nop     dword ptr [rax+rax+00h]
0x1800486e3  jmp     loc_180048660
0x1800486e8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800486ec  call    cs:__imp_RegCloseKey
0x1800486f3  nop     dword ptr [rax+rax+00h]
0x1800486f8  test    r15d, r15d
0x1800486fb  jz      short loc_18004870D
0x1800486fd  mov     rcx, [rbp+57h+phkResult]; hKey
0x180048701  call    cs:__imp_RegCloseKey
0x180048708  nop     dword ptr [rax+rax+00h]
0x18004870d  xor     eax, eax
0x18004870f  mov     rcx, [rbp+57h+var_40]
0x180048713  xor     rcx, rsp; StackCookie
0x180048716  call    __security_check_cookie
0x18004871b  mov     rbx, [rsp+130h+arg_0]
0x180048723  add     rsp, 100h
0x18004872a  pop     r15
0x18004872c  pop     r14
0x18004872e  pop     r13
0x180048730  pop     r12
0x180048732  pop     rdi
0x180048733  pop     rsi
0x180048734  pop     rbp
0x180048735  retn
```
