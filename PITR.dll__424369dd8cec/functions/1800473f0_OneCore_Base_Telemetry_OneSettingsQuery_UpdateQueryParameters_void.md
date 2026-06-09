# OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)

- ea: `0x1800473f0`
- end: `0x18004758b`
- name: `?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180044ba0`

## callees

- `0x18001c5bc`
- `0x1800473f0`
- `0x180047d58`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800474b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800474b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004748b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004748b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004754f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004755f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004754f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004755f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047508`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047508`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  bool v4; // cc
  HKEY v6; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  hKey = 0;
  v2 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", (char *)this + 1080, (char *)this + 40, (char *)this + 560);
  if ( v2 < 0 )
    goto LABEL_11;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  v2 = v3;
  v4 = v3 <= 0;
  if ( v3 )
    goto LABEL_3;
  v3 = RegDeleteTreeW(hKey, L"QueryParameters");
  v2 = v3;
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    v4 = v3 <= 0;
    goto LABEL_3;
  }
  v3 = RegCreateKeyExW(hKey, L"QueryParameters", 0, 0, 0, 0xF003Fu, 0, &v6, 0);
  v2 = v3;
  v4 = v3 <= 0;
  if ( v3 )
  {
LABEL_3:
    if ( !v4 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_11;
  }
  v2 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v6,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656));
  if ( v2 >= 0 )
  {
    v2 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
           v6,
           (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704));
    if ( v2 >= 0 )
      v2 = 0;
  }
LABEL_11:
  if ( v6 )
    RegCloseKey(v6);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800473f0  mov     [rsp-8+arg_8], rbx
0x1800473f5  mov     [rsp-8+arg_10], rdi
0x1800473fa  push    rbp
0x1800473fb  lea     rbp, [rsp-180h]
0x180047403  sub     rsp, 280h
0x18004740a  mov     rax, cs:__security_cookie
0x180047411  xor     rax, rsp
0x180047414  mov     [rbp+180h+var_10], rax
0x18004741b  lea     rdx, [rcx+28h]
0x18004741f  mov     [rsp+280h+var_230], 0
0x180047428  lea     rax, [rcx+230h]
0x18004742f  mov     [rsp+280h+hKey], 0
0x180047438  mov     qword ptr [rsp+280h+samDesired], rax
0x18004743d  lea     r9, [rcx+438h]
0x180047444  mov     [rsp+280h+phkResult], rdx
0x180047449  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180047450  mov     rdi, rcx
0x180047453  mov     edx, 104h; unsigned __int64
0x180047458  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18004745d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047462  mov     ebx, eax
0x180047464  test    eax, eax
0x180047466  js      loc_180047545
0x18004746c  lea     rax, [rsp+280h+hKey]
0x180047471  mov     r9d, 0F003Fh; samDesired
0x180047477  xor     r8d, r8d; ulOptions
0x18004747a  mov     [rsp+280h+phkResult], rax; phkResult
0x18004747f  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180047484  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004748b  call    cs:__imp_RegOpenKeyExW
0x180047491  mov     ebx, eax
0x180047493  test    eax, eax
0x180047495  jz      short loc_1800474AB
0x180047497  jle     loc_180047545
0x18004749d  movzx   ebx, ax
0x1800474a0  or      ebx, 80070000h
0x1800474a6  jmp     loc_180047545
0x1800474ab  mov     rcx, [rsp+280h+hKey]; hKey
0x1800474b0  lea     rdx, aQueryparameter; "QueryParameters"
0x1800474b7  call    cs:__imp_RegDeleteTreeW
0x1800474bd  mov     ebx, eax
0x1800474bf  test    eax, 0FFFFFFFDh
0x1800474c4  jz      short loc_1800474CA
0x1800474c6  test    eax, eax
0x1800474c8  jmp     short loc_180047497
0x1800474ca  mov     rcx, [rsp+280h+hKey]; hKey
0x1800474cf  lea     rax, [rsp+280h+var_230]
0x1800474d4  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x1800474dd  lea     rdx, aQueryparameter; "QueryParameters"
0x1800474e4  mov     [rsp+280h+var_248], rax; phkResult
0x1800474e9  xor     r9d, r9d; lpClass
0x1800474ec  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800474f5  xor     r8d, r8d; Reserved
0x1800474f8  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x180047500  mov     dword ptr [rsp+280h+phkResult], 0; dwOptions
0x180047508  call    cs:__imp_RegCreateKeyExW
0x18004750e  mov     ebx, eax
0x180047510  test    eax, eax
0x180047512  jnz     short loc_180047497
0x180047514  mov     rcx, [rsp+280h+var_230]; hKey
0x180047519  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x180047520  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180047525  mov     ebx, eax
0x180047527  test    eax, eax
0x180047529  js      short loc_180047545
0x18004752b  mov     rcx, [rsp+280h+var_230]; hKey
0x180047530  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x180047537  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18004753c  mov     ebx, eax
0x18004753e  xor     eax, eax
0x180047540  test    ebx, ebx
0x180047542  cmovns  ebx, eax
0x180047545  mov     rcx, [rsp+280h+var_230]; hKey
0x18004754a  test    rcx, rcx
0x18004754d  jz      short loc_180047555
0x18004754f  call    cs:__imp_RegCloseKey
0x180047555  mov     rcx, [rsp+280h+hKey]; hKey
0x18004755a  test    rcx, rcx
0x18004755d  jz      short loc_180047565
0x18004755f  call    cs:__imp_RegCloseKey
0x180047565  mov     eax, ebx
0x180047567  mov     rcx, [rbp+180h+var_10]
0x18004756e  xor     rcx, rsp; StackCookie
0x180047571  call    __security_check_cookie
0x180047576  lea     r11, [rsp+280h+var_s0]
0x18004757e  mov     rbx, [r11+18h]
0x180047582  mov     rdi, [r11+20h]
0x180047586  mov     rsp, r11
0x180047589  pop     rbp
0x18004758a  retn
```
