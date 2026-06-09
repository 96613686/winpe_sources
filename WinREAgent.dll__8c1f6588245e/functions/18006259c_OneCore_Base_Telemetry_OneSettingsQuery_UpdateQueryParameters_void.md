# OneCore::Base::Telemetry::OneSettingsQuery::UpdateQueryParameters(void)

- ea: `0x18006259c`
- end: `0x180062737`
- name: `?UpdateQueryParameters@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `411`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18005fd5c`

## callees

- `0x180012864`
- `0x18006259c`
- `0x180062db8`
- `0x18006c690`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x180062663`
- `ADVAPI32!RegDeleteTreeW` at `0x180062663`
- `ADVAPI32!RegCreateKeyExW` at `0x1800626b4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800626b4`
- `ADVAPI32!RegCloseKey` at `0x1800626fb`
- `ADVAPI32!RegCloseKey` at `0x18006270b`
- `ADVAPI32!RegCloseKey` at `0x1800626fb`
- `ADVAPI32!RegCloseKey` at `0x18006270b`
- `ADVAPI32!RegOpenKeyExW` at `0x180062637`
- `ADVAPI32!RegOpenKeyExW` at `0x180062637`

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
0x18006259c  mov     [rsp-8+arg_8], rbx
0x1800625a1  mov     [rsp-8+arg_10], rdi
0x1800625a6  push    rbp
0x1800625a7  lea     rbp, [rsp-180h]
0x1800625af  sub     rsp, 280h
0x1800625b6  mov     rax, cs:__security_cookie
0x1800625bd  xor     rax, rsp
0x1800625c0  mov     [rbp+180h+var_10], rax
0x1800625c7  lea     rdx, [rcx+28h]
0x1800625cb  mov     [rsp+280h+var_230], 0
0x1800625d4  lea     rax, [rcx+230h]
0x1800625db  mov     [rsp+280h+hKey], 0
0x1800625e4  mov     qword ptr [rsp+280h+samDesired], rax
0x1800625e9  lea     r9, [rcx+438h]
0x1800625f0  mov     [rsp+280h+phkResult], rdx
0x1800625f5  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x1800625fc  mov     rdi, rcx
0x1800625ff  mov     edx, 104h; unsigned __int64
0x180062604  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180062609  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006260e  mov     ebx, eax
0x180062610  test    eax, eax
0x180062612  js      loc_1800626F1
0x180062618  lea     rax, [rsp+280h+hKey]
0x18006261d  mov     r9d, 0F003Fh; samDesired
0x180062623  xor     r8d, r8d; ulOptions
0x180062626  mov     [rsp+280h+phkResult], rax; phkResult
0x18006262b  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180062630  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062637  call    cs:__imp_RegOpenKeyExW
0x18006263d  mov     ebx, eax
0x18006263f  test    eax, eax
0x180062641  jz      short loc_180062657
0x180062643  jle     loc_1800626F1
0x180062649  movzx   ebx, ax
0x18006264c  or      ebx, 80070000h
0x180062652  jmp     loc_1800626F1
0x180062657  mov     rcx, [rsp+280h+hKey]; hKey
0x18006265c  lea     rdx, aQueryparameter; "QueryParameters"
0x180062663  call    cs:__imp_RegDeleteTreeW
0x180062669  mov     ebx, eax
0x18006266b  test    eax, 0FFFFFFFDh
0x180062670  jz      short loc_180062676
0x180062672  test    eax, eax
0x180062674  jmp     short loc_180062643
0x180062676  mov     rcx, [rsp+280h+hKey]; hKey
0x18006267b  lea     rax, [rsp+280h+var_230]
0x180062680  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x180062689  lea     rdx, aQueryparameter; "QueryParameters"
0x180062690  mov     [rsp+280h+var_248], rax; phkResult
0x180062695  xor     r9d, r9d; lpClass
0x180062698  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800626a1  xor     r8d, r8d; Reserved
0x1800626a4  mov     [rsp+280h+samDesired], 0F003Fh; samDesired
0x1800626ac  mov     dword ptr [rsp+280h+phkResult], 0; dwOptions
0x1800626b4  call    cs:__imp_RegCreateKeyExW
0x1800626ba  mov     ebx, eax
0x1800626bc  test    eax, eax
0x1800626be  jnz     short loc_180062643
0x1800626c0  mov     rcx, [rsp+280h+var_230]; hKey
0x1800626c5  lea     rdx, [rdi+678h]; this
0x1800626cc  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800626d1  mov     ebx, eax
0x1800626d3  test    eax, eax
0x1800626d5  js      short loc_1800626F1
0x1800626d7  mov     rcx, [rsp+280h+var_230]; hKey
0x1800626dc  lea     rdx, [rdi+6A8h]; this
0x1800626e3  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800626e8  mov     ebx, eax
0x1800626ea  xor     eax, eax
0x1800626ec  test    ebx, ebx
0x1800626ee  cmovns  ebx, eax
0x1800626f1  mov     rcx, [rsp+280h+var_230]; hKey
0x1800626f6  test    rcx, rcx
0x1800626f9  jz      short loc_180062701
0x1800626fb  call    cs:__imp_RegCloseKey
0x180062701  mov     rcx, [rsp+280h+hKey]; hKey
0x180062706  test    rcx, rcx
0x180062709  jz      short loc_180062711
0x18006270b  call    cs:__imp_RegCloseKey
0x180062711  mov     eax, ebx
0x180062713  mov     rcx, [rbp+180h+var_10]
0x18006271a  xor     rcx, rsp; StackCookie
0x18006271d  call    __security_check_cookie
0x180062722  lea     r11, [rsp+280h+var_s0]
0x18006272a  mov     rbx, [r11+18h]
0x18006272e  mov     rdi, [r11+20h]
0x180062732  mov     rsp, r11
0x180062735  pop     rbp
0x180062736  retn
```
