# OneCore::Base::Telemetry::OneSettingsQuery::SaveSettingsToRegistry(void)

- ea: `0x180022028`
- end: `0x1800222df`
- name: `?SaveSettingsToRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f3f4`

## callees

- `0x180022028`
- `0x180024610`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002214b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002217b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002214b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002217b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022290`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002229f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022290`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002229f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800222cc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180022196`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002220e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180022196`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002220e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022083`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800220cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022106`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800221d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002224a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022083`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800220cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022106`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800221d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002224a`

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
0x180022028  mov     r11, rsp
0x18002202b  push    rbp
0x18002202c  push    rbx
0x18002202d  push    rsi
0x18002202e  push    rdi
0x18002202f  push    r14
0x180022031  mov     rbp, rsp
0x180022034  sub     rsp, 60h
0x180022038  xor     esi, esi
0x18002203a  lea     rax, [rbp+hKey]
0x18002203e  mov     [r11-48h], rsi
0x180022042  lea     rdx, [rcx+438h]; lpSubKey
0x180022049  mov     [r11-50h], rax
0x18002204d  mov     rdi, rcx
0x180022050  mov     [r11-58h], rsi
0x180022054  mov     r14d, 0F003Fh
0x18002205a  mov     [r11-60h], r14d
0x18002205e  xor     r9d, r9d; lpClass
0x180022061  xor     r8d, r8d; Reserved
0x180022064  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180022068  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002206f  mov     [rbp+arg_8], rsi
0x180022073  mov     [rbp+arg_10], rsi
0x180022077  mov     [rbp+arg_0], rsi
0x18002207b  mov     [rbp+arg_18], rsi
0x18002207f  mov     [rbp+hKey], rsi
0x180022083  call    cs:__imp_RegCreateKeyExW
0x180022089  mov     ebx, eax
0x18002208b  test    eax, eax
0x18002208d  jz      short loc_1800220A3
0x18002208f  jle     loc_180022287
0x180022095  movzx   ebx, ax
0x180022098  or      ebx, 80070000h
0x18002209e  jmp     loc_180022287
0x1800220a3  mov     rcx, [rbp+hKey]; hKey
0x1800220a7  lea     rax, [rbp+arg_18]
0x1800220ab  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800220b0  lea     rdx, [rdi+28h]; lpSubKey
0x1800220b4  mov     [rsp+60h+phkResult], rax; phkResult
0x1800220b9  xor     r9d, r9d; lpClass
0x1800220bc  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800220c1  xor     r8d, r8d; Reserved
0x1800220c4  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800220c9  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800220cd  call    cs:__imp_RegCreateKeyExW
0x1800220d3  mov     ebx, eax
0x1800220d5  test    eax, eax
0x1800220d7  jnz     short loc_18002208F
0x1800220d9  mov     rcx, [rbp+arg_18]; hKey
0x1800220dd  lea     rax, [rbp+arg_0]
0x1800220e1  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800220e6  lea     rdx, [rdi+230h]; lpSubKey
0x1800220ed  mov     [rsp+60h+phkResult], rax; phkResult
0x1800220f2  xor     r9d, r9d; lpClass
0x1800220f5  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800220fa  xor     r8d, r8d; Reserved
0x1800220fd  mov     [rsp+60h+samDesired], r14d; samDesired
0x180022102  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180022106  call    cs:__imp_RegCreateKeyExW
0x18002210c  mov     ebx, eax
0x18002210e  test    eax, eax
0x180022110  jnz     loc_18002208F
0x180022116  mov     rcx, [rdi+20h]
0x18002211a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002211e  inc     rax
0x180022121  cmp     [rcx+rax*2], si
0x180022125  jnz     short loc_18002211E
0x180022127  lea     eax, ds:2[rax*2]
0x18002212e  mov     r9d, 1; dwType
0x180022134  mov     [rsp+60h+samDesired], eax; cbData
0x180022138  lea     rdx, aEtag; "ETag"
0x18002213f  mov     qword ptr [rsp+60h+dwOptions], rcx; lpData
0x180022144  xor     r8d, r8d; Reserved
0x180022147  mov     rcx, [rbp+arg_0]; hKey
0x18002214b  call    cs:__imp_RegSetValueExW
0x180022151  mov     ebx, eax
0x180022153  test    eax, eax
0x180022155  jnz     loc_18002208F
0x18002215b  mov     rcx, [rbp+arg_0]; hKey
0x18002215f  lea     r9d, [rbx+4]; dwType
0x180022163  lea     rax, [rdi+18h]
0x180022167  mov     [rsp+60h+samDesired], r9d; cbData
0x18002216c  xor     r8d, r8d; Reserved
0x18002216f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180022174  lea     rdx, aRefreshinterva_0; "RefreshInterval"
0x18002217b  call    cs:__imp_RegSetValueExW
0x180022181  mov     ebx, eax
0x180022183  test    eax, eax
0x180022185  jnz     loc_18002208F
0x18002218b  mov     rcx, [rbp+arg_0]; hKey
0x18002218f  lea     rdx, aSettings_0; "Settings"
0x180022196  call    cs:__imp_RegDeleteTreeW
0x18002219c  mov     ebx, eax
0x18002219e  test    eax, 0FFFFFFFDh
0x1800221a3  jz      short loc_1800221AC
0x1800221a5  test    eax, eax
0x1800221a7  jmp     loc_18002208F
0x1800221ac  mov     rcx, [rbp+arg_0]; hKey
0x1800221b0  lea     rax, [rbp+arg_10]
0x1800221b4  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x1800221b9  lea     rdx, aSettings_0; "Settings"
0x1800221c0  mov     [rsp+60h+phkResult], rax; phkResult
0x1800221c5  xor     r9d, r9d; lpClass
0x1800221c8  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800221cd  xor     r8d, r8d; Reserved
0x1800221d0  mov     [rsp+60h+samDesired], r14d; samDesired
0x1800221d5  mov     [rsp+60h+dwOptions], esi; dwOptions
0x1800221d9  call    cs:__imp_RegCreateKeyExW
0x1800221df  mov     ebx, eax
0x1800221e1  test    eax, eax
0x1800221e3  jnz     loc_18002208F
0x1800221e9  mov     rcx, [rbp+arg_10]; hKey
0x1800221ed  lea     rdx, [rdi+648h]; struct RtlNameValueArray *
0x1800221f4  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x1800221f9  mov     ebx, eax
0x1800221fb  test    eax, eax
0x1800221fd  js      loc_180022287
0x180022203  mov     rcx, [rbp+arg_0]; hKey
0x180022207  lea     rdx, aQueryparameter; "QueryParameters"
0x18002220e  call    cs:__imp_RegDeleteTreeW
0x180022214  mov     ebx, eax
0x180022216  test    eax, 0FFFFFFFDh
0x18002221b  jnz     short loc_1800221A5
0x18002221d  mov     rcx, [rbp+arg_0]; hKey
0x180022221  lea     rax, [rbp+arg_8]
0x180022225  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18002222a  lea     rdx, aQueryparameter; "QueryParameters"
0x180022231  mov     [rsp+60h+phkResult], rax; phkResult
0x180022236  xor     r9d, r9d; lpClass
0x180022239  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002223e  xor     r8d, r8d; Reserved
0x180022241  mov     [rsp+60h+samDesired], r14d; samDesired
0x180022246  mov     [rsp+60h+dwOptions], esi; dwOptions
0x18002224a  call    cs:__imp_RegCreateKeyExW
0x180022250  mov     ebx, eax
0x180022252  test    eax, eax
0x180022254  jnz     loc_18002208F
0x18002225a  mov     rcx, [rbp+arg_8]; hKey
0x18002225e  lea     rdx, [rdi+678h]; struct RtlNameValueArray *
0x180022265  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x18002226a  mov     ebx, eax
0x18002226c  test    eax, eax
0x18002226e  js      short loc_180022287
0x180022270  mov     rcx, [rbp+arg_8]; hKey
0x180022274  lea     rdx, [rdi+6A8h]; struct RtlNameValueArray *
0x18002227b  call    ?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)
0x180022280  test    eax, eax
0x180022282  mov     ebx, eax
0x180022284  cmovns  ebx, esi
0x180022287  mov     rcx, [rbp+arg_8]; hKey
0x18002228b  test    rcx, rcx
0x18002228e  jz      short loc_180022296
0x180022290  call    cs:__imp_RegCloseKey
0x180022296  mov     rcx, [rbp+arg_10]; hKey
0x18002229a  test    rcx, rcx
0x18002229d  jz      short loc_1800222A5
0x18002229f  call    cs:__imp_RegCloseKey
0x1800222a5  mov     rcx, [rbp+arg_0]; hKey
0x1800222a9  test    rcx, rcx
0x1800222ac  jz      short loc_1800222B4
0x1800222ae  call    cs:__imp_RegCloseKey
0x1800222b4  mov     rcx, [rbp+arg_18]; hKey
0x1800222b8  test    rcx, rcx
0x1800222bb  jz      short loc_1800222C3
0x1800222bd  call    cs:__imp_RegCloseKey
0x1800222c3  mov     rcx, [rbp+hKey]; hKey
0x1800222c7  test    rcx, rcx
0x1800222ca  jz      short loc_1800222D2
0x1800222cc  call    cs:__imp_RegCloseKey
0x1800222d2  mov     eax, ebx
0x1800222d4  add     rsp, 60h
0x1800222d8  pop     r14
0x1800222da  pop     rdi
0x1800222db  pop     rsi
0x1800222dc  pop     rbx
0x1800222dd  pop     rbp
0x1800222de  retn
```
