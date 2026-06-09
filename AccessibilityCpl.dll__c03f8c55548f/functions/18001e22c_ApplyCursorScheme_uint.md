# ApplyCursorScheme(uint)

- ea: `0x18001e22c`
- end: `0x18001e66a`
- name: `?ApplyCursorScheme@@YAXI@Z`
- size: `1086`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016290`

## callees

- `0x180002018`
- `0x180002024`
- `0x18001e22c`
- `0x18001e7b0`
- `0x18001e984`
- `0x18001e9f0`

## import_xrefs

- `msvcrt!wcschr` at `0x18001e521`
- `msvcrt!wcschr` at `0x18001e521`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e647`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e651`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e647`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e651`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e296`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001e296`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e311`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e38a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e575`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e5e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e61d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e311`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e38a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e575`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e5e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e61d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e456`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e456`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e3fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e4b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e4b7`
- `USER32!SystemParametersInfoW` at `0x18001e63b`
- `USER32!SystemParametersInfoW` at `0x18001e63b`

## pseudocode

```c
void __fastcall ApplyCursorScheme(unsigned int a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int j; // ebx
  unsigned int i; // esi
  const BYTE *v6; // r11
  HKEY v7; // rcx
  const WCHAR *v8; // r12
  unsigned __int64 v9; // r15
  _WORD *v10; // rax
  void *v11; // rsi
  unsigned __int64 v12; // r15
  const wchar_t *v13; // r13
  unsigned int v14; // eax
  wchar_t *v15; // rax
  unsigned __int64 v16; // rbx
  bool v17; // cf
  DWORD Type; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v23; // [rsp+70h] [rbp-10h]
  int Data; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int64 cbData; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v26; // [rsp+D8h] [rbp+58h]

  LoadCursorSchemeNames();
  hKey = 0;
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Control Panel\\Cursors",
         0,
         (LPWSTR)&::Data,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition) )
  {
    return;
  }
  Data = 0;
  if ( a1 > 5 )
  {
    v2 = a1 - 6;
    if ( a1 != 6 )
    {
LABEL_6:
      v3 = v2 - 1;
      if ( v3 && v3 - 1 >= 2 )
      {
LABEL_36:
        RegSetValueExW(hKey, L"Scheme Source", 0, 4u, (const BYTE *)&Data, 4u);
        RegCloseKey(hKey);
        SystemParametersInfoW(0x57u, 0, 0, 2u);
        return;
      }
    }
  }
  else if ( a1 != 5 )
  {
    if ( !a1 )
    {
      Data = *(_DWORD *)&g_dwOrigSchemeSource;
      for ( i = 0; i < 0x12; ++i )
      {
        cbData = 0;
        StringCchLengthW((const unsigned __int16 *)&(&g_szOrigCursors)[65 * (int)i], 0x104u, &cbData);
        RegSetValueExW(hKey, off_180030150[i], 0, 1u, v6, 2 * cbData + 2);
      }
      goto LABEL_36;
    }
    v2 = a1 - 1;
    if ( a1 == 1 )
    {
      for ( j = 0; j < 0x12; ++j )
        RegSetValueExW(hKey, off_180030150[j], 0, 1u, (const BYTE *)&::Data, 2u);
      goto LABEL_36;
    }
    goto LABEL_6;
  }
  Data = 2;
  hkey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Cursors\\Schemes",
         0,
         0x20019u,
         &hkey)
    && (Data = 1, RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors\\Schemes", 0, 0x20019u, &hkey)) )
  {
    v7 = hKey;
  }
  else
  {
    LODWORD(cbData) = 0;
    Type = 0;
    v8 = &g_szSchemeNames + 100 * nSchemeMinus2SafeHelper(a1);
    if ( !RegQueryValueExW(hkey, v8, 0, &Type, 0, (LPDWORD)&cbData) && (cbData & 1) == 0 && (_DWORD)cbData )
    {
      v9 = (unsigned int)cbData;
      v10 = operator new[]((unsigned int)cbData);
      v11 = v10;
      if ( v10 )
      {
        *v10 = 0;
        if ( RegGetValueW(hkey, 0, v8, 0x20000002u, &Type, v10, (LPDWORD)&cbData) )
        {
          RegCloseKey(hKey);
          RegCloseKey(hkey);
          operator delete[](v11);
          return;
        }
        v12 = v9 >> 1;
        v21 = 0;
        v13 = (const wchar_t *)v11;
        StringCchLengthW((const unsigned __int16 *)v11, v12, &v21);
        v23 = (unsigned __int64)v11 + 2 * v21;
        v14 = 0;
        v26 = 0;
        while ( v14 != 17 )
        {
          v15 = wcschr(v13, 0x2Cu);
          if ( v15 )
            *v15 = 0;
          v21 = 0;
          StringCchLengthW(v13, v12, &v21);
          v16 = v21;
          RegSetValueExW(hKey, off_180030150[v26], 0, 1u, (const BYTE *)v13, 2 * v21 + 2);
          v17 = v23 < (unsigned __int64)&v13[v16 + 1];
          v13 += v16 + 1;
          if ( v17 )
            v13 = (const wchar_t *)v23;
          v14 = v26 + 1;
          v26 = v14;
          if ( v14 >= 0x12 )
            goto LABEL_34;
        }
        v21 = 0;
        StringCchLengthW(v8, 0x64u, &v21);
        RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)v8, 2 * v21 + 2);
LABEL_34:
        operator delete[](v11);
      }
      RegCloseKey(hkey);
      goto LABEL_36;
    }
    RegCloseKey(hKey);
    v7 = hkey;
  }
  RegCloseKey(v7);
}

```

## disassembly

```asm
0x18001e22c  push    rbp
0x18001e22e  push    rbx
0x18001e22f  push    rsi
0x18001e230  push    r12
0x18001e232  push    r13
0x18001e234  push    r14
0x18001e236  push    r15
0x18001e238  mov     rbp, rsp
0x18001e23b  sub     rsp, 80h
0x18001e242  mov     ebx, ecx
0x18001e244  call    ?LoadCursorSchemeNames@@YAXXZ; LoadCursorSchemeNames(void)
0x18001e249  xor     r13d, r13d
0x18001e24c  lea     rax, [rbp+dwDisposition]
0x18001e250  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18001e255  lea     rsi, Data
0x18001e25c  lea     rax, [rbp+hKey]
0x18001e260  mov     [rbp+hKey], r13
0x18001e264  mov     [rsp+80h+phkResult], rax; phkResult
0x18001e269  lea     rdx, SubKey; "Control Panel\\Cursors"
0x18001e270  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18001e275  mov     r14, 0FFFFFFFF80000001h
0x18001e27c  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18001e284  mov     r9, rsi; lpClass
0x18001e287  xor     r8d, r8d; Reserved
0x18001e28a  mov     [rsp+80h+dwOptions], r13d; dwOptions
0x18001e28f  mov     rcx, r14; hKey
0x18001e292  mov     [rbp+dwDisposition], r13d
0x18001e296  call    cs:__imp_RegCreateKeyExW
0x18001e29c  test    eax, eax
0x18001e29e  jnz     loc_18001E657
0x18001e2a4  mov     [rbp+Data], r13d
0x18001e2a8  cmp     ebx, 5
0x18001e2ab  ja      loc_18001E39C
0x18001e2b1  jz      loc_18001E3A7
0x18001e2b7  mov     eax, ebx
0x18001e2b9  test    ebx, ebx
0x18001e2bb  jz      short loc_18001E323
0x18001e2bd  sub     eax, 1
0x18001e2c0  jz      short loc_18001E2E2
0x18001e2c2  sub     eax, 1
0x18001e2c5  jz      loc_18001E3A7
0x18001e2cb  sub     eax, 1
0x18001e2ce  jz      loc_18001E3A7
0x18001e2d4  cmp     eax, 1
0x18001e2d7  jz      loc_18001E3A7
0x18001e2dd  jmp     loc_18001E5FB
0x18001e2e2  mov     ebx, r13d
0x18001e2e5  lea     r14, __ImageBase
0x18001e2ec  mov     rcx, [rbp+hKey]; hKey
0x18001e2f0  mov     r9d, 1; dwType
0x18001e2f6  movsxd  rdx, ebx
0x18001e2f9  xor     r8d, r8d; Reserved
0x18001e2fc  mov     [rsp+80h+samDesired], 2; cbData
0x18001e304  mov     qword ptr [rsp+80h+dwOptions], rsi; lpData
0x18001e309  mov     rdx, ds:rva off_180030150[r14+rdx*8]; lpValueName
0x18001e311  call    cs:__imp_RegSetValueExW
0x18001e317  inc     ebx
0x18001e319  cmp     ebx, 12h
0x18001e31c  jb      short loc_18001E2EC
0x18001e31e  jmp     loc_18001E5FB
0x18001e323  mov     eax, cs:?g_dwOrigSchemeSource@@3KA; ulong g_dwOrigSchemeSource
0x18001e329  lea     r14, __ImageBase
0x18001e330  mov     [rbp+Data], eax
0x18001e333  mov     esi, r13d
0x18001e336  movsxd  rbx, esi
0x18001e339  lea     r11, rva ?g_szOrigCursors@@3PAY0BAE@GA[r14]; ushort (near * g_szOrigCursors)[260] ...
0x18001e340  imul    rax, rbx, 208h
0x18001e347  lea     r8, [rbp+cbData]; unsigned __int64 *
0x18001e34b  mov     [rbp+cbData], r13
0x18001e34f  add     r11, rax
0x18001e352  mov     edx, 104h; unsigned __int64
0x18001e357  mov     rcx, r11; unsigned __int16 *
0x18001e35a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e35f  mov     r8d, dword ptr [rbp+cbData]
0x18001e363  mov     r9d, 1; dwType
0x18001e369  mov     rdx, ds:rva off_180030150[r14+rbx*8]; lpValueName
0x18001e371  mov     rcx, [rbp+hKey]; hKey
0x18001e375  lea     r8d, ds:2[r8*2]
0x18001e37d  mov     [rsp+80h+samDesired], r8d; cbData
0x18001e382  xor     r8d, r8d; Reserved
0x18001e385  mov     qword ptr [rsp+80h+dwOptions], r11; lpData
0x18001e38a  call    cs:__imp_RegSetValueExW
0x18001e390  inc     esi
0x18001e392  cmp     esi, 12h
0x18001e395  jb      short loc_18001E336
0x18001e397  jmp     loc_18001E5FB
0x18001e39c  mov     eax, ebx
0x18001e39e  sub     eax, 6
0x18001e3a1  jnz     loc_18001E2C2
0x18001e3a7  lea     rax, [rbp+hkey]
0x18001e3ab  mov     [rbp+Data], 2
0x18001e3b2  mov     esi, 20019h
0x18001e3b7  mov     [rbp+hkey], r13
0x18001e3bb  mov     r9d, esi; samDesired
0x18001e3be  mov     qword ptr [rsp+80h+dwOptions], rax; phkResult
0x18001e3c3  xor     r8d, r8d; ulOptions
0x18001e3c6  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001e3cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e3d4  call    cs:__imp_RegOpenKeyExW
0x18001e3da  test    eax, eax
0x18001e3dc  jz      short loc_18001E411
0x18001e3de  lea     rax, [rbp+hkey]
0x18001e3e2  mov     [rbp+Data], 1
0x18001e3e9  mov     r9d, esi; samDesired
0x18001e3ec  mov     qword ptr [rsp+80h+dwOptions], rax; phkResult
0x18001e3f1  xor     r8d, r8d; ulOptions
0x18001e3f4  lea     rdx, aControlPanelCu_1; "Control Panel\\Cursors\\Schemes"
0x18001e3fb  mov     rcx, r14; hKey
0x18001e3fe  call    cs:__imp_RegOpenKeyExW
0x18001e404  test    eax, eax
0x18001e406  jz      short loc_18001E411
0x18001e408  mov     rcx, [rbp+hKey]
0x18001e40c  jmp     loc_18001E651
0x18001e411  mov     ecx, ebx; unsigned int
0x18001e413  mov     dword ptr [rbp+cbData], r13d
0x18001e417  mov     [rbp+Type], r13d
0x18001e41b  call    ?nSchemeMinus2SafeHelper@@YAII@Z; nSchemeMinus2SafeHelper(uint)
0x18001e420  mov     rcx, [rbp+hkey]; hKey
0x18001e424  lea     r14, __ImageBase
0x18001e42b  mov     edx, eax
0x18001e42d  lea     r12, rva ?g_szSchemeNames@@3PAY0GE@GA[r14]; ushort (near * g_szSchemeNames)[100] ...
0x18001e434  imul    rax, rdx, 0C8h
0x18001e43b  lea     r9, [rbp+Type]; lpType
0x18001e43f  xor     r8d, r8d; lpReserved
0x18001e442  add     r12, rax
0x18001e445  lea     rax, [rbp+cbData]
0x18001e449  mov     qword ptr [rsp+80h+samDesired], rax; lpcbData
0x18001e44e  mov     rdx, r12; lpValueName
0x18001e451  mov     qword ptr [rsp+80h+dwOptions], r13; lpData
0x18001e456  call    cs:__imp_RegQueryValueExW
0x18001e45c  test    eax, eax
0x18001e45e  jnz     loc_18001E643
0x18001e464  mov     eax, dword ptr [rbp+cbData]
0x18001e467  test    al, 1
0x18001e469  jnz     loc_18001E643
0x18001e46f  test    eax, eax
0x18001e471  jz      loc_18001E643
0x18001e477  mov     ecx, eax; unsigned __int64
0x18001e479  mov     r15d, eax
0x18001e47c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e481  mov     rsi, rax
0x18001e484  test    rax, rax
0x18001e487  jz      loc_18001E5F1
0x18001e48d  mov     [rax], r13w
0x18001e491  mov     r9d, 20000002h; dwFlags
0x18001e497  mov     rcx, [rbp+hkey]; hkey
0x18001e49b  lea     rax, [rbp+cbData]
0x18001e49f  mov     [rsp+80h+lpSecurityAttributes], rax; pcbData
0x18001e4a4  mov     r8, r12; lpValue
0x18001e4a7  lea     rax, [rbp+Type]
0x18001e4ab  mov     qword ptr [rsp+80h+samDesired], rsi; pvData
0x18001e4b0  xor     edx, edx; lpSubKey
0x18001e4b2  mov     qword ptr [rsp+80h+dwOptions], rax; pdwType
0x18001e4b7  call    cs:__imp_RegGetValueW
0x18001e4bd  test    eax, eax
0x18001e4bf  jz      short loc_18001E4E2
0x18001e4c1  mov     rcx, [rbp+hKey]; hKey
0x18001e4c5  call    cs:__imp_RegCloseKey
0x18001e4cb  mov     rcx, [rbp+hkey]; hKey
0x18001e4cf  call    cs:__imp_RegCloseKey
0x18001e4d5  mov     rcx, rsi; void *
0x18001e4d8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e4dd  jmp     loc_18001E657
0x18001e4e2  shr     r15, 1
0x18001e4e5  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18001e4e9  mov     rdx, r15; unsigned __int64
0x18001e4ec  mov     [rbp+var_20], 0
0x18001e4f4  mov     rcx, rsi; unsigned __int16 *
0x18001e4f7  mov     r13, rsi
0x18001e4fa  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e4ff  mov     r8, [rbp+var_20]
0x18001e503  lea     rax, [rsi+r8*2]
0x18001e507  mov     [rbp+var_10], rax
0x18001e50b  xor     eax, eax
0x18001e50d  mov     [rbp+arg_18], eax
0x18001e510  cmp     eax, 11h
0x18001e513  jz      loc_18001E5A5
0x18001e519  mov     edx, 2Ch ; ','; Ch
0x18001e51e  mov     rcx, r13; Str
0x18001e521  call    cs:__imp_wcschr
0x18001e527  test    rax, rax
0x18001e52a  jz      short loc_18001E531
0x18001e52c  xor     ecx, ecx
0x18001e52e  mov     [rax], cx
0x18001e531  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18001e535  mov     [rbp+var_20], 0
0x18001e53d  mov     rdx, r15; unsigned __int64
0x18001e540  mov     rcx, r13; unsigned __int16 *
0x18001e543  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e548  mov     rbx, [rbp+var_20]
0x18001e54c  mov     r9d, 1; dwType
0x18001e552  movsxd  rdx, [rbp+arg_18]
0x18001e556  xor     r8d, r8d; Reserved
0x18001e559  mov     rcx, [rbp+hKey]; hKey
0x18001e55d  lea     eax, ds:2[rbx*2]
0x18001e564  mov     rdx, ds:rva off_180030150[r14+rdx*8]; lpValueName
0x18001e56c  mov     [rsp+80h+samDesired], eax; cbData
0x18001e570  mov     qword ptr [rsp+80h+dwOptions], r13; lpData
0x18001e575  call    cs:__imp_RegSetValueExW
0x18001e57b  lea     rax, ds:2[rbx*2]
0x18001e583  add     rax, r13
0x18001e586  cmp     [rbp+var_10], rax
0x18001e58a  mov     r13, rax
0x18001e58d  mov     eax, [rbp+arg_18]
0x18001e590  cmovb   r13, [rbp+var_10]
0x18001e595  inc     eax
0x18001e597  mov     [rbp+arg_18], eax
0x18001e59a  cmp     eax, 12h
0x18001e59d  jb      loc_18001E510
0x18001e5a3  jmp     short loc_18001E5E9
0x18001e5a5  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18001e5a9  mov     [rbp+var_20], 0
0x18001e5b1  mov     edx, 64h ; 'd'; unsigned __int64
0x18001e5b6  mov     rcx, r12; unsigned __int16 *
0x18001e5b9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e5be  mov     r8d, dword ptr [rbp+var_20]
0x18001e5c2  mov     r9d, 1; dwType
0x18001e5c8  mov     rcx, [rbp+hKey]; hKey
0x18001e5cc  xor     edx, edx; lpValueName
0x18001e5ce  lea     r8d, ds:2[r8*2]
0x18001e5d6  mov     [rsp+80h+samDesired], r8d; cbData
0x18001e5db  xor     r8d, r8d; Reserved
0x18001e5de  mov     qword ptr [rsp+80h+dwOptions], r12; lpData
0x18001e5e3  call    cs:__imp_RegSetValueExW
0x18001e5e9  mov     rcx, rsi; void *
0x18001e5ec  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e5f1  mov     rcx, [rbp+hkey]; hKey
0x18001e5f5  call    cs:__imp_RegCloseKey
0x18001e5fb  mov     rcx, [rbp+hKey]; hKey
0x18001e5ff  lea     rax, [rbp+Data]
0x18001e603  mov     r9d, 4; dwType
0x18001e609  lea     rdx, ValueName; "Scheme Source"
0x18001e610  mov     [rsp+80h+samDesired], r9d; cbData
0x18001e615  xor     r8d, r8d; Reserved
0x18001e618  mov     qword ptr [rsp+80h+dwOptions], rax; lpData
0x18001e61d  call    cs:__imp_RegSetValueExW
0x18001e623  mov     rcx, [rbp+hKey]; hKey
0x18001e627  call    cs:__imp_RegCloseKey
0x18001e62d  xor     edx, edx; uiParam
0x18001e62f  mov     r9d, 2; fWinIni
0x18001e635  xor     r8d, r8d; pvParam
0x18001e638  lea     ecx, [rdx+57h]; uiAction
0x18001e63b  call    cs:__imp_SystemParametersInfoW
0x18001e641  jmp     short loc_18001E657
0x18001e643  mov     rcx, [rbp+hKey]; hKey
0x18001e647  call    cs:__imp_RegCloseKey
0x18001e64d  mov     rcx, [rbp+hkey]; hKey
0x18001e651  call    cs:__imp_RegCloseKey
0x18001e657  add     rsp, 80h
0x18001e65e  pop     r15
0x18001e660  pop     r14
0x18001e662  pop     r13
0x18001e664  pop     r12
0x18001e666  pop     rsi
0x18001e667  pop     rbx
0x18001e668  pop     rbp
0x18001e669  retn
```
