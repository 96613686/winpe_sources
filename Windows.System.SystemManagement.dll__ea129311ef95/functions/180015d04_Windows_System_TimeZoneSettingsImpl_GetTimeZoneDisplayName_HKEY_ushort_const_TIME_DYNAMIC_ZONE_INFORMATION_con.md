# Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(HKEY__ *,ushort const *,_TIME_DYNAMIC_ZONE_INFORMATION * const,HSTRING__ * *)

- ea: `0x180015d04`
- end: `0x180015e88`
- name: `?GetTimeZoneDisplayName@TimeZoneSettingsImpl@System@Windows@@AEAAJPEAUHKEY__@@PEBGQEAU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAPEAUHSTRING__@@@Z`
- size: `388`
- prototype: `int(Windows::System::TimeZoneSettingsImpl *__hidden this, HKEY, const unsigned __int16 *, struct _TIME_DYNAMIC_ZONE_INFORMATION *const, HSTRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800161bc`
- `0x180017820`

## callees

- `0x180002dc0`
- `0x180015d04`
- `0x180016080`
- `0x180016c48`
- `0x180017348`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015e5c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015e19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015e19`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180015db4`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180015db4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d6e`

## pseudocode

```c
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(
        Windows::System::TimeZoneSettingsImpl *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _TIME_DYNAMIC_ZONE_INFORMATION *const a4,
        HSTRING *a5)
{
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS MUIStringW; // eax
  unsigned __int64 v9; // rcx
  int LastError; // eax
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  void **v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszOutBuf[128]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  string = 0;
  pszOutBuf[0] = 0;
  v14 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  v6 = RegOpenKeyExW(a2, a4->TimeZoneKeyName, 0, 1u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    MUIStringW = RegLoadMUIStringW(hKey, L"MUI_Display", pszOutBuf, 0x100u, 0, 1u, a3);
    v7 = MUIStringW;
    if ( MUIStringW > 0 )
      v7 = (unsigned __int16)MUIStringW | 0x80070000;
    if ( v7 >= 0 )
    {
      v12 = 0;
      v9 = -1;
      do
        ++v9;
      while ( pszOutBuf[v9] );
      if ( (int)ULongLongToUInt(v9, &v12) >= 0 )
        Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, pszOutBuf, v12);
      *a5 = string;
      string = 0;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  v14 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  if ( hKey
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(&v14) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015d04  mov     [rsp-8+arg_0], rbx
0x180015d09  push    rbp
0x180015d0a  push    rsi
0x180015d0b  push    rdi
0x180015d0c  push    r13
0x180015d0e  push    r14
0x180015d10  lea     rbp, [rsp-70h]
0x180015d15  sub     rsp, 170h
0x180015d1c  mov     rax, cs:__security_cookie
0x180015d23  xor     rax, rsp
0x180015d26  mov     [rbp+90h+var_30], rax
0x180015d2a  mov     rsi, [rbp+90h+arg_20]
0x180015d31  lea     rax, [rsp+190h+hKey]
0x180015d36  xor     r14d, r14d
0x180015d39  mov     [rsp+190h+phkResult], rax; phkResult
0x180015d3e  mov     rcx, rdx; hKey
0x180015d41  mov     [rsp+190h+hKey], r14
0x180015d46  mov     rdi, r8
0x180015d49  mov     [rsp+190h+string], r14
0x180015d4e  lea     rdx, [r9+0ACh]; lpSubKey
0x180015d55  mov     [rsp+190h+pszOutBuf], r14w
0x180015d5b  lea     r13, ??_7?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable'
0x180015d62  xor     r8d, r8d; ulOptions
0x180015d65  lea     r9d, [r14+1]; samDesired
0x180015d69  mov     [rsp+190h+var_140], r13
0x180015d6e  call    cs:__imp_RegOpenKeyExW
0x180015d74  mov     ebx, eax
0x180015d76  test    eax, eax
0x180015d78  jle     short loc_180015D83
0x180015d7a  movzx   ebx, ax
0x180015d7d  or      ebx, 80070000h
0x180015d83  test    ebx, ebx
0x180015d85  js      loc_180015E14
0x180015d8b  mov     rcx, [rsp+190h+hKey]; hKey
0x180015d90  lea     r8, [rsp+190h+pszOutBuf]; pszOutBuf
0x180015d95  mov     [rsp+190h+pszDirectory], rdi; pszDirectory
0x180015d9a  lea     rdx, pszValue; "MUI_Display"
0x180015da1  mov     [rsp+190h+Flags], 1; Flags
0x180015da9  mov     r9d, 100h; cbOutBuf
0x180015daf  mov     [rsp+190h+phkResult], r14; pcbData
0x180015db4  call    cs:__imp_RegLoadMUIStringW
0x180015dba  mov     ebx, eax
0x180015dbc  test    eax, eax
0x180015dbe  jle     short loc_180015DC9
0x180015dc0  movzx   ebx, ax
0x180015dc3  or      ebx, 80070000h
0x180015dc9  test    ebx, ebx
0x180015dcb  js      short loc_180015E14
0x180015dcd  mov     [rsp+190h+var_150], r14d
0x180015dd2  lea     rax, [rsp+190h+pszOutBuf]
0x180015dd7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015ddb  inc     rcx; unsigned __int64
0x180015dde  cmp     [rax+rcx*2], r14w
0x180015de3  jnz     short loc_180015DDB
0x180015de5  lea     rdx, [rsp+190h+var_150]; unsigned int *
0x180015dea  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180015def  test    eax, eax
0x180015df1  js      short loc_180015E07
0x180015df3  mov     r8d, [rsp+190h+var_150]; unsigned int
0x180015df8  lea     rdx, [rsp+190h+pszOutBuf]; unsigned __int16 *
0x180015dfd  lea     rcx, [rsp+190h+string]; this
0x180015e02  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180015e07  mov     rax, [rsp+190h+string]
0x180015e0c  mov     [rsi], rax
0x180015e0f  mov     [rsp+190h+string], r14
0x180015e14  mov     rcx, [rsp+190h+string]; string
0x180015e19  call    cs:__imp_WindowsDeleteString
0x180015e1f  mov     [rsp+190h+string], r14
0x180015e24  mov     [rsp+190h+var_140], r13
0x180015e29  cmp     [rsp+190h+hKey], r14
0x180015e2e  jz      short loc_180015E63
0x180015e30  lea     rcx, [rsp+190h+var_140]
0x180015e35  call    ?InternalClose@?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(void)
0x180015e3a  test    al, al
0x180015e3c  jnz     short loc_180015E63
0x180015e3e  call    cs:__imp_GetLastError
0x180015e44  test    eax, eax
0x180015e46  jle     short loc_180015E50
0x180015e48  movzx   eax, ax
0x180015e4b  or      eax, 80070000h
0x180015e50  xor     r9d, r9d; lpArguments
0x180015e53  xor     r8d, r8d; nNumberOfArguments
0x180015e56  mov     ecx, eax; dwExceptionCode
0x180015e58  lea     edx, [r9+1]; dwExceptionFlags
0x180015e5c  call    cs:__imp_RaiseException
0x180015e62  int     3; Trap to Debugger
0x180015e63  mov     eax, ebx
0x180015e65  mov     rcx, [rbp+90h+var_30]
0x180015e69  xor     rcx, rsp; StackCookie
0x180015e6c  call    __security_check_cookie
0x180015e71  mov     rbx, [rsp+190h+arg_0]
0x180015e79  add     rsp, 170h
0x180015e80  pop     r14
0x180015e82  pop     r13
0x180015e84  pop     rdi
0x180015e85  pop     rsi
0x180015e86  pop     rbp
0x180015e87  retn
```
