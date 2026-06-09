# FindCreateOrDeleteConnectionKey

- ea: `0x18002df2c`
- end: `0x18002e2af`
- name: `FindCreateOrDeleteConnectionKey`
- size: `899`
- prototype: `__int64 __fastcall(HKEY hKey, PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e7a8`
- `0x18002e944`
- `0x18002e9c4`

## callees

- `0x18000b5c0`
- `0x18001e420`
- `0x18002df2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18002e22f`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18002e22f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002e114`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002e114`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002df9e`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002df9e`
- `ntdll!RtlInitUnicodeString` at `0x18002e1fb`
- `ntdll!RtlInitUnicodeString` at `0x18002e1fb`
- `ntdll!RtlHashUnicodeString` at `0x18002e210`
- `ntdll!RtlHashUnicodeString` at `0x18002e210`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dfe9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e270`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002dfe9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e270`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e01b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e0bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e01b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e0bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e13c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e13c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e0f5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e08e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e08e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002e005`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002e15d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002e005`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002e15d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e046`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e27d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e27d`

## string_xrefs

- `0x18002e0d3`: `RemotePath`

## pseudocode

```c
__int64 __fastcall FindCreateOrDeleteConnectionKey(HKEY hKey, wint_t *SourceString, int a3, HKEY *a4)
{
  __int64 v4; // rsi
  __int64 v6; // rdi
  DWORD v7; // r13d
  unsigned int Key; // ebx
  wint_t v12; // ax
  HKEY v14; // rax
  HKEY *v15; // rdi
  unsigned int i; // eax
  WCHAR SubKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE dwDisposition[12]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  PHKEY lpdwDisposition; // [rsp+68h] [rbp-98h] BYREF
  LPBYTE lpData; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v4 = -1;
  lpdwDisposition = a4;
  v6 = -1;
  v7 = 0;
  do
    ++v6;
  while ( SourceString[v6] );
  if ( (unsigned int)v6 < 2 )
    return 87;
  if ( SourceString[1] == 58 )
  {
    v12 = towupper(*SourceString);
    SubKey[1] = 0;
    SubKey[0] = v12;
    if ( a3 == 1 )
    {
      *(_DWORD *)dwDisposition = 0;
      return (unsigned int)RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, a4, (LPDWORD)dwDisposition);
    }
    else if ( a3 == 2 )
    {
      return (unsigned int)RegDeleteKeyExW(hKey, SubKey, 0x100u, 0);
    }
    else
    {
      return (unsigned int)RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, a4);
    }
  }
  *(_DWORD *)&dwDisposition[8] = 0;
  *(_DWORD *)SubKey = 0;
  cbData = 0;
  Type = 0;
  *(_QWORD *)dwDisposition = (unsigned int)(2 * v6 + 2);
  lpData = (LPBYTE)LocalAlloc(0, *(SIZE_T *)dwDisposition);
  if ( !lpData )
    return 8;
  while ( 1 )
  {
    wcscpy(SubKey, L"ą");
    Key = RegEnumKeyExW(hKey, v7, Name, (LPDWORD)SubKey, 0, 0, 0, 0);
    if ( Key )
    {
      v15 = lpdwDisposition;
      goto LABEL_25;
    }
    if ( !RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, (PHKEY)&dwDisposition[4]) )
      break;
LABEL_20:
    ++v7;
  }
  cbData = *(_DWORD *)dwDisposition;
  Key = RegQueryValueExW(*(HKEY *)&dwDisposition[4], L"RemotePath", 0, &Type, lpData, &cbData);
  if ( Key || Type != 1 || (unsigned int)_o__wcsnicmp(lpData, SourceString, (unsigned int)(v6 + 1)) )
  {
    RegCloseKey(*(HKEY *)&dwDisposition[4]);
    goto LABEL_20;
  }
  if ( a3 == 2 )
  {
    RegCloseKey(*(HKEY *)&dwDisposition[4]);
    *(_QWORD *)&dwDisposition[4] = 0;
    Key = RegDeleteKeyExW(hKey, Name, 0x100u, 0);
  }
  v14 = *(HKEY *)&dwDisposition[4];
  v15 = lpdwDisposition;
  *(_QWORD *)&dwDisposition[4] = 0;
  *lpdwDisposition = v14;
LABEL_25:
  if ( a3 == 1 && Key == 259 )
  {
    *(_DWORD *)dwDisposition = 0;
    DestinationString = 0;
    StringCchCopyW(pszDest, 0xFAu, SourceString);
    do
      ++v4;
    while ( pszDest[v4] );
    for ( i = 0; i < (unsigned int)v4; ++i )
    {
      if ( pszDest[i] == 92 )
        pszDest[i] = 47;
    }
    pszDest[(unsigned int)v4] = 95;
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlHashUnicodeString(&DestinationString, 1u, 0, (PULONG)dwDisposition);
    _o__itow_s(*(unsigned int *)dwDisposition, &pszDest[(unsigned int)(v4 + 1)], 9);
    pszDest[260] = 0;
    LODWORD(lpdwDisposition) = 0;
    Key = RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x2001Fu, 0, v15, (LPDWORD)&lpdwDisposition);
  }
  LocalFree(lpData);
  return Key;
}

```

## disassembly

```asm
0x18002df2c  mov     [rsp-8+arg_10], rbx
0x18002df31  push    rbp
0x18002df32  push    rsi
0x18002df33  push    rdi
0x18002df34  push    r12
0x18002df36  push    r13
0x18002df38  push    r14
0x18002df3a  push    r15
0x18002df3c  lea     rbp, [rsp-3C0h]
0x18002df44  sub     rsp, 4C0h
0x18002df4b  mov     rax, cs:__security_cookie
0x18002df52  xor     rax, rsp
0x18002df55  mov     [rbp+3F0h+var_40], rax
0x18002df5c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002df60  mov     rbx, r9
0x18002df63  mov     [rsp+4F0h+var_488], rbx
0x18002df68  mov     rdi, rsi
0x18002df6b  xor     r13d, r13d
0x18002df6e  mov     r15d, r8d
0x18002df71  mov     r12, rdx
0x18002df74  mov     r14, rcx
0x18002df77  inc     rdi
0x18002df7a  cmp     [rdx+rdi*2], r13w
0x18002df7f  jnz     short loc_18002DF77
0x18002df81  cmp     edi, 2
0x18002df84  jnb     short loc_18002DF90
0x18002df86  mov     ebx, 57h ; 'W'
0x18002df8b  jmp     loc_18002E283
0x18002df90  cmp     word ptr [rdx+2], 3Ah ; ':'
0x18002df95  jnz     loc_18002E023
0x18002df9b  movzx   ecx, word ptr [rdx]; C
0x18002df9e  call    cs:__imp_towupper
0x18002dfa4  mov     [rsp+4F0h+SubKey+2], r13w
0x18002dfaa  lea     rdx, [rsp+4F0h+SubKey]; lpSubKey
0x18002dfaf  mov     [rsp+4F0h+SubKey], ax
0x18002dfb4  mov     rcx, r14; hKey
0x18002dfb7  cmp     r15d, 1
0x18002dfbb  jnz     short loc_18002DFF6
0x18002dfbd  lea     rax, [rsp+4F0h+dwDisposition]
0x18002dfc2  mov     [rsp+4F0h+dwDisposition], r13d
0x18002dfc7  mov     [rsp+4F0h+lpdwDisposition], rax; lpdwDisposition
0x18002dfcc  xor     r9d, r9d; lpClass
0x18002dfcf  mov     [rsp+4F0h+phkResult], rbx; phkResult
0x18002dfd4  xor     r8d, r8d; Reserved
0x18002dfd7  mov     [rsp+4F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002dfdc  mov     [rsp+4F0h+samDesired], 2001Fh; samDesired
0x18002dfe4  mov     [rsp+4F0h+dwOptions], r13d; dwOptions
0x18002dfe9  call    cs:__imp_RegCreateKeyExW
0x18002dfef  mov     ebx, eax
0x18002dff1  jmp     loc_18002E283
0x18002dff6  cmp     r15d, 2
0x18002dffa  jnz     short loc_18002E00D
0x18002dffc  xor     r9d, r9d; Reserved
0x18002dfff  mov     r8d, 100h; samDesired
0x18002e005  call    cs:__imp_RegDeleteKeyExW
0x18002e00b  jmp     short loc_18002DFEF
0x18002e00d  mov     r9d, 2001Fh; samDesired
0x18002e013  mov     qword ptr [rsp+4F0h+dwOptions], rbx; phkResult
0x18002e018  xor     r8d, r8d; ulOptions
0x18002e01b  call    cs:__imp_RegOpenKeyExW
0x18002e021  jmp     short loc_18002DFEF
0x18002e023  lea     eax, ds:2[rdi*2]
0x18002e02a  mov     [rsp+4F0h+hKey], r13
0x18002e02f  mov     edx, eax; uBytes
0x18002e031  xor     ecx, ecx; uFlags
0x18002e033  mov     dword ptr [rsp+4F0h+SubKey], r13d
0x18002e038  mov     [rsp+4F0h+cbData], r13d
0x18002e03d  mov     [rsp+4F0h+Type], r13d
0x18002e042  mov     [rsp+4F0h+dwDisposition], eax
0x18002e046  call    cs:__imp_LocalAlloc
0x18002e04c  mov     [rsp+4F0h+lpData], rax
0x18002e051  test    rax, rax
0x18002e054  jnz     short loc_18002E05E
0x18002e056  lea     ebx, [rax+8]
0x18002e059  jmp     loc_18002E283
0x18002e05e  xor     eax, eax
0x18002e060  mov     dword ptr [rsp+4F0h+SubKey], 105h
0x18002e068  mov     [rsp+4F0h+phkResult], rax; lpftLastWriteTime
0x18002e06d  lea     r9, [rsp+4F0h+SubKey]; lpcchName
0x18002e072  mov     [rsp+4F0h+lpSecurityAttributes], rax; lpcchClass
0x18002e077  lea     r8, [rbp+3F0h+Name]; lpName
0x18002e07e  mov     qword ptr [rsp+4F0h+samDesired], rax; lpClass
0x18002e083  mov     edx, r13d; dwIndex
0x18002e086  mov     rcx, r14; hKey
0x18002e089  mov     qword ptr [rsp+4F0h+dwOptions], rax; lpReserved
0x18002e08e  call    cs:__imp_RegEnumKeyExW
0x18002e094  mov     ebx, eax
0x18002e096  test    eax, eax
0x18002e098  jnz     loc_18002E17E
0x18002e09e  lea     rax, [rsp+4F0h+hKey]
0x18002e0a3  mov     r9d, 2001Fh; samDesired
0x18002e0a9  xor     r8d, r8d; ulOptions
0x18002e0ac  mov     qword ptr [rsp+4F0h+dwOptions], rax; phkResult
0x18002e0b1  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x18002e0b8  mov     rcx, r14; hKey
0x18002e0bb  call    cs:__imp_RegOpenKeyExW
0x18002e0c1  test    eax, eax
0x18002e0c3  jnz     short loc_18002E129
0x18002e0c5  mov     eax, [rsp+4F0h+dwDisposition]
0x18002e0c9  lea     r9, [rsp+4F0h+Type]; lpType
0x18002e0ce  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18002e0d3  lea     rdx, aRemotepath; "RemotePath"
0x18002e0da  mov     [rsp+4F0h+cbData], eax
0x18002e0de  xor     r8d, r8d; lpReserved
0x18002e0e1  lea     rax, [rsp+4F0h+cbData]
0x18002e0e6  mov     qword ptr [rsp+4F0h+samDesired], rax; lpcbData
0x18002e0eb  mov     rax, [rsp+4F0h+lpData]
0x18002e0f0  mov     qword ptr [rsp+4F0h+dwOptions], rax; lpData
0x18002e0f5  call    cs:__imp_RegQueryValueExW
0x18002e0fb  mov     ebx, eax
0x18002e0fd  test    eax, eax
0x18002e0ff  jnz     short loc_18002E11E
0x18002e101  cmp     [rsp+4F0h+Type], 1
0x18002e106  jnz     short loc_18002E11E
0x18002e108  mov     rcx, [rsp+4F0h+lpData]
0x18002e10d  lea     r8d, [rdi+1]
0x18002e111  mov     rdx, r12
0x18002e114  call    cs:__imp__o__wcsnicmp
0x18002e11a  test    eax, eax
0x18002e11c  jz      short loc_18002E131
0x18002e11e  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18002e123  call    cs:__imp_RegCloseKey
0x18002e129  inc     r13d
0x18002e12c  jmp     loc_18002E05E
0x18002e131  cmp     r15d, 2
0x18002e135  jnz     short loc_18002E167
0x18002e137  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18002e13c  call    cs:__imp_RegCloseKey
0x18002e142  xor     r13d, r13d
0x18002e145  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x18002e14c  xor     r9d, r9d; Reserved
0x18002e14f  mov     [rsp+4F0h+hKey], r13
0x18002e154  mov     r8d, 100h; samDesired
0x18002e15a  mov     rcx, r14; hKey
0x18002e15d  call    cs:__imp_RegDeleteKeyExW
0x18002e163  mov     ebx, eax
0x18002e165  jmp     short loc_18002E16A
0x18002e167  xor     r13d, r13d
0x18002e16a  mov     rax, [rsp+4F0h+hKey]
0x18002e16f  mov     rdi, [rsp+4F0h+var_488]
0x18002e174  mov     [rsp+4F0h+hKey], r13
0x18002e179  mov     [rdi], rax
0x18002e17c  jmp     short loc_18002E186
0x18002e17e  mov     rdi, [rsp+4F0h+var_488]
0x18002e183  xor     r13d, r13d
0x18002e186  cmp     r15d, 1
0x18002e18a  jnz     loc_18002E278
0x18002e190  cmp     ebx, 103h
0x18002e196  jnz     loc_18002E278
0x18002e19c  xorps   xmm0, xmm0
0x18002e19f  mov     [rsp+4F0h+dwDisposition], r13d
0x18002e1a4  mov     r8, r12; pszSrc
0x18002e1a7  lea     edx, [rbx-9]; cchDest
0x18002e1aa  lea     rcx, [rbp+3F0h+pszDest]; pszDest
0x18002e1ae  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x18002e1b3  call    StringCchCopyW
0x18002e1b8  lea     r11, [rbp+3F0h+pszDest]
0x18002e1bc  inc     rsi
0x18002e1bf  cmp     [r11+rsi*2], r13w
0x18002e1c4  jnz     short loc_18002E1BC
0x18002e1c6  mov     eax, r13d
0x18002e1c9  test    esi, esi
0x18002e1cb  jz      short loc_18002E1E7
0x18002e1cd  mov     ecx, eax
0x18002e1cf  cmp     [rbp+rcx*2+3F0h+pszDest], 5Ch ; '\'
0x18002e1d5  jnz     short loc_18002E1E1
0x18002e1d7  mov     edx, 2Fh ; '/'
0x18002e1dc  mov     [rbp+rcx*2+3F0h+pszDest], dx
0x18002e1e1  inc     eax
0x18002e1e3  cmp     eax, esi
0x18002e1e5  jb      short loc_18002E1CD
0x18002e1e7  mov     eax, esi
0x18002e1e9  mov     ecx, 5Fh ; '_'
0x18002e1ee  mov     rdx, r12; SourceString
0x18002e1f1  mov     [rbp+rax*2+3F0h+pszDest], cx
0x18002e1f6  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x18002e1fb  call    cs:__imp_RtlInitUnicodeString
0x18002e201  lea     r9, [rsp+4F0h+dwDisposition]; HashValue
0x18002e206  xor     r8d, r8d; HashAlgorithm
0x18002e209  mov     dl, 1; CaseInSensitive
0x18002e20b  lea     rcx, [rsp+4F0h+DestinationString]; String
0x18002e210  call    cs:__imp_RtlHashUnicodeString
0x18002e216  mov     ecx, [rsp+4F0h+dwDisposition]
0x18002e21a  lea     eax, [rsi+1]
0x18002e21d  mov     r9d, 10h
0x18002e223  lea     rdx, [rbp+3F0h+pszDest]
0x18002e227  lea     rdx, [rdx+rax*2]
0x18002e22b  lea     r8d, [r9-7]
0x18002e22f  call    cs:__imp__o__itow_s
0x18002e235  lea     rax, [rsp+4F0h+var_488]
0x18002e23a  mov     [rbp+3F0h+var_258], r13w
0x18002e242  mov     [rsp+4F0h+lpdwDisposition], rax; lpdwDisposition
0x18002e247  lea     rdx, [rbp+3F0h+pszDest]; lpSubKey
0x18002e24b  mov     [rsp+4F0h+phkResult], rdi; phkResult
0x18002e250  xor     r9d, r9d; lpClass
0x18002e253  mov     [rsp+4F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002e258  xor     r8d, r8d; Reserved
0x18002e25b  mov     [rsp+4F0h+samDesired], 2001Fh; samDesired
0x18002e263  mov     rcx, r14; hKey
0x18002e266  mov     [rsp+4F0h+dwOptions], r13d; dwOptions
0x18002e26b  mov     dword ptr [rsp+4F0h+var_488], r13d
0x18002e270  call    cs:__imp_RegCreateKeyExW
0x18002e276  mov     ebx, eax
0x18002e278  mov     rcx, [rsp+4F0h+lpData]; hMem
0x18002e27d  call    cs:__imp_LocalFree
0x18002e283  mov     eax, ebx
0x18002e285  mov     rcx, [rbp+3F0h+var_40]
0x18002e28c  xor     rcx, rsp; StackCookie
0x18002e28f  call    __security_check_cookie
0x18002e294  mov     rbx, [rsp+4F0h+arg_10]
0x18002e29c  add     rsp, 4C0h
0x18002e2a3  pop     r15
0x18002e2a5  pop     r14
0x18002e2a7  pop     r13
0x18002e2a9  pop     r12
0x18002e2ab  pop     rdi
0x18002e2ac  pop     rsi
0x18002e2ad  pop     rbp
0x18002e2ae  retn
```
