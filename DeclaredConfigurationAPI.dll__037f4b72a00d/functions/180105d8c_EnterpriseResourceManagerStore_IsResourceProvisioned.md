# EnterpriseResourceManagerStore_IsResourceProvisioned

- ea: `0x180105d8c`
- end: `0x18010631b`
- name: `EnterpriseResourceManagerStore_IsResourceProvisioned`
- size: `1423`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180107940`

## callees

- `0x18000b9e0`
- `0x18000be80`
- `0x18000bf00`
- `0x18000bf4c`
- `0x1800a2fac`
- `0x1800a42c8`
- `0x180105d8c`
- `0x180106d50`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180106105`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180106105`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180106067`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801060ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180106067`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801060ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105efd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105f70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105fe5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105efd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105f70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105fe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010612a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801062a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010612a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106148`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106286`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180106296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801062a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105e57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105f32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010601d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105e57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105f32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180105fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010601d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105e23`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180105e23`
- `OLEAUT32!__imp_SysFreeString` at `0x1801062b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1801062b1`

## pseudocode

```c
__int64 __fastcall EnterpriseResourceManagerStore_IsResourceProvisioned(__int64 a1, ERMScopeData **a2, _DWORD *a3)
{
  DWORD v3; // r12d
  __int64 v4; // r14
  BYTE *v5; // rsi
  ERMScopeData *v6; // rdi
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  signed int v10; // ebx
  int i; // r15d
  LSTATUS v12; // eax
  bool v13; // cc
  DWORD j; // r13d
  DWORD k; // r14d
  unsigned __int64 v16; // rax
  BYTE *v17; // rax
  ERMScopeData *v18; // rax
  _DWORD *v19; // rax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v24; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  _DWORD *v31; // [rsp+88h] [rbp-78h]
  ERMScopeData **v32; // [rsp+90h] [rbp-70h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR v35[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR ValueName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v3 = 0;
  v31 = a3;
  v32 = a2;
  v30 = a1;
  v4 = a1;
  hKey = 0;
  v5 = 0;
  v25 = 0;
  v6 = 0;
  v24 = 0;
  phkResult = 0;
  cchName = 260;
  cbData = 0;
  v27 = 0;
  bstrString = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v10 = -2147024809;
    goto LABEL_56;
  }
  *a2 = 0;
  *a3 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  if ( !IsStateSeparationEnabled )
    v8 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20119u, &hKey);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
LABEL_8:
      v10 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_56;
  }
  v10 = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 0;
    if ( i > 2 )
      goto LABEL_56;
    v10 = AddURIPrefix(v4, (unsigned int)i, &v27);
    if ( v10 >= 0 )
      break;
LABEL_39:
    ;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v27 + 64LL))(v27, 0, 0, &bstrString);
  if ( v10 < 0 )
    goto LABEL_56;
  v26 = 0;
LABEL_14:
  cchName = 260;
  v12 = RegEnumKeyExW(hKey, (DWORD)v5, Name, &cchName, 0, 0, 0, 0);
  if ( v12 == 259 )
  {
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    v4 = v30;
    goto LABEL_39;
  }
  v13 = v12 <= 0;
  if ( v12 || (v12 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &phkResult), v13 = v12 <= 0, v12) )
  {
LABEL_51:
    if ( v13 )
      v10 = v12;
    else
      v10 = (unsigned __int16)v12 | 0x80070000;
    v5 = 0;
    goto LABEL_56;
  }
  for ( j = 0; ; ++j )
  {
    cchName = 260;
    v12 = RegEnumKeyExW(phkResult, j, SubKey, &cchName, 0, 0, 0, 0);
    if ( v12 == 259 )
    {
      RegCloseKey(phkResult);
      LODWORD(v5) = v26 + 1;
      phkResult = 0;
      ++v26;
      goto LABEL_14;
    }
    v13 = v12 <= 0;
    if ( v12 )
      goto LABEL_51;
    v12 = RegOpenKeyExW(phkResult, SubKey, 0, 0x20119u, &v24);
    v13 = v12 <= 0;
    if ( v12 )
      goto LABEL_51;
LABEL_21:
    cchName = 260;
    v12 = RegEnumKeyExW(v24, v3, v35, &cchName, 0, 0, 0, 0);
    if ( v12 != 259 )
      break;
    RegCloseKey(v24);
    v3 = 0;
    v24 = 0;
  }
  if ( v12 || (v12 = RegOpenKeyExW(v24, v35, 0, 0x20119u, &v25)) != 0 )
  {
LABEL_50:
    v13 = v12 <= 0;
    goto LABEL_51;
  }
  for ( k = 0; ; ++k )
  {
    cbData = 0;
    cchName = 260;
    v12 = RegEnumValueW(v25, k, ValueName, &cchName, 0, 0, 0, &cbData);
    if ( v12 == 259 )
    {
      RegCloseKey(v25);
      ++v3;
      v25 = 0;
      goto LABEL_21;
    }
    if ( v12 )
      goto LABEL_50;
    v16 = 2 * ((unsigned __int64)cbData >> 1);
    if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
      v16 = -1;
    v17 = (BYTE *)operator new[](v16, (const struct std::nothrow_t *)std::nothrow);
    v5 = v17;
    if ( !v17 )
    {
      v10 = -2147024882;
      goto LABEL_56;
    }
    *(_WORD *)v17 = 0;
    cchName = 260;
    v9 = RegEnumValueW(v25, k, ValueName, &cchName, 0, 0, v17, &cbData);
    if ( v9 )
      break;
    if ( !(unsigned int)_o__wcsicmp(v5, bstrString) )
    {
      v18 = (ERMScopeData *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
      v6 = v18;
      if ( !v18 )
      {
        v10 = -2147024882;
        goto LABEL_46;
      }
      *((_QWORD *)v18 + 1) = 0;
      *(_DWORD *)v18 = 1;
      *((_QWORD *)v18 + 2) = 0;
      *((_QWORD *)v18 + 3) = 0;
      *((_QWORD *)v18 + 4) = 0;
      *((_QWORD *)v18 + 5) = 0;
      *((_DWORD *)v18 + 12) = 0;
      v10 = Copy_String((char *)v18 + 16, Name);
      if ( v10 >= 0 )
      {
        v10 = Copy_String((char *)v6 + 24, SubKey);
        if ( v10 >= 0 )
        {
          v10 = Copy_String((char *)v6 + 32, v35);
          if ( v10 >= 0 )
          {
            v19 = v31;
            *((_DWORD *)v6 + 11) = i;
            *v19 = 1;
            *v32 = v6;
LABEL_46:
            v6 = 0;
            goto LABEL_56;
          }
        }
      }
      goto LABEL_56;
    }
    operator delete(v5);
  }
  if ( v9 > 0 )
    goto LABEL_8;
  v10 = v9;
LABEL_56:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v24 )
    RegCloseKey(v24);
  if ( v25 )
    RegCloseKey(v25);
  if ( hKey )
    RegCloseKey(hKey);
  SysFreeString(bstrString);
  operator delete(v5);
  if ( v6 )
  {
    ERMScopeData::~ERMScopeData(v6);
    operator delete(v6);
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180105d8c  mov     [rsp-8+arg_18], rbx
0x180105d91  push    rbp
0x180105d92  push    rsi
0x180105d93  push    rdi
0x180105d94  push    r12
0x180105d96  push    r13
0x180105d98  push    r14
0x180105d9a  push    r15
0x180105d9c  lea     rbp, [rsp-7F0h]
0x180105da4  sub     rsp, 8F0h
0x180105dab  mov     rax, cs:__security_cookie
0x180105db2  xor     rax, rsp
0x180105db5  mov     [rbp+820h+var_40], rax
0x180105dbc  xor     r12d, r12d
0x180105dbf  mov     [rbp+820h+var_898], r8
0x180105dc3  mov     [rbp+820h+var_890], rdx
0x180105dc7  mov     rax, rdx
0x180105dca  mov     [rbp+820h+var_8A0], rcx
0x180105dce  mov     r14, rcx
0x180105dd1  mov     [rsp+920h+hKey], r12
0x180105dd6  mov     esi, r12d
0x180105dd9  mov     [rsp+920h+var_8C8], r12
0x180105dde  mov     edi, r12d
0x180105de1  mov     [rsp+920h+var_8D0], r12
0x180105de6  mov     [rsp+920h+var_8D8], r12
0x180105deb  mov     [rsp+920h+cchName], 104h
0x180105df3  mov     [rsp+920h+cbData], r12d
0x180105df8  mov     [rsp+920h+var_8B8], r12
0x180105dfd  mov     [rsp+920h+bstrString], r12
0x180105e02  test    rcx, rcx
0x180105e05  jz      loc_180106267
0x180105e0b  test    rax, rax
0x180105e0e  jz      loc_180106267
0x180105e14  test    r8, r8
0x180105e17  jz      loc_180106267
0x180105e1d  mov     [rdx], r12
0x180105e20  mov     [r8], r12d
0x180105e23  call    cs:__imp_RtlIsStateSeparationEnabled
0x180105e29  lea     rcx, aSoftwareMicros_22; "Software\\Microsoft\\EnterpriseResource"...
0x180105e30  mov     r9d, 20119h; samDesired
0x180105e36  test    al, al
0x180105e38  lea     rdx, aOsdataSoftware_61; "OSData\\Software\\Microsoft\\Enterprise"...
0x180105e3f  lea     rax, [rsp+920h+hKey]
0x180105e44  cmovz   rdx, rcx; lpSubKey
0x180105e48  mov     [rsp+920h+phkResult], rax; phkResult
0x180105e4d  xor     r8d, r8d; ulOptions
0x180105e50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180105e57  call    cs:__imp_RegOpenKeyExW
0x180105e5d  mov     ebx, eax
0x180105e5f  test    eax, eax
0x180105e61  jz      short loc_180105E77
0x180105e63  jle     loc_18010626C
0x180105e69  movzx   ebx, ax
0x180105e6c  or      ebx, 80070000h
0x180105e72  jmp     loc_18010626C
0x180105e77  mov     ebx, r12d
0x180105e7a  mov     r15d, r12d
0x180105e7d  mov     rsi, r12
0x180105e80  cmp     r15d, 2
0x180105e84  jg      loc_18010626C
0x180105e8a  lea     r8, [rsp+920h+var_8B8]
0x180105e8f  mov     edx, r15d
0x180105e92  mov     rcx, r14
0x180105e95  call    AddURIPrefix
0x180105e9a  mov     ebx, eax
0x180105e9c  test    eax, eax
0x180105e9e  js      loc_18010619C
0x180105ea4  mov     rcx, [rsp+920h+var_8B8]
0x180105ea9  lea     r9, [rsp+920h+bstrString]
0x180105eae  xor     r8d, r8d
0x180105eb1  xor     edx, edx
0x180105eb3  mov     rax, [rcx]
0x180105eb6  mov     rax, [rax+40h]
0x180105eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105ebf  mov     ebx, eax
0x180105ec1  test    eax, eax
0x180105ec3  js      loc_18010626C
0x180105ec9  mov     [rsp+920h+var_8C0], r12d
0x180105ece  mov     r14d, 104h
0x180105ed4  mov     rcx, [rsp+920h+hKey]; hKey
0x180105ed9  lea     r9, [rsp+920h+cchName]; lpcchName
0x180105ede  mov     [rsp+920h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180105ee3  lea     r8, [rbp+820h+Name]; lpName
0x180105ee7  mov     [rsp+920h+lpcchClass], r12; lpcchClass
0x180105eec  mov     edx, esi; dwIndex
0x180105eee  mov     [rsp+920h+lpClass], r12; lpClass
0x180105ef3  mov     [rsp+920h+phkResult], r12; lpReserved
0x180105ef8  mov     [rsp+920h+cchName], r14d
0x180105efd  call    cs:__imp_RegEnumKeyExW
0x180105f03  cmp     eax, 103h
0x180105f08  jz      loc_18010617D
0x180105f0e  test    eax, eax
0x180105f10  jnz     loc_180106253
0x180105f16  mov     rcx, [rsp+920h+hKey]; hKey
0x180105f1b  lea     rax, [rsp+920h+var_8D8]
0x180105f20  mov     r9d, 20119h; samDesired
0x180105f26  mov     [rsp+920h+phkResult], rax; phkResult
0x180105f2b  xor     r8d, r8d; ulOptions
0x180105f2e  lea     rdx, [rbp+820h+Name]; lpSubKey
0x180105f32  call    cs:__imp_RegOpenKeyExW
0x180105f38  test    eax, eax
0x180105f3a  jnz     loc_180106253
0x180105f40  mov     r13d, r12d
0x180105f43  mov     rcx, [rsp+920h+var_8D8]; hKey
0x180105f48  lea     r9, [rsp+920h+cchName]; lpcchName
0x180105f4d  mov     [rsp+920h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180105f52  lea     r8, [rbp+820h+SubKey]; lpName
0x180105f59  mov     [rsp+920h+lpcchClass], r12; lpcchClass
0x180105f5e  mov     edx, r13d; dwIndex
0x180105f61  mov     [rsp+920h+lpClass], r12; lpClass
0x180105f66  mov     [rsp+920h+phkResult], r12; lpReserved
0x180105f6b  mov     [rsp+920h+cchName], r14d
0x180105f70  call    cs:__imp_RegEnumKeyExW
0x180105f76  cmp     eax, 103h
0x180105f7b  jz      loc_18010615E
0x180105f81  test    eax, eax
0x180105f83  jnz     loc_180106253
0x180105f89  mov     rcx, [rsp+920h+var_8D8]; hKey
0x180105f8e  lea     rax, [rsp+920h+var_8D0]
0x180105f93  mov     r9d, 20119h; samDesired
0x180105f99  mov     [rsp+920h+phkResult], rax; phkResult
0x180105f9e  xor     r8d, r8d; ulOptions
0x180105fa1  lea     rdx, [rbp+820h+SubKey]; lpSubKey
0x180105fa8  call    cs:__imp_RegOpenKeyExW
0x180105fae  test    eax, eax
0x180105fb0  jnz     loc_180106253
0x180105fb6  xor     esi, esi
0x180105fb8  mov     rcx, [rsp+920h+var_8D0]; hKey
0x180105fbd  lea     r9, [rsp+920h+cchName]; lpcchName
0x180105fc2  mov     [rsp+920h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180105fc7  lea     r8, [rbp+820h+var_460]; lpName
0x180105fce  mov     [rsp+920h+lpcchClass], rsi; lpcchClass
0x180105fd3  mov     edx, r12d; dwIndex
0x180105fd6  mov     [rsp+920h+lpClass], rsi; lpClass
0x180105fdb  mov     [rsp+920h+phkResult], rsi; lpReserved
0x180105fe0  mov     [rsp+920h+cchName], r14d
0x180105fe5  call    cs:__imp_RegEnumKeyExW
0x180105feb  cmp     eax, 103h
0x180105ff0  jz      loc_180106143
0x180105ff6  test    eax, eax
0x180105ff8  jnz     loc_18010624E
0x180105ffe  mov     rcx, [rsp+920h+var_8D0]; hKey
0x180106003  lea     rax, [rsp+920h+var_8C8]
0x180106008  mov     r9d, 20119h; samDesired
0x18010600e  mov     [rsp+920h+phkResult], rax; phkResult
0x180106013  xor     r8d, r8d; ulOptions
0x180106016  lea     rdx, [rbp+820h+var_460]; lpSubKey
0x18010601d  call    cs:__imp_RegOpenKeyExW
0x180106023  test    eax, eax
0x180106025  jnz     loc_18010624E
0x18010602b  mov     r14d, esi
0x18010602e  mov     rcx, [rsp+920h+var_8C8]; hKey
0x180106033  lea     rax, [rsp+920h+cbData]
0x180106038  mov     [rsp+920h+lpftLastWriteTime], rax; lpcbData
0x18010603d  lea     r9, [rsp+920h+cchName]; lpcchValueName
0x180106042  mov     [rsp+920h+lpcchClass], rsi; lpData
0x180106047  lea     r8, [rbp+820h+ValueName]; lpValueName
0x18010604e  mov     [rsp+920h+lpClass], rsi; lpType
0x180106053  mov     edx, r14d; dwIndex
0x180106056  mov     [rsp+920h+phkResult], rsi; lpReserved
0x18010605b  mov     [rsp+920h+cbData], esi
0x18010605f  mov     [rsp+920h+cchName], 104h
0x180106067  call    cs:__imp_RegEnumValueW
0x18010606d  cmp     eax, 103h
0x180106072  jz      loc_180106125
0x180106078  test    eax, eax
0x18010607a  jnz     loc_18010624E
0x180106080  mov     ecx, [rsp+920h+cbData]
0x180106084  mov     eax, 2
0x180106089  shr     rcx, 1
0x18010608c  mul     rcx
0x18010608f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180106096  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010609d  cmovb   rax, rcx
0x1801060a1  mov     rcx, rax; unsigned __int64
0x1801060a4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801060a9  mov     rsi, rax
0x1801060ac  test    rax, rax
0x1801060af  jz      loc_180106247
0x1801060b5  xor     ecx, ecx
0x1801060b7  lea     r9, [rsp+920h+cchName]; lpcchValueName
0x1801060bc  mov     [rax], cx
0x1801060bf  lea     r8, [rbp+820h+ValueName]; lpValueName
0x1801060c6  lea     rax, [rsp+920h+cbData]
0x1801060cb  mov     [rsp+920h+cchName], 104h
0x1801060d3  mov     [rsp+920h+lpftLastWriteTime], rax; lpcbData
0x1801060d8  mov     edx, r14d; dwIndex
0x1801060db  mov     [rsp+920h+lpcchClass], rsi; lpData
0x1801060e0  mov     [rsp+920h+lpClass], rcx; lpType
0x1801060e5  mov     [rsp+920h+phkResult], rcx; lpReserved
0x1801060ea  mov     rcx, [rsp+920h+var_8C8]; hKey
0x1801060ef  call    cs:__imp_RegEnumValueW
0x1801060f5  test    eax, eax
0x1801060f7  jnz     loc_18010623D
0x1801060fd  mov     rdx, [rsp+920h+bstrString]
0x180106102  mov     rcx, rsi
0x180106105  call    cs:__imp__o__wcsicmp
0x18010610b  test    eax, eax
0x18010610d  jz      loc_1801061A4
0x180106113  mov     rcx, rsi; Block
0x180106116  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010611b  xor     esi, esi
0x18010611d  inc     r14d
0x180106120  jmp     loc_18010602E
0x180106125  mov     rcx, [rsp+920h+var_8C8]; hKey
0x18010612a  call    cs:__imp_RegCloseKey
0x180106130  inc     r12d
0x180106133  mov     [rsp+920h+var_8C8], rsi
0x180106138  mov     r14d, 104h
0x18010613e  jmp     loc_180105FB8
0x180106143  mov     rcx, [rsp+920h+var_8D0]; hKey
0x180106148  call    cs:__imp_RegCloseKey
0x18010614e  xor     r12d, r12d
0x180106151  mov     [rsp+920h+var_8D0], r12
0x180106156  inc     r13d
0x180106159  jmp     loc_180105F43
0x18010615e  mov     rcx, [rsp+920h+var_8D8]; hKey
0x180106163  call    cs:__imp_RegCloseKey
0x180106169  mov     esi, [rsp+920h+var_8C0]
0x18010616d  inc     esi
0x18010616f  mov     [rsp+920h+var_8D8], r12
0x180106174  mov     [rsp+920h+var_8C0], esi
0x180106178  jmp     loc_180105ED4
0x18010617d  mov     rcx, [rsp+920h+var_8B8]
0x180106182  test    rcx, rcx
0x180106185  jz      short loc_180106198
0x180106187  mov     rax, [rcx]
0x18010618a  mov     rax, [rax+10h]
0x18010618e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106193  mov     [rsp+920h+var_8B8], r12
0x180106198  mov     r14, [rbp+820h+var_8A0]
0x18010619c  inc     r15d
0x18010619f  jmp     loc_180105E7D
0x1801061a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801061ab  mov     ecx, 38h ; '8'; unsigned __int64
0x1801061b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801061b5  xor     r12d, r12d
0x1801061b8  mov     rdi, rax
0x1801061bb  test    rax, rax
0x1801061be  jz      short loc_180106233
0x1801061c0  lea     r14d, [r12+1]
0x1801061c5  mov     [rax+8], r12
0x1801061c9  lea     rcx, [rax+10h]
0x1801061cd  mov     [rax], r14d
0x1801061d0  lea     rdx, [rbp+820h+Name]
0x1801061d4  mov     [rax+10h], r12
0x1801061d8  mov     [rax+18h], r12
0x1801061dc  mov     [rax+20h], r12
0x1801061e0  mov     [rax+28h], r12
0x1801061e4  mov     [rax+30h], r12d
0x1801061e8  call    Copy_String
0x1801061ed  mov     ebx, eax
0x1801061ef  test    eax, eax
0x1801061f1  js      short loc_18010626C
0x1801061f3  lea     rcx, [rdi+18h]
0x1801061f7  lea     rdx, [rbp+820h+SubKey]
0x1801061fe  call    Copy_String
0x180106203  mov     ebx, eax
0x180106205  test    eax, eax
0x180106207  js      short loc_18010626C
0x180106209  lea     rcx, [rdi+20h]
0x18010620d  lea     rdx, [rbp+820h+var_460]
0x180106214  call    Copy_String
0x180106219  mov     ebx, eax
0x18010621b  test    eax, eax
0x18010621d  js      short loc_18010626C
0x18010621f  mov     rax, [rbp+820h+var_898]
0x180106223  mov     [rdi+2Ch], r15d
0x180106227  mov     [rax], r14d
0x18010622a  mov     rax, [rbp+820h+var_890]
0x18010622e  mov     [rax], rdi
0x180106231  jmp     short loc_180106238
0x180106233  mov     ebx, 8007000Eh
0x180106238  mov     rdi, r12
0x18010623b  jmp     short loc_18010626C
0x18010623d  jg      loc_180105E69
0x180106243  mov     ebx, eax
0x180106245  jmp     short loc_18010626C
0x180106247  mov     ebx, 8007000Eh
0x18010624c  jmp     short loc_18010626C
0x18010624e  xor     r12d, r12d
0x180106251  test    eax, eax
0x180106253  jg      short loc_180106259
0x180106255  mov     ebx, eax
0x180106257  jmp     short loc_180106262
0x180106259  movzx   ebx, ax
0x18010625c  or      ebx, 80070000h
0x180106262  mov     rsi, r12
0x180106265  jmp     short loc_18010626C
0x180106267  mov     ebx, 80070057h
0x18010626c  mov     rcx, [rsp+920h+var_8D8]; hKey
0x180106271  test    rcx, rcx
0x180106274  jz      short loc_18010627C
0x180106276  call    cs:__imp_RegCloseKey
0x18010627c  mov     rcx, [rsp+920h+var_8D0]; hKey
0x180106281  test    rcx, rcx
0x180106284  jz      short loc_18010628C
0x180106286  call    cs:__imp_RegCloseKey
0x18010628c  mov     rcx, [rsp+920h+var_8C8]; hKey
0x180106291  test    rcx, rcx
  ... truncated ...
```
