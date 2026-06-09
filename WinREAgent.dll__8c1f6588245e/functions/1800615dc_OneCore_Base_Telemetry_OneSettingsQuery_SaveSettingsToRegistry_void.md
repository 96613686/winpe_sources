# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x1800615dc`
- end: `0x180061893`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005fd5c`

## callees

- `0x1800615dc`
- `0x180062db8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800616ff`
- `ADVAPI32!RegSetValueExW` at `0x18006172f`
- `ADVAPI32!RegSetValueExW` at `0x1800616ff`
- `ADVAPI32!RegSetValueExW` at `0x18006172f`
- `ADVAPI32!RegDeleteTreeW` at `0x18006174a`
- `ADVAPI32!RegDeleteTreeW` at `0x1800617c2`
- `ADVAPI32!RegDeleteTreeW` at `0x18006174a`
- `ADVAPI32!RegDeleteTreeW` at `0x1800617c2`
- `ADVAPI32!RegCreateKeyExW` at `0x180061637`
- `ADVAPI32!RegCreateKeyExW` at `0x180061681`
- `ADVAPI32!RegCreateKeyExW` at `0x1800616ba`
- `ADVAPI32!RegCreateKeyExW` at `0x18006178d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800617fe`
- `ADVAPI32!RegCreateKeyExW` at `0x180061637`
- `ADVAPI32!RegCreateKeyExW` at `0x180061681`
- `ADVAPI32!RegCreateKeyExW` at `0x1800616ba`
- `ADVAPI32!RegCreateKeyExW` at `0x18006178d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800617fe`
- `ADVAPI32!RegCloseKey` at `0x180061844`
- `ADVAPI32!RegCloseKey` at `0x180061853`
- `ADVAPI32!RegCloseKey` at `0x180061862`
- `ADVAPI32!RegCloseKey` at `0x180061871`
- `ADVAPI32!RegCloseKey` at `0x180061880`
- `ADVAPI32!RegCloseKey` at `0x180061844`
- `ADVAPI32!RegCloseKey` at `0x180061853`
- `ADVAPI32!RegCloseKey` at `0x180061862`
- `ADVAPI32!RegCloseKey` at `0x180061871`
- `ADVAPI32!RegCloseKey` at `0x180061880`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  bool v4; // cc
  const BYTE *v5; // rcx
  __int64 v6; // rax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v9; // [rsp+90h] [rbp+30h] BYREF
  HKEY v10; // [rsp+98h] [rbp+38h] BYREF
  HKEY v11; // [rsp+A0h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+48h] BYREF

  v10 = 0;
  v11 = 0;
  v9 = 0;
  phkResult = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)this + 540, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegCreateKeyExW(hKey, (LPCWSTR)this + 20, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegCreateKeyExW(phkResult, (LPCWSTR)this + 280, 0, 0, 0, 0xF003Fu, 0, &v9, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v5 = (const BYTE *)*((_QWORD *)this + 4);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&v5[2 * v6] );
  v2 = RegSetValueExW(v9, L"ETag", 0, 1u, v5, 2 * v6 + 2);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegSetValueExW(v9, L"RefreshInterval", 0, 4u, (const BYTE *)this + 24, 4u);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v2 = RegDeleteTreeW(v9, L"Settings");
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
  {
LABEL_11:
    v4 = v2 <= 0;
    goto LABEL_2;
  }
  v2 = RegCreateKeyExW(v9, L"Settings", 0, 0, 0, 0xF003Fu, 0, &v11, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
    goto LABEL_2;
  v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v11,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608));
  if ( v3 < 0 )
    goto LABEL_19;
  v2 = RegDeleteTreeW(v9, L"QueryParameters");
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
    goto LABEL_11;
  v2 = RegCreateKeyExW(v9, L"QueryParameters", 0, 0, 0, 0xF003Fu, 0, &v10, 0);
  v3 = v2;
  v4 = v2 <= 0;
  if ( v2 )
  {
LABEL_2:
    if ( !v4 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    goto LABEL_19;
  }
  v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
         v10,
         (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656));
  if ( v3 >= 0 )
  {
    v3 = OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
           v10,
           (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704));
    if ( v3 >= 0 )
      v3 = 0;
  }
LABEL_19:
  if ( v10 )
    RegCloseKey(v10);
  if ( v11 )
    RegCloseKey(v11);
  if ( v9 )
    RegCloseKey(v9);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800615dc  mov     r11, rsp
0x1800615df  push    rbp
0x1800615e0  push    rbx
0x1800615e1  push    rsi
0x1800615e2  push    rdi
0x1800615e3  push    r14
0x1800615e5  mov     rbp, rsp
0x1800615e8  sub     rsp, 60h
0x1800615ec  xor     esi, esi
0x1800615ee  lea     rax, [rbp+hKey]
0x1800615f2  mov     [r11-48h], rsi
0x1800615f6  lea     rdx, [rcx+438h]; lpSubKey
0x1800615fd  mov     [r11-50h], rax
0x180061601  mov     rdi, rcx
0x180061604  mov     [r11-58h], rsi
0x180061608  mov     r14d, 0F003Fh
0x18006160e  mov     [r11-60h], r14d
0x180061612  xor     r9d, r9d; lpClass
0x180061615  xor     r8d, r8d; Reserved
0x180061618  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18006161c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180061623  mov     [rbp+arg_8], rsi
0x180061627  mov     [rbp+arg_10], rsi
0x18006162b  mov     [rbp+arg_0], rsi
0x18006162f  mov     [rbp+arg_18], rsi
0x180061633  mov     [rbp+hKey], rsi
0x180061637  call    cs:__imp_RegCreateKeyExW
0x18006163d  mov     ebx, eax
0x18006163f  test    eax, eax
0x180061641  jz      short loc_180061657
0x180061643  jle     loc_18006183B
0x180061649  movzx   ebx, ax
0x18006164c  or      ebx, 80070000h
0x180061652  jmp     loc_18006183B
0x180061657  mov     rcx, [rbp+hKey]; hKey
0x18006165b  lea     rax, [rbp+arg_18]
0x18006165f  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180061664  lea     rdx, [rdi+28h]; lpSubKey
0x180061668  mov     [rsp+60h+phkResult], rax; phkResult
0x18006166d  xor     r9d, r9d; lpClass
0x180061670  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180061675  xor     r8d, r8d; Reserved
0x180061678  mov     [rsp+60h+samDesired], r14d; samDesired
0x18006167d  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180061681  call    cs:__imp_RegCreateKeyExW
0x180061687  mov     ebx, eax
0x180061689  test    eax, eax
0x18006168b  jnz     short loc_180061643
0x18006168d  mov     rcx, [rbp+arg_18]; hKey
0x180061691  lea     rax, [rbp+arg_0]
0x180061695  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18006169a  lea     rdx, [rdi+230h]; lpSubKey
0x1800616a1  mov     [rsp+60h+phkResult], rax; phkResult
0x1800616a6  xor     r9d, r9d; lpClass
0x1800616a9  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800616ae  xor     r8d, r8d; Reserved
0x1800616b1  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800616b6  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800616ba  call    cs:__imp_RegCreateKeyExW
0x1800616c0  mov     ebx, eax
0x1800616c2  test    eax, eax
0x1800616c4  jnz     loc_180061643
0x1800616ca  mov     rcx, [rdi+20h]
0x1800616ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800616d2  inc     rax
0x1800616d5  cmp     [rcx+rax*2], si
0x1800616d9  jnz     short loc_1800616D2
0x1800616db  lea     eax, ds:2[rax*2]
0x1800616e2  mov     r9d, 1; dwType
0x1800616e8  mov     [rsp+60h+samDesired], eax; cbData
0x1800616ec  lea     rdx, ValueName; "ETag"
0x1800616f3  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x1800616f8  xor     r8d, r8d; Reserved
0x1800616fb  mov     rcx, [rbp+arg_0]; hKey
0x1800616ff  call    cs:__imp_RegSetValueExW
0x180061705  mov     ebx, eax
0x180061707  test    eax, eax
0x180061709  jnz     loc_180061643
0x18006170f  mov     rcx, [rbp+arg_0]; hKey
0x180061713  lea     r9d, [rbx+4]; dwType
0x180061717  lea     rax, [rdi+18h]
0x18006171b  mov     [rsp+60h+samDesired], r9d; cbData
0x180061720  xor     r8d, r8d; Reserved
0x180061723  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180061728  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x18006172f  call    cs:__imp_RegSetValueExW
0x180061735  mov     ebx, eax
0x180061737  test    eax, eax
0x180061739  jnz     loc_180061643
0x18006173f  mov     rcx, [rbp+arg_0]; hKey
0x180061743  lea     rdx, aSettings_0; "Settings"
0x18006174a  call    cs:__imp_RegDeleteTreeW
0x180061750  mov     ebx, eax
0x180061752  test    eax, 0FFFFFFFDh
0x180061757  jz      short loc_180061760
0x180061759  test    eax, eax
0x18006175b  jmp     loc_180061643
0x180061760  mov     rcx, [rbp+arg_0]; hKey
0x180061764  lea     rax, [rbp+arg_10]
0x180061768  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18006176d  lea     rdx, aSettings_0; "Settings"
0x180061774  mov     [rsp+60h+phkResult], rax; phkResult
0x180061779  xor     r9d, r9d; lpClass
0x18006177c  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180061781  xor     r8d, r8d; Reserved
0x180061784  mov     [rsp+60h+samDesired], r14d; samDesired
0x180061789  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18006178d  call    cs:__imp_RegCreateKeyExW
0x180061793  mov     ebx, eax
0x180061795  test    eax, eax
0x180061797  jnz     loc_180061643
0x18006179d  mov     rcx, [rbp+arg_10]; hKey
0x1800617a1  lea     rdx, [rdi+648h]; this
0x1800617a8  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800617ad  mov     ebx, eax
0x1800617af  test    eax, eax
0x1800617b1  js      loc_18006183B
0x1800617b7  mov     rcx, [rbp+arg_0]; hKey
0x1800617bb  lea     rdx, aQueryparameter; "QueryParameters"
0x1800617c2  call    cs:__imp_RegDeleteTreeW
0x1800617c8  mov     ebx, eax
0x1800617ca  test    eax, 0FFFFFFFDh
0x1800617cf  jnz     short loc_180061759
0x1800617d1  mov     rcx, [rbp+arg_0]; hKey
0x1800617d5  lea     rax, [rbp+arg_8]
0x1800617d9  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800617de  lea     rdx, aQueryparameter; "QueryParameters"
0x1800617e5  mov     [rsp+60h+phkResult], rax; phkResult
0x1800617ea  xor     r9d, r9d; lpClass
0x1800617ed  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800617f2  xor     r8d, r8d; Reserved
0x1800617f5  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800617fa  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800617fe  call    cs:__imp_RegCreateKeyExW
0x180061804  mov     ebx, eax
0x180061806  test    eax, eax
0x180061808  jnz     loc_180061643
0x18006180e  mov     rcx, [rbp+arg_8]; hKey
0x180061812  lea     rdx, [rdi+678h]; this
0x180061819  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18006181e  mov     ebx, eax
0x180061820  test    eax, eax
0x180061822  js      short loc_18006183B
0x180061824  mov     rcx, [rbp+arg_8]; hKey
0x180061828  lea     rdx, [rdi+6A8h]; this
0x18006182f  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180061834  test    eax, eax
0x180061836  mov     ebx, eax
0x180061838  cmovns  ebx, esi
0x18006183b  mov     rcx, [rbp+arg_8]; hKey
0x18006183f  test    rcx, rcx
0x180061842  jz      short loc_18006184A
0x180061844  call    cs:__imp_RegCloseKey
0x18006184a  mov     rcx, [rbp+arg_10]; hKey
0x18006184e  test    rcx, rcx
0x180061851  jz      short loc_180061859
0x180061853  call    cs:__imp_RegCloseKey
0x180061859  mov     rcx, [rbp+arg_0]; hKey
0x18006185d  test    rcx, rcx
0x180061860  jz      short loc_180061868
0x180061862  call    cs:__imp_RegCloseKey
0x180061868  mov     rcx, [rbp+arg_18]; hKey
0x18006186c  test    rcx, rcx
0x18006186f  jz      short loc_180061877
0x180061871  call    cs:__imp_RegCloseKey
0x180061877  mov     rcx, [rbp+hKey]; hKey
0x18006187b  test    rcx, rcx
0x18006187e  jz      short loc_180061886
0x180061880  call    cs:__imp_RegCloseKey
0x180061886  mov     eax, ebx
0x180061888  add     rsp, 60h
0x18006188c  pop     r14
0x18006188e  pop     rdi
0x18006188f  pop     rsi
0x180061890  pop     rbx
0x180061891  pop     rbp
0x180061892  retn
```
