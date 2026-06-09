# DpspLoadLocalGroupPolicy

- ea: `0x180016914`
- end: `0x180016bce`
- name: `DpspLoadLocalGroupPolicy`
- size: `698`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800086e8`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009044`
- `0x180009090`
- `0x180009fb0`
- `0x180016914`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016b92`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016a39`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016a39`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800169c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800169c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016a75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ab6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016ab6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b00`

## pseudocode

```c
__int64 __fastcall DpspLoadLocalGroupPolicy(HKEY hKey, __int64 a2)
{
  WCHAR *v4; // rsi
  int v5; // r8d
  LSTATUS v6; // eax
  signed int v7; // ebx
  DWORD i; // edi
  __int64 v9; // rax
  __int64 *v10; // rcx
  LPDWORD lpcSubKeys; // [rsp+20h] [rbp-49h]
  DWORD cbData; // [rsp+60h] [rbp-9h] BYREF
  BYTE v14[4]; // [rsp+64h] [rbp-5h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-1h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+Fh] BYREF
  BYTE Data[4]; // [rsp+7Ch] [rbp+13h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp+17h] BYREF
  __int128 v20; // [rsp+88h] [rbp+1Fh] BYREF

  cchName = 39;
  hKeya = 0;
  cSubKeys = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v14 = 0;
  v20 = 0;
  cbData = 0;
  ftLastWriteTime = 0;
  v4 = (WCHAR *)WdipAlloc(78);
  if ( !v4 )
  {
    v5 = 393;
    goto LABEL_27;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v5 = 410;
    LODWORD(lpcSubKeys) = (unsigned __int16)v7;
    goto LABEL_28;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    if ( hKeya )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
    cchName = 39;
    if ( RegEnumKeyExW(hKey, i, v4, &cchName, 0, 0, 0, &ftLastWriteTime) )
      continue;
    v7 = WdipStringToGuid(v4, &v20);
    if ( v7 < 0 )
      continue;
    if ( RegOpenKeyExW(hKey, v4, 0, 0x20019u, &hKeya) )
      continue;
    if ( !hKeya )
      continue;
    cbData = 4;
    if ( RegQueryValueExW(hKeya, L"ScenarioExecutionEnabled", 0, 0, Data, &cbData) )
      continue;
    if ( *(_DWORD *)Data )
    {
      if ( *(_DWORD *)Data == 1 )
      {
        cbData = 4;
        if ( RegQueryValueExW(hKeya, L"EnabledScenarioExecutionLevel", 0, 0, v14, &cbData)
          || (*(_DWORD *)v14 & 0xFFFFFFFD) == 0 )
        {
          continue;
        }
      }
    }
    else
    {
      *(_DWORD *)v14 = 0;
    }
    v9 = WdipAlloc(40);
    if ( !v9 )
    {
      v5 = 508;
LABEL_27:
      LODWORD(lpcSubKeys) = 14;
      v7 = -2147024882;
LABEL_28:
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsgp.cpp",
        (__int64)L"DpspLoadLocalGroupPolicy",
        v5,
        (const wchar_t *)L"Error = %d",
        lpcSubKeys);
      break;
    }
    *(_OWORD *)(v9 + 16) = v20;
    *(_DWORD *)(v9 + 32) = *(_DWORD *)v14;
    v10 = *(__int64 **)(a2 + 8);
    if ( *v10 != a2 )
      __fastfail(3u);
    *(_QWORD *)v9 = a2;
    *(_QWORD *)(v9 + 8) = v10;
    *v10 = v9;
    *(_QWORD *)(a2 + 8) = v9;
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  WdipFree(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016914  mov     [rsp-8+arg_10], rbx
0x180016919  mov     [rsp-8+arg_18], rsi
0x18001691e  push    rbp
0x18001691f  push    rdi
0x180016920  push    r12
0x180016922  push    r14
0x180016924  push    r15
0x180016926  lea     rbp, [rsp-37h]
0x18001692b  sub     rsp, 0A0h
0x180016932  mov     rax, cs:__security_cookie
0x180016939  xor     rax, rsp
0x18001693c  mov     [rbp+57h+var_28], rax
0x180016940  xor     r12d, r12d
0x180016943  mov     [rbp+57h+cchName], 27h ; '''
0x18001694a  mov     r15, rcx
0x18001694d  mov     [rbp+57h+hKey], r12
0x180016951  xorps   xmm0, xmm0
0x180016954  mov     [rbp+57h+cSubKeys], r12d
0x180016958  mov     r14, rdx
0x18001695b  mov     dword ptr [rbp+57h+Data], r12d
0x18001695f  lea     ecx, [r12+4Eh]
0x180016964  mov     dword ptr [rbp+57h+var_5C], r12d
0x180016968  movups  [rbp+57h+var_38], xmm0
0x18001696c  mov     [rbp+57h+cbData], r12d
0x180016970  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r12
0x180016974  call    WdipAlloc
0x180016979  mov     rsi, rax
0x18001697c  test    rax, rax
0x18001697f  jnz     short loc_18001698C
0x180016981  mov     r8d, 189h
0x180016987  jmp     loc_180016B62
0x18001698c  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016991  lea     rax, [rbp+57h+cSubKeys]
0x180016995  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001699a  xor     r9d, r9d; lpReserved
0x18001699d  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800169a2  xor     r8d, r8d; lpcchClass
0x1800169a5  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800169aa  xor     edx, edx; lpClass
0x1800169ac  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x1800169b1  mov     rcx, r15; hKey
0x1800169b4  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800169b9  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800169be  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x1800169c3  call    cs:__imp_RegQueryInfoKeyW
0x1800169c9  mov     ebx, eax
0x1800169cb  test    eax, eax
0x1800169cd  jle     short loc_1800169D8
0x1800169cf  movzx   ebx, ax
0x1800169d2  or      ebx, 80070000h
0x1800169d8  test    ebx, ebx
0x1800169da  jns     short loc_1800169EE
0x1800169dc  movzx   eax, bx
0x1800169df  mov     r8d, 19Ah
0x1800169e5  mov     dword ptr [rsp+0C0h+lpcSubKeys], eax
0x1800169e9  jmp     loc_180016B6F
0x1800169ee  mov     edi, r12d
0x1800169f1  cmp     [rbp+57h+cSubKeys], r12d
0x1800169f5  jbe     loc_180016B89
0x1800169fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800169ff  test    rcx, rcx
0x180016a02  jz      short loc_180016A0E
0x180016a04  call    cs:__imp_RegCloseKey
0x180016a0a  mov     [rbp+57h+hKey], r12
0x180016a0e  lea     rax, [rbp+57h+ftLastWriteTime]
0x180016a12  mov     [rbp+57h+cchName], 27h ; '''
0x180016a19  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x180016a1e  lea     r9, [rbp+57h+cchName]; lpcchName
0x180016a22  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcchClass
0x180016a27  mov     r8, rsi; lpName
0x180016a2a  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpClass
0x180016a2f  mov     edx, edi; dwIndex
0x180016a31  mov     rcx, r15; hKey
0x180016a34  mov     [rsp+0C0h+lpcSubKeys], r12; lpReserved
0x180016a39  call    cs:__imp_RegEnumKeyExW
0x180016a3f  test    eax, eax
0x180016a41  jnz     loc_180016B48
0x180016a47  lea     rdx, [rbp+57h+var_38]
0x180016a4b  mov     rcx, rsi
0x180016a4e  call    WdipStringToGuid
0x180016a53  mov     ebx, eax
0x180016a55  test    eax, eax
0x180016a57  js      loc_180016B48
0x180016a5d  lea     rax, [rbp+57h+hKey]
0x180016a61  mov     r9d, 20019h; samDesired
0x180016a67  xor     r8d, r8d; ulOptions
0x180016a6a  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x180016a6f  mov     rdx, rsi; lpSubKey
0x180016a72  mov     rcx, r15; hKey
0x180016a75  call    cs:__imp_RegOpenKeyExW
0x180016a7b  test    eax, eax
0x180016a7d  jnz     loc_180016B48
0x180016a83  mov     rcx, [rbp+57h+hKey]; hKey
0x180016a87  test    rcx, rcx
0x180016a8a  jz      loc_180016B48
0x180016a90  lea     rax, [rbp+57h+cbData]
0x180016a94  mov     [rbp+57h+cbData], 4
0x180016a9b  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180016aa0  lea     rdx, aScenarioexecut; "ScenarioExecutionEnabled"
0x180016aa7  lea     rax, [rbp+57h+Data]
0x180016aab  xor     r9d, r9d; lpType
0x180016aae  xor     r8d, r8d; lpReserved
0x180016ab1  mov     [rsp+0C0h+lpcSubKeys], rax; lpData
0x180016ab6  call    cs:__imp_RegQueryValueExW
0x180016abc  test    eax, eax
0x180016abe  jnz     loc_180016B48
0x180016ac4  mov     eax, dword ptr [rbp+57h+Data]
0x180016ac7  test    eax, eax
0x180016ac9  jnz     short loc_180016AD1
0x180016acb  mov     dword ptr [rbp+57h+var_5C], r12d
0x180016acf  jmp     short loc_180016B13
0x180016ad1  cmp     eax, 1
0x180016ad4  jnz     short loc_180016B13
0x180016ad6  mov     rcx, [rbp+57h+hKey]; hKey
0x180016ada  lea     rax, [rbp+57h+cbData]
0x180016ade  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180016ae3  lea     rdx, aEnabledscenari; "EnabledScenarioExecutionLevel"
0x180016aea  lea     rax, [rbp+57h+var_5C]
0x180016aee  mov     [rbp+57h+cbData], 4
0x180016af5  xor     r9d, r9d; lpType
0x180016af8  mov     [rsp+0C0h+lpcSubKeys], rax; lpData
0x180016afd  xor     r8d, r8d; lpReserved
0x180016b00  call    cs:__imp_RegQueryValueExW
0x180016b06  test    eax, eax
0x180016b08  jnz     short loc_180016B48
0x180016b0a  test    dword ptr [rbp+57h+var_5C], 0FFFFFFFDh
0x180016b11  jz      short loc_180016B48
0x180016b13  mov     ecx, 28h ; '('
0x180016b18  call    WdipAlloc
0x180016b1d  test    rax, rax
0x180016b20  jz      short loc_180016B5C
0x180016b22  movups  xmm0, [rbp+57h+var_38]
0x180016b26  movdqu  xmmword ptr [rax+10h], xmm0
0x180016b2b  mov     ecx, dword ptr [rbp+57h+var_5C]
0x180016b2e  mov     [rax+20h], ecx
0x180016b31  mov     rcx, [r14+8]
0x180016b35  cmp     [rcx], r14
0x180016b38  jnz     short loc_180016B55
0x180016b3a  mov     [rax], r14
0x180016b3d  mov     [rax+8], rcx
0x180016b41  mov     [rcx], rax
0x180016b44  mov     [r14+8], rax
0x180016b48  inc     edi
0x180016b4a  cmp     edi, [rbp+57h+cSubKeys]
0x180016b4d  jb      loc_1800169FB
0x180016b53  jmp     short loc_180016B89
0x180016b55  mov     ecx, 3
0x180016b5a  int     29h; Win8: RtlFailFast(ecx)
0x180016b5c  mov     r8d, 1FCh; int
0x180016b62  mov     dword ptr [rsp+0C0h+lpcSubKeys], 0Eh; Args
0x180016b6a  mov     ebx, 8007000Eh
0x180016b6f  lea     r9, aErrorD; "Error = %d"
0x180016b76  lea     rdx, aDpsploadlocalg; "DpspLoadLocalGroupPolicy"
0x180016b7d  lea     rcx, aClientcoreBase; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016b84  call    WdipTraceError
0x180016b89  mov     rcx, [rbp+57h+hKey]; hKey
0x180016b8d  test    rcx, rcx
0x180016b90  jz      short loc_180016B9C
0x180016b92  call    cs:__imp_RegCloseKey
0x180016b98  mov     [rbp+57h+hKey], r12
0x180016b9c  mov     rcx, rsi
0x180016b9f  call    WdipFree
0x180016ba4  mov     eax, ebx
0x180016ba6  mov     rcx, [rbp+57h+var_28]
0x180016baa  xor     rcx, rsp; StackCookie
0x180016bad  call    __security_check_cookie
0x180016bb2  lea     r11, [rsp+0C0h+var_20]
0x180016bba  mov     rbx, [r11+40h]
0x180016bbe  mov     rsi, [r11+48h]
0x180016bc2  mov     rsp, r11
0x180016bc5  pop     r15
0x180016bc7  pop     r14
0x180016bc9  pop     r12
0x180016bcb  pop     rdi
0x180016bcc  pop     rbp
0x180016bcd  retn
```
