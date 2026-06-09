# AccentColors::UpdateHistory(ulong,bool)

- ea: `0x180264000`
- end: `0x1802644db`
- name: `?UpdateHistory@AccentColors@@SAJK_N@Z`
- size: `1243`
- prototype: `__int64 __fastcall(unsigned int, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180133f04`
- `0x1802635a4`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x18002e1f4`
- `0x1800740f4`
- `0x180263c94`
- `0x180264000`
- `0x1802644e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264241`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264383`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264444`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264495`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264241`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264383`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264444`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180264495`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180264094`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026415a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180264094`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026415a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180264200`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802642bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180264200`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802642bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802640e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802640e6`

## pseudocode

```c
__int64 __fastcall AccentColors::UpdateHistory(unsigned int a1, bool a2)
{
  BOOL v4; // r12d
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v7; // ebx
  __int64 v8; // rdx
  char v9; // di
  HKEY *v10; // rax
  LSTATUS v11; // eax
  bool v12; // sf
  HKEY *v13; // rax
  LSTATUS v14; // eax
  signed int v15; // esi
  int v16; // r15d
  LSTATUS v17; // eax
  bool v18; // sf
  int v19; // ebx
  LSTATUS v20; // eax
  __int64 v21; // rax
  int v22; // esi
  int v23; // ebx
  int v24; // eax
  int i; // edx
  int v26; // ebx
  int v27; // edi
  signed int v28; // edx
  int v29; // r8d
  int v30; // r9d
  LSTATUS v31; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v36[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v38; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE v40[8]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v41[6]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hKey = 0;
  v38 = 0;
  v4 = IsAutoColorizationEnabled();
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  Key = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History",
          0,
          0,
          0,
          0x2001Fu,
          0,
          phkResult,
          0);
  v7 = Key;
  if ( Key > 0 )
    v7 = (unsigned __int16)Key | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 380;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\themes\\accentcolors\\accentcolors.cpp",
      (const char *)(unsigned int)v7,
      dwOptions);
    goto LABEL_63;
  }
  v9 = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v38);
  v11 = RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors",
          0,
          0x2001Fu,
          v10);
  v12 = v11 < 0;
  if ( v11 > 0 )
    v12 = 1;
  if ( v12 )
  {
    if ( !a2 && AccentColors::_IsKnownColor(a1, 0) )
      v9 = 1;
    v13 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v38);
    v14 = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\History\\Colors",
            0,
            0,
            0,
            0x2001Fu,
            0,
            v13,
            0);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = 386;
      goto LABEL_15;
    }
  }
  if ( !AccentColors::_IsKnownColor(a1, a2) || v9 )
  {
    v15 = 0;
    v16 = 0;
    *(_DWORD *)Data = 0;
    if ( !v9 && a1 != 195948557 )
    {
      v41[0] = a1;
      v16 = 1;
    }
    cbData = 4;
    v17 = RegQueryValueExW(hKey, L"AutoColor", 0, 0, Data, &cbData);
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
    {
      *(_DWORD *)Data = v4;
      RegSetValueExW(hKey, L"AutoColor", 0, 4u, Data, 4u);
    }
    v19 = 0;
    while ( v19 < 5 )
    {
      if ( *(_DWORD *)Data == 1 && !v19 )
        goto LABEL_36;
      dwOptionsa[0] = v19;
      v15 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v15 < 0 )
        goto LABEL_36;
      *(_DWORD *)v36 = 0;
      cbData = 4;
      v20 = RegQueryValueExW(v38, ValueName, 0, 0, v36, &cbData);
      v15 = v20;
      if ( v20 > 0 )
        v15 = (unsigned __int16)v20 | 0x80070000;
      if ( v15 < 0 )
      {
LABEL_36:
        ++v19;
        if ( v15 < 0 )
          break;
      }
      else
      {
        if ( ((a1 ^ *(_DWORD *)v36) & 0xFFFFFF) != 0 )
        {
          v21 = v16++;
          v41[v21] = *(_DWORD *)v36;
        }
        ++v19;
      }
    }
    v22 = 0;
    v23 = 0;
    do
    {
LABEL_38:
      if ( v23 >= v16 )
        break;
      dwOptionsa[0] = v22;
      v24 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v24 >= 0 )
      {
        for ( i = 0; i < v23; ++i )
        {
          if ( ((v41[v23] ^ v41[i]) & 0xFFFFFF) == 0 )
          {
            ++v23;
            goto LABEL_38;
          }
        }
        v24 = RegSetValueExW(v38, ValueName, 0, 4u, (const BYTE *)&v41[v23], 4u);
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        ++v22;
      }
      ++v23;
    }
    while ( v24 >= 0 );
    v26 = 0;
    v27 = v22;
    do
    {
      if ( v27 >= 5 || v26 >= 5 )
        break;
      dwOptionsa[0] = v27;
      v28 = StringCchPrintfW(ValueName, 0x104u, L"%s%u", L"ColorHistory", *(_QWORD *)dwOptionsa);
      if ( v28 >= 0 )
      {
LABEL_53:
        if ( (unsigned int)v26 < 4 )
        {
          v29 = 0;
          v30 = *((_DWORD *)qword_18033BD50 + v26);
          *(_DWORD *)v36 = v30;
          while ( v29 < v22 )
          {
            if ( ((v41[v29] ^ v30) & 0xFFFFFF) == 0 )
            {
              ++v26;
              goto LABEL_53;
            }
            ++v29;
          }
          v31 = RegSetValueExW(v38, ValueName, 0, 4u, v36, 4u);
          v28 = v31;
          if ( v31 > 0 )
            v28 = (unsigned __int16)v31 | 0x80070000;
        }
      }
      ++v27;
      ++v26;
    }
    while ( v28 >= 0 );
  }
  *(_DWORD *)v40 = v4;
  RegSetValueExW(hKey, L"AutoColor", 0, 4u, v40, 4u);
  v7 = 0;
LABEL_63:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180264000  push    rbp
0x180264002  push    rbx
0x180264003  push    rsi
0x180264004  push    rdi
0x180264005  push    r12
0x180264007  push    r14
0x180264009  push    r15
0x18026400b  lea     rbp, [rsp-1B0h]
0x180264013  sub     rsp, 2B0h
0x18026401a  mov     rax, cs:__security_cookie
0x180264021  xor     rax, rsp
0x180264024  mov     [rbp+1E0h+var_40], rax
0x18026402b  mov     sil, dl
0x18026402e  mov     [rsp+2E0h+hKey], 0
0x180264037  mov     r14d, ecx
0x18026403a  mov     [rsp+2E0h+var_280], 0
0x180264043  call    ?IsAutoColorizationEnabled@@YA_NXZ; IsAutoColorizationEnabled(void)
0x180264048  lea     rcx, [rsp+2E0h+hKey]
0x18026404d  movzx   r12d, al
0x180264051  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180264056  mov     [rsp+2E0h+lpdwDisposition], 0; lpdwDisposition
0x18026405f  lea     rdx, aSoftwareMicros_59; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180264066  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18026406b  mov     r15d, 2001Fh
0x180264071  mov     [rsp+2E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18026407a  xor     r9d, r9d; lpClass
0x18026407d  mov     [rsp+2E0h+samDesired], r15d; samDesired
0x180264082  xor     r8d, r8d; Reserved
0x180264085  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18026408c  mov     [rsp+2E0h+dwOptions], 0; dwOptions
0x180264094  call    cs:__imp_RegCreateKeyExW
0x18026409b  nop     dword ptr [rax+rax+00h]
0x1802640a0  mov     ebx, eax
0x1802640a2  test    eax, eax
0x1802640a4  jle     short loc_1802640AF
0x1802640a6  movzx   ebx, ax
0x1802640a9  or      ebx, 80070000h
0x1802640af  test    ebx, ebx
0x1802640b1  jns     short loc_1802640BD
0x1802640b3  mov     edx, 17Ch
0x1802640b8  jmp     loc_18026417E
0x1802640bd  lea     rcx, [rsp+2E0h+var_280]
0x1802640c2  xor     dil, dil
0x1802640c5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1802640ca  mov     rbx, 0FFFFFFFF80000001h
0x1802640d1  mov     qword ptr [rsp+2E0h+dwOptions], rax; phkResult
0x1802640d6  mov     rcx, rbx; hKey
0x1802640d9  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1802640e0  mov     r9d, r15d; samDesired
0x1802640e3  xor     r8d, r8d; ulOptions
0x1802640e6  call    cs:__imp_RegOpenKeyExW
0x1802640ed  nop     dword ptr [rax+rax+00h]
0x1802640f2  test    eax, eax
0x1802640f4  jle     short loc_180264100
0x1802640f6  movzx   eax, ax
0x1802640f9  or      eax, 80070000h
0x1802640fe  test    eax, eax
0x180264100  jns     loc_180264199
0x180264106  test    sil, sil
0x180264109  jnz     short loc_18026411C
0x18026410b  xor     edx, edx; bool
0x18026410d  mov     ecx, r14d; unsigned int
0x180264110  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x180264115  test    al, al
0x180264117  jz      short loc_18026411C
0x180264119  mov     dil, 1
0x18026411c  lea     rcx, [rsp+2E0h+var_280]
0x180264121  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180264126  mov     [rsp+2E0h+lpdwDisposition], 0; lpdwDisposition
0x18026412f  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180264136  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18026413b  xor     r9d, r9d; lpClass
0x18026413e  mov     [rsp+2E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180264147  xor     r8d, r8d; Reserved
0x18026414a  mov     [rsp+2E0h+samDesired], r15d; samDesired
0x18026414f  mov     rcx, rbx; hKey
0x180264152  mov     [rsp+2E0h+dwOptions], 0; int
0x18026415a  call    cs:__imp_RegCreateKeyExW
0x180264161  nop     dword ptr [rax+rax+00h]
0x180264166  mov     ebx, eax
0x180264168  test    eax, eax
0x18026416a  jle     short loc_180264175
0x18026416c  movzx   ebx, ax
0x18026416f  or      ebx, 80070000h
0x180264175  test    ebx, ebx
0x180264177  jns     short loc_180264199
0x180264179  mov     edx, 182h; void *
0x18026417e  mov     rcx, [rbp+1E8h]; this
0x180264185  lea     r8, aShellThemesAcc; "shell\\themes\\accentcolors\\accentcolo"...
0x18026418c  mov     r9d, ebx; char *
0x18026418f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180264194  jmp     loc_1802644A3
0x180264199  mov     dl, sil; bool
0x18026419c  mov     ecx, r14d; unsigned int
0x18026419f  call    ?_IsKnownColor@AccentColors@@CA_NK_N@Z; AccentColors::_IsKnownColor(ulong,bool)
0x1802641a4  mov     ebx, 4
0x1802641a9  test    al, al
0x1802641ab  jz      short loc_1802641B6
0x1802641ad  test    dil, dil
0x1802641b0  jz      loc_180264470
0x1802641b6  xor     esi, esi
0x1802641b8  xor     r15d, r15d
0x1802641bb  mov     dword ptr [rsp+2E0h+Data], esi
0x1802641bf  test    dil, dil
0x1802641c2  jnz     short loc_1802641D6
0x1802641c4  cmp     r14d, 0BADF00Dh
0x1802641cb  jz      short loc_1802641D6
0x1802641cd  mov     [rsp+2E0h+var_268], r14d
0x1802641d2  lea     r15d, [rsi+1]
0x1802641d6  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1802641db  lea     rax, [rsp+2E0h+cbData]
0x1802641e0  mov     qword ptr [rsp+2E0h+samDesired], rax; lpcbData
0x1802641e5  lea     rdx, aAutocolor; "AutoColor"
0x1802641ec  lea     rax, [rsp+2E0h+Data]
0x1802641f1  mov     [rsp+2E0h+cbData], ebx
0x1802641f5  xor     r9d, r9d; lpType
0x1802641f8  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x1802641fd  xor     r8d, r8d; lpReserved
0x180264200  call    cs:__imp_RegQueryValueExW
0x180264207  nop     dword ptr [rax+rax+00h]
0x18026420c  test    eax, eax
0x18026420e  jle     short loc_18026421A
0x180264210  movzx   eax, ax
0x180264213  or      eax, 80070000h
0x180264218  test    eax, eax
0x18026421a  jns     short loc_18026424D
0x18026421c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180264221  lea     rax, [rsp+2E0h+Data]
0x180264226  mov     [rsp+2E0h+samDesired], ebx; cbData
0x18026422a  lea     rdx, aAutocolor; "AutoColor"
0x180264231  mov     r9d, ebx; dwType
0x180264234  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x180264239  xor     r8d, r8d; Reserved
0x18026423c  mov     dword ptr [rsp+2E0h+Data], r12d
0x180264241  call    cs:__imp_RegSetValueExW
0x180264248  nop     dword ptr [rax+rax+00h]
0x18026424d  xor     ebx, ebx
0x18026424f  lea     edi, [rbx+4]
0x180264252  cmp     ebx, 5
0x180264255  jge     loc_18026430B
0x18026425b  cmp     dword ptr [rsp+2E0h+Data], 1
0x180264260  jnz     short loc_18026426A
0x180264262  test    ebx, ebx
0x180264264  jz      loc_180264301
0x18026426a  lea     r9, aColorhistory; "ColorHistory"
0x180264271  mov     [rsp+2E0h+dwOptions], ebx
0x180264275  lea     r8, aSU_0; "%s%u"
0x18026427c  mov     edx, 104h; unsigned __int64
0x180264281  lea     rcx, [rbp+1E0h+ValueName]; unsigned __int16 *
0x180264285  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18026428a  mov     esi, eax
0x18026428c  test    eax, eax
0x18026428e  js      short loc_180264301
0x180264290  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180264295  lea     rax, [rsp+2E0h+cbData]
0x18026429a  mov     qword ptr [rsp+2E0h+samDesired], rax; lpcbData
0x18026429f  lea     rdx, [rbp+1E0h+ValueName]; lpValueName
0x1802642a3  lea     rax, [rsp+2E0h+var_28C]
0x1802642a8  mov     dword ptr [rsp+2E0h+var_28C], 0
0x1802642b0  xor     r9d, r9d; lpType
0x1802642b3  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x1802642b8  xor     r8d, r8d; lpReserved
0x1802642bb  mov     [rsp+2E0h+cbData], edi
0x1802642bf  call    cs:__imp_RegQueryValueExW
0x1802642c6  nop     dword ptr [rax+rax+00h]
0x1802642cb  mov     esi, eax
0x1802642cd  test    eax, eax
0x1802642cf  jle     short loc_1802642DA
0x1802642d1  movzx   esi, ax
0x1802642d4  or      esi, 80070000h
0x1802642da  test    esi, esi
0x1802642dc  js      short loc_180264301
0x1802642de  mov     ecx, dword ptr [rsp+2E0h+var_28C]
0x1802642e2  mov     eax, ecx
0x1802642e4  xor     eax, r14d
0x1802642e7  test    eax, 0FFFFFFh
0x1802642ec  jnz     short loc_1802642F5
0x1802642ee  inc     ebx
0x1802642f0  jmp     loc_180264252
0x1802642f5  movsxd  rax, r15d
0x1802642f8  inc     r15d
0x1802642fb  mov     [rsp+rax*4+2E0h+var_268], ecx
0x1802642ff  jmp     short loc_1802642EE
0x180264301  inc     ebx
0x180264303  test    esi, esi
0x180264305  jns     loc_180264252
0x18026430b  xor     esi, esi
0x18026430d  mov     r14d, 0FFFFFFh
0x180264313  xor     ebx, ebx
0x180264315  cmp     ebx, r15d
0x180264318  jge     loc_1802643A7
0x18026431e  lea     r9, aColorhistory; "ColorHistory"
0x180264325  mov     [rsp+2E0h+dwOptions], esi
0x180264329  lea     r8, aSU_0; "%s%u"
0x180264330  mov     edx, 104h; unsigned __int64
0x180264335  lea     rcx, [rbp+1E0h+ValueName]; unsigned __int16 *
0x180264339  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18026433e  test    eax, eax
0x180264340  js      short loc_18026439D
0x180264342  movsxd  rax, ebx
0x180264345  lea     r8, [rsp+2E0h+var_268]
0x18026434a  xor     edx, edx
0x18026434c  lea     r8, [r8+rax*4]
0x180264350  cmp     edx, ebx
0x180264352  jge     short loc_18026436B
0x180264354  movsxd  rax, edx
0x180264357  mov     ecx, [rsp+rax*4+2E0h+var_268]
0x18026435b  xor     ecx, [r8]
0x18026435e  test    r14d, ecx
0x180264361  jz      short loc_180264367
0x180264363  inc     edx
0x180264365  jmp     short loc_180264350
0x180264367  inc     ebx
0x180264369  jmp     short loc_180264315
0x18026436b  mov     rcx, [rsp+2E0h+var_280]; hKey
0x180264370  lea     rdx, [rbp+1E0h+ValueName]; lpValueName
0x180264374  mov     [rsp+2E0h+samDesired], edi; cbData
0x180264378  mov     r9d, edi; dwType
0x18026437b  mov     qword ptr [rsp+2E0h+dwOptions], r8; lpData
0x180264380  xor     r8d, r8d; Reserved
0x180264383  call    cs:__imp_RegSetValueExW
0x18026438a  nop     dword ptr [rax+rax+00h]
0x18026438f  test    eax, eax
0x180264391  jle     short loc_18026439B
0x180264393  movzx   eax, ax
0x180264396  or      eax, 80070000h
0x18026439b  inc     esi
0x18026439d  inc     ebx
0x18026439f  test    eax, eax
0x1802643a1  jns     loc_180264315
0x1802643a7  xor     ebx, ebx
0x1802643a9  mov     edi, esi
0x1802643ab  cmp     edi, 5
0x1802643ae  jge     loc_18026446B
0x1802643b4  cmp     ebx, 5
0x1802643b7  jge     loc_18026446B
0x1802643bd  lea     r9, aColorhistory; "ColorHistory"
0x1802643c4  mov     [rsp+2E0h+dwOptions], edi
0x1802643c8  lea     r8, aSU_0; "%s%u"
0x1802643cf  mov     edx, 104h; unsigned __int64
0x1802643d4  lea     rcx, [rbp+1E0h+ValueName]; unsigned __int16 *
0x1802643d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802643dd  mov     edx, eax
0x1802643df  test    eax, eax
0x1802643e1  js      short loc_18026445F
0x1802643e3  mov     r10d, 4
0x1802643e9  cmp     ebx, 5
0x1802643ec  jge     short loc_18026445F
0x1802643ee  cmp     ebx, r10d
0x1802643f1  jnb     short loc_18026445F
0x1802643f3  movsxd  rcx, ebx
0x1802643f6  lea     r9, qword_18033BD50
0x1802643fd  xor     r8d, r8d
0x180264400  mov     r9d, [r9+rcx*4]
0x180264404  mov     dword ptr [rsp+2E0h+var_28C], r9d
0x180264409  cmp     r8d, esi
0x18026440c  jge     short loc_180264426
0x18026440e  movsxd  rax, r8d
0x180264411  mov     ecx, r9d
0x180264414  xor     ecx, [rsp+rax*4+2E0h+var_268]
0x180264418  test    r14d, ecx
0x18026441b  jz      short loc_180264422
0x18026441d  inc     r8d
0x180264420  jmp     short loc_180264409
0x180264422  inc     ebx
0x180264424  jmp     short loc_1802643E9
0x180264426  mov     rcx, [rsp+2E0h+var_280]; hKey
0x18026442b  lea     rax, [rsp+2E0h+var_28C]
0x180264430  mov     [rsp+2E0h+samDesired], r10d; cbData
0x180264435  lea     rdx, [rbp+1E0h+ValueName]; lpValueName
0x180264439  mov     r9d, r10d; dwType
0x18026443c  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x180264441  xor     r8d, r8d; Reserved
0x180264444  call    cs:__imp_RegSetValueExW
0x18026444b  nop     dword ptr [rax+rax+00h]
0x180264450  mov     edx, eax
0x180264452  test    eax, eax
0x180264454  jle     short loc_18026445F
0x180264456  movzx   edx, ax
0x180264459  or      edx, 80070000h
0x18026445f  inc     edi
0x180264461  inc     ebx
0x180264463  test    edx, edx
0x180264465  jns     loc_1802643AB
0x18026446b  mov     ebx, 4
0x180264470  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180264475  lea     rax, [rsp+2E0h+var_270]
0x18026447a  mov     [rsp+2E0h+samDesired], ebx; cbData
0x18026447e  lea     rdx, aAutocolor; "AutoColor"
0x180264485  mov     r9d, ebx; dwType
0x180264488  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x18026448d  xor     r8d, r8d; Reserved
0x180264490  mov     dword ptr [rsp+2E0h+var_270], r12d
0x180264495  call    cs:__imp_RegSetValueExW
0x18026449c  nop     dword ptr [rax+rax+00h]
0x1802644a1  xor     ebx, ebx
0x1802644a3  lea     rcx, [rsp+2E0h+var_280]
0x1802644a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1802644ad  lea     rcx, [rsp+2E0h+hKey]
0x1802644b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
  ... truncated ...
```
