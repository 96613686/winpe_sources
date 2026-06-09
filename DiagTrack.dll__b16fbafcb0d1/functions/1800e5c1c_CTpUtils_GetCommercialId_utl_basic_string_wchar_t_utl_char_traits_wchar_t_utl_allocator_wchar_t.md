# CTpUtils::GetCommercialId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800e5c1c`
- end: `0x1800e5e6e`
- name: `?GetCommercialId@CTpUtils@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180191a0c`

## callees

- `0x1800e2674`
- `0x1800e3c84`
- `0x1800e3f00`
- `0x1800e4410`
- `0x1800e4454`
- `0x1800e4a40`
- `0x1800e5c1c`
- `0x18020afa4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e5d6f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800e5d6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5caa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e5caa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5c84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5dd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5c84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e5dd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5cec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5d4c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5cec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e5d4c`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x1800e5df0`
- `DiagnosticDataSettings!TelGetLocalAllowTelemetryRegPath` at `0x1800e5df0`

## string_xrefs

- `0x1800e5cbc`: `CommercialId`
- `0x1800e5d2e`: `CommercialId`
- `0x1800e5dfb`: `CommercialId`

## pseudocode

```c
__int64 __fastcall CTpUtils::GetCommercialId(__int64 a1)
{
  signed int String; // ebx
  HKEY v3; // rcx
  HKEY v4; // rbx
  LSTATUS ValueW; // eax
  size_t v6; // rax
  _BYTE *v7; // rdx
  _BYTE *v8; // r8
  const WCHAR *LocalAllowTelemetryRegPath; // rax
  PVOID pvData; // [rsp+40h] [rbp-40h] BYREF
  char *v12; // [rsp+48h] [rbp-38h]
  char v13; // [rsp+50h] [rbp-30h] BYREF
  void *v14; // [rsp+60h] [rbp-20h] BYREF
  _BYTE *v15; // [rsp+68h] [rbp-18h]
  char v16; // [rsp+70h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+20h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v14);
  pcbData = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pvData);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(&pvData) )
    goto LABEL_2;
  v3 = hKey;
  hKey = 0;
  if ( v3 )
    RegCloseKey(v3);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\DataCollection", 0, 0x101u, &hKey)
    || (v4 = hKey, pcbData = 0, RegGetValueW(hKey, 0, L"CommercialId", 2u, 0, 0, &pcbData)) )
  {
LABEL_14:
    String = UtilExpandEnvironmentStrings((LPCWSTR)pvData);
    if ( !String )
      goto LABEL_16;
    goto LABEL_15;
  }
  v12 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v4, 0, L"CommercialId", 2u, 0, pvData, &pcbData);
    String = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        String = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_15;
    }
    v6 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
    if ( v6 > (v12 - (_BYTE *)pvData) >> 1 )
      __int2c();
    v12 = (char *)pvData + 2 * v6;
    *(_WORD *)v12 = 0;
    goto LABEL_14;
  }
LABEL_2:
  String = -2147024882;
LABEL_15:
  v15 = v14;
  *(_WORD *)v14 = 0;
LABEL_16:
  if ( pvData != &v13 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  if ( String < 0 || (v7 = v14, v8 = v15, v14 == v15) )
  {
    LocalAllowTelemetryRegPath = (const WCHAR *)TelGetLocalAllowTelemetryRegPath();
    String = UtilRegGetString(HKEY_LOCAL_MACHINE, LocalAllowTelemetryRegPath, L"CommercialId", (__int64)&v14, 1, 1);
    if ( String < 0 )
      goto LABEL_25;
    v8 = v15;
    v7 = v14;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, v7, (v8 - v7) >> 1);
LABEL_25:
  if ( v14 != &v16 )
    operator delete(v14, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800e5c1c  mov     [rsp-8+arg_0], rbx
0x1800e5c21  mov     [rsp-8+arg_18], rdi
0x1800e5c26  push    rbp
0x1800e5c27  mov     rbp, rsp
0x1800e5c2a  sub     rsp, 80h
0x1800e5c31  mov     rdi, rcx
0x1800e5c34  lea     rcx, [rbp+var_20]
0x1800e5c38  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800e5c3d  lea     rcx, [rbp+var_40]
0x1800e5c41  mov     [rbp+arg_8], 0
0x1800e5c48  mov     [rbp+hKey], 0
0x1800e5c50  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800e5c55  lea     rdx, Src
0x1800e5c5c  lea     rcx, [rbp+var_40]
0x1800e5c60  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800e5c65  test    al, al
0x1800e5c67  jnz     short loc_1800E5C73
0x1800e5c69  mov     ebx, 8007000Eh
0x1800e5c6e  jmp     loc_1800E5DAA
0x1800e5c73  mov     rcx, [rbp+hKey]; hKey
0x1800e5c77  mov     [rbp+hKey], 0
0x1800e5c7f  test    rcx, rcx
0x1800e5c82  jz      short loc_1800E5C8A
0x1800e5c84  call    cs:__imp_RegCloseKey
0x1800e5c8a  lea     rax, [rbp+hKey]
0x1800e5c8e  mov     r9d, 101h; samDesired
0x1800e5c94  xor     r8d, r8d; ulOptions
0x1800e5c97  mov     [rsp+80h+phkResult], rax; phkResult
0x1800e5c9c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800e5ca3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e5caa  call    cs:__imp_RegOpenKeyExW
0x1800e5cb0  test    eax, eax
0x1800e5cb2  jnz     loc_1800E5D97
0x1800e5cb8  mov     rbx, [rbp+hKey]
0x1800e5cbc  lea     r8, aCommercialid_0; "CommercialId"
0x1800e5cc3  mov     [rbp+arg_8], eax
0x1800e5cc6  mov     r9d, 2; dwFlags
0x1800e5ccc  lea     rax, [rbp+arg_8]
0x1800e5cd0  xor     edx, edx; lpSubKey
0x1800e5cd2  mov     [rsp+80h+pcbData], rax; pcbData
0x1800e5cd7  mov     rcx, rbx; hkey
0x1800e5cda  mov     [rsp+80h+pvData], 0; pvData
0x1800e5ce3  mov     [rsp+80h+phkResult], 0; pdwType
0x1800e5cec  call    cs:__imp_RegGetValueW
0x1800e5cf2  test    eax, eax
0x1800e5cf4  jnz     loc_1800E5D97
0x1800e5cfa  mov     rcx, [rbp+var_40]
0x1800e5cfe  mov     [rbp+var_38], rcx
0x1800e5d02  mov     [rcx], ax
0x1800e5d05  lea     rcx, [rbp+var_40]
0x1800e5d09  mov     edx, [rbp+arg_8]
0x1800e5d0c  shr     rdx, 1
0x1800e5d0f  inc     rdx
0x1800e5d12  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800e5d17  test    al, al
0x1800e5d19  jz      loc_1800E5C69
0x1800e5d1f  lea     rax, [rbp+arg_8]
0x1800e5d23  mov     r9d, 2; dwFlags
0x1800e5d29  mov     [rsp+80h+pcbData], rax; pcbData
0x1800e5d2e  lea     r8, aCommercialid_0; "CommercialId"
0x1800e5d35  mov     rax, [rbp+var_40]
0x1800e5d39  xor     edx, edx; lpSubKey
0x1800e5d3b  mov     [rsp+80h+pvData], rax; pvData
0x1800e5d40  mov     rcx, rbx; hkey
0x1800e5d43  mov     [rsp+80h+phkResult], 0; pdwType
0x1800e5d4c  call    cs:__imp_RegGetValueW
0x1800e5d52  mov     ebx, eax
0x1800e5d54  test    eax, eax
0x1800e5d56  jz      short loc_1800E5D65
0x1800e5d58  jle     short loc_1800E5DAA
0x1800e5d5a  movzx   ebx, ax
0x1800e5d5d  or      ebx, 80070000h
0x1800e5d63  jmp     short loc_1800E5DAA
0x1800e5d65  mov     edx, [rbp+arg_8]
0x1800e5d68  mov     rcx, [rbp+var_40]; Source
0x1800e5d6c  shr     rdx, 1; MaxCount
0x1800e5d6f  call    cs:__imp_wcsnlen
0x1800e5d75  mov     rcx, [rbp+var_38]
0x1800e5d79  mov     rdx, [rbp+var_40]
0x1800e5d7d  sub     rcx, rdx
0x1800e5d80  sar     rcx, 1
0x1800e5d83  cmp     rax, rcx
0x1800e5d86  jbe     short loc_1800E5D8A
0x1800e5d88  int     2Ch; Windows NT - assertion failure
0x1800e5d8a  lea     rcx, [rdx+rax*2]
0x1800e5d8e  xor     eax, eax
0x1800e5d90  mov     [rbp+var_38], rcx
0x1800e5d94  mov     [rcx], ax
0x1800e5d97  mov     rcx, [rbp+var_40]; lpSrc
0x1800e5d9b  lea     rdx, [rbp+var_20]
0x1800e5d9f  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800e5da4  mov     ebx, eax
0x1800e5da6  test    eax, eax
0x1800e5da8  jz      short loc_1800E5DB7
0x1800e5daa  mov     rcx, [rbp+var_20]
0x1800e5dae  xor     eax, eax
0x1800e5db0  mov     [rbp+var_18], rcx
0x1800e5db4  mov     [rcx], ax
0x1800e5db7  mov     rcx, [rbp+var_40]; void *
0x1800e5dbb  lea     rax, [rbp+var_30]
0x1800e5dbf  cmp     rcx, rax
0x1800e5dc2  jz      short loc_1800E5DD0
0x1800e5dc4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e5dcb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5dd0  mov     rcx, [rbp+hKey]; hKey
0x1800e5dd4  test    rcx, rcx
0x1800e5dd7  jz      short loc_1800E5DDF
0x1800e5dd9  call    cs:__imp_RegCloseKey
0x1800e5ddf  test    ebx, ebx
0x1800e5de1  js      short loc_1800E5DF0
0x1800e5de3  mov     rdx, [rbp+var_20]
0x1800e5de7  mov     r8, [rbp+var_18]
0x1800e5deb  cmp     rdx, r8
0x1800e5dee  jnz     short loc_1800E5E30
0x1800e5df0  call    cs:__imp_TelGetLocalAllowTelemetryRegPath
0x1800e5df6  mov     byte ptr [rsp+80h+pcbData], 1; char
0x1800e5dfb  lea     r8, aCommercialid_0; "CommercialId"
0x1800e5e02  mov     rdx, rax; lpSubKey
0x1800e5e05  mov     byte ptr [rsp+80h+pvData], 1; char
0x1800e5e0a  lea     rax, [rbp+var_20]
0x1800e5e0e  xor     r9d, r9d
0x1800e5e11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e5e18  mov     [rsp+80h+phkResult], rax; __int64
0x1800e5e1d  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x1800e5e22  mov     ebx, eax
0x1800e5e24  test    eax, eax
0x1800e5e26  js      short loc_1800E5E3E
0x1800e5e28  mov     r8, [rbp+var_18]
0x1800e5e2c  mov     rdx, [rbp+var_20]
0x1800e5e30  sub     r8, rdx
0x1800e5e33  mov     rcx, rdi
0x1800e5e36  sar     r8, 1
0x1800e5e39  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800e5e3e  mov     rcx, [rbp+var_20]; void *
0x1800e5e42  lea     rax, [rbp+var_10]
0x1800e5e46  cmp     rcx, rax
0x1800e5e49  jz      short loc_1800E5E57
0x1800e5e4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e5e52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5e57  lea     r11, [rsp+80h+var_s0]
0x1800e5e5f  mov     eax, ebx
0x1800e5e61  mov     rbx, [r11+10h]
0x1800e5e65  mov     rdi, [r11+28h]
0x1800e5e69  mov     rsp, r11
0x1800e5e6c  pop     rbp
0x1800e5e6d  retn
```
