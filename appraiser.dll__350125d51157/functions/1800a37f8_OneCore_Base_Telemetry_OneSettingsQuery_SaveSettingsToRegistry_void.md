# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x1800a37f8`
- end: `0x1800a3aaf`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800a20bc`

## callees

- `0x1800a37f8`
- `0x1800a4c60`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800a3a60`
- `ADVAPI32!RegCloseKey` at `0x1800a3a6f`
- `ADVAPI32!RegCloseKey` at `0x1800a3a7e`
- `ADVAPI32!RegCloseKey` at `0x1800a3a8d`
- `ADVAPI32!RegCloseKey` at `0x1800a3a9c`
- `ADVAPI32!RegCloseKey` at `0x1800a3a60`
- `ADVAPI32!RegCloseKey` at `0x1800a3a6f`
- `ADVAPI32!RegCloseKey` at `0x1800a3a7e`
- `ADVAPI32!RegCloseKey` at `0x1800a3a8d`
- `ADVAPI32!RegCloseKey` at `0x1800a3a9c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a3853`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a389d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a38d6`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a39a9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a3a1a`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a3853`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a389d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a38d6`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a39a9`
- `ADVAPI32!RegCreateKeyExW` at `0x1800a3a1a`
- `ADVAPI32!RegDeleteTreeW` at `0x1800a3966`
- `ADVAPI32!RegDeleteTreeW` at `0x1800a39de`
- `ADVAPI32!RegDeleteTreeW` at `0x1800a3966`
- `ADVAPI32!RegDeleteTreeW` at `0x1800a39de`
- `ADVAPI32!RegSetValueExW` at `0x1800a391b`
- `ADVAPI32!RegSetValueExW` at `0x1800a394b`
- `ADVAPI32!RegSetValueExW` at `0x1800a391b`
- `ADVAPI32!RegSetValueExW` at `0x1800a394b`

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
0x1800a37f8  mov     r11, rsp
0x1800a37fb  push    rbp
0x1800a37fc  push    rbx
0x1800a37fd  push    rsi
0x1800a37fe  push    rdi
0x1800a37ff  push    r14
0x1800a3801  mov     rbp, rsp
0x1800a3804  sub     rsp, 60h
0x1800a3808  xor     esi, esi
0x1800a380a  lea     rax, [rbp+hKey]
0x1800a380e  mov     [r11-48h], rsi
0x1800a3812  lea     rdx, [rcx+438h]; lpSubKey
0x1800a3819  mov     [r11-50h], rax
0x1800a381d  mov     rdi, rcx
0x1800a3820  mov     [r11-58h], rsi
0x1800a3824  mov     r14d, 0F003Fh
0x1800a382a  mov     [r11-60h], r14d
0x1800a382e  xor     r9d, r9d; lpClass
0x1800a3831  xor     r8d, r8d; Reserved
0x1800a3834  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800a3838  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a383f  mov     [rbp+arg_8], rsi
0x1800a3843  mov     [rbp+arg_10], rsi
0x1800a3847  mov     [rbp+arg_0], rsi
0x1800a384b  mov     [rbp+arg_18], rsi
0x1800a384f  mov     [rbp+hKey], rsi
0x1800a3853  call    cs:__imp_RegCreateKeyExW
0x1800a3859  mov     ebx, eax
0x1800a385b  test    eax, eax
0x1800a385d  jz      short loc_1800A3873
0x1800a385f  jle     loc_1800A3A57
0x1800a3865  movzx   ebx, ax
0x1800a3868  or      ebx, 80070000h
0x1800a386e  jmp     loc_1800A3A57
0x1800a3873  mov     rcx, [rbp+hKey]; hKey
0x1800a3877  lea     rax, [rbp+arg_18]
0x1800a387b  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800a3880  lea     rdx, [rdi+28h]; lpSubKey
0x1800a3884  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a3889  xor     r9d, r9d; lpClass
0x1800a388c  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a3891  xor     r8d, r8d; Reserved
0x1800a3894  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800a3899  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800a389d  call    cs:__imp_RegCreateKeyExW
0x1800a38a3  mov     ebx, eax
0x1800a38a5  test    eax, eax
0x1800a38a7  jnz     short loc_1800A385F
0x1800a38a9  mov     rcx, [rbp+arg_18]; hKey
0x1800a38ad  lea     rax, [rbp+arg_0]
0x1800a38b1  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800a38b6  lea     rdx, [rdi+230h]; lpSubKey
0x1800a38bd  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a38c2  xor     r9d, r9d; lpClass
0x1800a38c5  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a38ca  xor     r8d, r8d; Reserved
0x1800a38cd  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800a38d2  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800a38d6  call    cs:__imp_RegCreateKeyExW
0x1800a38dc  mov     ebx, eax
0x1800a38de  test    eax, eax
0x1800a38e0  jnz     loc_1800A385F
0x1800a38e6  mov     rcx, [rdi+20h]
0x1800a38ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a38ee  inc     rax
0x1800a38f1  cmp     [rcx+rax*2], si
0x1800a38f5  jnz     short loc_1800A38EE
0x1800a38f7  lea     eax, ds:2[rax*2]
0x1800a38fe  mov     r9d, 1; dwType
0x1800a3904  mov     [rsp+60h+samDesired], eax; cbData
0x1800a3908  lea     rdx, aEtag; "ETag"
0x1800a390f  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x1800a3914  xor     r8d, r8d; Reserved
0x1800a3917  mov     rcx, [rbp+arg_0]; hKey
0x1800a391b  call    cs:__imp_RegSetValueExW
0x1800a3921  mov     ebx, eax
0x1800a3923  test    eax, eax
0x1800a3925  jnz     loc_1800A385F
0x1800a392b  mov     rcx, [rbp+arg_0]; hKey
0x1800a392f  lea     r9d, [rbx+4]; dwType
0x1800a3933  lea     rax, [rdi+18h]
0x1800a3937  mov     [rsp+60h+samDesired], r9d; cbData
0x1800a393c  xor     r8d, r8d; Reserved
0x1800a393f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800a3944  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x1800a394b  call    cs:__imp_RegSetValueExW
0x1800a3951  mov     ebx, eax
0x1800a3953  test    eax, eax
0x1800a3955  jnz     loc_1800A385F
0x1800a395b  mov     rcx, [rbp+arg_0]; hKey
0x1800a395f  lea     rdx, aSettings_0; "Settings"
0x1800a3966  call    cs:__imp_RegDeleteTreeW
0x1800a396c  mov     ebx, eax
0x1800a396e  test    eax, 0FFFFFFFDh
0x1800a3973  jz      short loc_1800A397C
0x1800a3975  test    eax, eax
0x1800a3977  jmp     loc_1800A385F
0x1800a397c  mov     rcx, [rbp+arg_0]; hKey
0x1800a3980  lea     rax, [rbp+arg_10]
0x1800a3984  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800a3989  lea     rdx, aSettings_0; "Settings"
0x1800a3990  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a3995  xor     r9d, r9d; lpClass
0x1800a3998  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a399d  xor     r8d, r8d; Reserved
0x1800a39a0  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800a39a5  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800a39a9  call    cs:__imp_RegCreateKeyExW
0x1800a39af  mov     ebx, eax
0x1800a39b1  test    eax, eax
0x1800a39b3  jnz     loc_1800A385F
0x1800a39b9  mov     rcx, [rbp+arg_10]; hKey
0x1800a39bd  lea     rdx, [rdi+648h]; struct RtlNameValueArray *
0x1800a39c4  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800a39c9  mov     ebx, eax
0x1800a39cb  test    eax, eax
0x1800a39cd  js      loc_1800A3A57
0x1800a39d3  mov     rcx, [rbp+arg_0]; hKey
0x1800a39d7  lea     rdx, aQueryparameter; "QueryParameters"
0x1800a39de  call    cs:__imp_RegDeleteTreeW
0x1800a39e4  mov     ebx, eax
0x1800a39e6  test    eax, 0FFFFFFFDh
0x1800a39eb  jnz     short loc_1800A3975
0x1800a39ed  mov     rcx, [rbp+arg_0]; hKey
0x1800a39f1  lea     rax, [rbp+arg_8]
0x1800a39f5  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800a39fa  lea     rdx, aQueryparameter; "QueryParameters"
0x1800a3a01  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a3a06  xor     r9d, r9d; lpClass
0x1800a3a09  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800a3a0e  xor     r8d, r8d; Reserved
0x1800a3a11  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800a3a16  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800a3a1a  call    cs:__imp_RegCreateKeyExW
0x1800a3a20  mov     ebx, eax
0x1800a3a22  test    eax, eax
0x1800a3a24  jnz     loc_1800A385F
0x1800a3a2a  mov     rcx, [rbp+arg_8]; hKey
0x1800a3a2e  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x1800a3a35  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800a3a3a  mov     ebx, eax
0x1800a3a3c  test    eax, eax
0x1800a3a3e  js      short loc_1800A3A57
0x1800a3a40  mov     rcx, [rbp+arg_8]; hKey
0x1800a3a44  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x1800a3a4b  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800a3a50  test    eax, eax
0x1800a3a52  mov     ebx, eax
0x1800a3a54  cmovns  ebx, esi
0x1800a3a57  mov     rcx, [rbp+arg_8]; hKey
0x1800a3a5b  test    rcx, rcx
0x1800a3a5e  jz      short loc_1800A3A66
0x1800a3a60  call    cs:__imp_RegCloseKey
0x1800a3a66  mov     rcx, [rbp+arg_10]; hKey
0x1800a3a6a  test    rcx, rcx
0x1800a3a6d  jz      short loc_1800A3A75
0x1800a3a6f  call    cs:__imp_RegCloseKey
0x1800a3a75  mov     rcx, [rbp+arg_0]; hKey
0x1800a3a79  test    rcx, rcx
0x1800a3a7c  jz      short loc_1800A3A84
0x1800a3a7e  call    cs:__imp_RegCloseKey
0x1800a3a84  mov     rcx, [rbp+arg_18]; hKey
0x1800a3a88  test    rcx, rcx
0x1800a3a8b  jz      short loc_1800A3A93
0x1800a3a8d  call    cs:__imp_RegCloseKey
0x1800a3a93  mov     rcx, [rbp+hKey]; hKey
0x1800a3a97  test    rcx, rcx
0x1800a3a9a  jz      short loc_1800A3AA2
0x1800a3a9c  call    cs:__imp_RegCloseKey
0x1800a3aa2  mov     eax, ebx
0x1800a3aa4  add     rsp, 60h
0x1800a3aa8  pop     r14
0x1800a3aaa  pop     rdi
0x1800a3aab  pop     rsi
0x1800a3aac  pop     rbx
0x1800a3aad  pop     rbp
0x1800a3aae  retn
```
