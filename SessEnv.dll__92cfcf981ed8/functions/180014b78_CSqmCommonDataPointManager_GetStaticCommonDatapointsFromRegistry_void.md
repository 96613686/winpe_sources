# CSqmCommonDataPointManager::GetStaticCommonDatapointsFromRegistry(void)

- ea: `0x180014b78`
- end: `0x180014f1b`
- name: `?GetStaticCommonDatapointsFromRegistry@CSqmCommonDataPointManager@@QEAAJXZ`
- size: `931`
- prototype: `__int64 __fastcall(CSqmCommonDataPointManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180041b04`

## callees

- `0x180003f30`
- `0x180014b78`
- `0x18001a280`
- `0x18001a2a4`
- `0x18001a8d0`
- `0x180041d34`
- `0x180041e34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014bff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014bff`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180014d3d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180014d3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014eea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014eea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180014c8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180014c8b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x180014d55`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x180014d55`

## string_xrefs

- `0x180014c36`: `RegOpenKeyEx failed, %!winerr!`
- `0x180014e1f`: `Failed to allocate %d bytes for Common DWord Datapoint`
- `0x180014dd2`: `Failed to allocate %d bytes for Common DWord64 Datapoint`
- `0x180014bcf`: `Software\Microsoft\SQMClient\Windows\CommonDatapoints`
- `0x180014c11`: `No Common Datapoints Set in the registry`
- `0x180014cdc`: `Failed to allocate buffer for reading registry values`
- `0x180014e87`: `CacheCommonDatapoint call failed, %!hresult!`

## pseudocode

```c
__int64 __fastcall CSqmCommonDataPointManager::GetStaticCommonDatapointsFromRegistry(CSqmCommonDataPointManager *this)
{
  LSTATUS v2; // eax
  int v3; // ecx
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  BYTE *v6; // rsi
  DWORD i; // r14d
  LSTATUS v8; // eax
  __int64 v9; // rbx
  int v10; // r12d
  _DWORD *v11; // rax
  __int64 v12; // r8
  const char *v13; // rdx
  int v14; // ebx
  int v15; // r12d
  _QWORD *v16; // rax
  unsigned int v17; // eax
  signed int LastError; // eax
  int piRet; // [rsp+60h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-35h] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp-31h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-2Dh] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-29h] BYREF
  DWORD Type; // [rsp+74h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-21h] BYREF
  WCHAR ValueName; // [rsp+80h] [rbp-19h] BYREF
  __int128 v28; // [rsp+82h] [rbp-17h]
  __int128 v29; // [rsp+92h] [rbp-7h]
  _BYTE v30[30]; // [rsp+A2h] [rbp+9h] BYREF

  cValues = 0;
  cbData = 0;
  memset(v30, 0, sizeof(v30));
  cchValueName = 0;
  piRet = 0;
  Type = 0;
  cbMaxValueLen = 0;
  hKey = 0;
  ValueName = 0;
  v28 = 0;
  v29 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\SQMClient\\Windows\\CommonDatapoints",
         0,
         0xF003Fu,
         &hKey);
  if ( v2 )
  {
    if ( v2 != 2 )
    {
      if ( v2 > 0 )
        v4 = (unsigned __int16)v2 | 0x80070000;
      else
        v4 = v2;
      _DbgPrintMessage(8, "RegOpenKeyEx failed, %!winerr!", (unsigned int)v2);
      goto LABEL_54;
    }
    v3 = 8;
    goto LABEL_4;
  }
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    else
      v4 = v5;
    _DbgPrintMessage(8, "RegQueryInfoKey failed, %!winerr!", (unsigned int)v5);
    goto LABEL_54;
  }
  if ( !cValues )
  {
    v3 = 1;
LABEL_4:
    v4 = 0;
    _DbgPrintMessage(v3, "No Common Datapoints Set in the registry");
    goto LABEL_54;
  }
  cbMaxValueLen += 2;
  v6 = (BYTE *)operator new(cbMaxValueLen, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    _DbgPrintMessage(8, "Failed to allocate buffer for reading registry values");
    v4 = -2147024882;
    goto LABEL_54;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= cValues )
    {
      v4 = 0;
      goto LABEL_53;
    }
    cchValueName = 32;
    cbData = cbMaxValueLen - 2;
    v8 = RegEnumValueW(hKey, i, &ValueName, &cchValueName, 0, &Type, v6, &cbData);
    if ( v8 )
    {
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      else
        v4 = v8;
      _DbgPrintMessage(8, "RegEnumValue Failed, %!winerr!", (unsigned int)v8);
      goto LABEL_53;
    }
    if ( !StrToIntExW(&ValueName, 0, &piRet) )
      break;
    switch ( Type )
    {
      case 1u:
        *(_WORD *)&v6[2 * ((unsigned __int64)cbData >> 1)] = 0;
        v17 = CSqmCommonDataPointManager::CacheCommonStringDatapoint(this, piRet, (unsigned __int16 *)v6);
        goto LABEL_39;
      case 3u:
        v17 = CSqmCommonDataPointManager::CacheCommonStreamDatapoint(this, piRet, cbData, v6);
LABEL_39:
        v4 = v17;
        goto LABEL_40;
      case 4u:
        if ( cbData != 4 )
        {
LABEL_42:
          v4 = -2147467259;
          _DbgPrintMessage(8, "Inconsistent Reg key value for Datapoint %d", (unsigned int)piRet);
          goto LABEL_53;
        }
        v14 = *(_DWORD *)v6;
        v15 = piRet;
        v16 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
        if ( v16 )
        {
          v16[1] = 0;
          *(_DWORD *)v16 = v15;
          *((_DWORD *)v16 + 1) = v14;
          v16[1] = *((_QWORD *)this + 1);
          *((_QWORD *)this + 1) = v16;
          goto LABEL_30;
        }
        v12 = 16;
        v13 = "Failed to allocate %d bytes for Common DWord Datapoint";
        break;
      case 0xBu:
        if ( cbData != 8 )
          goto LABEL_42;
        v9 = *(_QWORD *)v6;
        v10 = piRet;
        v11 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        if ( v11 )
        {
          v11[1] = 0;
          *((_QWORD *)v11 + 2) = 0;
          *v11 = v10;
          *((_QWORD *)v11 + 1) = v9;
          *((_QWORD *)v11 + 2) = *(_QWORD *)this;
          *(_QWORD *)this = v11;
LABEL_30:
          v4 = 0;
          goto LABEL_40;
        }
        v12 = 24;
        v13 = "Failed to allocate %d bytes for Common DWord64 Datapoint";
        break;
      default:
        continue;
    }
    v4 = -2147024882;
    _DbgPrintMessage(8, v13, v12);
LABEL_40:
    if ( (v4 & 0x80000000) != 0 )
    {
      _DbgPrintMessage(8, "CacheCommonDatapoint call failed, %!hresult!", v4);
      goto LABEL_53;
    }
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "StrToIntEx failed, %!hresult!", v4);
LABEL_53:
  operator delete(v6);
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180014b78  mov     [rsp-8+arg_8], rbx
0x180014b7d  mov     [rsp-8+arg_10], rsi
0x180014b82  push    rbp
0x180014b83  push    r12
0x180014b85  push    r13
0x180014b87  push    r14
0x180014b89  push    r15
0x180014b8b  lea     rbp, [rsp-37h]
0x180014b90  sub     rsp, 0D0h
0x180014b97  mov     rax, cs:__security_cookie
0x180014b9e  xor     rax, rsp
0x180014ba1  mov     [rbp+57h+var_30], rax
0x180014ba5  xor     r13d, r13d
0x180014ba8  lea     rax, [rbp+57h+hKey]
0x180014bac  xorps   xmm0, xmm0
0x180014baf  mov     [rbp+57h+cValues], r13d
0x180014bb3  mov     r15, rcx
0x180014bb6  mov     [rbp+57h+cbData], r13d
0x180014bba  movups  xmmword ptr [rbp+57h+var_4E], xmm0
0x180014bbe  mov     r9d, 0F003Fh; samDesired
0x180014bc4  mov     [rbp+57h+cchValueName], r13d
0x180014bc8  xor     r8d, r8d; ulOptions
0x180014bcb  mov     [rbp+57h+piRet], r13d
0x180014bcf  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\SQMClient\\Windows"...
0x180014bd6  mov     [rbp+57h+Type], r13d
0x180014bda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014be1  mov     [rbp+57h+cbMaxValueLen], r13d
0x180014be5  movups  xmmword ptr [rbp+57h+var_4E+0Eh], xmm0
0x180014be9  mov     [rbp+57h+hKey], r13
0x180014bed  mov     [rbp+57h+ValueName], r13w
0x180014bf2  movups  [rbp+57h+var_6E], xmm0
0x180014bf6  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180014bfb  movups  [rbp+57h+var_5E], xmm0
0x180014bff  call    cs:__imp_RegOpenKeyExW
0x180014c05  test    eax, eax
0x180014c07  jz      short loc_180014C4F
0x180014c09  cmp     eax, 2
0x180014c0c  jnz     short loc_180014C25
0x180014c0e  lea     ecx, [rax+6]; int
0x180014c11  lea     rdx, aNoCommonDatapo; "No Common Datapoints Set in the registr"...
0x180014c18  mov     ebx, r13d
0x180014c1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014c20  jmp     loc_180014EE1
0x180014c25  test    eax, eax
0x180014c27  jg      short loc_180014C2D
0x180014c29  mov     ebx, eax
0x180014c2b  jmp     short loc_180014C36
0x180014c2d  movzx   ebx, ax
0x180014c30  or      ebx, 80070000h
0x180014c36  lea     rdx, aRegopenkeyexFa_1; "RegOpenKeyEx failed, %!winerr!"
0x180014c3d  mov     r8d, eax
0x180014c40  mov     ecx, 8; int
0x180014c45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014c4a  jmp     loc_180014EE1
0x180014c4f  mov     rcx, [rbp+57h+hKey]; hKey
0x180014c53  lea     rax, [rbp+57h+cbMaxValueLen]
0x180014c57  mov     [rsp+0F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180014c5c  xor     r9d, r9d; lpReserved
0x180014c5f  mov     [rsp+0F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180014c64  xor     r8d, r8d; lpcchClass
0x180014c67  mov     [rsp+0F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180014c6c  xor     edx, edx; lpClass
0x180014c6e  mov     [rsp+0F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180014c73  lea     rax, [rbp+57h+cValues]
0x180014c77  mov     [rsp+0F0h+lpcValues], rax; lpcValues
0x180014c7c  mov     [rsp+0F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180014c81  mov     [rsp+0F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180014c86  mov     [rsp+0F0h+phkResult], r13; lpcSubKeys
0x180014c8b  call    cs:__imp_RegQueryInfoKeyW
0x180014c91  test    eax, eax
0x180014c93  jz      short loc_180014CAD
0x180014c95  jg      short loc_180014C9B
0x180014c97  mov     ebx, eax
0x180014c99  jmp     short loc_180014CA4
0x180014c9b  movzx   ebx, ax
0x180014c9e  or      ebx, 80070000h
0x180014ca4  lea     rdx, aRegqueryinfoke; "RegQueryInfoKey failed, %!winerr!"
0x180014cab  jmp     short loc_180014C3D
0x180014cad  cmp     [rbp+57h+cValues], r13d
0x180014cb1  jnz     short loc_180014CBD
0x180014cb3  mov     ecx, 1
0x180014cb8  jmp     loc_180014C11
0x180014cbd  mov     eax, [rbp+57h+cbMaxValueLen]
0x180014cc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014cc7  add     eax, 2
0x180014cca  mov     ecx, eax; unsigned __int64
0x180014ccc  mov     [rbp+57h+cbMaxValueLen], eax
0x180014ccf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014cd4  mov     rsi, rax
0x180014cd7  test    rax, rax
0x180014cda  jnz     short loc_180014CF5
0x180014cdc  lea     rdx, aFailedToAlloca_4; "Failed to allocate buffer for reading r"...
0x180014ce3  lea     ecx, [rax+8]; int
0x180014ce6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014ceb  mov     ebx, 8007000Eh
0x180014cf0  jmp     loc_180014EE1
0x180014cf5  mov     r14d, r13d
0x180014cf8  cmp     r14d, [rbp+57h+cValues]
0x180014cfc  jnb     loc_180014ED6
0x180014d02  mov     eax, [rbp+57h+cbMaxValueLen]
0x180014d05  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180014d09  mov     rcx, [rbp+57h+hKey]; hKey
0x180014d0d  lea     r8, [rbp+57h+ValueName]; lpValueName
0x180014d11  add     eax, 0FFFFFFFEh
0x180014d14  mov     [rbp+57h+cchValueName], 20h ; ' '
0x180014d1b  mov     [rbp+57h+cbData], eax
0x180014d1e  mov     edx, r14d; dwIndex
0x180014d21  lea     rax, [rbp+57h+cbData]
0x180014d25  mov     [rsp+0F0h+lpcValues], rax; lpcbData
0x180014d2a  lea     rax, [rbp+57h+Type]
0x180014d2e  mov     [rsp+0F0h+lpcbMaxClassLen], rsi; lpData
0x180014d33  mov     [rsp+0F0h+lpcbMaxSubKeyLen], rax; lpType
0x180014d38  mov     [rsp+0F0h+phkResult], r13; lpReserved
0x180014d3d  call    cs:__imp_RegEnumValueW
0x180014d43  test    eax, eax
0x180014d45  jnz     loc_180014EB1
0x180014d4b  lea     r8, [rbp+57h+piRet]; piRet
0x180014d4f  xor     edx, edx; dwFlags
0x180014d51  lea     rcx, [rbp+57h+ValueName]; pszString
0x180014d55  call    cs:__imp_StrToIntExW
0x180014d5b  test    eax, eax
0x180014d5d  jz      loc_180014E90
0x180014d63  mov     eax, [rbp+57h+Type]
0x180014d66  sub     eax, 1
0x180014d69  jz      loc_180014E4B
0x180014d6f  sub     eax, 2
0x180014d72  jz      loc_180014E37
0x180014d78  sub     eax, 1
0x180014d7b  jz      short loc_180014DDB
0x180014d7d  cmp     eax, 7
0x180014d80  jnz     loc_180014E6A
0x180014d86  cmp     [rbp+57h+cbData], 8
0x180014d8a  jnz     loc_180014E72
0x180014d90  mov     rbx, [rsi]
0x180014d93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d9a  mov     r12d, [rbp+57h+piRet]
0x180014d9e  lea     ecx, [rax+11h]; unsigned __int64
0x180014da1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014da6  test    rax, rax
0x180014da9  jz      short loc_180014DCC
0x180014dab  mov     [rax+4], r13d
0x180014daf  mov     [rax+10h], r13
0x180014db3  mov     [rax], r12d
0x180014db6  mov     [rax+8], rbx
0x180014dba  mov     rcx, [r15]
0x180014dbd  mov     [rax+10h], rcx
0x180014dc1  mov     [r15], rax
0x180014dc4  mov     ebx, r13d
0x180014dc7  jmp     loc_180014E66
0x180014dcc  mov     r8d, 18h
0x180014dd2  lea     rdx, aFailedToAlloca_3; "Failed to allocate %d bytes for Common "...
0x180014dd9  jmp     short loc_180014E26
0x180014ddb  cmp     [rbp+57h+cbData], 4
0x180014ddf  jnz     loc_180014E72
0x180014de5  mov     ebx, [rsi]
0x180014de7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014dee  mov     r12d, [rbp+57h+piRet]
0x180014df2  mov     ecx, 10h; unsigned __int64
0x180014df7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014dfc  test    rax, rax
0x180014dff  jz      short loc_180014E19
0x180014e01  mov     [rax+8], r13
0x180014e05  mov     [rax], r12d
0x180014e08  mov     [rax+4], ebx
0x180014e0b  mov     rcx, [r15+8]
0x180014e0f  mov     [rax+8], rcx
0x180014e13  mov     [r15+8], rax
0x180014e17  jmp     short loc_180014DC4
0x180014e19  mov     r8d, 10h
0x180014e1f  lea     rdx, aFailedToAlloca_5; "Failed to allocate %d bytes for Common "...
0x180014e26  mov     ecx, 8; int
0x180014e2b  mov     ebx, 8007000Eh
0x180014e30  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014e35  jmp     short loc_180014E66
0x180014e37  mov     r8d, [rbp+57h+cbData]; unsigned int
0x180014e3b  mov     r9, rsi; unsigned __int8 *
0x180014e3e  mov     edx, [rbp+57h+piRet]; unsigned int
0x180014e41  mov     rcx, r15; this
0x180014e44  call    ?CacheCommonStreamDatapoint@CSqmCommonDataPointManager@@QEAAJKKPEAE@Z; CSqmCommonDataPointManager::CacheCommonStreamDatapoint(ulong,ulong,uchar *)
0x180014e49  jmp     short loc_180014E64
0x180014e4b  mov     ecx, [rbp+57h+cbData]
0x180014e4e  mov     r8, rsi; unsigned __int16 *
0x180014e51  shr     rcx, 1
0x180014e54  mov     [rsi+rcx*2], r13w
0x180014e59  mov     rcx, r15; this
0x180014e5c  mov     edx, [rbp+57h+piRet]; unsigned int
0x180014e5f  call    ?CacheCommonStringDatapoint@CSqmCommonDataPointManager@@QEAAJKPEAG@Z; CSqmCommonDataPointManager::CacheCommonStringDatapoint(ulong,ushort *)
0x180014e64  mov     ebx, eax
0x180014e66  test    ebx, ebx
0x180014e68  js      short loc_180014E84
0x180014e6a  inc     r14d
0x180014e6d  jmp     loc_180014CF8
0x180014e72  mov     r8d, [rbp+57h+piRet]
0x180014e76  lea     rdx, aInconsistentRe; "Inconsistent Reg key value for Datapoin"...
0x180014e7d  mov     ebx, 80004005h
0x180014e82  jmp     short loc_180014ECA
0x180014e84  mov     r8d, ebx
0x180014e87  lea     rdx, aCachecommondat; "CacheCommonDatapoint call failed, %!hre"...
0x180014e8e  jmp     short loc_180014ECA
0x180014e90  call    cs:__imp_GetLastError
0x180014e96  mov     ebx, eax
0x180014e98  test    eax, eax
0x180014e9a  jle     short loc_180014EA5
0x180014e9c  movzx   ebx, ax
0x180014e9f  or      ebx, 80070000h
0x180014ea5  mov     r8d, ebx
0x180014ea8  lea     rdx, aStrtointexFail; "StrToIntEx failed, %!hresult!"
0x180014eaf  jmp     short loc_180014ECA
0x180014eb1  jg      short loc_180014EB7
0x180014eb3  mov     ebx, eax
0x180014eb5  jmp     short loc_180014EC0
0x180014eb7  movzx   ebx, ax
0x180014eba  or      ebx, 80070000h
0x180014ec0  mov     r8d, eax
0x180014ec3  lea     rdx, aRegenumvalueFa; "RegEnumValue Failed, %!winerr!"
0x180014eca  mov     ecx, 8; int
0x180014ecf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014ed4  jmp     short loc_180014ED9
0x180014ed6  mov     ebx, r13d
0x180014ed9  mov     rcx, rsi; Block
0x180014edc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014ee1  mov     rcx, [rbp+57h+hKey]; hKey
0x180014ee5  test    rcx, rcx
0x180014ee8  jz      short loc_180014EF0
0x180014eea  call    cs:__imp_RegCloseKey
0x180014ef0  mov     eax, ebx
0x180014ef2  mov     rcx, [rbp+57h+var_30]
0x180014ef6  xor     rcx, rsp; StackCookie
0x180014ef9  call    __security_check_cookie
0x180014efe  lea     r11, [rsp+0F0h+var_20]
0x180014f06  mov     rbx, [r11+38h]
0x180014f0a  mov     rsi, [r11+40h]
0x180014f0e  mov     rsp, r11
0x180014f11  pop     r15
0x180014f13  pop     r14
0x180014f15  pop     r13
0x180014f17  pop     r12
0x180014f19  pop     rbp
0x180014f1a  retn
```
