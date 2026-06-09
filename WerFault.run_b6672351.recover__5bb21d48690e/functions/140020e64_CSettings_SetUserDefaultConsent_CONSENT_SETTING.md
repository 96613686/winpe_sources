# CSettings::SetUserDefaultConsent(_CONSENT_SETTING)

- ea: `0x140020e64`
- end: `0x140020f4d`
- name: `?SetUserDefaultConsent@CSettings@@SAJW4_CONSENT_SETTING@@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020118`

## callees

- `0x14000551c`
- `0x140020e64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020f31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140020f31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140020f15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140020f15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140020ec8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140020ec8`

## pseudocode

```c
__int64 __fastcall CSettings::SetUserDefaultConsent(int a1)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v3; // ebx
  bool v4; // cc
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1;
  if ( (unsigned int)(a1 - 1) > 3 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    Key = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Consent",
            0,
            0,
            0,
            0x20106u,
            0,
            phkResult,
            0);
    v3 = Key;
    v4 = Key <= 0;
    if ( Key
      || (Key = RegSetValueExW(hKey, L"DefaultConsent", 0, 4u, (const BYTE *)&Data, 4u), v3 = Key, v4 = Key <= 0, Key) )
    {
      if ( !v4 )
        v3 = (unsigned __int16)Key | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140020e64  push    rbx
0x140020e66  sub     rsp, 50h
0x140020e6a  lea     eax, [rcx-1]
0x140020e6d  mov     [rsp+58h+hKey], 0
0x140020e76  mov     [rsp+58h+Data], ecx
0x140020e7a  cmp     eax, 3
0x140020e7d  ja      loc_140020F3F
0x140020e83  lea     rcx, [rsp+58h+hKey]
0x140020e88  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140020e8d  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x140020e96  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x140020e9d  mov     [rsp+58h+phkResult], rax; phkResult
0x140020ea2  xor     r9d, r9d; lpClass
0x140020ea5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140020eae  xor     r8d, r8d; Reserved
0x140020eb1  mov     [rsp+58h+samDesired], 20106h; samDesired
0x140020eb9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140020ec0  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140020ec8  call    cs:__imp_RegCreateKeyExW
0x140020ecf  nop     dword ptr [rax+rax+00h]
0x140020ed4  mov     ebx, eax
0x140020ed6  test    eax, eax
0x140020ed8  jz      short loc_140020EF1
0x140020eda  jle     short loc_140020EE5
0x140020edc  movzx   ebx, ax
0x140020edf  or      ebx, 80070000h
0x140020ee5  test    ebx, ebx
0x140020ee7  mov     eax, 80004005h
0x140020eec  cmovns  ebx, eax
0x140020eef  jmp     short loc_140020F27
0x140020ef1  mov     rcx, [rsp+58h+hKey]; hKey
0x140020ef6  lea     rax, [rsp+58h+Data]
0x140020efb  mov     r9d, 4; dwType
0x140020f01  lea     rdx, ValueName; "DefaultConsent"
0x140020f08  mov     [rsp+58h+samDesired], r9d; cbData
0x140020f0d  xor     r8d, r8d; Reserved
0x140020f10  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x140020f15  call    cs:__imp_RegSetValueExW
0x140020f1c  nop     dword ptr [rax+rax+00h]
0x140020f21  mov     ebx, eax
0x140020f23  test    eax, eax
0x140020f25  jnz     short loc_140020EDA
0x140020f27  mov     rcx, [rsp+58h+hKey]; hKey
0x140020f2c  test    rcx, rcx
0x140020f2f  jz      short loc_140020F44
0x140020f31  call    cs:__imp_RegCloseKey
0x140020f38  nop     dword ptr [rax+rax+00h]
0x140020f3d  jmp     short loc_140020F44
0x140020f3f  mov     ebx, 80070057h
0x140020f44  mov     eax, ebx
0x140020f46  add     rsp, 50h
0x140020f4a  pop     rbx
0x140020f4b  retn
```
