# CW32System::SkipObjectData(void)

- ea: `0x180205278`
- end: `0x1802054d9`
- name: `?SkipObjectData@CW32System@@SAHXZ`
- size: `609`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c820`

## callees

- `0x18013bad0`
- `0x18013bf10`
- `0x180148134`
- `0x180205278`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802052c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802052c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180205369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020543e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180205369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18020543e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802054a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802054ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802054a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802054ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802053ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802053ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180205480`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180205480`

## string_xrefs

- `0x18020535b`: `Software\Microsoft\Office\12.0\Common\ObjectBlocking`

## pseudocode

```c
__int64 CW32System::SkipObjectData(void)
{
  DWORD ModuleFileNameW; // eax
  int v1; // ebx
  WCHAR *v2; // rdi
  DWORD i; // esi
  DWORD v5; // ecx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( CW32System::_fCheckExe )
    return CW32System::_fSkipObjectData;
  CW32System::_fCheckExe = 1;
  CW32System::_fSkipObjectData = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return CW32System::_fSkipObjectData;
  v1 = 1;
  v2 = &Filename[ModuleFileNameW];
  if ( 2LL * ModuleFileNameW )
  {
    while ( *v2 != 92 )
    {
      --v2;
      ++v1;
      if ( v2 == Filename )
        goto LABEL_6;
    }
    goto LABEL_7;
  }
LABEL_6:
  if ( *v2 == 92 )
  {
LABEL_7:
    --v1;
    ++v2;
  }
  if ( v1 == 12 )
  {
    if ( !CW32System::lstrcmpi(v2, L"OUTLOOK.EXE") )
    {
      CW32System::_fSkipObjectData = 1;
      return 1;
    }
    goto LABEL_12;
  }
  if ( v1 )
  {
LABEL_12:
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Office\\12.0\\Common\\ObjectBlocking", 0, 9u, &hKey) )
    {
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        Name[0] = 0;
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        v5 = cchName;
        if ( !cchName )
          break;
        if ( cchName > 0x103 )
        {
          v5 = 259;
          cchName = 259;
        }
        if ( 2 * (unsigned __int64)v5 >= 0x208 )
          _report_rangecheckfailure();
        Name[v5] = 0;
        if ( v5 + 1 == v1 && !CW32System::lstrcmpi(v2, Name) )
        {
          phkResult = 0;
          CW32System::_fSkipObjectData = 1;
          if ( !RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult) )
          {
            Type = 0;
            *(_DWORD *)Data = 0;
            cbData = 4;
            if ( !RegQueryValueExW(phkResult, L"SkipObjects", 0, &Type, Data, &cbData) )
              CW32System::_fSkipObjectData = Data[0] & 1;
          }
          if ( phkResult )
            RegCloseKey(phkResult);
          break;
        }
      }
      RegCloseKey(hKey);
    }
  }
  return CW32System::_fSkipObjectData;
}

```

## disassembly

```asm
0x180205278  push    rbp
0x18020527a  push    rbx
0x18020527b  push    rsi
0x18020527c  push    rdi
0x18020527d  lea     rbp, [rsp-398h]
0x180205285  sub     rsp, 498h
0x18020528c  mov     rax, cs:__security_cookie
0x180205293  xor     rax, rsp
0x180205296  mov     [rbp+3B0h+var_30], rax
0x18020529d  cmp     cs:?_fCheckExe@CW32System@@2EA, 0; uchar CW32System::_fCheckExe
0x1802052a4  jnz     loc_1802054B1
0x1802052aa  mov     r8d, 104h; nSize
0x1802052b0  mov     cs:?_fCheckExe@CW32System@@2EA, 1; uchar CW32System::_fCheckExe
0x1802052b7  lea     rdx, [rbp+3B0h+Filename]; lpFilename
0x1802052be  mov     cs:?_fSkipObjectData@CW32System@@2EA, 0; uchar CW32System::_fSkipObjectData
0x1802052c5  xor     ecx, ecx; hModule
0x1802052c7  call    cs:__imp_GetModuleFileNameW
0x1802052cd  test    eax, eax
0x1802052cf  jz      loc_1802054B1
0x1802052d5  mov     eax, eax
0x1802052d7  lea     rdi, [rbp+3B0h+Filename]
0x1802052de  add     rax, rax
0x1802052e1  mov     ebx, 1
0x1802052e6  lea     rdi, [rdi+rax]
0x1802052ea  jz      short loc_180205304
0x1802052ec  cmp     word ptr [rdi], 5Ch ; '\'
0x1802052f0  jz      short loc_18020530A
0x1802052f2  sub     rdi, 2
0x1802052f6  lea     rax, [rbp+3B0h+Filename]
0x1802052fd  inc     ebx
0x1802052ff  cmp     rdi, rax
0x180205302  jnz     short loc_1802052EC
0x180205304  cmp     word ptr [rdi], 5Ch ; '\'
0x180205308  jnz     short loc_180205310
0x18020530a  dec     ebx
0x18020530c  add     rdi, 2
0x180205310  cmp     ebx, 0Ch
0x180205313  jnz     short loc_180205337
0x180205315  lea     rdx, aOutlookExe; "OUTLOOK.EXE"
0x18020531c  mov     rcx, rdi; unsigned __int16 *
0x18020531f  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180205324  test    eax, eax
0x180205326  jnz     short loc_18020533F
0x180205328  mov     cs:?_fSkipObjectData@CW32System@@2EA, 1; uchar CW32System::_fSkipObjectData
0x18020532f  lea     eax, [rbx-0Bh]
0x180205332  jmp     loc_1802054B8
0x180205337  test    ebx, ebx
0x180205339  jz      loc_1802054B1
0x18020533f  lea     rax, [rsp+4B0h+hKey]
0x180205344  mov     [rsp+4B0h+hKey], 0
0x18020534d  mov     r9d, 9; samDesired
0x180205353  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180205358  xor     r8d, r8d; ulOptions
0x18020535b  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Office\\12.0\\Comm"...
0x180205362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180205369  call    cs:__imp_RegOpenKeyExW
0x18020536f  test    eax, eax
0x180205371  jnz     loc_1802054B1
0x180205377  xor     esi, esi
0x180205379  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18020537e  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x180205383  xor     eax, eax
0x180205385  mov     [rsp+4B0h+cchName], 104h
0x18020538d  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180205392  lea     r8, [rsp+4B0h+Name]; lpName
0x180205397  mov     [rsp+4B0h+lpcchClass], rax; lpcchClass
0x18020539c  mov     edx, esi; dwIndex
0x18020539e  mov     [rsp+4B0h+lpClass], rax; lpClass
0x1802053a3  mov     [rsp+4B0h+phkResult], rax; lpReserved
0x1802053a8  mov     [rsp+4B0h+Name], ax
0x1802053ad  call    cs:__imp_RegEnumKeyExW
0x1802053b3  test    eax, eax
0x1802053b5  jnz     loc_1802054A6
0x1802053bb  mov     ecx, [rsp+4B0h+cchName]
0x1802053bf  test    ecx, ecx
0x1802053c1  jz      loc_1802054A6
0x1802053c7  cmp     ecx, 103h
0x1802053cd  jbe     short loc_1802053D8
0x1802053cf  mov     ecx, 103h
0x1802053d4  mov     [rsp+4B0h+cchName], ecx
0x1802053d8  mov     eax, ecx
0x1802053da  lea     rdx, [rax+rax]
0x1802053de  cmp     rdx, 208h
0x1802053e5  jnb     loc_1802054D3
0x1802053eb  xor     eax, eax
0x1802053ed  mov     [rsp+rdx+4B0h+Name], ax
0x1802053f2  lea     eax, [rcx+1]
0x1802053f5  cmp     eax, ebx
0x1802053f7  jnz     short loc_18020540A
0x1802053f9  lea     rdx, [rsp+4B0h+Name]; unsigned __int16 *
0x1802053fe  mov     rcx, rdi; unsigned __int16 *
0x180205401  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180205406  test    eax, eax
0x180205408  jz      short loc_180205411
0x18020540a  inc     esi
0x18020540c  jmp     loc_180205379
0x180205411  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180205416  lea     rax, [rsp+4B0h+var_458]
0x18020541b  mov     r9d, 1; samDesired
0x180205421  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180205426  xor     r8d, r8d; ulOptions
0x180205429  mov     [rsp+4B0h+var_458], 0
0x180205432  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x180205437  mov     cs:?_fSkipObjectData@CW32System@@2EA, 1; uchar CW32System::_fSkipObjectData
0x18020543e  call    cs:__imp_RegOpenKeyExW
0x180205444  test    eax, eax
0x180205446  jnz     short loc_180205496
0x180205448  mov     rcx, [rsp+4B0h+var_458]; hKey
0x18020544d  lea     r9, [rsp+4B0h+Type]; lpType
0x180205452  mov     [rsp+4B0h+Type], eax
0x180205456  lea     rdx, aSkipobjects; "SkipObjects"
0x18020545d  mov     dword ptr [rsp+4B0h+Data], eax
0x180205461  xor     r8d, r8d; lpReserved
0x180205464  lea     rax, [rsp+4B0h+cbData]
0x180205469  mov     [rsp+4B0h+cbData], 4
0x180205471  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x180205476  lea     rax, [rsp+4B0h+Data]
0x18020547b  mov     [rsp+4B0h+phkResult], rax; lpData
0x180205480  call    cs:__imp_RegQueryValueExW
0x180205486  test    eax, eax
0x180205488  jnz     short loc_180205496
0x18020548a  mov     al, [rsp+4B0h+Data]
0x18020548e  and     al, 1
0x180205490  mov     cs:?_fSkipObjectData@CW32System@@2EA, al; uchar CW32System::_fSkipObjectData
0x180205496  mov     rcx, [rsp+4B0h+var_458]; hKey
0x18020549b  test    rcx, rcx
0x18020549e  jz      short loc_1802054A6
0x1802054a0  call    cs:__imp_RegCloseKey
0x1802054a6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1802054ab  call    cs:__imp_RegCloseKey
0x1802054b1  movzx   eax, cs:?_fSkipObjectData@CW32System@@2EA; uchar CW32System::_fSkipObjectData
0x1802054b8  mov     rcx, [rbp+3B0h+var_30]
0x1802054bf  xor     rcx, rsp; StackCookie
0x1802054c2  call    __security_check_cookie
0x1802054c7  add     rsp, 498h
0x1802054ce  pop     rdi
0x1802054cf  pop     rsi
0x1802054d0  pop     rbx
0x1802054d1  pop     rbp
0x1802054d2  retn
0x1802054d3  call    __report_rangecheckfailure
```
