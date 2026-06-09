# OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)

- ea: `0x180023818`
- end: `0x1800239b3`
- name: `?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18001f3f4`

## callees

- `0x180003850`
- `0x180023818`
- `0x180024610`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023987`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023987`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800238df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800238df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023930`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023930`

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
0x180023818  mov     [rsp-8+arg_8], rbx
0x18002381d  mov     [rsp-8+arg_10], rdi
0x180023822  push    rbp
0x180023823  lea     rbp, [rsp-180h]
0x18002382b  sub     rsp, 280h
0x180023832  mov     rax, cs:__security_cookie
0x180023839  xor     rax, rsp
0x18002383c  mov     [rbp+180h+var_10], rax
0x180023843  lea     rdx, [rcx+28h]
0x180023847  mov     [rsp+280h+var_230], 0
0x180023850  lea     rax, [rcx+230h]
0x180023857  mov     [rsp+280h+hKey], 0
0x180023860  mov     qword ptr [rsp+280h+samDesired], rax
0x180023865  lea     r9, [rcx+438h]
0x18002386c  mov     [rsp+280h+phkResult], rdx
0x180023871  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180023878  mov     rdi, rcx
0x18002387b  mov     edx, 104h; unsigned __int64
0x180023880  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180023885  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002388a  mov     ebx, eax
0x18002388c  test    eax, eax
0x18002388e  js      loc_18002396D
0x180023894  lea     rax, [rsp+280h+hKey]
0x180023899  mov     r9d, 0F003Fh; samDesired
0x18002389f  xor     r8d, r8d; ulOptions
0x1800238a2  mov     [rsp+280h+phkResult], rax; phkResult
0x1800238a7  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x1800238ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800238b3  call    cs:__imp_RegOpenKeyExW
0x1800238b9  mov     ebx, eax
0x1800238bb  test    eax, eax
0x1800238bd  jz      short loc_1800238D3
0x1800238bf  jle     loc_18002396D
0x1800238c5  movzx   ebx, ax
0x1800238c8  or      ebx, 80070000h
0x1800238ce  jmp     loc_18002396D
0x1800238d3  mov     rcx, [rsp+280h+hKey]; hKey
0x1800238d8  lea     rdx, aQueryparameter; "QueryParameters"
0x1800238df  call    cs:__imp_RegDeleteTreeW
0x1800238e5  mov     ebx, eax
0x1800238e7  test    eax, 0FFFFFFFDh
0x1800238ec  jz      short loc_1800238F2
0x1800238ee  test    eax, eax
0x1800238f0  jmp     short loc_1800238BF
0x1800238f2  mov     rcx, [rsp+280h+hKey]; hKey
0x1800238f7  lea     rax, [rsp+280h+var_230]
0x1800238fc  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x180023905  lea     rdx, aQueryparameter; "QueryParameters"
0x18002390c  mov     [rsp+280h+var_248], rax; phkResult
0x180023911  xor     r9d, r9d; lpClass
0x180023914  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002391d  xor     r8d, r8d; Reserved
0x180023920  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x180023928  mov     dword ptr [rsp+280h+phkResult], 0; dwOptions
0x180023930  call    cs:__imp_RegCreateKeyExW
0x180023936  mov     ebx, eax
0x180023938  test    eax, eax
0x18002393a  jnz     short loc_1800238BF
0x18002393c  mov     rcx, [rsp+280h+var_230]; hKey
0x180023941  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x180023948  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18002394d  mov     ebx, eax
0x18002394f  test    eax, eax
0x180023951  js      short loc_18002396D
0x180023953  mov     rcx, [rsp+280h+var_230]; hKey
0x180023958  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x18002395f  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180023964  mov     ebx, eax
0x180023966  xor     eax, eax
0x180023968  test    ebx, ebx
0x18002396a  cmovns  ebx, eax
0x18002396d  mov     rcx, [rsp+280h+var_230]; hKey
0x180023972  test    rcx, rcx
0x180023975  jz      short loc_18002397D
0x180023977  call    cs:__imp_RegCloseKey
0x18002397d  mov     rcx, [rsp+280h+hKey]; hKey
0x180023982  test    rcx, rcx
0x180023985  jz      short loc_18002398D
0x180023987  call    cs:__imp_RegCloseKey
0x18002398d  mov     eax, ebx
0x18002398f  mov     rcx, [rbp+180h+var_10]
0x180023996  xor     rcx, rsp; StackCookie
0x180023999  call    __security_check_cookie
0x18002399e  lea     r11, [rsp+280h+var_s0]
0x1800239a6  mov     rbx, [r11+18h]
0x1800239aa  mov     rdi, [r11+20h]
0x1800239ae  mov     rsp, r11
0x1800239b1  pop     rbp
0x1800239b2  retn
```
