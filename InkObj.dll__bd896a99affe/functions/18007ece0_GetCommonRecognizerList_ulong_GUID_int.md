# GetCommonRecognizerList(ulong *,_GUID *,int)

- ea: `0x18007ece0`
- end: `0x18007eede`
- name: `?GetCommonRecognizerList@@YAJPEAKPEAU_GUID@@H@Z`
- size: `510`
- prototype: `__int64 __fastcall(unsigned int *, struct _GUID *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a2b0`
- `0x18007e640`
- `0x18007eee4`
- `0x18007f168`

## callees

- `0x18007ece0`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ed6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ed6b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007edf7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007ee93`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007edf7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18007ee93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ed85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eda0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ed85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eda0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007eead`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ee18`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007ee18`

## pseudocode

```c
__int64 __fastcall GetCommonRecognizerList(unsigned int *a1, struct _GUID *a2, int a3)
{
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  LSTATUS v8; // ebx
  unsigned int v9; // edi
  DWORD v10; // r12d
  HRESULT v11; // r14d
  LSTATUS v12; // eax
  unsigned int v13; // eax
  HKEY v14; // rcx
  DWORD cchName; // [rsp+40h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-51h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-49h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-41h] BYREF
  WCHAR Name[40]; // [rsp+70h] [rbp-29h] BYREF

  cchName = 80;
  ftLastWriteTime = 0;
  hKey = 0;
  pclsid = 0;
  if ( !a1 )
    return 2147500035LL;
  v6 = L"Software\\Microsoft\\TPG\\System Recognizers";
  if ( !a3 )
    v6 = L"Software\\Microsoft\\TPG\\Recognizers";
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      *a1 = 0;
    }
    else if ( hKey )
    {
      RegCloseKey(hKey);
    }
    return 2147746357LL;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    do
    {
      if ( a2 && v9 >= *a1 )
        break;
      cchName = 40;
      v12 = RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      v8 = v12;
      if ( v12 == 259 )
        break;
      if ( !v12 && cchName <= 0x28 )
      {
        v11 = CLSIDFromString(Name, &pclsid);
        if ( v11 >= 0 )
        {
          v13 = v9++;
          if ( a2 )
          {
            if ( v9 <= *a1 )
              a2[v13] = pclsid;
          }
        }
      }
      ++v10;
    }
    while ( !v8 );
    if ( v8 != 259 )
    {
      if ( a2 )
      {
        cchName = 40;
        if ( RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, &ftLastWriteTime) != 259 )
          v11 = 262738;
      }
    }
    v14 = hKey;
    *a1 = v9;
    RegCloseKey(v14);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18007ece0  mov     [rsp-8+arg_10], rbx
0x18007ece5  mov     [rsp-8+arg_18], rsi
0x18007ecea  push    rbp
0x18007eceb  push    rdi
0x18007ecec  push    r12
0x18007ecee  push    r14
0x18007ecf0  push    r15
0x18007ecf2  lea     rbp, [rsp-37h]
0x18007ecf7  sub     rsp, 0D0h
0x18007ecfe  mov     rax, cs:__security_cookie
0x18007ed05  xor     rax, rsp
0x18007ed08  mov     [rbp+57h+var_30], rax
0x18007ed0c  mov     [rbp+57h+cchName], 50h ; 'P'
0x18007ed13  xorps   xmm0, xmm0
0x18007ed16  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], 0
0x18007ed1e  mov     r15, rdx
0x18007ed21  mov     [rbp+57h+hKey], 0
0x18007ed29  mov     rsi, rcx
0x18007ed2c  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18007ed30  test    rcx, rcx
0x18007ed33  jnz     short loc_18007ED3F
0x18007ed35  mov     eax, 80004003h
0x18007ed3a  jmp     loc_18007EEB6
0x18007ed3f  lea     rax, [rbp+57h+hKey]
0x18007ed43  mov     r9d, 20019h; samDesired
0x18007ed49  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18007ed4e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ed55  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\TPG\\System Recogn"...
0x18007ed5c  test    r8d, r8d
0x18007ed5f  jnz     short loc_18007ED68
0x18007ed61  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\TPG\\Recognizers"
0x18007ed68  xor     r8d, r8d; ulOptions
0x18007ed6b  call    cs:__imp_RegOpenKeyExW
0x18007ed71  mov     ebx, eax
0x18007ed73  test    eax, eax
0x18007ed75  jz      short loc_18007EDA8
0x18007ed77  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ed7b  cmp     eax, 2
0x18007ed7e  jnz     short loc_18007ED9B
0x18007ed80  test    rcx, rcx
0x18007ed83  jz      short loc_18007ED8B
0x18007ed85  call    cs:__imp_RegCloseKey
0x18007ed8b  mov     dword ptr [rsi], 0
0x18007ed91  mov     eax, 80040235h
0x18007ed96  jmp     loc_18007EEB6
0x18007ed9b  test    rcx, rcx
0x18007ed9e  jz      short loc_18007ED91
0x18007eda0  call    cs:__imp_RegCloseKey
0x18007eda6  jmp     short loc_18007ED91
0x18007eda8  xor     edi, edi
0x18007edaa  xor     r12d, r12d
0x18007edad  xor     r14d, r14d
0x18007edb0  test    r15, r15
0x18007edb3  jz      short loc_18007EDBD
0x18007edb5  cmp     edi, [rsi]
0x18007edb7  jnb     loc_18007EE4C
0x18007edbd  mov     rcx, [rbp+57h+hKey]; hKey
0x18007edc1  lea     rax, [rbp+57h+ftLastWriteTime]
0x18007edc5  mov     [rsp+0F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007edca  lea     r9, [rbp+57h+cchName]; lpcchName
0x18007edce  mov     [rsp+0F0h+lpcchClass], 0; lpcchClass
0x18007edd7  lea     r8, [rbp+57h+Name]; lpName
0x18007eddb  mov     [rsp+0F0h+lpClass], 0; lpClass
0x18007ede4  mov     edx, r12d; dwIndex
0x18007ede7  mov     [rsp+0F0h+phkResult], 0; lpReserved
0x18007edf0  mov     [rbp+57h+cchName], 28h ; '('
0x18007edf7  call    cs:__imp_RegEnumKeyExW
0x18007edfd  mov     ebx, eax
0x18007edff  cmp     eax, 103h
0x18007ee04  jz      short loc_18007EE4C
0x18007ee06  test    eax, eax
0x18007ee08  jnz     short loc_18007EE41
0x18007ee0a  cmp     [rbp+57h+cchName], 28h ; '('
0x18007ee0e  ja      short loc_18007EE41
0x18007ee10  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18007ee14  lea     rcx, [rbp+57h+Name]; lpsz
0x18007ee18  call    cs:__imp_CLSIDFromString
0x18007ee1e  mov     r14d, eax
0x18007ee21  test    eax, eax
0x18007ee23  js      short loc_18007EE41
0x18007ee25  mov     eax, edi
0x18007ee27  inc     edi
0x18007ee29  test    r15, r15
0x18007ee2c  jz      short loc_18007EE41
0x18007ee2e  cmp     edi, [rsi]
0x18007ee30  ja      short loc_18007EE41
0x18007ee32  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18007ee36  mov     ecx, eax
0x18007ee38  add     rcx, rcx
0x18007ee3b  movdqu  xmmword ptr [r15+rcx*8], xmm0
0x18007ee41  inc     r12d
0x18007ee44  test    ebx, ebx
0x18007ee46  jz      loc_18007EDB0
0x18007ee4c  cmp     ebx, 103h
0x18007ee52  jz      short loc_18007EEA7
0x18007ee54  test    r15, r15
0x18007ee57  jz      short loc_18007EEA7
0x18007ee59  mov     rcx, [rbp+57h+hKey]; hKey
0x18007ee5d  lea     rax, [rbp+57h+ftLastWriteTime]
0x18007ee61  mov     [rsp+0F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007ee66  lea     r9, [rbp+57h+cchName]; lpcchName
0x18007ee6a  mov     [rsp+0F0h+lpcchClass], 0; lpcchClass
0x18007ee73  lea     r8, [rbp+57h+Name]; lpName
0x18007ee77  mov     [rsp+0F0h+lpClass], 0; lpClass
0x18007ee80  mov     edx, r12d; dwIndex
0x18007ee83  mov     [rsp+0F0h+phkResult], 0; lpReserved
0x18007ee8c  mov     [rbp+57h+cchName], 28h ; '('
0x18007ee93  call    cs:__imp_RegEnumKeyExW
0x18007ee99  cmp     eax, 103h
0x18007ee9e  mov     ecx, 40252h
0x18007eea3  cmovnz  r14d, ecx
0x18007eea7  mov     rcx, [rbp+57h+hKey]; hKey
0x18007eeab  mov     [rsi], edi
0x18007eead  call    cs:__imp_RegCloseKey
0x18007eeb3  mov     eax, r14d
0x18007eeb6  mov     rcx, [rbp+57h+var_30]
0x18007eeba  xor     rcx, rsp; StackCookie
0x18007eebd  call    __security_check_cookie
0x18007eec2  lea     r11, [rsp+0F0h+var_20]
0x18007eeca  mov     rbx, [r11+40h]
0x18007eece  mov     rsi, [r11+48h]
0x18007eed2  mov     rsp, r11
0x18007eed5  pop     r15
0x18007eed7  pop     r14
0x18007eed9  pop     r12
0x18007eedb  pop     rdi
0x18007eedc  pop     rbp
0x18007eedd  retn
```
