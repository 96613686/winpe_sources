# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x1800464f8`
- end: `0x1800467af`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180044ba0`

## callees

- `0x1800464f8`
- `0x180047d58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004661b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004664b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004661b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004664b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046666`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800466de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046666`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800466de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004676f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004677e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004678d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004679c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004676f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004677e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004678d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004679c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046553`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004659d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800465d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800466a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004671a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046553`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004659d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800465d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800466a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004671a`

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
0x1800464f8  mov     r11, rsp
0x1800464fb  push    rbp
0x1800464fc  push    rbx
0x1800464fd  push    rsi
0x1800464fe  push    rdi
0x1800464ff  push    r14
0x180046501  mov     rbp, rsp
0x180046504  sub     rsp, 60h
0x180046508  xor     esi, esi
0x18004650a  lea     rax, [rbp+hKey]
0x18004650e  mov     [r11-48h], rsi
0x180046512  lea     rdx, [rcx+438h]; lpSubKey
0x180046519  mov     [r11-50h], rax
0x18004651d  mov     rdi, rcx
0x180046520  mov     [r11-58h], rsi
0x180046524  mov     r14d, 0F003Fh
0x18004652a  mov     [r11-60h], r14d
0x18004652e  xor     r9d, r9d; lpClass
0x180046531  xor     r8d, r8d; Reserved
0x180046534  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180046538  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004653f  mov     [rbp+arg_8], rsi
0x180046543  mov     [rbp+arg_10], rsi
0x180046547  mov     [rbp+arg_0], rsi
0x18004654b  mov     [rbp+arg_18], rsi
0x18004654f  mov     [rbp+hKey], rsi
0x180046553  call    cs:__imp_RegCreateKeyExW
0x180046559  mov     ebx, eax
0x18004655b  test    eax, eax
0x18004655d  jz      short loc_180046573
0x18004655f  jle     loc_180046757
0x180046565  movzx   ebx, ax
0x180046568  or      ebx, 80070000h
0x18004656e  jmp     loc_180046757
0x180046573  mov     rcx, [rbp+hKey]; hKey
0x180046577  lea     rax, [rbp+arg_18]
0x18004657b  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180046580  lea     rdx, [rdi+28h]; lpSubKey
0x180046584  mov     [rsp+60h+phkResult], rax; phkResult
0x180046589  xor     r9d, r9d; lpClass
0x18004658c  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180046591  xor     r8d, r8d; Reserved
0x180046594  mov     [rsp+60h+samDesired], r14d; samDesired
0x180046599  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18004659d  call    cs:__imp_RegCreateKeyExW
0x1800465a3  mov     ebx, eax
0x1800465a5  test    eax, eax
0x1800465a7  jnz     short loc_18004655F
0x1800465a9  mov     rcx, [rbp+arg_18]; hKey
0x1800465ad  lea     rax, [rbp+arg_0]
0x1800465b1  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800465b6  lea     rdx, [rdi+230h]; lpSubKey
0x1800465bd  mov     [rsp+60h+phkResult], rax; phkResult
0x1800465c2  xor     r9d, r9d; lpClass
0x1800465c5  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800465ca  xor     r8d, r8d; Reserved
0x1800465cd  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800465d2  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800465d6  call    cs:__imp_RegCreateKeyExW
0x1800465dc  mov     ebx, eax
0x1800465de  test    eax, eax
0x1800465e0  jnz     loc_18004655F
0x1800465e6  mov     rcx, [rdi+20h]
0x1800465ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800465ee  inc     rax
0x1800465f1  cmp     [rcx+rax*2], si
0x1800465f5  jnz     short loc_1800465EE
0x1800465f7  lea     eax, ds:2[rax*2]
0x1800465fe  mov     r9d, 1; dwType
0x180046604  mov     [rsp+60h+samDesired], eax; cbData
0x180046608  lea     rdx, aEtag; "ETag"
0x18004660f  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180046614  xor     r8d, r8d; Reserved
0x180046617  mov     rcx, [rbp+arg_0]; hKey
0x18004661b  call    cs:__imp_RegSetValueExW
0x180046621  mov     ebx, eax
0x180046623  test    eax, eax
0x180046625  jnz     loc_18004655F
0x18004662b  mov     rcx, [rbp+arg_0]; hKey
0x18004662f  lea     r9d, [rbx+4]; dwType
0x180046633  lea     rax, [rdi+18h]
0x180046637  mov     [rsp+60h+samDesired], r9d; cbData
0x18004663c  xor     r8d, r8d; Reserved
0x18004663f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180046644  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x18004664b  call    cs:__imp_RegSetValueExW
0x180046651  mov     ebx, eax
0x180046653  test    eax, eax
0x180046655  jnz     loc_18004655F
0x18004665b  mov     rcx, [rbp+arg_0]; hKey
0x18004665f  lea     rdx, aSettings_0; "Settings"
0x180046666  call    cs:__imp_RegDeleteTreeW
0x18004666c  mov     ebx, eax
0x18004666e  test    eax, 0FFFFFFFDh
0x180046673  jz      short loc_18004667C
0x180046675  test    eax, eax
0x180046677  jmp     loc_18004655F
0x18004667c  mov     rcx, [rbp+arg_0]; hKey
0x180046680  lea     rax, [rbp+arg_10]
0x180046684  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x180046689  lea     rdx, aSettings_0; "Settings"
0x180046690  mov     [rsp+60h+phkResult], rax; phkResult
0x180046695  xor     r9d, r9d; lpClass
0x180046698  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18004669d  xor     r8d, r8d; Reserved
0x1800466a0  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800466a5  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800466a9  call    cs:__imp_RegCreateKeyExW
0x1800466af  mov     ebx, eax
0x1800466b1  test    eax, eax
0x1800466b3  jnz     loc_18004655F
0x1800466b9  mov     rcx, [rbp+arg_10]; hKey
0x1800466bd  lea     rdx, [rdi+648h]; struct RtlNameValueArray *
0x1800466c4  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800466c9  mov     ebx, eax
0x1800466cb  test    eax, eax
0x1800466cd  js      loc_180046757
0x1800466d3  mov     rcx, [rbp+arg_0]; hKey
0x1800466d7  lea     rdx, aQueryparameter; "QueryParameters"
0x1800466de  call    cs:__imp_RegDeleteTreeW
0x1800466e4  mov     ebx, eax
0x1800466e6  test    eax, 0FFFFFFFDh
0x1800466eb  jnz     short loc_180046675
0x1800466ed  mov     rcx, [rbp+arg_0]; hKey
0x1800466f1  lea     rax, [rbp+arg_8]
0x1800466f5  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800466fa  lea     rdx, aQueryparameter; "QueryParameters"
0x180046701  mov     [rsp+60h+phkResult], rax; phkResult
0x180046706  xor     r9d, r9d; lpClass
0x180046709  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18004670e  xor     r8d, r8d; Reserved
0x180046711  mov     [rsp+60h+samDesired], r14d; samDesired
0x180046716  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18004671a  call    cs:__imp_RegCreateKeyExW
0x180046720  mov     ebx, eax
0x180046722  test    eax, eax
0x180046724  jnz     loc_18004655F
0x18004672a  mov     rcx, [rbp+arg_8]; hKey
0x18004672e  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x180046735  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18004673a  mov     ebx, eax
0x18004673c  test    eax, eax
0x18004673e  js      short loc_180046757
0x180046740  mov     rcx, [rbp+arg_8]; hKey
0x180046744  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x18004674b  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180046750  test    eax, eax
0x180046752  mov     ebx, eax
0x180046754  cmovns  ebx, esi
0x180046757  mov     rcx, [rbp+arg_8]; hKey
0x18004675b  test    rcx, rcx
0x18004675e  jz      short loc_180046766
0x180046760  call    cs:__imp_RegCloseKey
0x180046766  mov     rcx, [rbp+arg_10]; hKey
0x18004676a  test    rcx, rcx
0x18004676d  jz      short loc_180046775
0x18004676f  call    cs:__imp_RegCloseKey
0x180046775  mov     rcx, [rbp+arg_0]; hKey
0x180046779  test    rcx, rcx
0x18004677c  jz      short loc_180046784
0x18004677e  call    cs:__imp_RegCloseKey
0x180046784  mov     rcx, [rbp+arg_18]; hKey
0x180046788  test    rcx, rcx
0x18004678b  jz      short loc_180046793
0x18004678d  call    cs:__imp_RegCloseKey
0x180046793  mov     rcx, [rbp+hKey]; hKey
0x180046797  test    rcx, rcx
0x18004679a  jz      short loc_1800467A2
0x18004679c  call    cs:__imp_RegCloseKey
0x1800467a2  mov     eax, ebx
0x1800467a4  add     rsp, 60h
0x1800467a8  pop     r14
0x1800467aa  pop     rdi
0x1800467ab  pop     rsi
0x1800467ac  pop     rbx
0x1800467ad  pop     rbp
0x1800467ae  retn
```
