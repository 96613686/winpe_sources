# Wns::ConnectionProviderConfig::Load(void)

- ea: `0x180014950`
- end: `0x180014c4b`
- name: `?Load@ConnectionProviderConfig@Wns@@SA?AV12@XZ`
- size: `763`
- prototype: `GUID *__fastcall(GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800214d0`

## callees

- `0x180006160`
- `0x1800109d4`
- `0x180014950`
- `0x180014c54`
- `0x180021048`
- `0x180023e2c`
- `0x180032de0`
- `0x180032e04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014b8f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014b8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014bcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014bcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014c22`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180014b59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001498c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014abd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001498c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014abd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014a61`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014a61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800149ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800149ea`

## string_xrefs

- `0x180014a27`: `Error enumerating configuration keys for ConnectionProvider`

## pseudocode

```c
GUID *__fastcall Wns::ConnectionProviderConfig::Load(GUID *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // eax
  unsigned int v5; // r8d
  DWORD i; // ebx
  LSTATUS v7; // eax
  bool v8; // al
  unsigned int v9; // eax
  unsigned int v10; // r8d
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  HKEY v13; // rcx
  HRESULT v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-49h]
  unsigned int phkResulta; // [rsp+20h] [rbp-49h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-41h]
  BYTE Data[4]; // [rsp+60h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-5h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-1h] BYREF
  DWORD v22; // [rsp+6Ch] [rbp+3h] BYREF
  HKEY v23; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+Fh] BYREF
  LPWSTR lpName[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v26; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+E0h] [rbp+77h] BYREF
  int v30; // [rsp+E8h] [rbp+7Fh] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\WPN", 0, 0x20019u, &hKey);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x20, v3, (const char *)v2, phkResult);
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2A, v5, (const char *)v4, phkResulta);
  ++cbMaxSubKeyLen;
  *(_OWORD *)lpName = 0;
  v26 = 0;
  std::vector<unsigned short>::_Resize<std::_Value_init_tag>(lpName, cbMaxSubKeyLen);
  for ( i = 0; ; ++i )
  {
    if ( i >= cSubKeys )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
        (const char *)0x8000FFFFLL,
        phkResulta);
    cchName = cbMaxSubKeyLen;
    v7 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    v8 = !v7 || i == cSubKeys - 1 && v7 == 259;
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)v8,
      (bool)"Error enumerating configuration keys for ConnectionProvider",
      lpcbMaxSubKeyLen);
    v23 = 0;
    v9 = RegOpenKeyExW(hKey, lpName[0], 0, 0x20019u, &v23);
    v11 = retaddr;
    if ( v9 )
    {
      v12 = 70;
LABEL_14:
      wil::details::in1diag3::_Log_Win32(v11, (void *)v12, v10, (const char *)v9, phkResulta);
      goto LABEL_15;
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    v9 = RegQueryValueExW(v23, L"Flags", 0, 0, Data, &cbData);
    v11 = retaddr;
    if ( v9 )
    {
      v12 = 80;
      goto LABEL_14;
    }
    v30 = 0;
    v22 = 4;
    v9 = RegQueryValueExW(v23, L"Enabled", 0, 0, (LPBYTE)&v30, &v22);
    v11 = retaddr;
    if ( v9 )
    {
      v12 = 90;
      goto LABEL_14;
    }
    if ( !v30 )
    {
      v13 = v23;
      if ( !v23 )
        continue;
LABEL_33:
      RegCloseKey(v13);
      continue;
    }
    *a1 = 0;
    a1[1].Data1 = 4;
    v14 = CLSIDFromString(lpName[0], a1);
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
        (const char *)(unsigned int)v14,
        phkResulta);
      goto LABEL_15;
    }
    if ( !v14 )
      break;
LABEL_15:
    v13 = v23;
    if ( v23 )
      goto LABEL_33;
  }
  a1[1].Data1 = *(_DWORD *)Data;
  if ( v23 )
    RegCloseKey(v23);
  if ( lpName[0] )
  {
    std::_Deallocate<16>(lpName[0], 2 * ((signed __int64)(v26 - (unsigned __int64)lpName[0]) >> 1));
    *(_OWORD *)lpName = 0;
    v26 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180014950  push    rbp
0x180014952  push    rbx
0x180014953  push    rsi
0x180014954  push    rdi
0x180014955  push    r14
0x180014957  lea     rbp, [rsp-37h]
0x18001495c  sub     rsp, 0A0h
0x180014963  mov     rdi, rcx
0x180014966  xor     esi, esi
0x180014968  mov     [rbp+57h+hKey], rsi
0x18001496c  lea     rax, [rbp+57h+hKey]
0x180014970  mov     [rsp+0C0h+phkResult], rax; unsigned int
0x180014975  mov     r9d, 20019h; samDesired
0x18001497b  xor     r8d, r8d; ulOptions
0x18001497e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\WPN"
0x180014985  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001498c  call    cs:__imp_RegOpenKeyExW
0x180014992  mov     rcx, [rbp+5Fh]; this
0x180014996  test    eax, eax
0x180014998  jz      short loc_1800149A8
0x18001499a  mov     r9d, eax; char *
0x18001499d  mov     edx, 20h ; ' '; void *
0x1800149a2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800149a8  mov     [rbp+57h+cSubKeys], esi
0x1800149ab  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x1800149ae  mov     [rsp+0C0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800149b3  mov     [rsp+0C0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800149b8  mov     [rsp+0C0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800149bd  mov     [rsp+0C0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800149c2  mov     [rsp+0C0h+lpcValues], rsi; lpcValues
0x1800149c7  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800149cc  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800149d0  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800149d5  lea     rax, [rbp+57h+cSubKeys]
0x1800149d9  mov     [rsp+0C0h+phkResult], rax; int
0x1800149de  xor     r9d, r9d; lpReserved
0x1800149e1  xor     r8d, r8d; lpcchClass
0x1800149e4  xor     edx, edx; lpClass
0x1800149e6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800149ea  call    cs:__imp_RegQueryInfoKeyW
0x1800149f0  mov     rcx, [rbp+5Fh]; this
0x1800149f4  test    eax, eax
0x1800149f6  jz      short loc_180014A06
0x1800149f8  mov     r9d, eax; char *
0x1800149fb  mov     edx, 2Ah ; '*'; void *
0x180014a00  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180014a06  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180014a09  inc     eax
0x180014a0b  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x180014a0e  mov     edx, eax
0x180014a10  xorps   xmm0, xmm0
0x180014a13  movdqu  xmmword ptr [rbp+57h+lpName], xmm0
0x180014a18  mov     [rbp+57h+var_30], rsi
0x180014a1c  lea     rcx, [rbp+57h+lpName]
0x180014a20  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180014a25  mov     ebx, esi
0x180014a27  lea     r14, aErrorEnumerati; "Error enumerating configuration keys fo"...
0x180014a2e  xchg    ax, ax
0x180014a30  cmp     ebx, [rbp+57h+cSubKeys]
0x180014a33  jnb     loc_180014C2F
0x180014a39  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180014a3c  mov     [rbp+57h+cchName], eax
0x180014a3f  mov     [rsp+0C0h+lpcValues], rsi; lpftLastWriteTime
0x180014a44  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpcchClass
0x180014a49  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rsi; char *
0x180014a4e  mov     [rsp+0C0h+phkResult], rsi; lpReserved
0x180014a53  lea     r9, [rbp+57h+cchName]; lpcchName
0x180014a57  mov     r8, [rbp+57h+lpName]; lpName
0x180014a5b  mov     edx, ebx; dwIndex
0x180014a5d  mov     rcx, [rbp+57h+hKey]; hKey
0x180014a61  call    cs:__imp_RegEnumKeyExW
0x180014a67  test    eax, eax
0x180014a69  jz      short loc_180014A7F
0x180014a6b  mov     ecx, [rbp+57h+cSubKeys]
0x180014a6e  dec     ecx
0x180014a70  cmp     ebx, ecx
0x180014a72  jnz     short loc_180014A7B
0x180014a74  cmp     eax, 103h
0x180014a79  jz      short loc_180014A7F
0x180014a7b  xor     eax, eax
0x180014a7d  jmp     short loc_180014A81
0x180014a7f  mov     al, 1
0x180014a81  mov     rcx, [rbp+5Fh]; this
0x180014a85  mov     [rsp+0C0h+phkResult], r14; bool
0x180014a8a  movzx   r9d, al; char *
0x180014a8e  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180014a95  mov     edx, 3Dh ; '='; void *
0x180014a9a  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180014a9f  mov     [rbp+57h+var_50], rsi
0x180014aa3  lea     rax, [rbp+57h+var_50]
0x180014aa7  mov     [rsp+0C0h+phkResult], rax; unsigned int
0x180014aac  mov     r9d, 20019h; samDesired
0x180014ab2  xor     r8d, r8d; ulOptions
0x180014ab5  mov     rdx, [rbp+57h+lpName]; lpSubKey
0x180014ab9  mov     rcx, [rbp+57h+hKey]; hKey
0x180014abd  call    cs:__imp_RegOpenKeyExW
0x180014ac3  mov     rcx, [rbp+5Fh]; this
0x180014ac7  test    eax, eax
0x180014ac9  jz      short loc_180014AEA
0x180014acb  mov     edx, 46h ; 'F'; void *
0x180014ad0  mov     r9d, eax; char *
0x180014ad3  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180014ad8  mov     rcx, [rbp+57h+var_50]
0x180014adc  test    rcx, rcx
0x180014adf  jnz     loc_180014C22
0x180014ae5  jmp     loc_180014C28
0x180014aea  mov     dword ptr [rbp+57h+Data], esi
0x180014aed  mov     [rbp+57h+cbData], 4
0x180014af4  lea     rax, [rbp+57h+cbData]
0x180014af8  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180014afd  lea     rax, [rbp+57h+Data]
0x180014b01  mov     [rsp+0C0h+phkResult], rax; lpData
0x180014b06  xor     r9d, r9d; lpType
0x180014b09  xor     r8d, r8d; lpReserved
0x180014b0c  lea     rdx, ValueName; "Flags"
0x180014b13  mov     rcx, [rbp+57h+var_50]; hKey
0x180014b17  call    cs:__imp_RegQueryValueExW
0x180014b1d  mov     rcx, [rbp+5Fh]
0x180014b21  test    eax, eax
0x180014b23  jz      short loc_180014B2C
0x180014b25  mov     edx, 50h ; 'P'
0x180014b2a  jmp     short loc_180014AD0
0x180014b2c  mov     [rbp+57h+arg_18], esi
0x180014b2f  mov     [rbp+57h+var_54], 4
0x180014b36  lea     rax, [rbp+57h+var_54]
0x180014b3a  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180014b3f  lea     rax, [rbp+57h+arg_18]
0x180014b43  mov     [rsp+0C0h+phkResult], rax; int
0x180014b48  xor     r9d, r9d; lpType
0x180014b4b  xor     r8d, r8d; lpReserved
0x180014b4e  lea     rdx, aEnabled; "Enabled"
0x180014b55  mov     rcx, [rbp+57h+var_50]; hKey
0x180014b59  call    cs:__imp_RegQueryValueExW
0x180014b5f  mov     rcx, [rbp+5Fh]
0x180014b63  test    eax, eax
0x180014b65  jz      short loc_180014B71
0x180014b67  mov     edx, 5Ah ; 'Z'
0x180014b6c  jmp     loc_180014AD0
0x180014b71  cmp     [rbp+57h+arg_18], 0
0x180014b75  jz      loc_180014C19
0x180014b7b  xorps   xmm0, xmm0
0x180014b7e  movups  xmmword ptr [rdi], xmm0
0x180014b81  mov     dword ptr [rdi+10h], 4
0x180014b88  mov     rdx, rdi; pclsid
0x180014b8b  mov     rcx, [rbp+57h+lpName]; lpsz
0x180014b8f  call    cs:__imp_CLSIDFromString
0x180014b95  mov     rcx, [rbp+5Fh]; this
0x180014b99  test    eax, eax
0x180014b9b  jns     short loc_180014BB6
0x180014b9d  mov     r9d, eax; char *
0x180014ba0  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180014ba7  mov     edx, 5Fh ; '_'; void *
0x180014bac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014bb1  jmp     loc_180014AD8
0x180014bb6  jnz     loc_180014AD8
0x180014bbc  mov     eax, dword ptr [rbp+57h+Data]
0x180014bbf  mov     [rdi+10h], eax
0x180014bc2  mov     rcx, [rbp+57h+var_50]; hKey
0x180014bc6  test    rcx, rcx
0x180014bc9  jz      short loc_180014BD2
0x180014bcb  call    cs:__imp_RegCloseKey
0x180014bd1  nop
0x180014bd2  mov     rcx, [rbp+57h+lpName]
0x180014bd6  test    rcx, rcx
0x180014bd9  jz      short loc_180014BF9
0x180014bdb  mov     rdx, [rbp+57h+var_30]
0x180014bdf  sub     rdx, rcx
0x180014be2  sar     rdx, 1
0x180014be5  add     rdx, rdx
0x180014be8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014bed  xorps   xmm0, xmm0
0x180014bf0  movdqu  xmmword ptr [rbp+57h+lpName], xmm0
0x180014bf5  mov     [rbp+57h+var_30], rsi
0x180014bf9  mov     rcx, [rbp+57h+hKey]; hKey
0x180014bfd  test    rcx, rcx
0x180014c00  jz      short loc_180014C08
0x180014c02  call    cs:__imp_RegCloseKey
0x180014c08  mov     rax, rdi
0x180014c0b  add     rsp, 0A0h
0x180014c12  pop     r14
0x180014c14  pop     rdi
0x180014c15  pop     rsi
0x180014c16  pop     rbx
0x180014c17  pop     rbp
0x180014c18  retn
0x180014c19  mov     rcx, [rbp+57h+var_50]; hKey
0x180014c1d  test    rcx, rcx
0x180014c20  jz      short loc_180014C28
0x180014c22  call    cs:__imp_RegCloseKey
0x180014c28  inc     ebx
0x180014c2a  jmp     loc_180014A30
0x180014c2f  mov     rcx, [rbp+5Fh]; this
0x180014c33  mov     r9d, 8000FFFFh; char *
0x180014c39  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180014c40  mov     edx, 66h ; 'f'; void *
0x180014c45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
