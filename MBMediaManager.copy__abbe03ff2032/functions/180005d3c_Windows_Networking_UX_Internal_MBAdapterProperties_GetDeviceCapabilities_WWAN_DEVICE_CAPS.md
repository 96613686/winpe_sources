# Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities(_WWAN_DEVICE_CAPS)

- ea: `0x180005d3c`
- end: `0x180005fb7`
- name: `?GetDeviceCapabilities@MBAdapterProperties@Internal@UX@Networking@Windows@@AEAAXU_WWAN_DEVICE_CAPS@@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f94`

## callees

- `0x180005d3c`
- `0x180005fc0`
- `0x18000600c`
- `0x180008c84`
- `0x18000ad20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f2c`

## string_xrefs

- `0x180005f36`: `cached DeviceObject data. _wwanDataClasses=%d, _cellularClass=%d, _voiceClass=%d, _gsmBandClass=%d, _cdmaBandClass=%d, _smsCaps=%d, _controlCaps=%d, _customDataClassName=%ls, _customBandClass=%ls, _deviceID=%ls, _manufacturer=%ls, _model=%ls, _firmwareInfo=%ls`
- `0x180005e41`: `Failed to cache the DeviceId. DeviceID=%ls`
- `0x180005dab`: `Failed to cache the CustomDataClass name. CustomDataClass=%ls`
- `0x180005e03`: `Failed to cache the CustomBandClass. CustomBandClass=%ls`
- `0x180005e6a`: `Failed to cache the Manufacturer. Manufacturer=%ls`
- `0x180005e98`: `Failed to cache the Model. Model=%ls`
- `0x180005ecc`: `Failed to cache the FirmwareInfo. FirmwareInfo=%ls`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // r8
  const wchar_t *StringRawBuffer; // r14
  const wchar_t *v8; // rbp
  const wchar_t *v9; // rsi
  const wchar_t *v10; // rdi
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rax

  v2 = -1;
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 4);
  *(_DWORD *)(a1 + 44) = *(_DWORD *)(a2 + 8);
  v5 = -1;
  *(_DWORD *)(a1 + 48) = *(_DWORD *)(a2 + 16);
  do
    ++v5;
  while ( *(_WORD *)(a2 + 2 * v5 + 20) );
  if ( v5 > 0xFFFFFFFF
    || Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 56), (const unsigned __int16 *)(a2 + 20), v5) < 0 )
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x111u,
      "Failed to cache the CustomDataClass name. CustomDataClass=%ls",
      (const wchar_t *)(a2 + 20));
  }
  v6 = -1;
  *(_DWORD *)(a1 + 64) = *(_DWORD *)(a2 + 44);
  *(_DWORD *)(a1 + 68) = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(a2 + 92);
  *(_DWORD *)(a1 + 84) = *(_DWORD *)(a2 + 96);
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6 + 52) );
  if ( v6 > 0xFFFFFFFF
    || Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 72), (const unsigned __int16 *)(a2 + 52), v6) < 0 )
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x11Bu,
      "Failed to cache the CustomBandClass. CustomBandClass=%ls",
      (const wchar_t *)(a2 + 52));
  }
  do
    ++v2;
  while ( *(_WORD *)(a2 + 2 * v2 + 100) );
  if ( v2 > 0xFFFFFFFF
    || Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 88), (const unsigned __int16 *)(a2 + 100), v2) < 0 )
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x120u,
      "Failed to cache the DeviceId. DeviceID=%ls",
      (const wchar_t *)(a2 + 100));
  }
  if ( Microsoft::WRL::Wrappers::HString::Set<32>((HSTRING *)(a1 + 96), (PCNZWCH)(a2 + 136)) < 0 )
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x125u,
      "Failed to cache the Manufacturer. Manufacturer=%ls",
      (const wchar_t *)(a2 + 136));
  if ( Microsoft::WRL::Wrappers::HString::Set<32>((HSTRING *)(a1 + 104), (PCNZWCH)(a2 + 200)) < 0 )
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x12Au,
      "Failed to cache the Model. Model=%ls",
      (const wchar_t *)(a2 + 200));
  if ( Microsoft::WRL::Wrappers::HString::Set<32>((HSTRING *)(a1 + 112), (PCNZWCH)(a2 + 264)) < 0 )
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
      0x12Fu,
      "Failed to cache the FirmwareInfo. FirmwareInfo=%ls",
      (const wchar_t *)(a2 + 264));
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 112), 0);
  v8 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 104), 0);
  v9 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 96), 0);
  v10 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 88), 0);
  v11 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 72), 0);
  v12 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 56), 0);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBAdapterProperties::GetDeviceCapabilities",
    323,
    "cached DeviceObject data. _wwanDataClasses=%d, _cellularClass=%d, _voiceClass=%d, _gsmBandClass=%d, _cdmaBandClass=%"
    "d, _smsCaps=%d, _controlCaps=%d, _customDataClassName=%ls, _customBandClass=%ls, _deviceID=%ls, _manufacturer=%ls, _"
    "model=%ls, _firmwareInfo=%ls",
    *(_DWORD *)(a1 + 48),
    *(_DWORD *)(a1 + 40),
    *(_DWORD *)(a1 + 44),
    *(_DWORD *)(a1 + 64),
    *(_DWORD *)(a1 + 68),
    *(_DWORD *)(a1 + 80),
    *(_DWORD *)(a1 + 84),
    v12,
    v11,
    v10,
    v9,
    v8,
    StringRawBuffer);
}

```

## disassembly

```asm
0x180005d3c  mov     [rsp+arg_10], rbx
0x180005d41  push    rbp
0x180005d42  push    rsi
0x180005d43  push    rdi
0x180005d44  push    r12
0x180005d46  push    r13
0x180005d48  push    r14
0x180005d4a  push    r15
0x180005d4c  sub     rsp, 80h
0x180005d53  mov     eax, [rdx+4]
0x180005d56  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005d5a  mov     [rcx+28h], eax
0x180005d5d  mov     rbx, rdx
0x180005d60  mov     eax, [rdx+8]
0x180005d63  mov     r15, rcx
0x180005d66  mov     [rcx+2Ch], eax
0x180005d69  mov     r8, rdi
0x180005d6c  mov     eax, [rdx+10h]
0x180005d6f  xor     ebp, ebp
0x180005d71  mov     [rcx+30h], eax
0x180005d74  inc     r8; unsigned int
0x180005d77  cmp     [rdx+r8*2+14h], bp
0x180005d7d  jnz     short loc_180005D74
0x180005d7f  mov     r12d, 0FFFFFFFFh
0x180005d85  lea     r14, aWindowsNetwork_257; "Windows::Networking::UX::Internal::MBAd"...
0x180005d8c  cmp     r8, r12
0x180005d8f  ja      short loc_180005DA2
0x180005d91  add     rcx, 38h ; '8'; this
0x180005d95  add     rdx, 14h; unsigned __int16 *
0x180005d99  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180005d9e  test    eax, eax
0x180005da0  jns     short loc_180005DBA
0x180005da2  lea     r9, [rbx+14h]
0x180005da6  mov     edx, 111h; unsigned int
0x180005dab  lea     r8, aFailedToCacheT_4; "Failed to cache the CustomDataClass nam"...
0x180005db2  mov     rcx, r14; char *
0x180005db5  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005dba  mov     eax, [rbx+2Ch]
0x180005dbd  mov     r8, rdi
0x180005dc0  mov     [r15+40h], eax
0x180005dc4  mov     eax, [rbx+30h]
0x180005dc7  mov     [r15+44h], eax
0x180005dcb  mov     eax, [rbx+5Ch]
0x180005dce  mov     [r15+50h], eax
0x180005dd2  mov     eax, [rbx+60h]
0x180005dd5  mov     [r15+54h], eax
0x180005dd9  inc     r8; unsigned int
0x180005ddc  cmp     [rbx+r8*2+34h], bp
0x180005de2  jnz     short loc_180005DD9
0x180005de4  cmp     r8, r12
0x180005de7  ja      short loc_180005DFA
0x180005de9  lea     rcx, [r15+48h]; this
0x180005ded  lea     rdx, [rbx+34h]; unsigned __int16 *
0x180005df1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180005df6  test    eax, eax
0x180005df8  jns     short loc_180005E12
0x180005dfa  lea     r9, [rbx+34h]
0x180005dfe  mov     edx, 11Bh; unsigned int
0x180005e03  lea     r8, aFailedToCacheT; "Failed to cache the CustomBandClass. Cu"...
0x180005e0a  mov     rcx, r14; char *
0x180005e0d  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005e12  inc     rdi
0x180005e15  cmp     [rbx+rdi*2+64h], bp
0x180005e1a  jnz     short loc_180005E12
0x180005e1c  cmp     rdi, r12
0x180005e1f  lea     r12, [r15+58h]
0x180005e23  ja      short loc_180005E38
0x180005e25  mov     r8d, edi; unsigned int
0x180005e28  lea     rdx, [rbx+64h]; unsigned __int16 *
0x180005e2c  mov     rcx, r12; this
0x180005e2f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180005e34  test    eax, eax
0x180005e36  jns     short loc_180005E50
0x180005e38  lea     r9, [rbx+64h]
0x180005e3c  mov     edx, 120h; unsigned int
0x180005e41  lea     r8, aFailedToCacheT_2; "Failed to cache the DeviceId. DeviceID="...
0x180005e48  mov     rcx, r14; char *
0x180005e4b  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005e50  lea     rdi, [rbx+88h]
0x180005e57  mov     rdx, rdi; sourceString
0x180005e5a  lea     rcx, [r15+60h]; string
0x180005e5e  call    ??$Set@$0CA@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0CA@G@Z; Microsoft::WRL::Wrappers::HString::Set<32>(ushort (&)[32])
0x180005e63  test    eax, eax
0x180005e65  jns     short loc_180005E7E
0x180005e67  mov     r9, rdi
0x180005e6a  lea     r8, aFailedToCacheT_0; "Failed to cache the Manufacturer. Manuf"...
0x180005e71  mov     edx, 125h; unsigned int
0x180005e76  mov     rcx, r14; char *
0x180005e79  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005e7e  lea     rdi, [rbx+0C8h]
0x180005e85  mov     rdx, rdi; sourceString
0x180005e88  lea     rcx, [r15+68h]; string
0x180005e8c  call    ??$Set@$0CA@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0CA@G@Z; Microsoft::WRL::Wrappers::HString::Set<32>(ushort (&)[32])
0x180005e91  test    eax, eax
0x180005e93  jns     short loc_180005EAC
0x180005e95  mov     r9, rdi
0x180005e98  lea     r8, aFailedToCacheT_1; "Failed to cache the Model. Model=%ls"
0x180005e9f  mov     edx, 12Ah; unsigned int
0x180005ea4  mov     rcx, r14; char *
0x180005ea7  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005eac  lea     rdx, [rbx+108h]; sourceString
0x180005eb3  lea     rcx, [r15+70h]; string
0x180005eb7  call    ??$Set@$0CA@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0CA@G@Z; Microsoft::WRL::Wrappers::HString::Set<32>(ushort (&)[32])
0x180005ebc  test    eax, eax
0x180005ebe  jns     short loc_180005EDB
0x180005ec0  lea     r9, [rbx+108h]
0x180005ec7  mov     edx, 12Fh; unsigned int
0x180005ecc  lea     r8, aFailedToCacheT_3; "Failed to cache the FirmwareInfo. Firmw"...
0x180005ed3  mov     rcx, r14; char *
0x180005ed6  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180005edb  mov     rcx, [r15+70h]; string
0x180005edf  xor     edx, edx; length
0x180005ee1  call    cs:__imp_WindowsGetStringRawBuffer
0x180005ee7  mov     rcx, [r15+68h]; string
0x180005eeb  xor     edx, edx; length
0x180005eed  mov     r14, rax
0x180005ef0  call    cs:__imp_WindowsGetStringRawBuffer
0x180005ef6  mov     rcx, [r15+60h]; string
0x180005efa  xor     edx, edx; length
0x180005efc  mov     rbp, rax
0x180005eff  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f05  mov     rcx, [r12]; string
0x180005f09  xor     edx, edx; length
0x180005f0b  mov     rsi, rax
0x180005f0e  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f14  mov     rcx, [r15+48h]; string
0x180005f18  xor     edx, edx; length
0x180005f1a  mov     rdi, rax
0x180005f1d  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f23  mov     rcx, [r15+38h]; string
0x180005f27  xor     edx, edx; length
0x180005f29  mov     rbx, rax
0x180005f2c  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f32  mov     r9d, [r15+30h]
0x180005f36  lea     r8, aCachedDeviceob; "cached DeviceObject data. _wwanDataClas"...
0x180005f3d  mov     [rsp+0B8h+var_40], r14
0x180005f42  lea     rcx, aWindowsNetwork_257; "Windows::Networking::UX::Internal::MBAd"...
0x180005f49  mov     [rsp+0B8h+var_48], rbp
0x180005f4e  mov     edx, 143h; unsigned int
0x180005f53  mov     [rsp+0B8h+var_50], rsi
0x180005f58  mov     [rsp+0B8h+var_58], rdi
0x180005f5d  mov     [rsp+0B8h+var_60], rbx
0x180005f62  mov     [rsp+0B8h+var_68], rax
0x180005f67  mov     eax, [r15+54h]
0x180005f6b  mov     [rsp+0B8h+var_70], eax
0x180005f6f  mov     eax, [r15+50h]
0x180005f73  mov     [rsp+0B8h+var_78], eax
0x180005f77  mov     eax, [r15+44h]
0x180005f7b  mov     [rsp+0B8h+var_80], eax
0x180005f7f  mov     eax, [r15+40h]
0x180005f83  mov     [rsp+0B8h+var_88], eax
0x180005f87  mov     eax, [r15+2Ch]
0x180005f8b  mov     [rsp+0B8h+var_90], eax
0x180005f8f  mov     eax, [r15+28h]
0x180005f93  mov     [rsp+0B8h+var_98], eax
0x180005f97  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180005f9c  mov     rbx, [rsp+0B8h+arg_10]
0x180005fa4  add     rsp, 80h
0x180005fab  pop     r15
0x180005fad  pop     r14
0x180005faf  pop     r13
0x180005fb1  pop     r12
0x180005fb3  pop     rdi
0x180005fb4  pop     rsi
0x180005fb5  pop     rbp
0x180005fb6  retn
```
